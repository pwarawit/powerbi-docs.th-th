---
title: ความสามารถ
description: ความสามารถและคุณสมบัติของการแสดงภาพ Power BI
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: f6bb4293a44f98f2f8098fb197c7b406b618d211
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425470"
---
# <a name="power-bi-visual-capabilities"></a>ความสามารถของการแสดงภาพ Power BI

ความสามารถในการให้ข้อมูลกับโฮสต์เกี่ยวกับการแสดงภาพของคุณ คุณสมบัติทั้งหมดบนแบบจำลองความสามารถเป็น `optional`

วัตถุรากของความสามารถของการแสดงภาพคือ `dataRoles`, `dataViewMappings`, และอื่น ๆ

```json
{
    "dataRoles": [ ... ],
    "dataViewMappings": [ ... ],
    "objects":  { ... },
    "supportsHighlight": true|false,
    "advancedEditModeSupport": 0|1|2,
    "sorting": { ... }
}

```

## <a name="define-the-data-fields-your-visual-expects---dataroles"></a>กำหนดเขตข้อมูลของการแสดงผลด้วยภาพของคุณ - `dataRoles`

หากต้องการกำหนดเขตข้อมูลที่สามารถผูกกับข้อมูลเรา เราใช้ `dataRoles` ซึ่งใช้อาร์เรย์ของ `DataViewRole` วัตถุ ซึ่งกำหนดคุณสมบัติทั้งหมดที่จำเป็น

### <a name="properties"></a>คุณสมบัติ

* **ชื่อ** - ชื่อภายในของเขตข้อมูลนี้ (ต้องไม่ซ้ำกัน)
* **ชนิด** - ชนิดของเขตข้อมูล:
    * `Grouping` - แยกค่าที่ใช้เป็นส่วนชัดสำหรับการจัดกลุ่มเขตข้อมูลการวัด
    * `Measure` - ค่าข้อมูลตัวเลข
    * `GroupingOrMeasure` - สามารถใช้เป็นกลุ่มหรือการวัด
* **displayName** - ชื่อที่แสดงให้กับผู้ใช้ในบานหน้าต่างคุณสมบัติ
* **คำอธิบาย** - คำอธิบายแบบสั้นของเขตข้อมูล (ไม่บังคับ)
* **requiredTypes** - ชนิดของข้อมูลที่จำเป็นสำหรับบทบาทข้อมูลนี้ มูลค่าใด ๆ ที่ไม่ตรงกันจะถูกกำหนดเป็น null (ไม่บังคับ)
* **preferredTypes** - ชนิดของข้อมูลที่ต้องการสำหรับบทบาทข้อมูลนี้ (ไม่บังคับ)

### <a name="valid-data-types-in-requiredtypes-and-preferredtypes"></a>ชนิดข้อมูลที่ถูกต้องใน "requiredTypes" และ "preferredTypes"

* **bool** - ค่าบูลีนไม่ถูกต้อง
* **จำนวนเต็ม** - ค่าจำนวนเต็ม (จำนวนเต็ม)
* **ตัวเลข** - ค่าตัวเลข
* **ข้อความ** - ค่าข้อความ
* **ภูมิศาสตร์** - ข้อมูลทางภูมิศาสตร์

### <a name="example"></a>ตัวอย่าง:

```json
"dataRoles": [
    {
        "displayName": "My Category Data",
        "name": "myCategory",
        "kind": "Grouping",
        "requiredTypes": [
            {
                "text": true
            },
            {
                "numeric": true
            },
            {
                "integer": true
            }
        ],
        "preferredTypes": [
            {
                "text": true
            }
        ]
    },
    {
        "displayName": "My Measure Data",
        "name": "myMeasure",
        "kind": "Measure",
        "requiredTypes": [
            {
                "integer": true
            },
            {
                "numeric": true
            }
        ],
        "preferredTypes": [
            {
                "integer": true
            }
        ]
    },
    {
        "displayNameKey": "Visual_Location",
        "name": "Locations",
        "kind": "Measure",
        "displayName": "Locations",
        "requiredTypes": [
            {
                "geography": {
                    "address": true
                }
            },
            {
                "geography": {
                    "city": true
                }
            },
            {
                "geography": {
                    "continent": true
                }
            },
            {
                "geography": {
                    "country": true
                }
            },
            {
                "geography": {
                    "county": true
                }
            },
            {
                "geography": {
                    "place": true
                }
            },
            {
                "geography": {
                    "postalCode": true
                }
            },
            {
                "geography": {
                    "region": true
                }
            },
            {
                "geography": {
                    "stateOrProvince": true
                }
            }
        ]
    }
]
```

บทบาทข้อมูลข้างต้นจะสร้างเขตข้อมูลต่อไปนี้

![การแสดงบทบาทข้อมูล](./media/data-role-display.png)

## <a name="define-how-you-want-the-data-mapped---dataviewmappings"></a>กำหนดวิธีที่คุณต้องการแมปข้อมูล - `dataViewMappings`

DataViewMapping จะอธิบายว่าบทบาทข้อมูลเกี่ยวข้องกันอย่างไรและอนุญาตให้คุณระบุข้อกำหนดเงื่อนไขสำหรับบทบาทดังกล่าวได้

การแสดงภาพส่วนใหญ่ให้การแมปเดียวแต่คุณสามารถใส่หลาย dataViewMappings ได้ แต่ละการแมปที่ถูกต้องจะสร้าง DataView 

```json
"dataViewMappings": [
    {
        "conditions": [ ... ],
        "categorical": { ... },
        "table": { ... },
        "single": { ... },
        "matrix": { ... }
    }
]
```

[เรียนรู้เพิ่มเติมเกี่ยวกับ DataViewMappings](dataview-mappings.md)

## <a name="define-property-pane-options---objects"></a>กำหนดตัวเลือกบานหน้าต่างคุณสมบัติ - `objects`

วัตถุอธิบายคุณสมบัติแบบปรับแต่งได้ที่เกี่ยวข้องกับการแสดงภาพ
วัตถุแต่ละชนิดสามารถมีคุณสมบัติได้หลายรายการและแต่ละคุณสมบัติมีชนิดที่สัมพันธ์กัน
ชนิดอ้างอิงถึงสิ่งที่คุณสมบัติจะเป็น โปรดดูด้านล่างสำหรับข้อมูลเพิ่มเติมเกี่ยวกับการ ชนิด

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

[เรียนรู้เพิ่มเติมเกี่ยวกับ วัตถุ ](objects-properties.md)

## <a name="handle-partial-highlighting---supportshighlight"></a>จัดการการเน้นบางส่วน - `supportsHighlight`

ตามค่าเริ่มต้นค่านี้จะถูกตั้งค่าเป็น false ซึ่งหมายความว่า "ค่า" ของคุณจะได้รับการกรองโดยอัตโนมัติเมื่อมีการเลือกบางสิ่งในหน้าเว็บที่จะทำการอัปเดตการแสดงภาพของคุณเพื่อแสดงเฉพาะค่าที่เลือกไว้ ถ้าคุณต้องการแสดงข้อมูลทั้งหมด เพียงแค่เน้นรายการที่คุณต้องการเพื่อตั้งค่า `supportsHighlight` เป็น true ใน capabilities.json

[เรียนรู้เพิ่มเติมเกี่ยวกับการเน้น](highlight.md)

## <a name="handle-advanced-edit-mode---advancededitmodesupport"></a>จัดการโหมดการแก้ไขขั้นสูง - `advancedEditModeSupport`

ภาพสามารถประกาศการสนับสนุนของโหมดแก้ไขขั้นสูง
ตามค่าเริ่มต้นการแสดงภาพไม่สนับสนุนโหมดแก้ไขขั้นสูง เว้นแต่ว่าจะมีการระบุไว้เป็นอย่างอื่นใน capabilities json

[เรียนรู้เพิ่มเติมเกี่ยวกับ advancedEditModeSupport](advanced-edit-mode.md)

## <a name="data-sorting-options-for-visual---sorting"></a>ตัวเลือกการเรียงลำดับข้อมูลสำหรับการแสดงผลด้วยภาพ - `sorting`

การแสดงผลด้วยภาพสามารถกำหนดพฤติกรรมการเรียงลำดับผ่านความสามารถ
ตามค่าเริ่มต้นการแสดงผลด้วยภาพไม่รองรับการแก้ไขลำดับการเรียงลำดับยกเว้นจะระบบไว้เป็นอย่างอื่นใน capabilities.json

[เรียนรู้เพิ่มเติมเกี่ยวกับการเรียงลำดับ](sort-options.md)

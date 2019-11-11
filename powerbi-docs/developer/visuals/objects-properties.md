---
title: ออบเจ็กต์และคุณสมบัติของวิชวล Power BI
description: บทความนี้อธิบายคุณสมบัติแบบปรับแต่งได้ของวิชวล Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: ae548abd0d579414a69b0d970213ff9d69ff2f08
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/09/2019
ms.locfileid: "73879856"
---
# <a name="objects-and-properties-of-power-bi-visuals"></a>ออบเจ็กต์และคุณสมบัติของวิชวล Power BI

ออบเจ็กต์อธิบายคุณสมบัติแบบปรับแต่งได้ที่เกี่ยวข้องกับวิชวล ออบเจ็กต์สามารถมีคุณสมบัติได้หลายรายการ และแต่ละคุณสมบัติมีประเภทที่เกี่ยวข้องซึ่งอธิบายถึงคุณสมบัติที่จะเป็น บทความนี้ให้ข้อมูลเกี่ยวกับออบเจ็กต์และชนิดของคุณสมบัติ

`myCustomObject` เป็นชื่อภายในที่ใช้เพื่ออ้างอิงออบเจ็กต์ภายใน `dataView` และ `enumerateObjectInstances`

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

## <a name="display-name"></a>ชื่อที่แสดง

`displayName` คือชื่อที่จะแสดงในบานหน้าต่างคุณสมบัติ

## <a name="properties"></a>คุณสมบัติ

`properties` เป็นแผนที่ของคุณสมบัติที่กำหนดโดยผู้พัฒนา

```json
"properties": {
    "myFirstProperty": {
        "displayName": "firstPropertyName",
        "type": ValueTypeDescriptor | StructuralTypeDescriptor
    }
}
```

> [!NOTE]
> `show` เป็นคุณสมบัติพิเศษที่เปิดใช้งานสวิตช์เพื่อสลับวัตถุ

ตัวอย่าง:

```json
"properties": {
    "show": {
        "displayName": "My Property Switch",
        "type": {"bool": true}
    }
}
```

### <a name="property-types"></a>ชนิดของคุณสมบัติ

มีชนิดของคุณสมบัติสองชนิด: `ValueTypeDescriptor` และ `StructuralTypeDescriptor`

#### <a name="value-type-descriptor"></a>ตัวอธิบายชนิดค่า

ส่วนใหญ่ `ValueTypeDescriptor` เป็นชนิดพื้นฐาน และโดยปกติแล้วจะเป็นออบเจ็กต์แบบสแตติก

ต่อไปนี้เป็นองค์ประกอบส่วนหนึ่งของ `ValueTypeDescriptor` แบบทั่วไป

```typescript
export interface ValueTypeDescriptor {
    text?: boolean;
    numeric?: boolean;
    integer?: boolean;
    bool?: boolean;
}
```

#### <a name="structural-type-descriptor"></a>ตัวอธิบายชนิดโครงสร้าง

ส่วนใหญ่ `StructuralTypeDescriptor` จะใช้สำหรับออบเจ็กต์ที่ผูกกับข้อมูล
ชนิด `StructuralTypeDescriptor` ที่พบมากที่สุดคือ *การใส่สีพื้นหลัง*

```typescript
export interface StructuralTypeDescriptor {
    fill?: FillTypeDescriptor;
}
```

## <a name="gradient-property"></a>คุณสมบัติการไล่ระดับสี

คุณสมบัติการไล่ระดับสีเป็นคุณสมบัติที่ไม่สามารถกำหนดเป็นคุณสมบัติมาตรฐานได้ แต่คุณจำเป็นต้องกำหนดกฎสำหรับการแทนที่คุณสมบัติตัวเลือกสี (ชนิด *การใส่สีพื้นหลัง*)

ตัวอย่างจะแสดงในโค้ดต่อไปนี้:

```json
"properties": {
    "showAllDataPoints": {
        "displayName": "Show all",
        "displayNameKey": "Visual_DataPoint_Show_All",
        "type": {
            "bool": true
        }
    },
    "fill": {
        "displayName": "Fill",
        "displayNameKey": "Visual_Fill",
        "type": {
            "fill": {
                "solid": {
                    "color": true
                }
            }
        }
    },
    "fillRule": {
        "displayName": "Color saturation",
        "displayNameKey": "Visual_ColorSaturation",
        "type": {
            "fillRule": {}
        },
        "rule": {
            "inputRole": "Gradient",
            "output": {
                "property": "fill",
                    "selector": [
                        "Category"
                    ]
            }
        }
    }
}
```

กรุณาใส่ใจกับคุณสมบัติ *การใส่สีพื้นหลัง* และ *กฎการใส่สีพื้นหลัง* อันดับแรกคือตัวเลือกสี และอันดับที่สองคือกฎการทดแทนสำหรับการไล่ระดับสีที่จะแทนที่ *คุณสมบัติ การใส่สีพื้นหลัง*, `visually` เมื่อเป็นไปตามเงื่อนไขของกฎ

คุณสามารถตั้งค่าการเชื่อมโยงระหว่างคุณสมบัติ *การใส่สีพื้นหลัง* และกฎการแทนที่ได้ในส่วน `"rule"`>`"output"` ของคุณสมบัติ *กฎการใส่สีพื้นหลัง*

คุณสมบัติ `"Rule"`>`"InputRole"` กำหนดบทบาทข้อมูลที่ทริกเกอร์กฎ (เงื่อนไข) ในตัวอย่างนี้ ถ้าบทบาทข้อมูล `"Gradient"` ประกอบด้วยข้อมูลแล้ว กฏจะถูกนำไปใช้กับคุณสมบัติ `"fill"`

ตัวอย่างของบทบาทข้อมูลที่ทริกเกอร์กฎ การใส่สีพื้นหลัง (`the last item`) จะแสดงในโค้ดต่อไปนี้:

```json
{
    "dataRoles": [
            {
                "name": "Category",
                "kind": "Grouping",
                "displayName": "Details",
                "displayNameKey": "Role_DisplayName_Details"
            },
            {
                "name": "Series",
                "kind": "Grouping",
                "displayName": "Legend",
                "displayNameKey": "Role_DisplayName_Legend"
            },
            {
                "name": "Gradient",
                "kind": "Measure",
                "displayName": "Color saturation",
                "displayNameKey": "Role_DisplayName_Gradient"
            }
    ]
}
```

## <a name="the-enumerateobjectinstances-method"></a>เมธอด enumerateObjectInstances

ในการใช้ออบเจ็กต์อย่างมีประสิทธิภาพ คุณจะต้องมีฟังก์ชันในวิชวลแบบกำหนดเองของคุณที่เรียกว่า `enumerateObjectInstances` ฟังก์ชันนี้จะเติมข้อมูลในบานหน้าต่างคุณสมบัติที่มีออบเจ็กต์และจะกำหนดตำแหน่งที่ออบเจ็กต์ของคุณควรถูกผูกไว้ภายใน dataView  

นี่คือลักษณะการตั้งค่าทั่วไป:

```typescript
public enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstanceEnumeration {
    let objectName: string = options.objectName;
    let objectEnumeration: VisualObjectInstance[] = [];

    switch( objectName ) {
        case 'myCustomObject':
            objectEnumeration.push({
                objectName: objectName,
                properties: { ... },
                selector: { ... }
            });
            break;
    };

    return objectEnumeration;
}
```

### <a name="properties"></a>คุณสมบัติ

คุณสมบัติใน `enumerateObjectInstances` จะสะท้อนคุณสมบัติที่คุณกำหนดไว้ในความสามารถของคุณ สำหรับตัวอย่าง ให้ไปที่ส่วนท้ายของบทความนี้

### <a name="objects-selector"></a>ตัวเลือกวัตถุ

ตัวเลือกใน `enumerateObjectInstances` กำหนดตำแหน่งที่แต่ละออบเจ็กต์จะถูกผูกไว้ใน dataView มีสี่ตัวเลือกที่แตกต่างกัน

#### <a name="static"></a>คงที่

ออบเจ็กต์นี้ถูกผูกกับเมตาดาต้า `dataviews[index].metadata.objects` ดังที่แสดงไว้ที่นี่

```typescript
selector: null
```

#### <a name="columns"></a>คอลัมน์

ออบเจ็กต์นี้จะผูกกับคอลัมน์ที่มีการจับคู่ `QueryName`

```typescript
selector: {
    metadata: 'QueryName'
}
```

#### <a name="selector"></a>ตัวเลือก

ออบเจ็กต์นี้จะผูกกับองค์ประกอบที่คุณได้สร้าง `selectionID` ขึ้น ในตัวอย่างนี้ ให้สมมติว่าเราได้สร้าง `selectionID` ขึ้นสำหรับบางจุดข้อมูล และเราจะวนลูปผ่านจุดข้อมูลดังกล่าว

```typescript
for (let dataPoint in dataPoints) {
    ...
    selector: dataPoint.selectionID.getSelector()
}
```

#### <a name="scope-identity"></a>ข้อมูลเฉพาะตัวของขอบเขต

ออบเจ็กต์นี้จะผูกกับค่าเฉพาะที่จุดตัดของกลุ่ม ตัวอย่างเช่น ถ้าคุณมีข้อมูลจัดกลุ่ม `["Jan", "Feb", "March", ...]` และชุดข้อมูล `["Small", "Medium", "Large"]` คุณอาจต้องการให้มีออบเจ็กต์บนจุดตัดของค่าที่ตรงกับ `Feb` และ `Large` เมื่อต้องการทำเช่นนี้ คุณจะได้รับค่า `DataViewScopeIdentity` ทั้งสองคอลัมน์ ให้ส่งค่าเหล่านั้นไปยังตัวแปร `identities` และใช้ไวยากรณ์นี้กับตัวเลือก

```typescript
selector: {
    data: <DataViewScopeIdentity[]>identities
}
```

##### <a name="example"></a>ตัวอย่าง:

ตัวอย่างต่อไปนี้แสดงให้เห็นว่า objectEnumeration หนึ่งออบเจ็กต์จะมองหาออบเจ็กต์ customColor ที่มีหนึ่งคุณสมบัติ *การใส่สีพื้นหลัง* หนึ่งค่า เราต้องการให้ออบเจ็กต์นี้ผูกไว้กับ `dataViews[index].metadata.objects` แบบสแตติก ตามที่แสดง:

```typescript
objectEnumeration.push({
    objectName: "customColor",
    displayName: "Custom Color",
    properties: {
        fill: {
            solid: {
                color: dataPoint.color
            }
        }
    },
    selector: null
});
```

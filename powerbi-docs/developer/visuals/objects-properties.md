---
title: วัตถุและคุณสมบัติ
description: คุณสมบัติแบบปรับแต่งได้ของวิชวล Power BI
author: MrMeison
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: c22a1cfb281c9902d490e2320b85c2f6bbb63468
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424619"
---
# <a name="object-and-properties"></a>วัตถุและคุณสมบัติ

วัตถุอธิบายคุณสมบัติแบบปรับแต่งได้ที่เชื่อมโยงกับวิชวล
แต่ละวัตถุสามารถมีคุณสมบัติได้หลายรายการและแต่ละคุณสมบัติมีชนิดที่สัมพันธ์กัน
ชนิดอ้างอิงถึงสิ่งที่คุณสมบัติจะเป็น โปรดดูด้านล่างสำหรับข้อมูลเพิ่มเติมเกี่ยวกับการ ชนิด

`myCustomObject` เป็นชื่อภายในที่ใช้เพื่ออ้างอิงวัตถุภายใน `dataView` และ `enumerateObjectInstances`

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

## <a name="display-name"></a>ชื่อที่ใช้แสดง

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

มีชนิดคุณสมบัติสองชนิด: `ValueTypeDescriptor` และ `StructuralTypeDescriptor`

#### <a name="value-type-descriptor"></a>ตัวอธิบายชนิดค่า

ส่วนใหญ่ `ValueTypeDescriptor` เป็นชนิดข้อมูลพื้นฐานและมักใช้เป็นวัตถุแบบสแตติก
ต่อไปนี้เป็นส่วนหนึ่งของ `ValueTypeDescriptor` แบบทั่วไป

```typescript
export interface ValueTypeDescriptor {
    text?: boolean;
    numeric?: boolean;
    integer?: boolean;
    bool?: boolean;
}
```

#### <a name="structural-type-descriptor"></a>ตัวอธิบายชนิดโครงสร้าง

ส่วนใหญ่ `StructuralTypeDescriptor` จะใช้สำหรับวัตถุที่ผูกกับข้อมูล
เติมเป็น `StructuralTypeDescriptor` ที่พบบ่อยที่สุด

```typescript
export interface StructuralTypeDescriptor {
    fill?: FillTypeDescriptor;
}
```

## <a name="gradient-property"></a>คุณสมบัติการไล่ระดับสี

คุณสมบัติการไล่ระดับสีเป็นคุณสมบัติที่ไม่สามารถตั้งค่าเป็นคุณสมบัติมาตรฐานได้ แต่คุณจำเป็นต้องตั้งค่ากฎสำหรับการแทนที่คุณสมบัติตัวเลือกสี (ชนิดเติม)
ดูตัวอย่างด้านล่าง:

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

โปรดให้ความสนใจกับคุณสมบัติ `"fill"` และ `"fillRule"` อันแรกคือตัวเลือกสี อันที่สองคือกฎการแทนที่สำหรับการไล่ระดับที่จะแทนที่คุณสมบัติ `visually`"เติม" เมื่อตรงตามเงื่อนไขของกฎ

คุณสามารถตั้งค่าการเชื่อมโยงระหว่างคุณสมบัติเติมและกฎการแทนที่ได้ในส่วน`"rule"`->`"output"` ของคุณสมบัติ `"fillRule"`

`"Rule"`->`"InputRole"` ตั้งค่าบทบาทข้อมูลที่ทริกเกอร์กฎ (เงื่อนไข) ในตัวอย่างนี้ ถ้าบทบาทข้อมูล `"Gradient"` มีข้อมูล จากนั้นกฏจะถูกนำไปใช้กับคุณสมบัติ `"fill"`

ด้านล่าง คุณสามารถดูตัวอย่างของบทบาทข้อมูลที่ทริกเกอร์กฎเติม (`the last item`)

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

## <a name="enumerateobjectinstances-method"></a>เมธอด `enumerateObjectInstances`

ในการใช้วัตถุอย่างมีประสิทธิภาพ คุณจะต้องมีฟังก์ชันในการแสดงผลด้วยภาพแบบกำหนดเองของคุณที่เรียกว่า `enumerateObjectInstances` ฟังก์ชันนี้จะเติมข้อมูลในบานหน้าต่างคุณสมบัติที่มีวัตถุและจะกำหนดตำแหน่งที่วัตถุของคุณควรถูกผูกไว้ภายใน dataView  

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

คุณสมบัติใน `enumerateObjectInstances` จะสะท้อนคุณสมบัติที่คุณกำหนดไว้ในความสามารถของคุณ ดูตัวอย่างที่ด้านล่างของหน้า

### <a name="objects-selector"></a>ตัวเลือกวัตถุ

ตัวเลือกใน `enumerateObjectInstances` กำหนดตำแหน่งที่แต่ละวัตถุจะถูกผูกไว้ใน dataView มีสี่ตัวเลือกที่แตกต่างกัน

#### <a name="static"></a>คงที่

วัตถุนี้จะผูกกับเมตาดาต้า `dataviews[index].metadata.objects`

```typescript
selector: null
```

#### <a name="columns"></a>คอลัมน์

วัตถุนี้จะผูกกับคอลัมน์ที่มีการจับคู่ `QueryName`

```typescript
selector: {
    metadata: 'QueryName'
}
```

#### <a name="selector"></a>ตัวเลือก

วัตถุนี้จะผูกกับองค์ประกอบที่เราได้สร้าง `selectionID` ขึ้น ในตัวอย่างนี้ เราจะสมมติว่าเราได้สร้าง `selectionID` ขึ้นสำหรับบาง dataPoints และเราจะวนลูปผ่านจุดข้อมูลดังกล่าว

```typescript
for (let dataPoint in dataPoints) {
    ...
    selector: dataPoint.selectionID.getSelector()
}
```

#### <a name="scope-identity"></a>ข้อมูลเฉพาะตัวของขอบเขต

วัตถุนี้จะผูกกับค่าเฉพาะที่จุดตัดของกลุ่ม ตัวอย่างเช่น ถ้าฉันมีข้อมูลจัดกลุ่ม `["Jan", "Feb", "March", ...]`และชุดข้อมูล `["Small", "Medium", "Large"]` ฉันอาจต้องการให้มีวัตถุบนจุดตัดของค่าที่ตรงกับ `Feb` และ `Large` เมื่อต้องการทำเช่นนี้ฉัน`DataViewScopeIdentity`จะได้รับทั้งสองคอลัมน์ให้ส่ง`identities`ไปยังตัวแปรและใช้ไวยากรณ์นี้กับตัวเลือก

```typescript
selector: {
    data: <DataViewScopeIdentity[]>identities
}
```

##### <a name="example"></a>ตัวอย่าง:

ในตัวอย่างนี้ เราแสดงให้เห็นว่า objectEnumeration หนึ่งวัตถุจะมองหาวัตถุ customColor ที่มีหนึ่งคุณสมบัติ `fill` หนึ่งค่า เราต้องการให้วัตถุนี้ผูกไว้กับ `dataViews[index].metadata.objects` แบบคงที่

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

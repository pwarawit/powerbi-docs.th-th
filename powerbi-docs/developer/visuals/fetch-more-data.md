---
title: ดึงข้อมูลเพิ่มเติม
description: เปิดใช้งานเซกเมนต์การดึงข้อมูลชุดข้อมูลขนาดใหญ่สำหรับ Power BI Visuals
author: AviSander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: bc8ff673927fd66bf44164e4e9950c279b98c6c1
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425079"
---
# <a name="fetch-more-data-from-power-bi"></a>ดึงข้อมูลเพิ่มเติมจาก Power BI

โหลด API ข้อมูลเพิ่มเติมเพื่อเอาชนะขีดจำกัดของจุดข้อมูล 30 K ซึ่งจะนำข้อมูลในแบบกลุ่ม ขนาดของกลุ่มจะได้รับการกำหนดค่าเพื่อปรับปรุงประสิทธิภาพการทำงานตามกรณีที่ใช้  

## <a name="enable-segmented-fetch-of-large-datasets"></a>เปิดใช้งานการดึงเซกเมนต์ชุดข้อมูลขนาดใหญ่

สำหรับโหมดเซกเมนต์ `dataview` ให้กำหนด dataReductionAlgorithm "หน้าต่าง" ในการแสดงผล `capabilities.json` สำหรับ dataViewMapping ที่จำเป็น
`count` จะกำหนดขนาดหน้าต่างซึ่งจำกัดจำนวนแถวข้อมูลใหม่ที่ผนวกเข้ากับ `dataview` ในแต่ละการอัปเดต

เพื่อเพิ่มเข้าไปใน capabilities.json

```typescript
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                },
                "dataReductionAlgorithm": {
                    "window": {
                        "count": 100
                    }
                }
            }
    }
]
```

เซกเมนต์ใหม่จะถูกผนวกเข้า `dataview` ที่มีอยู่และจัดให้กับการแสดงภาพเป็นการโทร `update`

## <a name="usage-in-the-custom-visual"></a>การใช้ในการแสดงภาพแบบกำหนดเอง

มีข้อมูลการบ่งชี้หรือไม่สามารถกำหนดได้โดยการตรวจสอบการมีอยู่ของ `dataView.metadata.segment`:

```typescript
    public update(options: VisualUpdateOptions) {
        const dataView = options.dataViews[0];
        console.log(dataView.metadata.segment);
        // output: __proto__: Object
    }
```

นอกจากนี้ยังเป็นไปได้ที่จะตรวจสอบว่าเป็นการอัปเดตตัวแรกหรือครั้งต่อ ๆ ไปโดยการตรวจสอบ `options.operationKind`

`VisualDataChangeOperationKind.Create` หมายถึงเซกเมนต์แรกและ `VisualDataChangeOperationKind.Append` หมายถึงเซกเมนต์ต่อมา

ดูส่วนย่อยของโค้ดด้านล่างสำหรับการดำเนินการตัวอย่าง:

```typescript
// CV update implementation
public update(options: VisualUpdateOptions) {
    // indicates this is the first segment of new data.
    if (options.operationKind == VisualDataChangeOperationKind.Create) {

    }

    // on second or subesquent segments:
    if (options.operationKind == VisualDataChangeOperationKind.Append) {

    }

    // complete update implementation
}
```

เมธอด `fetchMoreData` ยังสามารถเรียกใช้ได้จากตัวจัดการเหตุการณ์ UI

```typescript
btn_click(){
{
    // check if more data is expected for the current dataview
    if (dataView.metadata.segment) {
        //request for more data if available, as resopnce Power BI will call update method
        let request_accepted: bool = this.host.fetchMoreData();
        // handle rejection
        if (!request_accepted) {
            // for example when the 100 MB limit has been reached
        }
    }
}
```

Power BI จะเรียกเมธอด `update` ของการแสดงผลภาพที่มีเซกเมนต์ใหม่ของข้อมูลเป็นการตอบสนองเมธอดการโทร `this.host.fetchMoreData`

> [!NOTE]
> Power BI จะจำกัดข้อมูลทั้งหมดที่ได้รับจนถึง  **100 MB** เพื่อหลีกเลี่ยงข้อจำกัดของหน่วยความจำไคลเอ็นต์ คุณสามารถตรวจสอบขีดจำกัดนี้ได้เมื่อ fetchMoreData() ส่งกลับ 'false' *

---
title: ดึงข้อมูลเพิ่มเติมจาก Power BI
description: บทความนี้อธิบายถึงวิธีการเปิดใช้งานการดึงชุดข้อมูลขนาดใหญ่เป็นเซกเมนต์สำหรับวิชวล Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 6c79673e9d4b7edc95bdfe0373bb8a47d9fe587b
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/09/2019
ms.locfileid: "73880090"
---
# <a name="fetch-more-data-from-power-bi"></a>ดึงข้อมูลเพิ่มเติมจาก Power BI

บทความนี้อธิบายถึงวิธีการโหลดข้อมูลเพิ่มเติมเพื่อเลี่ยงผ่านขีดจำกัดฮาร์ดของจุดข้อมูล 30 KB แนวทางนี้ให้ข้อมูลเป็นกลุ่ม เพื่อปรับปรุงประสิทธิภาพการทำงาน คุณสามารถกำหนดขนาดกลุ่มเพื่อรองรับกรณีการใช้งานของคุณได้  

## <a name="enable-a-segmented-fetch-of-large-datasets"></a>เปิดใช้งานการดึงชุดข้อมูลขนาดใหญ่เป็นเซกเมนต์

สำหรับโหมดเซกเมนต์ `dataview` คุณกำหนดขนาดหน้าต่างสำหรับ dataReductionAlgorithm ในไฟล์ *capabilities.json* ของวิชวลสำหรับ dataViewMapping ที่ต้องการ `count` กำหนดขนาดหน้าต่างซึ่งจำกัดจำนวนแถวข้อมูลใหม่ที่สามารถผนวกเข้ากับ `dataview` ในแต่ละการอัปเดต

เพิ่มโค้ดต่อไปนี้ในไฟล์ *capabilities.json*:

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

## <a name="usage-in-the-power-bi-visual"></a>การใช้งานในวิชวลของ Power BI

คุณสามารถตรวจสอบว่ามีข้อมูลอยู่หรือไม่โดยตรวจสอบการมีอยู่ของ `dataView.metadata.segment`:

```typescript
    public update(options: VisualUpdateOptions) {
        const dataView = options.dataViews[0];
        console.log(dataView.metadata.segment);
        // output: __proto__: Object
    }
```

นอกจากนี้คุณยังสามารถตรวจสอบเพื่อดูว่ามันเป็นการอัปเดตครั้งแรกหรือการอัปเดตที่ตามมาภายหลังโดยการตรวจสอบ `options.operationKind` ในโค้ดต่อไปนี้ `VisualDataChangeOperationKind.Create`อ้างถึงเซกเมนต์แรกและ`VisualDataChangeOperationKind.Append` อ้างถึงเซกเมนต์ที่ตามมาภายหลัง

สำหรับตัวอย่างการนำไปใช้งาน โปรดดูข้อมูลโค้ดต่อไปนี้:

```typescript
// CV update implementation
public update(options: VisualUpdateOptions) {
    // indicates this is the first segment of new data.
    if (options.operationKind == VisualDataChangeOperationKind.Create) {

    }

    // on second or subsequent segments:
    if (options.operationKind == VisualDataChangeOperationKind.Append) {

    }

    // complete update implementation
}
```

คุณยังสามารถเรียกใช้เมธอด `fetchMoreData` จากตัวจัดการเหตุการณ์ UI ดังที่แสดงไว้ที่นี่:

```typescript
btn_click(){
{
    // check if more data is expected for the current data view
    if (dataView.metadata.segment) {
        //request for more data if available; as a response, Power BI will call update method
        let request_accepted: bool = this.host.fetchMoreData();
        // handle rejection
        if (!request_accepted) {
            // for example, when the 100 MB limit has been reached
        }
    }
}
```

Power BI เรียกเมธอด `update` ของวิชวลด้วยเซกเมนต์ใหม่ของข้อมูลเพื่อตอบสนองต่อการเรียกใช้เมธอด `this.host.fetchMoreData`

> [!NOTE]
> เพื่อหลีกเลี่ยงข้อจำกัดของหน่วยความจำไคลเอนต์ ปัจจุบัน Power BI จำกัดข้อมูลที่ดึงมาทั้งหมดเป็น 100 MB คุณสามารถเห็นว่าถึงขีดจำกัดแล้วเมื่อ fetchMoreData () ส่งกลับ `false`

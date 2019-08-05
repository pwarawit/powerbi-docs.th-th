---
title: บานหน้าต่างการวิเคราะห์
description: วิธีสร้างบรรทัดการอ้างอิงแบบไดนามิกสำหรับ Power BI Visuals
author: Guy-Moses
ms.author: guymos
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: b3b50f8dbcf40a3923e86422e24f8ed020894445
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425539"
---
# <a name="analytics-pane-in-power-bi-visuals"></a>บานหน้าต่างการวิเคราะห์ใน Power BI Visuals

**บานหน้าต่างการวิเคราะห์**ถูกนำมาใช้ใน[สำหรับวิชวลแบบเนทีฟ](https://docs.microsoft.com/power-bi/desktop-analytics-pane) ในเดือนพฤศจิกายน 2018
วิชวลแบบกำหนดเองที่มี API v2.5.0 สามารถนำเสนอและจัดการคุณสมบัติได้ใน**บานหน้าต่างการวิเคราะห์**

![บานหน้าต่างการวิเคราะห์](./media/visualization-pane-analytics-tab.png)

มีการจัดการคล้ายกับ [การจัดการคุณสมบัติในบานหน้าต่างรูปแบบ](https://docs.microsoft.com/power-bi/developer/custom-visual-develop-tutorial-format-options) โดยการกำหนดวัตถุในไฟล์ capabilities.json ของวิชวล 

ความแตกต่างมีดังนี้:

1. ภายใต้ข้อกำหนดของ `object` ให้เพิ่มเขตข้อมูล `objectCategory` ด้วยค่า 2

    > [!NOTE]
    > `objectCategory`เขตข้อมูลเป็นเขตข้อมูลทางเลือกที่นำมาใช้ใน API 2.5.0 ซึ่งจะกำหนดลักษณะของวิชวลที่ตัวควบคุมวัตถุ (1 = การจัดรูปแบบ 2 = การวิเคราะห์) "การจัดรูปแบบ" ใช้สำหรับรูปลักษณ์และความรู้สึก สี แกน ฉลาก และอื่น ๆ "การวิเคราะห์" ใช้สำหรับการคาดการณ์ เส้นแนวโน้ม บรรทัดอ้างอิง และรูปร่าง เป็นต้น
    >
    > `objectCategory` ค่าเริ่มต้นเป็น "จัดรูปแบบ" ถ้าเว้นไว้

2. วัตถุจะต้องมีคุณสมบัติสองประการต่อไปนี้:
    1. `show` ของชนิด bool ด้วยค่าเริ่มต้นของ false
    2. `displayName` ของชนิดข้อความ ค่าเริ่มต้นที่คุณเลือกจะกลายเป็นชื่อที่แสดงเริ่มต้นของอินสแตนซ์

```json
{
  "objects": {
    "YourAnalyticsPropertiesCard": {
      "displayName": "Your analytics properties card's name",
      "objectCategory": 2,
      "properties": {
        "show": {
          "type": {
            "bool": true
          }
        },
        "displayName": {
          "type": {
            "text": true
          }
        },
      ... //any other properties for your Analytics card
      }
    }
  ...
  }
}
```

คุณสมบัติอื่นใดอาจถูกกำหนดในลักษณะเดียวกับที่ทำกับวัตถุรูปแบบ การแจงนับวัตถุเสร็จสิ้นเหมือนกับใน **บานหน้าต่างรูปแบบ**

***ข้อจำกัดและปัญหาที่ทราบ***

  1. ยังไม่มีการสนับสนุนหลายอินสแตนซ์ วัตถุไม่สามารถมี [ตัวเลือก](https://microsoft.github.io/PowerBI-visuals/docs/concepts/objects-and-properties/#selector) นอกเหนือจากสแตติก (นั่นคือ "ตัวเลือก": เป็น null) และวิชวลที่กำหนดเองไม่สามารถมีอินสแตนซ์ของการ์ดที่ผู้ใช้กำหนดหลายรายการได้
  2. คุณสมบัติของชนิด `integer` แสดงอย่างไม่ถูกต้อง เพื่อหลีกเลี่ยงปัญหา ให้ใช้ชนิด `numeric` แทน

> [!NOTE]
> ใช้บานหน้าต่างการวิเคราะห์ สำหรับวัตถุที่เพิ่มข้อมูลใหม่หรือฉายแสงใหม่ในข้อมูลที่นำเสนอ ตัวอย่างเช่น เส้นอ้างอิงแบบไดนามิกที่แสดงแนวโน้มที่สำคัญ
> ตัวเลือกใดที่ควบคุมรูปลักษณ์และความรู้สึกของวิชวล นั่นคือการจัดรูปแบบควรถูกเก็บไว้ในบานหน้าต่างการจัดรูปแบบ

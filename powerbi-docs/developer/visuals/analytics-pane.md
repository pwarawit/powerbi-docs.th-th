---
title: บานหน้าต่างการวิเคราะห์ในวิชวล Power BI
description: บทความนี้อธิบายวิธีการสร้างเส้นอ้างอิงแบบไดนามิกในวิชวล Power BI
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 06/18/2019
ms.openlocfilehash: 67f9bc793b78d2019875b8165ea71fa712fd9d23
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/23/2019
ms.locfileid: "71193685"
---
# <a name="the-analytics-pane-in-power-bi-visuals"></a>บานหน้าต่างการวิเคราะห์ในวิชวล Power BI

บานหน้าต่าง**การวิเคราะห์**ถูกนำมาใช้สำหรับ[วิชวลแบบเนทีฟ](https://docs.microsoft.com/power-bi/desktop-analytics-pane) ในเดือนพฤศจิกายน 2018
บทความนี้อธิบายถึงวิธีการที่วิชวล Power BI ที่มี API v2.5.0 สามารถแสดงและจัดการคุณสมบัติได้ในบานหน้าต่าง **การวิเคราะห์**

![บานหน้าต่างการวิเคราะห์](./media/visualization-pane-analytics-tab.png)

## <a name="manage-the-analytics-pane"></a>จัดการบานหน้าต่างการวิเคราะห์

เช่นเดียวกับที่คุณจัดการคุณสมบัติในบานหน้าต่าง [**รูปแบบ**](https://docs.microsoft.com/power-bi/developer/custom-visual-develop-tutorial-format-options) คุณสามารถจัดการบานหน้าต่าง **การวิเคราะห์** โดยกำหนดวัตถุในไฟล์ *capabilities.json* ของวิชวลได้ 

สำหรับบานหน้าต่าง **การวิเคราะห์** ความแตกต่างมีดังนี้:

* ภายใต้คำจำกัดความของวัตถุ คุณเพิ่มเขตข้อมูล **objectCategory** ที่มีค่าเป็น 2

    > [!NOTE]
    > มีการนำเขตข้อมูล `objectCategory` แบบทางเลือกมาใช้ใน API 2.5.0 ซึ่งจะกำหนดลักษณะของวิชวลที่ตัวควบคุมวัตถุ (1 = การจัดรูปแบบ 2 = การวิเคราะห์) `Formatting` ใช้สำหรับองค์ประกอบเช่น รูปลักษณ์และความรู้สึก สี แกน และป้ายกำกับ `Analytics` ใช้สำหรับองค์ประกอบเช่น การคาดการณ์ เส้นแนวโน้ม เส้นอ้างอิง และรูปร่าง
    >
    > หากไม่ได้ระบุค่าไว้ `objectCategory` จะใช้ค่าเริ่มต้นเป็น "การจัดรูปแบบ"

* วัตถุจะต้องมีคุณสมบัติสองประการต่อไปนี้:
    * `show` ของชนิด `bool` โดยมีค่าเริ่มต้นคือ `false`
    * `displayName` ของชนิด `text` ค่าเริ่มต้นที่คุณเลือกจะกลายเป็นชื่อที่แสดงเริ่มต้นของอินสแตนซ์

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

คุณสามารถกำหนดคุณสมบัติอื่น ๆ ในลักษณะเดียวกับที่คุณทำกับอ็อบเจ็กต์ **รูปแบบ** และคุณสามารถแจกแจงอ็อบเจ็กต์ได้เช่นเดียวกับที่คุณทำในบานหน้าต่าง **รูปแบบ**

## <a name="known-limitations-and-issues-of-the-analytics-pane"></a>ข้อจำกัดและปัญหาที่ทราบของบานหน้าต่าง การวิเคราะห์

* บานหน้าต่าง **การวิเคราะห์** ยังไม่มีการสนับสนุนหลายอินสแตนซ์ อ็อบเจ็กต์ไม่สามารถมี [ตัวเลือก](https://microsoft.github.io/PowerBI-visuals/docs/concepts/objects-and-properties/#selector) นอกเหนือจากสแตติก (นั่นคือ "ตัวเลือก": เป็น null) และวิชวล Power BI ไม่สามารถมีอินสแตนซ์ของการ์ดที่ผู้ใช้กำหนดหลายรายการได้
* คุณสมบัติของชนิด `integer` แสดงอย่างไม่ถูกต้อง เพื่อหลีกเลี่ยงปัญหา ให้ใช้ชนิด `numeric` แทน

> [!NOTE]
> * ใช้บานหน้าต่าง **การวิเคราะห์** เฉพาะสำหรับอ็อบเจ็กต์ที่เพิ่มข้อมูลใหม่หรือฉายแสงใหม่ในข้อมูลที่นำเสนอ (ตัวอย่างเช่น เส้นอ้างอิงแบบไดนามิกที่แสดงแนวโน้มที่สำคัญ)
> * ตัวเลือกใดก็ตามที่ควบคุมรูปลักษณ์และความรู้สึกของวิชวล (นั่นคือ การจัดรูปแบบ) ควรถูกจำกัดไว้ที่บานหน้าต่าง **การจัดรูปแบบ**

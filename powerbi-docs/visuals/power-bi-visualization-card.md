---
title: การแสดงภาพการ์ด (ไทล์จำนวนมาก)
description: สร้างการแสดงภาพการ์ดใน Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/10/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 268b69362f0f8c98ba01fbd0673fc46856d54ba2
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/23/2019
ms.locfileid: "71195515"
---
# <a name="card-visualizations"></a>การแสดงภาพการ์ด

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

บางครั้งตัวเลขเพียงตัวเดียวก็เป็นสิ่งสำคัญที่สุดที่คุณต้องการติดตามในแดชบอร์ด Power BI หรือรายงานของคุณ เช่น ยอดขายรวม ส่วนแบ่งตลาดแบบปีต่อปี ตลาดแชร์ปีปี หรือโอกาสทั้งหมด แสดงภาพชนิดนี้จะเรียกว่า*การ์ด* เช่นเดียวกับการแสดงภาพดั้งเดิมของ Power BI แทบจะทุกชนิด คุณสามารถสร้างการ์ดขึ้นได้ โดยใช้ตัวแก้ไขรายงาน หรือการถามตอบ

![การแสดงภาพการ์ด](media/power-bi-visualization-card/pbi-opptuntiescard.png)

## <a name="prerequisite"></a>เงื่อนไขเบื้องต้น

บทช่วยสอนนี้ใช้ [ไฟล์ PBIX ตัวอย่าง การวิเคราะห์การขายปลีก](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)

1. จากด้านซ้ายบนของแถบเมนู เลือก **ไฟล์** \> **เปิด**
   
2. ค้นหาสำเนา**ไฟล์ PBIX ตัวอย่างการวิเคราะห์การค้าปลีก**

1. เปิด**ไฟล์ PBIX ตัวอย่างการวิเคราะห์การค้าปลีก**ในมุมมองรายงาน ![ภาพหน้าจอไอคอนมุมมองรายงาน](media/power-bi-visualization-kpi/power-bi-report-view.png)

1. เลือก ![สกรีนช็อตของแท็บสีเหลือง](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) หากต้องการเพิ่มหน้าใหม่

## <a name="option-1-create-a-card-using-the-report-editor"></a>ตัวเลือกที่ 1: สร้างการ์ดโดยใช้ตัวแก้ไขรายงาน

วิธีแรกในการจัดทำการ์ดคือใช้ Report Editor จาก Power BI Desktop

1. เริ่มต้นจากหน้ารายงานว่างแล้วเลือก**ร้านค้า** เปิดเขตข้อมูล\> **จำนวนร้านค้า**

    Power BI จะสร้างแผนภูมิคอลัมน์ที่มีตัวเลขเพียงตัวเลขเดียว

   ![ตัวอย่างแผนภูมิไทล์ตัวเลข](media/power-bi-visualization-card/pbi-overview-chart.png)

2. ในบานหน้าต่างการแสดงภาพ ให้เลือกไอคอนการ์ด

   ![ตัวอย่างการ์ดชื่อแบบตัวเลข](media/power-bi-visualization-card/power-bi-card-visualization.png)

คุณจัดทำการ์ดพร้อม Report Editor เสร็จสิ้นแล้ว ต่อไปนี้เป็นตัวเลือกที่สองในการจัดทำการ์ดโดยใช้ช่องคำถาม ถามตอบ

## <a name="option-2-create-a-card-from-the-qa-question-box"></a>ตัวเลือกที่ 2: สร้างการ์ดจากกล่องคำถามการถามตอบ
กล่องคำถาม ถามตอบ เป็นอีกทางเลือกสำหรับคุณในการใช้ขณะจัดทำการ์ด ช่องคำถาม ถามตอบ มีอยู่ในมุมมองรายงานของ Power BI Desktop

1. เริ่มต้นบน หน้ารายงานเปล่า

1. ด้านบนของหน้าต่าง ให้เลือกไอคอน **ถามคำถาม** 

    Power BI จะจัดทำการ์ดและช่องสำหรับคำถามของคุณ 

   ![ตำแหน่งไอคอนถามคำถาม](media/power-bi-visualization-card/power-bi-q-and-a-overview.png)

2. เช่น พิมพ์ “Total Sales for Tina” ในช่องคำถาม

    กล่องคำถามจะคอยช่วยเหลือคุณ โดยจะมีคำแนะนำรวมทั้งการกล่าวซ้ำ และสุดท้ายก็จะแสดงจำนวนรวม  

   ![ตัวอย่างช่องคำถาม](media/power-bi-visualization-card/power-bi-q-and-a-box.png)

   ![ตัวอย่างการ์ดจากวิธีการถาม](media/power-bi-visualization-card/power-bi-q-and-a-card.png)

คุณจัดทำการ์ดพร้อมช่องคำถาม ถามตอบ เสร็จสิ้นแล้ว ต่อไปนี้เป็นขั้นตอนในการกำหนดรูปแบบการ์ดของคุณตามความต้องการ

## <a name="format-a-card"></a>จัดรูปแบบการ์ด
คุณมีตัวเลือกมากมายสำหรับการเปลี่ยนป้ายชื่อ, ข้อความ, สี และอีกมาก วิธีดีที่สุดในการเรียนรู้คือ สร้างการ์ด จากนั้นสำรวจบานหน้าต่างการจัดรูปแบบ ต่อไปนี้เป็นเพียงบางตัวเลือกของการจัดรูปแบบที่มี 

บานหน้าต่างการจัดรูปแบบจะพร้อมใช้งานขณะโต้ตอบกับการ์ดในรายงาน 

1. เริ่มต้นด้วยการเลือกไอคอนรูปลูกกลิ้งทาสีเพื่อเปิดบานหน้าต่างการจัดรูปแบบ 

    ![การ์ดที่มีเค้าโครงลูกกลิ้งทาสี](media/power-bi-visualization-card/power-bi-format-card-2.png)

2. ด้วยการ์ดที่เลือก ขยาย**ป้ายชื่อข้อมูล** และเปลี่ยนสี ขนาด และตระกูลแบบอักษร ถ้าคุณมีหลายพันร้านค้า คุณสามารถใช้**แสดงหน่วย**เพื่อแสดงจำนวนของร้านค้าเป็นหลักพัน และควบคุมตำแหน่งทศนิยมได้เช่นกัน ตัวอย่างเช่น แสดง 125.8K แทนที่จะเป็น 125,832.00

    ![ตัวอย่างการ์ดพร้อมรูปแบบข้อมูล](media/power-bi-visualization-card/power-bi-card-format-2.png)

3.  ขยาย**ป้ายชื่อประเภท**และเปลี่ยนสีและขนาด

    ![ตัวอย่างการ์ดพร้อมหมวดหมู่](media/power-bi-visualization-card/power-bi-card-format-category.png)

4. ขยาย**พื้นหลัง**และเลื่อนแถบเลื่อนเป็นเปิด  ตอนนี้คุณสามารถเปลี่ยนสีพื้นหลังและความโปร่งใส

    ![ตั้งค่าเป็นเปิดแถบเลื่อน](media/power-bi-visualization-card/power-bi-format-color-2.png)

5. ลองสำรวจตัวเลือกการจัดรูปแบบต่อไป จนกว่าการ์ดของคุณเป็นแบบที่คุณต้องการ 

## <a name="considerations-and-troubleshooting"></a>ข้อควรพิจารณาและการแก้ไขปัญหา
ถ้าคุณไม่สามารถเห็นกล่องคำถามทั้งหมด โปรดติดต่อผู้ดูแลระบบหรือผู้ดูแลผู้เช่าของคุณ    

## <a name="next-steps"></a>ขั้นตอนถัดไป
[แผนภูมิผสมใน Power BI](power-bi-visualization-combo-chart.md)

[ชนิดการแสดงภาพใน Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

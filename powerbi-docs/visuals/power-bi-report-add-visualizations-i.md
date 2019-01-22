---
title: ส่วนที่ 1 เพิ่มการแสดงภาพไปยังรายงาน Power BI
description: ส่วนที่ 1 เพิ่มการแสดงภาพไปยังรายงาน Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 52c0211aea0462e0bf79d7a48808f1f826c09fb6
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54296098"
---
# <a name="part-i-add-visualizations-to-a-power-bi-report"></a>ส่วนที่ 1 เพิ่มการแสดงภาพไปยังรายงาน Power BI
บทความนี้ให้คำแนะนำสั้น ๆ สำหรับการสร้างการแสดงภาพในรายงาน โดยใช้บริการของ Power BI หรือ Power BI Desktop  สำหรับเนื้อหาขั้นสูงขึ้น กรุณา[ดูส่วนที่ II](power-bi-report-add-visualizations-ii.md) ดู Amanda สาธิตสักสองสามวิธีสำหรับ สร้าง แก้ไข และจัดรูปแบบวิชวลบนพื้นที่รายงาน แล้วทดลองด้วยตัวเองโดยใช้[ตัวอย่างการขายและการตลาด](../sample-datasets.md)เพื่อสร้างรายงานของคุณเอง

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>


## <a name="open-a-report-and-add-a-new-page"></a>เปิดรายงาน และเพิ่มหน้าใหม่
1. เปิด[รายงานในมุมมองการแก้ไข](../consumer/end-user-reading-view.md) บทช่วยสอนนี้ใช้[ตัวอย่างการขายและการตลาด](../sample-datasets.md)
2. ถ้าคุณมองไม่เห็นบานหน้าต่างเขตข้อมูล เลือกไอคอนลูกศรเพื่อเปิด 
   
   ![](media/power-bi-report-add-visualizations-i/pbi_nancy_fieldsfiltersarrow.png)
3. เพิ่มหน้าเปล่าลงในรายงาน

## <a name="add-visualizations-to-the-report"></a>เพิ่มการแสดงภาพลงในรายงาน
1. สร้างการแสดงภาพ โดยการเลือกเขตข้อมูลจากบานหน้าต่าง**เขตข้อมูล**บานหน้าต่าง  
   
   **เริ่มต้นด้วยเขตข้อมูลตัวเลข**เช่น SalesFact > ยอดขาย $ Power BI จะสร้างแผนภูมิคอลัมน์ที่มีคอลัมน์เดียว
   
   ![](media/power-bi-report-add-visualizations-i/pbi_onecolchart.png)
   
   **หรือ เริ่มต้น ด้วยประเภทของเขตข้อมูล**เช่นชื่อหรือผลิตภัณฑ์: Power BI สร้างตารางและเพิ่มเขตข้อมูลนั้นไปยังส่วนที่เป็น**ค่าตัวเลข**ด้วยเช่นกัน
   
   ![](media/power-bi-report-add-visualizations-i/pbi_agif_createchart3.gif)
   
   **หรือเริ่มต้น ด้วยเขตข้อมูลภูมิศาสตร์**เช่น ภูมิศาสตร์ > เมือง Power BI และ Bing Maps จะสร้างการแสดงภาพแผนที่ให้
   
   ![](media/power-bi-report-add-visualizations-i/power-bi-map.png)
2. สร้างการแสดงภาพ แล้วเปลี่ยนชนิดของการแสดงภาพนั้น เลือก**ผลิตภัณฑ์ > ประเภท** จากนั้น **ผลิตภัณฑ์ > จำนวนผลิตภัณฑ์** เพื่อเพิ่มไปยัง**ค่า**
   
   ![](media/power-bi-report-add-visualizations-i/part1table1.png)
3. เปลี่ยนการแสดงภาพเป็นในแผนภูมิคอลัมน์ โดยการเลือกไอคอนแผนภูมิคอลัมน์
   
   ![](media/power-bi-report-add-visualizations-i/part1converttocolumn.png)
4. เมื่อคุณสร้างการแสดงภาพในรายงานของคุณ คุณสามารถ[ปักหมุดภาพเหล่านั้นไปยังแดชบอร์ด](../service-dashboard-pin-tile-from-report.md)ได้ เมื่อต้องการปักหมุดการแสดงภาพ เลือกไอคอนรูปเข็มหมด ![](media/power-bi-report-add-visualizations-i/pinnooutline.png)
   
   ![](media/power-bi-report-add-visualizations-i/part1pin1.png)
  

## <a name="next-steps"></a>ขั้นตอนถัดไป
 ไปต่อยัง[ส่วนที่ 2: เพิ่มภาพไปยังรายงาน Power BI](power-bi-report-add-visualizations-ii.md)
   
   [โต้ตอบกับการแสดงภาพ](../consumer/end-user-reading-view.md)ในรายงาน
   
   [ทำอีกหลายอย่างกับการแสดงภาพ](power-bi-report-visualizations.md)
   
   [บันทึกรายงานของคุณ](../service-report-save.md)

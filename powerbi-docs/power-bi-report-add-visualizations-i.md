---
title: ส่วนที่ I เพิ่มการแสดงภาพไปยังรายงาน Power BI (บทช่วยสอน)
description: 'บทช่วยสอน: ส่วนที่ I เพิ่มการแสดงภาพไปยังรายงาน Power BI'
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
featuredvideoid: IkJda4O7oGs
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/08/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: b81061c25b453fc35e1490c3ded2d9c9770d4599
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
---
# <a name="part-i-add-visualizations-to-a-power-bi-report-tutorial"></a>ส่วนที่ I เพิ่มการแสดงภาพไปยังรายงาน Power BI (บทช่วยสอน)
บทความนี้ให้คำแนะนำสั้น ๆ สำหรับการสร้างวิชวลในรายงาน  สำหรับเนื้อหาขั้นสูงขึ้น กรุณา[ดูส่วนที่ II](power-bi-report-add-visualizations-ii.md) ดู Amanda สาธิตสักสองสามวิธีสำหรับ สร้าง แก้ไข และจัดรูปแบบวิชวลบนพื้นที่รายงาน แล้วทดลองด้วยตัวเองโดยใช้[ตัวอย่างการขายและการตลาด](sample-datasets.md)เพื่อสร้างรายงานของคุณเอง

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>


## <a name="open-a-report-and-add-a-new-page"></a>เปิดรายงาน และเพิ่มหน้าใหม่
1. เปิด[รายงานในมุมมองการแก้ไข](service-reading-view-and-editing-view.md) บทช่วยสอนนี้ใช้[ตัวอย่างการขายและการตลาด](sample-datasets.md)
2. ถ้าคุณมองไม่เห็นบานหน้าต่างเขตข้อมูล เลือกไอคอนลูกศรเพื่อเปิด 
   
   ![](media/power-bi-report-add-visualizations-i/pbi_nancy_fieldsfiltersarrow.png)
3. [เพิ่มหน้าเปล่าลงในรายงาน](power-bi-report-add-page.md)

## <a name="add-visualizations-to-the-report"></a>เพิ่มการแสดงภาพลงในรายงาน
1. สร้างการแสดงภาพ โดยการเลือกเขตข้อมูลจากบานหน้าต่าง**เขตข้อมูล**บานหน้าต่าง  
   
   **เริ่มต้น ด้วยเขตข้อมูลตัวเลข** เช่น ยอดขาย > ยอดขายเป็นดอลลาร์ Power BI สร้างแผนภูมิคอลัมน์ ที่มีคอลัมน์เดียว
   
   ![](media/power-bi-report-add-visualizations-i/pbi_onecolchart.png)
   
   **เริ่มต้น ด้วยเขตข้อมูลประเภท** เช่นชื่อหรือผลิตภัณฑ์ Power BI จะสร้างตาราง และเพิ่มเขตข้อมูลนั้นไปยัง**ค่า**ด้วย
   
   ![](media/power-bi-report-add-visualizations-i/pbi_agif_createchart3.gif)
   
   **เริ่มต้น ด้วยเขตข้อมูลภูมิศาสตร์**เช่น ภูมิศาสตร์ > เมือง Power BI และ Bing Maps จะสร้างการแสดงภาพแผนที่ให้
   
   ![](media/power-bi-report-add-visualizations-i/power-bi-map.png)
2. สร้างการแสดงภาพ แล้วเปลี่ยนชนิดของการแสดงภาพนั้น เลือก**ผลิตภัณฑ์ > จำนวนผลิตภัณฑ์**และ**ผลิตภัณฑ์ > ประเภท** เพื่อเพิ่มไปยัง**ค่า**
   
   ![](media/power-bi-report-add-visualizations-i/part1table1.png)
3. เปลี่ยนการแสดงภาพเป็นในแผนภูมิคอลัมน์ โดยการเลือกไอคอนแผนภูมิคอลัมน์
   
   ![](media/power-bi-report-add-visualizations-i/part1converttocolumn.png)
4. เมื่อคุณสร้างการแสดงภาพในรายงานของคุณ คุณสามารถ[ปักหมุดภาพเหล่านั้นไปยังแดชบอร์ด](service-dashboard-pin-tile-from-report.md)ได้ เมื่อต้องการปักหมุดการแสดงภาพ เลือกไอคอนรูปเข็มหมด ![](media/power-bi-report-add-visualizations-i/pinnooutline.png)
   
   ![](media/power-bi-report-add-visualizations-i/part1pin1.png)
5. ในตอนนี้คุณสามารถ:
   
   ไปต่อยัง[ส่วนที่ 2: เพิ่มการแสดงภาพไปยังรายงาน Power BI](power-bi-report-add-visualizations-ii.md)
   
   [โต้ตอบกับการแสดงภาพ](service-reading-view-and-editing-view.md)ในรายงาน
   
   [ทำอีกหลายอย่างกับการแสดงภาพ](power-bi-report-visualizations.md)
   
   [บันทึกรายงานของคุณ](service-report-save.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป
อ่านเพิ่มเติมเกี่ยวกับ[การแสดงภาพในรายงาน Power BI](power-bi-report-visualizations.md)

[รายงานใน Power BI](service-reports.md)

คำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


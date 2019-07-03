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
ms.date: 06/17/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: c5838d12351c06d0a76a975c9c473b1c00856d97
ms.sourcegitcommit: 90aa7ea5fcc7cf0fd7f6c3c1efeff5f27e8ef0dd
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/20/2019
ms.locfileid: "67299205"
---
# <a name="part-1-add-visualizations-to-a-power-bi-report"></a>ส่วนที่ 1 เพิ่มการแสดงภาพไปยังรายงาน Power BI

บทความนี้ให้คำแนะนำสั้น ๆ สำหรับการสร้างวิชวลในรายงาน รายงานสามารถใช้ได้ทั้งบริการของ Power BI และ Power BI Desktop สำหรับเนื้อหาขั้นสูง ให้ดูที่ [ส่วนที่ 2](power-bi-report-add-visualizations-ii.md)ของชุดข้อมูลนี้ ดู Amanda สาธิตสักสองสามวิธีสำหรับ สร้าง แก้ไข และจัดรูปแบบวิชวลบนพื้นที่รายงาน แล้วทดลองด้วยตัวเองโดยใช้[ตัวอย่างการขายและการตลาด](../sample-datasets.md)เพื่อสร้างรายงานของคุณเอง

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

## <a name="open-a-report-and-add-a-new-page"></a>เปิดรายงาน และเพิ่มหน้าใหม่

1. เปิด[รายงานในมุมมองการแก้ไข](../service-interact-with-a-report-in-editing-view.md)

    บทช่วยสอนนี้ใช้[ตัวอย่างการขายและการตลาด](../sample-datasets.md)

1. ถ้าคุณมองไม่เห็นบานหน้าต่าง**เขตข้อมูล** เลือกไอคอนลูกศรเพื่อเปิด

   ![](media/power-bi-report-add-visualizations-i/pbi_nancy_fieldsfiltersarrow.png)

1. เพิ่มหน้าเปล่าลงในรายงาน

## <a name="add-visualizations-to-the-report"></a>เพิ่มการแสดงภาพลงในรายงาน

1. สร้างการแสดงภาพ โดยการเลือกเขตข้อมูลจากบานหน้าต่าง**เขตข้อมูล**บานหน้าต่าง

    เริ่มต้นด้วยเขตข้อมูลตัวเลขเช่น **SalesFact** >  **ยอดขาย $** Power BI จะสร้างแผนภูมิคอลัมน์ที่มีคอลัมน์เดียว

    ![สกรีนช็อตของแผนภูมิคอลัมน์ที่มีคอลัมน์เดียว](media/power-bi-report-add-visualizations-i/pbi_onecolchart.png)

    หรือ เริ่มต้น ด้วยประเภทของเขตข้อมูลเช่น**ชื่อ**หรือ**ผลิตภัณฑ์** Power BI สร้างตารางและเพิ่มเขตข้อมูลนั้นไปยังส่วนที่เป็น**ค่าตัวเลข**ด้วยเช่นกัน

    ![GIF ของบุคคลที่เลือกผลิตภัณฑ์และหมวดหมู่เพื่อสร้างตาราง](media/power-bi-report-add-visualizations-i/pbi_agif_createchart3.gif)

    หรือเริ่มต้น ด้วยเขตข้อมูลภูมิศาสตร์เช่น **ภูมิศาสตร์** > **เมือง** Power BI และ Bing Maps จะสร้างการแสดงภาพแผนที่ให้

    ![สกรีนช๊อตของการแสดงภาพของแผนที่](media/power-bi-report-add-visualizations-i/power-bi-map.png)

1. สร้างการแสดงภาพ แล้วเปลี่ยนชนิดของการแสดงภาพนั้น เลือก**ผลิตภัณฑ์** > **ประเภท** จากนั้น **ผลิตภัณฑ์**  >  **จำนวนผลิตภัณฑ์**เพื่อเพิ่มไปยัง**ค่า**

   ![สกรีนช็อตของการเรียกบานหน้าต่างเขตข้อมูลที่มีค่าด้วยเช่นกันออกมา](media/power-bi-report-add-visualizations-i/part1table1.png)

1. เปลี่ยนการแสดงภาพเป็นในแผนภูมิคอลัมน์ โดยการเลือกไอคอน**แผนภูมิคอลัมน์แบบเรียงซ้อน**

   ![สกรีนช็อตของการเรียกบานหน้าต่างการแสดงภาพที่มีไอคอนแผนภูมิคอลัมน์แบบเรียงซ้อนออกมา](media/power-bi-report-add-visualizations-i/part1converttocolumn.png)

1. เมื่อคุณสร้างการแสดงภาพในรายงานของคุณ คุณสามารถ[ปักหมุดภาพเหล่านั้นไปยังแดชบอร์ด](../service-dashboard-pin-tile-from-report.md)ได้ เมื่อต้องการปักหมุดการแสดงภาพ เลือกไอคอนรูปเข็มหมด ![สกรีนช็อตของไอคอนรูปเข็ม](media/power-bi-report-add-visualizations-i/pinnooutline.png)

   ![สกรีนช็อตของการเรียกแผนภูมิคอลัมน์การแสดงภาพมีไอคอนรูปหมุดออกมา](media/power-bi-report-add-visualizations-i/part1pin1.png)
  
## <a name="next-steps"></a>ขั้นตอนถัดไป

 ไปต่อยัง:

* [ส่วนที่ 2: เพิ่มภาพไปยังรายงาน Power BI](power-bi-report-add-visualizations-ii.md)

* [โต้ตอบกับการแสดงภาพ](../consumer/end-user-reading-view.md)ในรายงาน

* [ทำอีกหลายอย่างกับการแสดงภาพ](power-bi-report-visualizations.md)

* [บันทึกรายงานของคุณ](../service-report-save.md)

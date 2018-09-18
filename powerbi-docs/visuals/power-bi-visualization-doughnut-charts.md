---
title: แผนภูมิโดนัทใน Power BI
description: แผนภูมิโดนัทใน Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 12/23/2017
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: d09f9d9d0de8608a39111f24e6f605c3fbce55fb
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2018
ms.locfileid: "44744843"
---
# <a name="doughnut-charts-in-power-bi"></a>แผนภูมิโดนัทใน Power BI
แผนภูมิโดนัทจะคล้ายกับแผนภูมิวงกลมที่จะแสดงความสัมพันธ์ของข้อมูลองค์ประกอบต่างๆ กับข้อมูลทั้งหมด ความแตกต่างเพียงประการเดียว คือ ส่วนตรงกลางนั้นว่างเปล่า และมีพื้นที่ว่างสำหรับระบุป้ายชื่อหรือไอคอน

## <a name="create-a-doughnut-chart"></a>สร้างแผนภูมิโดนัท
คำแนะนำเหล่านี้จะใช้ตัวอย่างการวิเคราะห์การค้าปลีก เพื่อสร้างแผนภูมิโดนัทที่แสดงยอดขายสำหรับปีนี้โดยจำแนกตามประเภท ถ้าต้องการทำตามคำแนะนำดังกล่าว ให้[ดาวน์โหลดตัวอย่าง](../sample-datasets.md)สำหรับบริการของ Power BI (app.powerbi.com) หรือ Power BI Desktop

1. เริ่มต้นจาก[หน้ารายงานเปล่า](../power-bi-report-add-page.md) และเลือกเขตข้อมูล**ขั้นตอนการขาย** \> **ขั้นตอนการขาย** ถ้าคุณกำลังใช้บริการของ Power BI ให้ตรวจสอบให้แน่ใจว่าคุณได้เปิดรายงานใน[มุมมองการแก้ไข](../service-interact-with-a-report-in-editing-view.md) แล้ว

2. ในส่วนบานหน้าต่างเขตข้อมูล ให้เลือก**ยอดขาย** \> **ยอดขายของปีล่าสุด**  
   
3. ในส่วนบานหน้าต่างการแสดงภาพ ให้เลือกไอคอนสำหรับแผนภูมิโดนัท![ไอคอนแผนภูมิโดนัท]() เพื่อแปลงแผนภูมิแท่งของคุณให้กลายเป็นแผนภูมิโดนัท ถ้า**ยอดขายปีล่าสุด**ไม่อยู่ในพื้นที่**ค่า** ให้ลากไปไว้ในส่วนนั้น
     
   ![](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. เลือก**สินค้า** \> **ประเภท** ที่จะเพิ่มไปยังพื้นที่**คำอธิบายแผนภูมิ** 
     
    ![](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. อีกวิธีหนึ่ง คือ [ปรับขนาดและสีของข้อความในแผนภูมิ](power-bi-visualization-customize-title-background-and-legend.md) 

## <a name="considerations-and-troubleshooting"></a>ข้อควรพิจารณาและการแก้ไขปัญหา
* ผลรวมของค่าแผนภูมิโดนัทต้องเพิ่มเป็น 100%
* จำนวนประเภทที่มากเกินไปจะทำให้อ่านและตีความข้อมูลได้ยาก
* แผนภูมิโดนัทเหมาะอย่างยิ่งที่จะใช้เพื่อเปรียบเทียบข้อมูลส่วนใดส่วนหนึ่งกับข้อมูลทั้งหมด มากกว่าจะใช้เปรียบเทียบระหว่างข้อมูลแต่ละส่วน 

## <a name="next-steps"></a>ขั้นตอนถัดไป
[รายงานใน Power BI](../service-reports.md)

[ชนิดการแสดงภาพใน Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

[การแสดงภาพในรายงาน Power BI](power-bi-report-visualizations.md)

[Power BI - แนวคิดพื้นฐาน](../service-basic-concepts.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


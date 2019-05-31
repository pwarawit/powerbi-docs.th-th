---
title: แผนภูมิโดนัทใน Power BI
description: แผนภูมิโดนัทใน Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 4c69113d245d47a4d2702f16f6cea21a6cbd3b0b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "61136104"
---
# <a name="doughnut-charts-in-power-bi"></a>แผนภูมิโดนัทใน Power BI
แผนภูมิโดนัทจะคล้ายกับแผนภูมิวงกลมที่จะแสดงความสัมพันธ์ของข้อมูลองค์ประกอบต่างๆ กับข้อมูลทั้งหมด ความแตกต่างเพียงประการเดียว คือ ส่วนตรงกลางนั้นว่างเปล่า และมีพื้นที่ว่างสำหรับระบุป้ายชื่อหรือไอคอน

## <a name="create-a-doughnut-chart"></a>สร้างแผนภูมิโดนัท
คำแนะนำเหล่านี้จะใช้ตัวอย่างการวิเคราะห์การค้าปลีก เพื่อสร้างแผนภูมิโดนัทที่แสดงยอดขายสำหรับปีนี้โดยจำแนกตามประเภท ถ้าต้องการทำตามคำแนะนำดังกล่าว ให้[ดาวน์โหลดตัวอย่าง](../sample-datasets.md)สำหรับบริการ Power BI หรือ Power BI Desktop

1. เริ่มต้นบน หน้ารายงานเปล่า ถ้าคุณกำลังใช้บริการของ Power BI ตรวจสอบให้แน่ใจว่า คุณเปิดรายงานใน[มุมมองการแก้ไข](../service-interact-with-a-report-in-editing-view.md)

2. ในส่วนบานหน้าต่างเขตข้อมูล ให้เลือก**ยอดขาย** \> **ยอดขายของปีล่าสุด**  
   
3. ในส่วนบานหน้าต่างการแสดงภาพ ให้เลือกไอคอนสำหรับแผนภูมิโดนัท![ไอคอนแผนภูมิโดนัท](media/power-bi-visualization-doughnut-charts/power-bi-icon.png) เพื่อแปลงแผนภูมิแท่งของคุณให้กลายเป็นแผนภูมิโดนัท ถ้า**ยอดขายปีล่าสุด**ไม่อยู่ในพื้นที่**ค่า** ให้ลากไปไว้ในส่วนนั้น
     
   ![บานหน้าต่างการแสดงภาพที่เลือกแผนภูมิโดนัทแล้ว](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. เลือก**สินค้า** \> **ประเภท** ที่จะเพิ่มไปยังพื้นที่**คำอธิบายแผนภูมิ** 
     
    ![โดนัทถัดจากบานหน้าต่างเขตข้อมูล](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. อีกวิธีหนึ่ง คือ [ปรับขนาดและสีของข้อความในแผนภูมิ](power-bi-visualization-customize-title-background-and-legend.md) 

## <a name="considerations-and-troubleshooting"></a>ข้อควรพิจารณาและการแก้ไขปัญหา
* ผลรวมของค่าแผนภูมิโดนัทต้องเพิ่มเป็น 100%
* จำนวนประเภทที่มากเกินไปจะทำให้อ่านและตีความข้อมูลได้ยาก
* แผนภูมิโดนัทเหมาะอย่างยิ่งที่จะใช้เพื่อเปรียบเทียบข้อมูลส่วนใดส่วนหนึ่งกับข้อมูลทั้งหมด มากกว่าจะใช้เปรียบเทียบระหว่างข้อมูลแต่ละส่วน 

## <a name="next-steps"></a>ขั้นตอนถัดไป
[แผนภูมิกรวยใน Power BI](power-bi-visualization-funnel-charts.md)

[ชนิดการแสดงภาพใน Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)



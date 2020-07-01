---
title: แผนภูมิโดนัทใน Power BI
description: แผนภูมิโดนัทใน Power BI
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/05/2020
ms.author: rien
LocalizationGroup: Visualizations
ms.openlocfilehash: f76fe26f8b7d4f9e9c0cbe1ffe22c71d815a9307
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85239728"
---
# <a name="create-and-use-doughnut-charts-in-power-bi"></a>สร้างและใช้แผนภูมิโดนัทใน Power BI

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

แผนภูมิโดนัทจะคล้ายกับแผนภูมิวงกลมที่จะแสดงความสัมพันธ์ของข้อมูลองค์ประกอบต่างๆ กับข้อมูลทั้งหมด ความแตกต่างเพียงประการเดียว คือ ส่วนตรงกลางนั้นว่างเปล่า และมีพื้นที่ว่างสำหรับระบุป้ายชื่อหรือไอคอน

## <a name="prerequisite"></a>เงื่อนไขเบื้องต้น

บทช่วยสอนนี้ใช้[ไฟล์ PBIX ตัวอย่างการวิเคราะห์การค้าปลีก](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)

1. จากด้านบนซ้ายของแถบเมนู เลือก **ไฟล์** > **เปิด**
   
2. ค้นหาสำเนา**ไฟล์ PBIX ตัวอย่างการวิเคราะห์การค้าปลีก**

1. เปิด**ไฟล์ PBIX ตัวอย่างการวิเคราะห์การค้าปลีก**ในมุมมองรายงาน ![ภาพหน้าจอไอคอนมุมมองรายงาน](media/power-bi-visualization-kpi/power-bi-report-view.png)

1. เลือก ![สกรีนช็อตของแท็บสีเหลือง](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) หากต้องการเพิ่มหน้าใหม่


> [!NOTE]
> การแชร์รายงานของคุณกับผู้ร่วมงาน Power BI กำหนดให้คุณต้องมีสิทธิ์การใช้งาน Power BI Pro แต่ละรายการ หรือรายงานจะถูกบันทึกในความจุแบบพรีเมียม    

## <a name="create-a-doughnut-chart"></a>สร้างแผนภูมิโดนัท

1. เริ่มต้นที่หน้ารายงานเปล่า และจากบานหน้าต่างเขตข้อมูล เลือก **ยอดขาย** \> **ยอดขายปีล่าสุด**  
   
3. ในส่วนบานหน้าต่างการแสดงภาพ ให้เลือกไอคอนสำหรับแผนภูมิโดนัท![ไอคอนแผนภูมิโดนัท](media/power-bi-visualization-doughnut-charts/power-bi-icon.png) เพื่อแปลงแผนภูมิแท่งของคุณให้กลายเป็นแผนภูมิโดนัท ถ้า**ยอดขายปีล่าสุด**ไม่อยู่ในพื้นที่**ค่า** ให้ลากไปไว้ในส่วนนั้น
     
   ![บานหน้าต่างการแสดงภาพที่เลือกแผนภูมิโดนัทแล้ว](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. เลือก **หน่วยข้อมูล** \> **หมวดหมู่** เพิ่มเพิ่มรายการไปยังพื้นที่ **คำอธิบายแผนภูมิ** 
     
    ![โดนัทถัดจากบานหน้าต่างเขตข้อมูล](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. อีกวิธีหนึ่ง คือ [ปรับขนาดและสีของข้อความในแผนภูมิ](power-bi-visualization-customize-title-background-and-legend.md) 

## <a name="considerations-and-troubleshooting"></a>ข้อควรพิจารณาและการแก้ไขปัญหา
* ผลรวมของค่าแผนภูมิโดนัทต้องเพิ่มเป็น 100%
* จำนวนประเภทที่มากเกินไปจะทำให้อ่านและตีความข้อมูลได้ยาก
* แผนภูมิโดนัทเหมาะอย่างยิ่งที่จะใช้เพื่อเปรียบเทียบข้อมูลส่วนใดส่วนหนึ่งกับข้อมูลทั้งหมด มากกว่าจะใช้เปรียบเทียบระหว่างข้อมูลแต่ละส่วน 

## <a name="next-steps"></a>ขั้นตอนถัดไป
[แผนภูมิกรวยใน Power BI](power-bi-visualization-funnel-charts.md)

[ชนิดการแสดงภาพใน Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)



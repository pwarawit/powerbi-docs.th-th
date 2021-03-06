---
title: ส่วนที่ 1 เพิ่มการแสดงภาพไปยังรายงาน Power BI
description: ส่วนที่ 1 เพิ่มการแสดงภาพไปยังรายงาน Power BI
author: mihart
ms.reviewer: rien
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/06/2020
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 439807717a91a22520969a85a3991b76f8115833
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85232395"
---
# <a name="add-visuals-to-a-power-bi-report-part-1"></a>เพิ่มวิชวลไปยังรายงาน Power BI (ตอนที่ 1)

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]    

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

บทความนี้ให้คำแนะนำสั้น ๆ สำหรับการสร้างวิชวลในรายงาน รายงานสามารถใช้ได้ทั้งบริการของ Power BI และ Power BI Desktop สำหรับเนื้อหาขั้นสูง ให้ดูที่ [ส่วนที่ 2](power-bi-report-add-visualizations-ii.md)ของชุดข้อมูลนี้

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

บทช่วยสอนนี้ใช้ [ไฟล์ PBIX ตัวอย่างการขายและการตลาด](https://download.microsoft.com/download/9/7/6/9767913A-29DB-40CF-8944-9AC2BC940C53/Sales%20and%20Marketing%20Sample%20PBIX.pbix)

1. จากด้านบนซ้ายของแถบเมนู Power BI Desktop เลือก **ไฟล์** > **เปิด**
   
2. ค้นหาสำเนาของ **ไฟล์ PBIX ตัวอย่างการขายและการตลาด** ของคุณ

1. เปิด **ไฟล์ PBIX ตัวอย่างการขายและการตลาด** ในมุมมองรายงาน ![สกรีนช็อตไอคอนมุมมองรายงาน](media/power-bi-visualization-kpi/power-bi-report-view.png)

1. เลือก ![สกรีนช็อตของแท็บสีเหลือง](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) หากต้องการเพิ่มหน้าใหม่

> [!NOTE]
> การแชร์รายงานของคุณกับผู้ร่วมงาน Power BI กำหนดให้คุณต้องมีสิทธิ์การใช้งาน Power BI Pro แต่ละรายการ หรือรายงานจะถูกบันทึกในความจุแบบพรีเมียม ดู [การแชร์รายงาน](../collaborate-share/service-share-reports.md)

## <a name="add-visualizations-to-the-report"></a>เพิ่มการแสดงภาพลงในรายงาน

1. สร้างการแสดงภาพ โดยการเลือกเขตข้อมูลจากบานหน้าต่าง**เขตข้อมูล**บานหน้าต่าง

    เริ่มต้นด้วยเขตข้อมูลตัวเลข เช่น **Sales** > **TotalSales** Power BI จะสร้างแผนภูมิคอลัมน์ที่มีคอลัมน์เดียว

    ![สกรีนช็อตของแผนภูมิคอลัมน์ที่มีคอลัมน์เดียว](media/power-bi-report-add-visualizations-i/power-bi-column-chart.png)

    หรือ เริ่มต้น ด้วยประเภทของเขตข้อมูลเช่น**ชื่อ**หรือ**ผลิตภัณฑ์** Power BI สร้างตารางและเพิ่มเขตข้อมูลนั้นไปยังส่วนที่เป็น**ค่าตัวเลข**ด้วยเช่นกัน

    ![สกรีนช็อตของตารางที่มีสี่หมวดหมู่](media/power-bi-report-add-visualizations-i/power-bi-product.png)

    หรือเริ่มต้น ด้วยเขตข้อมูลภูมิศาสตร์เช่น **ภูมิศาสตร์** > **เมือง** Power BI และ Bing Maps จะสร้างการแสดงภาพแผนที่ให้

    ![สกรีนช๊อตของการแสดงภาพของแผนที่](media/power-bi-report-add-visualizations-i/power-bi-maps.png)

## <a name="change-the-type-of-visualization"></a>เปลี่ยนชนิดของการแสดงผลข้อมูลด้วยภาพ

 สร้างการแสดงภาพ แล้วเปลี่ยนชนิดของการแสดงภาพนั้น 
 
 1. เลือก**ผลิตภัณฑ์** > **ประเภท** จากนั้น **ผลิตภัณฑ์**  >  **จำนวนผลิตภัณฑ์**เพื่อเพิ่มไปยัง**ค่า**

    ![สกรีนช็อตของการเรียกบานหน้าต่างเขตข้อมูลที่มีค่าด้วยเช่นกันออกมา](media/power-bi-report-add-visualizations-i/power-bi-create-visual.png)

1. เปลี่ยนการแสดงภาพเป็นในแผนภูมิคอลัมน์ โดยการเลือกไอคอน**แผนภูมิคอลัมน์แบบเรียงซ้อน**

   ![สกรีนช็อตของการเรียกบานหน้าต่างการแสดงภาพที่มีไอคอนแผนภูมิคอลัมน์แบบเรียงซ้อนออกมา](media/power-bi-report-add-visualizations-i/power-bi-convert.png)

1. เมื่อต้องการเปลี่ยนวิธีการเรียงลำดับวิชวล ให้เลือก **การดำเนินการเพิ่มเติม** (...)  ใช้ตัวเลือกการเรียงลำดับเพื่อเปลี่ยนทิศทางของการเรียงลำดับ (จากน้อยไปหามากหรือมากไปหาน้อย) และเปลี่ยนคอลัมน์ที่ใช้ในการเรียงลำดับ (**เรียงลำดับตาม**)

   ![สกรีนช็อตของรายการดรอปดาวน์การดำเนินการเพิ่มเติม](media/power-bi-report-add-visualizations-i/power-bi-sort.png)
  
## <a name="next-steps"></a>ขั้นตอนถัดไป

 ไปต่อยัง:

* [ส่วนที่ 2: เพิ่มภาพไปยังรายงาน Power BI](power-bi-report-add-visualizations-ii.md)

* [โต้ตอบกับการแสดงภาพ](../consumer/end-user-reading-view.md)ในรายงาน

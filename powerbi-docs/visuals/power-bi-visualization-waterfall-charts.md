---
title: แผนภูมิแบบน้ำตกใน Power BI
description: แผนภูมิแบบน้ำตกใน Power BI
author: mihart
ms.reviewer: ''
featuredvideoid: maTzOJSRB3g
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/5/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 6abca661a1553bfabc3da35fe714ff9bced5555a
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "74907675"
---
# <a name="waterfall-charts-in-power-bi"></a>แผนภูมิแบบน้ำตกใน Power BI

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

แผนภูมิแบบน้ำตกจะแสดงผลรวมสะสมเป็นค่าของ Power BI ที่เพิ่มขึ้นหรือลดลง แผนภูมิเหล่านี้มีประโยชน์สำหรับการวิเคราะห์ว่าค่าเริ่มต้น (ตัวอย่างเช่น กำไรสุทธิ) ได้รับผลกระทบอย่างไร เมื่อมีการเปลี่ยนแปลงเชิงบวก และเชิงลบที่เกิดขึ้นอย่างต่อเนื่องในช่วงระยะเวลาหนึ่ง

คอลัมน์เป็นสีที่แสดงรหัส เพื่อให้คุณสามารถสังเกตการเพิ่มขึ้นและการลดลงได้อย่างรวดเร็ว คอลัมน์ค่าเริ่มต้นและคอลัมน์ค่าสุดท้ายมัก[เริ่มต้นบนแกนนอน](https://support.office.com/article/Create-a-waterfall-chart-in-Office-2016-for-Windows-8de1ece4-ff21-4d37-acd7-546f5527f185#BKMK_Float "เริ่มต้นบนแกนนอน")ขณะที่ค่ากลางจะเป็นคอลัมน์แบบลอยตัว เนื่องจากมี "สไตล์" แบบนี้ จึงยังเรียกแผนภูมิแบบน้ำตกอีกชื่อหนึ่งว่าแผนภูมิแบบสะพาน

   > [!NOTE]
   > วิดีโอนี้ใช้ Power BI Desktop เวอร์ชันเก่า
   > 
   > 

<iframe width="560" height="315" src="https://www.youtube.com/embed/qKRZPBnaUXM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## <a name="when-to-use-a-waterfall-chart"></a>เมื่อต้องการใช้แผนภูมิแบบน้ำตก

แผนภูมิแบบน้ำตกเป็นตัวเลือกที่เหมาะสมอย่างยิ่ง ในกรณีต่อไปนี้:

* เมื่อคุณมีการเปลี่ยนแปลงข้อมูลตัวเลขตลอดช่วงระยะเวลาหนึ่งหรือตามประเภทต่างๆ

* เมื่อต้องการตรวจสอบการเปลี่ยนแปลงหลักที่ส่งผลให้เกิดค่าผลรวม

* เมื่อต้องการลงจุดกำไรรายปีของบริษัทคุณ โดยแสดงแหล่งข้อมูลต่างๆ ของรายได้ และจนถึงกำไร (หรือขาดทุน) รวม

* เมื่อต้องการแสดงจำนวนพนักงานตอนต้นปีและปลายปีในบริษัทของคุณในหนึ่งปี

* เมื่อต้องการแสดงภาพจำนวนเงินที่หาได้และใช้จ่ายในแต่ละเดือน และยอดคงเหลือสะสมสำหรับบัญชีของคุณ

## <a name="prerequisite"></a>ข้อกำหนดเบื้องต้น

บทช่วยสอนนี้ใช้[ไฟล์ PBIX ตัวอย่างการวิเคราะห์การค้าปลีก](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)

1. จากด้านบนซ้ายของแถบเมนู เลือก **ไฟล์** > **เปิด**
   
2. ค้นหาสำเนา**ไฟล์ PBIX ตัวอย่างการวิเคราะห์การค้าปลีก**

1. เปิด**ไฟล์ PBIX ตัวอย่างการวิเคราะห์การค้าปลีก**ในมุมมองรายงาน ![ภาพหน้าจอไอคอนมุมมองรายงาน](media/power-bi-visualization-kpi/power-bi-report-view.png)

1. Select ![สกรีนช็อตของแท็บสีเหลือง](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) หากต้องการเพิ่มหน้าใหม่


## <a name="create-a-waterfall-chart"></a>สร้างแผนภูมิแบบน้ำตก

คุณจะสร้างแผนภูมิแบบน้ำตกที่แสดงผลต่างของยอดขาย (ประมาณการยอดขายเทียบกับยอดขายจริง) เป็นรายเดือน

### <a name="build-the-waterfall-chart"></a>สร้างแผนภูมิน้ำตก

1. ในส่วนบานหน้าต่าง **เขตข้อมูล** ให้เลือก**ยอดขาย** >  **ผลต่างของยอดขายรวม**

   ![สกรีนช็อตของยอดขาย >ผลต่างของยอดขายรวมที่เลือกและภาพที่เป็นผลลัพธ์](media/power-bi-visualization-waterfall-charts/power-bi-bar.png)

1. เลือกไอคอนน้ำตก ![สกรีนช็อตของไอคอนน้ำตก](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-icon.png)

    ![แม่แบบการแสดงภาพ](media/power-bi-visualization-waterfall-charts/convert-waterfall.png)

1. เลือก**เวลา** > **เดือนตามรอบบัญชี** เพื่อเพิ่มไปยัง**ประเภท** ตามที่เหมาะสม

    ![แผนภูมิน้ำตก](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-month.png)

### <a name="sort-the-waterfall-chart"></a>เรียงลำดับแผนภูมิน้ำตก

1. ตรวจสอบให้แน่ใจว่า Power BI เรียงลำดับแผนภูมิแบบน้ำตกตามลำดับเดือน จากมุมบนขวาของแผนภูมิ ให้เลือก **ตัวเลือกเพิ่มเติม** (...)

    สำหรับตัวอย่างนี้ ให้เลือก **เรียงลำดับตาม** และเลือก **FiscalMonth (เดือนงบประมาณ)** ตัวบ่งชี้สีเหลืองที่อยู่ถัดจากสิ่งที่คุณเลือกจะแสดงขึ้นเมื่อมีการใช้ตัวเลือกการเลือกของคุณ

    ![เลือกการเรียงลำดับตาม > เดือนงบประมาณ](media/power-bi-visualization-waterfall-charts/power-bi-sort-by-fiscalmonth.png)
    
    เพื่อแสดงเดือนตามลำดับเวลา ให้เลือก **เรียงลำดับจากน้อยไปหามาก** เช่นเดียวกับขั้นตอนก่อนหน้า ให้ตรวจสอบว่ามีตัวบ่งชี้สีเหลืองอยู่ถัดจากด้านซ้ายของตัวเลือก **การเรียงลำดับจากน้อยไปมาก** หรือไม่ ซึ่งเป็นการระบุว่าตัวเลือกที่คุณเลือกกำลังถูกปรับใช้

    ![เลือกเรียงจาก > ลำดับจากน้อยไปมาก](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-ascending.png)

    

    โปรดสังเกตว่าแผนภูมิของคุณถูกจัดเรียงตั้งแต่เดือนมกราคมถึงเดือนสิงหาคมสำหรับ FiscalMonth (เดือนงบประมาณ)  

### <a name="explore-the-waterfall-chart"></a>สำรวจแผนภูมิน้ำตก

ดูรายละเอียดเพิ่มเติมอีกเล็กน้อย เพื่อดูว่าอะไรคือปัจจัยที่สนับสนุนให้เกิดการเปลี่ยนแปลงมากที่สุดในแต่ละเดือน

1.  เลือก **ร้านค้า** > **พื้นที่** ซึ่งจะเป็นการเพิ่ม **พื้นที่** ไปยังบักเก็ต **แยกย่อย**

    ![แสดงร้านค้าในบักเก็ต](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown.png)

    Power BI ใช้ค่าใน **แยกย่อย** เพื่อเพิ่มข้อมูลเพิ่มเติมไปยังการแสดงผลข้อมูลด้วยภาพ ซึ่งจะเพิ่มปัจจัยสนับสนุนห้าอันดับแรกที่จะเพิ่ม หรือลดสำหรับแต่ละเดือนงบประมาณ ตัวอย่างเช่นในเดือนกุมภาพันธ์ มีจุดข้อมูลหกจุดแทนที่จะเป็นเพียงจุดเดียว  

    ![แสดงร้านค้าในบักเก็ต](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-default.png)

    สมมติว่าคุณสนใจเฉพาะปัจจัยสนับสนุน 2 อันดับแรก

1. ในบานหน้าต่าง**การจัดรูปแบบ** ให้เลือก **การแบ่งย่อย** แล้วตั้ง**การแบ่งย่อยสูงสุดเป็น** **2**

    ![รูปแบบ > แบ่งย่อย](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-two.png)

    การตรวจสอบอย่างรวดเร็วแสดงให้เห็นว่าเขตโอไฮโอ และเพนซิลเวเนียเป็นปัจจัยสนับสนุนที่มีอิทธิพลมากที่สุดที่ทำให้เกิดการเปลี่ยนแปลงทั้งในเชิงบวกและเชิงลบในแผนภูมิแบบน้ำตกของเรา

    ![แผนภูมิน้ำตก](media/power-bi-visualization-waterfall-charts/power-bi-axis-waterfall.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [เปลี่ยนวิธีการที่การแสดงผลด้วยภาพโต้ตอบในรายงาน Power BI](../service-reports-visual-interactions.md)

* [ชนิดการแสดงภาพใน Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)

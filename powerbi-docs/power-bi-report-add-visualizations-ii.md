---
title: ส่วนที่ 2 เพิ่มการแสดงภาพไปยังรายงาน Power BI (บทช่วยสอน)
description: 'บทช่วยสอน: ส่วนที่ 2 เพิ่มการแสดงภาพไปยังรายงาน Power BI'
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 567bece0089a01170e218af9606331e44cb7834f
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
---
# <a name="part-2-add-visualizations-to-a-power-bi-report-tutorial"></a>ส่วนที่ 2 เพิ่มการแสดงภาพไปยังรายงาน Power BI (บทช่วยสอน)
ใน[ส่วนที่ 1](power-bi-report-add-visualizations-ii.md) คุณได้สร้างภาพพื้นฐานแล้วโดยการเลือกกล่องข้อความถัดจากชื่อเขตข้อมูล  ในส่วนที่ 2 คุณจะได้เรียนรู้วิธีใช้การลากและวาง และใช้**เขตข้อมูล**และพื้นที่**การแสดงภาพ**เต็มรูปแบบเพื่อสร้างและปรับเปลี่ยนการแสดงภาพ

### <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
- [ส่วนที่ 1](power-bi-report-add-visualizations-ii.md)
- บริการ Power BI - เราสามารถเพิ่มการแสดงภาพลงในรายงานได้โดยใช้บริการ Power BI หรือ Power BI Desktop บทช่วยสอนนี้ใช้บริการ Power BI 
- ตัวอย่างการวิเคราะห์การค้าปลีก

## <a name="create-a-new-visualization"></a>สร้างการแสดงภาพใหม่
ในบทช่วยสอนนี้ เราจะเจาะลึกลงในชุดข้อมูลการวิเคราะห์ร้านค้าปลีก และสร้างการแสดงภาพที่สำคัญบางภาพ

### <a name="open-a-report-and-add-a-new-blank-page"></a>เปิดรายงานและเพิ่มหน้าเปล่าใหม่
1. เปิดพื้นที่ทำงานในตำแหน่งที่คุณบันทึกตัวอย่างการวิเคราะห์ร้านค้าปลีก เลือก**ตัวอย่างการวิเคราะห์ร้านค้าปลีก**เพื่อเปิดรายงานในมุมมองการอ่าน
   
   ![](media/power-bi-report-add-visualizations-ii/power-bi-open-report.png)
2. เลือก**แก้ไขรายงาน** เพื่อเปิดรายงานในมุมมองการแก้ไข
   
   ![](media/power-bi-report-add-visualizations-ii/editreport1.png)
3. [เพิ่มหน้าใหม่](power-bi-report-add-page.md)โดยการเลือกไอคอนเครื่องหมายถูกสีเหลืองที่ด้านล่างของพื้นที่รายงาน
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_addreportpage.png)

### <a name="add-a-visualization-that-looks-at-this-years-sales-compared-to-last-year"></a>เพิ่มการแสดงภาพที่ดูการขายของปีนี้เทียบกับปีที่แล้ว
1. จากตาราง**ยอดขาย** เลือก**ค่ายอดขายของ** > **ปีนี้**และ**ยอดขายของปีที่แล้ว** Power BI สร้างแผนภูมิคอลัมน์  ซึ่งส่วนนี้น่าสนใจพอสมควรและคุณจะอยากเจาะลึกลงไปอีก การขายจะมีลักษณะเป็นอย่างไรเมื่อแยกดูเป็นรายเดือน?  
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_4bnew.png)
2. จากตารางเวลา ลาก**เดือน**ลงในพื้นที่**แกน**  
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_5newnew.png)
3. [เปลี่ยนการแสดงภาพ](power-bi-report-change-visualization-type.md)ในแผนภูมิพื้นที่  มีการแสดงภาพมากมายหลายชนิดให้คุณเลือก ดู[คำอธิบายของแต่ละการแสดงภาพ คำแนะนำสำหรับแนวทางปฏิบัติที่ดีที่สุด และบทช่วยสอน](power-bi-visualization-types-for-reports-and-q-and-a.md)สำหรับความช่วยเหลือในการตัดสินใจว่าควรใช้ชนิดใด จากพื้นที่การแสดงภาพ เลือกไอคอนแผนภูมิพื้นที่
4. เรียงลำดับการแสดงภาพโดยการเลือกจุดไข่ปลา แล้วเลือก**เรียงลำดับตามเดือน**
5. [ปรับขนาดการแสดงภาพ](power-bi-visualization-move-and-resize.md)โดยเลือกการแสดงภาพ จับที่เค้าร่างวงกลมหนึ่งวงและลาก ทำให้กว้างพอที่จะกำจัดแถบเลื่อน และเล็กพอที่จะมีพื้นที่ให้เราเพิ่มการแสดงภาพแบบอื่นได้
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_7b.png)
6. [บันทึกรายงาน](service-report-save.md)

### <a name="add-a-map-visualization-that-looks-at-sales-by-location"></a>เพิ่มการแสดงภาพของแผนที่ท่ี่ดูยอดขายตามตำแหน่งที่ตั้ง
1. จากตาราง**ร้านค้า** เลือก**ดินแดน** Power BI จดจำว่าดินแดน (Territory) เป็นตำแหน่งที่ตั้งหนึ่ง และสร้างการแสดงภาพของแผนที่หนึ่ง  
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_8newnew.png)
2. ลาก**ร้านค้ารวม**ลงในพื้นที่ขนาด  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-add-visual-to-a-reportnew.png)
3. เพิ่มคำอธิบายแผนภูมิ  เมื่อต้องการดูข้อมูลตามชื่อร้านค้า ให้ลาก**ห่วงโซ่**ลงในพื้นที่คำอธิบายแผนภูมิ  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-add-visual-to-a-report-3new.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป
* สำหรับข้อมูลเพิ่มเติมเกี่ยวกับพื้นที่เขตข้อมูล ดู[ตัวแก้ไขรายงาน...สำรวจ](service-the-report-editor-take-a-tour.md)   
* เมื่อต้องการเรียนรู้วิธีการกรองและทำไฮไลท์การแสดงภาพของคุณ ดู[ตัวกรองและการทำไฮไลท์ในรายงาน Power BI](power-bi-reports-filters-and-highlighting.md)  
* อ่านเพิ่มเติมเกี่ยวกับ[การแสดงภาพในรายงาน Power BI](power-bi-report-visualizations.md)  
* มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


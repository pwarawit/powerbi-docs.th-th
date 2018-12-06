---
title: ส่วนที่ 2 เพิ่มการแสดงภาพไปยังรายงาน Power BI
description: ส่วนที่ 2 เพิ่มการแสดงภาพไปยังรายงาน Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 08/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 01051ab47304713fe3cf0f9128f5cd99af58bffe
ms.sourcegitcommit: e17fc3816d6ae403414cf5357afbf6a492822ab8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/04/2018
ms.locfileid: "52830228"
---
# <a name="part-2-add-visualizations-to-a-power-bi-report"></a>ส่วนที่ 2 เพิ่มการแสดงภาพไปยังรายงาน Power BI
ใน[ส่วนที่ 1](power-bi-report-add-visualizations-ii.md) คุณได้สร้างภาพพื้นฐานแล้วโดยการเลือกกล่องข้อความถัดจากชื่อเขตข้อมูล  ในส่วนที่ 2 คุณจะได้เรียนรู้วิธีใช้การลากและวาง และใช้**เขตข้อมูล**และพื้นที่**การแสดงภาพ**เต็มรูปแบบเพื่อสร้างและปรับเปลี่ยนการแสดงภาพ

### <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
- [ส่วนที่ 1](power-bi-report-add-visualizations-ii.md)
- Power BI Desktop - เราสามารถเพิ่มการแสดงภาพลงในรายงานได้โดยใช้บริการ Power BI หรือ Power BI Desktop บทช่วยสอนนี้ใช้ Power BI Desktop 
- [ตัวอย่างการวิเคราะห์การค้าปลีก](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)

## <a name="create-a-new-visualization"></a>สร้างการแสดงภาพใหม่
ในบทช่วยสอนนี้ เราจะเจาะลึกลงในชุดข้อมูลการวิเคราะห์ร้านค้าปลีก และสร้างการแสดงภาพที่สำคัญบางภาพ

### <a name="open-a-report-and-add-a-new-blank-page"></a>เปิดรายงานและเพิ่มหน้าเปล่าใหม่
1. เปิดไฟล์ .pbix ตัวอย่างการวิเคราะห์ด้านการขายปลีกใน Power BI Desktop 
   ![](media/power-bi-report-add-visualizations-ii/power-bi-open-desktop.png)   

2. เพิ่มหน้าใหม่โดยการเลือกไอคอนเครื่องหมายถูกสีเหลืองที่ด้านล่างของพื้นที่รายงาน

### <a name="add-a-visualization-that-looks-at-this-years-sales-compared-to-last-year"></a>เพิ่มการแสดงภาพที่ดูการขายของปีนี้เทียบกับปีที่แล้ว
1. จากตาราง**ยอดขาย** เลือก**ค่ายอดขายของ** > **ปีนี้**และ**ยอดขายของปีที่แล้ว** Power BI สร้างแผนภูมิคอลัมน์  ซึ่งส่วนนี้น่าสนใจพอสมควรและคุณจะอยากเจาะลึกลงไปอีก การขายจะมีลักษณะเป็นอย่างไรเมื่อแยกดูเป็นรายเดือน?  
   
   ![](media/power-bi-report-add-visualizations-ii/power-bi-barchart.png)
2. จากตารางเวลา ลาก**เดือนตามรอบบัญชี**ลงในพื้นที่**แกน**  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-month.png)
3. [เปลี่ยนการแสดงภาพ](power-bi-report-change-visualization-type.md)ในแผนภูมิพื้นที่  มีการแสดงภาพมากมายหลายชนิดให้คุณเลือก ดู[คำอธิบายของแต่ละการแสดงภาพ คำแนะนำสำหรับแนวทางปฏิบัติที่ดีที่สุด และบทช่วยสอน](power-bi-visualization-types-for-reports-and-q-and-a.md)สำหรับความช่วยเหลือในการตัดสินใจว่าควรใช้ชนิดใด จากพื้นที่การแสดงภาพ เลือกไอคอนแผนภูมิพื้นที่![](media/power-bi-report-add-visualizations-ii/power-bi-areachart.png)
4. เรียงลำดับการแสดงภาพโดยการเลือกจุดไข่ปลา แล้วเลือก**เรียงลำดับตามเดือนตามรอบบัญชี**
5. [ปรับขนาดการแสดงภาพ](power-bi-visualization-move-and-resize.md)โดยเลือกการแสดงภาพ จับที่เค้าร่างวงกลมหนึ่งวงและลาก ทำให้กว้างพอที่จะกำจัดแถบเลื่อน และเล็กพอที่จะมีพื้นที่ให้เราเพิ่มการแสดงภาพแบบอื่นได้
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_7b.png)
6. [บันทึกรายงาน](../service-report-save.md)

### <a name="add-a-map-visualization-that-looks-at-sales-by-location"></a>เพิ่มการแสดงภาพของแผนที่ท่ี่ดูยอดขายตามตำแหน่งที่ตั้ง
1. จากตาราง**ร้านค้า** เลือก**ดินแดน** Power BI จดจำว่าดินแดน (Territory) เป็นตำแหน่งที่ตั้งหนึ่ง และสร้างการแสดงภาพของแผนที่หนึ่ง  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-map.png)
2. ลาก**ร้านค้ารวม**ลงในพื้นที่ขนาด  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-map2.png)
3. เพิ่มคำอธิบายแผนภูมิ  เมื่อต้องการดูข้อมูลตามชื่อร้านค้า ให้ลาก**ห่วงโซ่**ลงในพื้นที่คำอธิบายแผนภูมิ  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-legend.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป
* อ่านเพิ่มเติมเกี่ยวกับ[การแสดงภาพในรายงาน Power BI](power-bi-report-visualizations.md)  
* มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


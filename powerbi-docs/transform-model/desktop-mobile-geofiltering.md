---
title: ตั้งค่าตัวกรองทางภูมิศาสตร์ใน Power BI Desktop สำหรับแอปบนอุปกรณ์เคลื่อนที่
description: เมื่อคุณตั้งค่าการกรองทางภูมิศาสตร์ในรูปแบบข้อมูลของคุณใน Power BI Desktop คุณสามารถกรองข้อมูลตามตำแหน่งของคุณได้โดยอัตโนมัติในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
author: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 01/16/2018
ms.author: maggies
LocalizationGroup: Model your data
ms.openlocfilehash: 361a5c6537c3ae1a149b67851b01776c880bf257
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85237120"
---
# <a name="set-geographic-filters-in-power-bi-desktop-for-use-in-the-mobile-app"></a>ตั้งค่าตัวกรองทางภูมิศาสตร์ใน Power BI Desktop สำหรับใช้ในแอปบนอุปกรณ์เคลื่อนที่
ใน Power BI Desktop คุณสามารถ[จัดประเภทข้อมูลทางภูมิศาสตร์](desktop-data-categorization.md)สำหรับคอลัมน์ เพื่อให้ Power BI Desktop ทราบว่าควรทำอย่างไรกับค่าในวิชวลในรายงานได้ ประโยชน์เพิ่มเติมคือ เมื่อคุณหรือเพื่อนร่วมงานของคุณดูรายงานนั้นในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ Power BI ใช้ตัวกรองทางภูมิศาสตร์ที่ตรงกับตำแหน่งของคุณโดยอัตโนมัติ 

ตัวอย่างเช่น คุณเป็นผู้จัดการฝ่ายขาย และกำลังเดินทางไปพบลูกค้า และคุณต้องการจะกรองยอดขายและรายได้สำหรับลูกค้าที่คุณกำลังจะไปพบอย่างรวดเร็ว คุณต้องการแยกดูเฉพาะข้อมูลสำหรับตำแหน่งปัจจุบันของคุณ ไม่ว่า จะเป็น รัฐ เมือง หรือที่อยู่ ต่อไป ถ้าคุณมีเวลาเหลือ คุณอยากจะไปเยี่ยมลูกค้ารายอื่น ๆ อยู่ที่ใกล้ คุณสามารถ[กรองรายงานตามตำแหน่งของคุณเพื่อค้นหาลูกค้าเหล่านั้น](../consumer/mobile/mobile-apps-geographic-filtering.md)ได้

> [!NOTE]
> คุณสามารถกรองข้อมูลตามตำแหน่งที่ตั้งในแอปสำหรับอุปกรณ์เคลื่อนที่ ก็ต่อเมื่อชื่อภูมิศาสตร์ในรายงานเป็นภาษาอังกฤษเท่านั้น &#150; เช่น "New York" หรือ "Germany"
> 
> 

## <a name="identify-geographic-data-in-your-report"></a>ระบุข้อมูลทางภูมิศาสตร์ในรายงานของคุณ
1. ใน Power BI Desktop สลับไปยังมุมมองข้อมูล ![ไอคอนมุมมองข้อมูล](media/desktop-mobile-geofiltering/pbi_desktop_data_icon.png).
2. เลือกคอลัมน์ที่เป็นข้อมูลทางภูมิศาสตร์ &#151; ตัวอย่างเช่น คอลัมน์เมือง
   
    ![คอลัมน์เมือง](media/desktop-mobile-geofiltering/power-bi-desktop-geo-column.png)
3. บนแท็บ**การวางรูปแบบ** เลือก**ประเภทข้อมูล** จากนั้นเลือกประเภทที่ถูกต้อง &#151; ในตัวอย่างนี้คือ **เมือง**
   
    ![กล่องประเภทข้อมูล](media/desktop-mobile-geofiltering/power-bi-desktop-geo-category.png)
4. ตั้งค่าประเภทข้อมูลทางภูมิศาสตร์สำหรับเขตข้อมูลอื่น ๆ ในรูปแบบข้อมูลต่อ 
   
   > [!NOTE]
   > คุณสามารถตั้งค่าหลายคอลัมน์ สำหรับแต่ละประเภทข้อมูลในรูปแบบ แต่ถ้าคุณทำแบบนั้น แอป Power BI สำหรับอุปกรณ์เคลื่อนที่ จะไม่สามารถกรองรูปแบบตามภูมิศาสตร์ได้ เพื่อใช้การกรองทางภูมิศาสตร์ในแอปสำหรับอุปกรณ์เคลื่อนที่ ตั้งค่าแค่คอลัมน์เดียวเท่านั้นสำหรับแต่ละประเภทข้อมูล &#151; เช่น มีคอลัมน์**เมือง**แค่คอลัมน์เดียว คอลัมน์**รัฐหรือจังหวัด**คอลัมน์เดียว และคอลัมน์**ประเทศ**คอลัมน์เดียว 
   > 
   > 

## <a name="create-visuals-with-your-geographic-data"></a>สร้างวิชวลด้วยข้อมูลทางภูมิศาสตร์ของคุณ
1. สลับไปยังมุมมองรายงาน ![ไอคอนมุมมองรายงาน](media/desktop-mobile-geofiltering/power-bi-desktop-report-icon.png)และสร้างวิชวลที่ใช้เขตข้อมูลทางภูมิศาสตร์ในข้อมูลของคุณ 
   
    ![รายงานที่มีแผนที่](media/desktop-mobile-geofiltering/power-bi-desktop-geo-report.png)
   
    ในตัวอย่างนี้ รูปแบบข้อมูลยังประกอบด้วยคอลัมน์จากการคำนวณ ที่รวมเมืองและรัฐเข้าด้วยกันเป็นหนึ่งคอลัมน์ อ่านเกี่ยวกับ[สร้างคอลัมน์จากการคำนวณใน Power BI Desktop](desktop-calculated-columns.md)
   
    ![เขตข้อมูล เมือง + รัฐ](media/desktop-mobile-geofiltering/power-bi-desktop-city-state-column.png)
2. เผยแพร่รายงานไปยังบริการ Power BI

## <a name="view-the-report-in-power-bi-mobile-app"></a>ดูรายงานในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
1. เปิดรายงานในใด ๆ ใน[แอป Power BI สำหรับอุปกรณ์เคลื่อนที่](../consumer/mobile/mobile-apps-for-mobile-devices.md)
2. ถ้าคุณอยู่ในตำแหน่งทางภูมิศาสตร์ที่มีข้อมูลในรายงาน คุณสามารถกรองข้อมูลนั้นด้วยตำแหน่งของคุณโดยอัตโนมัติ
   
    ![ตัวกรองทางภูมิศาสตร์ในแอปสำหรับอุปกรณ์เคลื่อนที่](media/desktop-mobile-geofiltering/power-bi-mobile-geo-map-set-filter.png)

อ่านเพิ่มเติมเกี่ยวกับ[การกรองรายงานตามตำแหน่งในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่](../consumer/mobile/mobile-apps-geographic-filtering.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [จัดประเภทข้อมูลใน Power BI Desktop](desktop-data-categorization.md)  
* มีคำถามหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)

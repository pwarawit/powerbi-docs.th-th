---
title: ตัวกรองรายงานตามตำแหน่งที่ตั้งทางภูมิศาสตร์ในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
description: เรียนรู้วิธีที่คุณสามารถกรองรายงานตามตำแหน่งที่ตั้งทางภูมิศาสตร์ในแอป Microsoft Power BI สำหรับอุปกรณ์เคลื่อนที่ ถ้าเจ้าของรายงานกำหนดแท็กที่ตั้งทางภูมิศาสตร์
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/09/2018
ms.author: maggies
ms.openlocfilehash: 90d6e6f80be49e8d1c2a9605558a57834e24e285
ms.sourcegitcommit: ad9bd4e52471b1179f46f847960d5ed79c0c0761
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/11/2018
---
# <a name="filter-a-report-by-geographic-location-in-the-power-bi-mobile-apps"></a>กรองรายงานตามตำแหน่งที่ตั้งทางภูมิศาสตร์ในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
ใช้ได้กับ:

| ![iPhone](media/mobile-apps-geographic-filtering/iphone-logo-50-px.png) | ![iPad](media/mobile-apps-geographic-filtering/ipad-logo-50-px.png) | ![มือถือ Android](media/mobile-apps-geographic-filtering/android-phone-logo-50-px.png) | ![แท็บเล็ต Android](media/mobile-apps-geographic-filtering/android-tablet-logo-50-px.png) | ![แท็บเล็ต Android](media/mobile-apps-geographic-filtering/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhones |iPads |มือถือ Android |แท็บเล็ต Android |มือถือ Windows 10 |

เมื่อคุณดูที่รายงาน Power BI บนอุปกรณ์เคลื่อนที่ของคุณ คุณเห็นไอคอนรูปเข็มหมุดเล็ก ๆ ที่มุมบนขวาหรือไม่? ถ้าเป็นเช่นนั้น คุณสามารถกรองรายงานตามตำแหน่งที่ตั้งทางภูมิศาสตร์ของคุณ

> [!NOTE]
> คุณสามารถกรองตามตำแหน่ง ถ้าชื่อทางภูมิศาสตร์ในรายงานเป็นภาษาอังกฤษเท่านั้น &#150; ตัวอย่างเช่น "New York City" หรือ "Germany" แท็บเล็ต Windows 10 และพีซีไม่สนับสนุนการกรองทางภูมิศาสตร์ แต่มือถือ Windows 10 ทำได้
> 
> 

## <a name="filter-your-report-by-your-geographic-location"></a>กรองรายงานของคุณตามที่ตั้งทางภูมิศาสตร์ของคุณ
1. เปิดรายงานในแอป Power BI สำหรับอุปกรณ์เคลื่อนที บนอุปกรณ์เคลื่อนที่ของคุณ
2. ถ้ารายงานมีข้อมูลทางภูมิศาสตร์ คุณเห็นข้อความขออนุญาตให้ Power BI เข้าถึงตำแหน่งที่ตั้งของคุณ คลิก**อนุญาต** แล้วให้แตะ**อนุญาต**อีกครั้ง
3. แตะที่เข็มหมุด ![ไอคอนเข็มหมุด](media/mobile-apps-geographic-filtering/power-bi-mobile-geo-icon.png). คุณสามารถกรองตาม เมือง รัฐ/จังหวัด หรือ ประเทศ/ภูมิภาค ขึ้นอยู่กับข้อมูลในรายงาน ตัวกรองแสดงรายการตัวเลือก เฉพาะที่ตรงกับตำแหน่งปัจจุบันของคุณ
   
    ![ตัวกรองเข็มหมุด](media/mobile-apps-geographic-filtering/power-bi-mobile-geo-map-set-filter.png)

## <a name="why-dont-i-see-location-tags-on-a-report"></a>ทำไมฉันจึงไม่เห็นแท็กตำแหน่งที่ตั้งในรายงาน
เงื่อนไขทั้งสามข้างล่างนี้ต้องเป็นจริง เพื่อคุณจะได้เห็นแท็กตำแหน่งที่ตั้ง 

* บุคคลที่สร้างรายงานใน Power BI Desktop [จัดประเภทข้อมูลทางภูมิศาสตร์](desktop-mobile-geofiltering.md)ให้กับคอลัมน์อย่างน้อยหนึ่งคอลัมน์ เช่น เมือง รัฐ หรือประเทศ/ภูมิภาค
* คุณอยู่ในตำแหน่งที่มีข้อมูลในคอลัมน์นั้น
* คุณกำลังใช้อุปกรณ์เคลื่อนที่อย่างใดอย่างหนึ่งในนี้:
  * iOS (iPad, iPhone, iPod)
  * มือถือหรือแท็บเล็ต Android
  * มือถือ Windows 10 (อุปกรณ์ Windows 10 อื่น ๆ เช่นพีซีและแท็บเล็ตไม่สนับสนุนการกรองทางภูมิศาสตร์)

อ่านเพิ่มเติมเกี่ยวกับ[การตั้งค่าการกรองทางภูมิศาสตร์](desktop-mobile-geofiltering.md)ใน Power BI Desktop

### <a name="next-steps"></a>ขั้นตอนถัดไป
* [เชื่อมต่อกับข้อมูล Power BI จากโลกแห่งความจริง](mobile-apps-data-in-real-world-context.md)ด้วยแอปสำหรับอุปกรณ์เคลื่อนที่
* [จัดประเภทข้อมูลใน Power BI Desktop](desktop-data-categorization.md) 
* คำถามหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


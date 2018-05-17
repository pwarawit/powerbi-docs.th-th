---
title: ปรับวิชวล Power BI ให้เหมาะสมกับทุกขนาด
description: เรียนรู้วิธีการปรับวิชวลใน Power BI Desktop และบริการ Power BI สำหรับแอป Power BI บนมือถือให้เหมาะสม
services: powerbi
documentationcenter: ''
author: maggiesMSFT
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
ms.date: 10/13/2017
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 4c80048213b20365102bcb9c6842c342d8b9052b
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>ปรับวิชวล Power BI ให้เหมาะสมกับทุกขนาด
คุณสามารถตั้งค่าวิชวลในแดชบอร์ดหรือรายงานให้เป็นแบบ*ตอบสนอง* นั่นคือสามารถเปลี่ยนแปลงตัวเองเพื่อแสดงข้อมูลและข้อมูลเชิงลึกให้ได้มากที่สุด โดยไม่ขึ้นกับขนาดหน้าจอได้

เมื่อวิชวลเปลี่ยนขนาด Power BI จัดลำดับความสำคัญมุมมองข้อมูล ตัวอย่างเช่น เอาช่องว่างภายในออก และการย้ายคำอธิบายแผนภูมิไปไว้ด้านบนของวิชวลโดยอัตโนมัติ เพื่อให้วิชวลยังคงให้ข้อมูลแม้ว่าจะมีขนาดเล็กลง การตอบสนอง จะมีประโยชน์โดยเฉพาะอย่างยิ่งในวิชวลในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ บนมือถือ

![ตอบสนองต่อการปรับขนาดวิชวล](media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

คุณสามารถเปิดการตอบสนองสำหรับวิชวลใด ๆ ทั้งแกน X และแกน Y และตัวแบ่งส่วนข้อมูลได้

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>เปิดใช้งานการตอบสนองใน Power BI Desktop
1. ใน Power BI Desktop บนแท็บ**มุมมอง** ตรวจสอบให้แน่ใจว่า คุณอยู่ใน**เค้าโครงเดสก์ท็อป**
   
    ![ไอคอนเค้าโครงเดสก์ท็อป](media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. เลือกวิชวล และในบานหน้าต่าง**การจัดรูปแบบการแสดงข้อมูล** เลือกส่วน**รูปแบบ**
3. ขยาย**ทั่วไป** > และเลื่อน**ตอบสนอง** ไปยัง**เปิด**
   
    ![เปิดการตอบสนอง](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     ตอนนี้ เมื่อคุณ[สร้างรายงานที่ปรับให้เหมาะสมสำหรับมือถือ](desktop-create-phone-report.md)และเพิ่มวิชวลนี้ วิชวลจะปรับขนาดตามอย่างนุ่มนวล

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>เปิดใช้งานการตอบสนองในบริการของ Power BI
คุณสามารถเปิดใช้งานการตอบสนองสำหรับวิชวลในรายงาน ในบริการของ Power BI คุณจำเป็นต้องแก้ไขรายงานได้

1. ในรายงาน ในบริการของ Power BI ([https://powerbi.com](https://powerbi.com)), เลือก**แก้ไขรายงาน**
2. เลือกวิชวล และในบานหน้าต่าง**การจัดรูปแบบการแสดงข้อมูล** เลือกส่วน**รูปแบบ**
3. ขยาย**ทั่วไป** > และเลื่อน**ตอบสนอง** ไปยัง**เปิด**
   
    ![เปิดการตอบสนอง](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     ตอนนี้ เมื่อคุณ[สร้างมุมมองโทรศัพท์ของแดชบอร์ด](service-create-dashboard-mobile-phone-view.md)และเพิ่มวิชวลนี้ วิชวลจะปรับขนาดตามอย่างนุ่มนวล

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [สร้างรายงานที่ปรับให้เหมาะสมสำหรับแอปมือถือ Power BI](desktop-create-phone-report.md)
* [สร้างมุมมองโทรศัพท์ของแดชบอร์ดใน Power BI](service-create-dashboard-mobile-phone-view.md)
* [ดูรายงาน Power BI ที่ปรับให้เหมาะสมกับมือถือของคุณ](mobile-apps-view-phone-report.md)
* คำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


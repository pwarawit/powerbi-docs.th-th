---
title: ปรับวิชวล Power BI ให้เหมาะสมกับทุกขนาด
description: เรียนรู้วิธีการปรับวิชวลในรายงานที่มีอยู่ใน Power BI Desktop และบริการ Power BI สำหรับแอป Power BI บนมือถือให้เหมาะสม
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/13/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 4372f37cf6afc8fe51d6650ddd888bd41d3ea678
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54280136"
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>ปรับวิชวล Power BI ให้เหมาะสมกับทุกขนาด
ตามค่าเริ่มต้น เมื่อคุณสร้างรายงานใหม่ ภาพจะถูกตั้งค่าเป็น*แบบตอบสนอง*: ภาพเปลี่ยนการแสดงผลข้อมูลทั่วไปและข้อมูลเชิงลึกปริมาณมากได้ โดยไม่ขึ้นอยู่กับขนาดของหน้าจอ สำหรับรายงานเก่า คุณสามารถตั้งค่าวิชวลเพื่อปรับขนาดให้ได้มากที่สุดเช่นกัน

เมื่อเปลี่ยนขนาดภาพ Power BI ก็จะจัดลำดับความสำคัญมุมมองข้อมูล ตัวอย่างเช่น เอาช่องว่างภายในออก และย้ายคำอธิบายแผนภูมิไปไว้ด้านบนสุดของภาพโดยอัตโนมัติ เพื่อให้ภาพยังคงแสดงข้อมูลได้ แม้ว่าจะมีขนาดเล็กลงก็ตาม การตอบสนอง จะมีประโยชน์โดยเฉพาะอย่างยิ่งในวิชวลในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ บนมือถือ

![การปรับขนาดภาพแบบตอบสนอง](media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

วิชวลใดๆ ทั้งแกน X และแกน Y และตัวแบ่งส่วนข้อมูลสามารถตอบสนองตามที่ปรับขนาดได้เช่นกัน

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>เปิดใช้งานการตอบสนองใน Power BI Desktop
1. สำหรับรายงานเก่าใน Power BI Desktop บนแท็บ**มุมมอง** ตรวจสอบให้แน่ใจว่า คุณอยู่ใน**เค้าโครงเดสก์ท็อป**
   
    ![ไอคอนเค้าโครงเดสก์ท็อป](media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. เลือกวิชวล และในบานหน้าต่าง**การจัดรูปแบบการแสดงข้อมูล** เลือกส่วน**รูปแบบ**
3. ขยาย**ทั่วไป** > และเลื่อน**ตอบสนอง** ไปยัง**เปิด**
   
    ![เปิดการตอบสนอง](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     ตอนนี้ เมื่อคุณ[สร้างรายงานที่ปรับให้เหมาะสมสำหรับมือถือ](../desktop-create-phone-report.md)และเพิ่มวิชวลนี้ วิชวลจะปรับขนาดตามอย่างนุ่มนวล

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>เปิดใช้งานการตอบสนองในบริการของ Power BI
คุณสามารถเปิดใช้งานการตอบสนองสำหรับวิชวลในรายงานเก่าในบริการของ Power BI คุณจำเป็นต้องแก้ไขรายงานได้

1. ในรายงาน ในบริการของ Power BI ([https://powerbi.com](https://powerbi.com)) เลือก**แก้ไขรายงาน**
2. เลือกวิชวล และในบานหน้าต่าง**การจัดรูปแบบการแสดงข้อมูล** เลือกส่วน**รูปแบบ**
3. ขยาย**ทั่วไป** > และเลื่อน**ตอบสนอง** ไปยัง**เปิด**
   
    ![เปิดการตอบสนอง](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     ตอนนี้ เมื่อคุณ[สร้างมุมมองโทรศัพท์ของรายงานนี้](../desktop-create-phone-report.md)และเพิ่มวิชวลนี้ วิชวลจะปรับขนาดตามอย่างน่าพอใจ

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [สร้างรายงานที่ปรับให้เหมาะสมสำหรับแอปมือถือ Power BI](../desktop-create-phone-report.md)
* [ดูรายงาน Power BI ที่ปรับให้เหมาะสมกับโทรศัพท์ของคุณ](../consumer/mobile/mobile-apps-view-phone-report.md)
* คำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


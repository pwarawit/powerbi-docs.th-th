---
title: ปรับวิชวล Power BI ให้เหมาะสมกับทุกขนาด
description: เรียนรู้วิธีการปรับวิชวลในรายงานที่มีอยู่ใน Power BI Desktop และบริการ Power BI สำหรับแอป Power BI บนมือถือให้เหมาะสม
author: maggiesMSFT
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/13/2018
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: d85d4bd60c341ef588cf56b1345f28aa25b810de
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2018
ms.locfileid: "44748704"
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>ปรับวิชวล Power BI ให้เหมาะสมกับทุกขนาด
โดยค่าเริ่มต้น เมื่อคุณสร้างรายงานใหม่ วิชวลเป็นแบบ*ตอบสนอง*: นั่นคือวิชวลจะสามารถเปลี่ยนแปลงเพื่อแสดงข้อมูลและข้อมูลเชิงลึกให้ได้มากที่สุด โดยไม่ขึ้นกับขนาดหน้าจอได้ สำหรับรายงานเก่า คุณสามารถตั้งค่าวิชวลเพื่อปรับขนาดให้ได้มากที่สุดเช่นกัน

เมื่อเปลี่ยนขนาดภาพ Power BI ก็จะจัดลำดับความสำคัญมุมมองข้อมูล ตัวอย่างเช่น เอาช่องว่างภายในออก และย้ายคำอธิบายแผนภูมิไปไว้ด้านบนสุดของภาพโดยอัตโนมัติ เพื่อให้ภาพยังคงแสดงข้อมูลได้ แม้ว่าจะมีขนาดเล็กลงก็ตาม การตอบสนอง จะมีประโยชน์โดยเฉพาะอย่างยิ่งในวิชวลในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ บนมือถือ

![การปรับขนาดภาพแบบตอบสนอง](./media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

วิชวลใดๆ ทั้งแกน X และแกน Y และตัวแบ่งส่วนข้อมูลสามารถตอบสนองตามที่ปรับขนาดได้เช่นกัน

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>เปิดใช้งานการตอบสนองใน Power BI Desktop
1. สำหรับรายงานเก่าใน Power BI Desktop บนแท็บ**มุมมอง** ตรวจสอบให้แน่ใจว่า คุณอยู่ใน**เค้าโครงเดสก์ท็อป**
   
    ![ไอคอนเค้าโครงเดสก์ท็อป](./media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. เลือกวิชวล และในบานหน้าต่าง**การจัดรูปแบบการแสดงข้อมูล** เลือกส่วน**รูปแบบ**
3. ขยาย**ทั่วไป** > และเลื่อน**ตอบสนอง** ไปยัง**เปิด**
   
    ![เปิดการตอบสนอง](././media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     ตอนนี้ เมื่อคุณ[สร้างรายงานที่ปรับให้เหมาะสมสำหรับมือถือ](../desktop-create-phone-report.md)และเพิ่มวิชวลนี้ วิชวลจะปรับขนาดตามอย่างนุ่มนวล

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>เปิดใช้งานการตอบสนองในบริการของ Power BI
คุณสามารถเปิดใช้งานการตอบสนองสำหรับวิชวลในรายงานเก่าในบริการของ Power BI คุณจำเป็นต้องแก้ไขรายงานได้

1. ในรายงาน ในบริการของ Power BI ([https://powerbi.com](https://powerbi.com)) เลือก**แก้ไขรายงาน**
2. เลือกวิชวล และในบานหน้าต่าง**การจัดรูปแบบการแสดงข้อมูล** เลือกส่วน**รูปแบบ**
3. ขยาย**ทั่วไป** > และเลื่อน**ตอบสนอง** ไปยัง**เปิด**
   
    ![เปิดการตอบสนอง](././media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     ตอนนี้ เมื่อคุณ[สร้างมุมมองโทรศัพท์ของรายงานนี้](../desktop-create-phone-report.md)และเพิ่มวิชวลนี้ วิชวลจะปรับขนาดตามอย่างน่าพอใจ

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [สร้างรายงานที่ปรับให้เหมาะสมสำหรับแอปมือถือ Power BI](../desktop-create-phone-report.md)
* [ดูรายงาน Power BI ที่ปรับให้เหมาะสมกับโทรศัพท์ของคุณ](../consumer/mobile/mobile-apps-view-phone-report.md)
* คำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


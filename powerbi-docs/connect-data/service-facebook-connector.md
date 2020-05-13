---
title: 'บริการจากบุคคลที่สาม: ตัวเชื่อมต่อ Facebook สำหรับ Power BI Desktop'
description: 'บริการจากบุคคลที่สาม: ตัวเชื่อมต่อ Facebook สำหรับ Power BI Desktop'
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 02/20/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 882cddf7728a27e78056a35c14fde20f00678e33
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83309555"
---
# <a name="use-the-facebook-connector-for-power-bi-desktop"></a>ใช้ตัวเชื่อมต่อ Facebook สำหรับ Power BI Desktop 
ตัวเชื่อมต่อ Facebook ใน**Power BI Desktop**อาศัย Facebook Graph API ด้วยเหตุนี้ คุณลักษณะและความพร้อมใช้งานอาจแตกต่างกันเมื่อเวลาผ่านไป

คุณสามารถดู[บทช่วยสอนเกี่ยวกับตัวเชื่อมต่อ Facebook สำหรับ Power BI Desktop](desktop-tutorial-facebook-analytics.md)ได้

> [!IMPORTANT]
> **การยกเลิกการสนับสนุนของประกาศตัวเชื่อมต่อข้อมูล Facebook:** การนำเข้าและรีเฟรชข้อมูลจาก Facebook ใน Excel จะไม่สามารถทำงานได้อย่างถูกต้องอีกต่อไปโดยเริ่มในเดือนเมษายน 2020 คุณสามารถใช้ตัวเชื่อมต่อ *Get & Transform (Power Query)* ของ Facebook ได้จนกว่าจะถึงเวลานั้น หลังจากวันที่ดังกล่าว คุณจะไม่สามารถเชื่อมต่อกับ Facebook และจะได้รับข้อความข้อผิดพลาด เราขอแนะนำให้คุณปรับเปลี่ยนหรือลบคิวรี *Get & Transform (Power Query)* ที่มีอยู่ ที่ใช้ตัวเชื่อมต่อ Facebook โดยเร็วที่สุดเพื่อหลีกเลี่ยงผลลัพธ์ที่ไม่คาดคิด


Facebook v1.0 ของ Graph API หมดอายุเมื่อวันที่ 30 เมษายน 2015 Power BI ใช้ API Graph เบื้องหลังสำหรับตัวเชื่อมต่อ Facebook ช่วยให้คุณสามารถเชื่อมต่อและวิเคราะห์ข้อมูลของคุณได้

การสอบถามที่สร้างขึ้นก่อนวันที่ 30 เมษายน 2015 อาจไม่สามารถใช้งานได้อีกต่อไปหรือส่งกลับข้อมูลน้อยลง หลังจากวันที่ 30 เมษายน 2015, Power BI ได้นำ v2.8 มาใช้งานในทุกการใช้งานไปยัง Facebook API ถ้าการสอบถามของคุณสร้างขึ้นก่อนวันที่ 30 เมษายน 2015 และคุณยังไม่ได้ใช้มาตั้งแต่วันที่ดังกล่าว คุณอาจต้องรับรองความถูกต้องอีกครั้งเพื่ออนุมัติชุดสิทธิ์ที่เราจะขอใหม่

แม้ว่าเราพยายามเผยแพร่อัปเดตที่สอดคล้องกับการเปลี่ยนแปลงใด ๆ API อาจเปลี่ยนแปลงในลักษณะที่ส่งผลกระทบต่อผลลัพธ์ของการสอบถามที่เราสร้างขึ้นได้ ในบางกรณี บางแบบสอบถามอาจไม่สนับสนุนอีกต่อไป เนื่องจากการต้องพึ่งพาจากบุคคลที่สามนี้ เราไม่สามารถรับประกันผลลัพธ์การสอบถามของคุณเมื่อใช้ตัวเชื่อมต่อนี้ได้

รายละเอียดเพิ่มเติมเกี่ยวกับการเปลี่ยนแปลงใน Facebook API ที่พร้อมใช้งาน[ที่นี่](https://developers.facebook.com/docs/apps/changelog#v2_0)


---
title: 'บริการของบุคคลที่สาม: ตัวเชื่อมต่อ Facebook สำหรับ Power BI Desktop'
description: 'บริการของบุคคลที่สาม: ตัวเชื่อมต่อ Facebook สำหรับ Power BI Desktop'
services: powerbi
documentationcenter: ''
author: davidiseminger
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
ms.date: 02/22/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 894791ddc4eb632ad4dc0ee55f19bbadad5e28d6
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
---
# <a name="facebook-connector-for-power-bi-desktop"></a>ตัวเชื่อมต่อ Facebook สำหรับ Power BI Desktop
ตัวเชื่อมต่อ Facebook ใน**Power BI Desktop**อาศัย Facebook Graph API ด้วยเหตุนี้ คุณลักษณะและความพร้อมใช้งานอาจแตกต่างกันเมื่อเวลาผ่านไป

คุณสามารถดู[บทช่วยสอนเกี่ยวกับตัวเชื่อมต่อ Facebook สำหรับ Power BI Desktop](desktop-tutorial-facebook-analytics.md)ได้

Facebook v1.0 ของ Graph API หมดอายุเมื่อวันที่ 30 เมษา<sup>ยน</sup> 2015 Power BI ใช้ API Graph เบื้องหลังสำหรับตัวเชื่อมต่อ Facebook ช่วยให้คุณสามารถเชื่อมต่อและวิเคราะห์ข้อมูลของคุณได้

การสอบถามที่สร้างขึ้นก่อนวันที่ 30 เมษา<sup>ยน</sup> 2015 อาจไม่สามารถใช้งานได้อีกต่อไปหรือส่งกลับข้อมูลน้อยลง หลังจากวันที่ 30 เมษา<sup>ยน</sup> 2015, Power BI ได้นำ v2.8 มาใช้งานในทุกการใช้งานไปยัง Facebook API ถ้าการสอบถามของคุณสร้างขึ้นก่อนวันที่ 30 เมษายน 2015 และคุณยังไม่ได้ใช้มาตั้งแต่วันที่ดังกล่าว คุณอาจต้องรับรองความถูกต้องอีกครั้งเพื่ออนุมัติชุดสิทธิ์ที่เราจะขอใหม่

แม้ว่าเราพยายามเผยแพร่อัปเดตที่สอดคล้องกับการเปลี่ยนแปลงใด ๆ API อาจเปลี่ยนแปลงในลักษณะที่ส่งผลกระทบต่อผลลัพธ์ของการสอบถามที่เราสร้างขึ้นได้ ในบางกรณี บางแบบสอบถามอาจไม่สนับสนุนอีกต่อไป เนื่องจากการต้องพึ่งพาจากบุคคลที่สามนี้ เราไม่สามารถรับประกันผลลัพธ์การสอบถามของคุณเมื่อใช้ตัวเชื่อมต่อนี้ได้

รายละเอียดเพิ่มเติมเกี่ยวกับการเปลี่ยนแปลงใน Facebook API ที่พร้อมใช้งาน[ที่นี่](https://developers.facebook.com/docs/apps/changelog#v2_0)


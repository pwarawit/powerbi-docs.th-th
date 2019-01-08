---
title: เชื่อมต่อกับ Lithium ด้วย Power BI
description: Lithium สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 9029d5b6268cacf17fc862a4c0a3d19f440f7de1
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007947"
---
# <a name="connect-to-lithium-with-power-bi"></a>เชื่อมต่อกับ Lithium ด้วย Power BI
Lithium สร้างความสัมพันธ์ที่น่าเชื่อถือระหว่างแบรนด์ที่ดีที่สุดในโลกกับลูกค้าของตน ช่วยให้ผู้คนได้รับคำตอบสำหรับคำถามและแชร์ประสบการณ์การใช้งานของตน ด้วยการเชื่อมต่อชุดเนื้อหา Lithium ไปยัง Power BI คุณสามารถวัดหน่วยวัดหลักเกี่ยวกับชุมชนออนไลน์ของคุณได้ เพื่อช่วยขับเคลื่อนการขาย ลดต้นทุนการบริการ และเพิ่มความซื่อสัตย์ต่อแบรนด์ 

เชื่อมต่อไปยัง[ชุดเนื้อหา Lithium](https://app.powerbi.com/getdata/services/lithium) สำหรับ Power BI

>[!NOTE]
>ชุดเนื้อหา Power BI ใช้ Lithium API การเรียกใช้ API มากเกินไปอาจมีค่าธรรมเนียมเพิ่มเติมจาก Lithium โปรดตรวจสอบกับผู้ดูแลระบบ Lithium ของคุณ

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-lithium/pbi_getdata.png) 
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-lithium/pbi_getservices.png) 
3. เลือก**Lithium** \> **รับ**
   
   ![](media/service-connect-to-lithium/lithiumconnect.png)
4. ใส่ URL ของชุมชน Lithium ของคุณ ซึ่งจะอยู่ในรูปแบบ *https://community.yoursite.com*
   
   ![](media/service-connect-to-lithium/params.png)
5. เมื่อมีข้อความปรากฏ ใส่ข้อมูลประจำตัวของ Lithium เลือก**oAuth 2**เป็นกลไกการรับรองความถูกต้อง แล้วคลิก**ลงชื่อเข้าใช้**และทำตามขั้นตอนการรับรองความถูกต้อง Lithium
   
   ![](media/service-connect-to-lithium/creds.png)
   
   ![](media/service-connect-to-lithium/creds2.png)
6. เมื่อขั้นตอนการเข้าสู่ระบบเสร็จสมบูรณ์ ระบบจะเริ่มกระบวนการนำเข้า เมื่อเสร็จสิ้น แดชบอร์ดใหม่ รายงาน และแบบจำลองจะปรากฏในบานหน้าต่างนำทาง เลือกแดชบอร์ดเพื่อดูข้อมูลที่นำเข้าของคุณ
   
    ![](media/service-connect-to-lithium/lithium.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="system-requirements"></a>ความต้องการของระบบ
ชุดเนื้อหา Lithium ต้องมีชุมชน Lithium v15.9 หรือเวอร์ชันสูงกว่า โปรดตรวจสอบกับผู้ดูแลระบบ Lithium ของคุณเพื่อยืนยัน

## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI คืออะไร](power-bi-overview.md)

[Power BI แนวคิดพื้นฐาน](consumer/end-user-basic-concepts.md)


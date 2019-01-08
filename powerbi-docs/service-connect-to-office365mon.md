---
title: เชื่อมต่อกับ Office365Mon ด้วย Power BI
description: Office365Mon for Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: cce886edbed00075efaa43bae9c8a712929e8b9a
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/04/2019
ms.locfileid: "54007993"
---
# <a name="connect-to-office365mon-with-power-bi"></a>เชื่อมต่อกับ Office365Mon ด้วย Power BI
กำลังวิเคราะห์การหยุดการทำงานและข้อมูลสมรรถนะทางสุขภาพของ Office 365 ของคุณ ซึ่งทำได้ง่ายด้วย Power BI และชุดเนื้อหา Office365Mon Power BI ดึงข้อมูลของคุณ ทั้งการหยุดทำงานและปัญหาด้านสุขภาพ จากนั้นสร้างแดชบอร์ดแบบคิดนอกกรอบและรายงานที่ยึดตามข้อมูลนั้น

เชื่อมต่อไปยัง[ชุดเนื้อหา Office365Mon](https://app.powerbi.com/groups/me/getdata/services/office365mon)สำหรับ Power BI

>[!NOTE]
>จำเป็นต้องมีบัญชีผู้ดูแลระบบ Office365Mon เพื่อเชื่อมต่อและโหลดชุดเนื้อหา Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-office365mon/pbi_getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-office365mon/pbi_getservices.png) 
3. เลือก**Office365Mon** \> **รับ**
   
   ![](media/service-connect-to-office365mon/o365mon.png)
4. สำหรับวิธีการรับรองความถูกต้อง ให้เลือก **oAuth2** \> **ลงชื่อเข้าใช้**
   
   เมื่อไดถูกถาม ให้ใส่ข้อมูลประจำตัวของผู้ดูแลระบบ Office365Mon และทำตามกระบวนการรับรองความถูกต้อง
   
   ![](media/service-connect-to-office365mon/creds.png)
   
   ![](media/service-connect-to-office365mon/creds2.png)
5. หลังจากที่ Power BI นำเข้าข้อมูลแล้ว คุณจะเห็นแดชบอร์ด รายงาน และชุดข้อมูลใหม่ ในบานหน้าต่างนำทางด้านซ้ายมือ รายการใหม่ถูกทำเครื่องหมายด้วยเครื่องหมายดอกจันสีเหลือง \* เลือกกรอก Office365Mon
   
   ![](media/service-connect-to-office365mon/dashboard4.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="troubleshooting"></a>การแก้ไขปัญหา
ถ้าคุณได้รับข้อผิดพลาด **"เข้าสู่ระบบล้มเหลว"** หลังจากใช้ข้อมูลประจำตัวของการสมัครใช้งาน Office365Mon เข้าระบบ จากนั้นบัญชีคุณไม่มีสิทธิ์ในการดึงข้อมูล Office365Mon จากบัญชีของคุณ ตรวจสอบนี่เป็นบัญชีผู้ดูแลระบบ และลองอีกครั้ง

## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI คืออะไร](power-bi-overview.md)

[รับข้อมูลสำหรับ Power BI](service-get-data.md)


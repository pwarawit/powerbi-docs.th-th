---
title: เชื่อมต่อกับ Office365Mon ด้วย Power BI
description: Office365Mon for Power BI
author: paulinbar
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: how-to
ms.date: 11/26/2019
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 422782c3036f94c1ea764f46135200116092d70c
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/10/2020
ms.locfileid: "86216238"
---
# <a name="connect-to-office365mon-with-power-bi"></a>เชื่อมต่อกับ Office365Mon ด้วย Power BI
การวิเคราะห์การหยุดการทำงานและข้อมูลสมรรถนะการทำงานของ Office 365 ของคุณทำได้ง่ายด้วย Power BI และแอปแม่แบบ Office365Mon Power BI ดึงข้อมูลของคุณ ทั้งการหยุดทำงานและปัญหาด้านสุขภาพ จากนั้นสร้างแดชบอร์ดแบบคิดนอกกรอบและรายงานที่ยึดตามข้อมูลนั้น

เชื่อมต่อไปยัง[แอปแม่แบบ Office365Mon](https://msit.powerbi.com/groups/me/getapps/services/office365mon.office365mon_powerbi_v3)สำหรับ Power BI

>[!NOTE]
>จำเป็นต้องมีบัญชีผู้ดูแลระบบ Office365Mon เพื่อเชื่อมต่อและโหลดแอปแม่แบบ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือก**รับข้อมูล**ที่ด้านล่างของบานหน้าต่างนำทาง
   
   ![ภาพหน้าจอของปุ่มรับข้อมูล ที่แสดงปุ่มในบานหน้าต่างการนำทาง](media/service-connect-to-office365mon/pbi_getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![ภาพหน้าจอของกล่องโต้ตอบบริการ ที่แสดงปุ่มรับ](media/service-connect-to-office365mon/pbi_getservices.png) 
3. เลือก **Office365Mon** \> **รับ**
   
   ![ภาพหน้าจอของกล่องโต้ตอบ Office365Mon ที่แสดงลิงก์รับ](media/service-connect-to-office365mon/o365mon.png)
4. สำหรับวิธีการรับรองความถูกต้อง ให้เลือก **oAuth2** \> **ลงชื่อเข้าใช้**
   
   เมื่อไดถูกถาม ให้ใส่ข้อมูลประจำตัวของผู้ดูแลระบบ Office365Mon และทำตามกระบวนการรับรองความถูกต้อง
   
   ![ภาพหน้าจอของกล่องโต้ตอบ Office365Mon ที่แสดง o Auth2 ในเขตข้อมูลวิธีการรับรองความถูกต้อง](media/service-connect-to-office365mon/creds.png)
   
   ![ภาพหน้าจอของการลงชื่อเข้าใช้ Office365Mon ที่แสดงการส่งข้อความแจ้งเตือนสำหรับข้อมูลประจำตัว](media/service-connect-to-office365mon/creds2.png)
5. หลังจากที่ Power BI นำเข้าข้อมูลแล้ว คุณจะเห็นแดชบอร์ด รายงาน และชุดข้อมูลใหม่ในบานหน้าต่างนำทาง รายการใหม่ถูกทำเครื่องหมายด้วยเครื่องหมายดอกจันสีเหลือง \* เลือกกรอก Office365Mon
   
   ![ภาพหน้าจอของบานหน้าต่างการนำทางใน Power B I ที่สดงแดชบอร์ด รายงาน และชุดข้อมูล](media/service-connect-to-office365mon/dashboard4.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](../consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](../create-reports/service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](../consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="troubleshooting"></a>การแก้ไขปัญหา
ถ้าคุณได้รับข้อผิดพลาด **"เข้าสู่ระบบล้มเหลว"** หลังจากใช้ข้อมูลประจำตัวของการสมัครใช้งาน Office365Mon เข้าระบบ จากนั้นบัญชีคุณไม่มีสิทธิ์ในการดึงข้อมูล Office365Mon จากบัญชีของคุณ ตรวจสอบนี่เป็นบัญชีผู้ดูแลระบบ และลองอีกครั้ง

## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI คืออะไร](../fundamentals/power-bi-overview.md)

[รับข้อมูลสำหรับ Power BI](service-get-data.md)

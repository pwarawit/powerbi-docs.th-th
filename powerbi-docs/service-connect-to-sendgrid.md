---
title: เชื่อมต่อกับ SendGrid ด้วย Power BI
description: SendGrid สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: a05d78cfb0c1e34f0ec263f5455982cd4064905b
ms.sourcegitcommit: b53a6f5575f5f8bc443ecdca9c72525ce123518f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/30/2019
ms.locfileid: "70185817"
---
# <a name="connect-to-sendgrid-with-power-bi"></a>เชื่อมต่อกับ SendGrid ด้วย Power BI
ชุดเนื้อหา Power BI สำหรับ SendGrid ช่วยให้คุณสามารถแยกข้อมูลเชิงลึกและสถิติจากบัญชี SendGrid ของคุณได้ การใช้ชุดเนื้อหา SendGrid ทำให้คุณสามารถมดูสถิติ SendGrid ของคุณในแดชบอร์ดได้

[!INCLUDE [include-short-name](./includes/service-deprecate-content-packs.md)]

เชื่อมต่อไปยัง[ชุดเนื้อหา SendGrid](https://app.powerbi.com/getdata/services/sendgrid)สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-sendgrid/pbi_getdata.png) 
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-sendgrid/pbi_getservices.png) 
3. เลือกชุดเนื้อหา**SendGrid** และคลิก**รับ**
   
   ![](media/service-connect-to-sendgrid/sendgrid.png) 
4. เมื่อปรากฏข้อความขึ้น ใส่ชื่อผู้ใช้และรหัสผ่าน SendGrid ของคุณ เลือก**ลงชื่อเข้าใช้**
   
   ![](media/service-connect-to-sendgrid/pbi_sendgridsignin.png)
5. หลังจากที่ Power BI นำเข้าข้อมูลแล้ว คุณจะเห็นแดชบอร์ด รายงาน และชุดข้อมูลใหม่ในแผงนำทางด้านซ้าย พร้อมด้วยข้อมูลสถิติของอีเมลในรอบ 90 วันที่ผ่านมา รายการใหม่จะถูกทำเครื่องหมายด้วย เครื่องหมายดอกจันสีเหลือง\*
   
   ![](media/service-connect-to-sendgrid/pbi_sendgriddash.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
เมตริกต่อไปนี้จะพร้อมใช้งานในแดชบอร์ด SendGrid:

* สถิติอีเมลโดยรวม - คำขอ จัดส่งแล้ว ส่งกลับ สแปมที่ถูกบล็อก รายงานสแปม และอื่น ๆ
* สถิติอีเมลแยกตามประเภท
* สถิติอีเมลแยกตามภูมิศาสตร์
* สถิติอีเมลแยกตาม ISP
* สถิติอีเมลแยกตามอุปกรณ์ ไคลเอ็นต์ เบราว์เซอร์

## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI คืออะไร](power-bi-overview.md)

[รับข้อมูล](service-get-data.md)


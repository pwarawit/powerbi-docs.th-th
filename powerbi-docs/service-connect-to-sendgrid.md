---
title: เชื่อมต่อกับ SendGrid ด้วย Power BI
description: SendGrid สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: a0ae99e2dfad889840cc29ca4fa9f0f29397bf04
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/29/2018
ms.locfileid: "37135386"
---
# <a name="connect-to-sendgrid-with-power-bi"></a>เชื่อมต่อกับ SendGrid ด้วย Power BI
ชุดเนื้อหา Power BI สำหรับ SendGrid ช่วยให้คุณสามารถแยกข้อมูลเชิงลึกและสถิติจากบัญชี SendGrid ของคุณได้ การใช้ชุดเนื้อหา SendGrid ทำให้คุณสามารถมดูสถิติ SendGrid ของคุณในแดชบอร์ดได้

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

* ลอง[ถามคำถามในกล่อง Q&A](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานด้านใน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

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


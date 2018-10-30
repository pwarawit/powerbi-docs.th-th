---
title: ชุดเนื้อหา SQL Database Auditing
description: ชุดเนื้อหาการตรวจสอบฐานข้อมูล SQL สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: ce1769d343f5a5923b1a436a2cc0c97428f74152
ms.sourcegitcommit: 60fb46b61ac73806987847d9c606993c0e14fb30
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/25/2018
ms.locfileid: "50101146"
---
# <a name="sql-database-auditing-content-pack-for-power-bi"></a>ชุดเนื้อหาการตรวจสอบฐานข้อมูล SQL สำหรับ Power BI
ชุดเนื้อหา Power BI สำหรับ Azure [การตรวจสอบฐานข้อมูล SQL](/azure/sql-database/sql-database-auditing/) ช่วยให้คุณเข้าใจกิจกรรมเกี่ยวกับฐานข้อมูลของคุณและรับข้อมูลเชิงลึกในความขัดแย้งและความผิดปกติที่อาจสามารถระบุถึงปัญหาทางธุรกิจ หรือการละเมิดความปลอดภัยที่สงสัย 

เชื่อมต่อไปยังชุดเนื้อหา[การตรวจสอบฐานข้อมูล SQL](https://app.powerbi.com/getdata/services/sql-db-auditing) สำหรับ Power BI

>[!NOTE]
>ชุดเนื้อหานี้จะนำเข้าข้อมูลจากตารางทั้งหมดที่มี "บันทึกการตรวจสอบ (AuditLogs)" แสดงไว้ในชื่อ และเพิ่มเข้าในตารางโมเดลข้อมูลเดี่ยว โดยตั้งชื่อเป็น "บันทึกการตรวจสอบ (AuditLogs)" เหตุการณ์ K 250 ล่าสุดจะรวมเข้าไว้ด้วย และจะรีเฟรชข้อมูลรายวัน

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือก**รับข้อมูล**ที่ด้านล่างของแผงนำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_getdata.png) 
2. ในกล่องบริการ เลือกรับ
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_getservices.png) 
3. เลือก**การตรวจสอบฐานข้อมูล SQL** \> **รับ**
   
   ![](media/service-connect-to-azure-sql-database-auditing/sqldbaudit.png)
4. ในการเชื่อมต่อกับหน้าต่างการตรวจสอบฐานข้อมูล SQL:
   
   - ใส่ชื่อบัญชี Azure Table Storage หรือ URL ซึ่งเป็นที่จัดเก็บบันทึกของคุณ
   
   - ใส่ชื่อของเซิร์ฟเวอร์ SQL ที่คุณสนใจ ใส่ "\*" เพื่อโหลดบันทึกการตรวจสอบสำหรับเซิร์ฟเวอร์ทั้งหมด
   
   - ใส่ชื่อของฐานข้อมูล SQL ที่คุณสนใจ ใส่ "\*" เพื่อโหลดบันทึกการตรวจสอบสำหรับฐานข้อมูลทั้งหมด
   
   - ใส่ชื่อของตาราง Azure ที่ประกอบด้วยบันทึกที่คุณสนใจ ใส่ "\*" เพื่อโหลดบันทึกการตรวจสอบจากตารางทั้งหมดที่ประกอบด้วย "บันทึกการตรวจสอบ" ในชื่อของตารางนั้น
   
   >[!IMPORTANT]
   >เพื่อเหตุผลด้านประสิทธิภาพการทำงาน เราแนะนำให้คุณระบุชื่อตารางที่ชัดเจนด้วยเสมอ แม้ว่าบันทึกการตรวจสอบทั้งหมดจัดเก็บอยู่ในตารางเดียวก็ตาม
   
   - ใส่วันที่เริ่มต้นของบันทึกการตรวจสอบที่คุณสนใจ ใส่ "\*" เพื่อโหลดบันทึกการตรวจสอบโดยไม่มีขีดจำกัดเวลาต่ำสุด หรือ “1 วัน” เพื่อทำการโหลดบันทึกการตรวจสอบจากวันที่สุดท้าย
   
   - ใส่วันที่สิ้นสุดของบันทึกการตรวจสอบที่คุณสนใจ ใส่ "\*"เพื่อโหลดบันทึกการตรวจสอบ โดยไม่มีขีดจำกัดเวลาสูงสุด
   
   ![](media/service-connect-to-azure-sql-database-auditing/dbauditing_param.png)
5. สำหรับวิธีการรับรองความถูกต้อง เลือก**คีย์** ใส่**คีย์บัญชี**ของคุณ \> **ลงชื่อเข้าใช้**
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqlauditing3.png)
6. หลังจาก Power BI นำเข้าข้อมูล คุณเห็นแดชบอร์ด รายงาน และชุดข้อมูลใหม่ในแผงนำทางด้านซ้าย รายการใหม่จะถูกทำเครื่องหมายด้วย เครื่องหมายดอกจันสีเหลือง\*
   
   ![](media/service-connect-to-azure-sql-database-auditing/pbi_sqldbauditingnewdash.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="next-steps"></a>ขั้นตอนถัดไป
[รับข้อมูลสำหรับ Power BI](service-get-data.md)
[Power BI คืออะไร](power-bi-overview.md)

---
title: ชุดเนื้อหา SQL Database Auditing
description: ชุดเนื้อหาการตรวจสอบฐานข้อมูล SQL สำหรับ Power BI
services: powerbi
documentationcenter: ''
author: SarinaJoan
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
ms.date: 08/10/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: eec1af16156e4d4180dd130f4dd285bb78b19903
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815268"
---
# <a name="sql-database-auditing-content-pack-for-power-bi"></a>ชุดเนื้อหาการตรวจสอบฐานข้อมูล SQL สำหรับ Power BI
ชุดเนื้อหา Power BI สำหรับ Azure [การตรวจสอบฐานข้อมูล SQL](http://azure.microsoft.com/documentation/articles/sql-database-auditing-get-started/) ช่วยให้คุณเข้าใจกิจกรรมเกี่ยวกับฐานข้อมูลของคุณและรับข้อมูลเชิงลึกในความขัดแย้งและความผิดปกติที่อาจสามารถระบุถึงปัญหาทางธุรกิจ หรือการละเมิดความปลอดภัยที่สงสัย 

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

**ฉันต้องทำอะไรต่อ?**

* ลอง[ถามคำถามในกล่องถามตอบ](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานพื้นฐาน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="next-steps"></a>ขั้นตอนถัดไป
[รับข้อมูลสำหรับ Power BI](service-get-data.md)
[เริ่มต้นใช้งาน Power BI](service-get-started.md)

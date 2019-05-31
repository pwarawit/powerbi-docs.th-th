---
title: เชื่อมต่อกับ ServiceNow ด้วย Power BI
description: ServiceNow สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 285c22347f049e6b99cb97fa19efc6363d9b57cb
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "61163740"
---
# <a name="connect-to-servicenow-with-power-bi-for-incident-reporting"></a>เชื่อมต่อกับ ServiceNow ด้วย Power BI สำหรับการรายงานปัญหา
ServiceNow นำเสนอหลายผลิตภัณฑ์และการแก้ไขปัญหาที่รวมถึงทางด้านธุรกิจ การดำเนินการ และการจัดการ IT เพื่อปรับปรุงธุรกิจของคุณ ชุดเนื้อหานี้ประกอบด้วยหลายรายงานและข้อมูลเชิงลึกเกี่ยวกับการเปิด การแก้ไขล่าสุด และการปิดเหตุการณ์เมื่อเร็วๆนี้ของคุณ  

เชื่อมต่อกับชุดเนื้อหา Power BI สำหรับ[เหตุการณ์ใน ServiceNow](https://app.powerbi.com/getdata/services/servicenow)

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-servicenow/pbi_getdata.png) 
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-servicenow/pbi_getservices.png) 
3. เลือก**เหตุการณ์ ServiceNow** \> **รับ**
   
   ![](media/service-connect-to-servicenow/connect.png)
4. ใส่ URL ของอินสแตนซ์ ServiceNow ของคุณและช่วงของวัน/รายการในการนำเข้า โปรดทราบว่า ทันทีทีถึงขีดจำกัดหการนำเข้าจะหยุดทันที
   
   ![](media/service-connect-to-servicenow/params.png)
5. เมื่อได้รับการถาม ให้ใส่ข้อมูลประจำตัว ServiceNow **พื้นฐาน**ของคุณ โปรดทราบว่า การลงชื่อเข้าใช้เพียงครั้งเดียวยังไม่รองรับในปัจจุบัน รายละเอียดเพิ่มเติมเกี่ยวกับข้อกำหนดของระบบด้านล่างนี้
   
   ![](media/service-connect-to-servicenow/creds.png)
6. เมื่อขั้นตอนการเข้าสู่ระบบเสร็จสมบูรณ์ ระบบจะเริ่มกระบวนการนำเข้า เมื่อเสร็จสิ้น แดชบอร์ดใหม่ รายงาน และแบบจำลองจะปรากฏในบานหน้าต่างนำทาง เลือกแดชบอร์ดเพื่อดูข้อมูลที่นำเข้าของคุณ
   
    ![](media/service-connect-to-servicenow/dashboard.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="system-requirements"></a>ความต้องการของระบบ
เมื่อต้องการเชื่อมต่อคุณจะต้อง  

* บัญชีผู้ใช้ที่สามารถเข้าถึง yourorganization.service-now.com ด้วยการรับรองตัวตนพื้นฐาน (ลงชื่อเข้าระบบเพียงครั้งเดียวไม่ได้รับการสนับสนุนในเวอร์ชันนี้)  
* บัญชีผู้ใช้ต้องมีบทบาท rest_service และอ่านการเข้าถึงแตารางเหตุการณ์  

## <a name="troubleshooting"></a>การแก้ไขปัญหา
ถ้าคุณกำลังเข้าถึงข้อมูลประจำตัวที่มีข้อผิดพลาดในระหว่างการโหลด โปรดตรวจสอบสิ่งจำเป็นในการเข้าถึงตรงด้านบน ถ้าคุณมีสิทธิ์ที่ถูกต้องและจะยังคงมีปัญหา โปรดทำงานกับผู้ดูแลระบบ ServiceNow ของคุณเพื่อให้แน่ใจว่า คุณมีสิทธิ์ต่างๆเพิ่มเติมที่อาจจำเป็นสำหรับอินสแตนซ์แบบกำหนดเองของคุณ

ถ้าคุณเห็นเวลาในการโหลดนาน โปรดตรวจสอบจำนวนของเหตุการณ์และจำนวนวันที่คุณระบุในระหว่างการเชื่อมต่อ และพิจารณาการลดมันลง

## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI คืออะไร](power-bi-overview.md)

[Power BI แนวคิดพื้นฐาน](consumer/end-user-basic-concepts.md)


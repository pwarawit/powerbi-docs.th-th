---
title: เชื่อมต่อกับ SweetIQ ด้วย Power BI
description: SweetIQ สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6592405de2d76c14334c8c31e4af84cd5a090ed9
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34247561"
---
# <a name="connect-to-sweetiq-with-power-bi"></a>เชื่อมต่อกับ SweetIQ ด้วย Power BI
ชุดเนื้อหา Power BI ดึงข้อมูลจากบัญชี SweetIQ ของคุณ และสร้างชุดเนื้อหาแบบใช้ทันทีที่ช่วยให้คุณสามารถสำรวจข้อมูลของคุณได้อย่างง่ายดาย ใช้ชุดเนื้อหา SweetIQ เพื่อวิเคราะห์ข้อมูลเกี่ยวกับตำแหน่งที่ตั้ง การจัดรายการ การจัดอันดับ และบทวิจารณ์ของคุณ ข้อมูลจะถูกตั้งค่าการรีเฟรชเป็นรีเฟรชทุกวัน เพื่อแน่ใจว่าข้อมูลที่คุณกำลังตรวจติดตามอัปเดตแล้ว

เชื่อมต่อไปยัง[ชุดเนื้อหา SweetIQ](https://app.powerbi.com/groups/me/getdata/services/sweetiq) สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. ในแผงนำทางทางด้านซ้าย คลิก**รับข้อมูล**
   
    ![](media/service-connect-to-sweetiq/getdata.png)
2. เลือก**SweetIQ** และคลิก**รับ**
   
    ![](media/service-connect-to-sweetiq/sweetiq.png)
3. ระบุ SweetIQ Client ID ของคุณ ซึ่งโดยทั่วไปคือค่าตัวอักษรและตัวเลข สำหรับรายละเอียดในการค้นหาค่านี้ โปรดดูที่ด้านล่าง
   
    ![](media/service-connect-to-sweetiq/parameter.png)
4. เลือกประเภทการรับรองความถูกต้อง**คีย์**และใส่คีย์ Sweet IQ API ของคุณ ซึ่งโดยทั่วไปคือค่าตัวอักษรและตัวเลข สำหรับรายละเอียดในการค้นหาค่านี้ โปรดดูที่ด้านล่าง
   
    ![](media/service-connect-to-sweetiq/credentials.png)
5. Power BI จะเริ่มการโหลดข้อมูลของคุณ ซึ่งอาจใช้เวลาสักครู่ ทั้งนี้ขึ้นอยู่กับขนาดของข้อมูลในบัญชีของคุณ เมื่อดาวน์โหลดเสร็จสิ้นแล้ว คุณเห็นแดชบอร์ด รายงาน และชุดข้อมูลใหม่ในแผงนำทางด้านซ้าย
   
    ![](media/service-connect-to-sweetiq/dashboard.png)

**ฉันต้องทำอะไรต่อ?**

* ลอง[ถามคำถามในกล่องถามตอบ](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานพื้นฐาน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="finding-parameters"></a>การค้นหาพารามิเตอร์
ID ไคลเอ็นต์และคีย์ API สำหรับชุดเนื้อหานี้จะไม่เหมือนกับชื่อผู้ใช้และรหัสผ่าน SweetIQ ของคุณ

เลือก ID ไคลเอ็นต์สำหรับหนึ่งในไคลเอ็นต์ที่บัญชีของคุณมีสิทธิ์เข้าถึง คุณสามารถค้นหารายการของไคลเอ็นต์ได้ที่ใต้ "การจัดการลูกค้า" ในบัญชี SweetIQ ของคุณ

พูดคุยกับผู้ดูแลระบบของคุณสำหรับคีย์ API ของคุณ เพื่อให้สามารถเข้าถึงข้อมูลสำหรับไคลเอ็นต์ที่เฉพาะเจาะจง

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งาน Power BI](service-get-started.md)

[รับข้อมูลสำหรับ Power BI](service-get-data.md)


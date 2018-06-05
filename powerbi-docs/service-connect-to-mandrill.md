---
title: เชื่อมต่อกับ Mandrill ด้วย Power BI
description: Mandrill สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 5e12e32d947779f4ebc5bc2d238125c7359c08fe
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34242306"
---
# <a name="connect-to-mandrill-with-power-bi"></a>เชื่อมต่อกับ Mandrill ด้วย Power BI
ชุดเนื้อหา Power BI จะดึงข้อมูลจากบัญชี Mandrill ของคุณและสร้างแดชบอร์ด ชุดรายงาน และชุดข้อมูล เพื่อให้คุณสามารถสำรวจข้อมูลของคุณได้ ใช้การวิเคราะห์ของ Mandrill เพื่อรับข้อมูลเชิงลึกลงในจดหมายข่าวหรือแคมเปญการตลาดของคุณได้อย่างรวดเร็ว ข้อมูลจะถูกตั้งค่าการรีเฟรชเป็นรีเฟรชทุกวัน เพื่อแน่ใจว่าข้อมูลที่คุณกำลังตรวจติดตามอัปเดตแล้ว

เชื่อมต่อไปยัง[ชุดเนื้อหา Mandrill](http://app.powerbi.com/getdata/services/mandrill) สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือก**รับข้อมูล**ที่ด้านล่างของแผงนำทางด้านซ้ายมือ
   
    ![](media/service-connect-to-mandrill/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
    ![](media/service-connect-to-mandrill/services.png)
3. เลือก**Mandrill** > **รับ**
   
    ![](media/service-connect-to-mandrill/mandrill.png)
4. สำหรับ**วิธีการรับรองความถูกต้อง**เลือก**คีย์**และใส่คีย์ API ของคุณ คุณสามารถค้นหาคีย์บนแท็บ**ตั้งค่า**ของแดชบอร์ด Mandrill ได้ เลือก**ลงชื่อเข้าใช้**เพื่อเริ่มกระบวนการนำเข้า ซึ่งอาจใช้เวลาสักครู่ทั้งนี้ขึ้นอยู่กับปริมาณของข้อมูลในบัญชีของคุณ
   
    ![](media/service-connect-to-mandrill/auth.png)
5. หลังจาก Power BI นำเข้าข้อมูล คุณจะเห็นแดชบอร์ด รายงาน และชุดข้อมูลใหม่ในแผงนำทางด้านซ้าย นี่คือแดชบอร์ดตามเริ่มต้นที่ Power BI สร้างขึ้นเพื่อแสดงข้อมูลของคุณ
   
    ![](media/service-connect-to-mandrill/mandrill-dashboard1.jpg)

**ฉันต้องทำอะไรต่อ?**

* ลอง[ถามคำถามในกล่องถามตอบ](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานพื้นฐาน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งาน Power BI](service-get-started.md)

[Power BI - แนวคิดพื้นฐาน](service-basic-concepts.md)


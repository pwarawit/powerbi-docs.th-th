---
title: เชื่อมต่อกับ Mandrill ด้วย Power BI
description: Mandrill สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/29/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: aa685ae9b51e1f5044dab883d8de871dcc7ed5da
ms.sourcegitcommit: b7a9862b6da940ddebe61bc945a353f91cd0e4bd
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/04/2019
ms.locfileid: "71945856"
---
# <a name="connect-to-mandrill-with-power-bi"></a>เชื่อมต่อกับ Mandrill ด้วย Power BI
ชุดเนื้อหา Power BI จะดึงข้อมูลจากบัญชี Mandrill ของคุณและสร้างแดชบอร์ด ชุดรายงาน และชุดข้อมูล เพื่อให้คุณสามารถสำรวจข้อมูลของคุณได้ ใช้การวิเคราะห์ของ Mandrill เพื่อรับข้อมูลเชิงลึกลงในจดหมายข่าวหรือแคมเปญการตลาดของคุณได้อย่างรวดเร็ว ข้อมูลจะถูกตั้งค่าการรีเฟรชเป็นรีเฟรชทุกวัน เพื่อแน่ใจว่าข้อมูลที่คุณกำลังตรวจติดตามอัปเดตแล้ว

[!INCLUDE [include-short-name](./includes/service-deprecate-content-packs.md)]

เชื่อมต่อไปยัง[ชุดเนื้อหา Mandrill](http://app.powerbi.com/getdata/services/mandrill) สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
    ![](media/service-connect-to-mandrill/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
    ![](media/service-connect-to-mandrill/services.png)
3. เลือก**Mandrill** > **รับ**
   
    ![](media/service-connect-to-mandrill/mandrill.png)
4. สำหรับ**วิธีการรับรองความถูกต้อง**เลือก**คีย์**และใส่คีย์ API ของคุณ คุณสามารถค้นหาคีย์บนแท็บ**ตั้งค่า**ของแดชบอร์ด Mandrill ได้ เลือก**ลงชื่อเข้าใช้**เพื่อเริ่มกระบวนการนำเข้า ซึ่งอาจใช้เวลาสักครู่ทั้งนี้ขึ้นอยู่กับปริมาณของข้อมูลในบัญชีของคุณ
   
    ![](media/service-connect-to-mandrill/auth.png)
5. หลังจาก Power BI นำเข้าข้อมูล คุณจะเห็นแดชบอร์ด รายงาน และชุดข้อมูลใหม่ในแผงนำทางด้านซ้าย นี่คือแดชบอร์ดตามเริ่มต้นที่ Power BI สร้างขึ้นเพื่อแสดงข้อมูลของคุณ
   
    ![](media/service-connect-to-mandrill/mandrill-dashboard1.png)

**ฉันต้องทำอะไรต่อ?**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI คืออะไร](power-bi-overview.md)

[แนวคิดพื้นฐานสำหรับนักออกแบบในบริการ Power BI](service-basic-concepts.md)


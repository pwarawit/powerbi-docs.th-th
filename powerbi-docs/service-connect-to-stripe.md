---
title: เชื่อมต่อกับ Stripe ด้วย Power BI
description: Stripe สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 6a194a4d56f4a940ad892ccd2f9097dd782f49d3
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008545"
---
# <a name="connect-to-stripe-with-power-bi"></a>เชื่อมต่อกับ Stripe ด้วย Power BI
ภาพและสำรวจข้อมูล Stripe ของคุณใน Power BI ด้วยชุดเนื้อหา Power BI ชุดเนื้อหา Power BI Stripe ดึงข้อมูลเกี่ยวกับลูกค้า ค่าธรรมเนียม เหตุการณ์ และใบแจ้งหนี้ ข้อมูลมีเหตุการณ์หมื่นเหตุการณ์ล่าสุดและค่าใช้จ่ายห้าพันใน 30 วันที่ผ่านมา เนื้อหาจะถูกรีเฟรชโดยอัตโนมัติวันละครั้งตามการกำหนดเวลาที่คุณควบคุม 

เชื่อมต่อไปยัง[ชุดเนื้อหา Stripe สำหรับ Power BI](https://app.powerbi.com/getdata/services/stripe)

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกรับข้อมูลที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ  
   
    ![](media/service-connect-to-stripe/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**  
   
    ![](media/service-connect-to-stripe/services.png)  
3. เลือก**Stripe** &gt; **รับ**  
   
    ![](media/service-connect-to-stripe/stripe.png)  
4. ให้แจ้ง [คีย์ API](https://dashboard.stripe.com/account/apikeys) Stripe ของคุณเพื่อเชื่อมต่อ  
   
    ![](media/service-connect-to-stripe/creds.png)
5. กระบวนการนำเข้าจะเริ่มโดยอัตโนมัติ เมื่อเสร็จ แดชบอร์ดใหม่ รายงาน และรูปแบบ จะปรากฏในบานหน้าต่างนำทาง ที่ทำเครื่องหมายดอกจันไว้ เลือกแดชบอร์ดเพื่อดูข้อมูลที่นำเข้าของคุณ
   
    ![](media/service-connect-to-stripe/dashboard.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI คืออะไร](power-bi-overview.md)

[รับข้อมูลสำหรับ Power BI](service-get-data.md)


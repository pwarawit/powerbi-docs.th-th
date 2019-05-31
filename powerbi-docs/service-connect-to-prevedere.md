---
title: เชื่อมต่อกับ Prevedere ด้วย Power BI
description: Prevedere สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e15333af4e2fb8508f76517b193ca4351c2782c7
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "61149674"
---
# <a name="connect-to-prevedere-with-power-bi"></a>เชื่อมต่อกับ Prevedere ด้วย Power BI
เข้าถึงข้อมูลทางการเงินที่เฉพาะและสำคัญ เพื่อให้มั่นใจและมุ่งขับเคลื่อนธุรกิจของคุณไปข้างหน้า

เชื่อมต่อกับ[ชุดเนื้อหา Prevedere](https://app.powerbi.com/getdata/services/prevedere)สำหรับ Power BI

>[!NOTE]
>ถ้าคุณไม่ใช่ผู้ใช้ที่มีอยู่ Prevedere โปรดใช้[คีย์ตัวอย่าง](https://prevederepowerbiconnector.azurewebsites.net/static/learnmore.html)เพื่อลองใช้

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-prevedere/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-prevedere/services.png)
3. เลือก**Prevedere**แล้วเลือก**รับ**
   
   ![](media/service-connect-to-prevedere/connect.png)
4. สำหรับ**วิธีการรับรองตัวตน**เลือก**คีย์**และใส Prevedere API key ของคุณ
   
    ![](media/service-connect-to-prevedere/creds.png)
5. เลือก**ลงชื่อเข้าใช้**เพื่อเริ่มกระบวนการนำเข้า เมื่อเสร็จสิ้น แดชบอร์ดใหม่ รายงาน และแบบจำลองจะปรากฏในบานหน้าต่างนำทาง เลือกแดชบอร์ดเพื่อดูข้อมูลที่นำเข้าของคุณ
   
     ![](media/service-connect-to-prevedere/dashboard.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
ชุดเนื้อหารับข้อมูลเชิงลึกเกี่ยวกับการคาดการณ์การขายปลีก แบบจำลองการคาดการณ์ ตัวบ่งชี้นำ และอื่น ๆของคุณ

## <a name="system-requirements"></a>ความต้องการของระบบ
ชุดเนื้อหานี้จำเป็นต้องมีการเข้าถึงคีย์ Prevedere API หรือแป้นตัวอย่าง (ดูด้านล่าง)

## <a name="finding-parameters"></a>การค้นหาพารามิเตอร์
<a name="FindingParams"></a>

ลูกค้าที่มีอยู่สามารถเข้าถึงข้อมูลของพวกเขาโดยใช้คีย์ API ของพวกเขา ถ้าคุณยังไม่ได้เป็นลูกค้า คุณสามารถดูตัวอย่างของข้อมูลและการวิเคราะห์ที่ใช้ใน[คีย์ตัวอย่าง](https://prevederepowerbiconnector.azurewebsites.net/static/learnmore.html)ได้

## <a name="troubleshooting"></a>การแก้ไขปัญหา
อาจใช้เวลาสักครู่ในการโหลดข้อมูล โดยขึ้นอยู่กับขนาดตัวอย่างของคุณ

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งานใน Power BI](service-get-started.md)

[รับข้อมูลใน Power BI](service-get-data.md)


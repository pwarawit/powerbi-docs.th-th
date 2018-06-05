---
title: เชื่อมต่อกับ Prevedere ด้วย Power BI
description: Prevedere สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 581bfa4a6eca07218d10b9f86753773a0fd9bb9d
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34249493"
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

* ลอง[ถามคำถามในกล่อง Q&A](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานด้านใน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

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


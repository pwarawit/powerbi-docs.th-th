---
title: เชื่อมต่อกับ comScore Digital Analytix ด้วย Power BI
description: comScore Digital Analytix สำหรับ Power BI
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: c7e476cb9e5a210ce2d37691c44ed05dd9f3c256
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815253"
---
# <a name="connect-to-comscore-digital-analytix-with-power-bi"></a>เชื่อมต่อกับ comScore Digital Analytix ด้วย Power BI
ดูภาพและสำรวจข้อมูล comScore Digital Analytix ของคุณใน Power BI ด้วยชุดเนื้อหา Power BI ข้อมูลจะรีเฟรชโดยอัตโนมัติหนึ่งครั้งต่อวัน

เชื่อมต่อกับ[ชุดเนื้อหา comScore สำหรับ Power BI](https://app.powerbi.com/getdata/services/comscore)

>[!NOTE]
>เมื่อต้องการเชื่อมต่อกับชุดเนื้อหา คุณต้องมีบัญชีผู้ใช้ comScore DAx และสามารถเข้าถึง comScore API ได้ [รายละเอียด](#Requirements)เพิ่มเติมที่ด้านล่าง

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกรับข้อมูลที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-connect-to/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-connect-to/services.png)
3. เลือก**comScore Digital Analytix** \> **รับ**
   
   ![](media/service-connect-to-connect-to/comscore.png)
4. ระบุศูนย์ข้อมูล comScore Client ID และไซต์ที่คุณต้องการเชื่อมต่อ สำหรับรายละเอียดเพิ่มเติมเกี่ยวกับวิธีการค้นหาค่าเหล่านี้ โปรดดู[ค้นหาพารามิเตอร์ comScore ของคุณ](#FindingParams)ที่ด้านล่าง
   
   ![](media/service-connect-to-connect-to/parameters.png)
5. ใส่ชื่อผู้ใช้และรหัสผ่าน comScore ของคุณเพื่อเชื่อมต่อ ดูรายละเอียดการค้นพบนี้ที่ค่าด้านล่างนี้
   
   ![](media/service-connect-to-connect-to/creds.png)
6. กระบวนการนำเข้าจะเริ่มโดยอัตโนมัติ เมื่อเสร็จสิ้น แดชบอร์ดใหม่ รายงาน และแบบจำลองจะปรากฏในบานหน้าต่างนำทาง เลือกแดชบอร์ดเพื่อดูข้อมูลที่นำเข้าของคุณ

**ฉันต้องทำอะไรต่อ?**

* ลอง[ถามคำถามในกล่องถามตอบ](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานพื้นฐาน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

<a name="Requirements"></a>

## <a name="system-requirements"></a>ข้อกำหนดของระบบ
ในการเชื่อมต่อ จำเป็นต้องมีบัญชีผู้ใช้ของ DAx comScore และการเข้าใช้งาน comScore DAx API โปรดติดต่อผู้ดูแลระบบ DAx comScore ของคุณเพื่อยืนยันบัญชีของคุณ

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>การค้นหาพารามิเตอร์
รายละเอียดเกี่ยวกับวิธีการค้นหาแต่ละพารามิเตอร์ comScore มีอยู่ที่ด้านล่าง

**ศูนย์ข้อมูล**

ในศูนย์ข้อมูลที่คุณเชื่อมต่อจะกำหนด โดย URL ที่คุณนำทางไปใน comScore

ถ้าคุณใช้ https://dax.comscore.com ใส่ "สหรัฐอเมริกา" ถ้าคุณใช้ https://dax.comscore.eu ใส่ "EU"

![](media/service-connect-to-connect-to/comscore_url.png) 

**ไคลเอ็นต์**

ไคลเอ็นต์จะเหมือนกันกับที่คุณกรอกเมื่อลงชื่อเข้าใช้ comScore DAx

![](media/service-connect-to-connect-to/comscore_signin.png) 

**ไซต์**

ไซต์ comScore จะกำหนดว่าไซต์ใดที่คุณต้องการดูข้อมูล คุณสามารถค้นหารายการของไซต์จากบัญชี comScore ของคุณ

![](media/service-connect-to-connect-to/comscore_sites.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งานใน Power BI](service-get-started.md)

[รับข้อมูลใน Power BI](service-get-data.md)


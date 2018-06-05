---
title: เชื่อมต่อกับ ClickDimensions ด้วย Power BI
description: ClickDimensions สำหรับ Power BI
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
ms.openlocfilehash: 35b6fd4c2594a29745fe307d804b3f0147d94e43
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815793"
---
# <a name="connect-to-clickdimensions-with-power-bi"></a>เชื่อมต่อกับ ClickDimensions ด้วย Power BI
แพคข้อมูล ClickDimensions สำหรับ Power BI ช่วยให้ผู้ใช้สามารถใช้ประโยชน์จากตลาดข้อมูล ClickDimensions ใน Power BI โดยให้ข้อมูลเชิงลึกแก่ทีมบริหาร เพื่อประสบความสำเร็จในการขายและการตลาด แสดงภาพและวิเคราะห์การโต้ตอบอีเมล การเยี่ยมชมเว็บ และการส่งฟอร์มในแดชบอร์ดและรายงาน Power BI

เชื่อมต่อกับ[แพคเนื้อหา ClickDimensions](https://app.powerbi.com/getdata/services/click-dimensions) สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-clickdimensions/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-clickdimensions/services.png)
3. เลือก**ClickDimensions** \> **รับ**
   
   ![](media/service-connect-to-clickdimensions/clickdimensions.png)
4. ระบุตำแหน่งที่ตั้งของศูนย์ข้อมูลของคุณ (US EU หรือ AU) และเลือก**ถัดไป**
   
   ![](media/service-connect-to-clickdimensions/params.png)
5. สำหรับ**วิธีการรับรองตัวตน**ให้เลือก**พื้นฐาน** \> **ลงชื่อเข้าใช้** เมื่อได้ถูกถาม ให้ใส่ข้อมูลประจำตัว ClickDimensions ของคุณ ดูรายละเอียดที่ [การค้นหาพารามิเตอร์เหล่านั้น](#FindingParams) ที่ด้านล่าง
   
    ![](media/service-connect-to-clickdimensions/creds.png)
6. หลังจากอนุมัติ กระบวนการนำเข้าจะเริ่มโดยอัตโนมัติ เมื่อเสร็จสิ้น แดชบอร์ดใหม่ รายงาน และแบบจำลองจะปรากฏในบานหน้าต่างนำทาง เลือกแดชบอร์ดเพื่อดูข้อมูลที่นำเข้าของคุณ
   
     ![](media/service-connect-to-clickdimensions/dashboard.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานด้านใน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="system-requirements"></a>ความต้องการของระบบ
เพื่อเชื่อมต่อกับชุดเนื้อหา Power BI คุณต้องให้ข้อมูลกับศูนย์ข้อมูลที่สอดคล้องกับบัญชีของคุณ และเข้าสู่ระบบ ด้วยบัญชี ClickDimensions ของคุณ ถ้าคุณไม่แน่ใจว่าข้อมูลใดบ้างทีศูนย์ข้อมูลให้ โปรดตรวจสอบกับผู้ดูแลระบบของคุณ

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>การค้นหาพารามิเตอร์
Account Key ที่เจอในการตั้งค่า CRM \> การตั้งค่า ClickDimensions คัดลอก Account Key จากภายในการตั้งค่า ClickDimensions และวางลงในเขตข้อมูลชื่อ User  

![](media/service-connect-to-clickdimensions/crm.png)  

คัดลอกโทเค็น Power BI จากภายในการตั้งค่า ClickDimensions และวางลงในเขตข้อมูล Password โทเค็น Power BI ที่เจอในการตั้งค่า CRM \> การตั้งค่า ClickDimensions  

![](media/service-connect-to-clickdimensions/crm2.png)  

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งานใน Power BI](service-get-started.md)

[รับข้อมูลใน Power BI](service-get-data.md)


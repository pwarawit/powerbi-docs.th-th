---
title: เชื่อมต่อกับ Azure Search ด้วย Power BI
description: Azure Search สำหรับ Power BI
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
ms.openlocfilehash: d868c50a69381c1ef95a8b3a69590223eb066e90
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815258"
---
# <a name="connect-to-azure-search-with-power-bi"></a>เชื่อมต่อกับ Azure Search ด้วย Power BI
การวิเคราะห์การรับส่งข้อมูล Azure Search (Azure Search Traffic Analytics) ช่วยให้คุณสามารถตรวจติดตามและทำความเข้าใจเกี่ยวกับการรับส่งข้อมูลไปยังบริการค้นหา Azure ของคุณ ชุดเนื้อหา Azure Search สำหรับ Power BI ให้ข้อมูลเชิงลึกโดยละเอียดเกี่ยวกับข้อมูลการค้นหาของคุณ โดยรวมถึงการค้นหา การทำดัชนี สถิติการบริการ และเวลาแฝงในช่วงเวลส 30 วันที่ผ่านมา คุณสามารถพบรายละเอียดเพิ่มเติมใน[บล็อกโพสต์ Azure](https://azure.microsoft.com/en-us/blog/analyzing-your-azure-search-traffic/)

เชื่อมต่อไปยัง[ชุดเนื้อหา Azure Search](https://app.powerbi.com/getdata/services/azure-search)สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือก**รับข้อมูล**ที่ด้านล่างของแผงนำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-azure-search/pbi_getdata.png) 
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-azure-search/pbi_getservices.png) 
3. เลือก**Azure Search** \> **รับ**
   
   ![](media/service-connect-to-azure-search/azuresearch.png)
4. ใส่ชื่อบัญชีเก็บข้อมูลตารางที่จัดเก็บการวิเคราะห์ Azure Search ของคุณ
   
   ![](media/service-connect-to-azure-search/params.png)
5. เลือก**คีย์**เป็นกลไกการรับรองความถูกต้อง และใส่คีย์บัญชีเก็บข้อมูลของคุณ คลิก**ลงชื่อเข้าใช้**เพื่อเริ่มกระบวนการการโหลด
   
   ![](media/service-connect-to-azure-search/creds.png)
6. เมื่อการดาวน์โหลดเสร็จสิ้น แดชบอร์ดใหม่ รายงาน และแบบจำลองจะปรากฏในบานหน้าต่างนำทาง เลือกแดชบอร์ดเพื่อดูข้อมูลที่นำเข้าของคุณ
   
    ![](media/service-connect-to-azure-search/dashboard2.png)

**ฉันต้องทำอะไรต่อ?**

* ลอง[ถามคำถามในกล่องถามตอบ](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานพื้นฐาน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="system-requirements"></a>ข้อกำหนดของระบบ
ชุดเนื้อหา Azure Search ต้องมีการวิเคราะห์การรับส่งข้อมูล Azure Search ที่เปิดใช้งานในบัญชีผู้ใช้

## <a name="troubleshooting"></a>การแก้ไขปัญหา
ตรวจสอบให้แน่ใจว่าใส่ชื่อบัญชีเก็บข้อมูลได้อย่างถูกต้อง พร้อมกับคีย์การเข้าถึงแบบเต็ม ชื่อบัญชีเก็บข้อมูลควรตรงกับบัญชีผู้ใช้ที่กำหนดค่าด้วยการวิเคราะห์การรับส่งข้อมูล Azure Search

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งาน Power BI](service-get-started.md)

[Power BI - แนวคิดพื้นฐาน](service-basic-concepts.md)


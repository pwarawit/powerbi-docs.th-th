---
title: วิธีรีเฟรชข้อมูลประจำตัวของชุดเนื้อหา Xero
description: ถ้าคุณใช้ชุดเนื้อหา Xero Power BI คุณอาจพบปัญหาเกี่ยวกับการรีเฟรชชุดเนื้อหาประจำวัน เนื่องปัญหาบริการของ Power BI เมื่อไม่นานมานี้
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
ms.date: 08/10/2017
ms.author: sarinas
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 2be07994ebd136fa3cd99cd3d64967618cde7258
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
---
# <a name="how-to-refresh-your-xero-content-pack-credentials-if-refresh-failed"></a>วิธีรีเฟรชข้อมูลประจำตัวของชุดเนื้อหา Xero ถ้าการรีเฟรชล้มเหลว
ถ้าคุณใช้ชุดเนื้อหา Xero Power BI คุณอาจพบปัญหาบางอย่าง กับการรีเฟรชชุดเนื้อหาประจำวัน เนื่องจากปัญหาบริการของ Power BI เมื่อไม่นานมานี้

คุณสามารถดูว่าชุดเนื้อหาของคุณรีเฟรชสำเร็จหรือไม่ โดยการตรวจสอบสถานะการรีเฟรชล่าสุด สำหรับชุดข้อมูล Xero ของคุณ ดังแสดงในภาพหน้าจอด้านล่าง

![](media/service-refresh-xero-credentials/powerbi-xero-refresh-failed.png)

ถ้าคุณเห็นการรีเฟรชที่ล้มเหลวตามที่แสดงด้านบน โปรดทำตามขั้นตอนเหล่านี้ เพื่อต่ออายุข้อมูลประจำตัวชุดเนื้อหาของคุณ

1. คลิกที่จุดไข่ปลา (...) ที่อยู่ถัดจากชุดข้อมูล Xero ของคุณ แล้วคลิก**กำหนดตารางเวลาการรีเฟรช** ซึ่งจะเปิดหน้าการตั้งค่า สำหรับชุดเนื้อหา Xero
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-schedule-refresh.png)
2. ในหน้า**ตั้งค่าสำหรับ Xero** เลือก**ข้อมูลประจำตัวแหล่งข้อมูล** > **แก้ไขข้อมูลประจำตัว**
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-settings-page.png)
3. ใส่ชื่อองค์กรของคุณ > **ถัดไป**
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-configure.png)
4. ลงชื่อเข้าใช้ ด้วยบัญชี Xero ของคุณ
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-welcome.png)
5. ตอนนี้ข้อมูลประจำตัวของคุณได้รับการปรับปรุงแล้ว ลองตรวจสอบว่า กำหนดเวลารีเฟรช ถูกตั้งค่าให้ทำงานทุกวัน ตรวจสอบโดยคลิกที่จุดไข่ปลา (...) ที่อยู่ถัดจากชุดข้อมูล Xero ของคุณ จาก นั้นคลิก**กำหนดตารางเวลาการรีเฟรช**อีกครั้ง
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-refresh-schedule.png)
6. คุณยังสามารถเลือกรีเฟรชชุดข้อมูลทันที คลิกที่จุดไข่ปลา (...) ที่อยู่ถัดจากชุดข้อมูลของคุณ Xero แล้วคลิก**รีเฟรชทันที**
   
    ![](media/service-refresh-xero-credentials/powerbi-xero-refresh-now.png)

ถ้าคุณยังคงมีปัญหาการรีเฟรช โปรดอย่าลังเลที่จะติดต่อเราที่ [http://support.powerbi.com](http://support.powerbi.com) 

เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับชุดเนื้อหา Xero สำหรับ Power BI โปรดไป[หน้าความช่วยเหลือของชุดเนื้อหา Xero](service-connect-to-xero.md)

### <a name="next-steps"></a>ขั้นตอนถัดไป
* มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


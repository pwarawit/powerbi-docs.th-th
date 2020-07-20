---
title: วิธีรีเฟรชข้อมูลประจำตัวของชุดเนื้อหา Xero
description: ถ้าคุณใช้ชุดเนื้อหา Xero Power BI คุณอาจพบปัญหาเกี่ยวกับการรีเฟรชชุดเนื้อหาประจำวัน เนื่องปัญหาบริการของ Power BI เมื่อไม่นานมานี้
author: SarinaJoan
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 08/10/2017
ms.author: sarinas
LocalizationGroup: Troubleshooting
ms.openlocfilehash: a1697bfce1db1ca92d50bfb83210d21b2820fdae
ms.sourcegitcommit: e8ed3d120699911b0f2e508dc20bd6a9b5f00580
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/11/2020
ms.locfileid: "86263703"
---
# <a name="how-to-refresh-your-xero-content-pack-credentials-if-refresh-failed"></a>วิธีรีเฟรชข้อมูลประจำตัวของชุดเนื้อหา Xero ถ้าการรีเฟรชล้มเหลว
ถ้าคุณใช้ชุดเนื้อหา Xero Power BI คุณอาจพบปัญหาบางอย่าง กับการรีเฟรชชุดเนื้อหาประจำวัน เนื่องจากปัญหาบริการของ Power BI เมื่อไม่นานมานี้

คุณสามารถดูว่าชุดเนื้อหาของคุณรีเฟรชสำเร็จหรือไม่ โดยการตรวจสอบสถานะการรีเฟรชล่าสุด สำหรับชุดข้อมูล Xero ของคุณ ดังแสดงในภาพหน้าจอด้านล่าง

![ภาพหน้าจอของกล่องโต้ตอบ Xero ที่แสดงสถานะสำหรับชุดข้อมูล Xero ของคุณ](media/service-refresh-xero-credentials/powerbi-xero-refresh-failed.png)

ถ้าคุณเห็นการรีเฟรชที่ล้มเหลวตามที่แสดงด้านบน โปรดทำตามขั้นตอนเหล่านี้ เพื่อต่ออายุข้อมูลประจำตัวชุดเนื้อหาของคุณ

1. คลิกที่**ตัวเลือกเพิ่มเติม** (...) ซึ่งอยู่ถัดจากชุดข้อมูล Xero ของคุณ แล้วคลิก**กำหนดตารางเวลาการรีเฟรช** ซึ่งจะเปิดหน้าการตั้งค่า สำหรับชุดเนื้อหา Xero
   
    ![ภาพหน้าจอของกล่องโต้ตอบ Xero ที่แสดงการเลือกกำหนดเวลาการรีเฟรช](media/service-refresh-xero-credentials/powerbi-xero-schedule-refresh.png)
2. ในหน้า**ตั้งค่าสำหรับ Xero** เลือก**ข้อมูลประจำตัวแหล่งข้อมูล** > **แก้ไขข้อมูลประจำตัว**
   
    ![ภาพหน้าจอของกล่องโต้ตอบการตั้งค่า Xero ที่แสดงการตั้งค่าสำหรับ Xero พร้อมด้วยการแก้ไขข้อมูลประจำตัวที่เลือกไว้](media/service-refresh-xero-credentials/powerbi-xero-settings-page.png)
3. ใส่ชื่อองค์กรของคุณ > **ถัดไป**
   
    ![ภาพหน้าจอของกล่องโต้ตอบกำหนดค่า Xero ที่แสดงชื่อขององค์กร](media/service-refresh-xero-credentials/powerbi-xero-configure.png)
4. ลงชื่อเข้าใช้ ด้วยบัญชี Xero ของคุณ
   
    ![ภาพหน้าจอของกล่องโต้ตอบลงชื่อเข้าใช้ Xero ที่แสดงวิธีการลงชื่อเข้าใช้บัญชี Xero ของคุณ](media/service-refresh-xero-credentials/powerbi-xero-welcome.png)
5. ตอนนี้ข้อมูลประจำตัวของคุณได้รับการปรับปรุงแล้ว ลองตรวจสอบว่า กำหนดเวลารีเฟรช ถูกตั้งค่าให้ทำงานทุกวัน ตรวจสอบโดยคลิกที่**ตัวเลือกเพิ่มเติม** (...) ซึ่งอยู่ถัดจากชุดข้อมูล Xero ของคุณ จาก นั้นคลิก**กำหนดตารางเวลาการรีเฟรช**อีกครั้ง
   
    ![ภาพหน้าจอของกล่องโต้ตอบกำหนดเวลาการรีเฟรช ที่แสดงความถี่และโซนเวลาในการรีเฟรช](media/service-refresh-xero-credentials/powerbi-xero-refresh-schedule.png)
6. คุณยังสามารถเลือกรีเฟรชชุดข้อมูลทันที คลิกที่**ตัวเลือกเพิ่มเติม** (...) ซึ่งอยู่ถัดจากชุดข้อมูล Xero ของคุณ แล้วคลิก **รีเฟรชทันที**
   
    ![ภาพหน้าจอของกล่องโต้ตอบ Xero ที่แสดงการเลือกรีเฟรชตอนนี้](media/service-refresh-xero-credentials/powerbi-xero-refresh-now.png)

ถ้าคุณยังคงมีปัญหาการรีเฟรช โปรดอย่าลังเลที่จะติดต่อเราที่ [https://support.powerbi.com](https://support.powerbi.com) 

เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับชุดเนื้อหา Xero สำหรับ Power BI โปรดไป[หน้าความช่วยเหลือของชุดเนื้อหา Xero](service-connect-to-xero.md)

### <a name="next-steps"></a>ขั้นตอนถัดไป
* มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)


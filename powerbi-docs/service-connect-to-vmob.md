---
title: เชื่อมต่อกับ VMob ด้วย Power BI
description: VMob สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 01c7866a47d20b51055aa77bdd4792e2277c335f
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/21/2018
ms.locfileid: "46549760"
---
# <a name="connect-to-vmob-with-power-bi"></a>เชื่อมต่อกับ VMob ด้วย Power BI
การติดตามและการสำรวจข้อมูล VMob ของคุณด้วย Power BI และชุดเนื้อหา VMob ทำได้ง่ายยิ่งขึ้น Power BI จะเรียกใช้ข้อมูลต่อไปนี้: สถิติผู้ใช้ในทุกเวลาและใน 30 วันที่ผ่านมา KPI ร้านค้าปลีกใน 30 วันที่ผ่านมา และประสิทธิภาพของแคมเปญในเวลา 30 วันที่ผ่านมา

เชื่อมต่อไปยัง[ชุดเนื้อหา VMob](https://app.powerbi.com/getdata/services/vmob) สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
    ![](media/service-connect-to-vmob/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-vmob/services.png)
3. เลือก**VMob** \> **รับ**
   
   ![](media/service-connect-to-vmob/vmob.png)
4. เมื่อมีข้อความปรากฏ ให้ใส่ URL ของ VMob และคลิกที่ปุ่มถัดไป URL นี้จัดเตรียมโดย VMob ที่แยกต่างหาก
   
    ![](media/service-connect-to-vmob/params.png)
5. เลือกตัวเลือก**พื้นฐาน (Basic)** ในรายการวิธีการรับรองความถูกต้องแบบเลื่อนลง ใส่ชื่อผู้ใช้และรหัสผ่าน VMob ของคุณ จากนั้นคลิกที่ปุ่ม**ลงชื่อเข้าใช้**
   
    ![](media/service-connect-to-vmob/creds.png)
6. กระบวนการนำเข้าจะเริ่มต้นโดยอัตโนมัติ และ Power BI จะดึงข้อมูล VMob ของคุณเพื่อสร้างรายงานและแดชบอร์ดแบบพร้อมใช้งานให้คุณ
   
   ![](media/service-connect-to-vmob/dashboard2.png)

**ฉันต้องทำอะไรต่อ?**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งานใน Power BI](service-get-started.md)

[รับข้อมูลใน Power BI](service-get-data.md)


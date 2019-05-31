---
title: เชื่อมต่อกับ Project Online ด้วย Power BI
description: Project Online สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: dd6698cab5b9fed407e6e8f45ceb160209a38fae
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "61146862"
---
# <a name="connect-to-project-online-with-power-bi"></a>เชื่อมต่อกับ Project Online ด้วย Power BI
Microsoft Project Online เป็นโซลูชันออนไลน์ที่ยืดหยุ่นสำหรับการจัดการพอร์ตโครงการ (Project Portfolio Management: PPM) และงานประจำวัน Project Online ช่วยให้องค์กรสามารถเริ่มต้นและจัดลำดับความสำคัญการลงทุนในพอร์ตโครงการ และส่งมอบมูลค่าทางธุรกิจตามที่ต้องการได้ ชุดเนื้อหา Project Online สำหรับ Power BI ช่วยให้คุณสามารถเข้าถึงข้อมูลเชิงลึกที่ให้บริการเพื่อจัดการโครงการ พอร์ตโครงการ และทรัพยากร

เชื่อมต่อไปยัง[ชุดเนื้อหา Project Online](https://app.powerbi.com/getdata/services/project-online)สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
    ![](media/service-connect-to-project-online/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-project-online/services.png)
3. เลือก**Microsoft Project Online** \> **รับ**
   
   ![](media/service-connect-to-project-online/mproject.png)
4. ในกล่องข้อความ**Project Web App URL** ใส่ URL สำหรับ Project Web Add (PWA) ที่คุณต้องการเชื่อมต่อ จากนั้นคลิก**ถัดไป** หมายเหตุ ส่วนนี้อาจแตกต่างจากตัวอย่างดังกล่าวถ้าคุณมีโดเมนแบบกำหนดเอง ในกล่องข้อความ**PWA ไซต์ภาษา**พิมพ์หมายเลขที่แสดงภาษาของไซต์ PWA ของคุณ พิมพ์ตัวเลขหลักเดียว '1' สำหรับภาษาอังกฤษ '2' สำหรับภาษาฝรั่งเศส '3' สำหรับภาษาเยอรมัน '4' สำหรับภาษาโปรตุเกส (บราซิล), ' 5' สำหรับภาษาโปรตุเกส (โปรตุเกส) และ ' 6' สำหรับภาษาสเปน 
   
    ![](media/service-connect-to-project-online/params.png)
5. สำหรับวิธีการรับรองความถูกต้อง ให้เลือก **oAuth2** \> **ลงชื่อเข้าใช้** เมื่อได้รับข้อความปรากฏขึ้น ให้ใส่ข้อมูลประจำตัวของ Project Online และทำตามกระบวนการรับรองความถูกต้อง
   
    ![](media/service-connect-to-project-online/creds.png)
    
โปรดทราบว่าคุณจำเป็นต้องมีสิทธิ์การใช้งานสำหรับ Portfolio Viewer (ผู้ดูพอร์ต) Portfolio Manager (ผู้จัดการพอร์ต) หรือ Administrator (ผู้ดูแลระบบ) สำหรับ Project Web App ที่คุณกำลังเชื่อมต่อ

6. คุณจะเห็นการแจ้งเตือนที่ระบุว่า กำลังโหลดข้อมูลของคุณ ขึ้นอยู่กับขนาดบัญชีของคุณ ซึ่งอาจใช้เวลาสักครู่ หลังจากที่ Power BI นำเข้าข้อมูลแล้ว คุณจะเห็นแดชบอร์ดใหม่ รายงาน 13 ฉบับ และชุดข้อมูล ในบานหน้าต่างนำทางด้านซ้ายมือ นี่คือแดชบอร์ดตามเริ่มต้นที่ Power BI สร้างขึ้นเพื่อแสดงข้อมูลของคุณ คุณสามารถปรับเปลี่ยนแดชบอร์ดนี้เพื่อแสดงข้อมูลของคุณด้วยวิธีใดก็ตามที่คุณต้องการ

   ![](media/service-connect-to-project-online/dashboard2.png)

7. หลังจากแดชบอร์ดและรายงานของคุณพร้อม ดำเนินการต่อและเริ่มการสำรวจข้อมูล Project Online ของคุณ ชุดเนื้อหามาพร้อมกับรายงาน 13 ฉบับ ที่เป็นภาพรวมการจัดการพอร์ตโครงการ (6 หน้ารายงาน), ภาพรวมทรัพยากร (5 หน้ารายงาน) และ สถานะของโครงการ (2 หน้ารายงาน) 

   ![](media/service-connect-to-project-online/report1.png)
   
   ![](media/service-connect-to-project-online/report3.png)
   
   ![](media/service-connect-to-project-online/report2.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

**ขยายชุดเนื้อหา**

ดาวน์โหลด[GitHub PBIT ไฟล์](https://github.com/OfficeDev/Project-Power-BI-Content-Packs)เมื่อต้องการกำหนดค่า และปรับปรุงชุดเนื้อหา

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งานใน Power BI](service-get-started.md)

[รับข้อมูลใน Power BI](service-get-data.md)


---
title: เชื่อมต่อกับ Projectplace ด้วย Power BI
description: Projectplace สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 70dcc7beb4525c84f1d52c511fa6a9f2ba666f94
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34249194"
---
# <a name="connect-to-projectplace-by-planview-with-power-bi"></a>เชื่อมต่อกับ Projectplace โดย Planview ด้วย Power BI
ด้วยชุดเนื้อหา Projectplace โดย Planview คุณสามารถมองเห็นภาพข้อมูลโครงการที่ทำงานร่วมกันในวิธีการใหม่ทั้งกระบวนการได้โดยตรงใน Power BI ใช้ข้อมูลประจำตัวการลงชื่อเข้าใช้ Projectplace ของคุณเพื่อดูสถิติโครงการที่สำคัญแบบโต้ตอบ ค้นหาผู้ใช้ที่ใช้งานมากที่สุดและสมาชิกในทีมที่ทำงานมีประสิทธิภาพมากที่สุด และระบุการ์ดและกิจกรรมที่มีความเสี่ยงในทั้งโครงการในบัญชี Projectplace ของคุณ นอกจากนี้ คุณยังสามารถขยายแดชบอร์ดและรายงานแบบใช้งานทันทีเพื่อรับข้อมูลเชิงลึกที่มีความสำคัญมากที่สุดสำหรับคุณ

[เชื่อมต่อกับชุดเนื้อหา Projectplace ใน Power BI](https://app.powerbi.com/getdata/services/projectplace)

>[!NOTE]
>เมื่อต้องการนำเข้าข้อมูล Projectplace ของคุณไปยัง Power BI คุณต้องเป็นผู้ใช้ Projectplace ดูข้อกำหนดเพิ่มเติมที่ด้านล่าง

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือก**รับข้อมูล**ที่ด้านล่างของแผงนำทางด้านซ้ายมือ
   
    ![](media/service-connect-to-projectplace/get.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
    ![](media/service-connect-to-projectplace/services.png)
3. ในหน้า Power BI เลือก**Projectplace โดย Planview** แล้วเลือก**รับ**:  
   
    ![](media/service-connect-to-projectplace/projectplace.png)
4. ในกล่องข้อความ URL ของตัวดึงข้อมูล OData ใส่ URL สำหรับตัวดึงข้อมูล Projectplace OData ที่คุณต้องการใช้ ดังที่แสดงในรูปต่อไปนี้:
   
    ![](media/service-connect-to-projectplace/params.png)
5. ในรายการวิธีการรับรองความถูกต้อง เลือก**OAuth**ถ้ายังไม่ได้เลือกไว้ คลิก**ลงชื่อเข้าใช้**และทำตามขั้นตอนการเข้าสู่ระบบ  
   
   ![](media/service-connect-to-projectplace/creds.png)
6. ในแผงด้านซ้าย เลือก**Projectplace**จากรายการแดชบอร์ด Power BI นำเข้าข้อมูล Projectplace ลงในแดชบอร์ด โปรดทราบว่าอาจใช้เวลาสักครู่ในการโหลดข้อมูล  
   
    แดชบอร์ดที่ประกอบด้วยไทล์ที่แสดงข้อมูลจากฐานข้อมูล Projectplace ของคุณ รูปต่อไปนี้แสดงตัวอย่างของแดชบอร์ด Projectplace ค่าเริ่มต้นใน Power BI
   
    ![](media/service-connect-to-projectplace/dashboard.png)

**ฉันต้องทำอะไรต่อ?**

* ลอง[ถามคำถามในกล่องถามตอบ](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานพื้นฐาน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="system-requirements"></a>ข้อกำหนดของระบบ
เมื่อต้องการนำเข้าข้อมูล Projectplace ของคุณไปยัง Power BI คุณต้องเป็นผู้ใช้ Projectplace ขั้นตอนนี้ถือว่าคุณลงชื่อเข้าใช้โฮมเพจ Microsoft Power BI ด้วยบัญชี Power BI แล้ว ถ้าคุณไม่มีบัญชี Power BI สร้างบัญชี Power BI ฟรีบนโฮมเพจ Power BI จากนั้นคลิกรับข้อมูล

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งาน Power BI](service-get-started.md)

[Power BI - แนวคิดพื้นฐาน](service-basic-concepts.md)


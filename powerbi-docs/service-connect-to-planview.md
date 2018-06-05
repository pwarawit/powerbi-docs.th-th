---
title: เชื่อมต่อกับ Planview Enterprise ด้วย Power BI
description: Planview Enterprise สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 4641fc0c36ad7fb64cc5da08ee8eda180f4ccc31
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34240500"
---
# <a name="connect-to-planview-enterprise-with-power-bi"></a>เชื่อมต่อกับ Planview Enterprise ด้วย Power BI
ด้วยชุดเนื้อหา Planview Enterprise คุณสามารถมองเห็นภาพทรัพยากรของคุณ และทำงานเพื่อจัดการข้อมูลในวิธีการใหม่ทั้งกระบวนการได้โดยตรงใน Power BI ใช้ข้อมูลประจำตัวการลงชื่อเข้าใช้ของ Planview Enterprise เพื่อดูการใช้จ่ายพอร์ตลงทุนแบบโต้ตอบของคุณ ทำความเข้าใจว่าคุณอยู่ตรงจุดไหน เกินงบประมาณหรือต่ำกว่างบประมาณ และดูว่าโครงการของคุณสอดคล้องกับลำดับความสำคัญเชิงกลยุทธ์ขององค์กรของคุณมากน้อยเพียงใด นอกจากนี้ คุณยังสามารถขยายแดชบอร์ดและรายงานแบบใช้งานทันทีเพื่อรับข้อมูลเชิงลึกที่มีความสำคัญมากที่สุดสำหรับคุณ

เชื่อมต่อกับ[ชุดเนื้อหา Planview Enterprise ใน Power BI](https://app.powerbi.com/getdata/services/planview-enterprise)

>[!NOTE]
>ในการนำเข้าข้อมูล Planview Enterprise ของคุณไปยัง Power BI คุณต้องเป็นผู้ใช้ Planview Enterprise ที่มีการเปิดใช้งานคุณลักษณะ Reporting Portal Viewer ในบทบาทของคุณ ดูข้อกำหนดเพิ่มเติมที่ด้านล่าง

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือก**รับข้อมูล**ที่ด้านล่างของแผงนำทางด้านซ้ายมือ
   
    ![](media/service-connect-to-planview/get.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
    ![](media/service-connect-to-planview/services.png)
3. บนหน้า Power BI เลือก**Planview Enterprise** แล้วเลือก**รับ**:  
    ![](media/service-connect-to-planview/planview.png)
4. ในกล่องข้อความ Planview Enterprise URL ใส่ URL สำหรับเซิร์ฟเวอร์ Planview Enterprise ที่คุณต้องการใช้ ในกล่องข้อความฐานข้อมูล Planview Enterprise ใส่ชื่อของฐานข้อมูล Planview Enterprise จากนั้นคลิกถัดไป  
    ![](media/service-connect-to-planview/params.png)
5. ในรายการวิธีการรับรองความถูกต้อง เลือก**พื้นฐาน**ถ้ายังไม่ได้เลือกไว้ ใส่**ชื่อผู้ใช้**และ**รหัสผ่าน**สำหรับบัญชีของคุณ แล้วเลือก**ลงชื่อเข้าใช้**  
   ![](media/service-connect-to-planview/creds.png)
6. ในแผงด้านซ้าย เลือก Planview Enterprise จากรายการของแดชบอร์ด  
     Power BI นำเข้าข้อมูล Planview Enterprise ลงในแดชบอร์ด โปรดทราบว่าอาจใช้เวลาสักครู่ในการโหลดข้อมูล  
    ![](media/service-connect-to-planview/dashboard.png)

**ฉันต้องทำอะไรต่อ?**

* ลอง[ถามคำถามในกล่องถามตอบ](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานพื้นฐาน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="system-requirements"></a>ข้อกำหนดของระบบ
ในการนำเข้าข้อมูล Planview Enterprise ของคุณไปยัง Power BI คุณต้องเป็นผู้ใช้ Planview Enterprise ที่มีการเปิดใช้งานคุณลักษณะ Reporting Portal Viewer ในบทบาทของคุณ ดูข้อกำหนดเพิ่มเติมที่ด้านล่าง

ขั้นตอนนี้ถือว่าคุณลงชื่อเข้าใช้โฮมเพจ Microsoft Power BI ด้วยบัญชี Power BI แล้ว ถ้าคุณไม่มีบัญชี Power BI สร้างบัญชี Power BI ฟรีบนโฮมเพจ Power BI จากนั้นคลิกรับข้อมูล

## <a name="next-steps"></a>ขั้นตอนถัดไป:

[เริ่มต้นใช้งาน Power BI](service-get-started.md)

[รับข้อมูลสำหรับ Power BI](service-get-data.md)
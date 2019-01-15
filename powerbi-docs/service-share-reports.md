---
title: แชร์รายงาน Power BI ที่ถูกกรองร่วมกับเพื่อนร่วมงาน
description: เรียนรู้วิธีการกรองรายงาน Power BI และแชร์รายงานกับเพื่อนร่วมงานในองค์กรของคุณ
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/21/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 05bdb9ccca7715b74cb18462f215f7d1bf640526
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54279780"
---
# <a name="share-a-filtered-power-bi-report-with-your-coworkers"></a>แชร์รายงาน Power BI ที่ถูกกรองร่วมกับเพื่อนร่วมงานของคุณ
*แชร์*เป็นวิธีที่ดีเมื่อต้องให้บางคนสามารถเข้าถึงแดชบอร์ดและรายงานของคุณ Power BI ยังนำเสนอ[หลายวิธีอื่นๆ เพื่อที่จะทำงานร่วมกันและเผยแพร่แดชบอร์ดและรายงาน](service-how-to-collaborate-distribute-dashboards-reports.md)

ด้วยการแชร์ คุณและผู้รับของคุณต้องมี[สิทธิ์การใช้งาน Power BI Pro](service-features-license-type.md)หรือเนื้อหาจำเป็นต้องเป็นแบบ[ความจุพรีเมียม](service-premium.md) 

คุณสามารถแชร์รายงานกับผู้ร่วมงานในโดเมนอีเมลเดียวกับคุณ จากสถานที่ส่วนใหญ่ใน Power BI service เช่น รายการโปรด ล่าสุด แชร์กับฉัน (ถ้าเจ้าของอนุญาต) My Workspace หรือพื้นที่ทำงานอื่นๆของคุณได้ เมื่อคุณแชร์รายงานซึ่งเพื่อนร่วมงานที่คุณแชร์ให้จะสามารถดูและโต้ตอบกับมันได้ แต่ไม่สามารถแก้ไขรายงานได้ พวกเขาจะเห็นข้อมูลเดียวกันกับที่คุณเห็นในแดชบอร์ดหรือรายงาน เว้นแต่ว่า[ระดับแถวความปลอดภัย (RLS)](service-admin-rls.md)จะถูกใช้ 

จะเกิดอะไรขึ้นถ้าคุณต้องการแชร์รายงานที่ถูกกรอง อาจรายงานที่แสดงเฉพาะข้อมูลสำหรับเมือง หรือพนักงานขาย หรือปีที่เฉพาะเจาะจง ลองสร้าง URL แบบกำหนดเอง รายงานจะถูกกรองเมื่อผู้รับเปิดเป็นครั้งแรก ผู้รับสามารถลบตัวกรองโดยการปรับเปลี่ยน URL

## <a name="filter-and-share-a-report"></a>กรองข้อมูลและแชร์รายงาน

1. เปิดรายงานใน[มุมมองการแก้ไข](consumer/end-user-reading-view.md) ให้ใช้ตัวกรอง และบันทึกรายงาน
   
   ในตัวอย่างนี้ เรากำลังกรอง[ตัวอย่างการวิเคราะห์ร้านค้าปลีก](sample-tutorial-connect-to-the-samples.md)เพื่อแสดงเฉพาะค่าที่**Territory**เท่ากับ**NC**
   
   ![บานหน้าต่างตัวกรองรายงาน](media/service-share-reports/power-bi-filter-report2.png)
2. เพิ่มต่อไปนี้ลงในส่วนท้ายของ URL ของหน้ารายงาน
   
   ?filter=*tablename*/*fieldname* eq *value*
   
    เขตข้อมูลต้องเป็นชนิด**สตริง** ค่าใน *tablename* หรือ *fieldname* ไม่สามารถประกอบด้วยช่องว่างได้
   
   ในตัวอย่างของเรา ชื่อของตารางคือ**Store**ชื่อของเขตข้อมูลคือ**Territory**และค่าเราต้องการกรองคืิิอ**NC**:
   
    ?filter=Store/Territory eq 'NC'
   
   ![URL รายงานที่กรองแล้ว](media/service-share-reports/power-bi-filter-url3.png)
   
   เบราว์เซอร์ของคุณเพิ่มอักขระพิเศษเพื่อแสดงเครื่องหมายทับ ช่องว่าง และเครื่องหมายบุพบท ดังนั้นคุณมี
   
   app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-xxxxxxxxxxxx/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

3. [แชร์รายงาน](service-share-dashboards.md)แต่ล้างกล่องกาเครื่องหมาย**ส่งอีเมลแจ้งเตือนไปยังผู้รับ** 

    ![กล่องโต้ตอบรายงานใช้ร่วมกัน](media/service-share-reports/power-bi-share-report-dialog.png)

4. ส่งลิงค์กับตัวกรองที่คุณสร้างไว้ก่อนหน้านี้

## <a name="next-steps"></a>ขั้นตอนถัดไป
* มีคำติชมหรือไม่? ไปที่[ไซต์ชุมชน Power BI](https://community.powerbi.com/)พร้อมกับคำแนะนำของคุณ
* [ฉันควรทำงานร่วมกัน และแชร์แดชบอร์ดและรายงานได้อย่างไร](service-how-to-collaborate-distribute-dashboards-reports.md)
* [แชร์แดชบอร์ด](service-share-dashboards.md)
* มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


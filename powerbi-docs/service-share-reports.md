---
title: กรองรายงาน และแชร์กับเพื่อนร่วมงาน - Power BI
description: เรียนรู้วิธีการกรองรายงาน Power BI และแชร์รายงานกับเพื่อนร่วมงานในองค์กรของคุณ
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/24/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 5f3808884e63521ec1dd775d876f1cf707bbe56b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770679"
---
# <a name="filter-a-power-bi-report-and-share-it-with-coworkers"></a>กรองรายงาน Power BI และแชร์กับเพื่อนร่วมงาน
*แชร์*เป็นวิธีที่ดีเมื่อต้องให้บางคนสามารถเข้าถึงแดชบอร์ดและรายงานของคุณ จะเกิดอะไรขึ้นถ้าคุณต้องการแชร์รายงานที่ถูกกรอง อาจรายงานที่แสดงเฉพาะข้อมูลสำหรับเมือง หรือพนักงานขาย หรือปีที่เฉพาะเจาะจง ลองกรองรายงาน และแชร์ หรือการสร้าง URL แบบกำหนดเอง รายงานจะถูกกรองเมื่อผู้รับเปิดเป็นครั้งแรก ผู้รับสามารถลบตัวกรองโดยการปรับเปลี่ยน URL 

Power BI ยังนำเสนอ[หลายวิธีอื่นๆ เพื่อที่จะทำงานร่วมกันและเผยแพร่แดชบอร์ดและรายงาน](service-how-to-collaborate-distribute-dashboards-reports.md) ด้วยการแชร์ คุณและผู้รับของคุณต้องมี[สิทธิ์การใช้งาน Power BI Pro](service-features-license-type.md)หรือเนื้อหาจำเป็นต้องเป็นแบบ[ความจุพรีเมียม](service-premium-what-is.md) 

## <a name="two-ways-to-filter-a-report"></a>สองวิธีในการกรองรายงาน

### <a name="set-a-filter"></a>ตั้งค่าตัวกรอง

เปิดรายงานใน[มุมมองการแก้ไข](consumer/end-user-reading-view.md) ให้ใช้ตัวกรอง และบันทึกรายงาน
   
ในตัวอย่างนี้ เรากำลังกรอง[ตัวอย่างการวิเคราะห์ร้านค้าปลีก](sample-tutorial-connect-to-the-samples.md)เพื่อแสดงเฉพาะค่าที่**Territory**เท่ากับ**NC**
   
![บานหน้าต่างตัวกรองรายงาน](media/service-share-reports/power-bi-filter-report2.png)

### <a name="create-a-filter-in-the-url"></a>สร้างตัวกรองใน URL

เพิ่มต่อไปนี้ลงในส่วนท้ายของ URL ของหน้ารายงาน
   
?filter=*tablename*/*fieldname* eq *value*
   
เขตข้อมูลต้องเป็นของชนิด number, datetime หรือ string ค่าใน *tablename* หรือ *fieldname* ไม่สามารถประกอบด้วยช่องว่างได้
   
ในตัวอย่างของเรา ชื่อของตารางคือ**Store**ชื่อของเขตข้อมูลคือ**Territory**และค่าเราต้องการกรองคืิิอ**NC**:
   
?filter=Store/Territory eq 'NC'
   
![URL รายงานที่กรองแล้ว](media/service-share-reports/power-bi-filter-url3.png)
   
เบราว์เซอร์ของคุณเพิ่มอักขระพิเศษเพื่อแสดงเครื่องหมายทับ ช่องว่าง และเครื่องหมายบุพบท ดังนั้นคุณมี
   
app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-xxxxxxxxxxxx/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

ดูบทความ[กรองรายงานโดยใช้พารามิเตอร์สตริงของแบบสอบถามใน URL](service-url-filters.md)สำหรับรายละเอียดมากขึ้น

## <a name="share-the-filtered-report"></a>แชร์รายงานที่กรองแล้ว

1. เมื่อคุณ[แชร์รายงาน](service-share-dashboards.md)ล้างการ**ส่งอีเมลแจ้งเตือนไปยังผู้รับ**กล่องกาเครื่องหมาย

    ![กล่องโต้ตอบรายงานใช้ร่วมกัน](media/service-share-reports/power-bi-share-report-dialog.png)

4. ส่งลิงค์กับตัวกรองที่คุณสร้างไว้ก่อนหน้านี้

## <a name="next-steps"></a>ขั้นตอนถัดไป
* มีคำติชมหรือไม่? ไปที่[ไซต์ชุมชน Power BI](https://community.powerbi.com/)พร้อมกับคำแนะนำของคุณ
* [ฉันควรทำงานร่วมกัน และแชร์แดชบอร์ดและรายงานได้อย่างไร](service-how-to-collaborate-distribute-dashboards-reports.md)
* [แชร์แดชบอร์ด](service-share-dashboards.md)
* มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


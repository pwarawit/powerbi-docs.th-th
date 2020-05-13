---
title: กรองและแชร์รายงาน Power BI
description: เรียนรู้วิธีการกรองรายงาน Power BI และแชร์รายงานกับเพื่อนร่วมงานในองค์กรของคุณ
author: maggiesMSFT
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/29/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 636aaf59a3a949b5b3571012d12cecc234e9763b
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83347964"
---
# <a name="filter-and-share-a-power-bi-report"></a>กรองและแชร์รายงาน Power BI
*แชร์*เป็นวิธีที่ดีเมื่อต้องให้บางคนสามารถเข้าถึงแดชบอร์ดและรายงานของคุณ จะเกิดอะไรขึ้นถ้าคุณต้องการแชร์รายงานที่ถูกกรอง คุณอาจต้องการให้รายงานแสดงเฉพาะข้อมูลสำหรับเมือง หรือพนักงานขาย หรือปีที่เฉพาะเจาะจง บทความนี้อธิบายวิธีการกรองรายงานและการแชร์เวอร์ชันที่กรองแล้วของรายงาน อีกวิธีหนึ่งในการแชร์รายงานที่กรองแล้วคือการ [เพิ่มพารามิเตอร์คิวรีไปยัง URL ของรายงาน](service-url-filters.md) ในทั้งสองกรณี รายงานจะถูกกรองเมื่อผู้รับเปิดเป็นครั้งแรก พวกเขาสามารถล้างตัวเลือกตัวกรองในรายงานได้

![กรองรายงานแล้ว](media/service-share-reports/power-bi-share-filter-pane-report.png)

Power BI ยังนำเสนอ[วิธีอื่นๆ เพื่อที่จะทำงานร่วมกันและเผยแพร่แดชบอร์ดและรายงาน](service-how-to-collaborate-distribute-dashboards-reports.md) ด้วยการแชร์ คุณและผู้รับของคุณต้องมี[สิทธิ์การใช้งาน Power BI Pro](../fundamentals/service-features-license-type.md)หรือเนื้อหาจำเป็นต้องเป็นแบบ[ความจุพรีเมียม](../admin/service-premium-what-is.md) 

## <a name="follow-along-with-sample-data"></a>ติดตามพร้อมด้วยข้อมูลตัวอย่าง

บทความนี้ใช้แอปแม่แบบตัวอย่างการตลาดและการขาย ต้องการลองใช้หรือไม่ 

1. ติดตั้ง [แอปแม่แบบตัวอย่างการตลาดและการขาย](https://appsource.microsoft.com/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample?tab=Overview)
2. เลือกแอปและเลือก **สำรวจแอป**

   ![สำรวจข้อมูลตัวอย่าง](media/service-share-reports/power-bi-sample-explore-data.png)

3. เลือกไอคอนรูปดินสอเพื่อเปิดพื้นที่ทำงานที่คุณติดตั้งด้วยแอป

    ![ดินสอแก้ไขแอป](media/service-share-reports/power-bi-edit-pencil-app.png)

4. ในรายการเนื้อหาพื้นที่ทำงาน ให้เลือก **รายงาน** จากนั้นเลือกรายงาน **ตัวอย่าง PBIX การขายและการตลาด**

    ![เปิดรายงานตัวอย่าง](media/service-share-reports/power-bi-open-sample-report.png)

    ในตอนนี้คุณก็พร้อมที่จะติดตามไปด้วยแล้ว

## <a name="set-a-filter-in-the-report"></a>ตั้งค่าตัวกรองในรายงาน

เปิดรายงานใน[มุมมองการแก้ไข](../consumer/end-user-reading-view.md)และใช้ตัวกรอง

ในตัวอย่างนี้ เรากำลังกรองหน้าประเภท YTD ของแอปแม่แบบตัวอย่างการตลาดและการขายเพื่อแสดงเฉพาะค่าที่**ภูมิภาค**นั้นคือ**ภาคกลาง** 
 
![บานหน้าต่างตัวกรองรายงาน](media/service-share-reports/power-bi-share-report-filter.png)

บันทึกรายงาน

## <a name="share-the-filtered-report"></a>แชร์รายงานี่กรองแล้ว

1. เลือก **แชร์**

   ![เลือก แชร์](media/service-share-reports/power-bi-share.png)

2. ล้าง **ส่งการแจ้งเตือนทางอีเมลไปยังผู้รับ** เพื่อที่คุณจะสามารถส่งการเชื่อมโยงที่ถูกกรองแล้วไปแทน เลือก **แชร์รายงานด้วยตัวกรองและตัวแบ่งส่วนข้อมูลปัจจุบัน**จากนั้นเลือก **แชร์**

    ![แชร์รายงานด้วยตัวกรอง](media/service-share-reports/power-bi-share-with-filters.png)

4. เลือก **แชร์** อีกครั้ง

   ![เลือก แชร์](media/service-share-reports/power-bi-share.png)

5. เลือกแท็บ **การเข้าถึง** จากนั้นเลือก **จัดการมุมมองรายงานที่แชร์**

    ![จัดการมุมมองรายงานที่แชร์](media/service-share-reports/power-bi-manage-shared-report-views.png)

6. คลิกขวาที่ URL ที่คุณต้องการ แล้วเลือก **คัดลอกลิงก์**

    ![คัดลอกลิงก์ที่กรองแล้ว](media/service-share-reports/power-bi-copy-filtered-link.png)

7. เมื่อคุณแชร์ลิงก์นี้ ผู้รับจะเห็นรายงานที่กรองแล้วของคุณ 


## <a name="next-steps"></a>ขั้นตอนถัดไป
* [วิธีการแชร์งานของคุณใน Power BI](service-how-to-collaborate-distribute-dashboards-reports.md)
* [แชร์แดชบอร์ด](service-share-dashboards.md)
* มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)
* มีคำติชมหรือไม่ ไปที่[ไซต์ชุมชน Power BI](https://community.powerbi.com/) พร้อมกับคำแนะนำของคุณ

---
title: เชื่อมต่อกับบริการที่คุณใช้กับ Power BI
description: เชื่อมต่อกับบริการคุณใช้เพื่อเรียกใช้ธุรกิจของคุณ เช่น Salesforce, Microsoft Dynamics CRM และ Google Analytics จำนวนมาก
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.date: 04/19/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 53abb5f82b75773817c72b53dd3e522cb4ccc63e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578748"
---
# <a name="connect-to-the-services-you-use-with-power-bi"></a>เชื่อมต่อกับบริการที่คุณใช้กับ Power BI
ด้วย Power BI คุณสามารถเชื่อมต่อกับบริการคุณใช้เพื่อเรียกใช้ธุรกิจของคุณ เช่น Salesforce, Microsoft Dynamics และ Google Analytics จำนวนมาก Power BI เริ่มต้น โดยใช้ข้อมูลประจำตัวของคุณเพื่อเชื่อมต่อกับบริการ สร้าง Power BI *พื้นที่ทำงาน*กับแดชบอร์ดและชุดของรายงาน Power BI ที่แสดงข้อมูลของคุณ และแสดงภาพข้อมูลเชิงลึกเกี่ยวกับธุรกิจของคุณโดยอัตโนมัติ

ลงชื่อเข้าใช้ Power BI เพื่อดูทั้งหมด[คุณสามารถเชื่อมต่อกับบริการ](https://app.powerbi.com/getdata/services) 

![แอป AppSource](media/service-connect-to-services/overview.png)

หลังจากที่คุณติดตั้งแอป คุณสามารถดูแดชบอร์ดและรายงานในแอปและพื้นที่ทำงานในบริการ Power BI ([https://app.powerbi.com](https://app.powerbi.com)) ได้ คุณยังสามารถดูได้ในแอปสำหรับอุปกรณ์เคลื่อน Power BI ในพื้นที่ทำงาน คุณสามารถปรับเปลี่ยนแดชบอร์ดและรายงานตามความต้องการขององค์กรของคุณ และกระจายให้เพื่อนร่วมงานของคุณเป็นแอ*แอ*ได้ 

![แอป Google analytics ในแอปมือถือ Power BI](media/service-connect-to-services/power-bi-service-mobile-app-240.png)

## <a name="get-started"></a>เริ่มใช้งาน
[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

## <a name="edit-the-dashboard-and-reports"></a>แก้ไขแดชบอร์ดและรายงาน
เมื่อการนำเข้าเสร็จสมบูรณ์ แอปใหม่จะปรากฏบนหน้าแอป

1. เลือก**Apps**ในบานหน้าต่างนำทางด้านซ้าย > เลือกแอป
   
     ![หน้าแอป](media/service-connect-to-services/power-bi-service-apps-open-app.png)
2. คุณสามารถถามคำถามโดยการพิมพ์ในกล่อง Q&A หรือคลิกที่ไทล์เพื่อเปิดรายงานด้านใน 
   
    ![แดชบอร์ Google Analytics](media/service-connect-to-services/googleanalytics2.png)
   
    เปลี่ยนแดชบอร์ดและรายงานให้พอดีกับความต้องการขององค์กรของคุณ แล้ว[แจกจ่ายแอปของคุณให้เพื่อนร่วมงานของคุณ](service-create-distribute-apps.md)

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
หลังจากเชื่อมต่อกับบริการ คุณเห็นแอปที่สร้างขึ้นใหม่และพื้นที่ทำงานกับแดชบอร์ด รายงาน และชุดข้อมูล ข้อมูลจากบริการจะเน้นไปที่สถานการณ์เฉพาะ และอาจรวมถึงข้อมูลทั้งหมดจากบริการ ข้อมูลมีการจัดกำหนดการการรีเฟรชโดยอัตโนมัตหนึ่งครั้งต่อวัน คุณสามารถควบคุมการกำหนดเวลาโดยการเลือกชุดข้อมูล

คุณยังสามารถ[เชื่อมต่อกับบริการมากมายใน Power BI Desktop](desktop-data-sources.md)เช่น Google Analytics และสร้างรายงานและแดชบอร์ดแบบกำหนดเองของคุณเองได้  

สำหรับรายละเอียดเพิ่มเติมเกี่ยวกับการเชื่อมต่อกับบริการแบบเจาะจง ดูวิธีใช้แต่ละหน้า

## <a name="troubleshooting"></a>การแก้ไขปัญหา
**ไทล์ที่ว่างเปล่า**  
ขณะที่ Power BI เชื่อมต่อไปยังบริการครั้งแรก คุณอาจเห็นชุดที่ว่างเปล่าของไทล์บนแดชบอร์ดของคุณ ถ้าคุณยังคงเห็นแดชบอร์ดว่างเปล่าหลังจากชั่วโมง 2 อาจเป็นได้ว่าการเชื่อมต่อล้มเหลว ถ้าคุณไม่เห็นข้อผิดพลาดกับข้อมูลบนการแก้ไขปัญหา ไฟล์บัตรสนับสนุน

* เลือกไอคอนเครื่องหมายคำถาม ( **?** ) ที่มุมบนขวา > **รับความช่วยเหลือ**
  
    ![ไอคอนรับความช่วยเหลือ](media/service-connect-to-services/power-bi-service-get-help.png)

**ข้อมูลที่หายไป**  
แดชบอร์ดและรายงานมีเนื้อหาจากบริการจะเน้นไปที่สถานการณ์เฉพาะ ถ้าคุณกำลังมองหาเมตริกเฉพาะในแอป และไม่เห็น เพิ่มความคิดเห็นบนการ[Power BI สนับสนุน](https://support.powerbi.com/forums/265200-power-bi)หน้า

## <a name="suggesting-services"></a>บริการให้คำปรึกษา
คุณใช้บริการและคุณต้องการให้คำแนะนำแอป Power BI ใช่หรือไม่ ไปที่[สนับสนุน Power BI ](https://support.powerbi.com/forums/265200-power-bi)หน้า และแจ้งให้เราทราบ

ถ้าคุณสนใจในการสร้างแอปแม่แบบเพื่อกระจายด้วยตนเอง ดู[สร้างแอปแม่แบบใน Power BI](service-template-apps-create.md) Power BI คู่ค้าสามารถสร้างแอป Power BI ด้วยเพียงเล็กน้อย หรือไม่มีการเข้ารหัส และปรับใช้กับลูกค้า Power BI 

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [แจกจ่ายแอปให้เพื่อนร่วมงานของคุณ](service-create-distribute-apps.md)
* [สร้างพื้นที่ทำงานใหม่ใน Power BI](service-create-the-new-workspaces.md)
* มีคำถามหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)
* มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](http://community.powerbi.com/)


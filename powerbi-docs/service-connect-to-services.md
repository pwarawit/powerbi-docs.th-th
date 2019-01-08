---
title: เชื่อมต่อกับบริการที่คุณใช้กับ Power BI
description: เชื่อมต่อกับบริการที่คุณใช้จำนวนหนึ่ง เพื่อเรียกใช้ธุรกิจของคุณ เช่น Salesforce, Microsoft Dynamics CRM และ Google Analytics
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 01/29/2018
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: c2a6e25cae2fcd1a2d84a5ffe6941559593f75c0
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008568"
---
# <a name="connect-to-the-services-you-use-with-power-bi"></a>เชื่อมต่อกับบริการที่คุณใช้กับ Power BI
คุณสามารถเชื่อมต่อกับบริการที่คุณใช้จำนวนหนึ่ง เพื่อเรียกใช้ธุรกิจของคุณ เช่น Salesforce, Microsoft Dynamics CRM และ Google Analytics Power BI เริ่มต้นโดยใช้ข้อมูลประจำตัวของคุณเพื่อเชื่อมต่อกับบริการ และจากนั้นสร้างแอป Power BI ด้วยแดชบอร์ดและชุดของรายงาน Power BI ที่แสดงข้อมูลของคุณและให้ข้อมูลภาพเชิงลึกเกี่ยวกับธุรกิจของคุณโดยอัตโนมัติ


เข้าสู่ระบบ Power BI เพื่อดู[บริการที่คุณสามารถเชื่อมต่อ](https://app.powerbi.com/getdata/services)ทั้งหมด ทีม Power BI เพิ่มบริการใหม่เป็นประจำ

![แอป AppSource](media/service-connect-to-services/overview.png)

หลังจากที่คุณติดตั้งแอป คุณสามารถดูแดชบอร์ดและรายงานในบริการของ Power BI ([https://powerbi.com](https://powerbi.com)) และในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ได้ 

![แอป Google analytics ในแอปมือถือ Power BI](media/service-connect-to-services/power-bi-service-mobile-app-240.png)

## <a name="get-started"></a>เริ่มใช้งาน
[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

## <a name="view-the-dashboard-and-reports"></a>ดูแดชบอร์ดและรายงาน
เมื่อการนำเข้าเสร็จสมบูรณ์ แอปใหม่จะปรากฏบนหน้าแอป

1. เลือก**Apps**ในบานหน้าต่างนำทางด้านซ้าย > เลือกแอป
   
     ![หน้าแอป](media/service-connect-to-services/power-bi-service-apps-open-app.png)
2. คุณสามารถถามคำถามโดยการพิมพ์ในกล่อง Q&A หรือคลิกที่ไทล์เพื่อเปิดรายงานด้านใน 
   
    ![แดชบอร์ Google Analytics](media/service-connect-to-services/googleanalytics2.png)
   
    คุณสามารถกรองและไฮไลต์ข้อมูลในรายงาน แต่คุณไม่สามารถบันทึกการเปลี่ยนแปลงของคุณ

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
หลังจากเชื่อมต่อกับบริการ คุณเห็นแอปที่สร้างขึ้นใหม่กับแดชบอร์ด รายงาน และชุดข้อมูล ข้อมูลจากบริการจะเน้นไปที่สถานการณ์เฉพาะ และอาจรวมถึงข้อมูลทั้งหมดจากบริการ ข้อมูลมีการจัดกำหนดการการรีเฟรชโดยอัตโนมัตหนึ่งครั้งต่อวัน คุณสามารถควบคุมการกำหนดเวลาโดยการเลือกชุดข้อมูล

คุณยังสามารถใช้[Power BI Desktop](desktop-get-the-desktop.md)เชื่อมต่อกับบริการบางอย่าง เช่น Google Analytics และสร้างแดชบอร์ดแบบกำหนดเองและรายงานของคุณเองได้  

สำหรับรายละเอียดเพิ่มเติมเกี่ยวกับการเชื่อมต่อกับบริการแบบเจาะจง โปรดดูวิธีใช้แต่ละหน้า

## <a name="troubleshooting"></a>การแก้ไขปัญหา
**ไทล์ที่ว่างเปล่า**  
ขณะที่ Power BI เชื่อมต่อไปยังบริการครั้งแรก คุณอาจเห็นชุดที่ว่างเปล่าของไทล์บนแดชบอร์ดของคุณ ถ้าคุณยังคงเห็นแดชบอร์ดว่างเปล่าหลังจากชั่วโมง 2 อาจเป็นได้ว่าการเชื่อมต่อล้มเหลว ถ้าคุณไม่เห็นข้อความการผิดพลาดกับรายละเอียดในการแก้ไขปัญหา โปรดเปิดทิกเก็ตการสนับสนุน

* เลือกไอคอนเครื่องหมายคำถาม (**?**) ที่มุมบนขวา > **รับความช่วยเหลือ**
  
    ![ไอคอนรับความช่วยเหลือ](media/service-connect-to-services/power-bi-service-get-help.png)

**ข้อมูลที่หายไป**  
แดชบอร์ดและรายงานมีเนื้อหาข้อมูลจากบริการจะเน้นไปที่สถานการณ์เฉพาะ และอาจรวมถึงข้อมูลทั้งหมดจากบริการร ถ้ามีเมตริกเฉพาะที่คุณไม่เห็นในชุดเนื้อหา โปรดเพิ่มแนวคิดบนหน้า[สนับสนุน Power BI ](https://support.powerbi.com/forums/265200-power-bi)

## <a name="suggesting-services"></a>บริการให้คำปรึกษา
คุณใช้บริการและคุณต้องการให้คำแนะนำแอป Power BI ใช่หรือไม่ ไปที่[สนับสนุน Power BI ](https://support.powerbi.com/forums/265200-power-bi)หน้า และแจ้งให้เราทราบ

คุณมีเซอร์วิซที่คุณต้องการสร้างแอปให้หรือไม่ [ส่งการเสนอชื่อของคุณ](https://azure.microsoft.com/marketplace/programs/certified/apply/)และเลือก "เผยแพร่ชุดเนื้อหา Power BI " เพื่อเริ่มต้นใช้งาน

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [แอป Power BI คืออะไร](service-install-use-apps.md)
* [รับข้อมูลใน Power BI](service-get-data.md)
* มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


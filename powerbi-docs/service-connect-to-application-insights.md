---
title: เชื่อมต่อกับ Application Insights Connect ไปยัง Power BI
description: Application Insights สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 08/10/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 3f0a23c2bdb97c6fbc75981c40cb92c529550b1b
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008246"
---
# <a name="connect-to-application-insights-with-power-bi"></a>เชื่อมต่อกับ Application Insights ด้วย Power BI
ใช้ Power BI เพื่อสร้างแดชบอร์ดแบบกำหนดเองที่มีประสิทธิภาพจากการวัดและส่งข้อมูลทางไกล[Application Insights](/azure/application-insights/app-insights-overview/) นึกภาพการวัดและส่งข้อมูลทางไกลของแอปของคุณในรูปแบบใหม่ รวมเมตริกจากแอปหรือบริการส่วนต่างๆลงบนแดชบอร์ดเดียวกัน การวางจำหน่ายครั้งแรกของชุดเนื้อหา Power BI สำหรับข้อมูลเชิงลึกของแอปพลิเคชันนี้ มีวิดเจ็ตสำหรับการวัดที่เกี่ยวข้องกับการใช้งานทั่วไป เช่นผู้ใช้ที่ใช้งานอยู่ มุมมองหน้า เซสชัน เบราว์เซอร์ และเวอร์ชันระบบปฏิบัติการ และการเผยแพร่ทางภูมิศาสตร์ของผู้ใช้ในแผนที่

เชื่อมต่อไปยัง[เนื้อหาข้อมูลเชิงลึกของแอปพลิเคชันสำหรับ Power BI](https://app.powerbi.com/getdata/services/application-insights)

>[!NOTE]
>**ไม่สนับสนุน**วิธีการรวมนี้ เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับวิธีเชื่อมต่อข้อมูลเชิงลึกของแอปพลิเคชันไปยัง Power BI ใช้ [ส่งออกฟังก์ชั่นคิวรีการวิเคราะห์](https://docs.microsoft.com/azure/application-insights/app-insights-export-power-bi#export-analytics-queries)

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
    ![ปุ่มรับข้อมูล](media/service-connect-to-application-insights/pbi_getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
    ![ปุ่มเริ่มบริการ](media/service-connect-to-application-insights/pbi_getservices.png)
3. เลือก**Application Insights** > **รับ**
   
    ![ชุดเนื้อหาข้อมูลเชิงลึกของแอปพลิเคชัน](media/service-connect-to-application-insights/appinsights.png)
4. ระบุรายละเอียดของแอปพลิเคชันที่คุณต้องการเชื่อมต่อ รวมถึง**ชื่อทรัพยากรข้อมูลเชิงลึกของแอปพลิเคชัน** **กลุ่มทรัพยากร**และ**ID การสมัครใช้งาน** ดู[ค้นหาพารามิเตอร์ของข้อมูลเชิงลึกของแอปพลิเคชัน](#FindingAppInsightsParams)ด้านล่างสำหรับรายละเอียดเพิ่มเติม
   
    ![กล่องโต้ตอบการเชื่อมต่อข้อมูลเชิงลึกของแอปพลิเคชัน](media/service-connect-to-application-insights/pbi_contpkappinsitconnectndialog.png)    
5. เลือก**ลงชื่อเข้าใช้**และทำตามหน้าจอเพื่อเชื่อมต่อ
   
    ![เข้าสู่ระบบเชื่อมต่อกับข้อมูลเชิงลึกของแอปพลิเคชัน](media/service-connect-to-application-insights/pbi_contpkappinsitconnectn2.png)
6. กระบวนการนำเข้าเริ่มต้นโดยอัตโนมัติ เมื่อเสร็จสมบูรณ์ การแจ้งเตือนจะแสดงขึ้นและแดชบอร์ด รายงาน และชุดข้อมูลใหม่จะปรากฏในบานหน้าต่างนำทางที่ทำเครื่องหมายด้วยเครื่องหมายดอกจัน  เลือกแดชบอร์ดเพื่อดูข้อมูลที่นำเข้าของคุณ
   
    ![แดชบอร์ข้อมูลเชิงลึกของแอปพลิเคชัน](media/service-connect-to-application-insights/pbi_contpkappinsitdash.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
ชุดเนื้อหาข้อมูลเชิงลึกของแอปพลิเคชันประกอบด้วยตารางและเมทริกซ์ต่อไปนี้  

    ´´´
    - ApplicationDetails  
    - UniqueUsersLast7Days   
    - UniqueUsersLast30Days   
    - UniqueUsersDailyLast30Days  
    - UniqueUsersByCountryLast7Days  
    - UniqueUsersByCountryLast30Days   
    - PageViewsDailyLast30Days   
    - SessionsLast7Days   
    - SessionsLast30Days  
    - PageViewsByBrowserVersionDailyLast30Days   
    - UniqueUsersByOperatingSystemLast7Days   
    - UniqueUsersByOperatingSystemLast30Days    
    - SessionsDailyLast30Days   
    - SessionsByCountryLast7Days   
    - SessionsByCountryLast30Days   
    - PageViewsByCountryDailyLast30Days  
    ´´´ 

<a name="FindingAppInsightsParams"></a>

## <a name="finding-parameters"></a>การค้นหาพารามิเตอร์
ชื่อทรัพยากร กลุ่มทรัพยากรและ ID การสมัครใช้งานของคุณ สามารถจะพบทั้งหมดในพอร์ทัล Azure โดยเลือกชื่อจะเปิดมุมมองรายละเอียด และคุณสามารถใช้รายการดรอปดาวน์เพื่อค้นหาค่าทั้งหมดที่คุณต้องการ

![พารามิเตอร์ข้อมูลเชิงลึกของแอปพลิเคชัน](media/service-connect-to-application-insights/pbi_contpkappinsitparams.png)

คัดลอก และวางลงในเขตข้อมูลเหล่านี้ลงใน Power BI

![พารามิเตอร์ข้อมูลเชิงลึกของแอปพลิเคชัน](media/service-connect-to-application-insights/pbi_contpkappinsitparam2.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งานใน Power BI](service-get-started.md)

[รับข้อมูลใน Power BI](service-get-data.md)


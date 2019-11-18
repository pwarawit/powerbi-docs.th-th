---
title: ดูรายงานและ KPI ภายในองค์กรในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
description: แอป Power BI สำหรับอุปกรณ์เคลื่อนที่เสนอการใช้งานระบบสัมผัสที่เชื่อมต่อแบบสดเพื่อเข้าถึงข้อมูลทางธุรกิจภายในองค์กรของคุณใน SQL Server Reporting Services และเซิร์ฟเวอร์รายงาน Power BI
author: mshenhav
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 06/13/2018
ms.author: mshenhav
ms.openlocfilehash: 50d44b99d8efea848588ab4c460a469ef6dc780b
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/09/2019
ms.locfileid: "73879450"
---
# <a name="view-on-premises-report-server-reports-and-kpis-in-the-power-bi-mobile-apps"></a>ดูรายงานจากรีพอร์ตเซิร์ฟเวอร์ภายในองค์กรและ KPI ในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่

แอป Power BI สำหรับอุปกรณ์เคลื่อนที่ให้คุณใช้งานในระบบสัมผัสที่เชื่อมต่อแบบสดเพื่อเข้าถึงข้อมูลทางธุรกิจภายในองค์กรของคุณในเซิร์ฟเวอร์รายงาน Power BI และ SQL Server 2016 Reporting Services (SSRS)

นำไปใช้กับ:

| ![iPhone](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![โทรศัพท์ Android](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![แท็บเล็ต Android](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhone |iPad |โทรศัพท์ Android |แท็บเล็ต Android |


![หน้าแรกของรีพอร์ตเซิร์ฟเวอร์ในแอปสำหรับอุปกรณ์เคลื่อนที่](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-pbi-report-server-home.png)

## <a name="first-things-first"></a>ขั้นแรก
**แอปสำหรับอุปกรณ์เคลื่อนที่เป็นตำแหน่งที่คุณดูเนื้อหา Power BI ไม่ใช่ตำแหน่งที่คุณสร้างเนื้อหา**

* คุณและผู้สร้างรายงานคนอื่นๆ ในองค์กรของคุณ[สร้างรายงาน Power BI ด้วย Power BI Desktop จากนั้นเผยแพร่รายงานนั้นไปยังพอร์ทัลเว็บของเซิร์ฟเวอร์รายงาน Power BI](../../report-server/quickstart-create-powerbi-report.md) 
* คุณสร้าง [KPI ในพอร์ทัลเว็บ](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services)จัดระเบียบในโฟลเดอร์ และทำเครื่องหมายรายการโปรดของคุณเพื่อให้คุณสามารถค้นหาได้ง่ายขึ้น 
* คุณ[สร้างรายงานสำหรับอุปกรณ์เคลื่อนที่จาก Reporting Services](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher) ด้วย SQL Server 2016 Enterprise Edition Mobile Report Publisher และเผยแพร่รายงานนนั้นไปยัง[พอร์ทัลเว็บของ Reporting Services](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode)  

จากนั้น ในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่เชื่อมต่อกับรีพอร์ตเซิร์ฟเวอร์ได้ถึงห้าตัวเมื่อต้องการดูรายงาน Power BI และ KPI ที่ถูกจัดระเบียบในโฟลเดอร์หรือถูกเก็บรวบรวมเป็นรายการโปรด 

## <a name="explore-samples-in-the-mobile-apps-without-a-server-connection"></a>สำรวจตัวอย่างในแอปสำหรับอุปกรณ์เคลื่อนที่โดยไม่มีการเชื่อมต่อเซิร์ฟเวอร์
แม้ว่าคุณไม่สามารถเข้าถึงพอร์ทัลเว็บของ Reporting Services คุณยังสามารถสำรวจฟีเจอร์ของรายงานสำหรับอุปกรณ์เคลื่อนที่ของ Reporting Services และ KPI 

1. แตะปุ่มนำทางส่วนกลาง ![ปุ่มนำทางส่วนกลาง](././media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png) ทางมุมบนซ้าย แตะไอคอนเฟืองมุมบนขวา ![ไอคอนรูปเฟือง](././media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png).
2. แตะ**ตัวอย่าง Reporting Services** จากนั้น เรียกดูเพื่อโต้ตอบกับตัวอย่าง KPI และรายงานสำหรับอุปกรณ์เคลื่อนที่
   
   ![ตัวอย่างของบริการการรายงาน](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-ssrs-samples.png)

## <a name="connect-to-an-on-premises-report-server"></a>เชื่อมต่อกับเซิร์ฟเวอร์ภายในองค์กร
คุณสามารถดูรายงาน Power BI สำหรับองค์กร รายงานจาก Reporting Services และ KPI ในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ 

1. บนอุปกรณ์เคลื่อนที่ เปิดแอป Power BI
2. ถ้าคุณยังไม่ได้ลงชื่อเข้าใช้ Power BI แตะ**รีพอร์ตเซิร์ฟเวอร์**
   
   ![ลงชื่อเข้าใช้รีพอร์ตเซิร์ฟเวอร์](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-connect-to-rs-login.png)
   
   ถ้าคุณได้ลงชื่อเข้าใช้แอป Power BI แล้ว แตะปุ่มนำทางส่วนกลาง ![ปุ่มนำทางส่วนกลาง](././media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png)จากนั้น แตะไอคอนรูปเฟือง ![ไอคอนรูปเฟือง](././media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png) มุมบนขวา
3. แตะ**เชื่อมต่อกับเซิร์ฟเวอร์**
   
    ![เชื่อมต่อกับเซิร์ฟเวอร์](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-android-server-sign-in.png)

     แอปสำหรับอุปกรณ์เคลื่อนที่จำเป็นต้องเข้าถึงเซิร์ฟเวอร์ในลักษณะบางอย่าง มีสองสามวิธีดำเนินการดังกล่าว:

    - การใช้เครือข่ายเดียวกัน/การใช้ VPN เป็นวิธีง่ายที่สุด
    - จำเป็นต้องใช้พร็อกซีของแอปพลิเคชันบนเว็บเพื่อเชื่อมต่อจากภายนอกองค์กร ดู[ใช้ OAuth เพื่อเชื่อมต่อกับ Reporting Services ](mobile-oauth-ssrs.md)สำหรับรายละเอียด 
    - เปิดการเชื่อมต่อ (พอร์ต) ในไฟร์วอลล์

1. กรอกที่อยู่เซิร์ฟเวอร์ และชื่อผู้ใช้และรหัสผ่านของคุณ ใช้รูปแบบนี้สำหรับที่อยู่ของเซิร์ฟเวอร์:
   
     `https://<servername>/reports`
   
     หรือ
   
     `https://<servername>/reports`
   
   ใส่**http**หรือ**https**ด้านหน้าของสตริงการเชื่อมต่อ
   
    ![เชื่อมต่อกับกล่องโต้ตอบของเซิร์ฟเวอร์](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-connect-to-server-dialog.png)
5. (ไม่บังคับ) ภายใต้**ตัวเลือกขั้นสูง**คุณสามารถตั้งชื่อเซิร์ฟเวอร์ด้วยชื่อที่เรียกง่าย ถ้าคุณต้องการ
6. ในตอนนี้ คุณเห็นเซิร์ฟเวอร์ในบานหน้าต่างนำทาง--ในตัวอย่างนี้ เรียกว่า "Power BI Report Server"
   
   ![เซิร์ฟเวอร์รายงานในบานหน้าต่างนำทาง](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-left-nav-report-server.png)

## <a name="connect-to-an-on-premises-report-server-in-ios"></a>เชื่อมต่อกับเซิร์ฟเวอร์รายงานภายในองค์กรใน iOS

ถ้าคุณกำลังดู Power BI ในแอปสำหรับอุปกรณ์ที่ iOS ผู้ดูแลระบบ IT ของคุณอาจมีนโยบายการกำหนดค่าแอป ถ้าเป็นเช่นนั้น ประสบการณ์การเชื่อมต่อกับเซิร์ฟเวอร์รายงานของคุณถูกทำให้ง่ายขึ้น และคุณไม่ต้องใส่ข้อมูลมากเท่าเดิมเมื่อคุณเชื่อมต่อกับเซิร์ฟเวอร์รายงาน 

1. คุณจะเห็นข้อความว่า แอปสำหรับอุปกรณ์เคลื่อนที่ของคุณได้กำหนดค่าสำหรับเซิร์ฟเวอร์รายงานแล้ว แตะ**ลงชื่อเข้าใช้**

    ![ลงชื่อเข้าใช้เซิร์ฟเวอร์รายงาน](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-config-server-sign-in.png)

2.  บนหน้า**เชื่อมต่อกับเซิร์ฟเวอร์** รายละเอียดของเซิร์ฟเวอร์รายงานได้ถูกกรอกให้แล้ว แตะ**เชื่อมต่อ**

    ![รายละเอียดของเซิร์ฟเวอร์รายงานที่กรอกให้แล้ว](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-remote-configure-connect-server.png)

3. พิมพ์รหัสผ่านเพื่อรับรองความถูกต้อง จากนั้นแตะ**ลงชื่อเข้าใช้** 

    ![รายละเอียดของเซิร์ฟเวอร์รายงานที่กรอกให้แล้ว](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-config-server-address.png)

ตอนนี้ คุณสามารถดูและโต้ตอบกับ KPI และรายงาน Power BI ที่จัดเก็บบนเซิร์ฟเวอร์รายงาน

## <a name="view-power-bi-reports-and-kpis-in-the-power-bi-app"></a>ดูรายงาน Power BI และ KPI ในแอป Power BI
รายงาน Power BI รายงานสำหรับอุปกรณ์เคลื่อนที่ของ Reporting Services และ KPI จะแสดงอยู่ในโฟลเดอร์เดียวกันบนพอร์ทัลเว็บของ Reporting Services 

* แตะรายงาน Power BI ![ไอคอนรายงานของ power BI](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-report-icon.png). การแตะจะเปิดโหมดแนวนอน และคุณสามารถโต้ตอบกับไฟล์ในแอป Power BI ได้

    > [!NOTE]
  > ดูรายละเอียดลงและขึ้นในขณะนี้ไม่ได้เปิดใช้งานในรายงานของ Power BI บนเซิร์ฟเวอร์รายงาน Power BI
  
    ![รายงาน power BI](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-report-server-report.png)
* ใน Power BI Desktop เจ้าของรายงานสามารถ[ปรับรายงาน](../../desktop-create-phone-report.md)ให้เหมาะสมสำหรับแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ได้ บนโทรศัพท์มือถือ รายงานที่ปรับให้เหมาะสมจะมีไอคอนพิเศษ![ไอคอนรายงาน Power BI ที่ปรับให้เหมาะสม](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-icon.png)และแบบการจัดหน้า
  
    ![รายงาน power BI ที่ปรับให้เหมาะสมสำหรับอุปกรณ์เคลื่อนที่](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-report.png)
* แตะ KPI เพื่อดูในโหมดโฟกัส
  
    ![KPI ในโหมดโฟกัส](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/pbi_ipad_ssmrp_tile.png)

## <a name="view-your-favorite-kpis-and-reports"></a>ดู KPI และรายงานที่เป็นรายการโปรดของคุณ
คุณสามารถเพิ่ม KPIs และรายงานให้เป็นรายการโปรดบนพอร์ทัลเว็บ จากนั้น ดูข้อมูลดังกล่าวได้ในโฟลเดอร์หนึ่งที่สะดวกบนอุปกรณ์เคลื่อนที่ พร้อมกับแดชบอร์ดโปรด Power BI ของคุณ

* แตะ **รายการโปรด**
  
   ![รายการโปรดในบานหน้าต่างนำทาง](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-faves-pbi-report-server-update.png)
  
   KPI และรายงานโปรดจากพอร์ทัลเว็บของคุณจะอยู่บนหน้านี้ทั้งหมด พร้อมกับแดชบอร์ด Power BI ในบริการของ Power BI:
  
   ![รายงาน Power BI และแดชบอร์ดในหน้ารายการโปรด](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-favorites.png)

## <a name="remove-a-connection-to-a-report-server"></a>ยุติการเชื่อมต่อกับรีพอร์ตเซิร์ฟเวอร์
1. ที่ด้านล่างของบานหน้าต่างนำทาง ให้แตะ **การตั้งค่า**
2. แตะชื่อเซิร์ฟเวอร์ที่คุณไม่ต้องการเชื่อมต่อ
3. แตะ**ถอดเซิร์ฟเวอร์**

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [Power BI คืออะไร](../../fundamentals/power-bi-overview.md)  
* มีคำถามหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)


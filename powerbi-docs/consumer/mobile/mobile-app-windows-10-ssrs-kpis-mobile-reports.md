---
title: ดูรายงานอุปกรณ์มือถือของ SSRS, KPI ในแอปสำหรับอุปกรณ์เคลื่อนที่ของ Windows 10 - Power BI
description: แอปสำหรับอุปกรณ์เคลื่อนที่ Power BI สำหรับ Windows 10 มีคุณลักษณะการเข้าถึงผ่านอุปกรณ์เคลื่อนที่แบบสดและรองรับระบบสัมผัส เพื่อเข้าใช้งานข้อมูลทางธุรกิจที่สำคัญภายในองค์กรของคุณ
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 06/28/2018
ms.author: mshenhav
ms.openlocfilehash: 114cf65e8abb072ab3f0254cbd4041a43a31d1dc
ms.sourcegitcommit: d441d350504f8c6d9e100d229757add6237f0bef
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/30/2019
ms.locfileid: "73059649"
---
# <a name="view-reporting-services-ssrs-mobile-reports-and-kpis-in-the-windows-10-power-bi-mobile-app"></a>ดรายงานอุปกรณ์มือถือของ Reporting Services (SSRS) และ KPI ในแอปสำหรับอุปกรณ์เคลื่อนที่ Power BI สำหรับ Windows 10
แอปสำหรับอุปกรณ์เคลื่อนที่ Power BI สำหรับ Windows 10 มีคุณลักษณะการเข้าถึงผ่านอุปกรณ์เคลื่อนที่แบบสดและรองรับระบบสัมผัส เพื่อเข้าใช้งานข้อมูลทางธุรกิจที่สำคัญภายในองค์กรของคุณใน SQL Server 2016 Reporting Services 

![รายงานอุปกรณ์มือถือของ Reporting Services](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="first-things-first"></a>สิ่งแรกที่ต้องทำ
[สร้างรายงานอุปกรณ์มือถือของ Reporting Services](https://msdn.microsoft.com/library/mt652547.aspx) ด้วย SQL Server 2016 Enterprise Edition Mobile Report Publisher แล้วเผยแพร่รายงานอุปกรณ์มือถือนั้นไปยัง [พอร์ทัลของเว็บ Reporting Services](https://msdn.microsoft.com/library/mt637133.aspx) สร้าง KPI อย่างเหมาะสมในพอร์ทัลของเว็บ จัดระเบียบรายงานอุปกรณ์มือถือในโฟลเดอร์ แล้วทำเครื่องหมายเป็นรายการโปรดของคุณ เพื่อให้คุณสามารถค้นหาได้ง่าย 

จากนั้น ในแอปสำหรับอุปกรณ์เคลื่อนที่ Power BI สำหรับ Windows 10 ให้ดูรายงานอุปกรณ์มือถือและ KPI ที่จัดระเบียบไว้ในโฟลเดอร์หรือเก็บรวบรวมไว้เป็นรายการโปรด 

> [!NOTE]
> อุปกรณ์ของคุณจะต้องสามารถใช้งาน Windows 10 ได้ แอปสามารถทำงานได้เต็มประสิทธิภาพในอุปกรณ์ที่มี RAM อย่างน้อย 1 GB และที่เก็บข้อมูลภายใน 8 GB
> 
> 

## <a name="explore-samples-without-a-sql-server-2016-reporting-services-server"></a>สำรวจตัวอย่างโดยไม่มีเซิร์ฟเวอร์ SQL Server 2016 Reporting Services
แม้ว่าคุณไม่สามารถเข้าถึงพอร์ทัลของเว็บ Reporting Services ได้ แต่ยังสามารถสำรวจดูคุณลักษณะต่างๆ ในรายงานอุปกรณ์มือถือของ Reporting Services ได้

1. ในอุปกรณ์ที่ใช้งาน Windows 10 ของคุณ ให้เปิดแอป Power BI
2. แตะปุ่มการนำทางส่วนกลาง ![ปุ่มการนำทางส่วนกลาง](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/powerbi_windows10_options_icon.png) ในมุมบนซ้าย
3. แตะไอคอน **การตั้งค่า** ![ไอคอนการตั้งค่า](./././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png) คลิกขวา หรือแตะค้าง **เชื่อมต่อกับเซิร์ฟเวอร์** แล้วแตะ **ดูตัวอย่าง**
   
   ![ดูตัวอย่างของ SSRS](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-win10-connect-ssrs-samples.png)
4. เปิดโฟลเดอร์รายงานการขายปลีกหรือรายงานการขาย เพื่อสำรวจ KPI และรายงานอุปกรณ์มือถือของโฟลเดอร์เหล่านี้
   
   ![ตัวอย่าง KPIs และรายงานอุปกรณ์มือถือ](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-win10-ssrs-sample-kpis.png)

เรียกดูตัวอย่าง เพื่อโต้ตอบกับ KPI และรายงานอุปกรณ์มือถือ

## <a name="connect-to-a-reporting-services-report-server"></a>เชื่อมต่อกับรีพอร์ตเซิร์ฟเวอร์ของ Reporting Services
1. ที่ด้านล่างของแถบนำทางด้านซ้าย ให้แตะ **การตั้งค่า** ![ไอคอนการตั้งค่า](./././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png)
2. แตะ **เชื่อมต่อกับเซิร์ฟเวอร์**
3. กรอกที่อยู่เซิร์ฟเวอร์ รวมทั้งชื่อผู้ใช้และรหัสผ่านของคุณ ใช้รูปแบบนี้สำหรับที่อยู่เซิร์ฟเวอร์:
   
     `http://<servername>/reports` OR   `https://<servername>/reports`
   
   > [!NOTE]
   > ใส่ **http**หรือ**https** ที่ด้านหน้าของสตริงการเชื่อมต่อ
   > 
   > 
   
    แตะ **ตัวเลือกขั้นสูง** เพื่อตั้งชื่อให้เซิร์ฟเวอร์ ถ้าต้องการ
4. แตะเครื่องหมายถูก เพื่อเชื่อมต่อ 
   
   ในตอนนี้ คุณจะเห็นเซิร์ฟเวอร์อยู่ในแถบนำทางด้านซ้าย
   
   ![เซิร์ฟเวอร์ในแถบนำทางด้านซ้าย](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-server.png)
   
   >[!TIP]
   >แตะปุ่มการนำทางส่วนกลาง ![ปุ่มการนำทางส่วนกลาง](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/powerbi_windows10_options_icon.png) ได้ตลอดเวลา เพื่อสลับไปมาระหว่างรายงานอุปกรณ์มือถือของ Reporting Services ของคุณกับแดชบอร์ดของคุณในบริการของ Power BI 
   > 

## <a name="view-reporting-services-kpis-and-mobile-reports-in-the-power-bi-app"></a>ดู KPI และรายงานอุปกรณ์มือถือของ Reporting Services ในแอป Power BI
KPI และรายงานอุปกรณ์มือถือของ Reporting Services จะปรากฏอยู่ในโฟลเดอร์เดียวกันซึ่งอยู่ในพอร์ทัลของเว็บ Reporting Services

![โฟลเดอร์รายงาน](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-folders.png)

* แตะ KPI เพื่อดูในโหมดโฟกัส
  
    ![KPI ในโหมดโฟกัส](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-kpis.png)
* แตะรายงานอุปกรณ์มือถือ เพื่อเปิด และโต้ตอบกับรายงานอุปกรณ์มือถือนั้นในแอป Power BI
  
    ![รายงานอุปกรณ์มือถือของ Reporting Services](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="view-your-favorite-kpis-and-reports"></a>ดู KPI และรายงานที่เป็นรายการโปรดของคุณ
คุณสามารถทำเครื่องหมายให้ KPI และรายงานอุปกรณ์มือถือต่างๆ ในพอร์ทัลของเว็บ Reporting Services ของคุณเป็นรายการโปรด จากนั้นดูรายการโปรดเหล่านี้ในโฟลเดอร์ใดโฟลเดอร์หนึ่งตามที่สะดวกในอุปกรณ์ Windows 10 ของคุณ รวมทั้งรายงานและแดชบอร์ดที่เป็นรายการโปรดใน Power BI ของคุณ

* แตะ **รายการโปรด**
  
   ![ไอคอนรายการโปรด](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-favorite-menu.png)
  
   รายการโปรดของคุณจากพอร์ทัลของเว็บทั้งหมดล้วนอยู่ในหน้านี้
  
   ![หน้ารายการโปรด](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-windows-10-ssrs-favorites.png)

อ่านข้อมูลเพิ่มเติมเกี่ยวกับ [รายการโปรดในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่](mobile-apps-favorites.md)

## <a name="remove-a-connection-to-a-report-server"></a>ยุติการเชื่อมต่อกับรีพอร์ตเซิร์ฟเวอร์
คุณสามารถเชื่อมต่อกับรีพอร์ตเซิร์ฟเวอร์จากแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ได้เพียงครั้งละหนึ่งเซิร์ฟเวอร์เท่านั้น ถ้าคุณต้องการเชื่อมต่อกับเซิร์ฟเวอร์อื่น ก็จะต้องยกเลิกการเชื่อมต่อกับเซิร์ฟเวอร์ที่ใช้งานอยู่ในปัจจุบันก่อน

1. ที่ด้านล่างของแถบนำทางด้านซ้าย ให้แตะ **การตั้งค่า** ![ไอคอนการตั้งค่า](./././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png)
2. แตะค้างที่ชื่อเซิร์ฟเวอร์ที่คุณไม่ต้องการเชื่อมต่อ
3. แตะ **ลบเซิร์ฟเวอร์**
   
    ![ลบเซิร์ฟเวอร์](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-windows-10-ssrs-remove-server-menu.png)

## <a name="create-reporting-services-mobile-reports-and-kpis"></a>สร้างรายงานอุปกรณ์มือถือและ KPI ของ Reporting Services
คุณไม่สามารถสร้าง KPI และรายงานอุปกรณ์มือถือของ Reporting Services ในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ได้ คุณสามารถสร้างส่วนเหล่านั้นได้ใน SQL Server Mobile Report Publisher และพอร์ทัลของเว็บ SQL Server 2016 Reporting Services

* [สร้างรายงานอุปกรณ์มือถือของ Reporting Services ของคุณเอง](https://msdn.microsoft.com/library/mt652547.aspx) แล้วเผยแพร่ไปยังพอร์ทัลของเว็บ Reporting Services
* สร้าง [KPI ในพอร์ทัลของเว็บ Reporting Services](https://msdn.microsoft.com/library/mt683632.aspx)

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [เริ่มต้นใช้งานแอป Power BI สำหรับอุปกรณ์เคลื่อนที่สำหรับ Windows 10](mobile-windows-10-phone-app-get-started.md)  
* [Power BI คืออะไร](../../fundamentals/power-bi-overview.md)  
* มีคำถามหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


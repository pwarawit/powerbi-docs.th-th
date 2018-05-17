---
title: เริ่มต้นใช้งานแอปสำหรับอุปกรณ์เคลื่อนที่ Power BI บนแท็บเล็ต Android
description: เรียนรู้วิธีที่แอปสำหรับอุปกรณ์เคลื่อนที่ Power BI สำหรับแท็บเล็ต Android พา Power BI ไปกับคุณทุกที่ ให้คุณเข้าถึงข้อมูลทางธุรกิจ ทั้งภายในองค์กรและในระบบคลาวด์ ด้วยอุปกรณ์เคลื่อนที่
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 407f4d8c2faf26b9837b24318c24c118786e21ae
ms.sourcegitcommit: ee5d044db99e253c27816e0ea6bdeb9e39a2cf41
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/08/2018
---
# <a name="get-started-with-the-power-bi-mobile-app-on-android-tablets"></a>เริ่มต้นใช้งานแอปสำหรับอุปกรณ์เคลื่อนที่ Power BI บนแท็บเล็ต Android
แอป Power BI สำหรับอุปกรณ์เคลื่อนที่ สำหรับแท็บเล็ต Android มอบประสบการณ์ BI บนอุปกรณ์เคลื่อนที่สำหรับ Power BI, เซิร์ฟเวอร์รายงาน Power BI และ Reporting Services ดูและโต้ตอบกับแดชบอร์ดของบริษัทของคุณ ภายในองค์กรและในคลาวด์ จากที่ใดก็ได้ ผ่านอุปกรณ์เคลื่อนที่ ที่รองรับระบบสัมผัสและดูข้อมูลสดได้ สำรวจข้อมูลในแดชบอร์ด และแชร์กับเพื่อนร่วมงานของคุณผ่านอีเมลหรือการส่งข้อความ 

![แดชบอร์ด Power BI ในแท็บเล็ต Android](media/mobile-android-tablet-app-get-started/power-bi-android-tablet-report.png)

คุณสร้างรายงาน Power BI ใน Power BI Desktop และเผยแพร่:

* [เผยแพร่ไปยังบริการของ Power BI](service-get-started.md) และสร้างแดชบอร์ด
* [เผยแพร่ภายในองค์กรไปยัง เซิร์ฟเวอร์รายงาน Power BI](report-server/quickstart-create-powerbi-report.md)

จากนั้น ในแอป Power BI สำหรับแท็บเล็ต Android คุณโต้ตอบกับแดชบอร์ดและรายงานของคุณ ไม่ว่าจะอยู่ภายในองค์กรหรืออยู่ในระบบคลาวด์ ดูว่า[มีอะไรใหม่ในแอป Power Bi](mobile-whats-new-in-the-mobile-apps.md) สำหรับอุปกรณ์เคลื่อนที่

## <a name="first-things-first"></a>ขั้นแรก
* **รับแอป** [รับแอป Power BI สำหรับ Android](http://go.microsoft.com/fwlink/?LinkID=544867) จาก Google Play
  
  > [!NOTE]
  > Power BI สามารถทำงานบนแท็บเล็ต Android ที่หลากหลาย แท็บเล็ตคุณจำเป็นต้องใช้ระบบปฏิบัติการ Android 5.0 หรือใหม่กว่า เพื่อตรวจสอบแท็บเล็ตคุณ ไปที่**การตั้งค่า** > **เกี่ยวกับ** > **เวอร์ชันของ Android** 
  > 
  > 
* **เริ่มต้นเมื่อคุณเปิดแอป** ถึงแม้ว่าคุณจะยังไม่ลงทะเบียนหรือลงชื่อเข้าใช้ หลังจากที่คุณเปิดแอปแล้วคุณสามารถพลิกดูหน้าลงชื่อเข้าใช้ เพื่อเห็นภาพรวมของสิ่งที่คุณสามารถทำได้ ด้วยแอป Power BI บนแท็บเล็ต Android ของคุณ แตะ**ข้าม** เพื่อดูและสำรวจตัวอย่าง และทดลองประสบการณ์การใช้งานกับแอป คุณสามารถ[กลับไปยังตัวอย่าง](mobile-android-tablet-app-get-started.md#try-the-power-bi-and-reporting-services-samples) เมื่อใดก็ตามที่คุณต้องการ จากโฮมเพจแดชบอร์ดได้
* ดูว่า[มีอะไรใหม่ในแอป Power Bi](mobile-whats-new-in-the-mobile-apps.md) สำหรับอุปกรณ์เคลื่อนที่

## <a name="sign-up-for-the-power-bi-service-on-the-web"></a>ลงทะเบียนสำหรับบริการของ Power BI บนเว็บ
ถ้าคุณยังไม่ได้ลงทะเบียน ไปที่[บริการของ Power BI (http://powerbi.com/)](http://powerbi.com/) เพื่อลงทะเบียนบัญชีของคุณ สำหรับสร้างและจัดเก็บแดชบอร์ดและรายงาน และนำข้อมูลของคุณรวมเข้าด้วยกัน จากนั้น ลงชื่อเข้าใช้ Power BI จากแท็บเล็ต Android ของคุณเพื่อดูแดชบอร์ดของคุณเองจากที่ไหนก็ได้

1. ในบริการของ Power BI แตะ[ลงทะเบียน](http://go.microsoft.com/fwlink/?LinkID=513879)เพื่อสร้างบัญชี Power BI
2. เริ่มต้น[สร้างแดชบอร์ดและรายงานของคุณเอง](service-get-started.md)

## <a name="get-started-with-the-power-bi-app-on-your-tablet"></a>เริ่มต้นใช้งานแอป Power BI บนแท็บเล็ตของคุณ
1. บนแท็บเล็ต Android จากหน้าจอเริ่ม เปิดแอป Power BI สำหรับ Android
   
   ![ไอคอนเริ่มต้นของ power BI](media/mobile-android-tablet-app-get-started/power-bi-logo-android.png)
2. เมื่อต้องการดูแดชบอร์ดและรายงาน Power BI ของคุณ แตะที่ **Power BI**  
   
   > [!IMPORTANT]
   > ถ้าคุณได้รับข้อความว่า Power BI ไม่สามารถลงชื่อคุณเข้าใช้ ดูที่ ["ไม่สามารถรับรองความถูกต้องได้เนื่องจากใบรับรอง SSL ของบริษัทของคุณไม่น่าเชื่อถือ"](mobile-android-app-error-corporate-ssl-account-is-untrusted.md) สำหรับรายละเอียดวิธีการแก้ปัญหานี้
   > 
   > 
   
   เพื่อดูรายงานและ KPI ของรีพอร์ตเซิร์ฟเวอร์ Power BI และ Reporting Services ภายในองค์กรของคุณ แตะที่ **รีพอร์ตเซิร์ฟเวอร์**
   
   ![ลงชื่อเข้าใช้ไปยัง Power BI](media/mobile-android-tablet-app-get-started/power-bi-connect-to-login.png)
   
   ให้ข้อมูลการลงชื่อเข้าใช้ของคุณกับเซิร์ฟเวอร์รายงาน เพื่อ[ดูรายงานและ KPI ของเซิร์ฟเวอร์รายงาน Power BI และ Reporting Services](mobile-app-ssrs-kpis-mobile-on-premises-reports.md) ในแอปแท็บเล็ต Android สำหรับ Power BI

## <a name="try-the-power-bi-and-reporting-services-samples"></a>ลองใช้ตัวอย่าง Power BI และ Reporting Services
แม้ว่าจะยังไม่ลงทะเบียน คุณสามารถเล่นกับตัวอย่าง Power BI และ Reporting Services ได้ หลังจากคุณดาวน์โหลดแอป คุณสามารถดูตัวอย่าง หรือเริ่มต้นใช้งาน กลับไปยังตัวอย่างเมื่อใดก็ตามที่คุณต้องการ จากโฮมเพจแดชบอร์ด

### <a name="power-bi-samples"></a>ตัวอย่าง Power BI
คุณสามารถดูและโต้ตอบกับตัวอย่างแดชบอร์ด Power BI แต่มีบางสิ่งที่คุณไม่สามารถทำได้กับตัวอย่างนี้ คุณไม่สามารถเปิดรายงานที่อยู่หลังแดชบอร์ด แชร์ตัวอย่างกับผู้อื่น หรือทำให้เป็นรายการโปรดของคุณ

1. แตะปุ่มนำทางส่วนกลาง ![ปุ่มการนำทางส่วนกลาง](media/mobile-android-tablet-app-get-started/power-bi-android-options-icon.png) ในมุมบนซ้าย
2. แตะที่**การตั้งค่า** > **ค้นพบตัวอย่างของเรา** จากนั้นเลือกบทบาท และสำรวจแดชบอร์ดตัวอย่างสำหรับบทบาทนั้น 
   
   ![ตัวอย่างสำหรับแอปอุปกรณ์เคลื่อนของ power BI](media/mobile-android-tablet-app-get-started/power-bi-android-tablet-samples.png)

### <a name="reporting-services-mobile-report-samples"></a>ตัวอย่างรายงานบนอุปกรณ์เคลื่อนท่ีของ Reporting Services
1. แตะปุ่มนำทางส่วนกลาง ![ปุ่มการนำทางส่วนกลาง](media/mobile-android-tablet-app-get-started/power-bi-android-options-icon.png) ในมุมบนซ้าย
2. แตะ**ตัวอย่างของรีพอร์ตเซิร์ฟเวอร์** จากนั้นเปิดโฟลเดอร์รายงานการขายปลีกหรือรายงานการขาย เพื่อสำรวจ KPI และรายงานบนอุปกรณ์เคลื่อนที่ของพวกเขา
   
   ![ตัวอย่างของรีพอร์ตเซิร์ฟเวอร์](media/mobile-android-tablet-app-get-started/power-bi-android-tablet-ssrs-samples.png)

## <a name="search-for-a-dashboard-or-report"></a>ค้นหาแดชบอร์ดหรือรายงาน
* แตะแว่นขยายที่มุมบนขวา ![ไอคอนค้นหา](media/mobile-android-tablet-app-get-started/power-bi-ipad-search-icon.png)จากนั้นพิมพ์คำเพื่อค้นหา
  
    ![ผลลัพธ์การค้นหา](media/mobile-android-tablet-app-get-started/power-bi-android-tablet-search.png)
  
    ตามค่าเริ่มต้น ระบบจะค้นหาแดชบอร์ดและรายงานทั้งหมด แต่คุณสามารถค้นหาเพียงประเภทเดียวก็ได้

## <a name="find-your-content-in-the-power-bi-mobile-apps"></a>ค้นหาเนื้อหาของคุณในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
แดชบอร์ดและรายงานของคุณถูกเก็บไว้คนละที่ในแอปสำหรับอุปกรณ์เคลื่อนที่ Power BI ขึ้นอยู่กับว่ามาจากที่ใด อ่านเกี่ยวกับ[การค้นหาเนื้อหาของคุณในแอปสำหรับอุปกรณ์เคลื่อนที่](mobile-apps-find-content-mobile-devices.md) นอกจากนี้ คุณสามารถค้นหาสิ่งต่าง ๆ ที่คุณมีในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่  

![บานหน้าต่างนำทางด้านซ้ายของ power BI](media/mobile-android-tablet-app-get-started/power-bi-mobile-new-nav-no-numbers.png)

## <a name="view-your-favorite-dashboards-kpis-and-reports"></a>ดูแดชบอร์ด KPI และรายงานโปรดของคุณ
บนหน้ารายการโปรดในแอปอุปกรณ์เคลื่อนที่ คุณเห็นแดชบอร์ด Power BI โปรดทั้งหมดของคุณ รวมไปถึง KPI และรายงาน เซิร์ฟเวอร์รายงาน Power BI และพอร์ทัลของเว็บ Reporting Services เมื่อคุณทำให้แดชบอร์ดเป็น*รายการโปรด*ในแอปอุปกรณ์เคลื่อนที่ Power BI คุณสามารถเข้าถึงแดชบอร์ดดังกล่าวได้จากทุกอุปกรณ์ของคุณ รวมถึงบริการของ Power BI ในเบราว์เซอร์ของคุณได้ 

* แตะ**รายการโปรด**
  
   ![รายการโปรดในบานหน้าต่างนำทางด้านซ้าย](media/mobile-android-tablet-app-get-started/power-bi-android-favorites-left-nav.png)
  
   รายการโปรดของ Power BI ของคุณ และรายการโปรดของคุณจากพอร์ทัลของเว็บเซิร์ฟเวอร์รายงาน Power BI และ Reporting Services ทั้งหมดจะอยู่บนหน้านี้
  
   ![หน้ารายการโปรด](media/mobile-android-tablet-app-get-started/power-bi-android-tablet-favorites.png)

อ่านเพิ่มเติมเกี่ยวกับ[รายการโปรดในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่](mobile-apps-favorites.md)

## <a name="enterprise-support-for-the-power-bi-mobile-apps"></a>การสนับสนุนองค์กรสำหรับแอปสำหรับอุปกรณ์เคลื่อนที่ Power BI
องค์กรสามารถใช้ Microsoft Intune เพื่อจัดการอุปกรณ์และแอปพลิเคชัน รวมถึงแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ สำหรับ Android และ iOS

Microsoft Intune ช่วยให้องค์กรควบคุมรายการ เช่น การบังคับใช้ Pin เพื่อเข้าใช้งาน การควบคุมวิธีจัดการกับข้อมูลโดยแอปพลิเคชัน หรือแม้แต่ารเข้ารหัสลับข้อมูลแอปพลิเคชันเมื่อไม่ได้ใช้งาน

> [!NOTE]
> ถ้าคุณใช้แอป Power BI สำหรับอุปกรณ์เคลื่อนที่ บนอุปกรณ์ Android ของคุณ และองค์กรของคุณได้กำหนดค่า Microsoft Intune MAM การรีเฟรชข้อมูลพื้นหลังจะถูกปิดใช้งาน ครั้งถัดไปที่คุณเข้าใช้งานแอป Power BI จะรีเฟรชข้อมูลจากบริการของ Power BI บนเว็บ
> 
> 

อ่านเพิ่มเติมเกี่ยวกับ[การกำหนดค่าแอปสำหรับอุปกรณ์เคลื่อนที่ Power BI สำหรับ Android ด้วย Microsoft Intune](service-admin-mobile-intune.md) 

## <a name="next-steps"></a>ขั้นตอนถัดไป
ต่อไปนี้คือสิ่งอื่น ๆ ที่คุณสามารถทำในแอปแท็บเล็ต Android สำหรับ Power BI กับแดชบอร์ดและรายงานใน Power BI, รายงานและ KPI ในพอร์ทัลของเว็บเซิร์ฟเวอร์รายงาน Power BI หรือ Reporting Services

### <a name="power-bi-dashboards-and-reports"></a>แดชบอร์ดและรายงาน Power BI
* ดู[แอปของคุณ](service-install-use-apps.md)
* ดู[แดชบอร์ด](mobile-apps-view-dashboard.md)ของคุณ
* [ใส่คำอธิบายประกอบ และแชร์ไทล์](mobile-annotate-and-share-a-tile-from-the-mobile-apps.md)
* แชร์[แดชบอร์ด](mobile-share-dashboard-from-the-mobile-apps.md)
* [สแกนรหัส QR Power BI](mobile-apps-qr-code.md) เพื่อเปิดไทล์แดชบอร์ดหรือรายงานที่เกี่ยวข้อง
* ดู[การแจ้งเตือนเกี่ยวกับอัปเดตต่าง ๆ ในบัญชี Power BI ของคุณ](mobile-apps-notification-center.md) เช่นแดชบอร์ดที่เพื่อนร่วมงานแชร์ให้คุณ

### <a name="reports-and-kpis-on-the-power-bi-report-server-and-reporting-services-web-portals"></a>รายงานและ KPI บนพอร์ทัลของเว็บเซิร์ฟเวอร์รายงาน Power BI และ Reporting Services
* [ดูรายงานและ KPI บนพอร์ทัลของเว็บ](mobile-app-ssrs-kpis-mobile-on-premises-reports.md)ในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ สำหรับอุปกรณ์ Android
* สร้าง [KPI บนพอร์ทัลของเว็บ](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services)
* สร้าง [รายงานใน Power BI Desktop และเผยแพร่รายการนั้น ๆ บนพอร์ทัลของเว็บเซิร์ฟเวอร์รายงาน Power BI](report-server/quickstart-create-powerbi-report.md)

### <a name="see-also"></a>ดูเพิ่มเติม
* [ดาวน์โหลดแอป Android](http://go.microsoft.com/fwlink/?LinkID=544867) จาก Android app store
* [เริ่มต้นใช้งาน Power BI](service-get-started.md)
* คำถามหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


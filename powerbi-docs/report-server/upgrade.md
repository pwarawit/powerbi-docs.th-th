---
title: อัปเกรด Power BI Report Server
description: เรียนรู้วิธีการอัปเกรด Power BI Report Server
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 09/05/2017
ms.author: maghan
ms.openlocfilehash: e54ddf59221b472bbac4e8665e036529ba475d9c
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/17/2018
---
# <a name="upgrade-power-bi-report-server"></a>อัปเกรด Power BI Report Server
เรียนรู้วิธีการอัปเกรด Power BI Report Server

 **ดาวน์โหลด** ![ดาวน์โหลด](media/upgrade/download.png "ดาวน์โหลด")

เมื่อต้องการดาวน์โหลด Power BI Report Server และ Power BI Desktop ซึ่งปรับให้เหมาะสมที่สุดกับ Power BI Report Server ไปที่ [การรายงานภายในองค์กรกับ Power BI Report Server](https://powerbi.microsoft.com/report-server/)

## <a name="before-you-begin"></a>ก่อนเริ่มต้น
ก่อนอัปเกรดเซิร์ฟเวอร์รายงาน ขอแนะนำให้คุณดำเนินการขั้นตอนต่อไปนี้เมื่อต้องสำรองข้อมูลเซิร์ฟเวอร์รายงานของคุณ

### <a name="backing-up-the-encryption-keys"></a>การสำรองข้อมูลคีย์การเข้ารหัสลับ
ควรสำรองข้อมูลคีย์การเข้ารหัสลับเมื่อคุณกำหนดค่าการติดตั้งเซิร์ฟเวอร์รายงานเป็นครั้งแรก คุณควรสำรองข้อมูลคีย์ทุกครั้งที่คุณเปลี่ยนแปลงข้อมูลประจำตัวของบัญชีบริการหรือเปลี่ยนชื่อคอมพิวเตอร์ด้วย สำหรับข้อมูลเพิ่มเติม ดู [สำรองข้อมูลและคืนค่าคีย์การเข้ารหัสลับบริการรายงาน](https://docs.microsoft.com/sql/reporting-services/install-windows/ssrs-encryption-keys-back-up-and-restore-encryption-keys)

### <a name="backing-up-the-report-server-databases"></a>สำรองฐานข้อมูลเซิร์ฟเวอร์รายงาน
เนื่องจากเซิร์ฟเวอร์รายงานเป็นเซิร์ฟเวอร์ไม่มีสถานะ ข้อมูลแอปพลิเคชันทั้งหมดจึงถูกเก็บไว้ในฐานข้อมูล **reportserver** และ **reportservertempdb**ที่ทำงานบนอินสแตนซ์ SQL Server Database Engine คุณสามารถสำรองฐานข้อมูล **reportserver** และ **reportservertempdb** ได้โดยใช้หนึ่งในวิธีที่ได้รับการสนับสนุนสำหรับการสำรองฐานข้อมูล SQL Server คำแนะนำที่จะใช้เฉพาะกับฐานข้อมูลเซิร์ฟเวอร์รายงานมีดังนี้:

* ใช้แบบจำลองการกู้คืนแบบเต็มอัตราเพื่อสำรองฐานข้อมูล **reportserver**
* ใช้แบบจำลองการกู้คืนอย่างง่ายเพื่อสำรองฐานข้อมูล **reportservertempdb**
* คุณสามารถใช้กำหนดการสำรองข้อมูลที่แตกต่างกันสำหรับแต่ละฐานข้อมูล เหตุผลเดียวที่ต้องสำรองข้อมูล **reportservertempdb** ก็คือเพื่อหลีกเลี่ยงการสร้างขึ้นใหม่หากฮาร์ดแวร์ล้มเหลว ในกรณีที่ฮาร์ดแวร์ล้มเหลว ไม่จำเป็นต้องกู้คืนข้อมูลใน **reportservertempdb** แต่คุณจำเป็นใช้โครงสร้างตาราง ถ้าคุณทำ **reportservertempdb**หายไป วิธีเดียวที่จะได้คืนมาก็คือ การสร้างฐานข้อมูลเซิร์ฟเวอร์รายงานขึ้นมาไป ถ้าคุณสร้าง **reportservertempdb** ขึ้นมาใหม่ ก็สำคัญว่าจะต้องมีชื่อเดียวกับฐานข้อมูลเซิร์ฟเวอร์รายงานหลัก

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการสำรองและกู้คืนฐานข้อมูลเชิงสัมพันธ์ SQL Server ดู [สำรองข้อมูลและคืนค่าฐานข้อมูล SQL Server](https://docs.microsoft.com/sql/relational-databases/backup-restore/back-up-and-restore-of-sql-server-databases)

### <a name="backing-up-the-configuration-files"></a>การสำรองข้อมูลไฟล์กำหนดค่า
Power BI Report Server จะใช้ไฟลกำหนดค่าเพื่อจัดเก็บการตั้งค่าแอปพลิเคชัน คุณควรสำรองข้อมูลไฟล์เมื่อคุณกำหนดค่าเซิร์ฟเวอร์ก่อนและหลัง จากที่คุณปรับใช้ส่วนขยายใด ๆ แบบกำหนดเองแล้ว ไฟล์ที่จะสำรองข้อมูลประกอบด้วย:

* config.json
* RSHostingService.exe.config
* Rsreportserver.config
* Rssvrpolicy.config
* Reportingservicesservice.exe.config
* Web.config สำหรับแอปพลิเคชัน Report Server ASP.NET
* Machine.config สำหรับ ASP.NET

## <a name="upgrade-the-report-server"></a>การอัปเกรดเซิร์ฟเวอร์รายงาน
การอัปเกรด Power BI Report Server จะเป็นไปอย่างง่ายดาย มีเพียงไม่กี่ขั้นตอนในการติดตั้งไฟล์

1. ค้นหาตำแหน่งที่ตั้งของ PowerBIReportServer.exe และเปิดใช้งานตัวติดตั้ง
2. เลือก **อัปเกรด Power BI Report Server**
   
    ![](media/upgrade/reportserver-upgrade1.png "อัปเกรด Power BI Report Server")
3. อ่านและยอมรับเงื่อนไขและข้อกำหนดสิทธิ์การใช้งาน และจากนั้นเลือก **อัปเกรด**
   
    ![](media/upgrade/reportserver-upgrade-eula.png "ข้อตกลงสิทธิ์การใช้งาน")
4. หลังจากอัปเกรดสำเร็จ คุณสามารถเลือก **กำหนดค่าเซิร์ฟเวอร์รายงาน**เพื่อเปิดใช้ตัวจัดการการกำหนดค่าบริการการรายงาน หรือเลือก **ปิด** เพื่ออกจากตัวติดตั้ง
   
    ![](media/upgrade/reportserver-upgrade-configure.png)

## <a name="upgrade-power-bi-desktop"></a>อัปเกรด Power BI Desktop
หลังจากอัปเกรดเซิร์ฟเวอร์รายงานแล้ว คุณจะต้องตรวจสอบให้แน่ใจว่า ผู้เขียนรายงาน Power BI ใดๆ อัปเกรดเป็น Power BI Desktop เวอร์ชันที่ปรับให้เหมาะสำหรับ Power BI Report Server ที่ตรงกับเซิร์ฟเวอร์

## <a name="next-steps"></a>ขั้นตอนถัดไป
[คู่มือผู้ดูแลระบบ](admin-handbook-overview.md)  
[ติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับ Power BI Report Server](install-powerbi-desktop.md)  
[ตรวจสอบการติดตั้งบริการการรายงาน](https://docs.microsoft.com/sql/reporting-services/install-windows/verify-a-reporting-services-installation)  
[กำหนดค่าบัญชีผู้ใช้บริการเซิร์ฟเวอร์รายงาน](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager)  
[กำหนดค่า URL ของเซิร์ฟเวอร์รายงาน](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager)  
[กำหนดค่าการเชื่อมต่อฐานข้อมูลเซิร์ฟเวอร์รายงาน](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager)  
[เตรียมใช้งานเซิร์ฟเวอร์รายงาน](https://docs.microsoft.com/sql/reporting-services/install-windows/ssrs-encryption-keys-initialize-a-report-server)  
[กำหนดค่าการเชื่อมต่อ SSL ในเซิร์ฟเวอร์รายงาน](https://docs.microsoft.com/sql/reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server)  
[กำหนดค่าบัญชีบริการ windows และสิทธิ์](https://docs.microsoft.com/sql/database-engine/configure-windows/configure-windows-service-accounts-and-permissions)  
[การสนับสนุนเบราว์เซอร์สำหรับ Power BI Report Server](browser-support.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)


---
title: ภาพรวมของการดูแลระบบ เซิร์ฟเวอร์รายงาน Power BI
description: บทความนี้เป็นภาพรวมของการดูแลระบบเซิร์ฟเวอร์รายงาน Power BI ที่ตั้งอยู่ภายในองค์กรสำหรับจัดเก็บและจัดการ รายงาน Power BI, Power BI สำหรับอุปกรณ์เคลื่อนที่ และรายงานที่มีการแบ่งหน้า
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: maghan
ms.openlocfilehash: 1dbca883bc4df2bde743963db7994361616be192
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34721926"
---
# <a name="admin-overview-power-bi-report-server"></a>ภาพรวมของการดูแลระบบ เซิร์ฟเวอร์รายงาน Power BI
บทความนี้เป็นภาพรวมของการดูแลระบบเซิร์ฟเวอร์รายงาน Power BI ที่ตั้งอยู่ภายในองค์กรสำหรับจัดเก็บและจัดการ รายงาน Power BI, Power BI สำหรับอุปกรณ์เคลื่อนที่ และรายงานที่มีการแบ่งหน้า บทความนี้แนะนำแนวคิดของการวางแผน, การปรับใช้ และการจัดการเซิร์ฟเวอร์รายงาน Power BI ของคุณ พร้อมลิงก์ไปยังข้อมูลเพิ่มเติม

![](media/admin-handbook-overview/admin-handbook.png)



## <a name="installing-and-migration"></a>การติดตั้งและการโยกย้าย
คุณต้องติดตั้งเซิร์ฟเวอร์รายงาน Power BI เพื่อเริ่มต้นใช้งาน เรามีบทความที่อธิบายวิธีติดตั้งนี้

ก่อนที่คุณจะเริ่มการติดตั้ง, อัปเกรด หรือโยกย้ายไปยังเซิร์ฟเวอร์รายงาน Power BI ให้ดู[ความต้องการของระบบ](system-requirements.md)สำหรับเซิร์ฟเวอร์รายงาน

### <a name="installing"></a>กำลังติดตั้ง
ถ้าคุณกำลังปรับใช้เซิร์ฟเวอร์รายงาน Power BI ใหม่ ให้ใช้เอกสารต่อไปนี้เพื่อช่วยคุณ 

[ติดตั้ง Power BI Report Server](install-report-server.md)

### <a name="migration"></a>การโยกย้าย
ไม่มีการอัปเกรดแบบแทนที่สำหรับ SQL Server Reporting Services ถ้าคุณมีอินสแตนซ์ของ SQL Server Reporting Services ที่คุณต้องการทำให้เป็นเซิร์ฟเวอร์รายงาน Power BI คุณต้องทำการโยกย้าย คุณอาจต้องทำการโยกย้ายด้วยเหตุผลอื่นเช่นกัน ทบทวนเอกสารการโยกย้ายสำหรับรายละเอียดเพิ่มเติม

[โยกย้ายการติดตั้งเซิร์ฟเวอร์รายงาน](migrate-report-server.md)

## <a name="configuring-your-report-server"></a>กำหนดค่าเซิร์ฟเวอร์รายงานของคุณ
คุณมีหลายตัวเลือกเมื่อทำการกำหนดค่าเซิร์ฟเวอร์รายงานของคุณ คุณจะใช้ SSL หรือไม่ คุณกำลังกำหนดค่าเซิร์ฟเวอร์อีเมลใช่หรือไม่ คุณต้องการรวมเข้ากับบริการ Power BI เพื่อปักหมุดการแสดงภาพหรือไม่

ส่วนใหญ่ของการกำหนดค่าจะเกิดขึ้นภายในตัวจัดการการกำหนดค่าเซิร์ฟเวอร์รายงาน ลองดูเอกสารประกอบ[การจัดการการกำหนดค่า](https://docs.microsoft.com/sql/reporting-services/install-windows/reporting-services-configuration-manager-native-mode)สำหรับรายละเอียดเพิ่มเติม

## <a name="security"></a>ความปลอดภัย
ความปลอดภัยและการป้องกันมีความสำคัญสำหรับทุกองค์กร คุณสามารถเรียนรู้เกี่ยวกับการรับรองความถูกต้อง การอนุญาต บทบาท และสิทธิ์บนเอกสารประกอบด้าน[ความปลอดภัย](https://docs.microsoft.com/sql/reporting-services/security/reporting-services-security-and-protection)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[ติดตั้ง Power BI Report Server](install-report-server.md)  
[ค้นหาคีย์ผลิตภัณฑ์ของเซิร์ฟเวอร์รายงานคุณ](find-product-key.md)  
[ติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับ Power BI Report Server](install-powerbi-desktop.md)  
[ติดตั้งตัวสร้างรายงาน](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[ดาวน์โหลด SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](https://community.powerbi.com/)


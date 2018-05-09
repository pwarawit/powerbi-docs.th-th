---
title: ภาพรวมคู่มือผู้ดูแล เซิร์ฟเวอร์รายงาน Power BI
description: ยินดีต้อนรับสู่คู่มือผู้ดูแลสำหรับเซิร์ฟเวอร์รายงาน Power BI ตำแหน่งที่ตั้งภายในองค์กรสำหรับการจัดเก็บและการจัดการ Power BI อุปกรณ์เคลื่อนที่ และรายงานที่มีการแบ่งหน้าของคุณ
services: powerbi
documentationcenter: ''
author: markingmyname
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 130a4264b2e8c4e511527f34088a580a7787673b
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/30/2018
---
# <a name="administrator-handbook-overview-power-bi-report-server"></a>ภาพรวมคู่มือผู้ดูแล เซิร์ฟเวอร์รายงาน Power BI
ยินดีต้อนรับสู่คู่มือผู้ดูแลสำหรับเซิร์ฟเวอร์รายงาน Power BI ตำแหน่งที่ตั้งภายในองค์กรสำหรับการจัดเก็บและการจัดการ Power BI อุปกรณ์เคลื่อนที่ และรายงานที่มีการแบ่งหน้าของคุณ

![](media/admin-handbook-overview/admin-handbook.png)

คู่มือนี้จะช่วยให้คุณเข้าใจแนวคิดเกี่ยวกับการวางแผน การปรับใช้ และการจัดการเซิร์ฟเวอร์รายงาน Power BI ของคุณ

## <a name="installing-and-migration"></a>การติดตั้งและการโยกย้าย
คุณจะต้องติดตั้งเซิร์ฟเวอร์รายงาน Power BI เพื่อเริ่มใช้งาน เรามีข้อมูลที่จะช่วยให้คุณสามารถจัดการงานนี้

ก่อนที่คุณเริ่มการติดตั้ง อัปเกรด หรือโยกย้ายไปยังเซิร์ฟเวอร์รายงาน Power BI ให้ดู[ความต้องการของระบบ](system-requirements.md)สำหรับเซิร์ฟเวอร์รายงาน

### <a name="installing"></a>กำลังติดตั้ง
ถ้าคุณกำลังปรับใช้เซิร์ฟเวอร์รายงาน Power BI ตัวใหม่ ให้คุณใช้เอกสารต่อไปนี้เพื่อช่วยให้คุณ การเริ่มต้นด่วนพร้อมให้ใช้งานทันที หรือคุณสามารถค้นหาเอกสารการติดตั้งสำหรับรายละเอียดทั้งหมด

* [การเริ่มต้นใช้งานด่วน: ติดตั้งเซิร์ฟเวอร์รายงาน Power BI](quickstart-install-report-server.md)
* [ติดตั้งเซิร์ฟเวอร์รายงาน Power BI](install-report-server.md)

### <a name="migration"></a>การโยกย้าย
ไม่มีการอัปเกรดในสถานที่สำหรับ SQL Server Reporting Services ถ้าคุณมีอินสแตนซ์ของ SQL Server Reporting Services อยู่แล้วที่คุณต้องการทำเซิร์ฟเวอร์รายงาน Power BI คุณจะต้องโยกย้ายอินสแตนซ์ดังกล่าว มีเหตุผลอื่น ๆ ที่คุณอาจต้องการดำเนินการโยกย้ายเช่นกัน ทบทวนเอกสารการโยกย้ายสำหรับรายละเอียดเพิ่มเติม

[โยกย้ายการติดตั้งเซิร์ฟเวอร์รายงาน](migrate-report-server.md)

## <a name="configuring-your-report-server"></a>กำหนดค่าเซิร์ฟเวอร์รายงานของคุณ
คุณมีหลายตัวเลือกเมื่อทำการกำหนดค่าเซิร์ฟเวอร์รายงานของคุณ คุณจะใช้ SSL หรือไม่ คุณกำลังกำหนดค่าเซิร์ฟเวอร์อีเมลใช่หรือไม่ คุณต้องการรวมเข้ากับบริการ Power BI เพื่อปักหมุดการแสดงภาพหรือไม่

ส่วนใหญ่ของการกำหนดค่าจะเกิดขึ้นภายในตัวจัดการการกำหนดค่าเซิร์ฟเวอร์รายงาน ลองดูเอกสารประกอบ[การจัดการการกำหนดค่า](https://docs.microsoft.com/sql/reporting-services/install-windows/reporting-services-configuration-manager-native-mode)สำหรับรายละเอียดเพิ่มเติม

## <a name="security"></a>ความปลอดภัย
ความปลอดภัยและการป้องกันมีความสำคัญสำหรับทุกองค์กร คุณสามารถเรียนรู้เกี่ยวกับการรับรองความถูกต้อง การอนุญาต บทบาท และสิทธิ์บนเอกสารประกอบด้าน[ความปลอดภัย](https://docs.microsoft.com/sql/reporting-services/security/reporting-services-security-and-protection)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[การเริ่มต้นใช้งานด่วน: ติดตั้งเซิร์ฟเวอร์รายงาน Power BI](quickstart-install-report-server.md)  
[วิธีการค้นหาคีย์ผลิตภัณฑ์เซิร์ฟเวอร์รายงานของคุณ](find-product-key.md)  
[ติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI](install-powerbi-desktop.md)  
[ติดตั้งตัวสร้างรายงาน](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[ดาวน์โหลด SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)


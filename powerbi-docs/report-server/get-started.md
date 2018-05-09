---
title: เริ่มต้นใช้งานกับ Power BI Desktop
description: 'ติดตั้งเซิร์ฟเวอร์รายงาน Power BI '
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
ms.date: 3/5/2018
ms.author: maghan
ms.openlocfilehash: 88aa347a5e6feae969cf9b32e0e2177114efc757
ms.sourcegitcommit: ee5d044db99e253c27816e0ea6bdeb9e39a2cf41
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/08/2018
---
# <a name="get-started-with-power-bi-report-server"></a>เริ่มต้นใช้งานกับ Power BI Desktop
สร้าง ปรับใช้ และจัดการ Power BI รายงานระยะไกล และภายในองค์กรกับช่วงของเตรียมพร้อมสำหรับการใช้เครื่องมือและบริการที่มีเซิร์ฟเวอร์รายงาน Power BI

## <a name="create-deploy-and-manage-reports"></a>สร้าง ปรับใช้ และจัดการรายงาน
Power BI Report Server เป็นโซลูชันที่ลูกค้าปรับใช้ภายในองค์กรของตนเองสำหรับการสร้าง เผย แพร่ และจัดการรายงาน จากนั้นส่งมอบให้ผู้ใช้ที่ถูกต้องในแบบต่าง ๆ ว่าที่กำลังดูเอกสารเหล่านั้นในเว็บเบราว์เซอร์ อุปกรณ์เคลื่อนที่ของพวกเขา หรือเป็นอีเมลในของพวกเขาในกล่อง

Power BI Report Server มีชุดของผลิตภัณฑ์:

* เว็บพอร์ทัล ที่คุณสามารถดูได้ในเบราว์เซอร์ที่ทันสมัยต่างๆ คุณสามารถจัดระเบียบ และแสดงรายงานและ Kpi ในพอร์ทัลเว็บ นอกจากนี้คุณยังสามารถเก็บ สมุดงาน Excel ไว้ที่นั่นได้
* รายงาน Power BI สร้างขึ้น ด้วย Power BI Desktop ที่คุณสามารถดูภายในพอร์ทัลเว็บในสภาพแวดล้อมของคุณเอง
* แบ่งรายงานเพื่อให้คุณสามารถสร้างรายงานดูทันสมัย ด้วยเครื่องมือสำหรับการสร้างเหล่านั้น
* อุปกรณ์เคลื่อนที่รายงานที่ มีเค้าโครงแบบตอบสนองที่ปรับมากขึ้นเท่ากับอุปกรณ์อื่น และวิธีการต่าง ๆ ที่คุณเก็บเหล่านั้น

อ่านเพิ่มเติมเกี่ยวกับแต่ละรายการ

### <a name="whats-new-in-power-bi-report-server"></a>ดาวน์โหลด Power BI Report Server
แหล่งข้อมูลเหล่านี้จะทำให้คุณได้ทันคุณลักษณะใหม ๆ ่ใน Power BI Report Server

* [ มีอะไรใหม่ใน Power BI Report Server](whats-new.md)
* [Microsoft Power BI บล็อก](https://powerbi.microsoft.com/blog/)
* [SQL Server Reporting Services ที่บล็อกของทีม](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [YouTube ช่อง Guy in a Cube](https://aka.ms/guyinacube)

## <a name="web-portal"></a>เว็บพอร์ทัล
![](media/get-started/web-portal.png)

ประตูหน้าของเซิร์ฟเวอร์รายงาน Power BI เป็นเว็บพอร์ทัลที่ทันสมัยที่คุณสามารถดูได้ในเบราว์เซอร์ที่สมัยใหม่ต่างๆ คุณสามารถเข้าถึงรายงานและ KPI ของคุณทั้งหมดในพอร์ทัลใหม่ได้

คุณสามารถนำไปใช้แบบกำหนดเองของคุณเอง[แบรนด์](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal)พอร์ทัลเว็บของคุณได้ และคุณสามารถสร้าง Kpi ขวาในพอร์ทัลเว็บ KPIs สามารถแสดงเมตริกซ์ทางธุรกิจที่สำคัญได้อย่างรวดเร็วในเบราว์เซอร์ ดังนั้นคุณจึงไม่จำเป็นต้องเปิดรายงาน

เนื้อหาบนพอร์ทัลเว็บได้รับการจัดระเบียบตามชนิด กล่าวคือ Power BI รายงาน อุปกรณ์เคลื่อนที่รายงาน รายงานไกลและ Kpi รวม ถึงเวิร์กบุ๊ก Excel แชร์ชุดข้อมูล และแชร์แหล่งข้อมูลเพื่อใช้เป็นแบบเอกสารสำเร็จสำหรับรายงานของคุณ คุณสามารถจัดเก็บ และจัดการได้อย่างปลอดภัยที่นี่ ในลำดับชั้นของโฟลเดอร์ดั้งเดิม คุณสามารถแท็กรายการโปรดของคุณ และคุณสามารถจัดการเนื้อหาถ้าคุณมีบทบาทนั้น

และคุณสามารถจัดกำหนดการประมวลผลรายงาน เข้าถึงรายงานตามต้องการ และสมัครใช้งานการเผยแพร่รายงานในพอร์ทัลเว็บใหม่

อ่านเพิ่มเติมเกี่ยวกับการ[พอร์ทัลเว็บ](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode)

## <a name="power-bi-reports"></a>รายงาน Power BI
![](media/get-started/powerbi-reports.png)

รายงาน Power BI เป็นมุมมองแบบหลากหลายมุมมองในชุดข้อมูล มีการแสดงภาพที่แสดงถึงการค้นพบและข้อมูลเชิงลึกที่แตกต่างกันจากชุดข้อมูลนั้น  รายงานสามารถมีการแสดงภาพเดียวหรือมีหน้าที่เต็มไปด้วยการแสดงภาพ ขึ้นอยู่กับบทบาทของงานของคุณ คุณอาจเป็นคนที่สร้างรายงาน และ/หรือคุณอาจเป็นผู้บริโภคหรือรายงานผู้ใช้

รายงานจะขึ้นอยู่กับชุดข้อมูลเดียว แสดงภาพในรายงานแต่ละหมายถึง nugget ของข้อมูล และการแสดงภาพจะไม่คงที่ คุณสามารถเพิ่ม และลบข้อมูล เปลี่ยนประเภทการแสดงภาพ และใช้ตัวกรองและตัวแบ่งส่วนข้อมูล ตามที่คุณเจาะลึกข้อมูลเพื่อค้นหาข้อมูลเชิงลึกและค้นหาคำตอบ รายงานเป็นแบบสามารถโต้ตอบได้สูง และกำหนดเองได้สูง และการแสดงภาพจะอัปเดตเมื่อมีการเปลี่ยนแปลงข้อมูลพื้นฐาน เหมือนกับแดชบอร์ดแต่มีประสิทธิภาพมากกว่า

## <a name="paginated-reports"></a>รายงานแบบแบ่งหน้า
![](media/get-started/paginated-reports.png)

รายงานไกลคือ รายงานที่เอกสารลักษณะไกล ที่ข้อมูลเพิ่มเติมคุณมี แถวเพิ่มเติมในตาราง และรายงานจะมีหน้าเพิ่มเติม ที่เหมาะสมสำหรับการสร้างเค้า โครงถาวร พิกเซลสมบูรณ์แบบเอกสารที่ปรับให้เหมาะสมสำหรับการพิมพ์ เช่นไฟล์ PDF และ Word

คุณสร้างรายงานแบบแบ่งหน้าเหล่านี้ด้วย[ตัวสร้างรายงาน](https://docs.microsoft.com/sql/reporting-services/report-builder/report-builder-in-sql-server-2016)หรือ ตัวออกแบบรายงาน ใน[SQL Server Data Tools (SSDT)](https://docs.microsoft.com/sql/reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt)

## <a name="report-server-programming-features"></a>ฟีเจอร์โปรแกรม Report Server
ใช้ประโยชน์จากคุณลักษณะการเขียนโปรแกรมพอร์ตเซิร์ฟเวอร์ Power BI เพื่อให้คุณสามารถขยาย และกำหนดเองของคุณฟังก์ชันการรายงาน กับ API เพื่อรวม หรือขยายข้อมูลและรายงานที่ประมวลผลในแอปพลิเคชันแบบกำหนดเอง

เพิ่มเติม[เอกสารของนักพัฒนาเซิร์ฟเวอร์รายงาน](https://docs.microsoft.com/sql/reporting-services/reporting-services-developer-documentation)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[คู่มือผู้ใช้](user-handbook-overview.md)  
[คู่มือผู้ดูแลระบบ](admin-handbook-overview.md)  
[การเริ่มต้นใช้งานด่วน: ติดตั้ง Power BI Report Server](quickstart-install-report-server.md)  
[ติดตั้งตัวสร้างรายงาน](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[ดาวน์โหลด SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)



---
title: ภาพรวมคู่มือสำหรับนักพัฒนา เซิร์ฟเวอร์รายงาน Power BI
description: ยินดีต้อนรับสู่คู่มือสำหรับนักพัฒนา สำหรับเซิร์ฟเวอร์รายงาน Power BI ซึ่งใช้จัดเก็บ และจัดการรายงาน Power BI, รายงานบนอุปกรณ์เคลื่อนที่ และรายงานที่จัดรูปหน้าแล้วของคุณภายในองค์กร
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 11/01/2017
ms.openlocfilehash: e981da28a70490d14bca2fa026f6428020d10ae7
ms.sourcegitcommit: e9c45d6d983e8cd4cb5af938f838968db35be0ee
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/05/2019
ms.locfileid: "57327906"
---
# <a name="developer-handbook-overview-power-bi-report-server"></a>ภาพรวมคู่มือสำหรับนักพัฒนา เซิร์ฟเวอร์รายงาน Power BI

ยินดีต้อนรับสู่คู่มือสำหรับนักพัฒนา สำหรับเซิร์ฟเวอร์รายงาน Power BI ซึ่งใช้จัดเก็บ และจัดการรายงาน Power BI, รายงานบนอุปกรณ์เคลื่อนที่ และรายงานที่จัดรูปหน้าแล้วของคุณภายในองค์กร

![คู่มือสำหรับผู้ดูแลระบบ](media/developer-handbook-overview/admin-handbook.png)

คู่มือนี้แสดงให้เห็นตัวเลือกที่คุณมีในฐานะนักพัฒนา เพื่อทำงานกับ เซิร์ฟเวอร์รายงาน Power BI

## <a name="embedding"></a>การฝังตัว

สำหรับรายงานใด ๆ ภายในเซิร์ฟเวอร์รายงาน Power BI คุณสามารถฝังตัวภายใน iFrame โดยการเพิ่มพารามิเตอร์ querystring `?rs:Embed=true` เข้าไปใน URL เทคนิคนี้สามารทำงานร่วมกับรายงาน Power BI เช่นเดียวกับรายงานชนิดอื่น ๆ

### <a name="report-viewer-control"></a>ตัวควบคุม Report Viewer

สำหรับรายงานที่มีการแบ่งหน้า คุณสามารถใช้ประโยชน์จากตัวควบคุม Report Viewer ด้วยเทคนิคนี้ คุณสามารถใส่ตัวควบคุมภายใน .NET Windows หรือแอปพลิเคชันเว็บ สำหรับข้อมูลเพิ่มเติม ดู[เริ่มต้นใช้งานตัวควบคุม Report Viewer](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started)

## <a name="apis"></a>API

คุณมีหลายตัวเลือกสำหรับ API เพื่อโต้ตอบกับเซิร์ฟเวอร์รายงาน Power BI ซึ่งรวมไปถึงรายการต่อไปนี้

* [REST API](rest-api.md)
* [การเข้าถึง URL](https://docs.microsoft.com/sql/reporting-services/url-access-ssrs)
* [ผู้ให้บริการ WMI](https://docs.microsoft.com/sql/reporting-services/wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs)

คุณยังสามารถใช้ [โปรแกรมอรรถประโยชน์ของ PowerShell](https://github.com/Microsoft/ReportingServicesTools) ที่เป็นโอเพนซอร์ส เพื่อจัดการเซิร์ฟเวอร์รายงานของคุณได้

> [!NOTE]
> โปรแกรมอรรถประโยชน์ของ PowerShell ในขณะนี้ยังไม่สนับสนุนไฟล์ Power BI Desktop (.pbix)

## <a name="custom-extensions"></a>ส่วนขยายแบบกำหนดเอง

ไลบรารีส่วนขยายคือ ชุดของคลาส อินเทอร์เฟซ และชนิดของค่า ที่มีอยู่ในเซิร์ฟเวอร์รายงาน Power BI ไลบรารีนี้ให้การเข้าถึงฟังก์ชันการทำงานของระบบ และถูกออกแบบมาเพื่อให้เป็นพื้นฐานที่ แอปพลิเคชัน Microsoft .NET Framework สามารถใช้ขยายคอมโพเนนต์ของ เซิร์ฟเวอร์รายงาน Power BI

มีส่วนขยายหลายชนิดที่คุณสามารถสร้างได้

* ส่วนขยายการประมวลผลข้อมูล
* ส่วนขยายการจัดส่ง
* ส่วนขยายการแสดงผลรายงานที่มีการแบ่งหน้า
* ส่วนขยายการรักษาความปลอดภัย

เมื่อต้องการเรียนรู้เพิ่มเติม ดู[ไลบรารีส่วนขยาย](https://docs.microsoft.com/sql/reporting-services/extensions/reporting-services-extension-library)

## <a name="next-steps"></a>ขั้นตอนถัดไป

[เริ่มต้นใช้งานตัวควบคุม Report Viewer](https://docs.microsoft.com/sql/reporting-services/application-integration/integrating-reporting-services-using-reportviewer-controls-get-started)  
[สร้างแอปพลิเคชันโดยใช้ บริการเว็บ และ .NET Framework](https://docs.microsoft.com/sql/reporting-services/report-server-web-service/net-framework/building-applications-using-the-web-service-and-the-net-framework)  
[การเข้าถึง URL](https://docs.microsoft.com/sql/reporting-services/url-access-ssrs)  
[ไลบรารีส่วนขยาย](https://docs.microsoft.com/sql/reporting-services/extensions/reporting-services-extension-library)  
[ผู้ให้บริการ WMI](https://docs.microsoft.com/sql/reporting-services/wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs)

คำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
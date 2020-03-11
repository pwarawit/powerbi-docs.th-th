---
title: แหล่งข้อมูลรายงานที่มีการแบ่งหน้าในเซิร์ฟเวอร์รายงาน Power BI
description: เรียนรู้เกี่ยวกับแหล่งข้อมูลที่รายงานที่มีการแบ่งหน้า (.rdl) สามารถเชื่อมต่อกับเซิร์ฟเวอร์รายงาน Power BI
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: maggies
ms.openlocfilehash: 7cb5772e6ccdc1e4036d70f65a3a28210a4f6df1
ms.sourcegitcommit: d55d3089fcb3e78930326975957c9940becf2e76
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/04/2020
ms.locfileid: "78260726"
---
# <a name="paginated-report-data-sources--in-power-bi-report-server"></a>แหล่งข้อมูลรายงานที่มีการแบ่งหน้าในเซิร์ฟเวอร์รายงาน Power BI
รายงานที่มีการแบ่งหน้าของ Reporting Services ในเซิร์ฟเวอร์รายงาน Power BI สนับสนุนแหล่งข้อมูลเดียวกันกับที่ได้รับการสนับสนุนใน SQL Server Reporting Services ดูรายการ [แหล่งข้อมูลที่สนับสนุนโดย Reporting Services](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs)

## <a name="connect-to-oracle-data-sources-with-useinstalleduiculture"></a>เชื่อมต่อกับแหล่งข้อมูล Oracle ด้วย UseInstalledUICulture

ในการเชื่อมต่อกับแหล่งข้อมูล Oracle เซิร์ฟเวอร์รายงาน Power BI จะใช้ผู้ให้บริการข้อมูล Oracle สำหรับ .NET (ODP.NET) ซึ่งเป็นการวินิจฉัย NLS

ตามค่าเริ่มต้น เซิร์ฟเวอร์รายงานจะใช้วัฒนธรรม UI ของไคลเอ็นต์แรกเพื่อโหลด ODP.NET  ด้วยเหตุนี้ การเชื่อมต่อในภายหลังทั้งหมดไปยัง Oracle จากเซิร์ฟเวอร์รายงานจะอยู่ในวัฒนธรรม UI เริ่มต้นจนกว่าจะเริ่มบริการใหม่  วิธีการนี้อาจทำให้เกิดปัญหาในการแสดงรายงานเนื่องจากไม่ตรงกันในการจัดรูปแบบวัฒนธรรม UI

เพื่อเสนอการใช้งานที่ดีขึ้นในเซิร์ฟเวอร์รายงาน Power BI เราได้แนะนำการตั้งค่าการกำหนดค่าชื่อ UseInstalledUICulture เมื่อ UseInstalledUICulture ถูกตั้งค่าเป็นจริง เซิร์ฟเวอร์รายงานจะโหลด ODP.NET ในวัฒนธรรม UI ของเซิร์ฟเวอร์แทนที่จะเป็นวัฒนธรรมของไคลเอ็นต์แรก
การตั้งค่านี้พร้อมใช้งานในเซิร์ฟเวอร์รายงาน Power BI เริ่มต้นด้วยการเผยแพร่บริการในเดือนกุมภาพันธ์

หากต้องการเปิดใช้งานฟีเจอร์ ให้ปรับเปลี่ยนไฟล์ rsreportserver.config ของรายการส่วนขยาย ORACLE เช่นเดียวกันกับด้านล่าง
```xml
<Extension Name="ORACLE" Type="Microsoft.ReportingServices.DataExtensions.OracleClientConnectionWrapper,Microsoft.ReportingServices.DataExtensions">
    <Configuration>
        <UseInstalledUICulture>true</UseInstalledUICulture>
    </Configuration>
</Extension>
```

## <a name="next-steps"></a>ขั้นตอนถัดไป
เมื่อคุณได้เชื่อมต่อกับแหล่งข้อมูลของคุณ [ให้สร้างรายงานที่มีการแบ่งหน้า](quickstart-create-paginated-report.md)  


มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)

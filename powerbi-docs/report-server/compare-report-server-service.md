---
title: เปรียบเทียบเซิร์ฟเวอร์รายงาน Power BI และบริการของ Power BI
description: บทความนี้เปรียบเทียบคุณลักษณะของเซิร์ฟเวอร์รายงาน Power BI และบริการของ Power BI
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.date: 05/07/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-report-server
manager: kfile
ms.custom: mvc
ms.openlocfilehash: c47722fda28fc45289858f082a0838f583b53dbb
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/26/2018
ms.locfileid: "34296802"
---
# <a name="comparing-power-bi-report-server-and-the-power-bi-service"></a>เปรียบเทียบเซิร์ฟเวอร์รายงาน Power BI และบริการของ Power BI

เซิร์ฟเวอร์รายงาน Power BI และบริการของ Power BI มีความคล้ายคลึงกันมาก และมีความแตกต่างที่สำคัญบางเรื่อง ตารางนี้จะอธิบายจุดที่เหมือนกัน และจุดที่แตกต่าง

| คุณลักษณะ | เซิร์ฟเวอร์รายงาน Power BI | บริการ Power BI | บันทึกย่อ
|---------|---------|---------|---------|
| การปรับใช้ | ภายในองค์กร หรือคลาวด์ที่โฮสต์ | ระบบคลาวด์ | สามารถปรับใช้เซิร์ฟเวอร์รายงาน Power BI ใน Azure VMs (คลาวด์ที่โฮสต์) ถ้าได้สิทธิ์การใช้งานผ่านทาง Power BI Premium
| ข้อมูลต้นทาง | ระบบคลาวด์ และ/หรือ ภายในองค์กร | ระบบคลาวด์ และ/หรือ ภายในองค์กร |  
| สิทธิ์การใช้งาน | Power BI Premium หรือ SQL Server EE with SA | Power BI Pro และ/หรือ Power BI Premium |  
| วงจรชีวิต | นโยบายวงจรชีวิตสมัยใหม่ | บริการที่มีการจัดการอย่างสมบูรณ์ |  
| รอบการเผยแพร่ | หนึ่งครั้งทุก ๆ 4 เดือน | เดือนละครั้ง | คุณลักษณะล่าสุดและการแก้ไข มาที่บริการของ Power BI ก่อน ความสามารถหลักส่วนใหญ่ มาถึงเซิร์ฟเวอร์รายงาน Power BI ในการเผยแพร่ไม่กี่ครั้งถัดไป บางคุณลักษณะมีไว้สำหรับบริการของ Power BI เท่านั้น
| สร้างรายงาน Power BI ใน Power BI Desktop | ใช่ | ใช่ |  
| สร้างรายงาน Power BI ในเบราว์เซอร์ | ไม่ใช่ | ใช่ |  
| จำเป็นต้องใช้เกตเวย์ | ไม่ใช่ | ใช่สำหรับแหล่งข้อมูลภายในองค์กร |  
| การสตรีมในเวลาจริง | ไม่ใช่ | ใช่ | [การสตรีมในเวลาจริงใน Power BI](../service-real-time-streaming.md)
| แดชบอร์ด | ไม่ใช่ | ใช่ | [แดชบอร์ดในบริการของ Power BI](../service-dashboards.md) 
| กลุ่มการแจกจ่ายรายงานโดยใช้แอป | ไม่ใช่ | ใช่ | [สร้างและเผยแพร่แอปที่มีแดชบอร์ดและรายงาน](../service-create-distribute-apps.md) 
| ชุดเนื้อหา | ไม่ใช่ | ใช่ | [ชุดเนื้อหาระดับองค์กร: บทนำ](../service-organizational-content-pack-introduction.md) 
| เชื่อมต่อกับบริการต่าง ๆ เช่น Salesforce | ไม่ใช่ | ใช่ | [เชื่อมต่อกับบริการที่คุณใช้](../service-connect-to-services.md)ด้วยบริการของ Power BI
| ถามตอบ | ไม่ใช่ | ใช่ | [ถามตอบในบริการของ Power BI และ Power BI Desktop](../power-bi-q-and-a.md) 
| ข้อมูลเชิงลึกด่วน | ไม่ใช่ | ใช่ | [สร้างข้อมูลเชิงลึกโดยอัตโนมัติด้วย Power BI](../service-insights.md) 
| วิเคราะห์ใน Excel | ไม่ใช่ | ใช่ | [วิเคราะห์ใน Excel](../service-analyze-in-excel.md) 
| รายงานที่มีการแบ่งหน้า | ใช่ | ไม่ใช่ | รายงานที่มีการแบ่งหน้า ยังไม่มีในบริการของ Power BI แต่คุณสามารถ[ปักหมุดรายการในรายงานที่มีการแบ่งหน้า ไปยังแดชบอร์ด Power BI](https://docs.microsoft.com/sql/reporting-services/pin-reporting-services-items-to-power-bi-dashboards)
| แอป Power BI สำหรับอุปกรณ์เคลื่อนที่ | ใช่ | ใช่ | [ภาพรวมแอป Power BI สำหรับอุปกรณ์เคลื่อนที่](../mobile-apps-for-mobile-devices.md) 
| แผนที่ ArcGIS | ไม่ใช่ | ใช่ | [แผนที่ ArcGIS ในบริการของ Power BI และ Power BI Desktop ที่ให้บริการโดย Esri](../power-bi-visualization-arcgis.md)
| การสมัครสมาชิกอีเมลสำหรับรายงาน Power BI | ไม่ใช่ | ใช่ | [การสมัครสมาชิกไปยังรายงานหรือแดชบอร์ด](../service-report-subscribe.md)ในบริการของ Power BI 
| การสมัครสมาชิกอีเมลสำหรับรายงานที่มีการแบ่งหน้า | ใช่ | ไม่ใช่ | [การจัดส่งอีเมลใน Reporting Services](https://docs.microsoft.com/sql/reporting-services/subscriptions/e-mail-delivery-in-reporting-services)  
| การแจ้งเตือนข้อมูล | ไม่ใช่ | ใช่ | [การแจ้งเตือนข้อมูล](../service-set-data-alerts.md)ในบริการของ Power BI
| รักษาความปลอดภัยตามระดับแถว | ผ่านทางแหล่งข้อมูลในโหมด DirectQuery เท่านั้น | มีทั้งใน DirectQuery (แหล่งข้อมูล) และโหมดการนำเข้า | [รักษาความปลอดภัยระดับแถว (RLS)](../service-admin-rls.md) ด้วย Power BI 
| โหมดเต็มหน้าจอ | ไม่ใช่ | ใช่ | [โหมดเต็มหน้าจอ](../service-fullscreen-mode.md)ในบริการของ Power BI 
| ทำงานร่วมกับ Office 365 ขั้นสูง | ไม่ใช่ | ใช่ | [ทำงานร่วมกันในพื้นที่ทำงานแอป](../service-collaborate-power-bi-workspace.md)ด้วย Office 365 
| วิชวล R | ไม่ใช่ | ใช่ | [สร้างวิชวล R](../service-r-visuals.md) ในบริการของ Power BI  
| แสดงตัวอย่างฟีเจอร์ | ไม่ใช่ | ใช่ | [ยินยอมเข้าร่วม สำหรับคุณลักษณะตัวอย่างในบริการของ Power BI](../service-preview-features.md) 
| ภาพแบบกำหนดเอง | ใช่ | ใช่ | [วิชวลแบบกำหนดเองใน Power BI](../power-bi-custom-visuals.md) 
| Power BI Desktop | เวอร์ชันที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน มีให้ดาวน์โหลดสำหรับเซิร์ฟเวอร์รายงาน | เวอร์ชันที่ปรับให้เหมาะสมสำหรับบริการของ Power BI มีที่ Windows Store | [Power BI Desktop สำหรับเซิร์ฟเวอร์รายงาน](https://powerbi.microsoft.com/report-server/) <br><br> [Power BI Desktop สำหรับบริการของ Power BI](http://aka.ms/pbidesktopstore)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[ติดตั้ง Power BI Report Server](install-report-server.md)  




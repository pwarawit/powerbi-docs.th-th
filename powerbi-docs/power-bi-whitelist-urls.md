---
title: URL ของ Power BI
description: บทความนี้อธิบายถึงจุดสิ้นสุดที่ควรเข้าถึงได้สำหรับลูกค้าที่ใช้ Power BI
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/22/2018
ms.openlocfilehash: 7b57e0d5e303f2b342e2d7750741717b178a8f4e
ms.sourcegitcommit: f9dd6098ca57d4d6cad34284126d4e58eab1c92c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/29/2018
ms.locfileid: "50222116"
---
# <a name="power-bi-urls"></a>URL ของ Power BI

**บริการออนไลน์ของ Power BI**หรือที่เรียกว่า แอปพลิเคชัน Power BI SaaS (ซอฟต์แวร์ที่เป็นบริการ) จำเป็นต้องมีการเชื่อมต่อกับอินเทอร์เน็ต จุดสิ้นสุดด้านล่างควรสามารถเข้าถึงได้สำหรับลูกค้าที่ใช้บริการออนไลน์ของ Power BI

เมื่อต้องใช้บริการออนไลน์ของ Power BI คุณต้องมีการเข้าถึงเพื่อเชื่อมต่อกับจุดสิ้นสุดที่ถูกทำเครื่องหมายว่า**จำเป็น**ในตารางด้านล่าง และจุดสิ้นสุดใด ๆ ที่ถูกทำเครื่องหมายว่า**จำเป็น**บนไซต์ที่เชื่อมโยง ถ้าลิงก์ไปยังไซต์ภายนอกอ้างอิงไปยังส่วนที่เฉพาะเจาะจง คุณเพียงแค่ต้องการตรวจทานจุดสิ้นสุดในส่วนนั้น

จุดสิ้นสุดที่ทำเครื่องหมาย**ตัวเลือก**อาจทำเป็น**รายการอนุญาต**สำหรับฟังก์ชันการใช้งานเฉพาะที่จะทำงาน

บริการออนไลน์ของ Power BI ต้องการเพียง TCP พอร์ต 443 ที่จะถูกเปิดไว้สำหรับจุดสิ้นสุดที่แสดงรายการไว้

อักขระตัวแทน (*) แสดงระดับทั้งหมดภายใต้โดเมนราก และเราใช้ N/A เมื่อข้อมูลไม่พร้อมใช้งาน คอลัมน์**ปลายทาง**คือรายการพร้อม FQDN/โดเมน และลิงก์ไปยังไซต์ภายนอก ซึ่งประกอบด้วยจุดสิ้นสุดข้อมูลเพิ่มเติม

>[!Important]
>ข้อมูลในตารางด้านล่างไม่แสดง**สหรัฐอเมริกา ระบบคลาวด์**, **ระบบคลาวด์ประเทศเยอรมัน**หรือ**ระบบคลาวด์ประเทศจีน**

## <a name="authentication"></a>การรับรองความถูกต้อง

Power BI ขึ้นอยู่กับจุดสิ้นสุดที่จำเป็นในส่วนการรับรองความถูกต้องและข้อมูลประจำตัวของ Office 365 เมื่อต้องใช้ Power BI คุณต้องสามารถเชื่อมต่อกับจุดสิ้นสุดในไซต์ที่เชื่อมโยงด้านล่าง

| แถว | วัตถุประสงค์ | ปลายทาง | พอร์ต |
| --- | --- | --- | --- |
| 1 | **จำเป็นต้องมี้:** การรับรองความถูกต้องและข้อมูลประจำตัว | ดูเอกสารประกอบ Office 365 สำหรับ[Office Online และ Url ทั่วไป](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online)  | N/A |

## <a name="general-site-usage"></a>การใช้งานไซต์ทั่วไป

สำหรับการใช้ทั่วไปของ Power BI คุณต้องสามารถเชื่อมต่อกับจุดสิ้นสุดในตารางและไซต์ที่เชื่อมโยงด้านล่าง

| แถว | วัตถุประสงค์ | ปลายทาง | พอร์ต |
| --- | --- | --- | --- |
| 1 | **จำเป็นต้องมี:** Backend APIs | *.analysis.windows.net | TCP 443 |
| 2 | **จำเป็นต้องมี:** การรวม Office 365 | ดูเอกสารประกอบ Office 365 สำหรับ[Office Online และ Url ทั่วไป](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) | N/A |
| 3 | **จำเป็นต้องมี:** พอร์ทัล | app.powerbi.com | TCP 443 |
| 4 | **จำเป็นต้องมี:** การบริการการวัดและส่งข้อมูลทางไกล | dc.services.visualstudio.com | TCP 443 |
| 5 | **ตัวเลือก:** ข้อความที่ให้ข้อมูล | dynmsg.modpim.com | TCP 443 |
| 6 | **ตัวเลือก:** แบบสำรวจ NPS | nps.onyx.azure.net | TCP 443 |
| | | |

## <a name="administration"></a>การดูแลระบบ

การใช้ฟังก์ชันการบริหารระบบภายใน Power BI คุณต้องสามารถเชื่อมต่อกับจุดสิ้นสุดในไซต์เชื่อมโยงด้านล่าง

| แถว | วัตถุประสงค์ | ปลายทาง | พอร์ต |
| --- | --- | --- | --- |
| 1 | **จำเป็นต้องมี:** สำหรับการจัดการผู้ใช้ และการดูบันทึกการตรวจสอบ | ดูเอกสารประกอบ Office 365 สำหรับ[Office Online และ Url ทั่วไป](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) | N/A |
| | | |

## <a name="getting-data"></a>การรับข้อมูล

เพื่อรับข้อมูลจากแหล่งข้อมูลที่เฉพาะเจาะจง เช่น OneDrive คุณต้องสามารถเชื่อมต่อกับจุดสิ้นสุดในตารางด้านล่าง การเข้าถึงโดเมนอินเทอร์เน็ตและ URL เพิ่มเติมอาจจำเป็นสำหรับแหล่งข้อมูลเฉพาะที่ใช้ภายในองค์กรของคุณ

| แถว | วัตถุประสงค์ | ปลายทาง | พอร์ต |
| --- | --- | --- | --- |
| 1 | **จำเป็นต้องมี:** AppSource (แอปภายในหรือภายนอกใน Power BI) | appsource.microsoft.com </br> *.s microsoft.com  | TCP 443 |
| 2 | **จำเป็น:** ลงชื่อเข้าใช้และรับข้อมูลสำหรับแพคเกจเนื้อหา | * github.com  | TCP 443 |
| 3 | **ตัวเลือก:** นำเข้าไฟล์จาก OneDrive ส่วนบุคคล | ดู[URL และพอร์ตที่จำเป็นสำหรับไซต์ OneDrive](https://docs.microsoft.com/onedrive/required-urls-and-ports) | N/A |
| 4 | **ตัวเลือก:** Power BI ในวิดีโอบทช่วยสอน 60 วินาที | *.doubleclick.net </br> *.ggpht.com </br> *.google.com </br> *.googlevideo.com </br> *.youtube.com </br> *.ytimg.com </br> fonts.gstatic.com | TCP 443 |
| 5 | **ตัวเลือก:** แหล่งข้อมูลการสตรีม PubNub | ดู[เอกสาร PubNub](https://support.pubnub.com/support/solutions/articles/14000043522) | N/A |
| | | |

## <a name="dashboard-and-report-integration"></a>การรวมแดชบอร์ดและรายงาน

Power BI ขึ้นอยู่กับจุดสิ้นสุดบางอย่างเพื่อให้สามารถสนับสนุนแดชบอร์ดและรายงานของคุณ คุณต้องสามารถเชื่อมต่อกับจุดสิ้นสุดในตารางและไซต์ที่เชื่อมโยงด้านล่าง

| แถว | วัตถุประสงค์ | ปลายทาง | พอร์ต |
| --- | --- | --- | --- |
| 1 | **จำเป็นต้องมี:** การรวม Excel | ดูเอกสารประกอบ Office 365 สำหรับ[Office Online และ Url ทั่วไป](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) | N/A |
| | | |

## <a name="custom-visuals"></a>ภาพแบบกำหนดเอง

Power BI ขึ้นอยู่กับจุดสิ้นสุดบางอย่างเพื่อให้สามารถดู และเข้าถึงวิชวลแบบกำหนดเอง คุณต้องสามารถเชื่อมต่อกับจุดสิ้นสุดในตารางและไซต์ที่เชื่อมโยงด้านล่าง

| แถว | วัตถุประสงค์ | ปลายทาง | พอร์ต |
| --- | --- | --- | --- |
| 1 | **จำเป็น:** นำเข้าวิชวลแบบกำหนดเองจากอินเทอร์เฟซ Marketplace หรือจากไฟล์ | *.azureedge.net </br> *.blob.core.windows.net </br> store.office.com | TCP 443 |
| 2 | **ตัวเลือก:** Bing Maps | bing.com </br> platform.bing.com </br> *.dynamic.tiles.virtualearth.net </br> *.virtualearth.net | TCP 443 |
| 3 | **ตัวเลือก:** PowerApps | ดู[ส่วนบริการที่จะเป็น](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config#required-services)จากไซต์ความต้องการของระบบ PowerApps | N/A |
| 4 | **ตัวเลือก:** Visio | ดูเอกสารประกอบสำหรับ Office 365 [Office Online และ Url ทั่วไป ](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online)ตลอดจน [SharePoint Online และ OneDrive for Business](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#sharepoint-online-and-onedrive-for-business) | N/A |
| | | |

## <a name="related-external-sites"></a>เว็บไซต์ภายนอกที่เกี่ยวข้อง

Power BI ลิงก์ไปยังเว็บไซต์อื่นที่เกี่ยวข้อง เว็บไซต์เหล่านี้ประกอบรวมด้วยเอกสารประกอบ การสนับสนุน คำขอคุณลักษณะใหม่ และอื่น ๆ เว็บไซต์เหล่านี้จะไม่ส่งผลกระทบต่อการทำงานของ Power BI ดังนั้นจึงสามารถเลือกที่จะเก็บไว้ในรายการอนุญาตพิเศษหากต้องการ

| แถว | วัตถุประสงค์ | ปลายทาง | พอร์ต |
| --- | --- | --- | --- |
| 1 | **ตัวเลือก:** เว็บไซต์ชุมชน | community.powerbi.com </br> oxcrx34285.i.lithium.com | TCP 443 |
| 2 | **ตัวเลือก:** เว็บไซต์เอกสารประกอบ | docs.microsoft.com </br> img-prod-cms-rt-microsoft-com.akamaized.net </br> statics-uhf-eas.akamaized.net </br> cdnssl.clicktale.neting-district.clicktale.net | TCP 443 |
| 3 | **ตัวเลือก:** เว็บไซต์ดาวน์โหลด (สำหรับ Power BI Desktop และอื่น ๆ) | download.microsoft.com | TCP 443 |
| 4 | **ตัวเลือก:** การเปลี่ยนเส้นทางภายนอก | aka.ms </br> go.microsoft.com | TCP 443 |
| 5 | **ตัวเลือก:** เว็บไซต์สำหรับคำติชมแนวคิด| ideas.powerbi.com </br> powerbi.uservoice.com | TCP 443 |
| 6 | **ตัวเลือก:** เว็บไซต์ Power BI - หน้าเว็บไซต์แรก เรียนรู้ลิงก์เพิ่มเติม ไซต์สนับสนุน ลิงก์ดาวน์โหลด พื้นที่นำเสนอคู่ค้า เป็นต้น | powerbi.microsoft.com | TCP 443 |
| 7 | **ตัวเลือก:** ศูนย์นักพัฒนา Power BI | dev.powerbi.com | TCP 443 |
| 8 | **ตัวเลือก:** เว็บไซต์สนับสนุน | support.powerbi.com </br> s3.amazonaws.com </br> *.olark.com </br> logx.optimizely.com </br> mscom.demdex.net </br> tags.tiqcdn.com | TCP 443 |
| | | |
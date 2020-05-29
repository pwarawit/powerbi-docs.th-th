---
title: Power BI Url สำหรับอนุญาตพิเศษ
description: บทความนี้แสดงรายการจุดสิ้นสุด URL และพอร์ตเพื่อให้ปลอดภัยสำหรับการเชื่อมต่อไปยัง Power BI
author: kfollis
ms.author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/29/2020
ms.custom: seodec18
ms.openlocfilehash: f74bfb92508564a01422729eefc251acc124baea
ms.sourcegitcommit: 250242fd6346b60b0eda7a314944363c0bacaca8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/20/2020
ms.locfileid: "83692734"
---
# <a name="power-bi-urls-for-whitelisting"></a>Power BI Url สำหรับอนุญาตพิเศษ
[//]: # "suparnap, miwehnia เป็นผู้ติดต่อสำหรับการดูแลรายการนี้"

**บริการออนไลน์ของ Power BI**หรือที่เรียกว่า แอปพลิเคชัน Power BI SaaS (ซอฟต์แวร์ที่เป็นบริการ) จำเป็นต้องมีการเชื่อมต่อกับอินเทอร์เน็ต จุดสิ้นสุดด้านล่างควรสามารถเข้าถึงได้สำหรับลูกค้าที่ใช้บริการออนไลน์ของ Power BI

เมื่อต้องใช้บริการออนไลน์ของ Power BI คุณต้องสามารถเชื่อมต่อกับจุดสิ้นสุดที่ถูกทำเครื่องหมายว่า**จำเป็น** ในตารางด้านล่าง และจุดสิ้นสุดใด ๆ ที่ถูกทำเครื่องหมายว่า**จำเป็น** บนไซต์ที่เชื่อมโยง ถ้าลิงก์ไปยังไซต์ภายนอกอ้างอิงไปยังส่วนที่เฉพาะเจาะจง คุณเพียงแค่ต้องการตรวจทานจุดสิ้นสุดในส่วนนั้น

จุดสิ้นสุดที่ทำเครื่องหมาย**ตัวเลือก**อาจทำเป็น**รายการอนุญาต**สำหรับฟังก์ชันการใช้งานเฉพาะที่จะทำงาน

บริการออนไลน์ของ Power BI ต้องการเพียง TCP พอร์ต 443 ที่จะถูกเปิดไว้สำหรับจุดสิ้นสุดที่แสดงรายการไว้

อักขระตัวแทน (*) แสดงระดับทั้งหมดภายใต้โดเมนราก และเราใช้ N/A เมื่อข้อมูลไม่พร้อมใช้งาน คอลัมน์**ปลายทาง**คือรายการพร้อม FQDN/โดเมน และลิงก์ไปยังไซต์ภายนอก ซึ่งประกอบด้วยจุดสิ้นสุดข้อมูลเพิ่มเติม

>[!Important]
>ข้อมูลในตารางด้านล่างไม่แสดง**สหรัฐอเมริกา ระบบคลาวด์**, **ระบบคลาวด์ประเทศเยอรมัน**หรือ**ระบบคลาวด์ประเทศจีน**

## <a name="authentication"></a>การรับรองความถูกต้อง

Power BI ขึ้นอยู่กับตำแหน่งข้อมูลที่จำเป็นในส่วนการรับรองความถูกต้องและข้อมูลประจำตัวของ Microsoft 365 เมื่อต้องใช้ Power BI คุณต้องสามารถเชื่อมต่อกับจุดสิ้นสุดในไซต์ที่เชื่อมโยงด้านล่าง

| แถว | วัตถุประสงค์ | ปลายทาง | พอร์ต |
| --- | --- | --- | --- |
| 1 | **จำเป็นต้องมี:** การรับรองความถูกต้องและข้อมูลประจำตัว | ดูเอกสารประกอบสำหรับ [Microsoft 365 ทั่วไปและ URL ของ Office Online](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online)  | N/A |

## <a name="general-site-usage"></a>การใช้งานไซต์ทั่วไป

สำหรับการใช้ทั่วไปของ Power BI คุณต้องสามารถเชื่อมต่อกับจุดสิ้นสุดในตารางและไซต์ที่เชื่อมโยงด้านล่าง

| แถว | วัตถุประสงค์ | ปลายทาง | พอร์ต |
| --- | --- | --- | --- |
| 1 | **จำเป็นต้องมี:** APIs ที่ Backend | *.analysis.windows.net | TCP 443 |
| 2 | **จำเป็นต้องมี:** APIs ที่ Backend | *.pbidedicated.windows.net | TCP 443 |
| 3 | **จำเป็นต้องมี:** เครือข่ายการให้บริการเนื้อหา (CDN) | content.powerapps.com | TCP 443 |
| 4 | **จำเป็นต้องมี:** การรวม Microsoft 365 | ดูเอกสารประกอบสำหรับ [Microsoft 365 ทั่วไปและ URL ของ Office Online](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) | N/A |
| 5 | **จำเป็นต้องมี:** พอร์ทัล | app.powerbi.com | TCP 443 |
| 6 | **จำเป็นต้องมี:** การบริการการวัดและส่งข้อมูลทางไกล | dc.services.visualstudio.com | TCP 443 |
| 7 | **ตัวเลือก:** ข้อความที่ให้ข้อมูล | dynmsg.modpim.com | TCP 443 |
| 8 | **ตัวเลือก:** แบบสำรวจ NPS | nps.onyx.azure.net | TCP 443 |
| | | |

## <a name="administration"></a>การดูแลระบบ

เพื่อใช้ฟังก์ชันการบริหารระบบภายใน Power BI คุณต้องสามารถเชื่อมต่อกับจุดสิ้นสุดในไซต์เชื่อมโยงด้านล่าง

| แถว | วัตถุประสงค์ | ปลายทาง | พอร์ต |
| --- | --- | --- | --- |
| 1 | **จำเป็นต้องมี:** สำหรับการจัดการผู้ใช้ และการดูบันทึกการตรวจสอบ | ดูเอกสารประกอบสำหรับ [Microsoft 365 ทั่วไปและ URL ของ Office Online](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) | N/A |
| | | |

## <a name="getting-data"></a>การรับข้อมูล

เพื่อรับข้อมูลจากแหล่งข้อมูลที่เฉพาะเจาะจง เช่น OneDrive คุณต้องสามารถเชื่อมต่อกับจุดสิ้นสุดในตารางด้านล่าง การเข้าถึงโดเมนอินเทอร์เน็ตและ URL เพิ่มเติมอาจจำเป็นสำหรับแหล่งข้อมูลเฉพาะที่ใช้ภายในองค์กรของคุณ

| แถว | วัตถุประสงค์ | ปลายทาง | พอร์ต |
| --- | --- | --- | --- |
| 1 | **จำเป็นต้องมี:** AppSource (แอปภายในหรือภายนอกใน Power BI) | appsource.microsoft.com <br> *.s microsoft.com  | TCP 443 |
| 2 | **ตัวเลือก:** ลงชื่อเข้าใช้และรับข้อมูลสำหรับแพคเกจเนื้อหา | ขึ้นอยู่กับชุดเนื้อหาที่ใช้ | ขึ้นอยู่กับชุดเนื้อหาที่ใช้ |
| 3 | **ตัวเลือก:** นำเข้าไฟล์จาก OneDrive ส่วนบุคคล | ดู[URL และพอร์ตที่จำเป็นสำหรับไซต์ OneDrive](https://docs.microsoft.com/onedrive/required-urls-and-ports) | N/A |
| 4 | **ตัวเลือก:** Power BI ในวิดีโอบทช่วยสอน 60 วินาที | *.doubleclick.net <br> *.ggpht.com <br> *.google.com <br> *.googlevideo.com <br> *.youtube.com <br> *.ytimg.com <br> fonts.gstatic.com | TCP 443 |
| 5 | **ตัวเลือก:** แหล่งข้อมูลการสตรีม PubNub | ดู[เอกสาร PubNub](https://support.pubnub.com/support/solutions/articles/14000043522) | N/A |
| | | |

## <a name="dashboard-and-report-integration"></a>การรวมแดชบอร์ดและรายงาน

Power BI ขึ้นอยู่กับจุดสิ้นสุดเฉพาะเพื่อให้สามารถสนับสนุนแดชบอร์ดและรายงานของคุณ คุณต้องสามารถเชื่อมต่อกับจุดสิ้นสุดในตารางและไซต์ที่เชื่อมโยงด้านล่าง

| แถว | วัตถุประสงค์ | ปลายทาง | พอร์ต |
| --- | --- | --- | --- |
| 1 | **จำเป็นต้องมี:** การรวม Excel | ดูเอกสารประกอบสำหรับ [Microsoft 365 ทั่วไปและ URL ของ Office Online](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online) | N/A |
| | | |

## <a name="power-bi-visuals"></a>วิชวล Power BI

Power BI ขึ้นอยู่กับจุดสิ้นสุดเฉพาะในการดู และเข้าถึงวิชวล คุณต้องสามารถเชื่อมต่อกับจุดสิ้นสุดในตารางและไซต์ที่เชื่อมโยงด้านล่าง

| แถว | วัตถุประสงค์ | ปลายทาง | พอร์ต |
| --- | --- | --- | --- |
| 1 | **จำเป็นต้องมี:** นำเข้าวิชวลแบบกำหนดเองจากอินเทอร์เฟซ Marketplace หรือจากไฟล์ | *.azureedge.net <br> *.blob.core.windows.net <br> *.osi.office.net <br> *.msecnd.net <br> store.office.com <br> web.vortex.data.microsoft.com <br> store-images.s-microsoft.com | TCP 443 |
| 2 | **ตัวเลือก:** แผนที่ Bing | bing.com <br> platform.bing.com <br> *.virtualearth.net | TCP 443 |
| 3 | **ตัวเลือก:** PowerApps | ดู[ส่วนบริการที่จะเป็น](https://docs.microsoft.com/powerapps/maker/canvas-apps/limits-and-config#required-services)จากไซต์ความต้องการของระบบ PowerApps | N/A |
| 4 | **ตัวเลือก:** Visio | ดูเอกสารประกอบสำหรับ [Microsoft 365 ทั่วไปและ URL ของ Office Online ](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#microsoft-365-common-and-office-online)ตลอดจน [SharePoint Online และ OneDrive for Business](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#sharepoint-online-and-onedrive-for-business) | N/A |
| | | |

## <a name="related-external-sites"></a>เว็บไซต์ภายนอกที่เกี่ยวข้อง

Power BI ลิงก์ไปยังเว็บไซต์อื่นที่เกี่ยวข้อง เว็บไซต์เหล่านี้โฮสต์เอกสารประกอบ การสนับสนุน คำขอคุณลักษณะใหม่ และอีกมากมาย การเข้าถึงไซต์เหล่านี้จะไม่ส่งผลกระทบต่อฟังก์ชันการทำงานของ Power BI ดังนั้นอนุญาตพิเศษจึงเป็นตัวเลือก

| แถว | วัตถุประสงค์ | ปลายทาง | พอร์ต |
| --- | --- | --- | --- |
| 1 | **ตัวเลือก:** เว็บไซต์ชุมชน | community.powerbi.com <br> oxcrx34285.i.lithium.com | TCP 443 |
| 2 | **ตัวเลือก:** เว็บไซต์เอกสารประกอบ | docs.microsoft.com <br> img-prod-cms-rt-microsoft-com.akamaized.net <br> statics-uhf-eas.akamaized.net <br> cdnssl.clicktale.net <br> ing-district.clicktale.net | TCP 443 |
| 3 | **ตัวเลือก:** เว็บไซต์ดาวน์โหลด (สำหรับ Power BI Desktop และอื่น ๆ) | download.microsoft.com | TCP 443 |
| 4 | **ตัวเลือก:** การเปลี่ยนเส้นทางภายนอก | aka.ms <br> go.microsoft.com | TCP 443 |
| 5 | **ตัวเลือก:** เว็บไซต์สำหรับคำติชมแนวคิด| ideas.powerbi.com <br> powerbi.uservoice.com | TCP 443 |
| 6 | **ตัวเลือก:** เว็บไซต์ Power BI - หน้าเว็บไซต์แรก ลิงก์เรียนรู้เพิ่มเติม ไซต์สนับสนุน ลิงก์ดาวน์โหลด พื้นที่นำเสนอคู่ค้า และอีกมากมาย | powerbi.microsoft.com | TCP 443 |
| 7 | **ตัวเลือก:** ศูนย์นักพัฒนา Power BI | dev.powerbi.com | TCP 443 |
| 8 | **ตัวเลือก:** เว็บไซต์การสนับสนุน | support.powerbi.com <br> s3.amazonaws.com <br> *.olark.com <br> logx.optimizely.com <br> mscom.demdex.net <br> tags.tiqcdn.com | TCP 443 |
| | | |

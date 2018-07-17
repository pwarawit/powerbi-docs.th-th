---
title: สร้างการเชื่อมโยงไปยังตำแหน่งที่ตั้งเฉพาะในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
description: เรียนรู้วิธีการสร้างการเชื่อมโยงโดยตรงไปยังแดชบอร์ด ไทล์ หรือรายงานในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ที่ระบุด้วย Uniform Resource Identifier (URI)
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 06/28/2018
ms.author: maggies
ms.openlocfilehash: fb05b6fd2378c8fe2b6dec35250df31d227b7760
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/29/2018
ms.locfileid: "37135455"
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>สร้างการเชื่อมโยงไปยังตำแหน่งที่ตั้งเฉพาะในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
คุณสามารถสร้างและใช้ Uniform Resource Identifier (URI) เพื่อเชื่อมโยงไปยังตำแหน่งที่ตั้งที่ระบุ (*การเชื่อมโยงโดยตรง*) ภายในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่บนแพลตฟอร์มสำหรับอุปกรณ์เคลื่อนที่ทั้งหมด: iOS อุปกรณ์ Android และ Windows 10

ลิงก์ URI สามารถชี้ตรงไปยังแดชบอร์ด ไทล์ รายงาน

ปลายทางของการเชื่อมโยงโดยตรงจะกำหนดรูปแบบของ URI ทำตามขั้นตอนเหล่านี้เพื่อสร้างการเชื่อมโยงโดยตรงไปยังตำแหน่งที่ตั้งต่างๆ 

## <a name="open-the-power-bi-mobile-app"></a>เปิดแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
ใช้ URI นี้เพื่อเปิดแอป Power BI สำหรับอุปกรณ์เคลื่อนที่บนอุปกรณ์ใดก็ได้:

    mspbi://app/


## <a name="open-to-a-specific-dashboard"></a>เปิดไปยังแดชบอร์ดทีระบุ
URI นี้จะเปิดแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ไปยังแดชบอร์ดที่ระบุ:

    mspbi://app/OpenDashboard?DashboardObjectId=<36-character-dashboard-id>

เพื่อค้นหา ID ออปเจ็กต์ของแดชบอร์ด 36 ตัวอักษร นำทางไปยังแดชบอร์ดนั้นในบริการของ Power BI (https://powerbi.com) ตัวอย่างเช่น ดูส่วนทีมีการไฮไลต์ไว้ของ URL นี้:

https://powerbi.com/groups/me/dashboards/**61b7e871-cb98-48ed-bddc-6572c921e270**

ถ้าแดชบอร์ดอยู่ในกลุ่มอื่นที่ไม่ใช่พื้นที่ทำงานของฉัน ให้เพิ่ม`&GroupObjectId=<36-character-group-id>`ก่อน หรือ หลัง ID แดชบอร์ด ตัวอย่างเช่น 

mspbi://app/OpenDashboard?DashboardObjectId=e684af3a-9e7f-44ee-b679-b9a1c59b5d60 **&GroupObjectId=8cc900cc-7339-467f-8900-fec82d748248**

โปรดสังเกตเครื่องหมายและ (&) ระหว่างทั้งสอง

## <a name="open-to-a-specific-tile-in-focus"></a>เปิดไปยังไทล์ที่ระบุในโฟกัส
URI นี้จะเปิดไทล์ที่ระบุในโฟกัสในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่:

    mspbi://app/OpenTile?DashboardObjectId=<36-character-dashboard-id>&TileObjectId=<36-character-tile-id>

เพื่อค้นหา ID ออปเจ็กต์ของแดชบอร์ดและไทล์ 36 ตัวอักษร นำทางไปยังแดชบอร์ดนั้นในบริการของ Power BI (https://powerbi.com) และเปิดไทล์ในโหมดโฟกัส ตัวอย่างเช่น ดูส่วนทีมีการไฮไลต์ไว้ของ URL นี้:

https://powerbi.com/groups/me/dashboards/**3784f99f-b460-4d5e-b86c-b6d8f7ec54b7**/tiles/**565f9740-5131-4648-87f2-f79c4cf9c5f5**/infocus

สำหรับไทล์นี้ URI จะเป็น:

    mspbi://app/OpenTile?DashboardObjectId=3784f99f-b460-4d5e-b86c-b6d8f7ec54b7&TileObjectId=565f9740-5131-4648-87f2-f79c4cf9c5f5

โปรดสังเกตเครื่องหมายและ (&) ระหว่างทั้งสอง

ถ้าแดชบอร์ดอยู่ในกลุ่มอื่นที่ไม่ใช่พื้นที่ทำงานของฉัน ให้เพิ่ม `&GroupObjectId=<36-character-group-id>`

## <a name="open-to-a-specific-report"></a>เปิดไปยังรายงานที่ระบุ
URI นี้จะเปิดรายงานที่ระบุในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>

เพื่อค้นหา ID ออปเจ็กต์ของรายงาน 36 ตัวอักษร นำทางไปยังรายงานนั้นในบริการของ Power BI (https://powerbi.com) ตัวอย่างเช่น ดูส่วนทีมีการไฮไลต์ไว้ของ URL นี้:

https://powerbi.com/groups/me/reports/**df9f0e94-31df-450b-b97f-4461a7e4d300**

## <a name="open-to-a-specific-report-page"></a>เปิดไปยังหน้ารายงานที่ระบุ
URI นี้จะเปิดหน้ารายงานที่ระบุในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>&reportPage=ReportSection<number>

หน้ารายงานจะเรียกว่า "ReportSection" ตามด้วยตัวเลข อีกครั้ง เปิดรายงานในบริการของ Power BI (https://powerbi.com) และนำทางไปยังหน้ารายงานนั้น 

ตัวอย่างเช่น ดูส่วนทีมีการไฮไลต์ไว้ของ URL นี้:

https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/**ReportSection11**

## <a name="open-in-full-screen-mode"></a>เปิดในโหมดเต็มหน้าจอ
เพิ่มพารามิเตอร์เป็นตัวหนาเมื่อต้องเปิดการรายงานที่ระบุในโหมดเต็มหน้าจอ:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>**&openFullScreen=true**

ตัวอย่างเช่น: 

mspbi://app/OpenReport?ReportObjectId=500217de-50f0-4af1-b345-b81027224033&openFullScreen=true

## <a name="add-context-optional"></a>เพิ่มบริบท (ไม่บังคับ)
คุณยังสามารถเพิ่มบริบทในสตริง จากนั้นถ้าคุณต้องการติดต่อเรา เราสามารถใช้บริบทนั้นเพื่อกรองข้อมูลของเราไปยังแอปของคุณ เพิ่ม`&context=<app-name>`ไปยังการเชื่อมโยง

ตัวอย่างเช่น ดูส่วนทีมีการไฮไลต์ไว้ของ URL นี้: 

https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/**&context=SlackDeepLink**

## <a name="next-steps"></a>ขั้นตอนถัดไป
คำติชมของคุณจะช่วยให้เราตัดสินใจว่าสิ่งใดควรดำเนินการในอนาคต ดังนั้นอย่าลืมลงคะแนนให้กับคุณลักษณะอื่นๆ ที่คุณต้องการเห็นในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ 

* [แอป Power BI สำหรับอุปกรณ์เคลื่อนที่](mobile-apps-for-mobile-devices.md)
* ติดตาม@MSPowerBIบน Twitter
* เข้าร่วมการสนทนาที่[ชุมชน Power BI](http://community.powerbi.com/)
* [Power BI คืออะไร](power-bi-overview.md)


---
title: 'Project Online: เชื่อมต่อกับข้อมูลผ่านทาง Power BI Desktop'
description: 'Project Online: เชื่อมต่อกับข้อมูลผ่านทาง Power BI Desktop'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b0dc84d7b2d8da0df8a9e61a43f35898d197c188
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "65513732"
---
# <a name="project-online-connect-to-data-through-power-bi-desktop"></a>Project Online: เชื่อมต่อกับข้อมูลผ่านทาง Power BI Desktop
คุณสามารถเชื่อมต่อไปยังข้อมูลใน Project Online ผ่านทาง Power BI Desktop

## <a name="step-1-download-power-bi-desktop"></a>ขั้นตอนที่ 1: ดาวน์โหลด Power BI Desktop
1. [ดาวน์โหลด Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=521662) แล้วเรียกใช้ตัวติดตั้งเพื่อรับ **Power BI Desktop** บนคอมพิวเตอร์ของคุณ

## <a name="step-2-connect-to-project-online-with-odata"></a>ขั้นตอนที่ 2: เชื่อมต่อกับ Project Online ด้วย OData
1. เปิด **Power BI Desktop**
2. บนหน้าจอ*ยินดีต้อนรับ* เลือก**รับข้อมูล**
3. เลือก**ตัวดึงข้อมูล OData** และเลือก**เชื่อมต่อ**
4. ใส่ที่อยู่ของตัวดึงข้อมูล OData ของคุณในกล่อง URL แล้ว คลิกตกลง
   
   ถ้าอยู่สำหรับไซต์ Project Web App ของคุณคล้ายกับ*https://\<tenantname\>.sharepoint.com/sites/pwa*จาก นั้นคุณจะใส่สำหรับตัวดึงข้อมูล OData ของคุณอยู่*https://\<tenantname\>.sharepoint.com/sites/pwa/\_api/Projectdata*
   
   สำหรับตัวอย่าง เรากำลังใช้ https://contoso.sharepoint.com/sites/pwa/default.aspx
5. Power BI Desktop จะพร้อมท์ให้คุณรับรองสิทธิ์กับบัญชี Office 365 ของคุณ เลือกบัญชีผู้ใช้ขององค์กร แล้วใส่ข้อมูลประจำตัวของคุณ
   
   ![](media/desktop-project-online-connect-to-data/image.png)

บัญชีคุณใช้เพื่อเชื่อมต่อกับ OData ตัวดึงข้อมูลต้องมีอย่างน้อยพอร์ตโครงการเพื่อข้าถึงไซต์ Project Web App 

จากที่นี่ คุณสามารถเลือกตารางที่คุณต้องการจะเชื่อมต่อและสร้างแบบสอบถาม  อยากทราบวิธีการเริ่มต้นใช้งานใช่หรือไม่  โพสต์ในบล็อกต่อไปนี้แสดงวิธีการสร้างเขียนลงในแผนภูมิจากข้อมูล Project Online ของคุณ  โพสต์ในบล็อกจะอ้างอิงเกี่ยวกับการใช้ Power Query เพื่อเชื่อมต่อกับ Project Online แต่ยังสามารถใช้กับ Power BI Desktop ได้เช่นกัน

[สร้างเขียนลงในแผนภูมิสำหรับโครงการโดยใช้ Power Pivot และ Power Query](http://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)


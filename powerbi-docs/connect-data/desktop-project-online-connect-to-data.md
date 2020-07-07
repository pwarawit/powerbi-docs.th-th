---
title: 'Project Online: เชื่อมต่อกับข้อมูลผ่านทาง Power BI Desktop'
description: 'Project Online: เชื่อมต่อกับข้อมูลผ่านทาง Power BI Desktop'
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 04/01/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 726c265198c7489ac1de055d0fc00b1988109d11
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85223316"
---
# <a name="connect-to-project-online-data-through-power-bi-desktop"></a>เชื่อมต่อกับข้อมูล Project Online ผ่าน Power BI Desktop
คุณสามารถเชื่อมต่อไปยังข้อมูลใน Project Online ผ่านทาง Power BI Desktop

## <a name="step-1-download-power-bi-desktop"></a>ขั้นตอนที่ 1: ดาวน์โหลด Power BI Desktop
1. [ดาวน์โหลด Power BI Desktop](https://go.microsoft.com/fwlink/?LinkID=521662) แล้วเรียกใช้ตัวติดตั้งเพื่อรับ **Power BI Desktop** บนคอมพิวเตอร์ของคุณ

## <a name="step-2-connect-to-project-online-with-odata"></a>ขั้นตอนที่ 2: เชื่อมต่อกับ Project Online ด้วย OData
1. เปิด **Power BI Desktop**
2. บนหน้าจอ*ยินดีต้อนรับ* เลือก**รับข้อมูล**
3. เลือก**ตัวดึงข้อมูล OData** และเลือก**เชื่อมต่อ**
4. ใส่ที่อยู่ของตัวดึงข้อมูล OData ของคุณในกล่อง URL แล้ว คลิกตกลง
   
   หากที่อยู่สำหรับไซต์ Project Web App ของคุณเป็นรูปแบบ *https://\<tenantname\>.sharepoint.com/sites/pwa* จากนั้นที่อยู่ที่คุณจะป้อนใส่สำหรับฟีด OData ของคุณคือ *https://\<tenantname\>.sharepoint.com/sites/pwa/\_api/Projectdata*
   
   สำหรับตัวอย่าง เรากำลังใช้:

    `https://contoso.sharepoint.com/sites/pwa/default.aspx`

5. Power BI Desktop จะพร้อมท์ให้คุณรับรองสิทธิ์กับบัญชีที่ทำงานหรือบัญชีโรงเรียนของคุณ เลือกบัญชีผู้ใช้ขององค์กร แล้วใส่ข้อมูลประจำตัวของคุณ
   
   ![](media/desktop-project-online-connect-to-data/image.png)

บัญชีที่คุณใช้เพื่อเชื่อมต่อกับตัวดึงข้อมูล OData อย่างน้อยต้องมีตัวแสดงพอร์ตโครงการเพื่อข้าถึงไซต์ Project Web App 

จากที่นี่ คุณสามารถเลือกตารางที่คุณต้องการจะเชื่อมต่อและสร้างแบบสอบถาม  อยากทราบวิธีการเริ่มต้นใช้งานใช่หรือไม่  โพสต์ในบล็อกต่อไปนี้จะแสดงวิธีการสร้างแผนภูมิการวัดความก้าวหน้าจากข้อมูล Project Online ของคุณ  โพสต์ในบล็อกจะอ้างอิงเกี่ยวกับการใช้ Power Query เพื่อเชื่อมต่อกับ Project Online แต่ยังสามารถใช้กับ Power BI Desktop ได้เช่นกัน

[สร้างแผนภูมิการวัดความก้าวหน้าสำหรับโครงการโดยใช้ Power Pivot และ Power Query](https://blogs.office.com/2014/03/24/creating-burndown-charts-for-project-using-power-pivot-and-power-query/)


---
title: แก้ไขปัญหาการรีเฟรชตามกำหนดการสำหรับ Azure SQL Database
description: แก้ไขปัญหาการรีเฟรชตามกำหนดการสำหรับ Azure SQL Database ใน Power BI
author: mgblythe
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 09/04/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 9846f65951c9cd45f011a2b5ec81852df10b063f
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/09/2019
ms.locfileid: "73855860"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>แก้ไขปัญหาการรีเฟรชตามกำหนดการสำหรับ Azure SQL Database ใน Power BI

สำหรับข้อมูลโดยละเอียดเกี่ยวกับการรีเฟรช โปรดดูหัวข้อ [รีเฟรชข้อมูลใน Power BI](refresh-data.md) และ [กำหนดค่าการรีเฟรชตามกำหนดเวลา](refresh-scheduled-refresh.md)

ขณะที่กำลังตั้งค่าการรีเฟรชตามกำหนดเวลสสำหรับฐานข้อมูล Azure SQL หากคุณได้รับข้อผิดพลาดที่มีรหัสข้อผิดพลาด 400 เมื่อแก้ไขข้อมูลประจำตัว กรุณาลองทำตามขั้นตอนต่อไปนี้เพื่อตั้งค่ากฎไฟร์วอลล์ที่เหมาะสม

1. ลงชื่อเข้าใช้ไปยัง [พอร์ทัล Azure](https://portal.azure.com)

1. ไปยังฐานข้อมูล Azure SQL ที่คุณกำลังกำหนดค่าการรีเฟรช

1. ที่ด้านบนของแผ่น **ภาพรวม** ให้เลือก **ตั้งค่าไฟร์วอลล์ของเซิร์ฟเวอร์**

1. บนแผ่น **การตั้งค่าไฟร์วอลล์** คุณควรตรวจสอบให้แน่ใจว่ามีการตั้งค่า **อนุญาตการเข้าถึงบริการ Azure** เป็น **ON**

    ![บริการ Azure ที่ได้รับอนุญาต](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)

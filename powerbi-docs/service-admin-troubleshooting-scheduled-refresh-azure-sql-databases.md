---
title: แก้ไขปัญหาการรีเฟรชตามกำหนดการสำหรับ Azure SQL Database
description: แก้ไขปัญหาการรีเฟรชตามกำหนดการสำหรับ Azure SQL Database ใน Power BI
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: d1cd68fbb995b7fac420a50f97a8930385086a10
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/07/2018
ms.locfileid: "53026074"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>แก้ไขปัญหาการรีเฟรชตามกำหนดการสำหรับ Azure SQL Database ใน Power BI
โปรดดูที่[รีเฟรชข้อมูลใน Power BI](refresh-data.md)สำหรับขั้นตอนโดยละเอียดเกี่ยวกับการตั้งค่าการรีเฟรชตามกำหนดการ

ขณะที่กำลังตั้งค่าการรีเฟรชตามกำหนดการสำหรับฐานข้อมูล Azure SQL หากคุณได้รับข้อผิดพลาดที่มีรหัสข้อผิดพลาด 400 ระหว่างการแก้ไขข้อมูลประจำตัว กรุณาลองทำตามขึ้นตอนต่อไปนี้เพื่อตั้งค่ากฎไฟร์วอลล์ที่เหมาะสม

1. ลงชื่อเข้าใช้ในพอร์ทัลการจัดการ Azure ของคุณ
2. ไปที่เซิร์ฟเวอร์ Azure SQL ที่คุณกำลังกำหนดค่าการรีเฟรช
3. เปิดใช้งาน 'Windows Azure Services' ในส่วนบริการที่ได้รับอนุญาต

![บริการ Azure ที่ได้รับอนุญาต](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


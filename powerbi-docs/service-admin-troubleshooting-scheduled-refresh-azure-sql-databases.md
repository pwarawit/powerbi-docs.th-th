---
title: แก้ไขปัญหาการรีเฟรชตามกำหนดการสำหรับ Azure SQL Database
description: แก้ไขปัญหาการรีเฟรชตามกำหนดการสำหรับ Azure SQL Database ใน Power BI
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 17ee932bf0331940c7b30b020ab8fc43cdc9fdf5
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54274690"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>แก้ไขปัญหาการรีเฟรชตามกำหนดการสำหรับ Azure SQL Database ใน Power BI
โปรดดูที่[รีเฟรชข้อมูลใน Power BI](refresh-data.md)สำหรับขั้นตอนโดยละเอียดเกี่ยวกับการตั้งค่าการรีเฟรชตามกำหนดการ

ขณะที่กำลังตั้งค่าการรีเฟรชตามกำหนดการสำหรับฐานข้อมูล Azure SQL หากคุณได้รับข้อผิดพลาดที่มีรหัสข้อผิดพลาด 400 ระหว่างการแก้ไขข้อมูลประจำตัว กรุณาลองทำตามขึ้นตอนต่อไปนี้เพื่อตั้งค่ากฎไฟร์วอลล์ที่เหมาะสม

1. ลงชื่อเข้าใช้ในพอร์ทัลการจัดการ Azure ของคุณ
2. ไปที่เซิร์ฟเวอร์ Azure SQL ที่คุณกำลังกำหนดค่าการรีเฟรช
3. เปิดใช้งาน 'Windows Azure Services' ในส่วนบริการที่ได้รับอนุญาต

![บริการ Azure ที่ได้รับอนุญาต](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


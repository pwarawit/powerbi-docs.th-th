---
title: แก้ไขปัญหาการรีเฟรชตามกำหนดการสำหรับ Azure SQL Database
description: แก้ไขปัญหาการรีเฟรชตามกำหนดการสำหรับ Azure SQL Database ใน Power BI
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 6fc118a2f809f06f1bdd61984d100ebece516baa
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/08/2018
ms.locfileid: "30977051"
---
# <a name="troubleshooting-scheduled-refresh-for-azure-sql-databases-in-power-bi"></a>แก้ไขปัญหาการรีเฟรชตามกำหนดการสำหรับ Azure SQL Database ใน Power BI
โปรดดูที่[รีเฟรชข้อมูลใน Power BI](refresh-data.md)สำหรับขั้นตอนโดยละเอียดเกี่ยวกับการตั้งค่าการรีเฟรชตามกำหนดการ

ขณะที่กำลังตั้งค่าการรีเฟรชตามกำหนดการสำหรับฐานข้อมูล Azure SQL หากคุณได้รับข้อผิดพลาดที่มีรหัสข้อผิดพลาด 400 ระหว่างการแก้ไขข้อมูลประจำตัว กรุณาลองทำตามขึ้นตอนต่อไปนี้เพื่อตั้งค่ากฎไฟร์วอลล์ที่เหมาะสม

1. ลงชื่อเข้าใช้ในพอร์ทัลการจัดการ Azure ของคุณ
2. ไปที่เซิร์ฟเวอร์ Azure SQL ที่คุณกำลังกำหนดค่าการรีเฟรช
3. เปิดใช้งาน 'Windows Azure Services' ในส่วนบริการที่ได้รับอนุญาต

![](media/service-admin-troubleshooting-scheduled-refresh-azure-sql-databases/azurerefresh.png)  

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


---
title: ข้อกำหนดเบื้องต้นของแหล่งข้อมูล Power BI
description: ข้อกำหนดเบื้องต้นของแหล่งข้อมูล Power BI
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/29/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 498636d61f61764cfaef29db32454f55f1328243
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "78401217"
---
# <a name="power-bi-data-source-prerequisites"></a>ข้อกำหนดเบื้องต้นของแหล่งข้อมูล Power BI
สำหรับตัวให้บริการข้อมูลแต่ละตัว Power BI รองรับเวอร์ชันตัวให้บริการที่เจาะจงกับวัตถุ สำหรับข้อมูลเพิ่มเติมเกี่ยวกับแหล่งข้อมูลที่มีใน Power BI โปรดดูที่[แหล่งข้อมูล](desktop-data-sources.md) ตารางต่อไปนี้แสดงข้อกำหนดเหล่านี้

| แหล่งข้อมูล | ตัวให้บริการ | เวอร์ชันขั้นต่ำของตัวให้บริการ | เวอร์ชันขั้นต่ำของแหล่งข้อมูล | วัตถุในแหล่งข้อมูลที่สนับสนุน | ลิงก์ดาวน์โหลด |
| --- | --- | --- | --- | --- | --- |
| เซิร์ฟเวอร์ SQL |ADO.net (มีอยู่แล้วใน .Net Framework) |.NET Framework 3.5 (เท่านั้น) |SQL Server 2005 + |ตาราง/มุมมอง, ฟังก์ชันสเกลา, ฟังก์ชันตาราง |รวมอยู่ใน .NET Framework 3.5 หรือใหม่กว่า |
| Access |Microsoft Access Database Engine (ACE) |ACE 2010 SP1 |ไม่มีข้อจำกัด |ตาราง/มุมมอง |[ลิงก์ดาวน์โหลด](https://go.microsoft.com/fwlink/?linkid=285987&clcid=0x409) |
| Excel (เฉพาะไฟล์ .xls เท่านั้น) (ดูหมายเหตุ 1) |Microsoft Access Database Engine (ACE) |ACE 2010 SP1 |ไม่มีข้อจำกัด |ตาราง, แผ่นงาน |[ลิงก์ดาวน์โหลด](https://go.microsoft.com/fwlink/?linkid=285987&clcid=0x409) |
| Oracle (ดูหมายเหตุ 2) |ODP.NET |ODAC 11.2 รีลีส 5 (11.2.0.3.20) |9.x+ |ตาราง/มุมมอง |[ลิงก์ดาวน์โหลด](https://go.microsoft.com/fwlink/?linkid=272376&clcid=0x409) |
| | System.Data.OracleClient (มีอยู่แล้วใน .NET Framework) |.NET Framework 3.5 |9.x+ |ตาราง/มุมมอง |รวมอยู่ใน .NET Framework 3.5 หรือใหม่กว่า |
| IBM DB2 |ไคลเอ็นต์ ADO.Net จาก IBM (ส่วนหนึ่งของแพคเกจโปรแกรมควบคุมเซิร์ฟเวอร์ข้อมูล IBM) |10.1 |9.1+ |ตาราง/มุมมอง |[ลิงก์ดาวน์โหลด](https://go.microsoft.com/fwlink/?linkid=274911&clcid=0x409) |
| MySQL |Connector/Net |6.6.5 |5.1 |ตาราง/มุมมอง, ฟังก์ชันสเกลา |[ลิงก์ดาวน์โหลด](https://go.microsoft.com/fwlink/?linkid=278885&clcid=0x409) |
| PostgreSQL |ผู้ให้บริการ NPGSQL ADO.NET (จัดส่งด้วย Power BI Desktop) |4.0.10 |9.4 |ตาราง/มุมมอง |[ลิงก์ดาวน์โหลด](https://go.microsoft.com/fwlink/?linkid=282716&clcid=0x409) |
| Teradata |.NET Data Provider for Teradata |14+ |12+ |ตาราง/มุมมอง |[ลิงก์ดาวน์โหลด](https://go.microsoft.com/fwlink/?linkid=278886&clcid=0x409) |
| SAP SQL Sybase Anywhere |iAnywhere.Data.SQLAnywhere for .NET 3.5 |16+ |16+ |ตาราง/มุมมอง |[ลิงก์ดาวน์โหลด](https://go.microsoft.com/fwlink/?linkid=324846) |

>[!NOTE]
>ไฟล์ Excel ที่มีนามสกุล .xlsx ไม่จำเป็นติดตั้งตัวให้บริการแยกต่างหาก

>[!NOTE]
>ตัวให้บริการ Oracle จำเป็นต้องมีซอฟต์แวร์ไคลเอ็นต์ Oracle (รุ่น 8.1.7+)
> 
> 


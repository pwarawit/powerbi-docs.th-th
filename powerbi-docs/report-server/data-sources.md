---
title: แหล่งข้อมูลรายงาน Power BI ใน Power BI Report Server
description: รายงาน Power BI สามารถเชื่อมต่อกับหลาย ๆ แหล่งข้อมูลได้ ขึ้นอยู่กับวิธีการใช้ข้อมูล แหล่งข้อมูลที่แตกต่างกันสามารถใช้งานได้
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 08/04/2020
ms.author: maggies
ms.openlocfilehash: 00c00ca7bbd7ad3f901c98f44a2900f332e3616a
ms.sourcegitcommit: 65822b51810a5239fea9d3d0af1fc286436c6cad
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/06/2020
ms.locfileid: "87837623"
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>แหล่งข้อมูลรายงาน Power BI ใน Power BI Report Server
รายงาน Power BI สามารถเชื่อมต่อกับหลาย ๆ แหล่งข้อมูลได้ ขึ้นอยู่กับวิธีการใช้ข้อมูล แหล่งข้อมูลที่แตกต่างกันสามารถใช้งานได้ สามารถนำเข้าข้อมูล หรือข้อมูลสามารถถูกคิวรี่ได้โดยตรงโดยใช้ DirectQuery หรือการเชื่อมต่อตรงกับ SQL Server Analysis Services บางแหล่งข้อมูลได้รับการสนับสนุนใน Power BI Desktop ที่ปรับให้เหมาะสมสำหรับเซิร์ฟเวอร์รายงาน Power BI แต่ไม่ได้ปรับให้เหมาะสมสำหรับรายงาน Power BI ที่เผยแพร่ไปยังเซิร์ฟเวอร์รายงาน Power BI ดูรายการต่อไปนี้สำหรับแหล่งข้อมูลที่รองรับทั้งสองที่

แหล่งข้อมูลเหล่านี้จะใช้เฉพาะกับรายงาน Power BI ที่ใช้ภายในเซิร์ฟเวอร์รายงาน Power BI สำหรับข้อมูลเกี่ยวกับแหล่งข้อมูลที่สนับสนุนรายงานที่มีการแบ่งหน้า (.rdl) ดูที่[ข้อมูลแหล่งข้อมูลที่สนับสนุนโดย Reporting Services](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs)

> [!IMPORTANT]
> แหล่งข้อมูลทั้งหมดในรายงาน Power BI Desktop ต้องสนับสนุนการกำหนดค่าการรีเฟรชตามกำหนดเวลา
>  

## <a name="list-of-supported-data-sources"></a>รายการของแหล่งข้อมูลทีรองรับ

| **แหล่งข้อมูล** | **ข้อมูลที่แคช** | **รีเฟรชตามกำหนดการ** | **Live/DirectQuery** |
| --- | --- | --- | --- |
| ฐานข้อมูล SQL Server |ใช่ |ใช่ |ใช่ |
| SQL Server Analysis Services |ใช่ |ใช่ |ใช่ |
| ฐานข้อมูล Azure SQL |ใช่ |ใช่ |ใช่ |
| คลังข้อมูล Azure SQL |ใช่ |ใช่ |ใช่ |
| Excel |ใช่ |ใช่ |ไม่ใช่ |
| ฐานข้อมูล Access |ใช่ |ใช่ |ไม่ใช่ |
| Active Directory |ใช่ |ใช่ |ไม่ใช่ |
| Amazon Redshift |ใช่ |ไม่ใช่ |ไม่ใช่ |
| พื้นที่เก็บข้อมูล Azure Blob |ใช่ |ใช่ |ไม่ใช่ |
| Azure Data Lake Store |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure HDInsight (HDFS) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure HDInsight (Spark) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| พื้นที่เก็บข้อมูล Azure Table |ใช่ |ใช่ |ไม่ใช่ |
| Dynamics 365 (ออนไลน์) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Facebook |ใช่ |ไม่ใช่ |ไม่ใช่ |
| โฟลเดอร์ |ใช่ |ใช่ |ไม่ใช่ |
| Google Analytics |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ไฟล์ Hadoop (HDFS) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล IBM DB2 |ใช่ |ใช่ |ไม่ใช่ |
| Impala |ใช่ |ไม่ใช่ |ไม่ใช่ |
| JSON |ใช่ |ใช่ |ไม่ใช่ |
| Microsoft Exchange |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Microsoft Exchange Online |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล MySQL |ใช่ |ใช่ |ไม่ใช่ |
| ตัวดึงข้อมูล OData |ใช่ |ใช่ |ไม่ใช่ |
| ODBC |ใช่ |ใช่ |ไม่ใช่ |
| OLE DB |ใช่ |ใช่ |ไม่ใช่ |
| Oracle Database |ใช่ |ใช่ |ใช่ |
| ฐานข้อมูล PostgreSQL |ใช่ |ใช่ |ไม่ใช่ |
| บริการ Power BI |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| สคริปต์ R |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ออบเจ็กต์ Salesforce |ใช่ |ไม่ใช่ |ไม่ใช่ |
| รายงาน Salesforce |ใช่ |ไม่ใช่ |ไม่ใช่ |
| เซิร์ฟเวอร์ SAP Business Warehouse |ใช่ |ใช่ |ใช่ |
| ฐานข้อมูล SAP HANA |ใช่ |ใช่ |ใช่ |
| โฟลเดอร์ SharePoint (ภายในองค์กร) |ใช่ |ใช่ |ไม่ใช่ |
| รายการ SharePoint (ภายในองค์กร) |ใช่ |ใช่ |ไม่ใช่ |
| รายการ SharePoint Online |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Snowflake |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล Sybase |ใช่ |ใช่ |ไม่ใช่ |
| Teradata |ใช่ |ใช่ |ใช่ |
| Text/CSV |ใช่ |ใช่ |ไม่ใช่ |
| เว็บ |ใช่ |ใช่ |ไม่ใช่ |
| XML |ใช่ |ใช่ |ไม่ใช่ |
| appFigures (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล Azure Analysis Services |ใช่ |ไม่ใช่ |ใช่ |
| Azure Cosmos DB (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure HDInsight Spark (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Common Data Service (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| comScore Digital Analytix (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Dynamics 365 for Customer Insights |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Dynamics 365 สำหรับ Financials (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| GitHub (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Google BigQuery |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล IBM Informix |ใช่ |ไม่ใช่ |ไม่ใช่ |
| IBM Netezza |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Kusto (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| MailChimp (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Microsoft Azure Consumption Insights (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Mixpanel (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Planview Enterprise (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Projectplace (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| QuickBooks Online (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Smartsheet |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Spark (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| SparkPost (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| SQL Sentry (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Stripe (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| SweetIQ (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Troux (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Twilio (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| tyGraph (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Vertica (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Visual Studio Team Services (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Webtrends (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Zendesk (เบต้า) |ใช่ |ไม่ใช่ |ไม่ใช่ |

> [!IMPORTANT]
> รักษาความปลอดภัยระดับแถวที่ถูกตั้งในระดับแหล่งข้อมูลควรทำงานกับ DirectQuery (SQL Server, Azure SQL Database, Oracle and Teradata) และเชื่อมต่อแบบตรงนั้นเข้าใจว่า Kerberos ได้ถูกตั้งค่าค่าอย่างถูกต้องสภาพแวดล้อมของระบบของคุณ
> 
> 

## <a name="list-of-supported-authentication-methods-for-model-refresh"></a>รายการของวิธีการรับรองตัวตนที่รองรับการีเฟรชแบบจำลอง

เซิร์ฟเวอรรายงาน์ power BI ไม่รองรับการรับรองตัวตน OAuth สำหรับการรีเฟรชแบบจำลอง แหล่งข้อมูลบางอย่างเช่นฐานข้อมูล Excel หรือ Access ทำให้การใช้ขั้นตอนที่แยกกัน เช่นไฟล์หรือเว็บเพื่อเชื่อมต่อกับข้อมูล

| **แหล่งข้อมูล** | **การรับรองตัวตนแบบไม่ระบุชื่อ** | **คีย์ตรวจสอบตัวตน** | **ชื่อผู้ใช้และรหัสผ่าน** | **รับรองตัวตนของ Windows** |
| --- | --- | --- | --- | --- |
| ฐานข้อมูล SQL Server |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| SQL Server Analysis Services |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| เว็บ |ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| ฐานข้อมูล Azure SQL |ไม่ใช่ |ไม่ใช่ |ใช่ |ไม่ใช่ |
| คลังข้อมูล Azure SQL |ไม่ใช่ |ไม่ใช่ |ใช่ |ไม่ใช่ |
| Active Directory |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| Amazon Redshift |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| พื้นที่เก็บข้อมูล Azure Blob |ใช่ |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure Data Lake Store |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure HDInsight (HDFS) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure HDInsight (Spark) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| พื้นที่เก็บข้อมูล Azure Table |ไม่ใช่ |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Dynamics 365 (ออนไลน์) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Facebook |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| โฟลเดอร์ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ใช่ |
| Google Analytics |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| ไฟล์ Hadoop (HDFS) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล IBM DB2 |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| Impala |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Microsoft Exchange |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Microsoft Exchange Online |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล MySQL |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| ตัวดึงข้อมูล OData |ใช่ |ใช่ |ใช่ |ใช่ |
| ODBC |ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| OLE DB |ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| Oracle Database |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| ฐานข้อมูล PostgreSQL |ไม่ใช่ |ไม่ใช่ |ใช่ |ไม่ใช่ |
| บริการ Power BI |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| สคริปต์ R |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| ออบเจ็กต์ Salesforce |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| รายงาน Salesforce |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| เซิร์ฟเวอร์ SAP Business Warehouse |ไม่ใช่ |ไม่ใช่ |ใช่ |ไม่ใช่ |
| ฐานข้อมูล SAP HANA |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| โฟลเดอร์ SharePoint (ภายในองค์กร) |ใช่ |ไม่ใช่ |ไม่ใช่ |ใช่ |
| รายการ SharePoint (ภายในองค์กร) |ใช่ |ไม่ใช่ |ไม่ใช่ |ใช่ |
| รายการ SharePoint Online |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Snowflake |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล Sybase |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| Teradata |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่** |
| appFigures (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure Analysis Services database (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure Cosmos DB (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure HDInsight Spark (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Common Data Service (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| comScore Digital Analytix (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Dynamics 365 for Customer Insights |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Dynamics 365 สำหรับ Financials (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| GitHub (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Google BigQuery |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล IBM Informix |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| IBM Netezza |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Kusto (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| MailChimp (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Microsoft Azure Consumption Insights (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Mixpanel (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Planview Enterprise (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Projectplace (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| QuickBooks Online (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Smartsheet |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Spark (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| SparkPost (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| SQL Sentry (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Stripe (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| SweetIQ (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Troux (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Twilio (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| tyGraph (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Vertica (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Visual Studio Team Services (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Webtrends (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Zendesk (เบต้า) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |

**การรีเฟรชโมเดลไม่รองรับการรับรองความถูกต้องแบบ LDAP กับ Teradata (เปิดใช้งานใน Power BI Desktop ได้โดยใช้คำสั่ง Command Prompt ว่า 'setx PBI_EnableTeradataLdap true')

## <a name="list-of-supported-authentication-methods-for-directquery"></a>รายการของวิธีการรับรองตัวตนได้รับการรองรับสำหรับ DirectQuery

เซิร์ฟเวอร์รายงาน power BI ไมรองรับการรับรองตัวตน OAuth สำหรับ DirectQuery

| **แหล่งข้อมูล** | **การรับรองตัวตนแบบไม่ระบุชื่อ** | **คีย์ตรวจสอบตัวตน** | **ชื่อผู้ใช้และรหัสผ่าน** | **รับรองตัวตนของ Windows** | **Integrated Windows Authentication** |
| --- | --- | --- | --- | --- | --- |
| ฐานข้อมูล SQL Server |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |ใช่ |
| SQL Server Analysis Services |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |ใช่ |
| ฐานข้อมูล Azure SQL |ไม่ใช่ |ไม่ใช่ |ใช่ |ไม่ใช่ |ไม่ใช่ |
| คลังข้อมูล Azure SQL |ไม่ใช่ |ไม่ใช่ |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Oracle Database |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |ใช่ |
| เซิร์ฟเวอร์ SAP Business Warehouse |ไม่ใช่ |ไม่ใช่ |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล SAP HANA |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |ใช่** |
| Teradata |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |ใช่ |

** SAP Hana สนับสนุน DirectQuery ด้วยการรับรองความถูกต้องของ Windows แบบรวมเท่านั้นเมื่อใช้เป็นฐานข้อมูลเชิงสัมพันธ์ในไฟล์ Power BI Desktop ที่เผยแพร่ (.pbix)

## <a name="next-steps"></a>ขั้นตอนถัดไป

[แหล่งข้อมูลสำหรับรายงาน Power BI[(../connect-data/power-bi-data-sources.md) ในบริการของ Power BI ในตอนนี้คุณได้เชื่อมต่อกับแหล่งข้อมูลของคุณ [สร้างรายงาน Power BI](quickstart-create-powerbi-report.md) โดยใช้ข้อมูลจากแหล่งข้อมูลดังกล่าว

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)

---
title: แหล่งข้อมูลรายงาน Power BI ใน Power BI Report Server
description: รายงาน Power BI สามารถเชื่อมต่อกับหลาย ๆ แหล่งข้อมูลได้ ขึ้นอยู่กับวิธีการใช้ข้อมูล แหล่งข้อมูลที่แตกต่างกันสามารถใช้งานได้
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: maggies
ms.openlocfilehash: fe8ad0b951fedb17a97007e48808d2bfd7467e88
ms.sourcegitcommit: 6c2c7a090b0826e3cfc3a897566e802857bbacc8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/06/2019
ms.locfileid: "68808216"
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>แหล่งข้อมูลรายงาน Power BI ใน Power BI Report Server
รายงาน Power BI สามารถเชื่อมต่อกับหลาย ๆ แหล่งข้อมูลได้ ขึ้นอยู่กับวิธีการใช้ข้อมูล แหล่งข้อมูลที่แตกต่างกันสามารถใช้งานได้ สามารถนำเข้าข้อมูล หรือข้อมูลสามารถถูกคิวรี่ได้โดยตรงโดยใช้ DirectQuery หรือการเชื่อมต่อตรงกับ SQL Server Analysis Services

แหล่งข้อมูลเหล่านี้จะใช้เฉพาะกับรายงาน Power BI ที่ใช้ภายในเซิร์ฟเวอร์รายงาน Power BI สำหรับข้อมูลเกี่ยวกับแหล่งข้อมูลที่สนับสนุนรายงานที่มีการแบ่งหน้า (.rdl) ดูที่[ข้อมูลแหล่งข้อมูลที่สนับสนุนโดย Reporting Services](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs)

> [!IMPORTANT]
> แหล่งข้อมูลทั้งหมดในรายงาน Power BI Desktop ต้องสนับสนุนการกำหนดค่าการรีเฟรชตามกำหนดเวลา
>  

## <a name="list-of-supported-data-sources"></a>รายการของแหล่งข้อมูลทีรองรับ

แหล่งข้อมูลอื่น ๆ อาจใช้ได้แม้ว่าจะไม่ได้อยูในรายการที่รองรับ

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
| Azure Blob Storage |ใช่ |ใช่ |ไม่ใช่ |
| Azure Data Lake Store |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure HDInsight (HDFS) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure HDInsight (Spark) |ใช่ |ใช่ |ไม่ใช่ |
| Azure Table Storage |ใช่ |ใช่ |ไม่ใช่ |
| Dynamics 365 (online) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Facebook |ใช่ |ไม่ใช่ |ไม่ใช่ |
| โฟลเดอร์ |ใช่ |ใช่ |ไม่ใช่ |
| Google Analytics |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ไฟล์ Hadoop (HDFS) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล IBM DB2 |ใช่ |ใช่ |ไม่ใช่ |
| Impala |ใช่ |ไม่ใช่ |ไม่ใช่ |
| JSON |ใช่ |ใช่ |ไม่ใช่ |
| Microsoft Exchange |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Microsoft Exchange Online |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล MySql |ใช่ |ใช่ |ไม่ใช่ |
| OData Feed |ใช่ |ใช่ |ไม่ใช่ |
| ODBC |ใช่ |ใช่ |ไม่ใช่ |
| OLE DB |ใช่ |ใช่ |ไม่ใช่ |
| ฐานข้อมูล Oracle |ใช่ |ใช่ |ใช่ |
| ฐานข้อมูล PostgreSQL |ใช่ |ใช่ |ไม่ใช่ |
| Power BI service |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| R Script |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Salesforce Objects |ใช่ |ไม่ใช่ |ไม่ใช่ |
| รายงาน Salesforce |ใช่ |ไม่ใช่ |ไม่ใช่ |
| เซิร์ฟเวอร์ SAP Business Warehouse |ใช่ |ใช่ |ใช่ |
| ฐานข้อมูล SAP HANA |ใช่ |ใช่ |ใช่ |
| โฟลเดอร์ SharePoint (ภายในองค์กร) |ใช่ |ใช่ |ไม่ใช่ |
| รายการ SharePoint (ภายในองค์กร) |ใช่ |ใช่ |ไม่ใช่ |
| รายการ SharePoint Online |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Snowflake |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล Sybase |ใช่ |ใช่ |ไม่ใช่ |
| ฐานข้อมูล Teradata |ใช่ |ใช่ |ใช่ |
| Text/CSV |ใช่ |ใช่ |ไม่ใช่ |
| เว็บ |ใช่ |ใช่ |ไม่ใช่ |
| XML |ใช่ |ใช่ |ไม่ใช่ |
| appFigures (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล Azure Analysis Services |ใช่ |ไม่ใช่ |ใช่ |
| Azure Cosmos DB (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure HDInsight Spark (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Common Data Service (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| comScore Digital Analytix (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Dynamics 365 for Customer Insights (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Dynamics 365 for Financials (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| GitHub (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Google BigQuery (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล IBM Informix (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| IBM Netezza (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Kusto (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| MailChimp (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Microsoft Azure Consumption Insights (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Mixpanel (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Planview Enterprise (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Projectplace (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| QuickBooks Online (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Smartsheet |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Spark (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| SparkPost (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| SQL Sentry (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Stripe (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| SweetIQ (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Troux (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Twilio (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| tyGraph (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Vertica (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Visual Studio Team Services (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Webtrends (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Zendesk (Beta) |ใช่ |ไม่ใช่ |ไม่ใช่ |

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
| Azure Blob Storage |ใช่ |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure Data Lake Store |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure HDInsight (HDFS) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure HDInsight (Spark) |ใช่ |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure Table Storage |ไม่ใช่ |ใช่ |ไม่ใช่ |ไม่ใช่ |
| Dynamics 365 (online) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Facebook |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| โฟลเดอร์ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ใช่ |
| Google Analytics |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Hadoop File (HDFS) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล IBM DB2 |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| Impala |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Microsoft Exchange |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Microsoft Exchange Online |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล MySql |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| OData Feed |ใช่ |ใช่ |ใช่ |ใช่ |
| ODBC |ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| OLE DB |ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| ฐานข้อมูล Oracle |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| ฐานข้อมูล PostgreSQL |ไม่ใช่ |ไม่ใช่ |ใช่ |ไม่ใช่ |
| Power BI service |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| R Script |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Salesforce Objects |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| รายงาน Salesforce |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| เซิร์ฟเวอร์ SAP Business Warehouse |ไม่ใช่ |ไม่ใช่ |ใช่ |ไม่ใช่ |
| ฐานข้อมูล SAP HANA |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| โฟลเดอร์ SharePoint (ภายในองค์กร) |ใช่ |ไม่ใช่ |ไม่ใช่ |ใช่ |
| รายการ SharePoint (ภายในองค์กร) |ใช่ |ไม่ใช่ |ไม่ใช่ |ใช่ |
| รายการ SharePoint Online |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Snowflake |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล Sybase |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| ฐานข้อมูล Teradata |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |
| appFigures (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure Analysis Services database (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure Cosmos DB (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Azure HDInsight Spark (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Common Data Service (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| comScore Digital Analytix (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Dynamics 365 for Customer Insights (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Dynamics 365 for Financials (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| GitHub (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Google BigQuery (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| IBM Informix database (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| IBM Netezza (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Kusto (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| MailChimp (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Microsoft Azure Consumption Insights (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Mixpanel (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Planview Enterprise (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Projectplace (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| QuickBooks Online (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Smartsheet |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Spark (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| SparkPost (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| SQL Sentry (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Stripe (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| SweetIQ (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Troux (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Twilio (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| tyGraph (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Vertica (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Visual Studio Team Services (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Webtrends (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |
| Zendesk (Beta) |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |ไม่ใช่ |

## <a name="list-of-supported-authentication-methods-for-directquery"></a>รายการของวิธีการรับรองตัวตนได้รับการรองรับสำหรับ DirectQuery

เซิร์ฟเวอร์รายงาน power BI ไมรองรับการรับรองตัวตน OAuth สำหรับ DirectQuery

| **แหล่งข้อมูล** | **การรับรองตัวตนแบบไม่ระบุชื่อ** | **คีย์ตรวจสอบตัวตน** | **ชื่อผู้ใช้และรหัสผ่าน** | **รับรองตัวตนของ Windows** | **Integrated Windows Authentication** |
| --- | --- | --- | --- | --- | --- |
| ฐานข้อมูล SQL Server |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |ใช่ |
| SQL Server Analysis Services |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |ใช่ |
| ฐานข้อมูล Azure SQL |ไม่ใช่ |ไม่ใช่ |ใช่ |ไม่ใช่ |ไม่ใช่ |
| คลังข้อมูล Azure SQL |ไม่ใช่ |ไม่ใช่ |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล Oracle |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |ใช่ |
| เซิร์ฟเวอร์ SAP Business Warehouse |ไม่ใช่ |ไม่ใช่ |ใช่ |ไม่ใช่ |ไม่ใช่ |
| ฐานข้อมูล SAP HANA |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |ไม่ใช่ |
| ฐานข้อมูล Teradata |ไม่ใช่ |ไม่ใช่ |ใช่ |ใช่ |ใช่ |


## <a name="next-steps"></a>ขั้นตอนถัดไป
ตอนนี้ คุณได้เชื่อมต่อกับแหล่งข้อมูลของคุณแล้ว [สร้างรายงาน Power BI](quickstart-create-powerbi-report.md) โดยใช้ข้อมูลจากแหล่งข้อมูลนั้น

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](https://community.powerbi.com/)


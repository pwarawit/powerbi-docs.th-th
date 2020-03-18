---
title: แหล่งข้อมูล Power BI
description: บทความนี้แสดงรายการแหล่งข้อมูลที่ Power BI สนับสนุน รวมถึงข้อมูลเกี่ยวกับ DirectQuery และเกตเวย์ข้อมูลภายในองค์กร
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/10/2020
ms.author: kfollis
ms.openlocfilehash: 1853e710958b5bed0dad011594d9e04ccc99842d
ms.sourcegitcommit: 87b7cb4a2e626711b98387edaa5ff72dc26262bb
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/10/2020
ms.locfileid: "79041688"
---
# <a name="power-bi-data-sources"></a>แหล่งข้อมูล Power BI

ตารางต่อไปนี้แสดงแหล่งข้อมูลที่ Power BI สนับสนุนสำหรับชุดข้อมูล รวมถึงข้อมูลเกี่ยวกับ DirectQuery และเกตเวย์ข้อมูลภายในองค์กร สำหรับข้อมูลเกี่ยวกับกระแสข้อมูล ให้ดูที่ [เชื่อมต่อกับแหล่งข้อมูลสำหรับ Power BI กระแสข้อมูล](service-dataflows-data-sources.md)

> [!NOTE]
> มีตัวเชื่อมต่อข้อมูลจำนวนมากสำหรับ Power BI Desktop ที่จำเป็นต้องใช้ Internet Explorer 10 (หรือใหม่กว่า) สำหรับการรับรองความถูกต้อง 


| แหล่งข้อมูล | เชื่อมต่อจากเดสก์ท็อป | เชื่อมต่อและรีเฟรชจากบริการ | DirectQuery/Live Connection | เกตเวย์ (ที่รองรับ) | เกตเวย์ (จำเป็น) |
|---|---|---|---|---|---|---|---|
| ฐานข้อมูล Access | ใช่ | ใช่ | ไม่ใช่ | ใช่ <sup>1</sup> | ใช่ |
| ActiveDirectory | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ใช่ |
| Adobe Analytics | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Amazon Redshift | ใช่ | ใช่ | ใช่ | ใช่ | ไม่ใช่ |
| appFigures | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| คิวบ์ AtScale | ใช่ | ใช่ | ใช่ | ใช่ | ไม่ใช่ |
| Azure Analysis Services | ใช่ | ใช่ | ใช่ | ใช่ <sup>2</sup> | ไม่ใช่ |
| พื้นที่เก็บข้อมูล Azure Blob | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ |
| Azure Cosmos DB | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Azure Cost Management | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Azure Data Explorer (Kusto) | ใช่ | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ |
| Azure Data Lake Storage Gen1 | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Azure Data Lake Storage Gen2 | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ |
| Azure DevOps | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Azure DevOps Server | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ใช่ |
| Azure HDInsight (HDFS) | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Azure HDInsight Spark | ใช่ | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ |
| ฐานข้อมูล Azure SQL | ใช่ | ใช่ | ใช่ | ใช่ <sup>2</sup> | ไม่ใช่ |
| คลังข้อมูล Azure SQL | ใช่ | ใช่ | ใช่ | ใช่ <sup>2</sup> | ไม่ใช่ |
| พื้นที่เก็บข้อมูล Azure Table | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ |
| BI Connector | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| BI360 - การรายงานการจัดทำงบประมาณและการเงิน | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Common Data Service | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Data.World - รับชุดข้อมูล | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Denodo | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| Dremio | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| Dynamics 365 (ออนไลน์) | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Dynamics 365 Business Central | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Dynamics 365 Business Central (ภายในองค์กร) | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Dynamics 365 Customer Insights | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Dynamics NAV | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| แหล่งข้อมูล Emigo | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Entersoft Business Suite | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Essbase | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| Exasol | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| Excel | ใช่ <sup>3</sup> | ใช่ <sup>3</sup> | ไม่ใช่ | ใช่ <sup>3</sup> | ไม่ใช่ <sup>4</sup> |
| Facebook | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| ไฟล์ | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ใช่ |
| โฟลเดอร์ | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ใช่ |
| GitHub | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Google Analytics | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Google BigQuery | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| ไฟล์ Hadoop (HDFS) | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| HDInsight Interactive Query | ใช่ | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ |
| IBM DB2 | ใช่ | ใช่ | ใช่ | ใช่ | ไม่ใช่ |
| ฐานข้อมูล IBM Informix | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ |
| IBM Netezza | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| Impala | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| Indexima | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| Industrial App Store | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| เส้นตารางข้อมูล | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| InterSystems IRIS | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| คลังข้อมูล Intune | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Jethro ODBC | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| JSON | ใช่ | ใช่ | ไม่ใช่ | ใช่** | ไม่ใช่ <sup>4</sup> |
| Kyligence Enterprise | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| MailChimp | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Marketo | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| MarkLogic ODBC | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| Microsoft Azure Consumption Insights | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Microsoft Exchange | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ |
| Microsoft Exchange Online | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| การรักษาความปลอดภัยของ Microsoft Graph | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ |
| Mixpanel | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| MySQL | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ใช่ |
| OData | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ |
| ODBC | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ใช่ |
| Oledb | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ใช่ |
| Oracle | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| Paxata | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ |
| PDF | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ <sup>4</sup> |
| Planview Enterprise One - CMT | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Planview Enterprise One - PRM | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Planview Projectplace | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| PostgreSQL | ใช่ | ใช่ | ใช่ | ใช่ | ไม่ใช่ |
| กระแสข้อมูล Power BI | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| ชุดข้อมูล Power BI | ใช่ | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ |
| กระแสข้อมูล Power Platform | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| สคริปต์ Python | ใช่ | ใช่ <sup>5</sup> | ไม่ใช่ | ใช่ <sup>5</sup> | ใช่ |
| QubolePresto | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| Quick Base | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ใช่ |
| QuickBooks Online | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| สคริปต์ R | ใช่ | ใช่ <sup>5</sup> | ไม่ใช่ | ใช่ <sup>5</sup> | ไม่ใช่ |
| Roamler | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ |
| ออบเจ็กต์ Salesforce | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| รายงาน Salesforce | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| เซิร์ฟเวอร์ข้อความ SAP Business Warehouse | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| เซิร์ฟเวอร์ SAP Business Warehouse | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| SAP HANA | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| โฟลเดอร์ SharePoint | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ <sup>4</sup> |
| รายการ SharePoint | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ <sup>4</sup> |
| รายการ SharePoint Online | ใช่ | ใช่ | ไม่ใช่ | ใช่ <sup>2</sup> | ไม่ใช่ |
| Smartsheet | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Snowflake | ใช่ | ใช่ | ใช่ | ใช่ | ไม่ใช่ |
| Spark | ใช่ | ใช่ | ใช่ | ใช่ | ไม่ใช่ |
| SparkPost | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| SQL Server | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| SQL Server Analysis Services | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| Stripe | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| SurveyMonkey | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ |
| SweetIQ | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Sybase | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ใช่ |
| TeamDesk | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ |
| Tenforce | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Teradata | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| Text/CSV | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ <sup>4</sup> |
| Twilio | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| tyGraph | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Vertica | ใช่ | ใช่ | ใช่ | ใช่ | ใช่ |
| เว็บ | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ใช่ <sup>6</sup> |
| Webtrends | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| Workforce Dimensions | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ |
| XML | ใช่ | ใช่ | ไม่ใช่ | ใช่ | ไม่ใช่ <sup>4</sup> |
| Zendesk | ใช่ | ใช่ | ไม่ใช่ | ไม่ใช่ | ไม่ใช่ |
| | | | | | | | |

<sup>1</sup> ได้รับการสนับสนุนกับ[ตัวให้บริการ ACE OLEDB](https://www.microsoft.com/download/details.aspx?id=54920)ที่ติดตั้งอยู่บนเครื่องเดียวกันเป็นเกตเวย์

<sup>2</sup> ได้รับการรองรับด้วยฟังก์ชัน M เดียวกับรุ่นในองค์กรที่ทำให้เกิดตัวเลือกการรับรองความถูกต้องแบบจำกัด (เกตเวย์ไม่สนับสนุน OAuth)

<sup>3</sup> ไฟล์ Excel 1997-2003 (.xls) จำเป็นต้องใช้[ตัวให้บริการ ACE OLEDB](https://www.microsoft.com/download/details.aspx?id=54920)

<sup>4</sup>จำเป็นสำหรับรุ่นภายในองค์กรของเทคโนโลยี

<sup>5</sup> ได้รับการสนับสนุนเฉพาะด้วย[เกตเวย์ส่วนบุคคล](service-gateway-personal-mode.md)เท่านั้น

<sup>6</sup> จำเป็นสำหรับฐานข้อมูล .html .xls และ Access

## <a name="single-sign-on-sso-for-directquery-sources"></a>การลงชื่อเข้าระบบครั้งเดียว (SSO) สำหรับแหล่งข้อมูล DirectQuery

เมื่อเปิดใช้งานตัวเลือก SSO และผู้ใช้ของคุณจะเข้าถึงรายงานที่สร้างขึ้นบนยอดของแหล่งข้อมูล Power BI จะส่งข้อมูลประจำตัว Azure AD ที่รับรองความถูกต้องของผู้ใช้ในการคิวรีไปยังแหล่งข้อมูลเบื้องต้น ซึ่งจะช่วยให้ Power BI เป็นไปตามการตั้งค่าความปลอดภัยที่มีการกำหนดค่าในระดับแหล่งข้อมูล
ตัวเลือก SSO จะมีผลต่อชุดข้อมูลทั้งหมดที่ใช้แหล่งข้อมูลนี้ แต่จะไม่มีผลต่อวิธีการรับรองความถูกต้องที่ใช้สำหรับสถานการณ์สมมติการนำเข้า แหล่งข้อมูลต่อไปนี้สนับสนุน SSO สำหรับการเชื่อมต่อผ่านทาง DirectQuery:

- ฐานข้อมูล Azure SQL
- คลังข้อมูล Azure SQL
- Impala
- SAP HANA
- SAP BW
- SAP BW Message Server
- Snowflake
- Spark
- SQL Server
- Teradata

> [!Note]
> ไม่รองรับ Azure Multi-Factor Authentication (MFA) ผู้ใช้ที่ต้องการใช้ SSO กับDirectQuery ต้องได้รับการยกเว้นจาก MFA

## <a name="next-steps"></a>ขั้นตอนถัดไป

[เชื่อมต่อกับข้อมูลใน Power BI Desktop](desktop-quickstart-connect-to-data.md)  
[การใช้ DirectQuery ใน Power BI](desktop-directquery-about.md)  
[ข้อมูลสดของ SQL Server Analysis Services ใน Power BI](sql-server-analysis-services-tabular-data.md)  
[เกตเวย์ข้อมูลภายในองค์กรคืออะไร](service-gateway-onprem.md)  

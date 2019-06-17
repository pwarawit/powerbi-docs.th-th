---
title: แหล่งข้อมูลที่สนับสนุนโดย DirectQuery Power BI
description: รับรายการที่แหล่งข้อมูลสามารถใช้ DirectQuery ได้
author: davidiseminger
ms.author: davidi
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/31/2019
LocalizationGroup: Connect to data
ms.openlocfilehash: dae93a2555101a42f072158f8536319783b3f973
ms.sourcegitcommit: aef57ff94a5d452d6b54a90598bd6a0dd1299a46
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/07/2019
ms.locfileid: "66809111"
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>แหล่งข้อมูลที่สนับสนุนโดย DirectQuery Power BI

**Power BI Desktop**และ**บริการ Power BI**มีแหล่งข้อมูลมากมายที่คุณสามารถเชื่อมต่อและรับการเข้าถึงข้อมูลได้ บทความนี้อธิบายว่าจะมีการเชื่อมต่อแหล่งข้อมูลใดสำหรับ Power BI ที่สนับสนุนวิธีการเชื่อมต่อที่เรียกว่า **DirectQuery** สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ DirectQuery ดู[ **DirectQuery ใน Power BI**](desktop-directquery-about.md)

แหล่งข้อมูลต่อไปนี้สนับสนุน DirectQuery ใน Power BI:

* Amazon Redshift
* AtScale (เบต้า)
* ตัวสำรวจข้อมูลของ Azure
* Azure HDInsight Spark
* [ฐานข้อมูล Azure SQL](service-azure-sql-database-with-direct-connect.md)
* [คลังข้อมูล Azure SQL](service-azure-sql-data-warehouse-with-direct-connect.md)
* Google BigQuery
* คิวรีแบบโต้ตอบ HDInsight
* ฐานข้อมูล IBM DB2
* IBM Netezza
* Impala (รุ่น 2.x)
* ฐานข้อมูล Oracle (เวอร์ชัน 12 หรือสูงกว่า)
* Oracle Essbase
* เซิร์ฟเวอร์แอปพลิเคชัน SAP Business Warehouse
* เซิร์ฟเวอร์ข้อความ SAP Business Warehouse
* SAP HANA
* Snowflake
* Spark (เวอร์ชัน 0.9 หรือสูงกว่า)
* SQL Server
* ฐานข้อมูล Teradata
* Vertica

แหล่งข้อมูลที่มี **(รุ่น Beta)** หรือ **(ตัวอย่าง)** หลังชื่อจะถูกเปลี่ยน และไม่ได้รับการสนับสนุนสำหรับการใช้งานการผลิต นอกจากนี้อาจไม่สนับสนุนหลังจากเผยแพร่รายงานไปยัง**บริการ Power BI**ด้วย ซึ่งหมายความว่าการเปิดรายงานที่เผยแพร่หรือการดูชุดข้อมูลอาจทำให้เกิดข้อผิดพลาดได้

ความแตกต่างเดียวระหว่างแหล่งข้อมูล **(Beta)** และ **(ตัวอย่าง)** คือ แหล่งข้อมูล **(ตัวอย่าง)** ต้องเปิดใช้งานเป็นคุณลักษณะการแสดงตัวอย่างก่อนที่แหล่งข้อมูลเหล่านี้จะพร้อมสำหรับการใช้งาน เมื่อต้องการเปิดใช้งานตัวเชื่อมต่อข้อมูล **(ตัวอย่าง)** ใน**Power BI Desktop**ไปที่**ไฟล์ > ตัวเลือกและการตั้งค่า > ตัวเลือก** แล้วเลือก**คุณลักษณะตัวอย่าง**

> [!NOTE]
> คิวรี DirectQuery ไปยัง SQL Server จำเป็นต้องรับรองความถูกต้องโดยใช้ข้อมูลประจำตัวการรับรองความถูกต้อง Windows ปัจจุบัน หรือข้อมูลประจำตัวของฐานข้อมูล เพื่อสร้างเข้าถึง ข้อมูลประจำตัวอื่น ๆ ไม่ได้รับการสนับสนุน
>

## <a name="on-premises-gateway-requirements"></a>ข้อกำหนดของเกตเวย์ภายในองค์กร
ตารางต่อไปนี้ระบุว่าต้องมี**เกตเวย์ข้อมูลภายในองค์กร**ในการเชื่อมต่อกับแหล่งข้อมูลที่ระบุหรือไม่ หลังจากเผยแพร่รายงานไปยัง**บริการ Power BI**

| แหล่งที่มา | ต้องมีเกตเวย์หรือไม่? |
| --- | --- |
| Amazon Redshift |ไม่ใช่ |
| Azure HDInsight Spark (Beta) |ไม่ใช่ |
| ฐานข้อมูล Azure SQL |ไม่ใช่ |
| คลังข้อมูล Azure SQL |ไม่ใช่ |
| Google BigQuery |ไม่ใช่ |
| IBM Netezza |ใช่ |
| Impala (รุ่น 2.x) |ใช่ |
| ฐานข้อมูล Oracle |ใช่ |
| เซิร์ฟเวอร์แอปพลิเคชัน SAP Business Warehouse |ใช่ |
| เซิร์ฟเวอร์ข้อความ SAP Business Warehouse |ยังไม่สนับสนุนใน**บริการ Power BI** |
| SAP HANA |ใช่ |
| Snowflake |ใช่ |
| Spark (รุ่น Beta) (เวอร์ชัน 0.9 หรือสูงกว่า) |ใช่ |
| เซิร์ฟเวอร์ SQL |ใช่ |
| ฐานข้อมูล Teradata |ใช่ |

## <a name="single-sign-on-sso-for-directquery-sources"></a>การลงชื่อเข้าระบบครั้งเดียว (SSO) สำหรับแหล่งข้อมูล DirectQuery

เมื่อเปิดใช้งานตัวเลือก SSO และผู้ใช้ของคุณจะเข้าถึงรายงานที่สร้างขึ้นบนยอดของแหล่งข้อมูล Power BI จะส่งข้อมูลประจำตัว Azure AD ที่รับรองความถูกต้องของผู้ใช้ในการคิวรีไปยังแหล่งข้อมูลเบื้องต้น ซึ่งจะช่วยให้ Power BI เป็นไปตามการตั้งค่าความปลอดภัยที่มีการกำหนดค่าในระดับแหล่งข้อมูล

ตัวเลือก SSO จะมีผลต่อชุดข้อมูลทั้งหมดที่ใช้แหล่งข้อมูลนี้ แต่จะไม่มีผลต่อวิธีการรับรองความถูกต้องที่ใช้สำหรับสถานการณ์สมมติการนำเข้า แหล่งข้อมูลต่อไปนี้สนับสนุน SSO สำหรับการเชื่อมต่อผ่านทาง DirectQuery:

- ฐานข้อมูล Azure SQL
- คลังข้อมูล Azure SQL
- Impala
- SAP HANA
- SAP BW
- Spark
- SQL Server
- Teradata

> [!Note]
> ไม่รองรับ Azure Multi-Factor Authentication (MFA) ผู้ใช้ที่ต้องการใช้ SSO กับDirectQuery ต้องได้รับการยกเว้นจาก MFA

## <a name="next-steps"></a>ขั้นตอนถัดไป
สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ DirectQuery โปรดดูที่ทรัพยากรดังต่อไปนี้:

* [DirectQuery ใน Power BI](desktop-directquery-about.md)
* [DirectQuery และ SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery และ SAP BW](desktop-directquery-sap-bw.md)
* [เกตเวย์ข้อมูลภายในองค์กร](service-gateway-onprem.md)


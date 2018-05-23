---
title: แหล่งข้อมูลที่สนับสนุนโดย DirectQuery Power BI
description: รับรายการที่แหล่งข้อมูลสามารถใช้ DirectQuery ได้
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 03/09/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: e36f8596141ab5d7ad82ffecb808b7d684334923
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/17/2018
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>แหล่งข้อมูลที่สนับสนุนโดย DirectQuery Power BI
**Power BI Desktop**และ**บริการ Power BI**มีแหล่งข้อมูลมากมายที่คุณสามารถเชื่อมต่อและรับการเข้าถึงข้อมูลได้ บทความนี้อธิบายว่าจะมีการเชื่อมต่อแหล่งข้อมูลใดสำหรับ Power BI ที่สนับสนุนวิธีการเชื่อมต่อที่เรียกว่า **DirectQuery** สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ DirectQuery ดู[ **DirectQuery ใน Power BI**](desktop-directquery-about.md)

แหล่งข้อมูลต่อไปนี้สนับสนุน DirectQuery ใน Power BI:

* Amazon Redshift
* Azure HDInsight Spark
* ฐานข้อมูล Azure SQL
* คลังข้อมูล Azure SQL
* Google BigQuery
* IBM Netezza
* Impala (รุ่น 2.x)
* ฐานข้อมูล Oracle (เวอร์ชัน 12 หรือสูงกว่า)
* เซิร์ฟเวอร์แอปพลิเคชันของ SAP Business Warehouse
* เซิร์ฟเวอร์ข้อความของ SAP Business Warehouse (Beta)
* SAP HANA
* Snowflake
* Spark (รุ่น Beta) (เวอร์ชัน 0.9 หรือสูงกว่า)
* เซิร์ฟเวอร์ SQL
* ฐานข้อมูล Teradata
* Vertica (รุ่น Beta)

แหล่งข้อมูลที่มี **(Beta)** หรือ **(ตัวอย่าง)** หลังชื่อของแหล่งข้อมูลเหล่านี้จะเปลี่ยนไป และไม่สนับสนุนสำหรับการใช้งานการผลิต นอกจากนี้อาจไม่สนับสนุนหลังจากเผยแพร่รายงานไปยัง**บริการ Power BI**ด้วย ซึ่งหมายความว่าการเปิดรายงานที่เผยแพร่หรือการดูชุดข้อมูลอาจทำให้เกิดข้อผิดพลาดได้

ความแตกต่างเดียวระหว่างแหล่งข้อมูล **(Beta)** และ **(ตัวอย่าง)** คือ แหล่งข้อมูล **(ตัวอย่าง)** ต้องเปิดใช้งานเป็นคุณลักษณะการแสดงตัวอย่างก่อนที่แหล่งข้อมูลเหล่านี้จะพร้อมสำหรับการใช้งาน เมื่อต้องการเปิดใช้งานตัวเชื่อมต่อข้อมูล **(ตัวอย่าง)** ใน**Power BI Desktop**ไปที่**ไฟล์ > ตัวเลือกและการตั้งค่า > ตัวเลือก** แล้วเลือก**คุณลักษณะตัวอย่าง** 

## <a name="on-premises-gateway-requirements"></a>ข้อกำหนดของเกตเวย์ภายในองค์กร
ตารางต่อไปนี้ระบุว่าต้องมี**เกตเวย์ข้อมูลภายในองค์กร**ในการเชื่อมต่อกับแหล่งข้อมูลที่ระบุหรือไม่ หลังจากเผยแพร่รายงานไปยัง**บริการ Power BI**

| แหล่งที่มา | ต้องมีเกตเวย์หรือไม่? |
| --- | --- |
| เซิร์ฟเวอร์ SQL |ใช่ |
| ฐานข้อมูล Azure SQL |ไม่ใช่ |
| คลังข้อมูล Azure SQL |ไม่ใช่ |
| SAP HANA |ใช่ |
| ฐานข้อมูล Oracle |ใช่ |
| ฐานข้อมูล Teradata |ใช่ |
| Amazon Redshift |ไม่ใช่ |
| Impala (รุ่น 2.x) |ใช่ |
| Snowflake |ใช่ |
| Spark (รุ่น Beta) (เวอร์ชัน 0.9 หรือสูงกว่า) |ยังไม่สนับสนุนใน**บริการ Power BI** |
| Azure HDInsight Spark |ไม่ใช่ |
| IBM Netezza |ใช่ |
| เซิร์ฟเวอร์แอปพลิเคชันของ SAP Business Warehouse |ใช่ |
| เซิร์ฟเวอร์ข้อความของ SAP Business Warehouse |ยังไม่สนับสนุนใน**บริการ Power BI** |
| Google BigQuery |ไม่ใช่ |


## <a name="next-steps"></a>ขั้นตอนถัดไป
สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ DirectQuery โปรดดูที่ทรัพยากรดังต่อไปนี้:

* [DirectQuery ใน Power BI](desktop-directquery-about.md)
* [DirectQuery และ SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery และ SAP BW](desktop-directquery-sap-bw.md)
* [เกตเวย์ข้อมูลภายในองค์กร](service-gateway-onprem.md)


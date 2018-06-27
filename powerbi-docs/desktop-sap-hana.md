---
title: ใช้ SAP HANA ใน Power BI Desktop
description: ใช้ SAP HANA ใน Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 03/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 44dff39d043bb7a71c01b5103cfdf65e7d5e33cb
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/26/2018
ms.locfileid: "34287612"
---
# <a name="use-sap-hana-in-power-bi-desktop"></a>ใช้ SAP HANA ใน Power BI Desktop
ตอนนี้คุณสามารถเข้าถึงฐานข้อมูล**SAP HANA**ได้ด้วย Power BI Desktop ในการใช้**SAP HANA**จะต้องติดตั้งไดรเวอร์ ODBC SAP Hana บนคอมพิวเตอร์ผู้รับบริการท้องถิ่นเพื่อให้การเชื่อมต่อข้อมูล**SAP HANA**ของ Power BI Desktop สามารถทำงานได้อย่างเหมาะสม คุณสามารถดาวน์โหลดไดรเวอร์ ODBC SAP HANA ได้จาก[ศูนย์ดาวน์โหลดซอฟต์แวร์ SAP](https://support.sap.com/swdc) ในศูนย์ดาวโหลดซอฟต์แวร์ ให้ค้นหา SAP HANA CLIENT สำหรับคอมพิวเตอร์ที่ใช้ Windows เนื่องด้วย**ศูนย์ดาวน์โหลดซอฟต์แวร์ SAP**นั้นมีการเปลี่ยนแปลงโครงสร้างบ่อยครั้ง คำแนะนำการนำทางที่เฉพาะเจาะจงมากกว่านี้ในเว็บไซต์ดังกล่าวจึงไม่พร้อมใช้งาน

ในการเชื่อมต่อไปยังฐานข้อมูล**SAP HANA** ให้เลือก**รับข้อมูล > ฐานข้อมูล > ฐานข้อมูล SAP HANA**ตามที่แสดงในรูปต่อไปนี้:

![](media/desktop-sap-hana/sap-hana-1.png)

เมื่อทำการเชื่อมต่อกับฐานข้อมูล SAP HANA ให้ระบุชื่อเซิร์ฟเวอร์และพอร์ตในรูปแบบ*เซิร์ฟเวอร์:พอร์ต* รูปต่อไปนี้แสดงตัวอย่างเซิร์ฟเวอร์ชื่อว่า*ServerXYZ*และพอร์ต*30015* 

![](media/desktop-sap-hana/sap-hana-2.png)

ในรุ่นนี้**SAP HANA**ในโหมด[DirectQuery](desktop-directquery-sap-hana.md)ได้รับการสนับสนุนการใช้งานใน Power BI Desktop และ บริการ Power BI และคุณสามารถเผยแพร่การอัปโหลดรายงานที่ใช้**SAP Hana**ใน โหมด DirectQuery ไปยังบริการ Power BI คุณยังสามารถเผยแพร่ และอัปโหลดรายงานไปยังบริการ Power BI เมื่อไม่ได้ใช้**SAP HANA**ในโหมด DirectQuery ได้อีกด้วย

### <a name="supported-features-for-sap-hana"></a>ฟีเจอร์ที่ได้รับการสนับสนุนสำหรับ SAP HANA
รุ่นนี้มีความสามารถสำหรับ**SAP HANA**มากมาย ดังที่แสดงในรายการต่อไปนี้:

* ตัวเชื่อมต่อ Power BI ของ**SAP HANA**ใช้ไดร์ฟเวอร์ SAP ODBC เพื่อประสบการณ์การใช้งานที่ดีที่สุดของผู้ใช้
* **SAP HANA**สนับสนุนทั้งโหมด DirectQuery และตัวเลือกการนำเข้าข้อมูลต่าง ๆ
* Power BI สนับสนุนโมเดลข้อมูล HANA (เช่น มุมมองการวิเคราะห์ และการคำนวณ) และมีตัวนำทางที่มีประสิทธิภาพมากที่สุด
* ด้วย**SAP HANA**คุณยังสามารถใช้ฟีเจอร์ SQL โดยตรงเพื่อเชื่อมต่อตารางแถวและคอลัมน์
* รวมถึงการนำทางที่มีประสิทธิภาพสูงสุดสำหรับโมเดล HANA
* Power BI สนับสนุนตัวแปรต่าง ๆ ของ**SAP HANA** และพารามิเตอร์ที่นำเข้ามา

### <a name="installing-the-sap-hana-odbc-driver"></a>กำลังติดตั้งไดร์ฟเวอร์ ODBC SAP HANA
### <a name="limitations-of-sap-hana"></a>ขีดจำกัดของ SAP HANA
ในการใช**SAP HANA**้นั้นมีข้อจำกัดบางประการตามที่แสดงไว้ด้านล่าง:

* สตริง NVARCHAR จะถูกตัดทอนให้อยู่ที่ความยาวสูงสุด 4000 ตัวอักขระ Unicode
* ไม่สนับสนุน SMALLDECIMAL
* ไม่สนับสนุน VARBINARY
* วันที่ใช้งานได้ อยู่ระหว่าง 1899/12/30 และ 9999/12/31


## <a name="next-steps"></a>ขั้นตอนถัดไป
สำหรับข้อมูลเพิ่มเติมเกี่ยวก ัDirectQuery กรุณาตรวจดูแหล่งที่มาต่อไปนี้:

* [DirectQuery และ SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery ใน Power BI](desktop-directquery-about.md)
* [แหล่งข้อมูลที่สนับสนุนโดย DirectQuery](desktop-directquery-data-sources.md)


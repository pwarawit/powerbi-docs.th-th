---
title: ใช้ SAP HANA ใน Power BI Desktop
description: ใช้ SAP HANA ใน Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/21/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1932848cb2f8ad7d75e841870265cc22308467c2
ms.sourcegitcommit: a00fe5fb545c3df13b7cd13a701fd6a2b2521a17
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/31/2019
ms.locfileid: "70200876"
---
# <a name="use-sap-hana-in-power-bi-desktop"></a>ใช้ SAP HANA ใน Power BI Desktop
ตอนนี้คุณสามารถเข้าถึงฐานข้อมูล**SAP HANA**ได้ด้วย Power BI Desktop ในการใช้**SAP HANA**จะต้องติดตั้งไดรเวอร์ ODBC SAP Hana บนคอมพิวเตอร์ผู้รับบริการท้องถิ่นเพื่อให้การเชื่อมต่อข้อมูล**SAP HANA**ของ Power BI Desktop สามารถทำงานได้อย่างเหมาะสม คุณสามารถดาวน์โหลดไดรเวอร์ ODBC SAP HANA ได้จาก[ศูนย์ดาวน์โหลดซอฟต์แวร์ SAP](https://support.sap.com/swdc) ในศูนย์ดาวโหลดซอฟต์แวร์ ให้ค้นหา SAP HANA CLIENT สำหรับคอมพิวเตอร์ที่ใช้ Windows เนื่องด้วย**ศูนย์ดาวน์โหลดซอฟต์แวร์ SAP**นั้นมีการเปลี่ยนแปลงโครงสร้างบ่อยครั้ง คำแนะนำการนำทางที่เฉพาะเจาะจงมากกว่านี้ในเว็บไซต์ดังกล่าวจึงไม่พร้อมใช้งาน

ในการเชื่อมต่อไปยังฐานข้อมูล**SAP HANA** ให้เลือก**รับข้อมูล > ฐานข้อมูล > ฐานข้อมูล SAP HANA**ตามที่แสดงในรูปต่อไปนี้:

![](media/desktop-sap-hana/sap-hana-1.png)

เมื่อเชื่อมต่อกับฐานข้อมูล SAP HANA ให้ระบุชื่อเซิร์ฟเวอร์ จากนั้นจากกล่องดรอปดาวน์และป้อนข้อมูล ให้ระบุพอร์ต

ในรุ่นนี้**SAP HANA**ในโหมด[DirectQuery](desktop-directquery-sap-hana.md)ได้รับการสนับสนุนการใช้งานใน Power BI Desktop และ บริการ Power BI และคุณสามารถเผยแพร่การอัปโหลดรายงานที่ใช้**SAP Hana**ใน โหมด DirectQuery ไปยังบริการ Power BI คุณยังสามารถเผยแพร่ และอัปโหลดรายงานไปยังบริการ Power BI เมื่อไม่ได้ใช้**SAP HANA**ในโหมด DirectQuery ได้อีกด้วย

## <a name="supported-features-for-sap-hana"></a>ฟีเจอร์ที่ได้รับการสนับสนุนสำหรับ SAP HANA
รุ่นนี้มีความสามารถสำหรับ**SAP HANA**มากมาย ดังที่แสดงในรายการต่อไปนี้:

* ตัวเชื่อมต่อ Power BI ของ**SAP HANA**ใช้ไดร์ฟเวอร์ SAP ODBC เพื่อประสบการณ์การใช้งานที่ดีที่สุดของผู้ใช้
* **SAP HANA**สนับสนุนทั้งโหมด DirectQuery และตัวเลือกการนำเข้าข้อมูลต่าง ๆ
* Power BI สนับสนุนโมเดลข้อมูล HANA (เช่น มุมมองการวิเคราะห์และการคำนวณ) และมีตัวนำทางที่มีประสิทธิภาพมากที่สุด
* ด้วย**SAP HANA**คุณยังสามารถใช้ฟีเจอร์ SQL โดยตรงเพื่อเชื่อมต่อตารางแถวและคอลัมน์
* รวมถึงการนำทางที่มีประสิทธิภาพสูงสุดสำหรับโมเดล HANA
* Power BI สนับสนุนตัวแปรต่าง ๆ ของ**SAP HANA** และพารามิเตอร์ที่นำเข้ามา
* มุมมองการคำนวณตามคอนเทนเนอร์ HDI
  * การสนับสนุนมุมมองการคำนวณตามคอนเทนเนอร์ HDI ในตัวอย่างสาธารณะในการเปิดตัว Power BI Desktop เมื่อเดือนสิงหาคม 2019 หากต้องการเข้าถึงมุมมองการคำนวณตามคอนเนทเนอร์ HDI ใน Power BI ของคุณ คุณต้องตรวจสอบให้แน่ใจว่าผู้ใช้ฐานข้อมูล HANA ที่คุณใช้งานกับ Power BI มีสิทธิ์ในการเข้าถึงคอนเทนเนอร์รันไทม์ HDI ที่บันทึกมุมมองที่คุณต้องการเข้าถึง เพื่อรับสิทธิ์ในการเข้าถึง คุณต้องสร้างบทบาทที่อนุญาตให้คุณสามารถเข้าถึงคอนเทนเนอร์ HDI ของคุณได้ และกำหนดบทบาทนี้ให้แก่ผู้ใช้ฐานข้อมูล HANA ที่คุณใช้กับ Power BI (ผู้ใช้นี้ต้องมีสิทธิ์ในการอ่านจากตารางระบบในโครงสร้างข้อมูล \_SYS\_BI ตามปกติ) ดูคำแนะนำต่าง ๆ เกี่ยวกับวิธีการสร้างและกำหนดบทบาทฐานข้อมูลอย่างละเอียดในเอกสาร SAP ทางการ [บล็อกโพสต์](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fblogs.sap.com%2F2018%2F01%2F24%2Fthe-easy-way-to-make-your-hdi-container-accessible-to-a-classic-database-user%2F&data=02%7C01%7Cv-adbold%40microsoft.com%7Cf7e0a405fe334598ba0608d7096ef5b4%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636988244476739316&sdata=PuRu61GPRYp34mLuGbQk6gdbRikdgbxfqo8q1RBQtm0%3D&reserved=0)ใน SAP นี้อาจเป็นจุดเริ่มต้นที่ดี
  * โปรดทราบว่ามีข้อจำกัดบางอย่างในปัจจุบันนี้สำหรับตัวแปร HANA ที่ติดตั้งมากับมุมมองการคำนวณตาม HDI ข้อจำกัดเหล่านี้เกิดขึ้นเนื่องจากข้อผิดพลาดในด้าน HANA และจะได้รับการแก้ไขในการเปิดตัว SAP HANA ในอนาคต ข้อจำกัดแรกก็คือตัวแปร HANA ไม่สามารถใช้กับคอลัมน์ที่แชร์จากมุมมองการคำนวณตามคอนเทนเนอร์ HDI ได้ ข้อจำกัดนี้สามารถแก้ไขได้โดยการอัปเกรดเป็น HANA 2 เวอร์ชัน 37.02 ขึ้นไปหรือ HANA 2 เวอร์ชัน 42 ขึ้นไป ข้อจำกัดที่สองคือค่าเริ่มต้นหลายรายการสำหรับตัวแปรและพารามิเตอร์ปัจจุบันไม่สามารถแสดงใน Power BI UI ได้ นอกจากนี้ยังเกิดขึ้นจากข้อผิดพลาดใน SAP HANA อย่างไรก็ตาม SAP ยังไม่ได้ประกาศเกี่ยวกับการแก้ไข

## <a name="limitations-of-sap-hana"></a>ขีดจำกัดของ SAP HANA
ในการใช**SAP HANA**้นั้นมีข้อจำกัดบางประการตามที่แสดงไว้ด้านล่าง:

* สตริง NVARCHAR จะถูกตัดทอนให้อยู่ที่ความยาวสูงสุด 4000 ตัวอักขระ Unicode
* ไม่สนับสนุน SMALLDECIMAL
* ไม่สนับสนุน VARBINARY
* วันที่ใช้งานได้ อยู่ระหว่าง 1899/12/30 และ 9999/12/31


## <a name="next-steps"></a>ขั้นตอนถัดไป
สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ DirectQuery และ SAP HANA กรุณาดูที่แหล่งข้อมูลต่อไปนี้:

* [DirectQuery และ SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery ใน Power BI](desktop-directquery-about.md)
* [แหล่งข้อมูลที่สนับสนุนโดย DirectQuery](desktop-directquery-data-sources.md)
* [เปิดใช้งานการเข้ารหัสสำหรับ SAP HANA](desktop-sap-hana-encryption.md)



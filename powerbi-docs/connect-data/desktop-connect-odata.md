---
title: เชื่อมต่อกับตัวดึงข้อมูล OData ใน Power BI Desktop
description: เชื่อมต่อและใช้ตัวดึงข้อมูล OData ได้อย่างง่ายดายใน Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 9e10d694940bda465e68f54370d87aab15b628ee
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/10/2020
ms.locfileid: "86216485"
---
# <a name="connect-to-odata-feeds-in-power-bi-desktop"></a>เชื่อมต่อกับตัวดึงข้อมูล OData ใน Power BI Desktop
ใน Power BI Desktop คุณสามารถเชื่อมต่อกับ **ตัวดึงข้อมูล OData** และใช้ข้อมูลเบื้องต้นเช่นเดียวกับแหล่งข้อมูลอื่นใน Power BI Desktop ได้

เมื่อต้องการเชื่อมต่อกับตัวดึงข้อมูล OData เลือก**รับข้อมูล > ตัวดึงข้อมูล OData**จาก Ribbon **หน้าหลัก** ใน Power BI Desktop

![ภาพหน้าจอของริบบอนรับข้อมูลใน Power BI Desktop ที่แสดงการเลือกตัวดึงข้อมูล OData](media/desktop-connect-odata/connect-to-odata_1.png)

ในหน้าต่าง**ตัวดึงข้อมูล OData**ที่ปรากฎขึ้น พิมพ์ หรือวาง URL ของตัวดึงข้อมูล OData ของคุณลงในกล่อง และเลือก**ตกลง**

![ภาพหน้าจอของกล่องโต้ตอบตัวดึงข้อมูล OData ที่แสดงเขตข้อมูล URL](media/desktop-connect-odata/connect-to-odata_2.png)

Power BI Desktop เชื่อมต่อกับตัวดึงข้อมูล OData และแสดงตารางที่พร้อมใช้งานและองค์ประกอบข้อมูลอื่น ๆ ในหน้าต่าง**ตัวนำทาง** เมื่อคุณเลือกหนึ่งองค์ประกอบ พื้นที่ด้านขวาของหน้าต่าง**ตัวนำทาง**จะแสดงตัวอย่างของข้อมูล คุณสามารถเลือกตารางต่าง ๆ ได้มากเท่าที่คุณต้องการนำเข้า หน้าต่าง**ตัวนำทาง**จะแสดงตัวอย่างของตารางที่เลือกในปัจจุบัน

![ภาพหน้าจอของกล่องโต้ตอบตัวนำทาง ที่แสดงตัวอย่างของข้อมูลของตารางที่เลือก](media/desktop-connect-odata/connect-to-odata_3.png)

คุณสามารถเลือกปุ่ม**แก้ไข** ซึ่งจะเปิด**ตัวแก้ไขแบบสอบถาม**ขึ้นมา ในหน้าต่างนี้คุณจะสามารถจัดการรูปร่างและเปลี่ยนแปลงข้อมูลจากตัวดึงข้อมูล OData ได้ ก่อนที่จะนำเข้าข้อมูลไปยัง Power BI Desktop หรือคุณสามารถเลือกปุ่ม**โหลด** และนำเข้าองค์ประกอบข้อมูลทั้งหมดที่คุณได้เลือกในช่องแสดงข้อมูลด้านซ้าย

เมื่อเราเลือก**การโหลด** Power BI Desktop จะนำเข้ารายการที่เลือกไว้และแสดงหน้าต่าง**การโหลด**ของความคืบหน้าการนำเข้า

![ภาพหน้าจอของกล่องโต้ตอบการโหลด ที่แสดงความคืบหน้าการนำเข้า](media/desktop-connect-odata/connect-to-odata_4.png)

เมื่อเสร็จสมบูรณ์ Power BI Desktop จะทำตารางที่เลือกและองค์ประกอบข้อมูลอื่น ๆ ที่พร้อมใช้งานในพื้นที่**ช่องข้อมูล** ที่พบบนด้านขวาของตัวมุมมอง*รายงาน*ใน Power BI Desktop

![ภาพหน้าจอของบานหน้าต่างเขตข้อมูล ที่แสดงรายการของตารางที่เลือก](media/desktop-connect-odata/connect-to-odata_5.png)

เท่านี้ก็เรียบร้อย!

ตอนนี้คุณพร้อมที่จะใช้ข้อมูลที่นำเข้าจากตัวดึงข้อมูล OData ใน Power BI Desktop เพื่อสร้างภาพ รายงาน หรือโต้ตอบกับข้อมูลอื่น ๆ ที่คุณอาจต้องการเชื่อมโยงและต้องการนำเข้า เช่น สมุดงาน Excel อื่น ๆ ฐานข้อมูล หรือแหล่งข้อมูลอื่น ๆ

## <a name="next-steps"></a>ขั้นตอนถัดไป
มีข้อมูลหลากหลายประเภทที่คุณสามารถเชื่อมต่อโดยใช้ Power BI Desktop สำหรับข้อมูลเพิ่มเติมเกี่ยวกับแหล่งข้อมูล โปรดดูทรัพยากรต่อไปนี้:

* [Power BI Desktop คืออะไร](../fundamentals/desktop-what-is-desktop.md)
* [แหล่งข้อมูลใน Power BI Desktop](desktop-data-sources.md)
* [จัดรูปทรงและรวมข้อมูลด้วย Power BI Desktop](desktop-shape-and-combine-data.md)
* [เชื่อมต่อกับเวิร์กบุ๊ก Excel ใน Power BI Desktop](desktop-connect-excel.md)   
* [ป้อนข้อมูลลงใน Power BI Desktop โดยตรง](desktop-enter-data-directly-into-desktop.md)   

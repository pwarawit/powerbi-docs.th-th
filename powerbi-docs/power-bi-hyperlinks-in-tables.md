---
title: เพิ่มไฮเปอร์ลิงก์ (URL) ไปยังตารางหรือเมทริกซ์
description: หัวข้อนี้จะสอนวิธีเพิ่มไฮเปอร์ลิงก์ (URL) ไปยังตาราง คุณใช้ Power BI Desktop เพื่อเพิ่มไฮเปอร์ลิงก์ (URL) ไปยังชุดข้อมูล จากนั้น ใน Power BI Desktop หรือบริการของ Power BI คุณสามารถเพิ่มไฮเปอร์ลิงก์เหล่านั้นไปยังตารางหรือเมทริกซ์รายงานของคุณได้
author: maggiesMSFT
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/13/2020
ms.author: maggies
LocalizationGroup: Visualizations
ms.openlocfilehash: ddb54ca91936626b4870b51b86b7fc7f0ac6b2c9
ms.sourcegitcommit: df8bcc65f0df69bf1fc1d47eb06575742eac1622
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2020
ms.locfileid: "75954064"
---
# <a name="add-hyperlinks-urls-to-a-table-or-matrix"></a>เพิ่มไฮเปอร์ลิงก์ (URL) ไปยังตารางหรือเมทริกซ์
หัวข้อนี้จะสอนวิธีเพิ่มไฮเปอร์ลิงก์ (URL) ไปยังตาราง คุณใช้ Power BI Desktop เพื่อเพิ่มไฮเปอร์ลิงก์ (URL) ไปยังชุดข้อมูล คุณสามารถเพิ่มไฮเปอร์ลิงก์เหล่านั้นไปยังตารางหรือเมทริกซ์รายงานของคุณได้ในทั้ง Power BI Desktop หรือบริการ Power BI จากนั้น คุณสามารถแสดงไอคอนของ URL หรือลิงก์ หรือจัดรูปแบบคอลัมน์อื่นเป็นข้อความลิงก์ได้

![ตารางที่มีไฮเปอร์ลิงก์](media/power-bi-hyperlinks-in-tables/power-bi-url-link-text.png)

คุณยังสามารถสร้างไฮเปอร์ลิงก์ใน [กล่องข้อความในรายงาน](service-add-hyperlink-to-text-box.md) ในบริการของ Power BI และ Power BI Desktop และในบริการ Power BI คุณสามารถเพิ่มไฮเปอร์ลิงก์ไปยัง [ไทล์บนแดชบอร์ด](service-dashboard-edit-tile.md) และ [กล่องข้อความบนแดชบอร์ด](service-dashboard-add-widget.md) 


## <a name="format-a-url-as-a-hyperlink-in-power-bi-desktop"></a>จัดรูปแบบ URL เป็นไฮเปอร์ลิงก์ใน Power BI Desktop

คุณสามารถจัดรูปแบบเขตข้อมูล URL เป็นไฮเปอร์ลิงก์ได้ใน Power BI Desktop แต่ไม่สามารถทำได้ในบริการของ Power BI คุณยังสามารถ [จัดรูปแบบไฮเปอร์ลิงก์ใน Excel Power Pivot](#create-a-table-or-matrix-hyperlink-in-excel-power-pivot) ก่อนนำเข้าเวิร์กบุ๊กไปยัง Power BI.

1. ใน Power BI Desktop ถ้าเขตข้อมูลที่มีไฮเปอร์ลิงก์ไม่ปรากฏในชุดข้อมูลของคุณอยู่แล้ว ให้เพิ่ทเป็น[คอลัมน์แบบกำหนดเอง](desktop-common-query-tasks.md)

    > [!NOTE]
    > คุณไม่สามารถสร้างคอลัมน์ในโหมด DirectQuery ได้  แต่ถ้าข้อมูลของคุณมี URL อยู่แล้ว คุณสามารถทำให้ URL เหล่านั้นเป็นไฮเปอร์ลิงก์ได้

2. ในมุมมองข้อมูล เลือกคอลัมน์ 

3. บนแท็บ **การสร้างแบบจำลอง** เลือก **ประเภทข้อมูล** > **URL เว็บ**
   
    ![รายการประเภทข้อมูลแบบดรอปดาวน์](media/power-bi-hyperlinks-in-tables/power-bi-format-web-url.png)

    > [!NOTE]
    > URL ต้องเริ่มต้นด้วยเลขนำหน้าบางอย่าง โปรดดู [ข้อควรพิจารณาและข้อจำกัด](#considerations-and-troubleshooting) ในบทความนี้สำหรับรายการทั้งหมด

## <a name="create-a-table-or-matrix-with-a-hyperlink"></a>สร้างตารางหรือเมทริกซ์ด้วยไฮเปอร์ลิงก์

1. หลังจากคุณได้ [จัดรูปแบบไฮเปอร์ลิงก์เป็น URL](#format-a-url-as-a-hyperlink-in-power-bi-desktop) แล้ว ให้สลับไปที่มุมมองรายงาน
2. สร้างตารางหรือเมทริกซ์ด้วยเขตข้อมูลที่คุณจัดหมวดหมู่เป็น URL เว็บ ไฮเปอร์ลิงก์จะมีสีน้ำเงินและขีดเส้นใต้

    ![ลิงก์สีน้ำเงินและขีดเส้นใต้](media/power-bi-hyperlinks-in-tables/power-bi-url-blue-underline.png)


## <a name="display-a-hyperlink-icon-instead-of-a-url"></a>แสดงไฮเปอร์ลิงก์ไอคอนแทน URL

ถ้าคุณไม่ต้องการแสดง URL ยาวในตาราง คุณสามารถแสดงเป็นไฮเปอร์ลิงก์แทนได้ ![ไฮเปอร์ลิงก์ไอคอน](media/power-bi-hyperlinks-in-tables/power-bi-hyperlink-icon.png) แทน 

> [!NOTE]
> คุณไม่สามารถแสดงไอคอนในเมทริกซ์ได้
   
1. อันดับแรก [สร้างตารางที่มีไฮเปอร์ลิงก์](#create-a-table-or-matrix-with-a-hyperlink)

2. เลือกตารางเพื่อเปิดใช้งาน

    เลือกไอคอน **จัดรูปแบบ** ![ไอคอนแปรงลูกกลิ้ง](media/power-bi-hyperlinks-in-tables/power-bi-paintroller.png) เพื่อเปิดแถบจัดรูปแบบ

    ขยาย **ค่า** ค้นหา **ไอคอน URL** และตั้งค่าการใช้งานเป็น **เปิด**

    ![เปิดไอคอน URL](media/power-bi-hyperlinks-in-tables/power-bi-url-icon-on.png)

1. (ไม่บังคับ) [เผยแพร่รายงาน](desktop-upload-desktop-files.md) จาก Power BI Desktop ไปยังบริการของ Power BI เมื่อคุณเปิดรายงานในบริการของ Power BI ไฮเปอร์ลิงก์จะทำงานด้วยเช่นกัน

## <a name="format-link-text-as-a-hyperlink"></a>จัดรูปแบบข้อความลิงก์เป็นไฮเปอร์ลิงก์

คุณยังสามารถจัดรูปแบบเขตข้อมูลอื่นในตารางเป็นไฮเปอร์ลิงก์และไม่มีคอลัมน์สำหรับ URL เลย ในกรณีนี้ คุณไม่จัดรูปแบบคอลัมน์เป็น URL เว็บ

> [!NOTE]
> คุณไม่สามารถจัดรูปแบบเขตข้อมูลอื่นเป็นไฮเปอร์ลิงก์ในเมทริกซ์ได้

1. ในเขตข้อมูลที่ไม่มีไฮเปอร์ลิงก์ปรากฏในชุดข้อมูลของคุณ ให้ใช้ Power BI Desktop เพื่อเพิ่มเป็น [คอลัมน์แบบกำหนดเอง](desktop-common-query-tasks.md) อีกครั้ง คุณไม่สามารถสร้างคอลัมน์ในโหมด DirectQuery ได้  แต่ถ้าข้อมูลของคุณมี URL อยู่แล้ว คุณสามารถทำให้ URL เหล่านั้นเป็นไฮเปอร์ลิงก์ได้

2. ในมุมมองรายงาน สร้างตารางหรือเมทริกซ์ด้วยคอลัมน์ที่คุณจะจัดรูปแบบเป็นข้อความลิงก์

3. ในตารางที่เลือกไว้ เลือกไอคอน **จัดรูปแบบ** ![ไอคอนแปรงลูกกลิ้ง](media/power-bi-hyperlinks-in-tables/power-bi-paintroller.png) เพื่อเปิดแถบจัดรูปแบบ

4. ขยาย **การจัดรูปแบบตามเงื่อนไข** ตรวจสอบให้แน่ใจว่าชื่อในกล่องเป็นคอลัมน์ที่คุณต้องการให้เป็นข้อความลิงก์ ค้นหา **ไอคอน URL** และเลือก **เปิด**

    ![URL เว็บการกำหนดรูปแบบตามเงื่อนไข](media/power-bi-hyperlinks-in-tables/power-bi-format-conditional-web-url.png)

5. ในกล่องข้อความ **URL เว็บ** เลือกเขตข้อมูลที่มี URL ในกล่อง **เขตข้อมูล อิงตาม** > **ตกลง**

    ![กล่องข้อความ URL เว็บ](media/power-bi-hyperlinks-in-tables/power-bi-format-web-url-dialog.png)

    ตอนนี้ข้อความในคอลัมน์นั้นจะได้รับการจัดรูปแบบเป็นลิงก์

    ![ข้อความที่จัดรูปแบบเป็นไฮเปอร์ลิงก์](media/power-bi-hyperlinks-in-tables/power-bi-url-link-text.png)

1. (ไม่บังคับ) [เผยแพร่รายงาน](desktop-upload-desktop-files.md) จาก Power BI Desktop ไปยังบริการของ Power BI เมื่อคุณเปิดรายงานในบริการของ Power BI ไฮเปอร์ลิงก์จะทำงานด้วยเช่นกัน

## <a name="create-a-table-or-matrix-hyperlink-in-excel-power-pivot"></a>สร้างไฮเปอร์ลิงก์ตารางหรือเมทริกซ์ใน Power Pivot ของ Excel

อีกวิธีในการเพิ่มไฮเปอร์ลิงก์ไปยัง Power BI ตารางและเมทริกซ์คือ การสร้างไฮเปอร์ลิงก์ในชุดข้อมูลก่อนที่คุณนำเข้า/เชื่อมต่อกับชุดข้อมูลนั้นจาก Power BI ตัวอย่างนี้ใช้สมุดงาน Excel

1. เปิดสมุดงานใน Excel
2. เลือกแถบ **PowerPivot** และจากนั้น เลือก**จัดการ**
   
   ![เปิด PowerPivot ใน Excel](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot2.png)
1. เมื่อ PowerPivot เปิดขึ้น เลือกแถบ**ขั้นสูง**
   
   ![แท็บ PowerPivot ขั้นสูง](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot3.png)
4. วางเคอร์เซอร์ในคอลัมน์ที่ประกอบด้วย URL ที่คุณต้องการเปลี่ยนเป็นไฮเปอร์ลิงก์ในตาราง Power BI
   
   > [!NOTE]
   > URL ต้องเริ่มต้นด้วยเลขนำหน้าบางอย่าง โปรดดู [ข้อควรพิจารณาและการแก้ไขปัญหา](#considerations-and-troubleshooting) สำหรับรายการทั้งหมด
   > 
   
5. ในกลุ่ม**รายงานคุณสมบัติ** เลือก**ประเภทข้อมูล**แบบเลื่อนลง แล้วเลือก**URL เว็บ** 
   
   ![ดรอปดาวน์ประเภทข้อมูลใน Excel](media/power-bi-hyperlinks-in-tables/createhyperlinksnew.png)

6. จากบริการของ Power BI หรือ Power BI Desktop เชื่อมต่อไปยัง หรือนำเข้าสมุดงานนี้
7. สร้างการแสดงภาพตารางที่มีเขตข้อมูล URL
   
   ![สร้างตารางใน Power BI ด้วย URL เขตข้อมูล](media/power-bi-hyperlinks-in-tables/hyperlinksintables.gif)

## <a name="considerations-and-troubleshooting"></a>ข้อควรพิจารณาและการแก้ไขปัญหา

URL ต้องเริ่มต้นด้วยหนึ่งในรายการต่อไปนี้:
- http
- https
- -mailto
- file
- ftp
- news
- telnet

Q: ฉันสามารถใช้ URL ที่กำหนดเองเป็นไฮเปอร์ลิงก์ในตารางหรือเมทริกซ์ได้หรือไม่?    
คำตอบ: หมายเลข คุณสามารถใช้ไอคอนลิงก์หนึ่งได้ ถ้าคุณต้องการข้อความแบบกำหนดเองสำหรับไฮเปอร์ลิงก์ของคุณ และรายการของ URL เป็นรายการที่สั้น ให้พิจารณาการใช้กล่องข้อความแทน


## <a name="next-steps"></a>ขั้นตอนถัดไป
[การแสดงภาพในรายงาน Power BI](visuals/power-bi-report-visualizations.md)

[แนวคิดพื้นฐานสำหรับนักออกแบบในบริการ Power BI](service-basic-concepts.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)


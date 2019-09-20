---
title: เพิ่มไฮเปอร์ลิงก์ (URL) ในตาราง
description: หัวข้อนี้สอนวิธีการเพิ่มไฮเปอร์ลิงก์ (URL) ในตาราง คุณใช้ Power BI Desktop เพื่อเพิ่มไฮเปอร์ลิงก์ (URL) ในตารางหรือเมทริกซ์ จากนั้น ไม่ว่าจะในบริการของ Power BI Desktop หรือ Power BI คุณสามารถพิ่มไฮเปอร์ลิงก์เหล่านั้นไปยังรายงานตารางและเมทริกซ์ของคุณได้
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/30/2019
ms.author: maggies
LocalizationGroup: Visualizations
ms.openlocfilehash: 58cb009e29c05ce318c5931fb418617e1ef63f4f
ms.sourcegitcommit: ba085b248c54e8fb1fd8eb2bb23a814e3fdd7ff6
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2019
ms.locfileid: "70937063"
---
# <a name="add-hyperlinks-urls-to-a-table"></a>เพิ่มไฮเปอร์ลิงก์ (URL) ในตาราง
หัวข้อนี้สอนวิธีการเพิ่มไฮเปอร์ลิงก์ (URL) ในตาราง คุณใช้ Power BI Desktop เพื่อเพิ่มไฮเปอร์ลิงก์ (URL) ในตารางหรือเมทริกซ์ จากนั้น ไม่ว่าจะในบริการของ Power BI Desktop หรือ Power BI คุณสามารถพิ่มไฮเปอร์ลิงก์เหล่านั้นไปยังรายงานตารางและเมทริกซ์ของคุณได้ 

![ตารางที่มีไฮเปอร์ลิงก์](media/power-bi-hyperlinks-in-tables/hyperlinkedtable.png)

> [!NOTE]
> คุณสามารถสร้างไฮเปอร์ลิงก์ใน[ไทล์บนแดชบอร์ด](service-dashboard-edit-tile.md)และ[กล่องข้อความบนแดชบอร์ด](service-dashboard-add-widget.md)ได้ทันทีในบริการของ Power BI คุณสามารถสร้างไฮเปอร์ลิงก์ใน[กล่องข้อความในรายงาน](service-add-hyperlink-to-text-box.md)ได้ทันทีในบริการของ Power BI และ Power BI Desktop
> 

## <a name="to-create-a-hyperlink-in-a-table-or-matrix-using-power-bi-desktop"></a>เมื่อต้องสร้างไฮเปอร์ลิงก์ในตารางหรือเมทริกซ์โดยใช้ Power BI Desktop
คุณสามารถสร้างการไฮเปอร์ลิงก์ในตารางและเมทริกซ์ใน Power BI Desktop ได้ แต่ไม่ใช่ในบริการของ Power BI นอกจากนี้ คุณยังสามารถสร้างไฮเปอร์ลิงก์ได้ใน Power Pivot ของ Excel ก่อนที่จะนำเข้าสมุดงานใน Power BI ทั้งสองวิธีจะอธิบายไว้ด้านล่าง

## <a name="create-a-table-or-matrix-hyperlink-in-power-bi-desktop"></a>สร้างไฮเปอร์ลิงก์ตารางหรือเมทริกซ์ใน Power BI Desktop
ขั้นตอนสำหรับการเพิ่มไฮเปอร์ลิงก์ขึ้นอยู่กับว่าคุณได้นำเข้าข้อมูลดังกล่าว หรือเชื่อมต่อเข้าโดยใช้ DirectQuery ทั้งสองสถานการณ์มีอธิบายไว้ด้านล่าง

### <a name="for-data-imported-into-power-bi"></a>สำหรับข้อมูลที่นำเข้าใน Power BI
1. ถ้าไฮเปอร์ลิงก์ดังกล่าวไม่ได้มีอยู่เป็นเขตข้อมูลในชุดข้อมูลของคุณ ใช้ Power BI Desktop เพื่อเพิ่มเป็นแบบ[คอลัมน์แบบกำหนดเอง](desktop-common-query-tasks.md)
2. ในมุมมองข้อมูล เลือกคอลัมน์ และที่แถบ**การสร้างแบบจำลอง** เลือกรายการแบบเลื่อนลงสำหรับ**ประเภทข้อมูล**
   
    ![รายการประเภทข้อมูลแบบดรอปดาวน์](media/power-bi-hyperlinks-in-tables/pbi_data_category.png)
3. เลือก**URL เว็บ**
4. สลับไปยังมุมมองรายงานและสร้างตารางหรือเมทริกซ์โดยใช้เขตข้อมูลที่มีการจัดประเภทเป็น URL เว็บ ไฮเปอร์ลิงก์จะเป็นสีน้ำเงินและขีดเส้นใต้

    ![ลิงก์สีน้ำเงินและขีดเส้นใต้](media/power-bi-hyperlinks-in-tables/power-bi-table-with-hyperlinks2.png)

    > [!NOTE]
    > URL ต้องเริ่มต้นด้วย**http://, https://** หรือ**www**
    >
   
1. ถ้าคุณไม่ต้องการแสดง URL ยาวในตาราง คุณสามารถแสดงเป็นไฮเปอร์ลิงก์แทนได้  ![ไฮเปอร์ลิงก์ไอคอน](media/power-bi-hyperlinks-in-tables/power-bi-hyperlink-icon.png) แทน โปรดทราบว่า คุณไม่สามารถแสดงไอคอนในเมทริกซ์ได้
   
    เลือกแผนภูมิเพื่อเปิดใช้งาน

    เลือกไอคอนรูปแบบ ![ไอคอนลูกกลิ้งระบายสี](media/power-bi-hyperlinks-in-tables/power-bi-paintroller.png) เพื่อเปิดแท็บพื้นที่การจัดรูปแบบ

    ขยาย**ค่า** ค้นหา**ไอคอน URL**และเปิดใช้งานเป็น**เปิด**

    ![เปิดไอคอน URL](media/power-bi-hyperlinks-in-tables/power-bi-url-icon-on.png)

1. (เป็นทางเลือก) [เผยแพร่รายงานจาก Power BI Desktop ไปยังบริการของ Power BI](guided-learning/publishingandsharing.yml?tutorial-step=2)และเปิดรายงานในบริการของ Power BI ไฮเปอร์ลิงก์จะทำงานตรงนั้นได้เช่นกัน

### <a name="for-data-connected-with-directquery"></a>สำหรับข้อมูลที่เชื่อมโยงกับ DirectQuery
คุณไม่สามารถสร้างคอลัมน์ใหม่ในโหมด DirectQuery ได้  แต่ถ้าข้อมูลของคุณมี URL อยู่แล้ว คุณสามารถทำให้ URL เหล่านั้นเป็นไฮเปอร์ลิงก์ได้

1. ในมุมมองรายงาน สร้างตารางโดยใช้เขตข้อมูลที่ประกอบด้วย URL
2. เลือกคอลัมน์ดังกล่าว และที่แถบ**การสร้างแบบจำลอง** เลือกรายการแบบเลื่อนลงสำหรับ**ประเภทข้อมูล**
3. เลือก**URL เว็บ** ไฮเปอร์ลิงก์จะเป็นสีน้ำเงินและขีดเส้นใต้
4. (เป็นทางเลือก) [เผยแพร่รายงานจาก Power BI Desktop ไปยังบริการของ Power BI](guided-learning/publishingandsharing.yml?tutorial-step=2)และเปิดรายงานในบริการของ Power BI ไฮเปอร์ลิงก์จะทำงานตรงนั้นได้เช่นกัน

## <a name="create-a-table-or-matrix-hyperlink-in-excel-power-pivot"></a>สร้างไฮเปอร์ลิงก์ตารางหรือเมทริกซ์ใน Power Pivot ของ Excel
อีกวิธีในการเพิ่มไฮเปอร์ลิงก์ไปยัง Power BI ตารางและเมทริกซ์คือ การสร้างไฮเปอร์ลิงก์ในชุดข้อมูลก่อนที่คุณนำเข้า/เชื่อมต่อกับชุดข้อมูลนั้นจาก Power BI ตัวอย่างนี้ใช้สมุดงาน Excel

1. เปิดสมุดงานใน Excel
2. เลือกแถบ **PowerPivot** และจากนั้น เลือก**จัดการ**
   
   ![เปิด PowerPivot ใน Excel](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot2.png)
1. เมื่อ PowerPivot เปิดขึ้น เลือกแถบ**ขั้นสูง**
   
   ![แท็บ PowerPivot ขั้นสูง](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot3.png)
4. วางเคอร์เซอร์ในคอลัมน์ที่ประกอบด้วย URL ที่คุณต้องการเปลี่ยนเป็นไฮเปอร์ลิงก์ในตาราง Power BI
   
   > [!NOTE]
   > URL ต้องเริ่มต้นด้วย**http://, https://** หรือ**www**
   > 
5. ในกลุ่ม**รายงานคุณสมบัติ** เลือก**ประเภทข้อมูล**แบบเลื่อนลง แล้วเลือก**URL เว็บ** 
   
   ![ดรอปดาวน์ประเภทข้อมูลใน Excel](media/power-bi-hyperlinks-in-tables/createhyperlinksnew.png)

6. จากบริการของ Power BI หรือ Power BI Desktop เชื่อมต่อไปยัง หรือนำเข้าสมุดงานนี้
7. สร้างการแสดงภาพตารางที่มีเขตข้อมูล URL
   
   ![สร้างตารางใน Power BI ด้วย URL เขตข้อมูล](media/power-bi-hyperlinks-in-tables/hyperlinksintables.gif)

## <a name="considerations-and-troubleshooting"></a>ข้อควรพิจารณาและการแก้ไขปัญหา
คำถาม: ฉันสามารถใช้ URL ที่กำหนดเองเป็นไฮเปอร์ลิงก์ในตารางหรือเมทริกซ์ได้หรือไม่?    
คำตอบ: หมายเลข คุณสามารถใช้ไอคอนลิงก์หนึ่งได้ ถ้าคุณต้องการข้อความแบบกำหนดเองสำหรับไฮเปอร์ลิงก์ของคุณ และรายการของ URL เป็นรายการที่สั้น ให้พิจารณาการใช้กล่องข้อความแทน


## <a name="next-steps"></a>ขั้นตอนถัดไป
[การแสดงภาพในรายงาน Power BI](visuals/power-bi-report-visualizations.md)

[แนวคิดพื้นฐานสำหรับนักออกแบบในบริการของ Power BI](service-basic-concepts.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


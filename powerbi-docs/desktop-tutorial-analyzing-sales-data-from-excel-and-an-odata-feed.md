---
title: บทเรียน การวิเคราะห์ข้อมูลยอดขายจาก Excel และ OData feed ใน Power BI Desktop
description: บทเรียน การวิเคราะห์ข้อมูลยอดขายจาก Excel และ OData feed
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: aad93a6c636fb0d75ad89f9e3d9eb70ec203cc88
ms.sourcegitcommit: afa10c016433cf72d6d366c024b862187a8692fd
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/04/2018
---
# <a name="tutorial-analyzing-sales-data-from-excel-and-an-odata-feed"></a>บทเรียน การวิเคราะห์ข้อมูลยอดขายจาก Excel และ OData feed
ด้วย**Power BI Desktop**คุณสามารถเชื่อมต่อกับแหล่งข้อมูลหลายชนิด จากนั้นรวมและจัดรูปแบบมันด้วยวิธีต่างๆ ที่ช่วยในการทำให้น่าสนใจ การดึงดูดความสนใจ วิเคราะห์ข้อมูลและแสดงภาพ ในบทเรียนนี้ คุณจะได้เรียนรู้วิธีการรวมข้อมูลจากแหล่งข้อมูลสองแหล่ง 

ซึ่งเป็นปกติที่จะมีข้อมูลกระจายอยู่ในแหล่งข้อมูลหลายแหล่ง เช่นข้อมูลผลิตภัณฑ์ในฐานข้อมูลหนึ่ง ข้อมูลการขายในอีกที่หนึ่ง เทคนิคที่คุณจะได้เรียนรู้ในเอกสารนี้รวมเวิร์กบุ๊ก Excel และ OData feed แต่เทคนิคเหล่านี้สามารถนำไปใช้กับแหล่งข้อมูลอื่นๆ เช่นกัน เช่นคิวรี่ SQL Server ไฟล์ CSV หรือแหล่งข้อมูลใด ๆ ใน Power BI Desktop

ในบทเรียนนี้ คุณนำเข้าข้อมูลจาก Excel (ซึ่งรวมถึงข้อมูลผลิตภัณฑ์) และ OData feed (ซึ่งประกอบด้วยข้อมูลใบสั่งซื้อ) คุณจะดำเนินการขั้นตอนการแปลงและการรวมข้อมูล และรวมข้อมูลจากแหล่งข้อมูลทั้งสองแหล่งเพื่อสร้างเป็นรายงาน**ยอดขายรวมต่อผลิตภัณฑ์ต่อปี**ที่มีการแสดงภาพแบบโต้ตอบ 

นี่คืออะไรรายงานขั้นสุดท้ายจะมีลักษณะเช่นนี้

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

เพื่อทำตามขั้นตอนในบทเรียนนี้ คุณต้องมี Products workbook ซึ่งคุณสามารถดาวน์โหลด **[คลิกที่นี่เพื่อดาวน์โหลด Products.xlsx](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)**

ในกล่องโต้ตอบ**บันทึกเป็น** ตั้งชื่อไฟล์**Products.xlsx**

## <a name="task-1-get-product-data-from-an-excel-workbook"></a>งานที่ 1 รับข้อมูลผลิตภัณฑ์จากเวิร์กบุ๊ก Excel
ในงาน คุณนำเข้าผลิตภัณฑ์จากไฟล์ Products.xlsx ลงใน Power BI Desktop

### <a name="step-1-connect-to-an-excel-workbook"></a>ขั้นตอนที่ 1 เชื่อมต่อไปยังสมุดงาน Excel
1. เปิดใช้ Power BI Desktop
2. จากริบบอนหน้าแรก เลือก**รับข้อมูล** Excel เป็นหนึ่งในการเชื่อมต่อข้อมูลที่**ธรรมดาที่สุด** ดังนั้นคุณสามารถเลือกได้โดยตรงจากเมนู**รับข้อมูล**
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
3. ถ้าคุณเลือกปุ่มรับข้อมูลโดยตรง คุณยังสามารถเลือก**แฟ้ม\> Excel**และเลือก**เชื่อมต่อ**
4. ในกล่องโต้ตอบ**เปิดไฟล์** เลือกไฟล์**Products.xlsx**
5. ในบานหน้าต่าง**ตัวนำทาง** ให้เลือกแบบตาราง **ผลิตภัณฑ์**จากนั้น เลือก**แก้ไข**
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)

### <a name="step-2-remove-other-columns-to-only-display-columns-of-interest"></a>ขั้นตอนที่ 2 ลบคอลัมน์อื่นๆ เพื่อแสดงเฉพาะคอลัมน์ที่สนใจ
ในขั้นตอนนี้ คุณลบคอลัมน์ทั้งหมดยกเว้น**ProductID**, **ProductName**, **UnitsInStock**และ**QuantityPerUnit** ใน Power BI Desktop มีมักจะเป็นวิธีการทำงานเดียวกัน ตัวอย่างเช่น ปุ่มจำนวนมากใน ริบบอนยังสามารถูกเก็บ โดยใช้เมนูคลิกขวาบนคอลัมน์หรือเซลล์

Power BI Desktop มีตัวแก้ไขแบบสอบถาม ซึ่งเป็นที่ที่คุณจัดรูปแบบ และแปลงการเชื่อมต่อข้อมูลของคุณ ตัวแก้ไขคิวรีเปิดขึ้นโดยอัตโนมัติเมื่อคุณเลือก**แก้ไข**จาก**ตัวนำทาง** คุณยังสามารถเปิดตัวแก้ไขคิวรีได้ โดยการเลือก**แก้ไขคิวรี่**จากริบบอน**หน้าแรก** ใน Power BI Desktop ได้ ขั้นตอนต่อไปนี้จะดำเนินการในตัวแก้ไขคิวรี

1. ในตัวแก้ไขคิวรี่ ให้เลือก**ProductID**, **ProductName**, **QuantityPerUnit**และคอลัมน์**UnitsInStock**(ใช้ **Ctrl + คลิก**เมื่อต้องเลือกมากกว่าหนึ่งคอลัมน์ หรือ**Shift + คลิก**เมื่อต้องเลือกคอลัมน์ที่อยู่ด้านข้างของแต่ละคน)
2. เลือก**ลบคอลัมน์** \> **ลบคอลัมน์อื่น**จากริบบอน หรือคลิกขวาในส่วนหัวของคอลัมน์แล้วคลิก**ลบคอลัมน์อื่น**

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_removeothercolumns.png)

### <a name="step-3-change-the-data-type-of-the-unitsinstock-column"></a>ขั้นตอนที่ 3 เปลี่ยนชนิดข้อมูลของคอลัมน์ UnitsInStock
เมื่อตัวแก้ไขคิวรีเชื่อมต่อกับข้อมูล จะตรวจทานแต่ละเขตข้อมูล เพื่อกำหนดชนิดข้อมูลที่ดีที่สุด สำหรับสมุดงาน Excel ผลิตภัณฑ์ในสินค้าคงคลังจะรวมจำนวนทั้งหมด ดังนั้นในขั้นตอนนี้ คุณยืนยันว่าชนิดข้อมูลของคอลัมน์**UnitsInStock**เป็นจำนวนเต็ม

1. เลือกคำคอลัมน์**UnitsInStock**
2. เลือกปุ่มรายการดรอปดาวน์**ชนิดข้อมูล**ในริบบอน**หน้าแรก**
3. ถ้าไม่ได้เป็นจำนวนเต็ม ให้เลือก**จำนวนเต็ม**สำหรับชนิดข้อมูลจากรายการแบบดรอปดาวน์ (**ชนิดข้อมูล** ปุ่มยังแสดงชนิดข้อมูลสำหรับคอลเล็คชั่นปัจจุบัน)
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_wholenumber.png)      

### <a name="power-bi-desktop-steps-created"></a>ขั้นตอนใน Power BI Desktop ที่สร้างขึ้น
เมื่อคุณดำเนินกิจกรรมของคิวรี่ในตัวแก้ไขคิวรี ขั้นตอนคิวรีจะถูกสร้างขึ้น และแสดงในบานหน้าต่าง**การตั้งค่าคิวรี** ในรายการ**ขั้นตอนที่ใช้** แต่ละขั้นตอนคิวรีมีสูตรที่เกี่ยวข้อง หรือที่เรียกว่าภาษา "M" สำหรับข้อมูลเพิ่มเติมเกี่ยวกับภาษาสูตร "M" ให้ดู[เรียนรู้เกี่ยวกับสูตร Power BI](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f)

| งาน | ขั้นตอนคิวรี | สูตร |
| --- | --- | --- |
| เชื่อมต่อกับสมุดงาน Excel |แหล่งที่มา |Source{[Name="Products"]}[Data] |
| เลื่อนระดับแถวแรกเป็นหัวของคอลัมน์ |FirstRowAsHeader |[Table.PromoteHeaders](https://support.office.com/Article/TablePromoteHeaders-b8eaeb95-042a-42e1-9164-6d3c646acadc "Table.PromoteHeaders") <br /> (ผลิตภัณฑ์) |
| ลบคอลัมน์อื่นเพื่อแสดงเฉพาะ คอลัมน์ที่สนใจ |RemovedOtherColumns |[Table.SelectColumns](https://support.office.com/Article/TableSelectColumns-20bb9e28-9fd3-4cd2-a21b-97972c82ec22 "Table.SelectColumns")  <br />(FirstRowAsHeader,{"ProductID", "ProductName", "QuantityPerUnit", "UnitsInStock"}) |
| เปลี่ยนชนิดข้อมูล |เปลี่ยนแปลงชนิดแล้ว |Table.TransformColumnTypes (\#"ลบคอลัมน์อื่น", {{"UnitsInStock", Int64.Type} }) |

## <a name="task-2-import-order-data-from-an-odata-feed"></a>งานที่ 2 นำเข้าข้อมูลจาก OData feed
ในงานนี้ คุณจะนำเข้าข้อมูลการสั่งซื้อ ขั้นตอนนี้แสดงการเชื่อมต่อกับระบบการขาย คุณนำเข้าข้อมูลลงใน Power BI Desktop จากตัวอย่าง Northwind OData feed ที่ URL ต่อไปนี้ ซึ่งคุณสามารถคัดลอก (แล้ววาง) ในขั้นตอนด้านล่าง <http://services.odata.org/V3/Northwind/Northwind.svc/> 

### <a name="step-1-connect-to-an-odata-feed"></a>ขั้นตอนที่ 1 เชื่อมต่อกับ OData feed
1. จาก**หน้าแรก**แท็บ ริบบอน ในตัวแก้ไขคิวรี เลือก**รับข้อมูล**
2. เรียกดูแหล่งข้อมูล**OData feed**
3. ในกล่องโต้ตอบ**OData Feed** วาง**URL**สำหรับ Northwind OData feed
4. เลือก**ตกลง**
5. ในบานหน้าต่าง**ตัวนำทาง**เลือกตาราง**Orders** จากนั้น**แก้ไข**
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_odatafeed.png)

>[!NOTE]
>คุณสามารถคลิกชื่อตาราง โดยไม่เลือกกล่องกาเครื่องหมาย เพื่อดูตัวอย่าง

### <a name="step-2-expand-the-orderdetails-table"></a>ขั้นตอนที่ 2 ขยาย\_ตารางรายละเอียดของการสั่งซื้อ
ในตาราง**Orders**ประกอบด้วยการอ้างอิงไปยังตาราง **Details** ซึ่งประกอบด้วยผลิตภัณฑ์แต่ละตัวที่รวมอยู่ในแต่ละ Order เมื่อคุณเชื่อมต่อกับแหล่งข้อมูลด้วยตารางหลายตัว (เช่นฐานข้อมูลเชิงสัมพันธ์) คุณสามารถใช้การอ้างอิงเหล่านี้เพื่อสร้างคิวรี่ได้ 

ในขั้นตอนนี้ คุณขยายตัวตาราง**Order\_Details**ซึ่งเชื่อมกับตาราง **Orders** เพื่อรวมคอลัมน์**ProductID**,**UnitPrice**และ**Quantity**จาก **Order\_Details** ลงในตาราง**Order** นี่คือการแสดงของข้อมูลในตารางเหล่านี้

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/orderdetails.png)

การดำเนินการ**ขยาย**ได้รวมคอลัมน์จากตารางที่เกี่ยวข้องลงในตารางปลายทาง เมื่อเรียกใช้คิวรี่ แถวจากตารางที่เกี่ยวข้อง (**Order\_Details**) จะถูกรวมลงในแถวจากตารางปลายทาง (**Orders**)

หลังจากที่คุณขยายตาราง **Order\_Details** สามคอลัมน์ใหม่และแถวเพิ่มเติมจะถูกเพิ่มไปในตาราง**Orders** หนึ่งตัวต่อแต่ละแถวในตารางที่ซ้อนหรือที่เกี่ยวข้องกัน

1. ในการ**มุมมองคิวรี่** เลื่อนไปที่คอลัมน์**Order\_Details**
2. ในคอลัมน์ **Order\_Details** เลือกไอคอนขยาย (![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png))
3. ในรายการดรอปดาวน์**ขยาย**
   1. เลือก **(เลือกคอลัมน์ทั้งหมด)** เพื่อล้างคอลัมน์ทั้งหมด
   2. เลือก **ProductID**, **UnitPrice**และ**Quantity**
   3. คลิก**ตกลง**
      ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)

### <a name="step-3-remove-other-columns-to-only-display-columns-of-interest"></a>ขั้นตอนที่ 3 ลบคอลัมน์อื่นเพื่อแสดงเฉพาะคอลัมน์ที่สนใจ
ในขั้นตอนนี้ คุณลบคอลัมน์ทั้งหมดยกเว้น**OrderDate, ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice** และคอลัมน์**Order\_Details.Quantity** ในงานก่อนหน้า คุณได้ใช้**ลบคอลัมน์อื่น** สำหรับงานนี้ คุณลบคอลัมน์ที่เลือกไว้

1. ใน**มุมมองคิวรี่** ให้เลือกคอลัมน์ทั้งหมดด้วยการกรอก a. และ b.
   1. คลิกคอลัมน์แรก (**OrderID**)
   2. Shift + คลิกคอลัมน์สุดท้าย (**ผู้จัดส่ง**)
   3. หลังจากที่มีเลือกคอลัมน์ทั้งหมด ใช้ Ctrl + คลิกเพื่อยกเลิกการเลือกคอลัมน์ต่อไปนี **OrderDate**, **ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice** และ **Order\_Details.Quantity**
2. หลังจากที่มีเลือกเฉพาะคอลัมน์ที่เราต้องการลบ คลิกขวาบนส่วนหัวของคอลัมน์ใดๆที่เลือกไว แล้วคลิก**ลบคอลัมน์**

### <a name="step-4-calculate-the-line-total-for-each-orderdetails-row"></a>ขั้นตอนที่ 4 คำนวณบรรทัดการรวมของแต่ละแถวของ Order\_Details
Power BI Desktop ช่วยให้คุณสามารถสร้างการคำนวณที่ยึดตามคอลัมน์ที่คุณกำลังนำเข้า ดังนั้นคุณสามารถเพิ่มพูลข้อมูลที่คุณเชื่อมต่ออยู่ได้ ในขั้นตอนนี้ คุณสร้าง**คอลัมน์แบบกำหนดเอง**เพื่อคำนวณบรรทัดทั้งหมดของแต่ละแถว**Order\_Details**

คำนวณยอดรวมบรรทัดสำหรับแต่ละแถว **Order\_Details**

1. ในแท็บริบบอน**เพิ่มคอลัมน์** ให้คลิก**เพิ่ม** **คอลัมน์แบบกำหนดเอง**
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. ในกล่องโต้ตอบ**เพิ่มคอลัมน์แบบกำหนดเอง** ในกล่องข้อความ**สูตรของคอลัมน์แบบกำหนดเอง** ให้ใส่ **[Order\_Details.UnitPrice]** \* **[Order\_Details.Quantity]**
3. ในกล่องข้อความ**ชื่อคอลัมน์ใหม่** ให้ใส่**LineTotal**
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)
4. คลิก**ตกลง**

### <a name="step-5-set-the-datatype-of-the-linetotal-field"></a>ขั้นตอนที่ 5 ตั้งค่าชนิดข้อมูลของเขตข้อมูล LineTotal
1. คลิกขวาที่คอลัมน์**LineTotal**
2. เลือก**เปลี่ยนชนิด**และเลือก**เลขทศนิยม**
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

### <a name="step-6-rename-and-reorder-columns-in-the-query"></a>ขั้นตอนที่ 6 เปลี่ยนชื่อและจัดลำดับคอลัมน์ในคิวรี่ใหม่
ในขั้นตอนนี้ คุณเสร็จสิ้นกาสร้างรายงานแบบง่าย ด้วยการเปลี่ยนชื่อคอลัมน์สุดท้าย และการเปลี่ยนแปลงลำดับของพวกมัน

1. ใน**ตัวแก้ไขคิวรี** ให้ลากคอลัมน์**LineTotal**ทางด้านซ้าย หลังจาก**ShipCountry**
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
2. ลบ *Order\_Details.* อักษรนำจากคอลัมน์ **Order\_Details.ProductID**, **Order\_Details.UnitPrice** และ **Order\_Details.Quantity** ด้วยการคลิกสองครั้งบนส่วนหัวของคอลัมน์ แล้วลบข้อความนั้นจากชื่อคอลัมน์

### <a name="power-bi-desktop-steps-created"></a>ขั้นตอนที่ถูกสร้าง Power BI Desktop
เมื่อคุณดำเนินกิจกรรมของคิวรี่ในตัวแก้ไขคิวรี ขั้นตอนคิวรีจะถูกสร้างขึ้น และแสดงในบานหน้าต่าง**การตั้งค่าคิวรี** ในรายการ**ขั้นตอนที่ใช้** แต่ละขั้นตอนคิวรีมีสูตร Power Query ที่เกี่ยวข้องกัน หรือที่เรียกว่าภาษา "M" สำหรับข้อมูลเพิ่มเติมเกี่ยวกับภาษานี้สูตร ให้ดู[เรียนรู้สูตร Power BI](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f "เรียนรู้สูตร Power Query")

| งาน | ขั้นตอนคิวรี | สูตร |
| --- | --- | --- |
| เชื่อมต่อไปยัง OData feed |แหล่งที่มา |Source{[Name="Orders"]}[Data] |
| ขยายลำดับ\_ตารางรายละเอียด |ขยายลำดับ\_รายละเอียด |[Table.ExpandTableColumn](https://support.office.com/Article/TableExpandTableColumn-54903f25-75a2-4a44-a9a3-52a9d895ee98 "Table.ExpandTableColumn") <br /> (Orders, "Order\_Details", {"ProductID", "UnitPrice", "Quantity"}, {"Order\_Details.ProductID", "Order\_Details.UnitPrice", "Order\_Details.Quantity"}) |
| ลบคอลัมน์อื่นเพื่อแสดงเฉพาะ คอลัมน์ที่สนใจ |RemovedColumns |[Table.RemoveColumns](https://support.office.com/Article/TableRemoveColumns-6265190e-2f58-4300-85b8-df88fc1a67d3 "Table.RemoveColumns") <br />(\#"Expand Order\_Details",{"OrderID", "CustomerID", "EmployeeID", "RequiredDate", "ShippedDate", "ShipVia", "Freight", "ShipName", "ShipAddress", "ShipCity", "ShipRegion", "ShipPostalCode", "ShipCountry", "Customer", "Employee", "Shipper"}) |
| คำนวณยอดรวมของบรรทัดสำหรับแต่ละแถว Order\_Details |InsertedColumn |[Table.AddColumn](https://support.office.com/Article/TableAddColumn-6c64d0a5-9654-4d15-bfb6-9cc380aaf3c0 "Table.AddColumn") <br /> (RemovedColumns, "Custom", each [Order\_Details.UnitPrice] \* [Order\_Details.Quantity]) |

## <a name="task-3-combine-the-products-and-total-sales-queries"></a>งานที่ 3 รวมคิวรี่ผลิตภัณฑ์และยอดขายรวม
Power BI Desktop ไม่จำเป็นต้องเรียกร้องให้รวมคิวรี่เป็นรายงาน คุณสามารถสร้าง**ความสัมพันธ์**ระหว่างชุดข้อมูลได้แทน คุณสามารถสร้างความสัมพันธ์เหล่านี้บนคอลัมน์ใดก็ตามที่ใช้ร่วมกับชุดข้อมูลของคุณ สำหรับข้อมูลเพิ่มเติมดู[สร้างและจัดการความสัมพันธ์](desktop-create-and-manage-relationships.md)

ในบทเรียนนี้ เรามีข้อมูลใบสั่งซื้อและผลิตภัณฑ์ที่ใช้เขตข้อมูล 'ProductID' ร่วมกัน ดังนั้นเราจำเป็นต้องทำให้แน่ใจว่า มีความสัมพันธ์ระหว่างกันในแบบจำลองที่เรากำลังใช้กับ Power BI Desktop เพียงแค่ระบุในคอลัมน์ Power BI Desktop จากตารางแต่ละตารางที่เกี่ยวข้อง (เช่นคอลัมน์ที่มีค่าเดียวกัน) Power BI Desktop หาทิศทางและจำนวนนับของความสัมพันธ์ที่เหมาะสมกับคุณ ในบางกรณี มันจะตรวจพบความสัมพันธ์โดยอัตโนมัติด้วยซ้ำ

ในงานนี้ คุณยืนยันว่าความสัมพันธ์ถูกสร้างขึ้นใน Power BI Desktop ระหว่าง คิวรี่**Products**และ**Total Sales**

### <a name="step-1-confirm-the-relationship-between-products-and-total-sales"></a>ขั้นตอนที่ 1 ยืนยันความสัมพันธ์ระหว่างผลิตภัณฑ์และยอดขายรวม
1. ก่อนอื่น เราจำเป็นต้องโหลดแบบจำลองที่เราสร้างขึ้นในตัวแก้ไขคิวรีลงใน Power BI Desktop จากริบบอน**หน้าแรก** ของตัวแก้ไขคิวรี เลือก**ปิดและโหลด**
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. Power BI Desktop โหลดข้อมูลจากสองคิวรี่
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)      
3. เมื่อข้อมูลถูกโหลด เลือกแบบปุ่ม**จัดการความสัมพันธ์**ริบบอน**หน้าแรก**
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
4. เลือก**ใหม่...** ปุ่ม
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
5. เมื่อเราพยายามที่จะสร้างความสัมพันธ์ เราเห็นว่ามีอยู่แล้วหนึ่งอัน ตามที่แสดงในกล่องโต้ตอบ**สร้างความสัมพันธ์**(โดยมีการแรเงาคอลัมน์) เขตข้อมูล**ProductsID**ในแต่ละคิวรีมีความสัมพันธ์ที่สร้างขึ้นอยู่แล้ว
   
    ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)
6. เลือก**ยกเลิก** แล้ว เลือกมุมมอง**ความสัมพันธ์**ใน Power BI Desktop
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
7. เราเห็นสิ่งต่อไปนี้ ซึ่งมองความสัมพันธ์ระหว่างคิวรี
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)
8. เมื่อคุณดับเบิลคลิกที่เส้นที่เชื่อมต่อลูกศรที่กับคิวรี่ กล่องโต้ตอบ**แก้ไขความสัมพันธ์**จะปรากฏขึ้น
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)
9. ไม่จำเป็นต้องทำการเปลี่ยนแปลง ดังนั้นเราจะเลือกเพียงแค่**ยกเลิก**เพื่อปิดกล่องโต้ตอบ**แก้ไขความสัมพันธ์**

## <a name="task-4-build-visuals-using-your-data"></a>งานที่ 4: สร้างภาพที่ใช้ข้อมูลของคุณ
Power BI Desktop ช่วยให้คุณสร้างจัดรูปแบบข้อมูลเพื่อรับข้อมูลเชิงลึกจากข้อมูลที่หลากหลายของคุณ คุณสามารถสร้างรายงานที่ มีหลายหน้า และรายการแต่ละหน้าสามารถมีหลายภาพ คุณสามารถโต้ตอบ ด้วยการแสดงภาพของคุณเพื่อช่วยวิเคราะห์ และทำความเข้าใจข้อมูล สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการแก้ไขรายงาน ให้ดู[แก้ไขรายงาน](service-interact-with-a-report-in-editing-view.md)

ในงานนี้ คุณสร้างรายงานที่ยึดตามข้อมูลที่โหลดก่อนหน้านี้ คุณสามารถใช้บานหน้าต่างเขตข้อมูลเมื่อต้องเลือกคอลัมน์ที่คุณสร้างการแสดงภาพ

### <a name="step-1-create-charts-showing-units-in-stock-by-product-and-total-sales-by-year"></a>ขั้นตอนที่ 1 สร้างแผนภูมิที่แสดงหน่วยในสินค้าคงคลัง โดยผลิตภัณฑ์และยอดขายรวมตามปี
ลาก**UnitsInStock**จากบานหน้าต่างเขตข้อมูล (บานหน้าต่างเขตข้อมูลคือตามแนวทางด้านขวาของหน้าจอ) บนช่องว่างเปล่าบนผืนผ้าใบ ภาพตารางได้ถูกสร้างขึ้น ถัดไป ลาก ProductName ไปยังกล่องแกน พบในด้านล่างตรงครึ่งของบานหน้าต่างการแสดงภาพ จากนั้นเราแล้วเลือก**เรียงลำดับตาม\>UnitsInStock** โดยใช้ skittles ที่มุมขวาด้านบนของการแสดงภาพ

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

ลาก**OrderDate**ไปยังพื้นที่ภายใต้แผนภูมิแรก จากนั้นลาก LineTotal (อีกครั้ง จากบานหน้าต่างเขตข้อมูล) ลงบนภาพ แล้วเลือกแผนภูมิเส้น การแสดงภาพต่อไปนี้ได้จะถูกสร้างขึ้น

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png)

 ถัดไป ลาก**ShipCountry**ไปยังพื้นที่ว่างบนพื้นที่แก้ไขด้านขวาบน เนื่องจากคุณได้เลือกเขตข้อมูลทางภูมิศาสตร์ แผนผังจึงถูกสร้างขึ้นโดยอัตโนมัติ ตอนนี้ ลาก**LineTotal**ไปยังฟิลด์ **Values** วงกลมบนแมปสำหรับแต่ละประเทศมีขนาดที่สัมพันธ์กับ **LineTotal** สำหรับคำสั่งซื้อที่จัดส่งไปยังประเทศนั้น

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

### <a name="step-2-interact-with-your-report-visuals-to-analyze-further"></a>ขั้นตอนที่ 2 โต้ตอบกับรายงานภาพของคุณเพื่อวิเคราะห์เพิ่มเติม
Power BI Desktop ช่วยให้คุณสามารถโต้ตอบกับรูปภาพที่ไฮไลท์สลับกัน และกรองซึ่งกันและกัน เมื่อต้องการเปิดเผยแนวโน้มที่เพิ่มเติม สำหรับรายละเอียดเพิ่มเติมดู[การกรองและการไฮไลท์ในรายงาน](power-bi-reports-filters-and-highlighting.md)

1. คลิกที่กลมสีน้ำเงินอ่อนที่กึ่งกลางใน**Canad****a.** ให้ตั้งใจดูวิธีกรองภาพต่างๆ สำหรับการแสดงสินค้าคงคลัง (**ShipCountry**) และการสั่งซื้อ (**LineTotal**) เฉพาะแคนาดา
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="complete-sales-analysis-report"></a>กรอกรายงานการวิเคราะห์การขาย
หลังจากที่คุณดำเนินการขั้นตอนเหล่านี้ทั้งหมด คุณจะมีการรายงานยอดขายที่รวมข้อมูลจากไฟล์ Products.xlsx และ Northwind OData feed รายงานจะแสดงรูปภาพซึ่งช่วยให้วิเคราะห์ข้อมูลการขายจากประเทศที่ต่างกัน คุณสามารถดาวน์โหลดไฟล์ Power BI Desktop ที่ทำเสร็จสมบูรณ์สำหรับบทเรียนนี้[ที่นี่](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Sales_Data.pbix)

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [อ่านบทเรียน Power BI Desktop อื่นๆ](http://go.microsoft.com/fwlink/?LinkID=521937)
* [ดูวิดีโอ Power BI Desktop](http://go.microsoft.com/fwlink/?LinkID=519322)
* [เยี่ยมชมฟอรั่ม Power BI](http://go.microsoft.com/fwlink/?LinkID=519326)
* [อ่านบล็อก Power BI](http://go.microsoft.com/fwlink/?LinkID=519327)



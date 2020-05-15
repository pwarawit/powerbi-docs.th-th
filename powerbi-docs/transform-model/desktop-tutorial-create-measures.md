---
title: 'บทช่วยสอน: สร้างหน่วยวัดของคุณเองใน Power BI Desktop'
description: หน่วยวัดใน Power BI Desktop ช่วยคุณโดยการคำนวณบนข้อมูลของคุณ ตามที่คุณโต้ตอบกับรายงานของคุณ
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 11/08/2019
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 91b0bba3b8e3fc221a05e6ccb2de1ec9b888d1ef
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83349321"
---
# <a name="tutorial-create-your-own-measures-in-power-bi-desktop"></a>บทช่วยสอน: สร้างหน่วยวัดของคุณเองใน Power BI Desktop
คุณสามารถสร้างโซลูชันของการวิเคราะห์ข้อมูลมีประสิทธิภาพที่สุดบางอย่างใน Power BI Desktop โดยใช้หน่วยวัด หน่วยวัดที่ช่วยคุณด้วยการคำนวนบนข้อมูลของคุณ ตามที่คุณโต้ตอบกับรายงานของคุณ บทเรียนนี้จะแนะนำคุณโดยผ่านการทำความเข้าใจเกี่ยวกับหน่วยวัด และสร้างหน่วยวัดพื้นฐานของคุณเองใน Power BI Desktop

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- บทเรียนนี้มีไว้สำหรับผู้ใช้ Power BI ที่คุณคุ้นเคยกับการใช้ Power BI Desktop เพื่อสร้างแบบจำลองที่ขั้นสูงขึ้น คุณควรจะคุ้นเคยกับการใช้ Get Data และตัวแก้ไขคิวรีเพื่อนำเข้าข้อมูล ทำงานกับหลายตารางที่เกี่ยวข้อง และเพิ่มเขตข้อมูลไปยังพื้นที่รายงาน ถ้าคุณยังไม่คุ้นเคยกับ Power BI Desktop ให้ตรวจดู[เริ่มต้นใช้งาน Power BI Desktop](../fundamentals/desktop-getting-started.md)
  
- บทช่วยสอนนี้ใช้ไฟล์[ตัวอย่างยอดขายของ Contoso สำหรับ Power BI Desktop](https://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip) ซึ่งรวมถึงข้อมูลยอดขายออนไลน์จากบริษัทจำลอง Contoso เนื่องจากข้อมูลนี้นำเข้ามาจากฐานข้อมูล ดังนั้นคุณจึงไม่สามารถเชื่อมต่อกับแหล่งข้อมูลหรือดูในตัวแก้ไขคิวรีได้ ดาวน์โหลดและแยกไฟล์บนคอมพิวเตอร์ของคุณ

## <a name="automatic-measures"></a>หน่วยวัดอัตโนมัติ

เมื่อ Power BI Desktop สร้างหน่วยวัด หน่วยวัดมักจะถูกสร้างขึ้นสำหรับคุณโดยอัตโนมัติ เมื่อต้องการดูวิธีการที่ Power BI Desktop สร้างหน่วยวัด ให้ทำตามขั้นตอนเหล่านี้:

1. ในPower BI Desktop ให้เลือก **ไฟล์** > **เปิด**, เรียกดูไฟล์ *ตัวอย่างยอดขายของ Contoso สำหรับ Power BI Desktop.pbix* จากนั้นเลือก**เปิด**

2. ในบานหน้าต่าง**เขตข้อมูล** ขยายตาราง**ยอดขาย** จากนั้นเลือกกล่องกาเครื่องหมายที่อยู่ถัดจากเขตข้อมูล **SalesAmount** หรือลาก **SalesAmount** ลงบนพื้นที่รายงาน

    การสร้างภาพแผนภูมิคอลัมน์ใหม่จะปรากฏขึ้นโดยแสดงผลรวมของค่าทั้งหมดในคอลัมน์ **SalesAmount** ของตาราง**ยอดขาย**

    ![แผนภูมิคอลัมน์ SalesAmount](media/desktop-tutorial-create-measures/meastut_salesamountchart.png)

เขตข้อมูล (คอลัมน์) ใน**เขตข้อมูล** บานหน้าต่างที่มีไอคอน sigma ![ไอคอน Sigma](media/desktop-tutorial-create-measures/meastut_sigma.png) และสามารถรวมค่าได้ Power BI Desktop จะสร้างและคำนวณหน่วยวัดเพื่อรวมข้อมูลโดยอัตโนมัติหากตรวจพบชนิดข้อมูลที่เป็นตัวเลข แทนการแสดงตารางที่มีค่าจำนวนมาก (สองล้านแถวสำหรับ **SalesAmount**) ผลรวมคือ การรวมค่าแบบเริ่มต้นสำหรับชนิดข้อมูลที่เป็นตัวเลข แต่คุณสามารถใช้การรวมข้อมูลอื่นๆเช่นหาค่าเฉลี่ยหรือการนับค่าได้อย่างง่ายดาย การทำความเข้าใจเกี่ยวกับรวมข้อมูลเป็นพื้นฐานเพื่อทำความเข้าใจเกี่ยวกับมาตรการวัด เนื่องจากหน่วยวัดทุกตัวมีการทำการรวมข้อมูลชนิดใดชนิดหนึ่ง 

เมื่อต้องการเปลี่ยนการรวมแผนภูมิ ให้ทำตามขั้นตอนเหล่านี้:

1. เลือกการแสดงภาพ **SalesAmount** ในพื้นที่รายงาน  

1. ในพื้นที่**ค่า**ของบานหน้าต่าง**การสร้างภาพ** เลือกลูกศรลงทางด้านขวาของ **SalesAmount** 

1. จากเมนูที่ปรากฏขึ้น เลือก**ค่าเฉลี่ย** 

    การแสดงภาพจะเปลี่ยนเป็นค่าเฉลี่ยของยอดขายทั้งหมดในเขตข้อมูล **SalesAmount**

    ![แผนภูมิโดยเฉลี่ย SalesAmount](media/desktop-tutorial-create-measures/meastut_salesamountaveragechart.png)

คุณสามารถเปลี่ยนชนิดของการรวมได้โดยขึ้นอยู่กับผลลัพธ์ที่คุณต้องการ อย่างไรก็ตาม การรวมไม่ได้มีผลกับประเภทข้อมูลที่เป็นตัวเลขทุกประเภท ตัวอย่างเช่น สำหรับเขตข้อมูล **SalesAmount** ผลรวม และค่าเฉลี่ยจะมีประโยชน์ รวมถึงค่าต่ำสุดและสูงสุดจะมีตำแหน่งของตนเช่นกัน อย่างไรก็ตาม การนับไม่เหมาะสมกับเขตข้อมูล **SalesAmount** เนื่องจากในขณะที่ค่าเป็นตัวเลข แต่ที่จริงมันเป็นสกุลเงิน

ค่าที่คำนวณจากการเปลี่ยนแปลงตัววัดได้ตอบสนองต่อการโต้ตอบกับรายงานของคุณ ตัวอย่างเช่น ถ้าคุณลากเขตข้อมูล **RegionCountryName** จากตาราง **ภูมิศาสตร์** ไปยังแผนภูมิ **SalesAmount** ของคุณที่มีอยู่ การดำเนินการนี้จะมีการเปลี่ยนแปลงเพื่อแสดงยอดขายเฉลี่ยสำหรับแต่ละประเทศ

![SaleAmount ตามประเทศ](media/desktop-tutorial-create-measures/meastut_salesamountavchartbyrcn.png)

เมื่อผลลัพธ์ของหน่วยวัดมีการเปลี่ยนแปลงเนื่องจากการโต้ตอบกับรายงานของคุณ *บริบท*ของหน่วยวัดจะได้รับผลกระทบ ทุกครั้งที่คุณโต้ตอบกับด้วยการแสดงภาพของคุณรายงาน คุณกำลังเปลี่ยนแปลงบริบท ซึ่งหน่วยวัดถูกคำนวณและแสดงผลลัพธ์

## <a name="create-and-use-your-own-measures"></a>สร้าง และใช้หน่วยวัดของคุณเอง

ในกรณีส่วนใหญ่ Power BI Desktop จะคำนวณและแสดงค่าโดยอัตโนมัติตามชนิดของเขตข้อมูลและการรวมที่คุณเลือก อย่างไรก็ตาม ในบางกรณีคุณอาจต้องการสร้างหน่วยวัดของคุณเองเพื่อทำการคำนวณที่ซับซ้อนและไม่ซ้ำกัน กับ คุณสามารถสร้างหน่วยวัดของคุณด้วยภาษาสูตร Data Analysis Expressions (DAX) ด้วย Power BI Desktop 

สูตร DAX ใช้ฟังก์ชัน ตัวดำเนินการ และไวยากรณ์เดียวกับสูตร Excel เป็นจำนวนมาก อย่างไรก็ตาม ฟังก์ชัน DAX ถูกออกแบบมาให้ทำงานกับข้อมูลแบบสัมพันธ์ และทำการคำนวณแบบไดนามิกมากกว่าที่คุณโต้ตอบกับรายงาน มีฟังก์ชัน DAX มากกว่า 200 ตัว ที่ทำทุกอย่างตั้งแต่การรวมข้อมูลอย่างง่าย เช่น ผลรวมและค่าเฉลี่ย ไปยังฟังก์ชันทางสถิติ และการกรองที่ซับซ้อนมากขึ้น มีแหล่งข้อมูลมากมายเพื่อช่วยให้คุณเรียนรู้เพิ่มเติมเกี่ยวกับ DAX หลังจากที่คุณเสร็จสิ้นบทช่วยสอนนี้ ดู[พื้นฐาน DAX ใน Power BI Desktop](desktop-quickstart-learn-dax-basics.md)

เมื่อคุณสร้างหน่วยวัดของคุณเอง การดำเนินการนี้จะเรียกว่าหน่วยวัดของ*แบบจำลอง* และจะถูกเพิ่มลงในรายการ**เขตข้อมูล**สำหรับตารางที่คุณเลือก ข้อดีบางประการของหน่วยวัดแบบจำลอง ซึ่งจะให้คุณสามารถตั้งชื่อตามที่คุณต้องการได้ ทำให้สามารถระบุตัวได้ง่ายขึ้น คุณสามารถใช้เป็นอาร์กิวเมนต์ในนิพจน์ DAX อื่น ๆ และคุณสามารถดำเนินการคำนวณที่ซับซ้อนได้อย่างรวดเร็ว

### <a name="quick-measures"></a>การวัดผลด่วน

นับตั้งแต่ Power BI Desktop รุ่นเดือนกุมภาพันธ์ 2018 คุณสามารถใช้การคำนวณทั่วไปหลายแบบเช่น *ตัววัดแบบด่วน* ซึ่งเขียนสูตร DAX ให้คุณ โดยยึดตามข้อมูลที่คุณป้อนเข้าในหน้าต่าง คำนวณที่รวดเร็วและมีประสิทธิภาพเหล่านี้เหมาะสำหรับการเรียนรู้ DAX หรือเริ่มหน่วยวัดแบบกำหนดเองของคุณเอง 

สร้างการวัดผลด่วนโดยใช้วิธีใดวิธีหนึ่งต่อไปนี้: 
 - จากตารางในบานหน้าต่าง **เขตข้อมูล** ให้คลิกขวาหรือเลือกตัวเลือก **เพิ่มเติม** ( **...** ), จากนั้นเลือก **การวัดผลด่วนใหม่** จากรายการ

 - ภายใต้ **การคำนวณ** ในแท็บ **Home** ของริบบอน Power BI Desktop ให้เลือก **การวัดผลด่วนใหม่**

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการสร้างและการใช้การวัดผลด่วน ให้ดู [ใช้การวัดผลด่วน](desktop-quick-measures.md)

### <a name="create-a-measure"></a>สร้างการวัด

สมมติว่าคุณต้องการวิเคราะห์ยอดขายสุทธิของคุณโดยลบส่วนลดและผลลัพธ์จากยอดขายรวม สำหรับบริบทที่มีอยู่ในการแสดงภาพของคุณ คุณจำเป็นต้องมีหน่วยวัดที่ลบผลรวมของ DiscountAmount และ ReturnAmount จากผลรวมของ SalesAmount ไม่มีเขตข้อมูลสำหรับยอดขายสุทธิในรายการ**เขตข้อมูล** แต่คุณต้องมีบล็อกการสร้างเพื่อสร้างหน่วยวัดของคุณเองในการคำนวณยอดขายสุทธิ 

แล้วทำตามขั้นตอนเหล่านี้เพื่อสร้างหน่วยวัด:

1. ในบานหน้าต่าง **เขตข้อมูล** ให้คลิกขวาที่ตาราง **ยอดขาย** หรือวางเมาส์เหนือตารางและเลือก **ตัวเลือกเพิ่มเติม** ( **...** ) 

1. จากเมนูที่ปรากฏขึ้น เลือก**หน่วยวัดใหม่** 

    การดำเนินการนี้จะเป็นการบันทึกหน่วยวัดใหม่ของคุณในตาราง**ยอดขาย** ซึ่งเป็นเรื่องง่ายที่จะค้นหา
    
    ![หน่วยวัดใหม่จากรายการ](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure.png)
    
    คุณยังสามารถสร้างหน่วยวัดใหม่ได้โดยการเลือก **หน่วยวัดใหม่** ในกลุ่ม**การคำนวณ** บนแท็บ **Home** ของริบบอน Power BI Desktop
    
    ![หน่วยวัดใหม่จากริบบอน](media/desktop-tutorial-create-measures/meastut_netsales_newmeasureribbon.png)
    
    >[!TIP]
    >เมื่อคุณสร้างหน่วยวัดจากริบบอน คุณสามารถสร้างขึ้นในตารางใดก็ได้ แต่จะง่ายต่อการค้นหาถ้าคุณสร้างในที่ที่คุณวางแผนจะใช้ ในกรณีนี้ เลือกตาราง**ยอดขาย**ก่อนเพื่อเปิดใช้งาน จากนั้นเลือก**หน่วยวัดใหม่** 
    
    แถบสูตรจะปรากฏขึ้นตามแนวด้านบนของพื้นที่รายงาน ตำแหน่งที่คุณสามารถเปลี่ยนชื่อหน่วยวัดของคุณ และใส่สูตร DAX
    
    ![แถบสูตร](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formulabar.png)
    
1. ตามค่าเริ่มต้น หน่วยวัดใหม่แต่ละหน่วยจะมีชื่อว่า *Measure* ถ้าคุณไม่ได้เปลี่ยนชื่อ หน่วยวัดใหม่เพิ่มเติมจะมีชื่อว่า *Measure 2*, *Measure 3* และอื่นๆ เนื่องจากเราต้องการให้หน่วยวัดนี้สามารถระบุได้มากขึ้น ให้ไฮไลท์ *Measure* ในแถบสูตรแล้วเปลี่ยนเป็น *ยอดขายสุทธิ*
    
1. เริ่มต้นการใส่สูตรของคุณ หลังจากเครื่องหมายเท่ากัน เริ่มพิมพ์*Sum* ขณะที่คุณพิมพ์ รายการคำแนะนำแบบดรอปดาวน์จะปรากฏขึ้น ซึ่งแสดงฟังก์ชัน DAX ทั้งหมดที่ขึ้นต้นด้วยตัวอักษรที่คุณพิมพ์ เลื่อนลง ถ้าจำเป็น หากต้องการเลือก**SUM**จากรายการ จากนั้นกด **Enter**
    
    ![เลือก SUM จากรายการ](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_s.png)
    
    วงเล็บเปิดจะปรากฏขึ้น พร้อมกับรายการแนะนำแบบดรอปดาวน์สำหรับคอลัมน์พร้อมใช้งานที่คุณสามารถส่งไปยังฟังก์ชัน SUM
    
    ![เลือกคอลัมน์](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_sum.png)
    
1. นิพจน์ปรากฏตลอดเวลาระหว่างวงเล็บปิดและวงเล็บปิด ตัวอย่างเช่น นิพจน์ของคุณจะประกอบด้วยอาร์กิวเมนต์เดียว เพื่อส่งผ่านไปยังฟังก์ชัน SUM ของคอลัมน์ **SalesAmount** เริ่มพิมพ์ *SalesAmount* จนกว่า **Sales(SalesAmount)** จะเป็นค่าเดียวที่เหลืออยู่ในรายการ 

    ชื่อคอลัมน์ที่นำหน้าด้วยชื่อตารางจะถือว่าเป็นชื่อที่ตรงตามหลักเกณฑ์ของคอลัมน์ ชื่อคอลัมน์ที่ตรงตามหลักเกณฑ์ทำให้สูตรของคุณอ่านง่ายขึ้น
    
    ![เลือก SalesAmount](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_salesam.png)
    
1. เลือก **Sales[SalesAmount]** จากรายการ จากนั้นใส่วงเล็บปิด
    
    > [!TIP]
    > ข้อผิดพลาดทางไวยากรณ์มักเกิดขึ้นจากวงเล็บปิดที่วางผิดตำแหน่ง หรือขาดหายไป
    
    
    
1. ลบสองคอลัมน์อื่นภายในสูตร:

    a. หลังจากวงเล็บปิดในนิพจน์แรก พิมพ์ช่องว่าง ตัวดำเนินการลบ (-) และช่องว่างอีกช่อง 

    b. ใส่ฟังก์ชัน SUM อีกอัน และเริ่มพิมพ์ *DiscountAmount* จนกว่าคุณสามารถเลือกคอลัมน์ **Sales[DiscountAmount]** เป็นอาร์กิวเมนต์ เพิ่มวงเล็บปิด 

    c. พิมพ์ช่องว่าง ตัวดำเนินการลบ ช่องว่าง ฟังก์ชัน SUM อีกฟังก์ชัน พร้อมกับ**Sales[ReturnAmount]** เป็นอาร์กิวเมนต์ และวงเล็บปิด
    
    ![เติมสูตร](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_discamount.png)
    
1. กด **Enter** หรือเลือก **ยืนยัน** (ไอคอนเครื่องหมายถูก) ในแถบสูตรเพื่อทำให้เสร็จสมบูรณ์และตรวจสอบความถูกต้องสูตร 

    ขณะนี้หน่วยวัด**ยอดขายสุทธิ**ที่ตรวจสอบความถูกต้องแล้วพร้อมใช้งานในตาราง**ยอดขาย**ในบานหน้าต่าง **เขตข้อมูล**
    
    ![หน่วยวัดยอดขายสุทธิในรายการเขตข้อมูลของตารางยอดขาย](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_complete.png)
    
1. ถ้าคุณมีพื้นที่ไม่พอสำหรับการใส่สูตรหรือต้องการในบรรทัดที่แยกต่างหาก ให้เลือกลูกศรลงทางด้านขวาของแถบสูตรเพื่อให้มีช่องว่างมากขึ้น 

    ลูกศรลงจะเปลี่ยนเป็นลูกศรขึ้นและกล่องขนาดใหญ่จะปรากฏขึ้น

    ![ลูกศรขึ้นของสูตร](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_chevron.png)

1. แยกส่วนต่าง ๆ ของสูตรของคุณโดยการกด **Alt** + **Enter** สำหรับบรรทัดที่แยกต่างหาก หรือกด **Tab** เพื่อเพิ่มระยะห่างของแท็บ

   ![สูตรที่ขยาย](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_expanded.png)

### <a name="use-your-measure-in-the-report"></a>ใช้หน่วยวัดของคุณในรายงาน
เพิ่มหน่วยวัด**ยอดขายสุทธิ**ของคุณไปยังพื้นที่รายงาน และคำนวณยอดขายสุทธิสำหรับเขตข้อมูลอื่นใดก็ตามที่คุณเพิ่มลงในรายงาน 

เมื่อต้องดูยอดขายสุทธิตามประเทศ

1. เลือก**ยอดขายสุทธิ**วัดจากการตาราง**Sales** หรือลากไปที่พื้นที่รายงาน
    
1. เลือกเขตข้อมูล **RegionCountryName** จากตาราง **ภูมิศาสตร์** หรือลากไปยังแผนภูมิ **ยอดขายสุทธิ**
    
    ![ยอดขายสุทธิตามประเทศ](media/desktop-tutorial-create-measures/meastut_netsales_byrcn.png)
    
1. เมื่อต้องการดูความแตกต่างระหว่างยอดขายสุทธิและยอดขายรวมตามประเทศ เลือกเขตข้อมูล**SalesAmount** หรือลากไปยังแผนภูมิ 

    ![ยอดขายและขายสุทธิตามประเทศ](media/desktop-tutorial-create-measures/meastut_netsales_byrcnandsalesamount.png)

    แผนภูมิตอนนี้ใช้หน่วยวัดสองตัวคือ: **SalesAmount**ซึ่ง Power BI จะรวมโดยอัตโนมัติและหน่วยวัด**ยอดขายสุทธิ**ที่คุณสร้างด้วยตนเอง หน่วยวัดแต่ละหน่วยจะได้รับการคำนวณในบริบทของเขตข้อมูลอื่น **RegionCountryName**
    
### <a name="use-your-measure-with-a-slicer"></a>ใช้หน่วยวัดของคุณกับตัวแบ่งส่วนข้อมูล

เพิ่มตัวแบ่งส่วนข้อมูลเพื่อกรองยอดขายสุทธิและยอดขายตามปีปฏิทินเพิ่มเติม:
    
1. เลือกพื้นที่ว่างที่อยู่ถัดจากแผนภูมิ ในบานหน้าต่าง**การแสดงภาพ** ให้เลือกการแสดงภาพ **ตาราง** 

    การดำเนินการนี้จะเป็นการสร้างการแสดงภาพตารางที่ว่างเปล่าบนพื้นที่รายงาน
    
    ![การแสดงภาพตารางที่ว่างเปล่าใหม่](media/desktop-tutorial-create-measures/meastut_netsales_blanktable.png)
    
1. ลากเขตข้อมูล**ปี**จากตาราง**ปฏิทิน** ไปยังการแสดงภาพตารางที่ว่างเปล่าใหม่ 
    
    เนื่องจาก**ปี** เป็นเขตข้อมูลตัวเลข Power BI Desktop จะสรุปค่า การสรุปนี้ใช้งานไม่ได้เช่นเดียวกับการรวม เราจะจัดการเรื่องนั้นในขั้นตอนต่อไป

    ![เพิ่มการรวมข้อมูล](media/desktop-tutorial-create-measures/meastut_netsales_yearaggtable.png)
    
3. ในกล่อง**ค่า** ในบานหน้าต่าง **การแสดงภาพ** เลือกลูกศรลงถัดจาก**ปี** จากนั้นเลือก **ไม่สรุป**จากรายการ ตารางแสดงรายการของแต่ละปี
    
    ![เลือกไม่สรุป](media/desktop-tutorial-create-measures/meastut_netsales_year_donotsummarize.png)
    
4.  เลือกไอคอน**ตัวแบ่งส่วนข้อมูล** ในบานหน้าต่าง**การแสดงภาพ**เพื่อเปลี่ยนตารางเป็นตัวแบ่งส่วนข้อมูล ถ้าการแสดงภาพแสดงแถบเลื่อนแทนที่จะเป็นรายการ ให้เลือก**รายการ**จากลูกศรลงในแถบเลื่อน

    ![แปลงตารางเป็นตัวแบ่งส่วนข้อมูล](media/desktop-tutorial-create-measures/meastut_netsales_year_changetoslicer.png)
    
5.  เลือกค่าใด ๆ ในตัวแบ่งส่วนข้อมูลของ **ปี** เพื่อกรอง **ยอดขายสุทธิและจำนวนยอดขายตามแผนภูมิ RegionCountryName** ตามลำดับ หน่วยวัด**ยอดขายสุทธิ**และ **SalesAmount** ทำการคำนวณอีกครั้งและแสดงผลลัพธ์ในบริบทของเขตข้อมูล**ปี**ที่เลือก 
    
    ![แผนภูมิส่วน ๆ ตามปี](media/desktop-tutorial-create-measures/meastut_netsales_chartslicedbyyear.png)

### <a name="use-your-measure-in-another-measure"></a>ใช้การวัดในหน่วยวัดอื่น

สมมติว่าคุณต้องการค้นหาผลิตภัณฑ์ที่มียอดขายสุทธิสูงสุดต่อหน่วยที่ขาย คุณจะต้องมีหน่วยวัดที่หารยอดขายสุทธิตามปริมาณของหน่วยที่ขาย สร้างหน่วยวัดใหม่ที่หารผลลัพธ์ของหน่วยวัด**ยอดขายสุทธิ**ของคุณ ด้วยผลรวมของ **Sales[SalesQuantity]**

1.  ในบานหน้าต่าง**เขตข้อมูล** สร้างหน่วยวัดใหม่ที่ชื่อว่า **ยอดขายสุทธิต่อหน่วย** ในตาราง**ยอดขาย**
    
1. ในแถบสูตร เริ่มพิมพ์*Net Sales* รายการคำแนะนำจะแสดงสิ่งที่คุณสามารถเพิ่มได้ เลือก **[ยอดขายสุทธิ]**
    
    ![สูตรที่ใช้ยอดขายสุทธิ](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2a.png)
    
1. คุณยังสามารถอ้างอิงหน่วยวัด โดยเพียงแค่พิมพ์วงเล็บเปิด ( **[** ) ได้ รายการคำแนะนำจะแสดงเฉพาะหน่วยวัดที่จะเพิ่มลงในสูตรของคุณเท่านั้น
    
    ![วงเล็บเหลี่ยมแสดงหน่วยวัดเท่านั้น](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2b.png)
    
1. ใส่ช่องว่าง ตัวดำเนินการหาร (/) ช่องว่างอีกอัน ฟังก์ชัน SUM จากนั้นพิมพ์*Quantity* รายการคำแนะนำแสดงคอลัมน์ทั้งหมดทีมี *Quantity* อยู่ในชื่อ เลือก **Sales[SalesQuantity]** พิมพ์วงเล็บปิดและกด **ENTER** หรือเลือก **ยืนยัน** (ไอคอนเครื่องหมายถูก) เพื่อตรวจสอบความถูกต้องสูตรของคุณ 

    สูตรผลลัพธ์ควรปรากฏเป็น:
    
    `Net Sales per Unit = [Net Sales] / SUM(Sales[SalesQuantity])`
    
1. เลือกหน่วยวัด**ยอดขายสุทธิต่อหน่วย** จากตาราง**ยอดขาย** หรือลากไปยังพื้นที่ว่างในพื้นที่รายงาน 

    แผนภูมิแสดงยอดขายสุทธิต่อหน่วยในผลิตภัณฑ์ทั้งหมดที่ขาย แผนภูมินี้ไม่มีข้อมูลมากนัก เราจะจัดการเรื่องนั้นในขั้นตอนต่อไป
    
    ![สุทธิยอดขายต่อหน่วยโดยรวม](media/desktop-tutorial-create-measures/meastut_nspu_chart.png)
    
1. เพื่อให้มีลักษณะแตกต่างกัน เปลี่ยนชนิดของการแสดงภาพแผนภูมิสำหรับ**ทรีแมป**
    
    ![เปลี่ยนเป็นทรีแมป](media/desktop-tutorial-create-measures/meastut_nspu_changetotreemap.png)
    
1. เลือกเขตข้อมูล**ประเภทผลิตภัณฑ์** หรือลากไปยังเขตข้อมูลแผนที่ต้นไม้ หรือ**กลุ่ม**ของบานหน้าต่าง**การแสดงภาพ** ขณะนี้ คุณมีข้อมูลดีบางอย่าง
    
    ![ทรีแมปตามประเภทผลิตภัณฑ์](media/desktop-tutorial-create-measures/meastut_nspu_byproductcat.png)
    
7. ให้พยายามลบเขตข้อมูล **ProductCategory** และลากเขตข้อมูล**ProductName**ไปยังแผนภูมิแทน 
    
    ![ทรีแมปตามชื่อผลิตภัณฑ์](media/desktop-tutorial-create-measures/meastut_nspu_byproductname.png)
    
   ตกลง ขณะนี้เรากำลังเล่นอยู่เท่านั้น แต่คุณจำเป็นต้องยอมรับว่ามันยอดเยี่ยม ทดลองใช้วิธีอื่นๆ ในการกรองและจัดรูปแบบการแสดงภาพ

## <a name="what-youve-learned"></a>สิ่งที่คุณได้เรียนรู้
หน่วยวัดจะช่วยให้คุณสามารถรับข้อมูลเชิงลึกที่คุณต้องการจากข้อมูลของคุณ คุณได้เรียนรู้วิธีการสร้างหน่วยวัดโดยใช้แถบสูตร ตั้งชือให้เหมาะสมที่สุด และค้นหาและเลือกองค์ประกอบของสูตรที่ใช่ โดยใช้รายการคำแนะนำของ DAX คุณถูกแนะนำให้รู้จักกับบริบท ซึ่งเป็นผลลัพธ์ของการคำนวณ ที่หน่วยวัดได้เปลี่ยนตามเขตข้อมูลอื่นๆ หรือนิพจน์อื่นๆในสูตรของคุณ

## <a name="next-steps"></a>ขั้นตอนถัดไป
- เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับตัววัดแบบด่วนของ Power BI Desktop ที่มีการคำนวณหน่วยวัดทั่วไปมากมายให้คุณ ให้ดู[ใช้ตัววัดแบบด่วนเพื่อดำเนินการการคำนวณทั่วไปและแบบมีประสิทธิภาพได้อย่างง่ายดาย](desktop-quick-measures.md)
  
- ถ้าคุณต้องการเจาะลึกลงในสูตร DAX และสร้างหน่วยวัดขั้นสูงเพิ่มเติม ให้ดู[พื้นฐาน DAX ใน Power BI Desktop](desktop-quickstart-learn-dax-basics.md) บทความนี้มุ่งเน้นแนวคิดพื้นฐานใน DAX เช่นไวยากรณ์ ฟังก์ชัน และทำความเข้าใจบริบทโดยละเอียด
  
- โปรดให้แน่ใจว่าได้เพิ่ม[ข้ออ้างอิง Data Analysis Expressions (DAX)](https://docs.microsoft.com/dax/index)ไปยังรายการโปรดของคุณ การอ้างอิงนี้คือที่ที่คุณสามารถค้นหาข้อมูลโดยละเอียดเกี่ยวกับไวยากรณ์ DAX ตัวดำเนินการ และฟังก์ชัน DAX มากกว่า 200 ฟังก์ชันโดยละเอียด
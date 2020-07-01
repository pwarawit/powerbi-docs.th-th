---
title: เชื่อมต่อกับข้อมูลใน Power BI Desktop
description: เชื่อมต่อกับข้อมูลใน Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 01/21/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 3319c2d3d739c1f67e5b8477de385e9dfa71e25a
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85224096"
---
# <a name="connect-to-data-sources-in-power-bi-desktop"></a>เชื่อมต่อกับแหล่งข้อมูลใน Power BI Desktop

ด้วย Power BI Desktop คุณสามารถเชื่อมต่อไปทั่วโลกแห่งข้อมูลที่กำลังขยายตัวได้อย่างง่ายดาย ถ้าคุณไม่มี Power BI Desktop คุณสามารถ[ดาวน์โหลด](https://go.microsoft.com/fwlink/?LinkID=521662)และติดตั้งได้

ใน Power BI Desktop จะมีแหล่งข้อมูลต่าง ๆ *ทุกประเภท*ที่พร้อมใช้งาน รูปต่อไปนี้แสดงวิธีการเชื่อมต่อกับข้อมูลโดยการเลือก **รับข้อมูล** > **อื่น ๆ** > **เว็บ**

![รับข้อมูลจากเว็บ](media/desktop-connect-to-data/get-data-from-the-web.png)

## <a name="example-of-connecting-to-data"></a>ตัวอย่างการเชื่อมต่อกับแหล่งข้อมูล

สำหรับตัวอย่างนี้ เราจะเชื่อมต่อไปยัง**Web**แหล่งข้อมูล

สมมติว่าคุณกำลังจะเกษียณ คุณต้องการใช้ชีวิตในสถานที่ที่มีแสงแดดเยอะ ๆ มีการเก็บภาษีที่เหมาะสม และมีการดูแลสุขภาพที่ดี หรือ... คุณอาจจะเป็นนักวิเคราะห์ข้อมูล และคุณต้องการให้ข้อมูลเหล่านั้นเป็นประโยชน์ต่อลูกค้าของคุณ เช่น ช่วยลูกค้าผู้ผลิตเสื้อกันฝนในการตั้งเป้าหมายการขายในสถานที่ที่มีฝนตก*เยอะ*

ไม่ว่าวิธีใด คุณจะพบแหล่งข้อมูลบนเว็บที่มีข้อมูลที่น่าสนใจเกี่ยวกับหัวข้อเหล่านั้น และอื่น ๆ อีกมาก

[https://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx](https://www.bankrate.com/finance/retirement/best-places-retire-how-state-ranks.aspx)

เลือก **รับข้อมูล** > **อื่น ๆ** > **เว็บ** ใน **จากเว็บ** ให้ใส่ที่อยู่

![ป้อนที่อยู่เแหล่งที่มาของเว็บ](media/desktop-connect-to-data/connecttodata_3.png)

เมื่อคุณเลือก**ตกลง** ฟังก์ชันการทำงานของ Power BI Desktop ของ *Query*จะทำงาน Power BI Desktop ติดต่อแหล่งข้อมูลเว็บ และหน้าต่าง**ตัวนำทาง**ส่งกลับผลลัพธ์ของสิ่งที่พบบนหน้าเว็บ ในกรณีนี้ จะพบตารางและเอกสารโดยรวม เราสนใจตาราง ดังนั้นเราเลือกตารางจากรายการ หน้าต่าง**ตัวนำทาง**จะแสดงตัวอย่าง

![การแสดงตัวอย่างข้อมูลในตัวนำทาง](media/desktop-connect-to-data/datasources_fromnavigatordialog.png)

ในตอนนี้ คุณสามารถแก้ไขการคิวรีก่อนทำการโหลดตาราง โดยการเลือก**แปลงข้อมูล**จากด้านล่างของหน้าต่าง หรือเพียงแค่โหลดตาราง

เลือก **แปลงข้อมูล** เพื่อโหลดตารางและเปิดใช้งานตัวแก้ไข Power Query บานหน้าต่าง**การตั้งค่าคิวรี** จะแสดงขึ้นมา ถ้าไม่ใช่ เลือก **ดู** จาก ribbon จากนั้น **การตั้งค่าคิวรี** เพื่อแสดงบานหน้าต่าง **การตั้งค่าคิวรี** ซึ่งจะมีลักษณะเช่นนี้

![ตัวแก้ไข Power Query พร้อมการตั้งค่าคิวรี](media/desktop-connect-to-data/designer_gsg_editquery.png)

คะแนนเหล่านั้นเป็นข้อความมากกว่าจะเป็นตัวเลข และเราต้องการให้มันเป็นตัวเลข ไม่มีปัญหา แค่เพียงคลิกขวาที่ส่วนหัวของคอลัมน์ และเลือก**เปลี่ยนชนิด** > **จำนวนเต็ม**เพื่อทำการเปลี่ยนแปลง เมื่อต้องเลือกมากกว่าหนึ่งคอลัมน์ ก่อนอื่นให้เลือกคอลัมน์ แล้วกดค้างที่ปุ่ม Shift เลือกคอลัมน์ที่อยู่ติดกันเพิ่มเติม และจากนั้นคลิกขวาที่ส่วนหัวของคอลัมน์เมื่อต้องเปลี่ยนคอลัมน์ที่เลือกทั้งหมด ใช้ Ctrl เมื่อต้องเลือกคอลัมน์ที่ไม่ได้อยู่ติดกัน

![เปลี่ยนชนิดข้อมูลเป็นจำนวนเต็ม](media/desktop-connect-to-data/designer_gsg_changedatatype.png)

ใน**การตั้งค่า Query** **ขั้นตอนที่กำหนดใช้**จะแสดงการเปลี่ยนแปลงทุกอย่างที่เกิดขึ้น ขณะที่คุณทำการเปลี่ยนแปลงเพิ่มเติมไปยังข้อมูลตัวแก้ไข Power Query จะบันทึกการเปลี่ยนแปลงเหล่านั้นใน**ขั้นตอนที่กำหนดใช้**เป็นส่วนที่คุณสามารถ เข้ามาดูอีกครั้ง หรือลบได้หากจำเป็น

![ขั้นตอนที่กำหนดใช้](media/desktop-connect-to-data/designer_gsg_appliedsteps_changedtype.png)

คุณยังคงสามารถทำการเปลี่ยนแปลงเพิ่มเติมไปยังตารางหลังจากที่ทำการโหลดแล้วได้ แต่ในตอนนี้ยังไม่จำเป็น เมื่อคุณทำเสร็จแล้ว ให้เลือก **ปิด & ใช้** จาก **หน้าหลัก** แถบ ribbon และ Power BI Desktop นำการเปลี่ยนแปลงไปใช้ และปิดตัวแก้ไข Power Query

![ปิดและใช้](media/desktop-connect-to-data/connecttodata_closenload.png)

ด้วยโมเดลข้อมูลที่โหลดใน**รายงาน**มุมมองใน Power BI Desktop เราสามารถเริ่มสร้างแสดงภาพ โดยการลากเขตข้อมูลลงบนพื้นที่รายงานได้

![ลากค่าไปยังพื้นที่ทำงาน](media/desktop-connect-to-data/connecttodata_dragontoreportview.png)

แน่นอนว่า นี่คือโมเดลอย่างง่ายด้วยการเชื่อมต่อข้อมูลเดียว รายงาน Power BI Desktop ส่วนใหญ่จะมีการเชื่อมต่อกับแหล่งข้อมูลอื่นที่แตกต่างกันไป สร้างรูปร่างเพื่อให้ตรงกับความต้องการของของคุณด้วยความสัมพันธ์ที่สร้างโมเดลข้อมูลที่สมบูรณ์

## <a name="next-steps"></a>ขั้นตอนถัดไป
มีมากมายหลากหลายสิ่งที่คุณสามารถทำได้ด้วย Power BI Desktop สำหรับข้อมูลเพิ่มเติมเกี่ยวกับขีดความสามารถ กรุณาดูแหล่งทรัพยากรต่อไปนี้:

* [Power BI Desktop คืออะไร](../fundamentals/desktop-what-is-desktop.md)
* [เกี่ยวกับการใช้ตัวแก้ไขคิวรีใน Power BI Desktop](../transform-model/desktop-query-overview.md)
* [แหล่งข้อมูลใน Power BI Desktop](desktop-data-sources.md)
* [จัดรูปร่างและรวมข้อมูลใน Power BI Desktop](desktop-shape-and-combine-data.md)
* [ใช้งานคิวรีที่ใช้บ่อยใน Power BI Desktop](../transform-model/desktop-common-query-tasks.md)   

ต้องการส่งคำติชมถึงเราหรือไม่ เยี่ยม! ใช้รายการเมนู**ส่งความคิดเห็น**ใน Power BI Desktop หรือเยี่ยมชม[คำติชมชุมชน](https://community.powerbi.com/t5/Community-Feedback/bd-p/community-feedback) เราหวังว่าจะได้รับคำติชมจากคุณ!

![นำส่งแนวความคิด](media/desktop-connect-to-data/sendfeedback.png)

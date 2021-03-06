---
title: รายงานที่มีการแบ่งหน้าในบริการ Power BI
description: เอกสารที่อธิบายรายงานที่มีการแบ่งหน้าและวิธีการดูรายงานดังกล่าวในบริการ Power BI
author: mihart
ms.reviewer: christopher.finlan
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: how-to
ms.date: 03/11/2020
ms.author: mihart
LocalizationGroup: Common tasks
ms.openlocfilehash: f0f2d57b1a60307cef2d848854355715dd74a412
ms.sourcegitcommit: 2131f7b075390c12659c76df94a8108226db084c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/03/2020
ms.locfileid: "87537998"
---
# <a name="paginated-reports-in-the-power-bi-service"></a>รายงานที่มีการแบ่งหน้าในบริการ Power BI

[!INCLUDE[consumer-appliesto-yyny](../includes/consumer-appliesto-yyny.md)]

คุณได้เรียนรู้เกี่ยวกับ[รายงาน Power BI](end-user-reports.md) และรายงานเหล่านี้เป็นประเภทของรายงานที่คุณน่าจะพบบ่อยที่สุด มีรายงานอีกประเภทหนึ่งที่เรียกว่า *รายงานที่มีการแบ่งหน้า* *ผู้ออกแบบ* รายงานสามารถแชร์รายงานที่มีการแบ่งหน้ากับคุณในพื้นที่ทำงานในความจุพรีเมียม หรือแอปจากพื้นที่ทำงานนั้นได้ 

## <a name="what-is-a-paginated-report"></a>รายงานที่มีการแบ่งหน้าคืออะไร?

รายงานเหล่านี้ถูกเรียกว่ารายงาน *แบบแบ่งหน้า* เนื่องจากมีการจัดรูปแบบให้พอดีกับหน้าที่พิมพ์ ข้อดีอย่างหนึ่งคือรายงานเหล่านี้แสดงข้อมูลทั้งหมดในตาราง แม้ว่าตารางนั้นต้องใช้พื้นที่หลายหน้า รายงานที่มีการแบ่งหน้าบางครั้งเรียกว่า "พิกเซลสมบูรณ์แบบ" เนื่องจาก *ผู้ออกแบบ* รายงานสามารถควบคุมการจัดวางหน้ารายงานได้อย่างแม่นยำ

เมื่อ*ผู้ออกแบบ*รายงานสร้างรายงานที่มีการแบ่งหน้า คือพวกเขากำลังสร้าง*ข้อกำหนดของรายงาน*อย่างแท้จริง ซึ่งไม่ได้มีข้อมูล แต่จะระบุว่าต้องรับเอาข้อมูลจากที่ใด เอาข้อมูลใด และแสดงข้อมูลอย่างไร เมื่อคุณเรียกดูรายงาน ตัวประมวลผลรายงานจะใช้ข้อกำหนดของรายงาน ดึงข้อมูลออกมา แล้วรวมเข้ากับเค้าโครงรายงานเพื่อสร้างรายงานขึ้น ในบางครั้ง รายงานจะแสดงข้อมูลเริ่มต้น บางครั้งคุณจำเป็นต้องป้อนพารามิเตอร์ก่อนรายงานจึงสามารถแสดงข้อมูลใดก็ตามได้ 

   ![พารามิเตอร์สำหรับรายงาน](./media/end-user-paginated-report/power-bi-report-parameters.png)

และโดยทั่วไปแล้ว นั่นคือขอบเขตของการโต้ตอบ - การตั้งค่าพารามิเตอร์ หากคุณเป็นนักวิเคราะห์การเรียกเก็บเงิน คุณอาจใช้รายงานที่มีการแบ่งหน้าเพื่อสร้างหรือพิมพ์ใบแจ้งหนี้ได้ หากคุณเป็นผู้จัดการฝ่ายขาย คุณสามารถใช้รายงานที่มีการแบ่งหน้าเพื่อดูคำสั่งซื้อตามร้านค้าหรือพนักงานขายได้ 

รายงานที่มีการแบ่งหน้าแบบง่ายนี้จะสร้างผลกำไรตามปีหลังจากที่คุณเลือกพารามิเตอร์ **Year (ปี)** 

![รายงานอย่างง่ายแบบหนึ่งพารามิเตอร์](./media/end-user-paginated-report/power-bi-report-simple.png)

เมื่อเปรียบเทียบกับรายงานที่มีการแบ่งหน้า Power BI นั้นตอบสนองได้มากกว่ามาก รายงาน Power BI อนุญาตให้มีการรายงานแบบเฉพาะกิจ และรองรับวิชวลประเภทอื่น ๆ อีกมากมาย รวมถึงวิชวล Power BI

## <a name="identify-a-paginated-report"></a>ระบุรายงานที่มีการแบ่งหน้า

ในรายการเนื้อหาและในหน้า Landing Page คุณสามารถระบุรายงานที่มีการแบ่งหน้าได้โดยไอคอนของรายงานเหล่านั้น ![ไอคอนรายงานที่มีการแบ่งหน้า](media/end-user-paginated-report/power-bi-report-icon.png)  ซึ่งสามารถแชร์รายงานที่มีการแบ่งหน้ากับคุณได้โดยตรง หรือให้เป็นส่วนหนึ่งของ [แอป Power BI](end-user-apps.md) หาก*ผู้ออกแบบ*รายงานให้สิทธิ์แก่คุณ คุณจะสามารถแชร์รายงานที่มีการแบ่งหน้า และสมัครใช้งานด้วยตัวคุณเองและผู้อื่นได้

![รายการรายงานที่แสดงไอคอนที่แตกต่างกัน](./media/end-user-paginated-report/power-bi-report-list.png)

## <a name="interact-with-a-paginated-report"></a>โต้ตอบกับรายงานที่มีการแบ่งหน้า

วิธีที่คุณโต้ตอบกับรายงานที่มีการแบ่งหน้านั้นแตกต่างจากรายงานอื่น คุณสามารถทำสิ่งต่าง ๆ เช่น พิมพ์ บุ๊กมาร์ก ส่งออก และแสดงความคิดเห็น แต่มีการโต้ตอบน้อยลง บ่อยครั้งที่รายงานที่มีการแบ่งหน้าต้องการอินพุตจากคุณเพื่อเติมข้อมูลลงในพื้นที่รายงาน  ในบางครั้งรายงานจะแสดงข้อมูลค่าเริ่มต้น และคุณสามารถป้อนพารามิเตอร์เพื่อดูข้อมูลที่แตกต่างกันได้

### <a name="print-a-paginated-report"></a>พิมพ์รายงานที่มีการแบ่งหน้า

รายงาน*ที่มีการแบ่งหน้า*ถูกจัดรูปแบบเพื่อให้พอดีกับหน้าและพิมพ์ออกมาได้ด้วย สิ่งที่คุณเห็นในเบราว์เซอร์คือสิ่งที่คุณเห็นเมื่อคุณพิมพ์ออกมา นอกจากนี้ หากรายงานมีตารางยาว ทั้งตารางจะถูกพิมพ์ออกมาแม้ว่าจะครอบคลุมหลายหน้าก็ตาม 

รายงานแบบแบ่งหน้าสามารถมีหลายหน้าได้ ตัวอย่าง รายงานฉบับนี้มี 563 หน้า แต่ละหน้ามีรูปแบบเหมือนกัน โดยใช้หนึ่งหน้าต่อใบแจ้งหนี้หนึ่งใบ และมีส่วนหัวกับส่วนท้ายหน้าซ้ำกัน เมื่อคุณพิมพ์รายงานนี้ คุณจะได้รับตัวแบ่งหน้าระหว่างใบแจ้งหนี้

   ![หน้าหนึ่งของรรายงานที่มีการแบ่งหน้าสำหรับของเล่น Tailspin](./media/end-user-paginated-report/power-bi-paginated-500.png)


### <a name="navigate-the-paginated-report"></a>นำทางไปยังรายงานที่มีการแบ่งหน้า

ในรายงานคำสั่งขายนี้ มีพารามิเตอร์สามตัวดังนี้ ประเภทธุรกิจ ผู้ค้าปลีก และหมายเลขคำสั่งซื้อ 

![รายงานที่มีสามพารามิเตอร์](./media/end-user-paginated-report/power-bi-parameter.png)

หากต้องการเปลี่ยนแปลงข้อมูลที่แสดง ให้ป้อนค่าใหม่สำหรับพารามิเตอร์สามรายการและเลือก **ดูรายงาน** ที่นี่ เราได้เลือก **ร้านจักรยานชนิดพิเศษ**, **Alpine Ski House** และหมายเลขคำสั่งซื้อ **SO46085** การเลือก **ดูรายงาน** รีเฟรชพื้นที่รายงานของเราด้วยคำสั่งขายใหม่นี้

![เปลี่ยนพารามิเตอร์](./media/end-user-paginated-report/power-bi-order.png)

คำสั่งขายใหม่จะแสดงขึ้นโดยใช้พารามิเตอร์ที่เราเลือก 

![คำสั่งขายใหม่](./media/end-user-paginated-report/power-bi-new-order.png)

รายงานที่มีการแบ่งหน้าบางรายงานมีหลายหน้า  ใช้ตัวควบคุมหน้าเพื่อนำทางไปยังรายงาน 

![ตัวควบคุมหน้า](./media/end-user-paginated-report/power-bi-page.png)

### <a name="export-the-paginated-report"></a>ส่งออกรายงานที่มีการแบ่งหน้า
คุณมีตัวเลือกมากมายสำหรับการส่งออกรายงานที่มีการแบ่งหน้า รวมทั้ง PDF, Word, XML, PowerPoint, Excel และอื่นๆ อีกมากมาย เมื่อส่งออกรายงาน จะมีการเก็บรักษาการจัดรูปแบบให้มากที่สุดเท่าที่เป็นไปได้ รายงานที่มีการแบ่งหน้าที่ส่งออกไปยัง Excel, Word, PowerPoint, MHTML และ PDF ตัวอย่างเช่น เก็บรักษาการจัดรูปแบบ "พิกเซลสมบูรณ์แบบ" 

![คำสั่งขายใหม่](./media/end-user-paginated-report/power-bi-exporting.png)

![การส่งออกที่แตกต่างกันสี่ประเภท](./media/end-user-paginated-report/power-bi-four.png)

### <a name="subscribe-to-the-paginated-report"></a>สมัครใช้งานรายงานที่มีการแบ่งหน้า
เมื่อคุณสมัครใช้งานรายงานที่มีการแบ่งหน้า Power BI จะส่งอีเมลพร้อมกับรายงานเป็นเอกสารแนบมาให้ ในการตั้งค่าการสมัครใช้งานของคุณ คุณเลือกจำนวนครั้งที่คุณต้องการรับอีเมล: รายวัน รายสัปดาห์ รายชั่วโมง หรือรายเดือน การสมัครใช้งานประกอบด้วยเอกสารแนบของเอาต์พุตรายงานทั้งหมด ขนาดสูงสุด 25 MB ส่งออกรายงานทั้งหมดหรือเลือกพารามิเตอร์ล่วงหน้า เลือกจากไฟล์แนบที่แตกต่างกันมากมาย ได้แก่ Excel, PDF, PowerPoint และอื่น ๆ อีกมากมาย  

![รูปแบบสำหรับการสมัครใช้งาน](./media/end-user-paginated-report/power-bi-export-list.png)

## <a name="considerations-and-troubleshooting"></a>ข้อควรพิจารณาและการแก้ไขปัญหา

- รายงานที่มีการแบ่งหน้าสามารถปรากฏขึ้นเป็นรายงานว่างเปล่าจนกว่าคุณจะเลือกพารามิเตอร์ และเลือก **ดูรายงาน**

- หากคุณไม่มีรายงานที่มีการแบ่งหน้า อาจเป็นเพราะไม่มีใครแบ่งปันรายงานประเภทนี้กับคุณ นอกจากนี้ยังอาจหมายความว่าผู้ดูแลระบบของคุณยังไม่ได้เปิดใช้งานรายงานที่มีการแบ่งหน้าสำหรับคุณอีกด้วย 

 

## <a name="next-steps"></a>ขั้นตอนถัดไป
- [รายงาน Power BI](end-user-reports.md)
- มีคำถามเพิ่มเติมหรือไม่ ลองไปที่ [ชุมชน Power BI](https://community.powerbi.com/)


---
title: เคล็ดลับการออกแบบรายงานของตัวสร้างรายงานใน Power BI
description: ใช้เคล็ดลับต่อไปนี้ในการช่วยออกแบบรายงานแบบแบ่งหน้าของตัวสร้างรายงานใน Power BI
ms.date: 06/06/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: c1490ff0-5b8a-43c1-8d22-e459395db4f6
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 13b9e37d4a64493dfdcac02d9df86a1e19a1c24b
ms.sourcegitcommit: ced8c9d6c365cab6f63fbe8367fb33e6d827cb97
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/07/2020
ms.locfileid: "78921182"
---
# <a name="report-design-tips-in-power-bi-report-builder"></a>เคล็ดลับการออกแบบรายงานของตัวสร้างรายงานใน Power BI
  ใช้เคล็ดลับต่อไปนี้ในการช่วยออกแบบรายงานแบบแบ่งหน้าของตัวสร้างรายงานใน Power BI  
  
   
  
##  <a name="DesigningReports"></a> รายงานการออกแบบ  
  
-   รายงานที่มีการออกแบบที่ดีแสดงถึงข้อมูลที่จะนำไปสู่การดำเนินการ ระบุคำถามที่รายงานจะช่วยตอบ เก็บคำถามเหล่านั้นไว้ในใจ เมื่อคุณออกแบบรายงาน  
  
-   ในการออกแบบการจัดรูปแบบการแสดงข้อมูลที่มีประสิทธิภาพ ลองคิดถึงวิธีในการแสดงข้อมูลที่ง่ายต่อการเข้าใจของผู้ใช้รายงาน เลือกขอบเขตข้อมูลที่เหมาะสมกับข้อมูลที่คุณต้องการจะแสดงผลด้วยภาพ ตัวอย่างเช่น แผนภูมิแสดงถึงข้อสรุปและข้อมูลที่รวบรวมได้อย่างมีประสิทธิภาพ ซึ่งดีกว่าตารางที่ครอบคลุมข้อมูลที่มีรายละเอียดหลายหน้า คุณสามารถแสดงข้อมูลด้วยภาพจากชุดข้อมูลในขอบเขตข้อมูลใดๆ ซึ่งรวมถึงแผนภูมิ แผนที่ ตัวบ่งชี้ เส้นแบบประกายไฟ แถบข้อมูล และข้อมูลแบบตารางในเค้าโครงเส้นตารางต่างๆ ตาม tablix 
  
-   หากคุณวางแผนที่จะส่งรายงานในรูปแบบการส่งออกที่เฉพาะเจาะจง ให้ทดสอบรูปแบบการส่งออกในการออกแบบของคุณก่อน การสนับสนุนคุณลักษณะแตกต่างกันไปตามการแสดงที่คุณเลือก  
  
-   เมื่อคุณสร้างเค้าโครงที่ซับซ้อนขึ้น ให้สร้างเค้าโครงนั้นในพื้นที่แสดง คุณสามารถใช้สี่เหลี่ยมผืนผ้าเป็นที่บรรจุในการจัดการหน่วยข้อมูลของรายงานได้ คุณสามารถสร้างขอบเขตข้อมูลบนพื้นผิวการออกแบบได้โดยตรงเพื่อขยายพื้นที่การทำงานของคุณให้มากที่สุด และจากนั้นเมื่อคุณทำแต่ละงานเสร็จ ลากไปยังที่บรรจุสี่เหลี่ยมผืนผ้า ในการใช้สี่เหลี่ยมผืนผ้าเป็นที่บรรจุนั้น คุณสามารถจัดวางตำแหน่งเนื้อหาทั้งหมดได้ในขั้นตอนเดียว นอกจากนี้ สี่เหลี่ยมผืนผ้ายังสามารถช่วยควบคุมวิธีที่หน่วยข้อมูลของรายงานในแต่ละหน้าได้  
  
-   เพื่อลดกองข้อความในรายงาน ให้พิจารณาการใช้การมองเห็นได้ตามเงื่อนไขสำหรับหน่วยข้อมูลของรายงานที่เฉพาะเจาะจงและให้ผู้ใช้เลือกว่าจะแสดงหน่วยข้อมูลหรือไม่ คุณสามารถตั้งค่าการมองเห็นตามพารามิเตอร์หรือกล่องข้อความสลับได้ คุณสามารถเพิ่มกล่องข้อความที่ซ่อนตามเงื่อนไขได้ในการแสดงผลนิพจน์ชั่วคราว เมื่อรายงานแสดงข้อมูลที่ไม่คาดคิด คุณสามารถแสดงผลชั่วคราวในการช่วยแก้จุดบกพร่องของนิพจน์  
  
-   เมื่อคุณทำงานกับหน่วยข้อมูลที่ซ้อนกันในเซลล์ tablix หรือสี่เหลี่ยมผืนผ้า คุณสามารถตั้งค่าสีพื้นหลังต่างๆ สำหรับที่บรรจุและหน่วยข้อมูลที่มีอยู่ได้ ตามค่าเริ่มต้น สีพื้นหลังจะ **ไม่มีสี** หน่วยข้อมูลที่มีสีพื้นหลังที่เจาะจงจะแสดงผ่านหน่วยข้อมูลที่มีสีพื้นหลังที่ตั้งค่าเป็น **ไม่มีสี** เทคนิคนี้สามารถช่วยให้คุณเลือกหน่วยข้อมูลที่ถูกต้องในการตั้งค่าคุณสมบัติการแสดงผล เช่น เส้นขอบการมองเห็นบนเซลล์ tablix  
  
 สำหรับข้อมูลเพิ่มเติมเกี่ยวกับสิ่งที่จะพิจารณาเมื่อคุณออกแบบรายงานของคุณ ดูที่[การวางแผนรายงานในผู้สร้างรายงาน](report-builder-planning-report.md))  
  
##  <a name="NamingConventions"></a> ข้อกำหนดการตั้งชื่อสำหรับรายงาน แหล่งข้อมูลและชุดข้อมูล  
  
-   ใช้ข้อกำหนดการตั้งชื่อสำหรับแหล่งข้อมูลและชุดข้อมูลที่บันทึกแหล่งของข้อมูล  
  
    1.  **แหล่งข้อมูล** หากคุณไม่ต้องการใช้เซิร์ฟเวอร์หรือชุดข้อมูลจริงเนื่องจากเหตุผลทางด้านความปลอดภัย ให้ใช้นามแฝงที่บ่งชี้ผู้ใช้ว่าแหล่งของข้อมูลคืออะไร  
  
    2.  **ชุดข้อมูล** ใช้ชื่อที่บ่งชี้ว่าชุดข้อมูลขึ้นอยู่กับแหล่งข้อมูลใด  
  
##  <a name="Data"></a> การทำงานกับข้อมูล  
  
-   ตามขั้นตอนแรก นำข้อมูลทั้งหมดที่คุณต้องการใช้ในการทำงานให้ปรากฏในบานหน้าต่างข้อมูลรายงาน เมื่อคุณกลั่นกรองคำถามที่รายงานถูกออกแบบขึ้นมาเพื่อตอบคำถาม ให้คิดถึงวิธีการจำกัดข้อมูลในชุดข้อมูลรายงานเพื่อพิจารณาว่าสิ่งใดจำเป็น  
  
-   โดยทั่วไปแล้ว ให้รวมข้อมูลที่คุณจะแสดงในรายงานเท่านั้น ใช้ตัวแปรคิวรีในคิวรีชุดข้อมูลของคุณเพื่อให้ผู้ใช้สามารถเลือกว่าข้อมูลใดที่พวกเขาต้องการเห็นในรายงาน หากคุณกำลังสร้างชุดข้อมูลที่ใช้ร่วมกัน ให้จัดเตรียมตัวกรองตามพารามิเตอร์ในการจัดเตรียมระบบการทำงานเดียวกัน  
  
-   หากคุณคือนักเขียนแบบสอบถามที่มีประสบการณ์ เข้าใจสำหรับจำนวนข้อมูลขนาดกลาง คุณอาจจะต้องการข้อมูลกลุ่มในรายงานและไม่ต้องการในแบบสอบถาม หากคุณทำการจัดกลุ่มของคุณทั้งหมดในคิวรี แสดงว่ารายงานมีแนวโน้มว่าจะเป็นการนำเสนอชุดผลลัพธ์ของคิวรี ในทางกลับกัน ในการแสดงค่ารวมสำหรับจำนวนข้อมูลขนาดใหญ่บนแผนภูมิหรือเมทริกซ์ ไม่มีความจำเป็นที่จะต้องรวมข้อมูลรายละเอียด  
  
-   ตามข้อกำหนดของคุณ คุณสามารถแสดงชื่อและตำแหน่งที่ตั้งของแหล่งข้อมูลรายงาน ข้อความคำสั่งสำหรับแบบสอบถามของชุดข้อมูลและค่าพารามิเตอร์ในรายงานได้ คำถามแรกที่ผู้ใช้ใหม่หลายคนมี คือ ข้อมูลมาจากที่ใด ในการลดกองข้อความในรายงาน คุณสามารถซ่อนกล่องข้อความตามเงื่อนไขด้วยข้อมูลประเภทนี้และให้ผู้ใช้เลือกว่าต้องการจะเห็นมันหรือไม่ ลองทำการเพิ่มข้อมูลนี้ลงในหน้าสุดท้ายของรายงาน ตั้งค่าการมองเห็นกล่องข้อความตามพารามิเตอร์ที่ผู้ใช้สามารถเปลี่ยนได้  
  
##  <a name="DesignSurface"></a> การโต้ตอบด้วยพื้นผิวการออกแบบรายงาน  
 พื้นผิวการออกแบบรายงานไม่ใช่ WYSIWIG เมื่อคุณวางหน่วยข้อมูลของรายงานลงในพื้นผิวการออกแบบ ตำแหน่งที่สัมพันธ์กันจะส่งผลกระทบต่อวิธีที่หน่วยข้อมูลปรากฏในหน้ารายงานที่แสดง ช่องว่างถูกป้องกันไว้  
  
-   ใช้เส้นช่วยจัดแนวและปุ่มเค้าโครงในการจัดแนวและจัดเรียงหน่วยข้อมูลบนพื้นผิวการออกแบบรายงาน ตัวอย่างเช่น คุณสามารถจัดแนวด้านบนหรือขอบของหน่วยข้อมูลที่เลือก ขยายหน่วยข้อมูลให้เหมาะกับขนาดของหน่วยข้อมูลอื่นๆ หรือปรับพื้นที่ระหว่างหน่วยข้อมูลได้  
  
-   ใช้แป้นลูกศรในการปรับตำแหน่งและขนาดของหน่วยข้อมูลที่เลือกบนพื้นผิวการออกแบบ ตัวอย่างเช่น การกดแป้นพิมพ์พร้อมกันต่อไปนี้จะเป็นประโยชน์มาก:  
  
    -   **แป้นลูกศร** ย้ายหน่วยข้อมูลของรายงานที่เลือก  
  
    -   **CTRL+แป้นลูกศร** เลื่อนหน่วยข้อมูลของรายงานที่เลือก  
  
    -   **CTRL+SHIFT+แป้นลูกศร** เพิ่มหรือลดขนาดของหน่วยข้อมูลของรายงานที่เลือก  
  
-   เพื่อเพิ่มหน่วยข้อมูลไปยังสี่เหลี่ยมผืนผ้า ให้ใช้เคล็ดลับด้านบนซ้ายของเมาส์ในการชี้ไปยังตำแหน่งเริ่มต้นของหน่วยข้อมูลในที่บรรจุสี่เหลี่ยมพื้นผ้า ใช้แป้นพิมพ์ลัดเพื่อช่วยบอกตำแหน่งของวัตถุที่เลือก สี่เหลี่ยมผืนผ้าขยายโดยอัตโนมัติเพื่อรองรับขนาดของหน่วยข้อมูลที่มียู่  
  
-   เพื่อเพิ่มหน่วยข้อมูลหลายหน่วยข้อมูลไปยังเซลล์ tablix ให้เพิ่มสี่เหลี่ยมผืนผ้าก่อน จากนั้นเพิ่มหน่วยข้อมูล  
  
     ตามค่าเริ่มต้น เซลล์ tablix แต่ละเซลล์จะมีกล่องข้อความ เมื่อคุณเพิ่มสี่เหลี่ยมผืนผ้าไปยังเซลล์ สี่เหลี่ยมผืนผ้าจะแทนที่กล่องข้อความ ตัวอย่างเช่น วางตัวบ่งชี้ที่ซ้อนกันในสี่เหลี่ยมผืนผ้า ในเซลล์ tablix เพื่อช่วยในการควบคุมวิธีการขยายขนาดของแผนภูมิหรือตัวบ่งชี้ เมื่อคุณปรับความสูงของแถวที่เซลล์อยู่  
  
-   ใช้ **ย่อ/ขยาย** เพื่อปรับมุมมองพื้นผิวการออกแบบของคุณ คุณสามารถใช้งานกับหน้าทั้งหมดหรือส่วนที่เล็กลงของหน้าได้  
  
-   เพื่อลากฟิลด์จากบานหน้าต่างข้อมูลของรายงานไปยังบานหน้าต่างการจัดกลุ่ม ให้หลีกเลี่ยงการลากฟิลด์ข้ามหน่วยข้อมูลของรายงานอื่นๆ บนพื้นผิวการออกแบบ เนื่องจากสิ่งนี้เลือกหน่วยข้อมูลอื่นหรือไม่เลือกขอบฟิลด์ tablix ลากฟิลด์ลงไปยังบานหน้าต่างข้อมูลของรายงาน จากนั้นข้ามไปยังบานหน้าต่างการจัดกลุ่ม  
  
###  <a name="Selecting"></a> การเลือกหน่วยข้อมูล  
 เพื่อช่วยในการเลือกวัตถุที่คุณต้องการบนพื้นผิวการออกแบบรายงาน ให้ใช้แป้น ESC คลิกขวาที่เมนูบริบท บานหน้าต่างคุณสมบัติและบานหน้าต่างการจัดกลุ่ม  
  
-   -   กด ESC ในการวนดูสแตกหน่วยข้อมูลของรายงานที่อยู่ในพื้นที่เดียวกันบนพื้นผิวการออกแบบ  
  
    -   บนหน่วยข้อมูลของรายงานบางอย่าง ให้ลองทำการคลิกขวาที่เมนูบริบทเพื่อเลือกหน่วยข้อมูลของรายงานหรือหน่วยข้อมูลของรายงานบางส่วนที่คุณต้องการ  
  
    -   บานหน้าต่างคุณสมบัติแสดงคุณสมบัติสำหรับการเลือกในปัจจุบัน  
  
    -   เพื่อใช้งานกับกลุ่มแถวและกลุ่มคอลัมน์ในขอบเขตข้อมูล tablix ให้เลือกกลุ่มจากบานหน้าต่างการจัดกลุ่ม  

  
##  <a name="ReportItems"></a> การทำงานกับประเภทที่เฉพาะเจาะจงหน่วยข้อมูลของรายงาน  
  
###  <a name="Parameters"></a> การทำงานกับพารามิเตอร์  
  
-   วัตถุประสงค์หลักของพารามิเตอร์รายงาน คือ เพื่อกรองข้อมูลที่แหล่งข้อมูล และเรียกดูเฉพาะข้อมูลที่จำเป็นสำหรับวัตถุประสงค์ของรายงาน  
  
-   สำหรับพารามิเตอร์รายงานนั้น ให้หาจุดสมดุลระหว่างการเปิดใช้งานการโต้ตอบและการช่วยเหลือผู้ใช้ให้ได้รับผลที่พวกเขาต้องการ ตัวอย่างเช่น คุณสามารถตั้งค่าเริ่มต้นสำหรับพารามิเตอร์เพื่อหาค่าที่คุณรู้ว่าเป็นที่นิยมได้  
  
###  <a name="Text"></a> การทำงานกับข้อความ  
  
-   เมื่อคุณวางบรรทัดหลายบรรทัดลงในกล่องข้อความ ข้อความจะถูกเพิ่มเป็นการเรียกใช้ข้อความหนึ่ง การเรียกใช้แต่ละข้อความสามารถจัดรูปแบบได้เป็นหน่วยเท่านั้น เพื่อจัดรูปแบบบรรทัดอย่างอิสระ ให้แทรกบรรทัดใหม่โดยการกดย้อนกลับในการเรียกใช้ข้อความตามต้องการ คุณสามารถใช้การจัดรูปแบบและสไตล์กับบรรทัดข้อความอิสระแต่ละบรรทัดในกล่องข้อความได้  
  
-   คุณสามารถตั้งค่ารูปแบบคุณสมบัติและการดำเนินการบนกล่องข้อความหรือบนตัวแทนข้อความในกล่องข้อความ หากมีบรรทัดข้อความเพียงหนึ่งบรรทัด การตั้งค่าคุณสมบัติบนกล่องข้อความจะมีประสิทธิภาพมากกว่าบนข้อความ  
  
###  <a name="Expressions"></a> การทำงานกับนิพจน์  
  
-   เข้าใจรูปแบบนิพจน์ธรรมดาและรูปแบบนิพจน์ที่ซับซ้อน คุณสามารถพิมพ์รูปแบบนิพจน์ธรรมดาลงในกล่องข้อความ คุณสมบัติในบานหน้าต่างคุณสมบัติหรือในตำแหน่งที่ตั้งในกล่องโต้ตอบที่รับนิพจน์ได้โดยตรง
  
-   เมื่อคุณสร้างนิพจน์ มันจะช่วยสร้างแต่ละส่วนอย่างอิสระและตรวจสอบค่าของมัน จากนั้นคุณสามารถรวมส่วนทั้งหมดลงในนิพจน์สุดท้ายได้ เทคนิคที่เป็นประโยชน์ในการเพิ่มกล่องข้อความในเซลล์เมทริกซ์ แสดงนิพจน์แต่ละส่วน และตั้งค่าการมองเห็นได้ตามเงื่อนไขบนกล่องข้อความ หากต้องการควบคุมรูปแบบและสีของเส้นขอบ เมื่อกล่องข้อความถูกซ่อน อันดับแรกให้วางกล่องข้อความในสี่เหลี่ยมผืนผ้า และจากนั้นตั้งค่าสไตล์และสีเส้นขอบของสี่เหลี่ยมผืนผ้าให้เหมาะกับเมทริกซ์  
  
###  <a name="Indicators"></a> การทำงานกับตัวบ่งชี้  
  
-   ตามค่าเริ่มต้น ตัวบ่งชี้แสดงอย่างน้อยสามสถานะ หลังจากที่คุณเพิ่มตัวบ่งชี้ไปยังรายงาน คุณสามารถกำหนดค่าได้โดยการเพิ่มหรือการลบสถานะออก เพื่อให้ผู้ใช้งานของคุณมองได้ง่ายขึ้น เลือกตัวบ่งชี้ที่หลากหลายทั้งสีและรูปร่าง  
  
##  <a name="Rendering"></a> การควบคุมการแสดงภาพหน่วยข้อมูลของรายงานบนหน้ารายงาน  
  
-   บนพื้นผิวการออกแบบรายงาน หน่วยข้อมูลของรายงานจะเพิ่มขึ้นเพื่อรอบรับเนื้อหาจากชุดข้อมูล นิพจน์ รายงานย่อย หรือข้อความที่เกี่ยวข้อง  
  
    -   เมื่อคุณบอกตำแหน่งหน่วยข้อมูลบนหน้ารายงาน ระยะระหว่างหน่วยข้อมูลนั้นและหน่วยข้อมูลทั้งหมดที่เริ่มไปทางด้านขวานั้นจะกลายเป็นระยะสั้นที่สุดที่จะต้องรักษาไว้ เมื่อรายงานเพิ่มขึ้นในแนวนอน เช่นเดียวกัน ระยะระหว่างหน่วยข้อมูลและหน่วยข้อมูลด้านบนจะกลายเป็นระยะสั้นที่สุดที่จะต้องรักษาไว้ เมื่อหน่วยข้อมูลที่อยู่ด้านบนเพิ่มขึ้นในแนวตั้ง  
  
    -   หน่วยข้อมูลในรายงานเพิ่มขึ้นเพื่อรองรับข้อมูลนั้นและผลักขั้นของหน่วยข้อมูล (หน่วยข้อมูลที่มีที่บรรจุหลักเดียวกัน) ออกจากวิธีในการใช้กฎต่อไปนี้:  
  
    -   แต่ละหน่วยข้อมูลจะย้ายลงไปเพื่อรักษาพื้นที่เล็กที่สุดระหว่างตัวมันเองและหน่วยข้อมูลอื่นที่จบลงด้านบนนี้  
  
    -   แต่ละหน่วยข้อมูลจะย้ายไปทางขวาเพื่อรักษาพื้นที่เล็กที่สุดระหว่างตัวมันเองและหน่วยข้อมูลอื่นที่จบลงด้านซ้ายของมัน สำหรับระบบที่เค้าโครงจากขวาไปซ้าย แต่ละหน่วยข้อมูลย้ายไปทางซ้ายเพื่อรักษาพื้นที่เล็กที่สุดระหว่างตัวมันเองและหน่วยข้อมูลอื่นที่จบลงด้านขวาของมัน  
  
    -   ที่บรรจุขยายเพื่อรองรับการเพิ่มขึ้นของหน่วยข้อมูลย่อย สำหรับหน่วยข้อมูลที่เลือก ในบานหน้าต่างคุณสมบัติ คุณสมบัติหลักจะระบุในที่บรรจุสำหรับหน่วยข้อมูลนั้น นอกจากนี้ คุณยังสามารถใช้บานหน้าต่างเค้าโครงของเอกสารในการดูลำดับชั้นการบรรจุหน่วยข้อมูลของรายงานได้  
  
    -   แถบเครื่องมือ **เค้าโครง** จัดเตรียมหลากหลายปุ่มเพื่อช่วยในการจัดแนวขอบ กึ่งกลาง และระยะห่างสำหรับหน่วยข้อมูลของรายงาน เพื่อเปิดใช้งานแถบเครื่องมือ**เค้าโครง**จาก**มุมมอง**เมนูชี้ไปยัง**แถบเครื่องมือ** และจากนั้นคลิกที่**เค้าโครง**  
  
-   หากคุณวางแผนที่จะบันทึกรายงานเป็นไฟล์ .pdf ความกว้างของรายงานจะต้องถูกตั้งค่าอย่างชัดเจนซึ่งให้ผลที่คุณต้องการในรูปแบบไฟล์ที่ส่งออก ตัวอย่างเช่น ตั้งค่าความกว้างของหน้ารายงานเป็น 7.9375 นิ้วและระยะขอบด้านซ่ายและด้านขวาเป็น 0.5 นิ้ว  
  
-   ใช้ **เค้าโครงการพิมพ์** และ **การตั้งค่าหน้ากระดาษ**บนแถบเครื่องมือตัวดูรายงานเพื่อแสดงรายงานในมุมมองการพิมพ์ที่สอดคล้องกัน หากต้องการช่วยลบหน้าที่ไม่จำเป็น ให้ทำตามขั้นตอนต่อไปนี้:  
  
    1.  ลบช่องว่างเพิ่มเติมทั้งหมดระหว่างขอบเขตข้อมูลและขอบของรายงานออก  
  
    2.  ลดระยะขอบของหน้าใน**คุณสมบัติของรายงาน**กล่องโต้ตอบ  
  
    3.  ใช้ **สี่เหลี่ยมผืนผ้า** เป็นที่บรรจุในการช่วยควบคุมวิธีแสดงหน่วยข้อมูลของรายงาน  
  
    4.  ในส่วนหัวของคอลัมน์ ให้เปลี่ยนคุณสมบัติของกล่องข้อความโหมดการเขียนเป็นการใช้ข้อความแนวตั้ง  

 สำหรับคำแนะนำเพิ่มเติมดู [หลีกเลี่ยงหน้าเปล่าเมื่อพิมพ์รายงานแบบแบ่งหน้า](../guidance/report-paginated-blank-page.md)

 การรวมกันของพฤติกรรมนี้ คุณสมบัติความกว้างและความสูงหน่วยของข้อมูลรายงาน ขนาดเนื้อความของรายงาน คำจำกัดความของความสูงและความกว้างของหน้า การตั้งค่าระยะขอบของรายงานหลักและส่วนที่รองรับการแสดงภาพที่เฉพาะเจาะจงสำหรับวิธีการจัดการเพจทั้งหมดรวมกันเพื่อกำหนดว่าหน่วยข้อมูลของรายงานใดที่เหมาะสมกับหน้าที่แสดง
 
## <a name="next-steps"></a>ขั้นตอนถัดไป

- [รายงานแบบแบ่งหน้าใน Power BI Premium คืออะไร](paginated-reports-report-builder-power-bi.md)  
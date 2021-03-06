---
title: ตัวสร้างรายงานใน Power BI
description: ตัวสร้างรายงานใน Power BI เป็นเครื่องมือสำหรับเขียนรายงานแบบแบ่งหน้า
ms.date: 07/08/2020
ms.service: powerbi
ms.subservice: report-builder
featuredvideoid: 78TZeiEhveY
ms.topic: conceptual
ms.assetid: 55bf4f9c-d037-412f-ae57-3fc39ce32fa5
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: f74fb596fb2a080922d0e62a4492ef6c8ccd4e0d
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/10/2020
ms.locfileid: "86216740"
---
# <a name="power-bi-report-builder"></a>ตัวสร้างรายงานใน Power BI

 เครื่องมือตัวสร้างรายงาน Power BI เป็นเครื่องมือสำหรับการสร้างรายงานที่มีการแบ่งหน้าซึ่งคุณสามารถเผยแพร่ไปยังบริการ Power BI ได้  เมื่อคุณออกแบบรายงานที่มีการแบ่งหน้า คุณกำลังสร้างข้อกำหนดของรายงานที่ระบุว่าจะเรียกใช้ข้อมูลใด สถานที่เรียก และวิธีแสดงข้อมูลดังกล่าว เมื่อคุณเรียกดูรายงาน ตัวประมวลผลรายงานจะใช้ข้อกำหนดของรายงานที่คุณได้ระบุไว้ ดึงเอาข้อมูลนั้นมา แล้วรวมเข้ากับเค้าโครงรายงานเพื่อสร้างรายงานขึ้น คุณดูรายงานของคุณได้ก่อนในตัวสร้างรายงาน จากนั้น คุณจะเผยแพร่รายงานไปยังบริการของ Power BI
 
พร้อมที่จะเริ่มการเขียนหรือไม่ [ติดตั้งตัวสร้างรายงาน Power BI](https://aka.ms/pbireportbuilder) จากศูนย์ดาวน์โหลด Microsoft

คุณอยากเรียนรู้จากวิดิโอมากกว่าใช่ไหม ดู[หลักสูตรที่สอนผ่านวิดีโอ: การเรียนรู้เกี่ยวกับรายงานแบบแบ่งหน้าของ Power BI ในวันเดียว](../learning-catalog/paginated-reports-online-course.md)

รายงานที่มีเลขต่อไปนี้มีเมทริกซ์ที่มีกลุ่มแถว และคอลัมน์เส้นแบบประกายไฟ ตัวบ่งชี้และแผนภูมิวงกลมแบบสรุปในเซลล์มุมพร้อมแผนที่ที่มีข้อมูลทางภูมิศาสตร์สองชุดที่แสดงด้วยสีและขนาดวงกลม  

![รายงานแบบแบ่งหน้าในบริการของ Power BI](media/report-builder-power-bi/report-builder-get-started-paginated-report.png)

##  <a name="jump-start-report-creation"></a><a name="JumpStartReptCreation"></a> การสร้างรายงานอย่างรวดเร็ว  
 
-   **เริ่มต้นด้วยตาราง, เมทริกซ์หรือตัวช่วยสร้างแผนภูมิ** สร้างการเชื่อมต่อแหล่งข้อมูล ลากฟิลด์และวางลงเพื่อสร้างคิวรีชุดข้อมูล เลือกเค้าโครงและสไตล์ แล้วปรับแต่งรายงานของคุณ  
  
-   **เริ่มด้วยตัวช่วยสร้างแผนที่** คุณสามารถสร้างรายงานที่แสดงข้อมูลรวมกับพื้นหลังทางภูมิศาสตร์หรือเรขาคณิตได้ ข้อมูลแผนที่อาจเป็นข้อมูลเชิงพื้นที่ที่ได้จากคิวรี Transact-SQL หรือจาก Environmental Systems Research Institute, Inc. แฟ้มเชปไฟล์ (ESRI) คุณยังสามารถเพิ่มพื้นหลังไทล์แผนที่ของ Microsoft Bing ได้  

##  <a name="design-your-report"></a><a name="DesignRept"></a> ออกแบบรายงานของคุณ  
  
-   **สร้างรายงานแบบแบ่งหน้าด้วยตาราง เมทริกซ์ แผนภูมิ และเค้าโครงรายงานแบบอิสระ** สร้างรายงานแบบตารางสำหรับข้อมูลจากคอลัมน์ รายงายเมทริกซ์ (เช่น รายงานแบบตารางไขว้หรือ PivotTable) สำหรับข้อมูลสรุป รายงานแผนภูมิสำหรับข้อมูลกราฟิก และรายงานแบบอิสระสำหรับข้อมูลอย่างอื่น รายงานสามารถฝังรายงานและแผนภูมิอื่นๆ พร้อมด้วยรายการ กราฟิก และการควบคุมสำหรับโปรแกรมประยุกต์บนเว็บแบบไดนามิก  
  
-   **รายงานจากแหล่งข้อมูลหลายแหล่ง** คุณสามารถสร้างรายงานที่ใช้ข้อมูลเชิงสัมพันธ์และหลายมิติจาก SQL Server และ Analysis Services, Oracle, ชุดข้อมูล Power BI และฐานข้อมูลอื่นๆ  
  
-   **การปรับแต่งรายงานที่มีอยู่** โดยการใช้ตัวสร้างรายงาน คุณสามารถปรับและอัพเดทรายงานต่าง ๆ ที่สร้างบนเครื่องมือ SQL เซริฟเวอร์ได้ (SSDT)  
  
-   **การแก้ไขข้อมูลของคุณ** ตัวกรอง กลุ่ม และเรียงลำดับข้อมูล หรือเพิ่มสูตรหรือนิพจน์  

-   **เพิ่มแผนภูมิ ตัววัด เส้นแบบประกายไฟ และตัวบ่งชี้** สรุปข้อมูลในรูปแบบภาพ และนำเสนอข้อมูลที่ถูกรวมเป็นปริมาณมากอย่างย่อ  
  
-   **เพิ่มคุณลักษณะแบบโต้ตอบ** เช่น แผนที่เอกสาร แสดง/ซ่อนปุ่ม และลิงก์ลงรายละเอียดไปยังรายงานย่อยและรายงานลงรายละเอียด ใช้พารามิเตอร์และตัวกรองเพื่อกรองข้อมูลสำหรับมุมมองแบบกำหนดเอง  
  
-   **รูปภาพฝังหรือรูปภาพอ้างอิง**และทรัพยากรอื่นๆ รวมทั้งเนื้อหาจากภายนอก  
  
##  <a name="manage-your-report"></a><a name="ManageRpt"></a> จัดการรายงานของคุณ  
  
-   **บันทึกคำอธิบายของรายงาน** ลงบนคอมพิวเตอร์ของคุณ หรือเซิร์ฟเวอร์รายงาน ที่คุณสามารถจัดการได้และแบ่งปันกับผู้อื่น  
  
-   **เลือกรูปแบบการนำเสนอ** เมื่อคุณเปิดรายงาน หรือหลังจากที่คุณเปิดรายงาน คุณสามารถเลือกสำหรับเว็บ สำหรับหน้า และรูปแบบแอปพลิเคชันเดสก์ท็อป รูปแบบรวมถึง MHTML, PDF, XML, CSV, Word และ Excel  
  
-   **การสมัครใช้งาน** หลังจากเผยแพร่รายงานไปยังบริการ Power BI แล้ว คุณจะสามารถกำหนดค่าให้รายงานของคุณเรียกใช้ ณ เวลาใดเวลาหนึ่ง และส่งเป็นอีเมลการสมัครใช้งาน  

## <a name="next-steps"></a>ขั้นตอนถัดไป

- [รายงานแบบแบ่งหน้าใน Power BI Premium คืออะไร](paginated-reports-report-builder-power-bi.md)
- [หลักสูตรที่สอนผ่านวิดีโอ: รายงานที่มีการแบ่งหน้าของ Power BI ในวันเดียว](../learning-catalog/paginated-reports-online-course.md)

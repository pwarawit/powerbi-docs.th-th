---
title: วางแผนรายงานในตัวสร้างรายงานใน Power BI
description: ตัวสร้างรายงานใน Power BI ช่วยให้คุณสร้างรายงานแบบแบ่งหน้าได้หลายรูปแบบ โปรแกรมนี้ช่วยวางแผนในขั้นแรกเพื่อสร้างรายงานที่เป็นประโยชน์และเข้าใจง่าย
ms.date: 06/06/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: 79113505-1ce8-4f8c-9260-d861838f7813
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: fd4a318d7a61f6f2298de6b9d5d23ad2ae063d28
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/12/2019
ms.locfileid: "66840521"
---
# <a name="planning-a-report-in-power-bi-report-builder"></a>วางแผนรายงานในตัวสร้างรายงานใน Power BI
  ตัวสร้างรายงานใน Power BI ช่วยให้คุณสร้างรายงานแบบแบ่งหน้าได้หลายรูปแบบ ตัวอย่างเช่น คุณสามารถสร้างรายงานที่แสดงผลสรุปหรือข้อมูลการขายโดยละเอียด, การตลาดหรือแนวโน้มการขาย, รายงานการปฏิบัติงาน, หรือแดชบอร์ด คุณยังสามารถสร้างรายงานที่ใช้ผลประโยชน์จากเนื้อหาซึ่งจัดรูปแบบสมบูรณ์ได้ เช่น คำสั่งขาย, แคตตาล็อกสินค้า, หรือจดหมายฟอร์ม รายงานทั้งหมดนี้สร้างโดยการใช้การรวมที่หลากหลายของแบบการสร้างพื้นฐานเดียวกันในตัวสร้างรายงาน โปรแกรมนี้ช่วยวางแผนในขั้นแรกเพื่อสร้างรายงานที่เป็นประโยชน์และเข้าใจง่าย ต่อไปนี้เป็นบางสิ่งที่คุณอาจต้องการพิจารณาก่อนเริ่มใช้งาน  
  
## <a name="in-what-format-do-you-want-the-report-to-appear"></a>คุณต้องการให้รายงานปรากฏในรูปแบบใด
  
คุณสามารถแสดงรายงานออนไลน์ในเบราว์เซอร์ เช่น พอร์ทัล Power BI หรือส่งออกไปยังรูปแบบอื่นๆ เช่น Excel, Word, หรือ PDF แบบฟอร์มสุดท้ายที่รายงานของคุณใช้เป็นการพิจารณาที่สำคัญ เนื่องจากไม่ใช่คุณลักษณะทั้งหมดจะพร้อมใช้งานในรูปแบบการส่งออกทั้งหมด 
  
## <a name="in-what-structure-do-you-want-to-present-the-data"></a>คุณต้องการนำเสนอข้อมูลด้วยโครงสร้างใด
  
คุณมีตัวเลือก ได้แก่ ตาราง, เมทริกซ์ (คล้ายกับรายงานแบบตารางไขว้หรือแบบ PivotTable), แผนภูมิ, โครงสร้างไร้รูปแบบ, หรือการรวมใดๆ เพื่อนำเสนอข้อมูล สำหรับข้อมูลเพิ่มเติม ดู[ตาราง เมทริกซ์ และรายการในตัวสร้างรายงานในower BI](report-builder-tables-matrices-lists.md)  
  
## <a name="how-do-you-want-your-report-to-look"></a>คุณต้องการให้รายงานของคุณมีลักษณอย่างไร
  
ตัวสร้างรายงานจัดเตรียมหน่วยข้อมูลของรายงานจำนวนมากที่คุณสามารถเพิ่มไปยังรายงานของคุณเพื่อให้อ่านง่ายขึ้น เน้นข้อมูลสำคัญ ช่วยผู้ชมของคุณหารายงาน และอื่นๆ การทราบว่าคุณต้องการให้รายงานปรากฏออกมาอย่างไรสามารถบ่งชี้ได้ว่าคุณต้องการรายการรายงาน เช่น กล่องข้อความ, สี่เหลี่ยมผืนผ้า, รูปภาพ, และเส้นหรือไม่ คุณอาจต้องการแสดงหรือซ่อนรายการ เพิ่มแผนที่ของเอกสาร รวมถึงรายงานลงรายละเอียดหรือรายงานย่อย หรือเชื่อมโยงกับรายงานอื่นๆ   
  
## <a name="should-the-data-be-filtered"></a>ข้อมูลควรได้รับการกรองหรือไม่
  
คุณอาจต้องการทำให้ขอบเขตของรายงานแคบลงเพื่อเจาะจงผู้ใช้งานหรือสถานที่ หรือช่วงเวลาเฉพาะ หากต้องการกรองข้อมูลรายการ ให้ใช้พารามิเตอร์เพื่อเรียกดูและแสดงเฉพาะข้อมูลที่คุณต้องการ สำหรับข้อมูลเพิ่มเติม ดู[พารามิเตอร์ของรายงานในตัวสร้างรายงานใน Power BI](paginated-reports-parameters.md)  
  
## <a name="do-you-need-to-create-calculations"></a>คุณต้องการสร้างการคำนวณหรือไม่ 
  
     Sometimes, your data source and datasets do not contain the exact fields that you need for your report. In that situation, you might have to create your own calculated fields. For example, you might want to multiply the price per unit times the quantity to get a line item sales amount. Expressions are also used to provide conditional formatting and other advanced features. For more information, see [Expressions in Power BI Report Builder](report-builder-expressions.md).  
  
## <a name="do-you-want-to-hide-report-items-initially"></a>คุณต้องการซ่อนรายการรายงานในขั้นต้นหรือไม่
  
พิจารณาว่าคุณต้องการซ่อนรายการรายงาน รวมถึงขอบเขตข้อมูล กลุ่มและคอลัมน์หรือไม่เมื่อมีการเรียกใช้รายงานครั้งแรก ตัวอย่างเช่น คุณสามารถนำเสนอตารางสรุปในขั้นต้น จากนั้นลงรายละเอียดในข้อมูลรายละเอียด 
  
## <a name="how-are-you-going-to-deliver-your-report"></a>คุณจะส่งรายงานของคุณอย่างไร  
  
     You can save your report to your local computer and continue to work on it, or run it locally for your own information. However, to share your report with others, you need to save the report to Power BI. Saving it to Power BI lets others run it whenever they want to. Alternatively, you can set up a subscription and e-mail delivery of the report to other individuals. You can have the report delivered in a specific export format if you prefer. 
  
## <a name="next-steps"></a>ขั้นตอนถัดไป

- [รายงานแบบแบ่งหน้าใน Power BI Premium คืออะไร](paginated-reports-report-builder-power-bi.md)

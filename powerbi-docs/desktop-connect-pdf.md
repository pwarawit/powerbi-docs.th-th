---
title: เชื่อมต่อกับไฟล์ PDF ใน Power BI Desktop (ดูตัวอย่าง)
description: เชื่อมต่อและใช้ข้อมูลจากไฟล์ PDF ได้อย่างง่ายดายใน Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/13/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: ff61c4d2cc8ec3570e7eee45b7e43ec81f8f7161
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54275122"
---
# <a name="connect-to-a-pdf-file-in-power-bi-desktop-preview"></a>เชื่อมต่อกับไฟล์ PDF ใน Power BI Desktop (ดูตัวอย่าง)
ใน Power BI Desktop คุณสามารถเชื่อมต่อกับ **ไฟล์ PDF** และใช้ข้อมูลที่รวมจากไฟล์เช่นเดียวกับแหล่งข้อมูลอื่น ๆ ใน Power BI Desktop

![เชื่อมต่อกับข้อมูลในไฟล์ PDF](media/desktop-connect-pdf/connect-pdf_04.png)

หัวข้อต่อไปนี้อธิบายถึงวิธีเชื่อมต่อกับ **ไฟล์ PDF** เลือกข้อมูล และนำข้อมูลดังกล่าวไปวางไว้ที่ **Power BI Desktop**

## <a name="enable-the-pdf-connector"></a>เปิดใช้งานตัวเชื่อมต่อ PDF
ตัวเชื่อมต่อ PDF อยู่ในรูปแบบตัวอย่างสำหรับ **Power BI Desktop** และต้องเปิดใช้งาน หากต้องการเปิดใช้งานตัวเชื่อมต่อ PDF ให้เลือก **ไฟล์> ตัวเลือกและการตั้งค่า> ตัวเลือก> ดูตัวอย่างคุณลักษณะ** จากนั้นเลือกช่องทำเครื่องหมายด้านข้าง **รับข้อมูลจากไฟล์ PDF**  

![เปิดใช้งานตัวเชื่อมต่อ PDF จาก ตัวเลือก> ดูตัวอย่างคุณลักษณะ](media/desktop-connect-pdf/connect-pdf_01.png)

คุณจะต้องรีสตาร์ท **Power BI Desktop** หลังจากที่คุณทำการเลือกแล้ว

เมื่อคุณใช้ตัวเชื่อมต่อ **PDF (รุ่นเบต้า)** เป็นครั้งแรก คุณจะได้รับคำเตือนว่าตัวเชื่อมต่อ PDF ยังอยู่ในระหว่างการพัฒนาและอาจมีการเปลี่ยนแปลงในอนาคต เลือก **ดำเนินการต่อ** เพื่อใช้ตัวเชื่อมต่อ

เราแนะนำให้อัปเกรดเป็นเวอร์ชันล่าสุด**Power BI Desktop**เสมอ ซึ่งคุณสามารถรับได้จากลิงก์ใน[รับ Power BI Desktop](desktop-get-the-desktop.md) 

## <a name="connect-to-a-pdf-file"></a>เชื่อมต่อกับไฟล์ PDF
หากต้องการเชื่อมต่อกับไฟล์ **PDF** ให้เลือก **รับข้อมูล** จากริบบิ้น **หน้าแรก** ใน Power BI Desktop เลือก **ไฟล์** จากหมวดหมู่ด้านซ้าย และคุณจะเห็น **PDF (เบต้า)**

![เลือก PDF จาก Get Data(รับข้อมูล)](media/desktop-connect-pdf/connect-pdf_01.png)

คุณได้รับพร้อมท์ให้ระบุตำแหน่งของไฟล์ PDF ที่คุณต้องการใช้ เมื่อคุณระบุตำแหน่งไฟล์และโหลดไฟล์ PDF หน้าต่าง **เนวิเกเตอร์** จะปรากฏขึ้นและแสดงข้อมูลจากไฟล์ ซึ่งคุณสามารถเลือกองค์ประกอบหนึ่งหรือหลายรายการเพื่อนำเข้าและใช้ใน **Power BI Desktop**

![เชื่อมต่อกับข้อมูลในไฟล์ PDF](media/desktop-connect-pdf/connect-pdf_04.png)

การเลือกช่องทำเครื่องหมายถัดจากองค์ประกอบที่ค้นพบในไฟล์ PDF จะแสดงรายการในบานหน้าต่างด้านขวา เมื่อคุณพร้อมที่จะนำเข้าแล้วให้เลือกปุ่ม **Load (โหลด)** เพื่อนำข้อมูลมาไว้ใน **Power BI Desktop**

ตั้งแต่เดือนพฤศจิกายน 2018 ในการเผยแพร่ของ **Power BI Desktop** คุณสามารถระบุ**หน้าเริ่มต้น**และ**หน้าสุดท้าย**เป็นพารามิเตอร์เพิ่มเติมสำหรับการเชื่อมต่อ PDF ของคุณได้ คุณยังสามารถระบุพารามิเตอร์เหล่านี้ในภาษาสูตร M โดยใช้รูปแบบต่อไปนี้:

`Pdf.Tables(File.Contents("c:\sample.pdf"), [StartPage=10, EndPage=11])`


## <a name="next-steps"></a>ขั้นตอนถัดไป
มีข้อมูลหลากหลายประเภทที่คุณสามารถเชื่อมต่อโดยใช้ Power BI Desktop สำหรับข้อมูลเพิ่มเติมเกี่ยวกับแหล่งข้อมูล โปรดดูทรัพยากรต่อไปนี้:

* [Power BI Desktop คืออะไร](desktop-what-is-desktop.md)
* [แหล่งข้อมูลใน Power BI Desktop](desktop-data-sources.md)
* [จัดรูปทรงและรวมข้อมูลด้วย Power BI Desktop](desktop-shape-and-combine-data.md)
* [เชื่อมต่อกับเวิร์กบุ๊ก Excel ใน Power BI Desktop](desktop-connect-excel.md)   
* [ป้อนข้อมูลลงใน Power BI Desktop โดยตรง](desktop-enter-data-directly-into-desktop.md)   


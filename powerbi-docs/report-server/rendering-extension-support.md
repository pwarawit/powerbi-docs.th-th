---
title: ความสอดคล้องของส่วนขยายการแสดงผล PDF กับ ISO 14289-1 - Power BI Report Server
description: เอกสารนี้อธิบายเกี่ยวกับความสอดคล้องของส่วนขยายการแสดงผล PDF ใน Power BI Report Server และ SQL Reporting Services กับข้อกำหนด ISO 14289-1 (PDF/UA)
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 11/04/2019
ms.author: maggies
ms.openlocfilehash: c800ee995bc3c03b3cbcda91503e6dea9495f6b5
ms.sourcegitcommit: 721cf375627b010e8ad12c4c668295f38d450a17
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/06/2019
ms.locfileid: "73638091"
---
# <a name="pdf-rendering-extension-conformance-to-iso-14289-1---power-bi-report-server"></a>ความสอดคล้องของส่วนขยายการแสดงผล PDF กับ ISO 14289-1 - Power BI Report Server 

นำไปใช้กับ: Power BI Report Server และ SQL Reporting Services

เอกสารนี้อธิบายเกี่ยวกับความสอดคล้องของส่วนขยายการแสดงผล PDF ใน Power BI Report Server และ SQL Reporting Services กับข้อกำหนด [ISO 14289-1 (PDF/UA)](https://www.pdfa.org/publication/pdfua-in-a-nutshell/)

> [!NOTE]
> คุณสามารถบันทึกหรือพิมพ์เอกสารทางเทคนิคนี้ได้โดยเลือก **พิมพ์** จากเบราว์เซอร์ของคุณ แล้วเลือก**บันทึกเป็น PDF**

## <a name="1--scope"></a>1.  ขอบเขต

ไม่สามารถใช้งานได้

## <a name="2--normative-references"></a>2.  มาตรฐานอ้างอิง

ไม่สามารถใช้งานได้

## <a name="3--terms-and-definitions"></a>3.  คำศัพท์และคำจำกัดความ

ไม่สามารถใช้งานได้

## <a name="4--notation"></a>4.  เครื่องหมายที่ใช้แทน

ไม่สามารถใช้งานได้

## <a name="5-version-identification"></a>5. การระบุเวอร์ชัน

ส่วนขยายการแสดงผล PDF ให้การสนับสนุน PDF/UA ตามที่อธิบายไว้ในเอกสารนี้ ในบางกรณีตามที่ระบุไว้ด้านล่าง ผู้ใช้ต้องปฏิบัติตามขั้นตอนเพื่อให้แน่ใจว่า PDF นั้นสอดคล้องกับมาตรฐาน PDF/UA อย่างสมบูรณ์  เราคาดหวังว่าผู้ใช้จะเพิ่มเวอร์ชัน PDF/UA ที่เหมาะสมและตัวระบุความสอดคล้องเป็นขั้นตอนสุดท้ายในกระบวนการนี้ ซึ่งแสดงให้เห็นว่ามีการดำเนินงานที่จำเป็นแล้วเพื่อทำให้ PDF สอดคล้องกับ PDF/UA ทั้งหมด

ทุกอย่างที่แสดงในเอกสารนี้ขึ้นอยู่กับการแสดงผลเอกสาร PDF ด้วยการตั้งค่าข้อมูลอุปกรณ์ AccessiblePdf ให้เป็น `true` ในบางกรณี ข้อจำกัดด้านการปฏิบัติตามข้อกำหนดนั้นเกิดจากขีดจำกัดใน Report Definition Language (RDL)

## <a name="6--conformance-requirements"></a>6.  ข้อกำหนดความสอดคล้อง

|     เกณฑ์     |     การสนับสนุนคุณลักษณะ     |     หมายเหตุ      |
|----|--------|--------|
|    6.1 ทั่วไป    |                 สนับสนุน    |    ส่วนขยายการแสดงผล PDF สร้าง PDF เวอร์ชัน 1.7    |
|    6.2 ไฟล์ที่สอดคล้อง    |                 ได้รับการสนับสนุน แต่มีข้อยกเว้น    |    ดูหมายเหตุในส่วนที่ 7 – ข้อกำหนดรูปแบบไฟล์    |
|    6.3 โปรแกรมอ่านที่สอดคล้อง    |     ไม่สามารถใช้งานได้     |         |
|    6.4 เทคโนโลยีการช่วยเหลือที่สอดคล้อง    |     ไม่สามารถใช้งานได้     |         |

## <a name="7--file-format-requirements"></a>7.  ข้อกำหนดรูปแบบไฟล์

|     เกณฑ์     |     การสนับสนุนคุณลักษณะ     |     หมายเหตุ      |
|-----|-------|------------------------|
|    7.1 ทั่วไป    |                 ได้รับการสนับสนุน แต่มีข้อยกเว้น    |    เนื้อหาจริงทั้งหมดจะถูกแท็กตามที่กำหนดไว้ใน ISO 32000-1:2008, 14.8 อาร์ทิแฟกต์ (ISO 32000-1:2008, 14.8.2.2.2) จะไม่ถูกแท็กในแผนผังโครงสร้าง <li> ส่วนขยายการแสดงผล PDF ไม่ได้ให้ความยืดหยุ่นในการทำเครื่องหมายรายการแต่ละรายการเป็นอาร์ทิแฟกต์อย่างชัดเจน ดังนั้นจึงทำการแทนที่อาร์ทิแฟกต์ด้วยอะไรก็ตามที่แมปกับเกณฑ์ใน ISO 32000-1:2008, 14.8.2.2.2<br>เนื้อหาจะต้องถูกทำเครื่องหมายในแผนผังโครงสร้างด้วยแท็กที่เหมาะสมในเชิงความหมายในลำดับการอ่านเชิงตรรกะ <br> **หมายเหตุ** 4   WCAG 2.0, Guideline 1.4 อธิบายปัญหาเกี่ยวกับความคมชัด สี และการจัดรูปแบบอื่น ๆ สำหรับการเข้าถึง <br><li> ผู้ใช้จะต้องตรวจสอบให้แน่ใจว่าเอกสารของพวกเขาไม่อยู่ภายใต้ปัญหาเหล่านี้ <br>แท็กมาตรฐานที่กำหนดใน ISO 32000-1:2008, 14.8.4 จะต้องไม่ถูกแมปใหม่ <li> ส่วนขยายการแสดงผล PDF ไม่ทำการแมปแท็กมาตรฐานใหม่ เอกสารเริ่มต้นด้วยองค์ประกอบรูทเอกสาร <br>ไฟล์ที่อ้างว่าสอดคล้องกับมาตรฐานสากลนี้จะต้องมีค่าที่ต้องสงสัยเป็นเท็จ (ISO   32000-1:2008, ตารางที่ 321) <li> ส่วนขยายการแสดงผล PDF ไม่มีรายการที่ต้องสงสัย คุณสมบัตินี้เป็นแบบทางเลือก    |
|    7.2 ข้อความ    |                 ได้รับการสนับสนุน แต่มีข้อยกเว้น    |    เนื้อหาจะถูกแท็กในลำดับการอ่านเชิงตรรกะ แท็กที่เหมาะสมในเชิงความหมายมากที่สุดจะต้องถูกใช้สำหรับแต่ละองค์ประกอบเชิงตรรกะในเนื้อหาของเอกสาร <br><li> ส่วนขยายการแสดงผล PDF ติดแท็กเนื้อหาในลำดับการอ่านแบบลอจิคัลเท่าที่จะทำได้<br>รหัสอักขระจะแมปกับ Unicode ตามที่อธิบายไว้ใน ISO 32000-1: 2008, 14.8.2.4.2 อักขระที่ไม่รวมอยู่ในข้อกำหนด Unicode อาจใช้พื้นที่ใช้งานส่วนตัวของ Unicode หรือประกาศการเข้ารหัสอักขระอื่น <br>ภาษาธรรมชาติจะต้องประกาศตามที่กล่าวไว้ใน ISO 32000-1:2008, 14.9.2 และ/หรือตามที่อธิบายไว้ใน ISO   32000-1:2008, 7.9.2 ต้องประกาศการเปลี่ยนแปลงในภาษาธรรมชาติ การเปลี่ยนแปลงในภาษาธรรมชาติภายในสตริงข้อความ (เช่น ภายในคำอธิบายสำรอง) จะถูกประกาศโดยใช้ตัวระบุภาษาตามที่อธิบายไว้ใน ISO 32000-1:2008,   14.9.2.2 <br><li> ส่วนขยายการแสดงผล PDF ประกาศภาษาธรรมชาติในระดับเอกสารเท่านั้น    |
|    7.3 กราฟิก    |                 ได้รับการสนับสนุน แต่มีข้อยกเว้น    |    ออบเจ็กต์กราฟิก นอกเหนือจากออบเจ็กต์ข้อความจะถูกแท็กด้วยแท็กรูปภาพ ตามที่อธิบายไว้ใน ISO 32000-1:2008, 14.8.4.5 ตารางที่ 340 หากข้อยกเว้นใดก็ตามต่อไปนี้เป็นจริง กราฟิกจะต้องถูกแท็กเป็นอาร์ทิแฟกต์: <br><li> กราฟิกไม่ได้แสดงเนื้อหาที่มีความหมาย หรือ <li>  กราฟิกจะปรากฏเป็นพื้นหลังของคำอธิบายประกอบลิงก์ ซึ่งในกรณีนี้ข้อความทางเลือกในลิงก์จะต้องอธิบายทั้งกราฟิกและลิงก์ <li> ส่วนขยายการแสดงผล PDF ติดแท็กออบเจ็กต์ของกราฟิกด้วยแท็กรูปภาพ <br>คำอธิบายที่มาพร้อมกับรูปภาพจะถูกแท็กด้วยแท็กคำอธิบาย <li> ในขณะนี้ ส่วนขยายการแสดงผล PDF ไม่ได้ติดแท็กคำอธิบายที่มีแท็กคำอธิบาย <br>แท็กรูปจะต้องประกอบด้วยตัวแทนทางเลือกหรือข้อความทดแทนที่ทำเครื่องหมายด้วยแท็กรูปตามที่ระบุไว้ใน ISO 32000-1: 2008, 14.7.2, ตารางที่ 323 <br>**หมายเหตุ** 1 โปรดดู WCAG 2.0, Guideline 1.1 <br>หากข้อความที่แสดงในกราฟิกไม่ใช่ข้อความในภาษาธรรมชาติที่มนุษย์เป็นคนอ่าน ให้ใช้ข้อความทางเลือกที่อธิบายลักษณะหรือวัตถุประสงค์ของกราฟิก <br>**หมายเหตุ** 2 ข้อความที่เป็นประเภทตัวอย่างหรือตัวอย่างของระบบการเขียนที่ใช้โดยภาษาเป็นตัวอย่างของข้อความที่ไม่ได้อยู่ในภาษาธรรมชาติ   ส่วนขยายการแสดงผล PDF สนับสนุนข้อความแสดงแทนบนรูปภาพ ถึงแม้ว่าจะขึ้นอยู่กับผู้ใช้ที่จะเพิ่มข้อความแสดงแทนก็ตาม <br>หมายเหตุเพิ่มเติมเกี่ยวกับแอตทริบิวต์ BBox: <br><li> ในขณะนี้ ส่วนขยายการแสดงผล PDF ไม่ได้เขียนแอตทริบิวต์ BBox <li> การแก้ไขปัญหาชั่วคราวคือ การติดแท็กรูปประกอบซ้ำด้วยตนเองให้เป็นรูปใหม่หรือเป็นอาร์ทิแฟกต์    |
|    7.4 หัวเรื่อง    |                 ไม่สามารถใช้งานได้    |    RDL ไม่สนับสนุนการทำเครื่องหมายหัวเรื่องด้วยวิธีใดก็ตาม ซึ่งขึ้นอยู่กับผู้ใช้ที่จะแท็กหัวเรื่องดังกล่าวตามความเหมาะสม    |
|    7.5 ตาราง    |                 ได้รับการสนับสนุน แต่มีข้อยกเว้น    |    ตารางควรประกอบด้วยส่วนหัว ส่วนหัวของตารางจะถูกติดแท็กตาม ISO 32000-1:2008, ตารางที่ 337 และตารางที่ 349 <br>**หมายเหตุ** 1 ตารางสามารถมีส่วนหัวของคอลัมน์ ส่วนหัวของแถว หรือทั้งสองอย่าง <br>**หมายเหตุ** 2 ต้องมีข้อมูลเกี่ยวกับโครงสร้างของตารางให้พร้อมใช้งานมากที่สุดเท่าที่เป็นไปได้เมื่อมีการใช้งานเทคโนโลยีช่วยเหลือ ส่วนหัวมีบทบาทสำคัญในการให้ข้อมูลโครงสร้าง <br><li> ซึ่งขึ้นอยู่กับผู้ใช้ที่จะรวมส่วนหัวในตารางของพวกเขา RDL และส่วนขยายการแสดงผล PDF ให้การสนับสนุนส่วนหัวของแถว <br>  องค์ประกอบโครงสร้างของประเภท TH จะต้องมีแอตทริบิวต์ขอบเขต   <li> ส่วนขยายการแสดงผล PDF ประกอบรวมด้วยแอตทริบิวต์ขอบเขต (Scope) บนองค์ประกอบ TH สำหรับสมาชิกคอลัมน์และแถว แต่ไม่รวมถึงเซลล์ตรงมุม<br>โครงสร้างการติดแท็กตารางจะใช้เพื่อติดแท็กเนื้อหาที่แสดงภายในความสัมพันธ์ของแถวและ/หรือความสัมพันธ์ของคอลัมน์เชิงตรรกะเท่านั้น   <li> การดำเนินการนี้จะขึ้นอยู่กับวิธีการที่ผู้ใช้เลือกใช้ตารางใน RDL ของพวกเขา    |
|    7.6 รายการ    |                 ไม่สามารถใช้งานได้    |    RDL ไม่สนับสนุนการทำเครื่องหมายรายการ ใน RDL จะมีการจัดโครงสร้างตารางด้วยเซลล์ตารางเดียว <br>ซึ่งขึ้นอยู่กับผู้ใช้ที่จะแท็กหัวเรื่องดังกล่าวตามความเหมาะสมอีกครั้ง    |
|    7.7 นิพจน์ทางคณิตศาสตร์    |                 ได้รับการสนับสนุน แต่มีข้อยกเว้น    |    นิพจน์ทางคณิตศาสตร์ทั้งหมดจะต้องอยู่ภายในแท็กสูตรตามรายละเอียดใน ISO 32000-1:2008, 14.8.4.5 และต้องมีแอตทริบิวต์ทางเลือก <br><li> ในขณะนี้ ส่วนขยายการแสดงผล PDF ไม่ได้รวมนิพจน์ทางคณิตศาสตร์ไว้ภายในแท็กสูตร <br>ข้อกำหนดที่เกี่ยวข้องกับการแมปอักขระกับ Unicode จะต้องนำนิพจน์ทางคณิตศาสตร์ไปใช้ตามที่กำหนดไว้ใน ISO   32000-1:2008, 9.10.2 และ 14.8.2.4 <br><li> ซึ่งสิ่งนี้ได้รับการสนับสนุนจากส่วนขยายการแสดงผล PDF    |
|    7.8 ส่วนหัวและส่วนท้ายของหน้า    |                 สนับสนุน    |    ส่วนหัวและส่วนท้ายที่ทำงานอยู่จะต้องถูกระบุว่าเป็นอาร์ทิแฟกต์การแบ่งหน้าและจัดเป็นประเภทย่อยส่วนหัวหรือท้ายกระดาษตามมาตรฐาน ISO   32000-1:2008, 14.8.2.2.2, ตารางที่ 330 <br><li> ส่วนหัวและส่วนท้ายของหน้าได้รับการปฏิบัติและติดแท็กเหมือนกับอาร์ทิแฟกต์    |
|    7.9 บันทึกย่อและการอ้างอิง    |                 ไม่สามารถใช้งานได้    |    ส่วนขยายการแสดงผล PDF ไม่สนับสนุนการทำเครื่องหมายบันทึกย่อและการอ้างอิง <br>ซึ่งขึ้นอยู่กับผู้ใช้ที่จะแท็กบันทึกย่อและการอ้างอิงดังกล่าวตามความเหมาะสม    |
|    7.10 เนื้อหาทางเลือก    |                 ไม่สามารถใช้งานได้    |         |
|    7.11 ไฟล์แบบฝัง    |                 ไม่สามารถใช้งานได้    |         |
|    7.12 เธรดบทความ    |                 ไม่สามารถใช้งานได้    |         |
|    7.13 ลายเซ็นดิจิทัล    |                 ไม่สามารถใช้งานได้    |         |
|    7.14 แบบฟอร์มที่ไม่มีการโต้ตอบ    |                 ไม่สามารถใช้งานได้    |         |
|    7.15 XFA    |                 ไม่สามารถใช้งานได้    |         |
|    7.16 ความปลอดภัย    |                 ไม่สามารถใช้งานได้    |         |
|    7.17 การนำทาง    |                 สนับสนุน    |    เอกสารควรประกอบด้วยเค้าร่างเอกสารที่ตรงกับลำดับการอ่านและระดับของเป้าหมายการนำทาง (ISO 32000-1:2008, 12.3.3) <br><li> RDL สนับสนุนบุ๊กมาร์กสำหรับรายการรายงาน แต่ผู้ใช้ต้องเลือกตัวเลือกนี้ จากนั้น บุ๊กมาร์กเหล่านั้นจะแสดงเป็นโครงร่างเอกสารโดยส่วนขยายการแสดงผล PDF <br>ถ้ามีอยู่ รายการในแผนผังหมายเลข PageLabels (ISO 32000-1:2008, 7.7.2,   ตารางที่ 28) ควรมีความเหมาะสมทางความหมาย <br><li> ส่วนขยายการแสดงผล PDF ไม่ประกอบด้วยแผนผังหมายเลข PageLabels    |
|    7.18 คำอธิบายประกอบ    |                 ไม่สามารถใช้งานได้    |    RDL ไม่สนับสนุนคำอธิบายประกอบ    |
|    7.21 ฟอนต์    |                 สนับสนุน    |         |
|    7.21.1 ทั่วไป    |                 สนับสนุน    |         |
|    7.21.2 ชนิดของฟอนต์    |                 สนับสนุน    |         |
|    7.21.3 ฟอนต์แบบรวม    |                 สนับสนุน    |         |
|    7.21.3.1 ทั่วไป    |                 สนับสนุน    |         |
|    7.21 3.2 CIDFonts    |                 สนับสนุน    |         |
|    7.21.3.3 CMaps    |                 สนับสนุน    |         |
|    7.21.4 การฝัง    |                 สนับสนุน    |         |
|    7.21.4.1 ทั่วไป    |                 สนับสนุน    |         |
|    7.21.4.2 การฝังชุดย่อย    |                 สนับสนุน    |         |
|    7.21.5 เมตริกของฟอนต์    |                 สนับสนุน    |         |
|    7.21.6 การเข้ารหัสอักขระ    |                 สนับสนุน    |         |
|    7.21.7 การแมปอักขระ Unicode    |                 สนับสนุน    |         |
|    7.21.8 การใช้ .notdef glyph    |                 สนับสนุน    |         |

## <a name="8--conforming-reader-requirements"></a>8.  ข้อกำหนดของโปรแกรมอ่านที่สอดคล้อง

ไม่สามารถใช้งานได้

## <a name="9--at-requirements"></a>9.  ข้อกำหนด AT

ไม่สามารถใช้งานได้

## <a name="disclaimer"></a>Disclaimer

© 2017 Microsoft Corporation. All rights reserved. The names of actual companies and products mentioned herein may be the trademarks of their respective owners. The information contained in this document represents the current view of Microsoft Corporation on the issues discussed as of the date of publication. Microsoft cannot guarantee the accuracy of any information presented after the date of publication. Microsoft regularly updates its websites with new information about the accessibility of products as that information becomes available.

Customization of the product voids this conformance statement from Microsoft. Please consult with Assistive Technology (AT) vendors for compatibility specifications of specific AT products.

This document is for informational purposes only. MICROSOFT MAKES NO WARRANTIES, EXPRESS OR IMPLIED, IN THIS DOCUMENT.


## <a name="next-steps"></a>ขั้นตอนถัดไป
[ภาพรวมของผู้ดูแลระบบ](admin-handbook-overview.md)  

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](https://community.powerbi.com/)

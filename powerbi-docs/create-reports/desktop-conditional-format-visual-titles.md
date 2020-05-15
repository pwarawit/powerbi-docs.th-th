---
title: ชื่อเรื่องตามนิพจน์ใน Power BI Desktop
description: สร้างชื่อเรื่องแบบไดนามิกใน Power BI Desktop ที่เปลี่ยนแปลงตามนิพจน์ทางการเขียนโปรแกรมโดยใช้การจัดรูปแบบทางโปรแกรมแบบมีเงื่อนไข
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: reference
ms.date: 04/10/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: f3c1f047e3be7520005458294381877d1198ee21
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83298400"
---
# <a name="expression-based-titles-in-power-bi-desktop"></a>ชื่อเรื่องตามนิพจน์ใน Power BI Desktop

คุณสามารถสร้างชื่อเรื่องแบบไดนามิกที่กำหนดเองสำหรับวิชวลของ Power BI ของคุณได้ ด้วยการสร้างนิพจน์การวิเคราะห์ข้อมูล (DAX) ที่ขึ้นอยู่กับเขตข้อมูล ตัวแปร หรือองค์ประกอบทางการเขียนโปรแกรมอื่นๆ ซึ่งชื่อเรื่องของวิชวลจะถูกปรับเปลี่ยนโดยอัตโนมัติตามความต้องการ การเปลี่ยนแปลงเหล่านี้จะขึ้นอยู่กับตัวกรอง การเลือก หรือการโต้ตอบและการกำหนดค่าของผู้ใช้อื่นๆ

![ภาพหน้าจอของตัวเลือกการจัดรูปแบบตามเงื่อนไขของ Power BI Desktop](media/desktop-conditional-formatting-visual-titles/expression-based-title-01.png)

สร้างชื่อเรื่องแบบไดนามิก บางครั้งเรียกว่า*ชื่อเรื่องตามนิพจน์* จะตรงไปตรงมา 

## <a name="create-a-field-for-your-title"></a>สร้างเขตข้อมูลสำหรับชื่อเรื่องของคุณ

ขั้นตอนแรกในการสร้างชื่อเรื่องตามนิพจน์คือการสร้างเขตข้อมูลในแบบจำลองของคุณเพื่อใช้สำหรับชื่อเรื่อง 

มีวิธีที่สร้างสรรค์มากมายที่จะทำให้ชื่อวิชวลของคุณสะท้อนถึงสิ่งที่คุณต้องการให้พูดหรือสิ่งที่คุณต้องการแสดง มาลองดูตัวอย่างซักสองตัวอย่างกันเถอะ

คุณสามารถสร้างนิพจน์ที่เปลี่ยนแปลงตามบริบทตัวกรองที่วิชวลได้รับสำหรับชื่อแบรนด์ของผลิตภัณฑ์ได้ รูปภาพต่อไปนี้แสดงสูตร DAX สำหรับเขตข้อมูลดังกล่าว

![ภาพหน้าจอของสูตร DAX](media/desktop-conditional-formatting-visual-titles/expression-based-title-02.png)

อีกตัวอย่างหนึ่งคือการใช้ชื่อเรื่องแบบไดนามิกที่เปลี่ยนแปลงตามภาษาหรือวัฒนธรรมของผู้ใช้ คุณสามารถสร้างชื่อเรื่องเฉพาะภาษาในหน่วยวัด DAX โดยใช้ฟังก์ชัน `USERCULTURE()` ฟังก์ชันนี้ส่งกลับรหัสวัฒนธรรมสำหรับผู้ใช้โดยยึดตามระบบปฏิบัติการหรือการตั้งค่าเบราว์เซอร์ของผู้ใช้ คุณสามารถใช้คำสั่ง DAX switch ดังต่อไปนี้เพื่อเลือกค่าที่ผ่านการแปลอย่างถูกต้องได้ 

```
SWITCH (
  USERCULTURE(),
  "de-DE", “Umsatz nach Produkt”,
  "fr-FR", “Ventes par produit”,
  “Sales by product”
)
```

หรือคุณสามารถเรียกใช้สตริงของตาราง Lookup ที่ประกอบด้วยการแปลทั้งหมดได้ คุณวางตารางนั้นในแบบจำลองของคุณ 

นี่เป็นเพียงตัวอย่างสองแบบที่คุณสามารถใช้เพื่อสร้างชื่อเรื่องตามนิพจน์แบบไดนามิกสำหรับวิชวลของคุณใน Power BI Desktop ได้ สิ่งที่คุณสามารถทำได้กับชื่อของคุณนั้นถูกจำกัดด้วยจินตนาการและแบบจำลองของคุณเท่านั้น


## <a name="select-your-field-for-your-title"></a>เลือกเขตข้อมูลสำหรับชื่อเรื่องของคุณ

หลังจากที่คุณได้สร้างนิพจน์ DAX สำหรับเขตข้อมูลที่คุณสร้างในแบบจำลองของคุณแล้ว คุณจำเป็นต้องนำไปใช้กับชื่อของวิชวลของคุณ

หากต้องการเลือกเขตข้อมูลและนำไปใช้ ให้ไปที่บานหน้าต่าง **การแสดงผลด้วยภาพข้อมูล** ในพื้นที่ **รูปแบบ** ให้เลือก **ชื่อ** เพื่อแสดงตัวเลือกชื่อเรื่องสำหรับวิชวล 

เมื่อคุณคลิกขวาที่ **ข้อความหัวเรื่อง** เมนูบริบทจะปรากฏขึ้นเพื่อให้คุณเลือก **<em>fx</em>การจัดรูปแบบตามเงื่อนไข** เมื่อคุณเลือกรายการเมนูนั้น กล่องโต้ตอบ**ข้อความชื่อเรื่อง**จะปรากฏขึ้น 

![ภาพหน้าจอของกล่องโต้ตอบข้อความชื่อเรื่อง](media/desktop-conditional-formatting-visual-titles/expression-based-title-02b.png)

จากหน้าต่างนั้น คุณสามารถเลือกเขตข้อมูลที่คุณสร้างขึ้นเพื่อใช้สำหรับชื่อเรื่องของคุณได้

## <a name="limitations-and-considerations"></a>ข้อจำกัดและข้อควรพิจารณา

มีข้อจำกัดบางอย่างสำหรับการนำชื่อเรื่องตามนิพจน์สำหรับวิชวลไปใช้งานในปัจจุบัน:

* ในปัจจุบันการจัดรูปแบบตามนิพจน์ไม่รองรับวิชวลบน Python, วิชวลบน R หรือวิชวลของผู้มีอิทธิพลที่สำคัญ
* เขตข้อมูลที่คุณสร้างขึ้นสำหรับชื่อเรื่องต้องเป็นชนิดข้อมูลสตริง หน่วยวัดที่ส่งกลับตัวเลขหรือวันที่/เวลา (หรือชนิดข้อมูลอื่นๆ) ไม่ได้รับการสนับสนุนในขณะนี้
* ชื่อเรื่องตามนิพจน์จะไม่ถูกนำมาใช้เมื่อคุณปักหมุดวิชวลไปยังแดชบอร์ด

## <a name="next-steps"></a>ขั้นตอนถัดไป

บทความนี้อธิบายวิธีการสร้างนิพจน์ DAX ที่เปลี่ยนชื่อเรื่องของวิชวลของคุณลงในเขตข้อมูลแบบไดนามิก ซึ่งสามารถเปลี่ยนแปลงได้เมื่อผู้ใช้โต้ตอบกับรายงานของคุณ คุณอาจพบว่าบทความต่อไปนี้มีประโยชน์เช่นกัน

* [การจัดรูปแบบตามเงื่อนไขในตาราง](desktop-conditional-table-formatting.md)
* [ใช้ตัวเจาะเข้าถึงรายละเอียดข้ามรายงานใน Power BI Desktop](desktop-cross-report-drill-through.md)
* [ใช้ตัวเจาะเข้าถึงรายละเอียดใน Power BI Desktop](desktop-drillthrough.md)
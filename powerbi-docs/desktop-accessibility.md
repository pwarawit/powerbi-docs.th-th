---
title: การช่วยสำหรับการเข้าถึง ในรายงาน Power BI Desktop
description: คุณลักษณะและคำแนะนำสำหรับการสร้างรายงาน Power BI Desktop ที่สามารถเข้าถึงได้
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
ms.date: 11/21/2017
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: c0e11a46e6e228da2f2ca8ac3f7be63ae20c1d92
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
---
# <a name="accessibility-in-power-bi-desktop-reports"></a>การช่วยสำหรับการเข้าถึง ในรายงาน Power BI Desktop
**Power BI Desktop** มีคุณลักษณะที่ช่วยให้ผู้ทุพพลภาพสามารถใช้ และโต้ตอบกับรายงาน **Power BI Desktop** ได้อย่างง่ายขึ้น คุณลักษณะเหล่านี้รวมถึง ความสามารถในการใช้รายงานโดยใช้แป้นพิมพ์ หรือใช้โปรแกรมอ่านหน้าจอ แตะเพื่อโฟกัสบนวัตถุต่าง ๆ บนหน้า และใช้เครื่องหมายในการแสดงภาพที่ได้คิดถี่ถ่วนแล้ว

![ใช้เครื่องหมายที่แตกต่างกันในแผนภูมิเส้น และแผนภูมิพื้นที่เพื่อช่วยการเข้าถึง](media/desktop-accessibility/accessibility_01.png)

> [!NOTE]
> คุณลักษณะการช่วยสำหรับการเข้าถึงเหล่านี้ มีตั้งแต่ **Power BI Desktop** รุ่นเดือนมิถุนายน 2017 และที่ใหม่กว่า การช่วยสำหรับการเข้าถึง มีแผนเพิ่มขีดความสามารถขึ้นอีก ในการเผยแพร่ในอนาคต
> 
> 

## <a name="consuming-a-power-bi-desktop-report-with-a-keyboard-or-screen-reader"></a>การใช้รายงาน Power BI Desktop ด้วยแป้นพิมพ์ หรือโปรแกรมอ่านหน้าจอ
เริ่มตั้งแต่การเผยแพร่เดือนกันยายน 2017 ของ **Power BI Desktop** คุณสามารถกดปุ่ม **?** เพื่อแสดงหน้าต่างที่อธิบายเกี่ยวกับ แป้นพิมพ์ลัด การช่วยสำหรับการเข้าถึงใน **Power BI Desktop**

![กดปุ่ม ? ใน Power BI Desktop เพื่อแสดง แป้นพิมพ์ลัด การช่วยสำหรับการเข้าถึง](media/desktop-accessibility/accessibility_03.png)

ด้วยการปรับปรุงการช่วยสำหรับการเข้าถึง คุณสามารถใช้รายงานใน **Power BI Desktop** โดยใช้แป้นพิมพ์หรือโปรแกรมอ่านหน้าจอ ด้วยเทคนิคต่าง ๆ ต่อไปนี้:

คุณสามารถ**สลับโฟกัส**ระหว่างแท็บหน้ารายงาน หรือวัตถุบนหน้ารายงาน โดยใช้ **Ctrl+F6** ได้

* เมื่อโฟกัสอยู่บน*แท็บหน้ารายงาน* ใช้แป้น*แท็บ*หรือ*ลูกศร* เพื่อย้ายโฟกัสจากรายงานหน้าหนึ่งไปอีกหน้าหนึ่ง ชื่อของหน้ารายงาน และสถานะการเลือกในปัจจุบัน จะถูกอ่านออกเสียง ด้วยโปรแกรมอ่านหน้าจอ เพื่อโหลดหน้ารายงานที่กำลังโฟกัสในขณะนี้ ใช้แป้น *Enter*หรือ*ช่องว่าง*
* เมื่อโฟกัสอยู่บน*หน้ารายงาน*ที่โหลด ใช้แป้น*แท็บ*เพื่อเลื่อนโฟกัสไปยังแต่ละวัตถุบนหน้า ซึ่งรวมถึงกล่องข้อความ รูปภาพ รูปร่าง และแผนภูมิทั้งหมด โปรแกรมอ่านหน้าจอ อ่านชนิดของวัตถุและคำอธิบายของวัตถุ ที่ให้โดยผู้สร้าง 

คุณสามารถกด **Alt + Shift + F10** เพื่อย้ายโฟกัสไปยังเมนูวิชวลได้

คุณสามารถกด **Alt + Shift + F11** เพื่อนำเสนอหน้าต่าง*ดูข้อมูล* ในแบบที่เข้าถึงได้

![กด Alt + Shift + F11 ใน Power BI Desktop เพื่อแสดงหน้าต่างดูข้อมูลที่สามารถเข้าถึงได้ สำหรับวิชวล](media/desktop-accessibility/accessibility_04.png)

การช่วยสำหรับการเข้าถึง ที่เพิ่มเติมเข้ามา ช่วยให้ให้ผู้ใช้สามารถใช้รายงาน **Power BI Desktop** ด้วยโปรแกรมอ่านหน้าจอและนำทางโดยแป้นพิมพ์ได้

## <a name="tips-for-creating-accessible-reports"></a>เคล็ดลับการสร้างรายงานที่สามารถเข้าถึงได้
เคล็ดลับต่อไปนี้สามารถช่วยให้คุณสร้างรายงาน **Power BI Desktop** ที่สามารถเข้าถึงได้มากขึ้น

* สำหรับแผนภูมิ**เส้น**, **แผนภูมิพื้นที่**และ**แผนภูมิผสม** เช่นเดียวกับ**แผนภูมิกระจาย**และ**แผนภูมิฟอง** เปิดใช้การทำเครื่องหมาย และใช้*รูปร่างเครื่องหมาย*ที่แตกต่างกันสำหรับแต่ละเส้น
  
  * เพื่อเปิดการ*ทำเครื่องหมาย* เลือกส่วน**รูปแบบ**ในบานหน้าต่าง**การจัดรูปแบบการแสดงข้อมูล** ขยายส่วน**รูปร่าง** จากนั้นเลื่อนลงไป ค้นหา **ทำเครื่องหมาย** และสลับให้เป็น*เปิด*
  * จากนั้น เลือกชื่อของแต่ละเส้น (หรือ พื้นที่ ถ้าใช้แผนภูมิ**พื้นที่**) จากกล่องรายการดรอปดาวน์ในส่วน**รูปร่าง** ด้านล่างเมนูดรอปดาวน์ คุณสามารถปรับเปลี่ยนลักษณะต่าง ๆ ของเครื่องหมายที่ใช้สำหรับเส้นที่เลือก รวมไปถึงรูปร่าง สี และขนาด
  
  ![ใช้เครื่องหมายที่แตกต่างกันในแผนภูมิเส้น และแผนภูมิพื้นที่เพื่อช่วยการเข้าถึง](media/desktop-accessibility/accessibility_01.png)
  
  * ใช้*รูปร่างเครื่องหมาย*ที่แตกต่างกันสำหรับแต่ละเส้น ทำให้ง่ายสำหรับผู้บริโภครายงาน เพื่อแยกแยะเส้น (หรือพื้นที่) ออกจากกัน
* เพิ่มเติมจากหัวข้อที่แล้ว อย่าใช้สีเพื่อสื่อข้อมูล การใช้รูปร่างบนเส้น (หรือเครื่องหมาย ตามที่อธิบายไว้ในหัวข้อที่แล้ว) เป็นสิ่งมีประโยชน์
* เลือก*ธีม* ที่มีความคมชัด และเป็นมิตรกับคนตาบอดสี จากแกลเลอรีธีม และนำเข้าโดยใช้ [คุณลักษณะตัวอย่าง**การกำหนดธีม**](desktop-report-themes.md)
* สำหรับทุก ๆ วัตถุบนรายงาน ใส่*ข้อความแสดงแทน* การทำอย่างนั้นช่วยให้ ผู้บริโภครายงานของคุณความเข้าใจสิ่งที่คุณพยายามสื่อสารด้วยวิชวล แม้ว่าพวกเขาไม่สามารถมองเห็นวิชวล รูปภาพ รูปร่าง หรือกล่องข้อความ คุณสามารถใส่*ข้อความแสดงแทน* สำหรับวัตถุใด ๆ บนรายงาน **Power BI Desktop** โดยการเลือกวัตถุ (เช่นวิชวล รูปร่าง และอื่น ๆ) และในบานหน้าต่าง**การจัดรูปแบบการแสดงข้อมูล** เลือกส่วน**รูปแบบ** ขยาย**ทั่วไป** แล้ว เลื่อนลงไปด้านล่าง และกรอกข้อมูลในกล่องข้อความ**ข้อความแสดงแทน**
  
  ![สามารถเพิ่ม ข้อความแสดงแทน สำหรับวัตถุใด ๆ ในรายงานใน การแสดงภาพ > รูปแบบ > ทั่วไป > ข้อความแสดงแทน](media/desktop-accessibility/accessibility_02.png)
* ตรวจสอบให้แน่ใจว่า รายงานของคุณมีความเปรียบต่างเพียงพอ ระหว่างข้อความและสีพื้นหลัง
* ใช้ขนาดข้อความและแบบอักษรที่อ่านง่าย ข้อความขนาดเล็ก หรือแบบอักษรที่ยากต่อการอ่าน ไม่ได้ช่วยสำหรับการเข้าถึง
* ใส่ชื่อให้กับ ป้ายชื่อแกน และป้ายชื่อข้อมูล ในทุกวิชวล

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด
มีปัญหาที่ทราบแล้วและข้อจำกัดบางประการ ของคุณลักษณะการช่วยสำหรับการเข้าถึง ที่จะอธิบายไว้ในรายการต่อไปนี้:

* JAWS ได้รับการสนับสนุนในรายงานที่ดูใน **บริการของ Power BI** รวมถึงรายงานที่ฝัง JAWS ยังได้รับการสนับสนุนใน **Power BI Desktop** แต่คุณต้องเปิดตัวอ่านหน้าจอ ก่อนที่จะเปิดไฟล์ **Power BI Desktop** ใด ๆ เพื่อให้โปรแกรมอ่านหน้าจอทำงานถูกต้อง

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [ใช้ธีมรายงานใน Power BI Desktop (ตัวอย่าง)](desktop-report-themes.md)

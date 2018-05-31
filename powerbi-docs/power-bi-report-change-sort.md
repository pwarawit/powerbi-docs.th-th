---
title: เปลี่ยนวิธีการเรียงลำดับแผนภูมิในรายงาน Power BI
description: เปลี่ยนวิธีการเรียงลำดับแผนภูมิในรายงาน Power BI
services: powerbi
documentationcenter: ''
author: mihart
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
ms.date: 01/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 8160011a30b54345d446f352148665e3840323d9
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
ms.locfileid: "30974556"
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>เปลี่ยนวิธีการเรียงลำดับแผนภูมิในรายงาน Power BI
ในรายงาน Power BI คุณสามารถเรียงลำดับการแสดงภาพส่วนใหญ่ตามลำดับตัวอักษร โดยชื่อของประเภทในแผนภูมิ หรือค่าตัวเลขของแต่ละประเภท ตัวอย่างเช่น แผนภูมินี้จะเรียงตามชื่อร้านค้า

![](media/power-bi-report-change-sort/pbi_chartsortcategory.png)

เป็นเรื่องง่ายเมื่อต้องเปลี่ยนการเรียงลำดับจากประเภท (ชื่อร้าน) เป็นค่า(ยอดขายสำหรับแต่ละตารางฟุต) แทน

1. เลือกจุดไข่ปลา (...) แล้วเลือก**เรียงลำดับตาม Sq Ft**
2. ถ้าจำเป็น เลือกไอคอนเรียงลำดับ![](media/power-bi-report-change-sort/sorticon.png)เปลี่ยนเป็น**มากไปหาน้อย**

   ![](media/power-bi-report-change-sort/sortby.gif)

   **หมายเหตุ** ภาพไม่สามารถเรียงลำดับได้ทั้งหมด  ตัวอย่างเช่น ไม่สามารถจัดเรียงภาพต่อไปนี้ ทรีแมป แผนที่ แผนที่ที่กรอกข้อมูล ลายจุด หน้าปัด บัตร บัตรหลายแถว น้ำตก

<a name="other"></a>
## <a name="sorting-using-other-criteria"></a>เรียงลำดับโดยใช้เกณฑ์อื่น
บางครั้ง คุณต้องการเรียงภาพของคุณโดยใช้เขตข้อมูลที่แตกต่างกันหรือเงื่อนไขอื่น  ตัวอย่างเช่น คุณอาจต้องการเรียงลำดับตามเดือน (และไม่ได้อยู่ในลำดับตัวอักษร) หรือคุณอาจต้องการเรียงลำดับตามตัวเลขทั้งหมด แทนที่เรียงด้วยตัวเลข (ตัวอย่าง 0, 1, 9, 20 และไม่ 0, 1, 20, 9)  

ในบางกรณี คุณอาจสามารถเรียงลำดับภาพที่คุณต้องการ ตัวอย่างเช่น ตามเดือน  แต่ถ้าไม่ใช่ อาจเนื่องมาจากชุดข้อมูลเบื้องหลังรายงานขาดบางอย่าง ต่อไปนี้เป็นวิธีแก้ไขปัญหาหลากหลาย

* ใน Power BI Desktop, [ใช้แท็บแบบจำลองข้อมูลเครื่องมือเพื่อเรียงลำดับตามคอลัมน์ต่างๆ](desktop-sort-by-column.md)
* ใน Excel ถ้าคุณเป็นเจ้าของชุดข้อมูล เพิ่มคอลัมน์ใหม่ซึ่งรวมชื่อเดือนและตัวเลข จากนั้น รีเฟรชหรือนำเข้าชุดข้อมูลเพื่อจะเห็นคอลัมน์ใหม่ในพื้นที่เขตข้อมูล
* ใน Excel ตรวจสอบให้แน่ใจว่า คอลัมน์ของตัวเลขที่ถูกแท็กเป็น "จำนวนเต็ม" หรือ "ทศนิยม" และไม่ เป็น "ข้อความ"

## <a name="next-steps"></a>ขั้นตอนถัดไป
อ่านเพิ่มเติมเกี่ยวกับ[การแสดงภาพในรายงาน Power BI](power-bi-report-visualizations.md)

[Power BI แนวคิดพื้นฐาน](service-basic-concepts.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)

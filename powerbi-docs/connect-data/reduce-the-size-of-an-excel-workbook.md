---
title: ลดขนาดของเวิร์กบุ๊ก Excel เพื่อดูใน Power BI
description: ลดขนาดของเวิร์กบุ๊ก Excel เพื่อดูใน Power BI
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/10/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 8c58c85ea46f9884586e1ff73f1ef9f7b1db9cdd
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83327242"
---
# <a name="reduce-the-size-of-an-excel-workbook-to-view-it-in-power-bi"></a>ลดขนาดของเวิร์กบุ๊ก Excel เพื่อดูใน Power BI
คุณสามารถอัปโหลดเวิร์กบุ๊ก Excel ต่างๆ ที่มีขนาดเล็กกว่า 1 GB ไปยัง Power BI ได้ เวิร์กบุ๊ก Excel สามารถมีส่วนประกอบสองส่วน ได้แก่: รูปแบบข้อมูล และส่วนเหลือของรายงาน ซึ่งเป็นเนื้อหาหลักของเวิร์กชีต ถ้ารายงานมีขนาดที่ตรงตามขีดจำกัดด้านขนาดต่อไปนี้ คุณก็สามารถบันทึกไปยัง**OneDrive for Business** ให้เชื่อมต่อจาก Power BI แล้วดูใน Excel Online:

* ทั้งเวิร์กบุ๊กสามารถมีขนาดได้สูงสุดถึง 1 GB
* เนื้อหาหลักของเวิร์กชีตสามารถมีขนาดได้สูงสุดถึง 30 MB

## <a name="what-makes-core-worksheet-contents-larger-than-30-mb"></a>สิ่งที่ทำให้เนื้อหาหลักของเวิร์กชีตมีขนาดใหญ่กว่า 30 MB
นี่คือองค์ประกอบบางอย่างที่สามารถทำใหเนื้อหาหลักของเวิร์กชีตมีขนาดใหญ่กว่า 30 MB:

* รูปภาพ
* เซลล์ที่แรเงา [เอารูปแบบการแรเงาเซลล์ออก](https://support.office.com/article/Add-or-change-the-background-color-of-cells-ac10f131-b847-428f-b656-d65375fb815e)
* เวิร์กชีตที่มีการใช้สี [เอาพื้นหลังของแผ่นงานออก](https://support.office.com/article/add-or-remove-a-sheet-background-3577a762-8450-4556-96a2-cc265abc00a8)
* กล่องข้อความ
* ภาพตัดปะ

พิจารณาเอาองค์ประกอบเหล่านี้ออก ถ้าเป็นไปได้ 

ถ้ารายงานมีรูปแบบข้อมูล คุณก็จะมีตัวเลือกอื่นๆ บางตัวเลือก ได้แก่: 

* เอาข้อมูลออกจากเวิร์กชีต Excel แล้วจัดเก็บไว้ในรูปแบบข้อมูลแทน โปรดดู "เอาข้อมูลออกจากเวิร์กชีต" ที่ด้านล่าง สำหรับรายละเอียด 
* [สร้างรูปแบบข้อมูลที่มีหน่วยความจำที่มีประสิทธิภาพ](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70) เพื่อลดขนาดโดยรวมของรายงาน

เมื่อต้องการให้เกิดการเปลี่ยนแปลงดังกล่าว คุณจะต้องแก้ไขเวิร์กบุ๊กใน Excel

อ่านข้อมูลเพิ่มเติมเกี่ยวกับ[ขีดจำกัดของขนาดไฟล์สำหรับเวิร์กบุ๊ก Excel ใน SharePoint Online](https://support.office.com/article/File-size-limits-for-workbooks-in-SharePoint-Online-9e5bc6f8-018f-415a-b890-5452687b325e)

## <a name="remove-data-from-worksheets"></a>เอาข้อมูลออกจากเวิร์กชีต
ถ้าคุณนำเข้าข้อมูลลงใน Excel จากแท็บ Power Query หรือแท็บข้อมูลของ Excel เวิร์กบุ๊กอาจมีข้อมูลเหมือนกับในตาราง Excel และในรูปแบบข้อมูล ตารางขนาดใหญ่ในเวิร์กชีต Excel อาจทำให้เนื้อหาหลักของเวิร์กชีตมีขนาดใหญ่เกินกว่า 30 MB การลบตารางใน Excel และการเก็บข้อมูลในรูปแบบข้อมูลสามารถลดเนื้อหาหลักของเวิร์กชีตในรายงานได้เป็นอย่างมาก 

เมื่อคุณนำเข้าข้อมูลลงใน Excel ให้ทำตามคำแนะนำเหล่านี้:

* **ใน Power Query**: ล้างข้อมูลในกล่อง**การโหลดไปยังเวิร์กชีต**
  
  ข้อมูลได้รับการนำเข้าเฉพาะในรูปแบบข้อมูลที่ไม่มีข้อมูลในเวิร์กชีต Excel เท่านั้น
* **จากแท็บข้อมูล Excel**ถ้าคุณได้เลือก**ตาราง**ไว้ก่อนหน้านี้ในตัวช่วยสร้างนำเข้า: ไปยัง**การเชื่อมต่อที่ยังคงอยู่** \>คลิกการเชื่อมต่อ\> **สร้างเฉพาะการเชื่อมต่อ** ลบตารางต้นฉบับหรือตารางที่สร้างขึ้นในระหว่างการนำเข้าเริ่มต้น
* **ในส่วนแท็บข้อมูล Excel**: ไม่ต้องทำเครื่องหมายเลือก**ตาราง**ในกล่อง**การนำเข้าข้อมูล**

## <a name="workbook-size-optimizer"></a>ตัวปรับเพิ่มขนาดเวิร์กบุ๊ก
ถ้าเวิร์กบุ๊กของคุณประกอบด้วยรูปแบบข้อมูล คุณก็สามารถเรียกใช้ตัวปรับเพิ่มขนาดเวิร์กบุ๊กเพื่อลดขนาดเวิร์กบุ๊กของคุณได้ [ดาวน์โหลดตัวปรับเพิ่มขนาดเวิร์กบุ๊ก](https://www.microsoft.com/download/details.aspx?id=38793)

## <a name="related-info"></a>ข้อมูลที่เกี่ยวข้อง
[สร้างรูปแบบข้อมูลที่มีหน่วยความจำที่มีประสิทธิภาพ](https://support.office.com/article/Create-a-memory-efficient-Data-Model-using-Excel-2013-and-the-Power-Pivot-add-in-951c73a9-21c4-46ab-9f5e-14a2833b6a70)

[ใช้ลิงก์ OneDrive for Business ใน Power BI Desktop](desktop-use-onedrive-business-links.md)


---
title: การกรองข้ามแบบสองทิศทางใน Power BI Desktop
description: เปิดใช้งานการกรองข้ามด้วย DirectQuery ใน Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 141dabdce7816d21c49d8c7f98d1438c2fc20e8d
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "76709831"
---
# <a name="enable-bidirectional-cross-filtering-for-directquery-in-power-bi-desktop"></a>เปิดใช้การกรองข้ามแบบสองทิศทางสำหรับ DirectQuery ใน Power BI Desktop

ขณะกรองตารางเพื่อสร้างมุมมองข้อมูลที่เหมาะสม ผู้สร้างรายงานและผู้จัดรูปแบบข้อมูลจะพบกับความท้าทายในการกำหนดวิธีการใช้ตัวกรองต่างๆ กับรายงาน ก่อนหน้านี้ บริบทของตัวกรองตารางจะขึ้นอยู่กับด้านหนึ่งของความสัมพันธ์ ไม่ใช่อีกด้านหนึ่ง การจัดการนี้มักจะต้องใช้สูตร DAX ที่ซับซ้อนเพื่อให้ได้ผลลัพธ์ที่ต้องการ

ด้วยการกรองแบบไขว้สองทิศทาง ทำให้ขณะนี้ ผู้สร้างรายงานและผู้จัดรูปแบบข้อมูลสามารถควบคุมลักษณะการใช้ฟิลเตอร์ต่าง ๆ ขณะทำงานกับตารางที่เกี่ยวข้องได้แล้ว การกรองแบบไขว้สองทิศทางจะทำให้พวกเขาสามารถใช้ตัวกรองกับความสัมพันธ์ของตารางได้ทั้ง*สอง*ด้าน คุณสามารถปรับใช้ตัวกรองต่าง ๆ โดยการเผยแพร่บริบทตัวกรองไปยังตารางที่เกี่ยวข้องลำดับที่สอง ที่อีกด้านหนึ่งของความสัมพันธ์ของตาราง

## <a name="enable-bidirectional-cross-filtering-for-directquery"></a>เปิดใช้การกรองแบบไขว้สองทิศทางสำหรับ DirectQuery

คุณสามารถเปิดใช้การกรองแบบไขว้ในกล่องโต้ตอบ **แก้ไขความสัมพันธ์** เพื่อเปิดใช้การกรองแบบไขว้สำหรับความสัมพันธ์ คุณจะต้องกำหนดค่าตัวเลือกต่อไปนี้:

* ตั้งค่า**ทิศทางตัวกรองแบบไขว้** เป็น **ทั้งคู่**
* เลือก **ปรับใช้ตัวกรองด้านความปลอดภัยทั้งสองทิศทาง**

  ![กำหนดค่าการกรองแบบสองทิศทางใน Power BI Desktop](media/desktop-bidirectional-filtering/bidirectional-filtering_2.png)

> [!NOTE]
> ขณะสร้างสูตร DAX สำหรับการกรองแบบไขว้ใน Power BI Desktop ให้ใช้ *UserPrincipalName* เขตข้อมูลนี้มักจะเป็นข้อมูลเดียวกับการเข้าสู่ระบบของผู้ใช้ ตัวอย่างเช่น <em>joe@contoso.com</em> แทนที่จะเป็น *UserName* ด้วยเหตุนี้ คุณจึงอาจจำเป็นต้องสร้างตารางที่เกี่ยวข้องที่แมป *UserName* หรือ *EmployeeID* ไปยัง *UserPrincipalName*

สำหรับข้อมูลเพิ่มเติม และตัวอย่างลักษณะการกรองแบบไขว้สองทิศทาง โปรดตรวจสอบ [การกรองไขว้แบบสองทิศทางสำหรับเอกสารทางเทคนิคเกี่ยวกับ Power BI Desktop](https://download.microsoft.com/download/2/7/8/2782DF95-3E0D-40CD-BFC8-749A2882E109/Bidirectional%20cross-filtering%20in%20Analysis%20Services%202016%20and%20Power%20BI.docx)


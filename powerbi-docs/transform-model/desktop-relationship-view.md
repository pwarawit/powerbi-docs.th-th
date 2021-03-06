---
title: มุมมองแบบจำลองใน Power BI Desktop
description: มุมมองแบบจำลองใน Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 01/17/2020
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 1c580d403ef33f1c61d5fcd0707d78b4b331da5d
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85239854"
---
# <a name="work-with-model-view-in-power-bi-desktop"></a>ทำงานร่วมกับมุมมองแบบจำลองใน Power BI Desktop

*มุมมองแบบจำลอง* แสดงตาราง คอลัมน์ และความสัมพันธ์ทั้งหมดในรูปแบบข้อมูลของคุณ ซึ่งจะเป็นประโยชน์โดยเฉพาะเมื่อรูปแบบของคุณมีความสัมพันธ์ระหว่างตารางต่าง ๆ ที่ซับซ้อน

เลือกไอคอน **แบบจำลอง** ที่อยู่ใกล้กับด้านข้างของหน้าต่างเพื่อดูมุมมองของแบบจำลองที่มีอยู่ วางเมาส์เคอร์เซอร์ของคุณเหนือเส้นความสัมพันธ์เพื่อแสดงคอลัมน์ที่ใช้

![มุมมองแบบจำลอง, Power BI Desktop](media/desktop-relationship-view/model-view-full-screen.png)

ในรูป คุณสามารถเห็นว่าตาราง*ร้านค้า* มีคอลัมน์ *StoreKey* ที่เกี่ยวข้องกับตาราง*ยอดขาย* ซึ่งมีคอลัมน์ *StoreKey* เช่นเดียวกัน ตารางทั้งสองมีความสัมพันธ์แบบ *กลุ่มต่อหนึ่ง* (\*: 1) ลูกศรที่กึ่งกลางเส้นแสดงทิศทางโฟลว์ของบริบทตัวกรอง ลูกศรคู่หมายความว่า ทิศทางตัวกรองแบบไขว้ ถูกตั้งค่าเป็น *ทั้งสอง*

คุณสามารถดับเบิลคลิกที่ความสัมพันธ์เพื่อเปิดรายการในกล่องโต้ตอบ **แก้ไขความสัมพันธ์** เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับความสัมพันธ์ ดู[สร้าง และจัดการความสัมพันธ์ใน Power BI Desktop](desktop-create-and-manage-relationships.md)

---
title: เพิ่มหลายเขตข้อมูลไปยังตัวแบ่งส่วนลำดับชั้น
description: เรียนรู้วิธีการสร้างตัวแบ่งส่วนลำดับชั้นที่มีหลายเขตข้อมูลในหนึ่งลำดับชั้น
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 07/06/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 5fbaeaafb14fc935e26b4a2d13acf9dc09ea188f
ms.sourcegitcommit: 11deeccf596e9bb8f22615276a152614f7579f35
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/16/2020
ms.locfileid: "86409589"
---
# <a name="add-multiple-fields-to-a-hierarchy-slicer"></a>เพิ่มหลายเขตข้อมูลไปยังตัวแบ่งส่วนลำดับชั้น

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

หากคุณต้องการกรองหลายเขตข้อมูลที่เกี่ยวข้องกันภายในหนึ่งตัวแบ่งส่วน คุณสามารถทำได้โดยการสร้างสิ่งที่เรียกว่า ตัวแบ่งส่วน *ลำดับชั้น* คุณสามารถสร้างตัวแบ่งส่วนข้อมูลเหล่านี้ได้ทั้งใน Power BI Desktop หรือในบริการของ Power BI

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy.png" alt-text="สกรีนช็อตของตัวแบ่งส่วนลำดับชั้นใน Power B I":::

เมื่อคุณเพิ่มหลายเขตข้อมูลไปที่ตัวแบ่งส่วนข้อมูล โดยค่าเริ่มต้นแล้ว ระบบจะแสดงลูกศร หรือ *เครื่องหมายบั้ง* ถัดจากรายการที่สามารถขยายเพื่อแสดงรายการในระดับถัดไป

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-arrow.png" alt-text="สกรีนช็อตรายการดรอปดาวน์ของตัวแบ่งส่วนลำดับชั้นใน Power B I":::
 
 
เมื่อคุณเลือกรายการอย่างน้อยหนึ่งรายการ คุณจะเห็นวงกลมแบบกึ่งเลือกสำหรับรายการระดับสูงสุด
 
:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-semi-selected.png" alt-text="สกรีนช็อตของตัวแบ่งส่วนลำดับชั้นการเลือกครั้งเดียวใน Power B I":::

## <a name="format-the-slicer"></a>จัดรูปแบบตัวแบ่งส่วนข้อมูล

ลักษณะการทำงานของตัวแบ่งส่วนไม่มีการเปลี่ยนแปลง คุณยังสามารถจัดรูปแบบตัวแบ่งส่วนข้อมูลของคุณได้ตามที่คุณต้องการ ตัวอย่างเช่น คุณสามารถตั้งค่าเป็นโหมดเลือกครั้งเดียวได้ หรือคุณสามารถสลับระหว่างรายการและดรอปดาวน์ได้ 

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-dropdown.png" alt-text="สกรีนช็อตของตัวแบ่งส่วนลำดับชั้นที่จัดรูปแบบเป็นตัวแบ่งส่วนข้อมูลดรอปดาวน์":::

คุณยังสามารถทำการเปลี่ยนแปลงรูปแบบต่อไปนี้ได้:

### <a name="change-the-title"></a>เปลี่ยนชื่อเรื่อง

คุณสามารถแก้ไขชื่อสำหรับตัวแบ่งส่วนข้อมูลได้ แต่ใช้ได้เฉพาะกับตัวแบ่งส่วนลำดับชั้น ตามค่าเริ่มต้น ชื่อของตัวแบ่งส่วนลำดับชั้นคือรายการของชื่อเขตข้อมูลในลำดับชั้น

ในตัวอย่างนี้ ชื่อของตัวแบ่งส่วนข้อมูลจะแสดงรายการสามเขตข้อมูลในลำดับชั้น: ประเภท แพลตฟอร์ม และชื่อ

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-title.png" alt-text="สกรีนช็อตของตัวแบ่งส่วนลำดับชั้นด้วยประเภท แพลตฟอร์ม และชื่อ":::

ถ้าต้องการเปลี่ยนชื่อ ให้เลือกตัวแบ่งส่วนข้อมูล จากนั้นเลือกบานหน้าต่าง **รูปแบบ** ใน **ส่วนหัวของตัวแบ่งส่วนข้อมูล** คุณจะเห็นชื่อปัจจุบันของตัวแบ่งส่วนข้อมูลในกล่อง **ข้อความชื่อ**

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-edit-title.png" alt-text="สกรีนช็อตของบานหน้าต่างรูปแบบที่มีชื่อปัจจุบัน":::

เลือกข้อความและเพิ่มชื่อใหม่

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-new-title.png" alt-text="สกรีนช็อตของชื่อใหม่สำหรับตัวแบ่งส่วนลำดับชั้น":::


### <a name="change-the-expandcollapse-icon"></a>เปลี่ยนไอคอนขยาย/ยุบ

ตัวแบ่งส่วนลำดับชั้นมีตัวเลือกการจัดรูปแบบอื่น คุณสามารถเปลี่ยนไอคอนขยาย/ยุบจากลูกศรตามค่าเริ่มต้นเป็นเครื่องหมายบวก/ลบหรืออักขระ ^ ได้

1. เลือกตัวแบ่งส่วนข้อมูล จากนั้นเลือก **รูปแบบ**
1. ขยาย **รายการ** และเลือก **ไอคอนขยาย/ยุบ**
1. เลือกจาก **เครื่องหมายบั้ง** **บวก/ลบ** หรือ **อักขระ ^**
 
    :::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-caret.png" alt-text="สกรีนช็อตของการเลือกไอคอนขยาย/ยุบสำหรับตัวแบ่งส่วนลำดับชั้นของคุณ":::
 
### <a name="change-the-indentation"></a>เปลี่ยนการเยื้อง

หากเนื้อที่ในรายงานของคุณอัดแน่น คุณอาจต้องการลดจำนวนการเยื้องรายการย่อย ตามค่าเริ่มต้น การเยื้องตั้งไว้ที่ 15 พิกเซล แต่คุณสามารถเพิ่มหรือลดค่านั้นได้ 

1. เลือกตัวแบ่งส่วนข้อมูล จากนั้นเลือก **รูปแบบ**
1. ขยาย **รายการ** จากนั้นลาก **การเยื้องรูปแบบขั้น** ให้มีขนาดเล็กลงหรือใหญ่ขึ้น คุณยังสามารถพิมพ์ตัวเลขลงในกล่องได้เช่นกัน

    :::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-indentation.png" alt-text="สกรีนช็อตของการตั้งค่าตัวแบ่งส่วนลำดับชั้น":::

## <a name="next-steps"></a>ขั้นตอนถัดไป

- [ตัวแบ่งส่วนข้อมูลใน Power BI](../visuals/power-bi-visualization-slicers.md)
- มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
---
title: เพิ่มหลายเขตข้อมูลไปยังตัวแบ่งส่วนลำดับชั้น
description: เรียนรู้วิธีการสร้างตัวแบ่งส่วนลำดับชั้นที่มีหลายเขตข้อมูลในหนึ่งลำดับชั้น
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 06/11/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 2b9c4a8f4695f8d701eba535180194d29dd8bdec
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85238173"
---
# <a name="add-multiple-fields-to-a-hierarchy-slicer"></a>เพิ่มหลายเขตข้อมูลไปยังตัวแบ่งส่วนลำดับชั้น

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

หากคุณต้องการกรองหลายเขตข้อมูลที่เกี่ยวข้องกันภายในหนึ่งตัวแบ่งส่วน คุณสามารถทำได้โดยการสร้างสิ่งที่เรียกว่า ตัวแบ่งส่วน *ลำดับชั้น* คุณสามารถสร้างตัวแบ่งส่วนข้อมูลเหล่านี้ได้ทั้งใน Power BI Desktop หรือในบริการของ Power BI

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy.png" alt-text="ตัวแบ่งส่วนลำดับชั้นใน Power BI":::

เมื่อคุณเพิ่มหลายเขตข้อมูลไปที่ตัวแบ่งส่วนข้อมูล โดยค่าเริ่มต้นแล้ว ระบบจะแสดงลูกศร หรือ *เครื่องหมายบั้ง* ถัดจากรายการที่สามารถขยายเพื่อแสดงรายการในระดับถัดไป

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-arrow.png" alt-text="รายการแบบเลื่อนลงของตัวแบ่งส่วนลำดับชั้นใน Power BI":::
 
 
เมื่อคุณเลือกรายการอย่างน้อยหนึ่งรายการ คุณจะเห็นวงกลมแบบกึ่งเลือกสำหรับรายการระดับสูงสุด
 
:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-semi-selected.png" alt-text="ตัวแบ่งส่วนลำดับชั้นแบบเลือกครั้งเดียวใน Power BI":::

## <a name="format-the-slicer"></a>จัดรูปแบบตัวแบ่งส่วนข้อมูล

ลักษณะการทำงานของตัวแบ่งส่วนไม่มีการเปลี่ยนแปลง คุณยังสามารถจัดรูปแบบตัวแบ่งส่วนข้อมูลของคุณได้ตามที่คุณต้องการ ตัวอย่างเช่น คุณสามารถตั้งค่าเป็นโหมดเลือกครั้งเดียวได้ หรือคุณสามารถสลับระหว่างรายการและดรอปดาวน์ได้ 

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-dropdown.png" alt-text="ตัวแบ่งส่วนลำดับชั้นที่จัดรูปแบบเป็นตัวแบ่งส่วนรายการแบบเลื่อนลง":::

### <a name="change-the-expandcollapse-icon"></a>เปลี่ยนไอคอนขยาย/ยุบ

ตัวแบ่งส่วนลำดับชั้นมีตัวเลือกการจัดรูปแบบอื่น คุณสามารถเปลี่ยนไอคอนขยาย/ยุบจากลูกศรตามค่าเริ่มต้นเป็นเครื่องหมายบวก/ลบหรืออักขระ ^ ได้

1. เลือกตัวแบ่งส่วนข้อมูล จากนั้นเลือก **รูปแบบ**
1. ขยาย **รายการ** และเลือก **ไอคอนขยาย/ยุบ**
1. เลือกจาก **เครื่องหมายบั้ง** **บวก/ลบ** หรือ **อักขระ ^**
 
    :::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-caret.png" alt-text="เลือกไอคอนขยาย/ยุบสำหรับตัวแบ่งส่วนลำดับชั้นของคุณ":::
 
### <a name="change-the-indentation"></a>เปลี่ยนการเยื้อง

หากเนื้อที่ในรายงานของคุณอัดแน่น คุณอาจต้องการลดจำนวนการเยื้องรายการย่อย ตามค่าเริ่มต้น การเยื้องตั้งไว้ที่ 15 พิกเซล แต่คุณสามารถเพิ่มหรือลดค่านั้นได้ 

1. เลือกตัวแบ่งส่วนข้อมูล จากนั้นเลือก **รูปแบบ**
1. ขยาย **รายการ** จากนั้นลาก **การเยื้องรูปแบบขั้น** ให้มีขนาดเล็กลงหรือใหญ่ขึ้น คุณยังสามารถพิมพ์ตัวเลขลงในกล่องได้เช่นกัน

    :::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-indentation.png" alt-text="ตั้งค่าการเยื้องของตัวแบ่งส่วนลำดับชั้น":::

## <a name="next-steps"></a>ขั้นตอนถัดไป

- [ตัวแบ่งส่วนข้อมูลใน Power BI](../visuals/power-bi-visualization-slicers.md)
- มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
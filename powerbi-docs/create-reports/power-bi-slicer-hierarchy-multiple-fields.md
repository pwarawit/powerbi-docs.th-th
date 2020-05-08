---
title: เพิ่มเขตข้อมูลหลายรายการในตัวแบ่งส่วนข้อมูล
description: เรียนรู้วิธีการสร้างตัวแบ่งส่วนที่มีหลายเขตข้อมูลในลำดับชั้นหนึ่ง
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/06/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: c41fa1e0c8510f64f9c6e53c83fe9ee8a2e75e67
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "81006904"
---
# <a name="add-multiple-fields-to-a-slicer-preview"></a>เพิ่มหลายเขตข้อมูลไปยังตัวแบ่งส่วน (ตัวอย่าง)

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

หากคุณต้องการกรองหลายเขตข้อมูลที่เกี่ยวข้องกันภายในตัวแบ่งส่วนหนึ่งตัว คุณจะสามารถทำเช่นนั้นได้โดยการสร้างสิ่งที่เรียกว่า ตัวแบ่งส่วน*ลำดับชั้น* 

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy.png" alt-text="ตัวแบ่งส่วนลำดับชั้นใน Power BI":::

เมื่อต้องการเปิดคุณลักษณะการแสดงตัวอย่างนี้ บนเมนู **ไฟล์** > **ตัวเลือกและการตั้งค่า** > **ตัวเลือก** ภายใต้**ทั่วโลก** ไปที่ส่วน **คุณลักษณะตัวอย่าง** และตรวจสอบให้แน่ใจว่า ได้ทำเครื่องหมายที่ **ตัวแบ่งส่วนลำดับชั้น** แล้ว

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-preview.png" alt-text="เลือกคุณลักษณะตัวอย่างตัวแบ่งส่วนข้อมูลลำดับชั้น":::

เมื่อคุณเพิ่มหลายเขตข้อมูลไปที่ตัวแบ่งส่วน ระบบจะแสดงลูกศร หรือ *เครื่องหมายบั้ง* ที่อยู่ถัดจากรายการที่สามารถขยายเพื่อแสดงรายการในระดับถัดไป

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-arrow.png" alt-text="รายการแบบเลื่อนลงของตัวแบ่งส่วนลำดับชั้นใน Power BI":::
 
ลักษณะการทำงานของตัวแบ่งส่วนไม่มีการเปลี่ยนแปลง คุณยังคงสามารถสลับไปมาได้ระหว่างรายการและรายการแบบเลื่อนลง และคุณยังคงสามารถจัดรูปแบบตัวแบ่งส่วนของคุณตามที่ต้องการ

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-dropdown.png" alt-text="ตัวแบ่งส่วนลำดับชั้นที่จัดรูปแบบเป็นตัวแบ่งส่วนรายการแบบเลื่อนลง":::
 
ทั้งนี้ คุณสามารถตั้งค่าเป็นโหมดเลือกครั้งเดียวได้ คุณจะเห็นวงกลมที่เลือกครึ่งวง สำหรับรายการที่มีเด็กบางคนเลือก
 
:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-semi-selected.png" alt-text="ตัวแบ่งส่วนลำดับชั้นแบบเลือกครั้งเดียวใน Power BI":::

## <a name="next-steps"></a>ขั้นตอนถัดไป

- [ตัวแบ่งส่วนข้อมูลใน Power BI](../visuals/power-bi-visualization-slicers.md)
- มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
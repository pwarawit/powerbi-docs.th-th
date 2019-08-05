---
title: เปิดใช้งานตัวแบ่งส่วนข้อมูลการซิงค์
description: วิธีการเพิ่มคุณลักษณะตัวแบ่งส่วนข้อมูลการซิงค์สำหรับวิชวล Power BI
author: EugeneElkin
ms.author: v-evelk
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 9966475e8bcaccad2090451b47ef09ef0a9af125
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425033"
---
# <a name="sync-slicers"></a>ตัวแบ่งส่วนข้อมูลการซิงค์

หากต้องการสนับสนุน[ตัวแบ่งส่วนข้อมูลการซิงค์](https://docs.microsoft.com/power-bi/desktop-slicers) วิชวลตัวแบ่งส่วนข้อมูลแบบกำหนดเองของคุณต้องใช้ API 1.13 หรือสูงกว่า

มีการเปิดใช้งานมุมมองที่จำเป็นสำรองใน `capabilities.json` (ดูตัวอย่างด้านล่าง)

```json
{
    ...
    "supportsHighlight": true,
    "suppressDefaultTitle": true,
    "supportsSynchronizingFilterState": true,
    "sorting": {
        "default": {}
    }
}
```

หลังจากการเปลี่ยนแปลงใน `capabilities.json` คุณสามารถดูบานหน้าต่างตัวเลือกตัวแบ่งส่วนข้อมูลการซิงค์เมื่อคุณคลิกที่วิชวลตัวแบ่งส่วนข้อมูลแบบกำหนดเองของคุณ

> [!NOTE]
> ถ้าตัวแบ่งส่วนข้อมูลของคุณมีมากกว่า 1 เขตข้อมูล (ประเภทหรือหน่วยวัด) คุณลักษณะนี้จะถูกปิดใช้งานเนื่องจากตัวแบ่งส่วนข้อมูลการซิงค์ไม่สนับสนุนหลายเขตข้อมูล

![บานหน้าต่างของตัวแบ่งส่วนข้อมูลการซิงค์](./media/sync-slicers-panel.png)

ในบานหน้าต่าง คุณสามารถดูว่าการแสดงผลของตัวแบ่งส่วนข้อมูลและการกรองอาจถูกนำไปใช้กับหน้ารายงานจำนวนมาก

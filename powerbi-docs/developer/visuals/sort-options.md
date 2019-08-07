---
title: เรียงลำดับ
description: พฤติกรรมการจัดเรียงค่าเริ่มต้นสำหรับการแสดงผลด้วยภาพ Power BI
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: f3d913e2bce34850dfae4c9486b2e43c78521a58
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424527"
---
# <a name="sorting-options"></a>ตัวเลือกการจัดเรียง

`Sorting` ระบุพฤติกรรมการจัดเรียงค่าเริ่มต้นสำหรับการแสดงผลด้วยภาพ
ความสามารถจำเป็นต้องมีหนึ่งในพารามิเตอร์ที่อธิบายไว้ด้านล่าง:

## <a name="default-sorting"></a>เรียงลำดับค่าเริ่มต้น

ตัวเลือก `default` คือฟอร์มที่ง่ายที่สุด ซึ่งช่วยการเรียงลำดับข้อมูลที่แสดงในส่วน 'DataMappings'
ตัวเลือกนี้จะเปิดใช้งานการเรียงลำดับของ 'DataMappings' โดยผู้ใช้และเพื่อระบุทิศทางการเรียงลำดับ

```json
    "sorting": {
        "default": {   }
    }
```

![ตัวเลือกการเรียงลำดับในเมนูบริบท](./media/sorting.png)

## <a name="implicit-sorting"></a>การเรียงลำดับโดยนัย

`implicit` มีการเรียงลำดับด้วยพารามิเตอรอาร์เรย์ `clauses` ซึ่งอธิบายการเรียงลำดับสำหรับแต่ละบทบาทข้อมูล
`implicit` หมายความว่าผู้ใช้ของการแสดงผลด้วยภาพไม่สามารถเปลี่ยนลำดับการจัดเรียงได้
Power BI จะไม่แสดงตัวเลือกการเรียงลำดับในเมนูของการแสดงผลด้วยภาพ อย่างไรก็ตาม Power BI จะเรียงลำดับข้อมูลตามการตั้งค่าที่ระบุ

`clauses` params สามารถมีหลายวัตถุที่มีสองพารามิเตอร์:

- `role` - กำหนด `DataMapping` สำหรับการเรียงลำดับ

- `direction` - กำหนดทิศทางการเรียงลำดับ (1 = จากน้อยไปหามาก 2 = จากมากไปหาน้อย)

```json
    "sorting": {
        "implicit": {
            "clauses": [
                {
                    "role": "category",
                    "direction": 1
                },
                {
                    "role": "measure",
                    "direction": 2
                }
            ]
        }
    }
```

## <a name="custom-sorting"></a>การเรียงลำดับแบบกำหนดเอง

`custom` หมายถึงการเรียงลำดับที่จัดการโดยผู้พัฒนาในโค้ดของการแสดงผลภาพ

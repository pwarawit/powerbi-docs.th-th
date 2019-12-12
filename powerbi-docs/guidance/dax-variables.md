---
title: 'DAX: ใช้ตัวแปรเพื่อปรับปรุงสูตรของคุณ'
description: คำแนะนำเกี่ยวกับการใช้ตัวแปรในนิพจน์ DAX
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/23/2019
ms.author: v-pemyer
ms.openlocfilehash: f352cbbd7c42aa54ae876e73c0ed821eccda59c8
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/02/2019
ms.locfileid: "74700719"
---
# <a name="dax-use-variables-to-improve-your-formulas"></a>DAX: ใช้ตัวแปรเพื่อปรับปรุงสูตรของคุณ

ในฐานะผู้สร้างแบบจำลองข้อมูล การเขียนและการดีบักการคำนวณ DAX บางอย่างอาจเป็นเรื่องที่ท้าทาย ซึ่งเป็นเรื่องปกติที่ข้อกำหนดการคำนวณที่ซับซ้อนมักเกี่ยวข้องกับการเขียนนิพจน์ประสมหรือนิพจน์ซับซ้อน นิพจน์ประสมสามารถเกี่ยวข้องกับการใช้ฟังก์ชันที่ซ้อนกันมากมาย และอาจมีการนำตรรกะของนิพจน์กลับมาใช้ใหม่

การใช้ตัวแปรในสูตร DAX ของคุณจะช่วยให้คุณสามารถเขียนการคำนวณที่ซับซ้อนและมีประสิทธิภาพได้ ตัวแปรสามารถ:

- [ปรับปรุงประสิทธิภาพ](#improve-performance)
- [ปรับปรุงความสามารถในการอ่าน](#improve-readability)
- [ทำให้การดีบักง่าย](#simplify-debugging)
- [ลดความซับซ้อน](#reduce-complexity)

ในบทความนี้ เราจะแสดงให้เห็นถึงประโยชน์สามประการแรกโดยใช้ตัวอย่างหน่วยวัดสำหรับการเติบโตของยอดขายแบบรายปี (YoY) (สูตรสำหรับการเติบโตของยอดขายแบบรายปีคือ: ยอดขาย sales _fewer ตามช่วงเวลาสำหรับช่วงเวลาเดียวกันของปีที่แล้ว _หารด้วย_ ยอดขายสำหรับช่วงเวลาเดียวกันของปีที่แล้ว)

มาเริ่มต้นจากข้อกำหนดหน่วยวัดต่อไปนี้กันดีกว่า

```dax
Sales YoY Growth % =
DIVIDE(
    ([Sales] - CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))),
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
)
```

หน่วยวัดให้ผลลัพธ์ที่ถูกต้อง แต่ตอนนี้มาดูกันว่าเราจะสามารถปรับปรุงอะไรได้อย่างไรบ้าง

## <a name="improve-performance"></a>ปรับปรุงประสิทธิภาพ

ขอให้สังเกตว่าสูตรทำซ้ำนิพจน์ที่คำนวณ "ช่วงเวลาเดียวกันของปีที่แล้ว" สูตรนี้ไม่มีประสิทธิภาพ เนื่องจากต้องใช้ Power BI เพื่อประเมินนิพจน์เดียวกันสองครั้ง ข้อกำหนดหน่วยวัดสามารถทำให้มีประสิทธิภาพมากขึ้นโดยใช้ตัวแปร

ข้อกำหนดหน่วยวัดต่อไปนี้แสดงถึงการปรับปรุง ซึ่งใช้นิพจน์เพื่อกำหนดผลลัพธ์ "ช่วงเวลาเดียวกันของปีที่แล้ว" ให้กับตัวแปรชื่อ **SalesPriorYear** จากนั้นตัวแปรจะถูกใช้สองครั้งในนิพจน์ RETURN

```dax
Sales YoY Growth % =
VAR SalesPriorYear =
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
RETURN
    DIVIDE(([Sales] - SalesPriorYear), SalesPriorYear)
```

หน่วยวัดยังคงสร้างผลลัพธ์ที่ถูกต้องอย่างต่อเนื่องและใช้เวลาประมาณครึ่งหนึ่งของเวลาคิวรี

## <a name="improve-readability"></a>ปรับปรุงความสามารถในการอ่าน

ในข้อกำหนดหน่วยวัดก่อนหน้านี้ ให้สังเกตว่าตัวเลือกของชื่อตัวแปรทำให้นิพจน์ RETURN นั้นง่ายต่อการเข้าใจอย่างไร นิพจน์สั้นและสามารถอธิบายตัวเองได้

## <a name="simplify-debugging"></a>ทำให้การดีบักง่าย

ตัวแปรยังสามารถช่วยคุณในการดีบักสูตรอีกด้วย หากต้องการทดสอบนิพจน์ที่กำหนดให้กับตัวแปร คุณจะเขียนนิพจน์ RETURN ชั่วคราวอีกครั้งเพื่อแสดงผลตัวแปร

ข้อกำหนดหน่วยวัดต่อไปนี้ส่งกลับเฉพาะตัวแปร **SalesPriorYear** เท่านั้น สังเกตว่ามีการคอมเมนต์นิพจน์ RETURN ที่ตั้งใจไว้อย่างไร เทคนิคนี้ช่วยให้คุณสามารถย้อนกลับได้ง่ายเมื่อการดีบักเสร็จสมบูรณ์

```dax
Sales YoY Growth % =
VAR SalesPriorYear =
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
RETURN
    --DIVIDE(([Sales] - SalesPriorYear), SalesPriorYear)
    SalesPriorYear
```

## <a name="reduce-complexity"></a>ลดความซับซ้อน

ใน DAX เวอร์ชันก่อนหน้า ยังไม่สนับสนุนตัวแปร ซึ่งต้องใช้นิพจน์ที่ซับซ้อนที่นำบริบทตัวกรองใหม่เข้ามาใช้เพื่อใช้ฟังก์ชัน [EARLIER](/dax/earlier-function-dax) หรือ [ EARLIEST](/dax/earliest-function-dax) DAX ในการอ้างอิงบริบทตัวกรองชั้นนอก แต่น่าเสียดายที่ผู้สร้างแบบจำลองข้อมูลพบว่าฟังก์ชันเหล่านี้เข้าใจและใช้งานยาก

ตัวแปรจะถูกประเมินนอกตัวกรองของคุณโดยใช้นิพจน์ RETURN เสมอ ด้วยเหตุผลนี้เมื่อคุณใช้ตัวแปรภายในบริบทตัวกรองที่ปรับเปลี่ยนแล้ว จะได้ผลลัพธ์เช่นเดียวกับฟังก์ชัน EARLIEST ดังนั้นจึงสามารถหลีกเลี่ยงการใช้ฟังก์ชัน EARLIER หรือ EARLIEST ได้ ซึ่งหมายความว่าตอนนี้คุณสามารถเขียนสูตรที่มีความซับซ้อนน้อยลง และทำความเข้าใจได้ง่ายขึ้น

พิจารณาคำจำกัดความคอลัมน์จากการคำนวณต่อไปนี้ที่ถูกเพิ่มลงในตาราง **Subcategory** ซึ่งจะประเมินอันดับสำหรับแต่ละหมวดหมู่ย่อยของผลิตภัณฑ์ตามค่าคอลัมน์ **Subcategory Sales**

```dax
Subcategory Sales Rank =
COUNTROWS(
    FILTER(
        Subcategory,
        EARLIER(Subcategory[Subcategory Sales]) < Subcategory[Subcategory Sales]
    )
) + 1
```

ฟังก์ชัน EARLIER ถูกใช้เพื่ออ้างถึงค่าคอลัมน์ **Subcategory Sales** _ในบริบทแถวปัจจุบัน_

คุณสามารถปรับปรุงคำจำกัดความคอลัมน์จากการคำนวณให้ดีขึ้นได้โดยใช้ตัวแปรแทนฟังก์ชัน EARLIER ตัวแปร **CurrentSubcategorySales** เก็บค่าคอลัมน์ **Subcategory Sales** _ในบริบทแถวปัจจุบัน_ และนิพจน์ RETURN จะใช้ตัวแปรดังกล่าวภายในบริบทตัวกรองที่ปรับเปลี่ยนแล้ว

```dax
Subcategory Sales Rank =
VAR CurrentSubcategorySales = Subcategory[Subcategory Sales]
RETURN
    COUNTROWS(
        FILTER(
            Subcategory,
            CurrentSubcategorySales < Subcategory[Subcategory Sales]
        )
    ) + 1
```

## <a name="next-steps"></a>ขั้นตอนถัดไป

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับบทความนี้ โปรดดูทรัพยากรต่อไปนี้:

- บทความ [VAR](/dax/var-dax) DAX
- มีคำถามหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)

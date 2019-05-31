---
title: ใช้มุมมองแบบจำลองใน Power BI Desktop
description: ใช้มุมมองแบบจำลองเพื่อดูชุดข้อมูลที่ซับซ้อนในรูปแบบภาพใน Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 1fdb6058a6306f63f53c770812f85ccd9f9113ea
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "65941339"
---
# <a name="modeling-view-in-power-bi-desktop"></a>มุมมองแบบจำลองใน Power BI Desktop

ด้วย**มุมมองแบบจำลอง**ใน **Power BI Desktop** คุณสามารถดู และทำงานกับชุดข้อมูลที่ซับซ้อนที่ประกอบด้วยหลายตารางได้


## <a name="using-modeling-view"></a>ใช้มุมมองแบบจำลอง

เมื่อต้องการเข้าถึงมุมมองแบบจำลอง ให้เลือกไอคอนมุมมองแบบจำลองที่ด้านบนซ้ายของ**Power BI Desktop**ดังที่แสดงในรูปต่อไปนี้

![ไอคอนมุมมองแบบจำลองใน Power BI Desktop](media/desktop-modeling-view/modeling-view_02.png)

## <a name="creating-separate-diagrams"></a>สร้างไดอะแกรมที่แยกต่างหาก

ด้วยมุมมองแบบจำลอง คุณสามารถสร้างไดอะแกรมแบบจำลองของคุณที่ประกอบด้วยชุดย่อยของตารางในแบบจำลองของคุณโดยเฉพาะ สิ่งนี้จะช่วยให้มุมมองชัดเจนยิ่งขึ้นในตารางที่คุณต้องการใช้งาน และให้การทำงานกับชุดข้อมูลที่ซับซ้อน เมื่อต้องการสร้างไดอะแกรมที่มีเฉพาะชุดย่อยของตาราง ให้คลิก **+** ลงชื่อเข้าใช้ถัดจากแท็บ**ตารางทั้งหมด**ที่ด้านล่างของบานหน้าต่าง Power BI Desktop

![สร้างไดอะแกรมใหม่ โดยการคลิกที่สัญลักษณ์ + ในส่วนของแท็บ](media/desktop-modeling-view/modeling-view_03.png)

คุณยังสามารถลากตารางจากรายการ**เขตข้อมูล**ไปยังพื้นผิวไดอะแกรมได้ คลิกขวาที่ตาราง จากนั้น**เพิ่มตารางที่เกี่ยวข้อง**จากเมนูที่ปรากฏขึ้น

![คลิกขวาที่ตาราง และเลือกเพิ่มตารางที่เกี่ยวข้อง](media/desktop-modeling-view/modeling-view_04.png)

เมื่อคุณทำตาม ตารางที่เกี่ยวข้องกับตารางต้นฉบับจะแสดงในไดอะแกรมใหม่ รูปต่อไปนี้แสดงตารางที่เกี่ยวข้องวิธีแสดงหลังจากเลือกตัว**เพิ่มตารางที่เกี่ยวข้อง**ตัวเลือกเมนู

![แสดงตารางที่เกี่ยวข้อง](media/desktop-modeling-view/modeling-view_05.png)

## <a name="setting-common-properties"></a>ตั้งค่าคุณสมบัติทั่วไป

คุณสามารถเลือกวัตถุหลายวัตถุพร้อมกันในมุมมองแบบจำลองได้โดยกดปุ่ม**CTRL**ค้างไว้และคลิกที่ตารางหลายๆ ตารางพร้อมกัน เมื่อคุณเลือกตารางหลายตาราง ตารางจะถูกเน้นไว้ในมุมมองแบบจำลอง เมื่อตารางหลายตารางถูกเน้น การเปลี่ยนแปลงได้ถูกนำไปใช้ในบานหน้าต่าง**คุณสมบัติ**กับตารางที่เลือกทั้งหมด

ตัวอย่าง คุณสามารถเปลี่ยน[โหมดที่เก็บ](desktop-storage-mode.md)สำหรับตารางหลายตารางในมุมมองไดอะแกรมของคุณได้โดยกดปุ่ม**CTRL**ค้าง เลือกตาราง จาก นั้นเปลี่ยนการตั้งค่าโหมดที่เก็บข้อมูลในบานหน้าต่าง**คุณสมบัติ**

![เลือกตารางหลายตาราง โดยกด CTRL แล้วตั้งค่าคุณสมบัติทั่วไปในตารางที่เลือกทั้งหมด](media/desktop-modeling-view/modeling-view_06.png)


## <a name="next-steps"></a>ขั้นตอนถัดไป

บทความต่อไปนี้อธิบายเพิ่มเติมเกี่ยวกับแบบจำลองข้อมูล และยังอธิบายเกี่ยวกับ DirectQuery อย่างละเอียด

* [รวมข้อมูลใน Power BI Desktop (ตัวอย่าง)](desktop-aggregations.md)
* [โมเดลแบบรวมใน Power BI Desktop](desktop-composite-models.md)
* [โหมดที่เก็บข้อมูล ใน Power BI Desktop (ตัวอย่าง)](desktop-storage-mode.md)
* [ความสัมพันธ์แบบกลุ่มต่อกลุ่มใน Power BI Desktop](desktop-many-to-many-relationships.md)


บทความ DirectQuery:

* [การใช้ DirectQuery ใน Power BI](desktop-directquery-about.md)
* [แหล่งข้อมูลที่ได้รับการรองรับโดย DirectQuery ใน Power BI](desktop-directquery-data-sources.md)

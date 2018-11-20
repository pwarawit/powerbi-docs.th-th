---
title: ใช้มุมมองแบบจำลองใน Power BI Desktop (ตัวอย่าง)
description: ใช้มุมมองแบบจำลองเพื่อดูชุดข้อมูลที่ซับซ้อนในรูปแบบภาพใน Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 11/13/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 67a04f1ae1bd5858aa4413c77a6d98ac5a04d32f
ms.sourcegitcommit: 6a6f552810a596e1000a02c8d144731ede59c0c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/14/2018
ms.locfileid: "51620180"
---
# <a name="modeling-view-in-power-bi-desktop-preview"></a>มุมมองแบบจำลองใน Power BI Desktop (ตัวอย่าง)

ด้วย**มุมมองแบบจำลอง**ใน **Power BI Desktop** คุณสามารถดู และทำงานกับชุดข้อมูลที่ซับซ้อนที่ประกอบด้วยหลายตารางได้ ด้วยมุมมองแบบจำลอง คุณสามารถทำสิ่งต่อไปนี้ได้:


## <a name="enabling-the-modeling-view-preview-feature"></a>เปิดใช้งานคุณลักษณะตัวอย่างมุมมองแบบจำลอง

ฟีเจอร์มุมมองแบบจำลองอยู่ในตัวอย่างและต้องเปิดใช้งานใน**Power BI Desktop** เมื่อต้องการเปิดใช้งานมุมมองแบบจำลอง เลือก**ไฟล์ > ตัวเลือกและการตั้งค่า > ตัวเลือก > ฟีเจอร์ตัวอย่าง**แล้วเลือก**มุมมองแบบจำลอง**กล่องกาเครื่องหมายดังที่แสดงในรูปภาพต่อไปนี้

![เปิดใช้งานฟีเจอร์มุมมองแบบจำลองใน Power BI Desktop](media/desktop-modeling-view/modeling-view_01.png)

คุณจะได้รับพร้อมท์ให้งรีสตาร์ต**Power BI Desktop**สำหรับฟีเจอร์ตัวอย่างเพื่อเปิดใช้งาน 

![รีสตาร์ท Power BI Desktop เพื่อเปิดใช้งานฟีเจอร์ตัวอย่าง](media/desktop-modeling-view/modeling-view_01b.png)

## <a name="using-modeling-view"></a>ใช้มุมมองแบบจำลอง

เมื่อต้องการเข้าถึงมุมมองแบบจำลอง ให้เลือกไอคอนมุมมองแบบจำลองที่ด้านบนซ้ายของ**Power BI Desktop**ดังที่แสดงในรูปต่อไปนี้

![ไอคอนมุมมองแบบจำลองใน Power BI Desktop](media/desktop-modeling-view/modeling-view_02.png)

## <a name="creating-separate-diagrams"></a>สร้างไดอะแกรมที่แยกต่างหาก

ด้วยมุมมองแบบจำลอง คุณสามารถสร้างไดอะแกรมแบบจำลองของคุณที่ประกอบด้วยชุดย่อยของตารางในแบบจำลองของคุณโดยเฉพาะ สิ่งนี้จะช่วยให้มุมมองชัดเจนยิ่งขึ้นในตารางที่คุณต้องการใช้งาน และให้การทำงานกับชุดข้อมูลที่ซับซ้อน เมื่อต้องการสร้างไดอะแกรมที่มีเฉพาะชุดย่อยของตาราง ให้คลิก**+** ลงชื่อเข้าใช้ถัดจากแท็บ**ตารางทั้งหมด**ที่ด้านล่างของบานหน้าต่าง Power BI Desktop

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
* [โมเดลแบบรวมใน Power BI Desktop (ตัวอย่าง)](desktop-composite-models.md)
* [โหมดที่เก็บข้อมูล ใน Power BI Desktop (ตัวอย่าง)](desktop-storage-mode.md)
* [ความสัมพันธ์แบบกลุ่ม-ต่อ-กลุ่มใน Power BI Desktop (ตัวอย่าง)](desktop-many-to-many-relationships.md)


บทความ DirectQuery:

* [การใช้ DirectQuery ใน Power BI](desktop-directquery-about.md)
* [แหล่งข้อมูลที่ได้รับการรองรับโดย DirectQuery ใน Power BI](desktop-directquery-data-sources.md)

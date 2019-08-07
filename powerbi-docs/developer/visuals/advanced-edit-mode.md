---
title: โหมดแก้ไขขั้นสูง
description: วิชวล Power BI ที่มีตัวควบคุม UI ขั้นสูง
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 625105aed773bce5cf70932f092faf60ea001c2c
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425562"
---
# <a name="advanced-edit-mode"></a>โหมดการแก้ไขขั้นสูง

วิชวลที่จำเป็นต้องใช้ตัวควบคุม UI ขั้นสูงสามารถรับรองการสนับสนุนในโหมดการแก้ไขขั้นสูง
ถ้าได้รับการสนับสนุนเมื่ออยู่ในโหมดการแก้ไขรายงาน ปุ่ม `Edit` จะปรากฏขึ้นในเมนูของวิชวล
เมื่อคลิกปุ่ม `Edit` EditMode ถูกตั้งค่าเป็น `Advanced`
วิชวลสามารถใช้ค่าสถานะ EditMode เพื่อกำหนดว่าควรแสดงตัวควบคุม UI ดังกล่าวหรือไม่

ตามค่าเริ่มต้น วิชวลไม่สนับสนุนโหมดการแก้ไขขั้นสูง
ถ้าจำเป็นต้องมีลักษณะการทำงานที่แตกต่างกัน ควรระบุไว้อย่างชัดเจนในไฟล์ `capabilities.json` ของวิชวล โดยการตั้งค่าคุณสมบัติ `advancedEditModeSupport`

ค่าที่เป็นไปได้คือ:

- 0-NotSupported

- 1 - SupportedNoAction

- 2 - SupportedInFocus

## <a name="entering-advanced-edit-mode"></a>การเข้าสู่โหมดการแก้ไขขั้นสูง

ปุ่ม `Edit` จะมองเห็นได้ถ้า:

 1- ตั้งค่าคุณสมบัติ `advancedEditModeSupport` ใน capabilities.json เป็น `SupportedNoAction` หรือ `SupportedInFocus`

 2- แสดงผลวิชวลในโหมดการแก้ไขรายงาน

ถ้าคุณสมบัติ `advancedEditModeSupport` หายไปจาก capabilities.json หรือตั้งค่าเป็น `NotSupported` ปุ่ม ' แก้ไข ' จะหายไป

![เข้าสู่โหมดการแก้ไข](./media/edit-mode.png)

เมื่อผู้ใช้คลิก`Edit` วิชวลจะมีการเรียกใช้การอัปเดต () ด้วย EditMode ที่ตั้งค่าเป็น `Advanced`
ตามค่าที่ตั้งไว้ในความสามารถ การดำเนินการต่อไปนี้จะเกิดขึ้น:

* `SupportedNoAction` -ไม่มีการดำเนินการเพิ่มเติมจากโฮสต์
* `SupportedInFocus` -โฮสต์จะเปิดหน้าต่างวิชวลใหม่ในโหมดโฟกัส

## <a name="exiting-advanced-edit-mode"></a>การออกจากโหมดการแก้ไขขั้นสูง

ปุ่ม `Back to report` จะมองเห็นได้ถ้า:

1- ตั้งค่าคุณสมบัติ `advancedEditModeSupport` ใน capabilities.json เป็น `SupportedInFocus`

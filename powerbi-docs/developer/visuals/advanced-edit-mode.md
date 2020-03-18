---
title: โหมดการแก้ไขขั้นสูงในวิชวล Power BI
description: บทความนี้อธิบายถึงวิธีการตั้งค่าการควบคุม UI ขั้นสูงในวิชวล Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 97242883fe90c8f5e115818a24e4bb1c49f69b77
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/14/2020
ms.locfileid: "79380580"
---
# <a name="advanced-edit-mode-in-power-bi-visuals"></a>โหมดการแก้ไขขั้นสูงในวิชวล Power BI

หากคุณต้องการการควบคุม UI ขั้นสูงในวิชวล Power BI คุณสามารถใช้ประโยชน์จากโหมดแก้ไขขั้นสูงได้ เมื่อคุณอยู่ในโหมดแก้ไขรายงาน ให้คุณเลือกปุ่ม **แก้ไข** เพื่อตั้งโหมดแก้ไขเป็น **ขั้นสูง** ภาพสามารถใช้ค่าสถานะ `EditMode` เพื่อพิจารณาว่าควรแสดงการควบคุม UI นี้หรือไม่

ตามค่าเริ่มต้น วิชวลไม่สนับสนุนโหมดการแก้ไขขั้นสูง คุณสามารถระบุสิ่งนี้ได้อย่างชัดเจนในไฟล์ *capabilities.json* ของวิชวลโดยการตั้งค่าคุณสมบัติ `advancedEditModeSupport`

ค่าที่เป็นไปได้คือ:

- `0` - NotSupported

- `1` - SupportedNoAction

- `2` - SupportedInFocus

## <a name="enter-advanced-edit-mode"></a>ป้อนโหมดการแก้ไขขั้นสูง

ปุ่ม**แก้ไข**จะแสดงขึ้นมาถ้า:

* คุณสมบัติ `advancedEditModeSupport` ถูกตั้งค่าในไฟล์ *capabilities.json* เป็น `SupportedNoAction` หรือ `SupportedInFocus`

* แสดงผลวิชวลในโหมดการแก้ไขรายงาน

หากคุณสมบัติ `advancedEditModeSupport` หายไปจากไฟล์ *capabilities.json* หรือตั้งค่าเป็น `NotSupported` ปุ่ม **แก้ไข** จะไม่ปรากฏขึ้น

![เข้าสู่โหมดการแก้ไข](media/advanced-edit-mode/edit-mode.png)

เมื่อคุณเลือก **แก้ไข** วิชวลจะทำการเรียกใช้ update() โดยมีการตั้งค่า EditMode เป็น `Advanced` ขึ้นอยู่กับค่าที่ตั้งไว้ในไฟล์ *capabilities.json* การดำเนินการต่อไปนี้เกิดขึ้น:

* `SupportedNoAction`: ไม่ต้องการการดำเนินการเพิ่มเติมจากโฮสต์
* `SupportedInFocus`: โฮสต์จะเปิดหน้าต่างวิชวลใหม่ในโหมดโฟกัส

## <a name="exit-advanced-edit-mode"></a>ออกจากโหมดการแก้ไขขั้นสูง

ปุ่ม **กลับไปยังรายงาน** จะปรากฏขึ้น ถ้า:

* คุณสมบัติ `advancedEditModeSupport` ถูกตั้งค่าในไฟล์ *capabilities.json* เป็น `SupportedInFocus`

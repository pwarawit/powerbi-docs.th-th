---
title: คุณลักษณะ supportsKeyboardFocus
description: บทความนี้อธิบายวิธีการใช้คุณลักษณะ supportsKeyboardFocus ในวิชวล Power BI และข้อกำหนด
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 04/30/2020
ms.openlocfilehash: c8cf0f4e896b8a44764d1c363c597182f55d30b3
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83276524"
---
# <a name="use-the-supportskeyboardfocus-feature"></a>ใช้คุณลักษณะ supportsKeyboardFocus

บทความนี้อธิบายวิธีการใช้คุณลักษณะ `supportsKeyboardFocus` ในวิชวล Power BI
คุณลักษณะ `supportsKeyboardFocus` อนุญาตให้นำทางจุดข้อมูลของวิชวลโดยใช้แป้นพิมพ์เท่านั้น

หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับการนำทางแป้นพิมพ์สำหรับวิชวล ดู [การนำทางแป้นพิมพ์](../../create-reports/desktop-accessibility-consuming-tools.md#keyboard-navigation)

## <a name="example"></a>ตัวอย่าง:

เปิดวิชวลที่ใช้คุณลักษณะ `supportsKeyboardFocus` เลือกจุดข้อมูลใดๆ ภายในวิชวลและเลือกแท็บ โฟกัสจะย้ายไปยังจุดข้อมูลถัดไปสำหรับแต่ละครั้งที่คุณเลือกแท็บ เลือก enter เพื่อเลือกจุดข้อมูลที่ไฮไลต์

![ตัวอย่าง Supports keyboard focus](./media/supportskeyboardfocus-feature/supports-keyboard-focus-example.png)

## <a name="requirements"></a>ข้อกำหนด

คุณลักษณะนี้จำเป็นต้องใช้ API  v2.1.0 หรือสูงกว่า

คุณลักษณะนี้สามารถนำไปใช้กับวิชวลทั้งหมดยกเว้นวิชวลภาพ

## <a name="usage"></a>การใช้งาน

หากต้องการใช้คุณลักษณะ `supportsKeyboardFocus` ให้เพิ่มรหัสต่อไปนี้ลงในไฟล์ *capabilities.json* ของวิชวลของคุณ
ความสามารถนี้อนุญาตให้วิชวลได้รับโฟกัสผ่านการนำทางแป้นพิมพ์

```json
    {   
            ...
        "supportsKeyboardFocus": true
            ...
    }

```

## <a name="next-steps"></a>ขั้นตอนถัดไป

หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับคุณลักษณะการช่วยสำหรับการเข้าถึงให้ดู [ออกแบบรายงาน Power BI สำหรับความสามารถในการเข้าถึง](../../create-reports/desktop-accessibility-creating-reports.md)

หากต้องการลองพัฒนา Power BI ดู [การพัฒนาวิชวล Power BI](custom-visual-develop-tutorial.md)

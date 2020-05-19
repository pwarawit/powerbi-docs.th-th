---
title: ฟีเจอร์ supportsMultiVisualSelection
description: บทความนี้อธิบายวิธีการใช้ฟีเจอร์ supportsMultiVisualSelection ในวิชวล Power BI และข้อกำหนดของคุณลักษณะ
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 04/30/2020
ms.openlocfilehash: 6ad986308fb82f8191829d29654bb96b55d0fbd0
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83272706"
---
# <a name="use-the-supportsmultivisualselection-feature"></a>ใช้ฟีเจอร์ supportsMultiVisualSelection

ฟีเจอร์ `supportsMultiVisualSelection`ช่วยให้คุณสามารถใช้การเลือกในวิชวลหลายรายการในรายงานได้

## <a name="example"></a>ตัวอย่าง:

ในรายงานที่มีวิชวลมากกว่าหนึ่งรายการ ให้เลือกสองค่าเพื่อให้ค่าเหล่านั้นนำไปใช้กับอื่นๆ ตัวอย่างเช่น ใน [ตัวอย่างการวิเคราะห์การค้าปลีก](../../create-reports/sample-retail-analysis.md) เลือก**Fashions Direct** ในหนึ่งวิชวล เลือก ctrl และเลือก **ม.ค.** ในอีกวิชวลหนึ่ง ในรายงานนั้น การเลือกของคุณจะนำไปใช้กับวิชวลอื่นๆ ที่สนับสนุนการใช้ฟีเจอร์นี้ วิชวลอื่นๆ จะได้รับการกำหนดขอบเขตเป็น **Fashions Direct** และ **ม.ค.**

## <a name="requirements"></a>ข้อกำหนด

ฟีเจอร์นี้ต้องการ API v3.2.0 หรือสูงกว่า

คุณไม่สามารถนำฟีเจอร์นี้ไปใช้กับวิชวลภาพได้ คุณไม่สามารถนำฟีเจอร์นี้ไปใช้กับวิชวลขั้นสูงบางรายการได้ เช่น Key Driver Decomposition Tree วิชวลแบบถามตอบ กล่องข้อความ และแผนภูมิหน้าปัด

## <a name="usage"></a>การใช้งาน

หากต้องการใช้ฟีเจอร์ `supportsMultiVisualSelection` ให้กรอกรหัสต่อไปนี้ลงในไฟล์ `capabilities.json` ของวิชวลของคุณ

```json
    {   
            ...
        "supportsMultiVisualSelection": true
            ...
    }
```

## <a name="next-steps"></a>ขั้นตอนถัดไป

หากต้องการเรียนรู้เกี่ยวกับแนวคิด Power BI ดู [วิชวลใน Power BI](power-bi-visuals-concept.md)

หากต้องการลองพัฒนา Power BI ดู [การพัฒนาวิชวล Power BI](custom-visual-develop-tutorial.md)

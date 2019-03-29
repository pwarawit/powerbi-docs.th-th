---
title: ฉันสามารถใช้ Power BI API ทำอะไรได้บ้าง
description: ฉันสามารถใช้ Power BI API ทำอะไรได้บ้าง
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/25/2018
ms.openlocfilehash: 764718ab86e040509790dd4debbbef25b6079a14
ms.sourcegitcommit: 9f31cd41bd92e398717da5a69a074273e8c6f8a6
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/26/2019
ms.locfileid: "58473786"
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>นักพัฒนาสามารถใช้ Power BI API ทำอะไรได้บ้าง

การใช้ Power BI REST API คุณสามารถสร้างแอพที่ฝังรายงาน Power BI นอกจากนี้ยังช่วยให้คุณสามารถรวมไทล์ Power BI และแดชบอร์ดลงในแอปได้อีกด้วย

ด้วย Power BI REST API คุณสามารถดำเนินการจัดการกับออบเจ็กต์ Power BI เช่น รายงาน ชุดข้อมูล และพื้นที่ทำงาน

ต่อไปนี้เป็นตัวอย่าง สิ่งที่คุณสามารถทำได้ด้วย Power BI API

| **เมื่อต้องการทำสิ่งต่อไปนี้** | **ให้ไปที่** |
| --- | --- |
| ฝังรายงาน แดชบอร์ด และไทล์สำหรับผู้ใช้ Power BI และผู้ใช้ที่ไม่ใช้ Power BI |[วิธีฝังแดชบอร์ด รายงานและไทล์ Power BI ของคุณ](embedding-content.md) |
| ดำเนินการจัดการกับออบเจ็กต์ Power BI |[การอ้างอิง Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/) |

> [!NOTE]
> Power BI API ยังคงอ้างอิงถึงพื้นที่ทำงานของแอปเป็นกลุ่ม การอ้างอิงใดๆ ถึงกลุ่มจะหมายความว่า คุณกำลังทำงานอยู่กับพื้นที่ทำงานของแอป

## <a name="developer-tools"></a>เครื่องมือสำหรับนักพัฒนา

ต่อไปนี้คือ เครื่องมือที่คุณสามารถใช้เพื่อช่วยการพัฒนาสิ่งต่าง ๆ สำหรับ Power BI

คุณสามารถเข้าถึง[เครื่องมือตั้งค่าการฝังตัว](https://aka.ms/embedsetup) เพื่อเริ่มต้นใช้งานได้อย่างรวดเร็ว และดาวน์โหลดแอปพลิเคชันตัวอย่างสำหรับวิธีการฝังเนื้อหา Power BI ได้

เลือกโซลูชันที่เหมาะกับคุณ:

* [การฝังตัวสำหรับลูกค้าของคุณ](embedding.md#embedding-for-your-customers) จะมอบความสามารถในการฝังแดชบอร์ดและรายงานสำหรับผู้ใช้ที่ไม่มีบัญชี Power BI เรียกใช้โซลูชัน[การฝังตัวสำหรับลูกค้าของคุณ](https://aka.ms/embedsetup/AppOwnsData)

* [การฝังตัวสำหรับองค์กรของคุณ](embedding.md#embedding-for-your-organization) ให้คุณสามารถขยายบริการของ Power BI เรียกใช้โซลูชัน[การฝังตัวสำหรับองค์กรของคุณ](https://aka.ms/embedsetup/UserOwnsData)

สำหรับตัวอย่างแบบเต็มของการใช้ JavaScript API คุณสามารถใช้[เครื่องมือ Playground](https://microsoft.github.io/PowerBI-JavaScript/demo) ได้ เครื่องมือนี้คือวิธีที่รวดเร็วเพื่อลองเล่นกับตัวอย่าง Power BI Embedded ชนิดต่าง ๆ กัน คุณยังสามารถรับข้อมูลเพิ่มเติมเกี่ยวกับ JavaScript API โดยไปที่หน้า [PowerBI-JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) ได้

## <a name="github-repositories"></a>ที่เก็บ GitHub

* [ตัวอย่างสำหรับนักพัฒนา Power BI](https://github.com/Microsoft/PowerBI-Developer-Samples)
* [.NET SDK](https://github.com/Microsoft/PowerBI-CSharp)
* [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](http://community.powerbi.com/)

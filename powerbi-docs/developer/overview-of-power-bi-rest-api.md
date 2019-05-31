---
title: ฉันสามารถใช้ Power BI API ทำอะไรได้บ้าง
description: ฉันสามารถใช้ Power BI API ทำอะไรได้บ้าง
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 03/25/2019
ms.openlocfilehash: fd49c69a14d3dac6b1a045f6aba407ec7aac0deb
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "61269469"
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>นักพัฒนาสามารถใช้ Power BI API ทำอะไรได้บ้าง

การใช้ Power BI REST API คุณสามารถสร้างแอปที่รวมกับรายงาน แดชบอร์ด และไทล์ของ Power BI

ด้วย Power BI REST API คุณสามารถดำเนินการจัดการกับออบเจ็กต์ Power BI เช่น รายงาน ชุดข้อมูล และพื้นที่ทำงาน

ต่อไปนี้เป็นตัวอย่าง สิ่งที่คุณสามารถทำได้ด้วย Power BI API

| **เมื่อต้องการเรียนรู้เพิ่มเติม** | **ข้อมูลนี้อ้างอิง** |
|----------------------------------------------------------------------------------|------------------------------------------------------------------------------------|
| ฝังรายงาน แดชบอร์ด และไทล์สำหรับผู้ใช้ Power BI และผู้ที่ไม่ใช้ Power BI | [วิธีการฝัง Power BI แดชบอร์ด รายงาน และไทล์ ](embedding-content.md) |
| ดำเนินการจัดการกับออบเจ็กต์ Power BI | [การอ้างอิง Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/) |
| ขยายเวิร์กโฟลว์ทางธุรกิจที่มีอยู่แล้ว โดยการพุชข้อมูลสำคัญลงในแดชบอร์ด Power BI | [ส่งข้อมูลลงในแดชบอร์ด ](walkthrough-push-data.md) |
| การรับรองความถูกต้องกับ Power BI | [การรับรองความถูกต้องไปยัง Power BI ](get-azuread-access-token.md) |

> [!NOTE]
> Power BI API ยังคงอ้างอิงถึงพื้นที่ทำงานของแอปเป็นกลุ่ม การอ้างอิงใดๆ ถึงกลุ่มจะหมายความว่า คุณกำลังทำงานอยู่กับพื้นที่ทำงานของแอป

## <a name="api-developer-tools"></a>เครื่องมือสำหรับนักพัฒนา API

| เครื่องมือ | คำอธิบาย |  |  |
|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|---|---|
| [เครื่องมือ playground](https://microsoft.github.io/PowerBI-JavaScript/demo) | ประสบการณ์การใช้งานตัวอย่าง Power BI JavaScript API แบบเต็ม เครื่องมือนี้คือ วิธีที่รวดเร็วเพื่อลองเล่นกับตัวอย่าง Power BI Embedded ชนิดต่าง ๆ กันอีกด้วย |  |  |
| [Power BI JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) | เพื่อรับข้อมูลเพิ่มเติมเกี่ยวกับ Power BI JavaScript API |  |  |
| [Postman](https://www.getpostman.com/) | เรียกใช้คำขอ การทดสอบ แก้จุดบกพร่อง ตรวจสอบ เรียกใช้การทดสอบอัตโนมัติและอื่น ๆ |

## <a name="push-data-into-power-bi"></a>ส่งข้อมูลไปยัง Power BI

คุณสามารถใช้ Power BI API เพื่อ[ส่งข้อมูลไปยังชุดข้อมูล ](walkthrough-push-data.md) คุณลักษณะนี้ทำให้คุณสามารถเพิ่มแถวลงในตารางภายในชุดข้อมูลได้ จากนั้น ข้อมูลใหม่จะสะท้อนผลในไทล์บนแดชบอร์ด และในวิชวลภายในรายงานของคุณ

![ตัวอย่างการส่งข้อมูล](media/what-can-you-do/powerbi-push-data.png)

## <a name="github-repositories"></a>ที่เก็บ GitHub

* [ตัวอย่างสำหรับนักพัฒนา Power BI](https://github.com/Microsoft/PowerBI-Developer-Samples)
* [.NET SDK](https://github.com/Microsoft/PowerBI-CSharp)
* [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [การพุชข้อมูลลงในชุดข้อมูล](walkthrough-push-data.md)
* [พัฒนาภาพแบบกำหนดเองของ Power BI](custom-visual-develop-tutorial.md)
* [การอ้างอิง REST API BI power](rest-api-reference.md)
* [Power BI REST APIs](https://docs.microsoft.com/rest/api/power-bi/)

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](http://community.powerbi.com/)

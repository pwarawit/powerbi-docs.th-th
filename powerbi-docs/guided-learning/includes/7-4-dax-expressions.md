---
ms.openlocfilehash: f22c12ec0ad5bd413f3658704132143c878df1aa
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "73800174"
---
การใช้**ตัวแปร**คือจุดที่มีประสิทธิภาพของนิพจน์ DAX

![](media/7-4-dax-expressions/dax-variables_1.png)

คุณสามารถกำหนดตัวแปรได้ทุกที่ในนิพจน์ DAX โดยใช้ไวยากรณ์ต่อไปนี้:

    VARNAME = RETURNEDVALUE

ตัวแปรสามารถเป็นชนิดข้อมูลใดก็ได้ รวมถึงเป็นได้ทั้งตาราง

โปรดจำไว้ว่าเมื่อคุณอ้างอิงตัวแปรในนิพจน์ DAX ทุกครั้ง Power BI จะต้องคำนวณค่าของตัวเองใหม่ให้ตรงตามข้อกำหนดของคุณ เนื่องด้วยเหตุนี้ การหลีกเลี่ยงตัวแปรที่ซ้ำกันในฟังก์ชันของคุณจึงเป็นสิ่งที่ดี

> เนื้อหาวิดีโอโดย [Alberto Ferrari, SQBI](https://www.sqlbi.com/learning-dax)
> 
> 


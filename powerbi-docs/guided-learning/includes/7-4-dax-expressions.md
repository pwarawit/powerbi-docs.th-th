---
ms.openlocfilehash: 5c2b254f20bd1eba97840a464a1b554cc4fe1238
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "61273604"
---
การใช้**ตัวแปร**คือจุดที่มีประสิทธิภาพของนิพจน์ DAX

![](media/7-4-dax-expressions/dax-variables_1.png)

คุณสามารถกำหนดตัวแปรได้ทุกที่ในนิพจน์ DAX โดยใช้ไวยากรณ์ต่อไปนี้:

    VARNAME = RETURNEDVALUE

ตัวแปรสามารถเป็นชนิดข้อมูลใดก็ได้ รวมถึงเป็นได้ทั้งตาราง

โปรดจำไว้ว่าเมื่อคุณอ้างอิงตัวแปรในนิพจน์ DAX ทุกครั้ง Power BI จะต้องคำนวณค่าของตัวเองใหม่ให้ตรงตามข้อกำหนดของคุณ เนื่องด้วยเหตุนี้ การหลีกเลี่ยงตัวแปรที่ซ้ำกันในฟังก์ชันของคุณจึงเป็นสิ่งที่ดี

> เนื้อหาวิดีโอโดย [Alberto Ferrari, SQBI](http://www.sqlbi.com/learning-dax)
> 
> 


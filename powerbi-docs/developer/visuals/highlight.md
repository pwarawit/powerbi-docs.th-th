---
title: การไฮไลต์
description: การเลือกจุดข้อมูลที่ไฮไลต์ใน Power BI Visuals
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 4ff2187dc99d4e790b08c11f55a37e31e85693ad
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/23/2019
ms.locfileid: "71193985"
---
# <a name="highlight-data-points-in-power-bi-visuals"></a>ไฮไลต์จุดข้อมูลใน Power BI Visuals

โดยค่าเริ่มต้นเมื่อใดก็ตามที่มีการเลือกองค์ประกอบ อาร์เรย์ `values` ในวัตถุ `dataView` จะถูกกรองให้เป็นเพียงค่าที่เลือกเท่านั้น ซึ่งจะทำให้วิชวลอื่น ๆ ทั้งหมดในหน้าแสดงเป็นเพียงข้อมูลที่เลือกเท่านั้น

![ไฮไลต์ `dataview` ในลักษณะตามค่าเริ่มต้น](./media/highlight-dataview.png)

หากคุณตั้งค่าคุณสมบัติ `supportsHighlight` ใน `capabilities.json` เป็น `true` คุณจะได้รับอาร์เรย์ `values` แบบไม่มีการกรองเต็มรูปแบบพร้อมกับอาร์เรย์ `highlights` อาร์เรย์ `highlights` จะมีความยาวเท่ากับอาร์เรย์ค่าและค่าที่ไม่ได้เลือกจะถูกตั้งค่าเป็น `null` เมื่อเปิดใช้งานคุณสมบัตินี้แล้ว จึงเป็นความรับผิดชอบของวิชวลในการไฮไลต์ข้อมูลที่เหมาะสมโดยการเปรียบเทียบอาร์เรย์ `values` กับอาร์เรย์ `highlights`

![ไฮไลต์ `dataview` ในลักษณะแบบ supportshighlight](./media/highlight-dataview-supports.png)

ในตัวอย่าง คุณจะสังเกตเห็นแถบ 1 แถบที่ถูกเลือก และเป็นเฉพาะค่าในอาร์เรย์ไฮไลต์ นอกจากนี้ สิ่งสำคัญคือต้องทราบว่าอาจมีตัวเลือกหลายตัวและไฮไลต์บางส่วนอีกด้วย มีค่าตัวเลขที่สอดคล้องกันในค่าและอาร์เรย์ไฮไลต์จะมีอยู่ แต่แตกต่างกัน

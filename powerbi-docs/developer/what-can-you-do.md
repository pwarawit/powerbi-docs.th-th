---
title: นักพัฒนาสามารถทำอะไรกับ Power BI ได้บ้าง
description: Power BI มีหลากหลายตัวเลือกสำหรับนักพัฒนา ซึ่งมีช่วงตั้งแต่การฝังเพื่อกำหนดวิชวลเองและการสตรีมชุดข้อมูล
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 07/20/2017
ms.author: maghan
ms.openlocfilehash: b310562ac31694f398a659018743b8fa7aa46e35
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/30/2018
---
# <a name="what-can-developers-do-with-power-bi"></a>นักพัฒนาสามารถทำอะไรกับ Power BI ได้บ้าง
Power BI มีหลากหลายตัวเลือกสำหรับนักพัฒนา ซึ่งมีช่วงตั้งแต่การฝังเพื่อกำหนดวิชวลเองและการสตรีมชุดข้อมูล

## <a name="embedding"></a>การฝัง
บริการ Power BI และ Power BI ที่ฝังใน Azure จะมาพร้อมกันเพื่อเสนอ API เดียวสำหรับการฝังแดชบอร์ดและรายงานของคุณ ซึ่งหมายความว่า คุณจะมี API surface ชุดความสามารถ และการเข้าถึงคุณลักษณะ Power BI ล่าสุด – เช่น แดชบอร์ด เกตเวย์ และพื้นที่ทำงานของแอป – เมื่อมีการฝังเนื้อหาของคุณ สำหรับข้อมูลเพิ่มเติม ดูที่[การฝังด้วย Power BI](embedding.md)

![](media/what-can-you-do/powerbi-embed-sample.png)

## <a name="custom-visuals"></a>วิชวลแบบกำหนดเอง
วิชวลแบบกำหนดเองจะช่วยให้คุณสามารถสร้างภาพของคุณเองสำหรับการใช้งานภายในรายงาน Power BI วิชวลแบบกำหนดเองจะถูกเขียนใน TypeScript ซึ่งคือเซตใหญ่ของ JavaScript ที่สนับสนุนคุณลักษณะขั้นสูงบางอย่างและสิทธิ์การเข้าถึงฟังก์ชันการทำงาน ES6/ES7 การกำหนดลักษณะวิชวลจะได้รับการจัดการโดยใช้ cascading styles sheets (css). เพื่อความสะดวกของคุณ เราจึงใช้ Less pre-compiler ที่สนับสนุนคุณลักษณะขั้นสูงบางอย่าง เช่น nesting, variables, mixins, conditions, loops และอื่น ๆ ถ้าคุณไม่ต้องการใช้คุณลักษณะเหล่านั้น คุณเพียงแค่เขียน plain css ลงใน less file

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับวิธีการพัฒนาและเผยแพร่วิชวลแบบกำหนดเอง ดูที่การ[เผยแพร่วิชวลแบบกำหนดเองไปยัง Office store](office-store.md)

![](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>ส่งข้อมูลไปยัง Power BI
คุณสามารถใช้ API Power BI เพื่อส่งข้อมูลไปยังชุดข้อมูล ซึ่งทำให้คุณสามารถเพิ่มแถวลงในตารางภายในชุดข้อมูลได้ จากนั้น ข้อมูลใหม่จะสามารถสะท้อนผลในไทล์บนแดชบอร์ด และในวิชวลภายในรายงานของคุณ

สำหรับข้อมูลเพิ่มเติม ดูที่การ[ส่งข้อมูลไปยังแดชบอร์ด](walkthrough-push-data.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[ฝังด้วย Power BI](embedding.md)  
[วิธีการย้ายเนื้อหาคอลเลกชันพื้นที่ทำงานแบบฝัง Power BI ไปยัง Power BI](migrate-from-powerbi-embedded.md)  
[JavaScript API Git repo](https://github.com/Microsoft/PowerBI-JavaScript)  
[Power BI C# Git repo](https://github.com/Microsoft/PowerBI-CSharp)  
[เผยแพร่วิชวลแบบกำหนดเองไปยัง Office store](office-store.md)  
[Power BI Visuals Git repo](https://github.com/Microsoft/PowerBI-visuals)  
[ตัวอย่างการฝัง JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[Power BI Premium whitepaper](https://aka.ms/pbipremiumwhitepaper)  
คุณมีคำถามเพิ่มเติมหรือไม่ [ ลองเข้าร่วมกับชุมชน Power BI ](http://community.powerbi.com/)


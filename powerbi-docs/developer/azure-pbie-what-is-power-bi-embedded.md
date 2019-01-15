---
title: Azure Power BI Embedded และ embedded analytics | Microsoft Docs คืออะไร
description: Power BI Embedded มีหน้าที่เป็นเครื่องมือวิเคราะห์แบบฝังตัวเพื่อลดความซับซ้อนของวิธีการใช้ความจุ Power BI โดย ISV และนักพัฒนาซอฟต์แวร์ ช่วยให้พวกเขาสามารถเพิ่มภาพ รายงาน และแดชบอร์ดที่สวยงามลงในแอปพลิเคชันของพวกเขาได้อย่างรวดเร็ว เรียนรู้วิธีการใช้ซอฟต์แวร์การวิเคราะห์แบบฝังตัว, เครื่องมือการวิเคราะห์แบบฝังตัวหรือเครื่องมือข่าวกรองธุรกิจแบบฝังตัวโดยใช้ Power BI แบบฝังตัว
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: power-bi-embedded
ms.subservice: ''
ms.devlang: csharp, javascript
ms.topic: overview
ms.custom: seodec18
ms.date: 12/10/2018
ms.openlocfilehash: 175e4409022192b7e34c4670b2738fc56166a122
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54288991"
---
# <a name="what-is-power-bi-embedded-in-azure"></a>Power BI Embedded ใน Azure คืออะไร

Power BI Embedded มีจุดมุ่งหมายเพื่อลดความซับซ้อนของวิธีการใช้ความจุ Power BI โดย ISV และนักพัฒนาซอฟต์แวร์ด้วยการวิเคราะห์แบบฝังตัว Power BI Embedded ช่วยลดความสามารถของ Power BI ด้วยการช่วยให้คุณสามารถเพิ่มภาพ รายงาน และแดชบอร์ดที่สวยงามลงในแอปพลิเคชันของคุณได้อย่างรวดเร็ว คล้ายกับแอปพลิเคชันที่สร้างขึ้นจาก Microsoft Azure จะใช้บริการ เช่น Machine Learning และ IoT ด้วยการสำรวจข้อมูลที่ใช้งานง่ายในแอปของพวกเขา ISV จะช่วยให้ลูกค้าสามารถตัดสินใจบริบทบนพื้นฐานการใช้ข้อมูลเป็นหลักได้อย่างรวดเร็ว

> [!VIDEO https://www.youtube.com/embed/iEHfUuoZseo]

ในเดือนพฤษภาคมปี 2017 เราได้ประกาศถึงการหลอมรวมบริการ Power BI และ Power BI Embedded การหลอมรวมมอบพื้นผิว API หนึ่งชนิด ชุดความสามารถที่สอดคล้องกัน และการเข้าถึงคุณลักษณะล่าสุดในบริการทั้งคู่ นอกจากนี้ เรายังได้นำเสนอรูปแบบการกำหนดราคาตามความจุเพื่อลดความยุ่งยากในวิธีการใช้ Power BI

เนื่องจาก Power BI Embedded ทำให้ ISV และนักพัฒนาซอฟต์แวร์ได้เพิ่มความยืดหยุ่นในการฝัง intelligence ให้แอปโดยใช้ Power BI APIs ISV และนักพัฒนาซอฟต์แวร์สามารถใช้ประโยชน์จากความพยายามในการพัฒนาที่ลดลงเพื่อให้สามารถเข้าถึงตลาดได้เร็วขึ้นและสร้างความแตกต่างด้วยการผสมผสานเครื่องมือวิเคราะห์ระดับโลกของ Microsoft เข้ากับแอปของพวกเขา ในทำนองเดียวกัน นักพัฒนาซอฟต์แวร์สามารถทุ่มเทเวลาในการแก้ปัญหาเพื่อตอบสนองความต้องการของลูกค้า แทนการพัฒนาคุณลักษณะการวิเคราะห์ด้วยภาพ นอกจากนี้ Power BI Embedded ยังช่วยให้คุณสามารถทำงานได้ภายในสภาพแวดล้อมการพัฒนาที่คุ้นเคย เช่น Visual Studio และ Azure ที่คุณใช้อยู่แล้ว

คุณมีแอปที่มีเนื้อหา Power BI แบบฝังโดยใช้ Power BI Premium อยู่แล้วหรือไม่ หากคุณเป็น ISV หรือนักพัฒนาซอฟต์แวร์ที่กำลังส่งมอบแอป หรือเป็นองค์กรที่ใช้แอปพลิเคชันเหล่านี้คุณจะไม่ต้องดำเนินการใดๆ คุณและลูกค้าของคุณสามารถใช้แอปเหล่านนี้ได้ต่อเนื่องโดยไม่หยุดชะงัก หากแอปพลิเคชันที่คุณมีอยู่สร้างขึ้นจากคอลเลกชันพื้นที่ทำงานของ Power BI และคุณสนใจที่จะใช้ประโยชน์จากพื้นผิว API ที่ผสานรวมอยู่และ SKUs Azure แบบใหม่ที่กำหนดราคาตามความจุ ให้ไปที่เอกสารคู่มือการโยกย้าย

## <a name="comparing-power-bi-embedded-with-power-bi-premium"></a>เปรียบเทียบ Power BI Embedded กับ Power BI Premium

**Power BI Embedded** เหมาะสำหรับผู้จัดจำหน่ายซอฟต์แวร์อิสระ (ISV) และนักพัฒนาซอฟต์แวร์ที่สร้างแอปพลิเคชันสำหรับลูกค้าของตน ซึ่งสามารถใช้เป็นบริการ business intelligence ของบุคคลที่สามที่ช่วยให้คุณเห็นภาพข้อมูลของแอปพลิเคชันแทนที่จะสร้างบริการด้วยตัวคุณเอง Power BI Embedded เป็นโซลูชันการวิเคราะห์รูปแบบบริการแพลตฟอร์มบนคลาวด์ (PaaS) ซึ่งนักพัฒนาซอฟต์แวร์สามารถฝังรายงานและแดชบอร์ดไว้ในแอปพลิเคชันสำหรับลูกค้าของตนได้ **Power BI Premium** เป็นโซลูชันการวิเคราะห์รูปแบบบริการซอฟต์แวร์บนคลาวด์ (SaaS) ที่ช่วยให้องค์กรของคุณสามารถดูข้อมูลทางธุรกิจที่สำคัญที่สุดได้ภายในหน้าจอเดียว 

[Power BI Embedded](https://azure.microsoft.com/pricing/details/power-bi-embedded/) เป็นคุณลักษณะการชำระค่าบริการแบบใช้เท่าไรจ่ายเท่านั้น (pay-as-you-go) ขณะที่ [Power BI Premium](https://powerbi.microsoft.com/calculator/) ต้องเสียค่าธรรมเนียมเป็นรายเดือน คุณสามารถดู [วิดีโอ](https://www.youtube.com/watch?v=0y2oJikC6Xc&t=0s&list=PLv2BtOtLblH1dQPV49Ni12olDcUoW-GEl&index=3) นี้เพื่อเรียนรู้เพิ่มเติมเกี่ยวกับวิธีเปรียบเทียบ

## <a name="easy-to-use-tools"></a>เครื่องมือที่ง่ายต่อการใช้งาน

Power BI Embedded ช่วยให้คุณสามารถมุ่งเน้นสิ่งที่คุณทำได้ดีที่สุด: สร้างแอปพลิเคชันที่ยอดเยี่ยม คุณสามารถจัดการและพัฒนาด้วย Power BI Embedded โดยใช้เครื่องมือและทักษะที่คุณมีอยู่แล้ว

* [**พอร์ทัล Azure**](https://portal.azure.com/): โปรแกรมประยุกต์บนเว็บสำหรับจัดการบริการ Azure ทั้งหมด
* [**Visual Studio Code**](https://code.visualstudio.com/docs): ฟรี ดาวน์โหลดได้ โอเพ่นซอร์ส โปรแกรมแก้ไขโค้ดสำหรับ Windows, macOS และ Linux ที่สนับสนุนส่วนขยาย
* [**Power BI Desktop**](https://powerbi.microsoft.com/desktop/): เป็นเครื่องมือฟรี ที่สามารถดาวน์โหลดได้เพื่อสร้างรายงานแบบโต้ตอบที่หลากหลายและมีการวิเคราะห์ด้วยภาพ

Power BI Embedded ช่วยในการพัฒนาด้วยภาษาใดก็ได้โดยใช้ REST API

## <a name="engage-with-the-power-bi-engineering-team"></a>มีส่วนร่วมกับทีมวิศวกรรมของ Power BI

* [ชุมชน](https://community.powerbi.com/): ถามคำถามเกี่ยวกับ Power BI
* [แนวคิด Power BI](https://ideas.powerbi.com): คำขอและลงคะแนนสำหรับคุณลักษณะ
* [Reddit](https://www.reddit.com/r/PowerBI/): พูดคุยเกี่ยวกับ Power BI

## <a name="next-steps"></a>ขั้นตอนถัดไป

ดู[หน้าการกำหนดราคา](https://azure.microsoft.com/pricing/details/power-bi-embedded/) สำหรับรายละเอียดโหนดของความจุ

หากต้องการสร้างความจุ Power BI Embedded ในพอร์ทัล Azure ดู[สร้างความจุ Power BI Embedded ในพอร์ทัล Azure](azure-pbie-create-capacity.md)

ในการเริ่มต้นฝังเนื้อหา Power BI ในแอปพลิเคชันของคุณ โปรดดูที่[วิธีฝังแดชบอร์ด รายงาน และไทล์ใน Power BI ของคุณ](https://powerbi.microsoft.com/documentation/powerbi-developer-embedding-content/)

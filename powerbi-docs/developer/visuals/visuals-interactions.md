---
title: การโต้ตอบกับวิชวลในวิชวล Power BI
description: บทความนี้อธิบายถึงวิธีการตรวจสอบว่าวิชวล Power BI ควรอนุญาตให้มีการโต้ตอบกับวิชวลหรือไม่
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: f2fb2d451deb63b5e9c08472654e28d0e1a469db
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/03/2019
ms.locfileid: "70236622"
---
# <a name="visual-interactions-in-power-bi-visuals"></a>การโต้ตอบกับวิชวลในวิชวล Power BI

วิชวลสามารถคิวรีค่าของสถานะ `allowInteractions` ได้ซึ่งบ่งชี้ว่าวิชวลควรอนุญาตให้มีการโต้ตอบกับวิชวลหรือไม่ ตัวอย่างเช่น วิชวลมีการโต้ตอบระหว่างการดูหรือแก้ไขรายงาน แต่ไม่สามารถโต้ตอบได้เมื่อดูวิชวลในแดชบอร์ด การโต้ตอบเหล่านี้คือ *การคลิก*, *การแพน*, *การซูม*, *การเลือก* และอื่น ๆ 

> [!NOTE]
> คุณควรเปิดใช้งานคำแนะนำเครื่องมือในทุกสถานการณ์โดยไม่คำนึงว่ามีการระบุเป็นสถานะใด

ค่าสถานะ `allowInteractions` จะถูกส่งผ่านค่าเป็นบูลีนในระหว่างการเตรียมใช้งานของวิชวลในฐานะสมาชิกของอินเทอร์เฟซ IVisualHost

ในสถานการณ์สมมติของ Power BI ใดก็ตามที่ต้องการให้วิชวลไม่สามารถโต้ตอบได้ (ตัวอย่างเช่น ไทล์แดชบอร์ด) `allowInteractions` จะถูกตั้งค่าเป็น `false` มิฉะนั้น (ตัวอย่างเช่น รายงาน) `allowInteractions` จะถูกตั้งค่าเป็น `true`

สำหรับข้อมูลเพิ่มเติม ให้ดู [ที่เก็บวิชวล SampleBarChart](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/59a47935d8f5272ce145fe804193599ddb7e2001)

```typescript
   ...
   let allowInteractions = options.host.allowInteractions;
   bars.on('click', function(d) {
       if (allowInteractions) {
           selectionManager.select(d.selectionId);
           ...
       }
   });
```

---
title: การโต้ตอบวิชวล
description: วิธีการตรวจสอบการแสดงผลด้วยภาพ Power BI ควรอนุญาตให้มีการโต้ตอบวิชวล
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 739e59c6da3c1e464e0462a928bc4f33ea0d01f8
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424504"
---
# <a name="visuals-interactions"></a>การโต้ตอบวิชวล

วิชวลสามารถสอบถามค่าสถานะ 'allowInteractions' ที่ระบุว่าภาพควรอนุญาตให้มีการโต้ตอบกับภาพหรือไม่
ตัวอย่างเช่น วิชวลจะโต้ตอบระหว่างการดูหรือแก้ไขรายงานแต่ไม่โต้ตอบเมื่อดูในแดชบอร์ด
การโต้ตอบเหล่านี้จะได้รับการคลิก แพน ซูม การเลือก และอื่น ๆ
โปรดทราบว่าคำแนะนำเครื่องมือควรเปิดใช้งานในทุกสถานการณ์ไม่ว่าจะเป็นค่าสถานะนี้หรือไม่ก็ตาม

ค่าสถานะ 'allowInteractions' จะถูกส่งผ่านเป็นบูลีนในระหว่างการเตรียมใช้งานของวิชวลในฐานะสมาชิกของอินเทอร์เฟซ IVisualHost

ในสถานการณ์สมมติ Power BI ใด ๆ ที่จำเป็นต้องใช้การแสดงผลด้วยภาพที่ไม่เป็นแบบโต้ตอบ (ตัวอย่างเช่น ไทล์แดชบอร์ด) - สถานะ 'allowInteractions' จะถูกตั้งค่าเป็น false
มิฉะนั้น (ตัวอย่างเช่น รายงาน) 'allowInteractions' จะได้รับการตั้งค่าเป็น true

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

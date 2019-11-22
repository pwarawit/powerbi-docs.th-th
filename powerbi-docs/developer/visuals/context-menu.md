---
title: ความสามารถและคุณสมบัติของวิชวล Power BI
description: บทความนี้อธิบายความสามารถและคุณสมบัติของวิชวล Power BI
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 206f1aec7c76b00b6f725d8469eb3e483a01c653
ms.sourcegitcommit: f7b28ecbad3e51f410eff7ee4051de3652e360e8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/13/2019
ms.locfileid: "74061787"
---
# <a name="add-context-menu-to-power-bi-visual"></a>เพิ่มเมนูบริบทไปยัง Power BI Visual

คุณสามารถใช้ `selectionManager.showContextMenu()`กับพารามิเตอร์ `selectionId`และตำแหน่ง (เป็นวัตถุ `{x:, y:}`) เพื่อให้ Power BI แสดงเมนูบริบทสำหรับการแสดงผลด้วยภาพของคุณได้

> [!IMPORTANT]
> `selectionManager.showContextMenu()`ได้รับการแนะนำใน Visuals API 1.7.0

โดยทั่วไปแล้วจะถูกเพิ่มเป็นการ "คลิกขวา" ที่เหตุการณ์ (หรือ "แตะ" สำหรับอุปกรณ์สัมผัส) ที่มีการเพิ่มเมนูบริบทในตัวอย่าง BarChart สำหรับการอ้างอิง:

```typescript
    public update(options: VisualUpdateOptions) {
        //...
        //handle context menu
        this.svg.on('contextmenu', () => {
            const mouseEvent: MouseEvent = d3.event as MouseEvent;
            const eventTarget: EventTarget = mouseEvent.target;
            let dataPoint = d3.select(eventTarget).datum();
            this.selectionManager.showContextMenu(dataPoint? dataPoint.selectionId : {}, {
                x: mouseEvent.clientX,
                y: mouseEvent.clientY
            });
            mouseEvent.preventDefault();
        });
```

---
title: ความสามารถและคุณสมบัติของวิชวล Power BI
description: บทความนี้อธิบายความสามารถและคุณสมบัติของวิชวล Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 7d24ea77fd73ca6a83176d1b8560c88fa98a8d6b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "79380766"
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

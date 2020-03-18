---
title: ความสามารถและคุณสมบัติของวิชวล Power BI
description: บทความนี้อธิบายความสามารถและคุณสมบัติของวิชวล Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: 1e2fbe3288e5dbb759a56ad1c299db2e277408b2
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/14/2020
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

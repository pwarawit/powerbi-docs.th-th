---
title: utils การโต้ตอบวิชวลของ Power BI
description: บทความนี้อธิบายวิธีการเพิ่มการเลือกลงในวิชวลของ Power BI โดยใช้ utils การโต้ตอบ
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: be7a708dfcc6ebc40c62a1a9075e2cbf134363b1
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/04/2020
ms.locfileid: "76818697"
---
# <a name="microsoft-power-bi-visuals-interactivity-utils"></a>utils การโต้ตอบวิชวลของ Microsoft Power BI

InteractiveivityUtils เป็นชุดของฟังก์ชันและคลาสเพื่อให้ง่ายต่อการใช้งานการเลือกข้ามและการกรองข้ามสำหรับวิชวลแบบกำหนดเองของ Power BI

## <a name="installation"></a>การติดตั้ง

> [!NOTE]
> หากคุณยังคงใช้ powerbi-visuals-tools เวอร์ชันเก่าต่อไป (หมายเลขเวอร์ชันน้อยกว่าที่ 3.x.x) ให้ติดตั้งเครื่องมือเวอร์ชันใหม่ (3.x.x)

> [!IMPORTANT]
> การอัปเดตยูทิลิตี้การโต้ตอบใหม่จะรองรับเฉพาะเครื่องเวอร์ชันล่าสุดเท่านั้น [อ่านเพิ่มเติมเกี่ยวกับวิธีการอัปเดตโค้ดวิชวลของคุณเพื่อใช้กับเครื่องมือล่าสุด](migrate-to-new-tools.md)

หากต้องการติดตั้งแพ็คเกจ คุณควรเรียกใช้คำสั่งต่อไปนี้ในไดเรกทอรีด้วยวิชวลของแบบกำหนดเอง

```bash
npm install powerbi-visuals-utils-interactivityutils --save
```

คุณอาจต้องติดตั้งเวอร์ชัน 3.0 ขึ้นไป```powerbi-models```เพื่อแก้ไขปัญหาการอ้างอิง

```bash
npm install powerbi-models --save
```

หากต้องการใช้ยูทิลิตี้การโต้ตอบ คุณต้องนำเข้าคอมโพเนนต์ที่จำเป็นในโค้ดต้นฉบับของวิชวล

```typescript
import { interactivitySelectionService } from "powerbi-visuals-utils-interactivityutils";
```

### <a name="including-css-artifacts-to-the-custom-visual"></a>รวมถึงวัตถุ CSS กับวิชวลแบบกำหนดเอง

หากต้องการใช้แพ็คเกจกับวิชวลแบบกำหนดเอง คุณควรนำเข้าไฟล์ CSS ไปยังไฟล์ `your.less`  ดังนี้

`node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css`

ด้วยเหตุนี้คุณจะมีโครงสร้างไฟล์ดังต่อไปนี้

```less
@import (less) "node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css";
```

> [!NOTE]
> คุณควรนำเข้าไฟล์ css เป็นไฟล์ .less เนื่องจากเครื่องมือวิชวลของ Power BI ครอบคลุมกฎ CSS ภายนอก

## <a name="usage"></a>การใช้งาน

### <a name="define-interface-for-data-points"></a>กำหนดอินเทอร์เฟซสำหรับจุดข้อมูล

โดยทั่วไปจุดข้อมูลประกอบด้วยตัวเลือกและค่าต่างๆ อินเทอร์เฟซจะขยายอินเทอร์เฟซ `SelectableDataPoint` `SelectableDataPoint` มีคุณสมบัติดังนี้

```typescript
  /** Flag for identifying that data point was selected */
  selected: boolean;
  /** Identity for identifying the selectable data point for selection purposes */
  identity: powerbi.extensibility.ISelectionId;
  /**
   * A specific identity for when data points exist at a finer granularity than
   * selection is performed.  For example, if your data points should select based
   * only on series even if they exist as category/series intersections.
   */
  specificIdentity?: powerbi.extensibility.ISelectionId;
```

ขั้นตอนแรกของการใช้ยูทิลิตี้การโต้ตอบคือการสร้างอินสแตนซ์ของยูทิลิตี้การโต้ตอบ และบันทึกออบเจ็กต์เป็นคุณสมบัติของวิชวล

```typescript
export class Visual implements IVisual {
  // ...
  private interactivity: interactivityBaseService.IInteractivityService<VisualDataPoint>;
  // ...
  constructor(options: VisualConstructorOptions) {
      // ...
      this.interactivity = interactivitySelectionService.createInteractivitySelectionService(this.host);
      // ...
  }
}
```

```typescript
import { interactivitySelectionService } from "powerbi-visuals-utils-interactivityutils";

export interface VisualDataPoint extends interactivitySelectionService.SelectableDataPoint {
    value: powerbi.PrimitiveValue;
}
```

ขั้นตอนที่สองคือการขยายคลาสการทำงานพื้นฐาน ดังนี้

> [!NOTE]
> BaseBehavior แนะนำใน [utils การโต้ตอบเวอร์ชัน 5.6.x](https://www.npmjs.com/package/powerbi-visuals-utils-interactivityutils/v/5.6.0) หากคุณใช้เวอร์ชันเก่า ให้สร้างคลาสลักษณะการทำงานจากตัวอย่างด้านล่าง (คลาส `BaseBehavior` เหมือนกัน) ดังนี้

กำหนดอินเทอร์เฟซสำหรับตัวเลือกของคลาสลักษณะการทำงาน

```typescript
import { SelectableDataPoint } from "./interactivitySelectionService";

import {
    IBehaviorOptions,
    BaseDataPoint
} from "./interactivityBaseService";

export interface BaseBehaviorOptions<SelectableDataPointType extends BaseDataPoint> extends IBehaviorOptions<SelectableDataPointType> {
    /** D3 selection object of main elements on the chart */
    elementsSelection: Selection<any, SelectableDataPoint, any, any>;
    /** D3 selection object of some element on backgroup to hadle click of reset selection */
    clearCatcherSelection: d3.Selection<any, any, any, any>;
}
```

กำหนดคลาสสำหรับ `visual behavior` คลาสจะรับผิดชอบในการจัดการ `click`, กิจกรรมของเม้าส์ `contextmenu`
เมื่อคลิกองค์ประกอบข้อมูล จากนั้นวิชวลจะใช้ตัวจัดการการเลือกเพื่อเลือกจุดข้อมูล หากผู้ใช้คลิกที่องค์ประกอบพื้นหลังของวิชวล จะเป็นการเรียกใช้ตัวจัดการล้างการเลือก และคลาสจะมีวิธีการที่สอดคล้องกันดังนี้ `bindClick`, `bindClearCatcher`, `bindContextMenu`

```typescript
export class Behavior<SelectableDataPointType extends BaseDataPoint> implements IInteractiveBehavior {
    /** D3 selection object of main elements on the chart */
    protected options: BaseBehaviorOptions<SelectableDataPointType>;
    protected selectionHandler: ISelectionHandler;

    protected bindClick() {
      // ...
    }

    protected bindClearCatcher() {
      // ...
    }

    protected bindContextMenu() {
      // ...
    }

    public bindEvents(
        options: BaseBehaviorOptions<SelectableDataPointType>,
        selectionHandler: ISelectionHandler): void {
      // ...
    }

    public renderSelection(hasSelection: boolean): void {
      // ...
    }
}
```

หรือคุณขยายคลาส `BaseBehavior` ดังนี้

```typescript
import powerbi from "powerbi-visuals-api";
import { interactivitySelectionService, baseBehavior } from "powerbi-visuals-utils-interactivityutils";

export interface VisualDataPoint extends interactivitySelectionService.SelectableDataPoint {
    value: powerbi.PrimitiveValue;
}

export class Behavior extends baseBehavior.BaseBehavior<VisualDataPoint> {
  // ...
}
```

หากต้องการจัดการคลิกในองค์ประกอบ ให้ใช้วิธีการ `on` ของตัวเลือก D3 (สำหรับ elementsSelection และ clearCatcherSelection ด้วยเช่นกัน)

```typescript
protected bindClick() {
  const {
      elementsSelection
  } = this.options;

  elementsSelection.on("click", (datum) => {
      const mouseEvent: MouseEvent = getEvent() as MouseEvent || window.event as MouseEvent;
      mouseEvent && this.selectionHandler.handleSelection(
          datum,
          mouseEvent.ctrlKey);
  });
}
```

เพิ่มตัวจัดการสำหรับวิธีการ`contextmenu`กิจกรรมที่เรียกใช้`showContextMenu`ของตัวจัดการการเลือกดังนี้

```typescript
protected bindContextMenu() {
    const {
        elementsSelection
    } = this.options;

    elementsSelection.on("contextmenu", (datum) => {
        const event: MouseEvent = (getEvent() as MouseEvent) || window.event as MouseEvent;
        if (event) {
            this.selectionHandler.handleContextMenu(
                datum,
                {
                    x: event.clientX,
                    y: event.clientY
                });
            event.preventDefault();
        }
    });
}
```

utils การโต้ตอบจะเรียกใช้เมธอด `bindEvents` เพื่อกำหนดฟังก์ชันให้กับตัวจัดการ เพิ่มการเรียกใช้ของ `bindClick`, `bindClearCatcher` และ `bindContextMenu` ไปยังเมธอด `bindEvents` ดังนี้:

```typescript
  public bindEvents(
      options: BaseBehaviorOptions<SelectableDataPointType>,
      selectionHandler: ISelectionHandler): void {

      this.options = options;
      this.selectionHandler = selectionHandler;

      this.bindClick();
      this.bindClearCatcher();
      this.bindContextMenu();
  }
```

เมธอด `renderSelection` จะรับผิดชอบในการปรับปรุงสถานะวิชวลขององค์ประกอบในแผนภูมิ

ตัวอย่างของเมธอด `renderSelection` การดำเนินการ:

```typescript
public renderSelection(hasSelection: boolean): void {
    this.options.elementsSelection.style("opacity", (category: any) => {
        if (category.selected) {
            return 0.5;
        } else {
            return 1;
        }
    });
}
```

ขั้นตอนสุดท้ายคือการสร้างอินสแตนซ์ของ `visual behavior` และเรียกใช้เมธอด `bind` ของอินสแตนซ์ยูทิลิตี้การโต้ตอบดังนี้:

```typescript
this.interactivity.bind(<BaseBehaviorOptions<VisualDataPoint>>{
    behavior: this.behavior,
    dataPoints: this.categories,
    clearCatcherSelection: select(this.target),
    elementsSelection: selectionMerge
});
```

* `selectionMerge` เป็นออบเจ็กต์การเลือก D3 ซึ่งจะแสดงองค์ประกอบที่สามารถเลือกได้ทั้งหมดในวิชวล

* `select(this.target)` เป็นออบเจ็กต์การเลือก D3 ซึ่งจะแสดงองค์ประกอบ DOM หลักในวิชวล

* `this.categories` เป็นจุดข้อมูลที่มีองค์ประกอบ ที่ซึ่งอินเทอร์เฟซคือ `VisualDataPoint` (หรือ `categories: VisualDataPoint[];`)

* `this.behavior` คืออินสแตนซ์ใหม่ของ `visual behavior`

  สร้างขึ้นในรูปแบบของการแสดงด้วยภาพ

  ```typescript
  export class Visual implements IVisual {
    // ...
    constructor(options: VisualConstructorOptions) {
        // ...
        this.behavior = new Behavior();
    }
    // ...
  }
  ```

ในตอนนี้ วิชวลพร้อมสำหรับการเลือกตัวจัดการแล้ว

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [อ่านวิธีการจัดการกับการเลือกในการสลับบุ๊กมาร์ก](bookmarks-support.md#visuals-with-selection)

* [อ่านวิธีการเพิ่มเมนูบริบทสำหรับจุดข้อมูลการแสดงด้วยภาพ](context-menu.md)

* [อ่านวิธีการใช้ตัวจัดการการเลือกเพื่อเพิ่มการเลือกลงในการแสดงด้วยภาพของ Power BI](selection-api.md)

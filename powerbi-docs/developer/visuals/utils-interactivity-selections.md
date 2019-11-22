---
title: utils การโต้ตอบวิชวลของ Power BI
description: บทความนี้อธิบายวิธีการเพิ่มการเลือกลงในวิชวลของ Power BI โดยใช้ utils การโต้ตอบ
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 8a9218085b0da655d1ce4b3ece0b2666c4826c86
ms.sourcegitcommit: f7b28ecbad3e51f410eff7ee4051de3652e360e8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/13/2019
ms.locfileid: "74061879"
---
# <a name="microsoft-power-bi-visuals-interactivity-utils"></a>utils การโต้ตอบวิชวลของ Microsoft Power BI

InteractiveivityUtils เป็นชุดของฟังก์ชั่นและคลาสเพื่อให้ง่ายต่อการใช้งานการเลือกข้ามและการกรองข้ามสำหรับวิชวลแบบกำหนดเองของ Power BI

## <a name="installation"></a>การติดตั้ง

> [!NOTE]
> หากคุณยังคงใช้ powerbi-visuals-tools (หมายเลขเวอร์ชันน้อยกว่าที่ 3.x.x) ให้ติดตั้งเครื่องมือเวอร์ชันใหม่ (3.x.x)

> [!IMPORTANT]
> การอัปเดตใหม่ของ utils การโต้ตอบจะรองรับเฉพาะเครื่องเวอร์ชันล่าสุดเท่านั้น [อ่านเพิ่มเติมเกี่ยวกับวิธีการอัปเดตรหัสวิชวลของคุณเพื่อใช้กับเครื่องมือล่าสุด](migrate-to-new-tools.md)

หากต้องการติดตั้งแพ็คเกจ คุณควรเรียกใช้คำสั่งต่อไปนี้ในไดเรกทอรีด้วยวิชวลของแบบกำหนดเอง

```bash
npm install powerbi-visuals-utils-interactivityutils --save
```

คุณอาจต้องติดตั้งเวอร์ชัน 3.0 ขึ้นไป```powerbi-models```เพื่อแก้ไขปัญหาการอ้างอิง

```bash
npm install powerbi-models --save
```

หากต้องการใช้ utils การโต้ตอบ คุณต้องนำเข้าคอมโพเนนต์ที่จำเป็นในโค้ดต้นฉบับของวิชวล

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
> คุณควรนำเข้าไฟล์ css เป็นไฟล์ .less  เนื่องจากเครื่องมือวิชวลของ Power BI ครอบคลุมกฎ CSS ภายนอก

## <a name="usage"></a>การใช้งาน

### <a name="define-interface-for-data-points"></a>กำหนดอินเทอร์เฟซสำหรับจุดข้อมูล

โดยทั่วไปจุดข้อมูลประกอบด้วยตัวเลือกเลือกและค่าต่างๆ อินเทอร์เฟซจะขยายอินเทอร์เฟซ `SelectableDataPoint` `SelectableDataPoint` มีคุณสมบัติดังนี้

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

ขั้นตอนแรกของการใช้ utils การโต้ตอบคือการสร้างอินสแตนซ์ของ utils การโต้ตอบกับและบันทึกวัตถุเป็นคุณสมบัติของวิชวล

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
> BaseBehavior แนะนำใน [utils การโต้ตอบเวอร์ชัน 5.6.x](https://www.npmjs.com/package/powerbi-visuals-utils-interactivityutils/v/5.6.0) หากคุณใช้เวอร์ชันเก่า ให้สร้างคลาสการทำงานจากตัวอย่างด้านล่าง (คลาส `BaseBehavior` เหมือนกัน) ดังนี้

กำหนดอินเทอร์เฟซสำหรับตัวเลือกของคลาสการทำงาน

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

กำหนดคลาสสำหรับ `visual behaviour` คลาสจะรับผิดชอบในการจัดการ `click`, กิจกรรมของเม้าส์ `contextmenu`
เมื่อคลิกองค์ประกอบข้อมูล วิชวลจะใช้ตัวจัดการการเลือกเพื่อเลือกจุดข้อมูล หรือล้างการเลือกหากผู้ใช้คลิกองค์ประกอบพื้นหลังของวิชวล และคลาสจะมีวิธีการที่สอดคล้องกันดังนี้ `bindClick`, `bindClearCatcher`, `bindContextMenu`

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

utils การโต้ตอบจะเรียกใช้วิธีการ `bindEvents` เพื่อกำหนดฟังก์ชันให้กับตัวจัดการ เพิ่มการเรียกใช้ของ `bindClick`, `bindClearCatcher` และ `bindContextMenu` ไปยัง วิธีการ `bindEvents` ดังนี้

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

วิธีการ `renderSelection` จะรับผิดชอบในการปรับปรุงสถานะวิชวลขององค์ประกอบในแผนภูมิ

ตัวอย่างของวิธีการ `renderSelection` การดำเนินการ

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

ขั้นตอนสุดท้ายคือการสร้างอินสแตนซ์ของ `visual behavior` และเรียกใช้วิธีการ `bind` ของอินสแตนซ์ utils การโต้ตอบดังนี้

```typescript
this.interactivity.bind(<BaseBehaviorOptions<VisualDataPoint>>{
    behavior: this.behavior,
    dataPoints: this.categories,
    clearCatcherSelection: select(this.target),
    elementsSelection: selectionMerge
});
```

* `selectionMerge` เป็นวัตถุการเลือก D3 ซึ่งจะแสดงองค์ประกอบทั้งหมดที่เลือกในการแสดงด้วยภาพ

* `select(this.target)` เป็นวัตถุการเลือก D3 ซึ่งจะแสดงองค์ประกอบ DOm หลักของการแสดงด้วยภาพ

* จุดข้อมูล `this.categories` กับองค์ประกอบในอินเทอร์เฟซคือ `VisualDataPoint` (หรือ `categories: VisualDataPoint[];`)

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

ในตอนนี้การแสดงด้วยภาพพร้อมสำหรับการเลือกตัวจัดการแล้ว

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [อ่านวิธีการจัดการกับการเลือกในการสลับบุ๊กมาร์ก](bookmarks-support.md#visuals-with-selection)

* [อ่านวิธีการเพิ่มเมนูบริบทสำหรับจุดข้อมูลการแสดงด้วยภาพ](context-menu.md)

* [อ่านวิธีการใช้ตัวจัดการการเลือกเพื่อเพิ่มการเลือกลงในการแสดงด้วยภาพของ Power BI](selection-api.md)

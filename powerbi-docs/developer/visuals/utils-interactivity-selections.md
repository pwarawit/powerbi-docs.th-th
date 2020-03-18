---
title: utils การโต้ตอบวิชวลของ Power BI
description: บทความนี้อธิบายวิธีการเพิ่มการเลือกลงในวิชวลของ Power BI โดยใช้ utils การโต้ตอบ
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 02/24/2020
ms.openlocfilehash: 3614505cec185779bce3f63c6e7a565a5ef39443
ms.sourcegitcommit: ced8c9d6c365cab6f63fbe8367fb33e6d827cb97
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/07/2020
ms.locfileid: "78920899"
---
# <a name="power-bi-visuals-interactivity-utils"></a>utils การโต้ตอบวิชวลของ Power BI

InteractiveivityUtils (`InteractivityUtils`) เป็นชุดของฟังก์ชันและคลาสเพื่อให้ง่ายต่อการใช้งานการเลือกข้ามและการกรองข้าม

> [!NOTE]
> การอัปเดตยูทิลิตี้การโต้ตอบใหม่จะรองรับเฉพาะเครื่องเวอร์ชันล่าสุดเท่านั้น (3.x.x และใหม่กว่า)

## <a name="installation"></a>การติดตั้ง

1. หากต้องการติดตั้งแพ็คเกจ คุณควรเรียกใช้คำสั่งต่อไปนี้ในไดเรกทอรีด้วยโครงการการแสดงผลด้วยภาพของ Power BI ปัจจุบันของคุณ

    ```bash
    npm install powerbi-visuals-utils-interactivityutils --save
    ```

2. ถ้าคุณกำลังใช้รุ่น 3.0 หรือใหม่กว่าหรือเครื่องมือ ให้ติดตั้ง `powerbi-models` เพื่อแก้ไขการขึ้นต่อกัน

    ```bash
    npm install powerbi-models --save
    ```

3. หากต้องการใช้ยูทิลิตี้การโต้ตอบ คุณต้องนำเข้าคอมโพเนนต์ที่จำเป็นในโค้ดต้นฉบับของการแสดงผลด้วยภาพ

    ```typescript
    import { interactivitySelectionService } from "powerbi-visuals-utils-interactivityutils";
    ```

### <a name="including-the-css-files"></a>รวมถึงไฟล์ CSS

หากต้องการใช้แพ็คเกจกับการแสดงผลด้วยภาพของ Power BI คุณควรนำเข้าไฟล์ CSS ไปยังไฟล์ `.less`  ดังนี้

`node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css`

นำเข้าไฟล์ CSS เป็นไฟล์ `.less` เนื่องจากเครื่องมือการแสดงผลด้วยภาพของ Power BI คลุมกฎ CSS ภายนอก

```less
@import (less) "node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css";
```

## <a name="selectabledatapoint-properties"></a>คุณสมบัติ SelectableDataPoint

โดยทั่วไปจุดข้อมูลประกอบด้วยตัวเลือกและค่าต่างๆ อินเทอร์เฟซจะขยายอินเทอร์เฟซ `SelectableDataPoint`

`SelectableDataPoint` มีคุณสมบัติตามที่อธิบายไว้ด้านล่างแล้ว

```typescript
  /** Flag for identifying that a data point was selected */
  selected: boolean;

  /** Identity for identifying the selectable data point for selection purposes */
  identity: powerbi.extensibility.ISelectionId;

  /*
   * A specific identity for when data points exist at a finer granularity than
   * selection is performed.  For example, if your data points select based
   * only on series, even if they exist as category/series intersections.
   */

  specificIdentity?: powerbi.extensibility.ISelectionId;
```

## <a name="defining-an-interface-for-data-points"></a>กำหนดอินเทอร์เฟซสำหรับจุดข้อมูล

1. สร้างอินสแตนซ์ของยูทิลิตี้แบบโต้ตอบและบันทึกวัตถุเป็นคุณสมบัติของการแสดงผลด้วยภาพ

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

2. ขยายคลาสของลักษณะการทำงานพื้นฐาน

    > [!NOTE]
    > `BaseBehavior` ได้รับการแนะนำใน[ยูทิลิตี้แบบโต้ตอบเวอร์ชัน 5.6.x](https://www.npmjs.com/package/powerbi-visuals-utils-interactivityutils/v/5.6.0) หากคุณใช้เวอร์ชันเก่า ให้สร้างคลาสลักษณะการทำงานจากตัวอย่างด้านล่าง

3. กำหนดอินเทอร์เฟซสำหรับตัวเลือกของคลาสลักษณะการทำงาน

    ```typescript
    import { SelectableDataPoint } from "./interactivitySelectionService";

    import {
        IBehaviorOptions,
        BaseDataPoint
    } from "./interactivityBaseService";

    export interface BaseBehaviorOptions<SelectableDataPointType extends BaseDataPoint> extends IBehaviorOptions<SelectableDataPointType> {

    /** d3 selection object of the main elements on the chart */
    elementsSelection: Selection<any, SelectableDataPoint, any, any>;

    /** d3 selection object of some elements on backgroup, to hadle click of reset selection */
    clearCatcherSelection: d3.Selection<any, any, any, any>;
    }
    ```

4. กำหนดคลาสสำหรับ `visual behavior` หรือขยายคลาส `BaseBehavior`

    **กำหนดคลาสสำหรับ `visual behavior`**

    คลาสจะรับผิดชอบในการจัดการ `click` `contextmenu` กิจกรรมของเม้าส์

    เมื่อผู้ใช้คลิกองค์ประกอบข้อมูล การแสดงผลด้วยภาพจะใช้ตัวจัดการการเลือกเพื่อเลือกจุดข้อมูล หากผู้ใช้คลิกที่องค์ประกอบพื้นหลังของการแสดงผลด้วยภาพ จะเป็นการเรียกใช้ตัวจัดการล้างการเลือก

    และคลาสจะมีวิธีการที่สอดคล้องกันดังนี้:
    * `bindClick`
    * `bindClearCatcher`
    * `bindContextMenu`

    ```typescript
    export class Behavior<SelectableDataPointType extends BaseDataPoint> implements IInteractiveBehavior {

        /** d3 selection object of main elements in the chart */
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

    **การขยาย`BaseBehavior`คลาส**

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

5. หากต้องการจัดการการคลิกที่องค์ประกอบ ให้เรียกใช้วิธีการ*การเลือกวัตถุ* d3`on` นอกจากนี้ยังใช้สำหรับ `elementsSelection` และ `clearCatcherSelection`

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

6. เพิ่มตัวจัดการที่คล้ายกันสำหรับเหตุการณ์ `contextmenu` เพื่อเรียกใช้วิธีการ `showContextMenu` ของผู้จัดการการเลือก

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

7. เพื่อกำหนดฟังก์ชันให้กับตัวจัดการยูทิลิตี้การโต้ตอบให้เรียกใช้วิธีการ `bindEvents` เพิ่มการเรียกไปยังวิธีการ `bindEvents` ต่อไปนี้:
    * `bindClick`
    * `bindClearCatcher`
    * `bindContextMenu`

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

8. เมธอด `renderSelection` จะรับผิดชอบในการปรับปรุงสถานะวิชวลขององค์ประกอบในแผนภูมิ ตัวอย่างของวิธีการ `renderSelection` การดำเนินการ:

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

9. ขั้นตอนสุดท้ายคือการสร้างอินสแตนซ์ของ `visual behavior` และเรียกใช้วิธีการ `bind` ของอินสแตนซ์ยูทิลิตี้การโต้ตอบดังนี้:

    ```typescript
    this.interactivity.bind(<BaseBehaviorOptions<VisualDataPoint>>{
        behavior: this.behavior,
        dataPoints: this.categories,
        clearCatcherSelection: select(this.target),
        elementsSelection: selectionMerge
    });
    ```

    * `selectionMerge` เป็นออบเจ็กต์การเลือก *d3* ซึ่งจะแสดงองค์ประกอบที่สามารถเลือกได้ทั้งหมดในการแสดงผลด้วยภาพ
    * `select(this.target)` เป็นออบเจ็กต์การเลือก *d3* ซึ่งจะแสดงองค์ประกอบ DOM หลักของการแสดงผลด้วยภาพ
    * `this.categories` เป็นจุดข้อมูลที่มีองค์ประกอบ ที่ซึ่งอินเทอร์เฟซคือ `VisualDataPoint` (หรือ `categories: VisualDataPoint[];`)
    * `this.behavior` เป็นอินสแตนซ์ใหม่ของ `visual behavior` ที่สร้างขึ้นในตัวจัดการของการแสดงผลด้วยภาพดังที่แสดงด้านล่าง

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
## <a name="next-steps"></a>ขั้นตอนถัดไป

* [อ่านวิธีการจัดการกับการเลือกในการสลับบุ๊กมาร์ก](bookmarks-support.md#visuals-with-selection)

* [อ่านวิธีการเพิ่มเมนูบริบทสำหรับจุดข้อมูลการแสดงด้วยภาพ](context-menu.md)

* [อ่านวิธีการใช้ตัวจัดการการเลือกเพื่อเพิ่มการเลือกลงในการแสดงด้วยภาพของ Power BI](selection-api.md)

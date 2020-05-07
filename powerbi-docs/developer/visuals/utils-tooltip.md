---
title: บทนำสู่การใช้ยูทิลิตีเครื่องมือในการแสดงผลด้วย Power BI
description: บทความนี้อธิบายวิธีการใช้คำแนะนำเครื่องมือยูทิลิตี้ การปรับแต่งคำแนะนำเครื่องมือสำหรับการแสดงผลด้วยภาพของ Power BI อย่างง่าย
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 02/14/2020
ms.openlocfilehash: 67470ec405806f44fdb483e857d222ad4ff05a45
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "79379179"
---
# <a name="tooltip-utils"></a>คำแนะนำเครื่องมือ
บทความนี้จะช่วยให้คุณสามารถติดตั้ง นำเข้า และใช้คำแนะนำเครื่องมือยูทิลิตี้ ยูทิลิตี้นี้มีประโยชน์สำหรับการปรับแต่งคำแนะนำเครื่องมือใดๆ ก็ตามในการแสดงผลด้วยภาพของ Power BI

## <a name="requirements"></a>ความต้องการ
หากต้องการใช้แพคเกจ คุณควรมีสิ่งต่อไปนี้:
* [node.js](https://nodejs.org) (เราขอแนะนำเวอร์ชัน LTS รุ่นล่าสุด)
* [npm](https://www.npmjs.com/) (เวอร์ชันเก่าที่สุดที่ได้รับการรองรับคือ 3.0.0)
* การแสดงผลด้วยภาพแบบกำหนดเองที่สร้างขึ้นโดย [PowerBI-visuals-tools](https://www.npmjs.com/package/powerbi-visuals-tools)

## <a name="installation"></a>การติดตั้ง

หากต้องการติดตั้งแพ็คเกจ คุณควรเรียกใช้คำสั่งต่อไปนี้ในไดเรกทอรีด้วยวิชวลปัจจุบันของคุณ

```bash
npm install powerbi-visuals-utils-colorutils --save
```
คำสั่งนี้จะติดตั้งแพคเกจและเพิ่มแพคเกจเป็นการขึ้นต่อกันของคุณ ```package.json```

## <a name="usage"></a>การใช้งาน

> คำแนะนำการใช้งานจะอธิบาย API สาธารณะของแพคเกจ คุณจะพบคำอธิบายและตัวอย่างสำหรับแต่ละอินเทอร์เฟซสาธารณะของแพคเกจ

แพคเกจนี้ประกอบด้วยวิธีการสร้าง `TooltipServiceWrapper` และวิธีการเพื่อช่วยจัดการการดำเนินการคำแนะนำเครื่องมือ ซึ่งใช้อินเทอร์เฟซคำแนะนำเครื่องมือ- `ITooltipServiceWrapper` `TooltipEventArgs` `TooltipEnabledDataPoint` 

นอกจากนี้ยังมีวิธีการเฉพาะ (ตัวจัดการเหตุการณ์การ touch) ที่เกี่ยวข้องกับการพัฒนาอุปกรณ์เคลื่อนที่: `touchEndEventName` `touchStartEventName` `usePointerEvents`

`TooltipServiceWrapper` ให้วิธีที่ง่ายที่สุดในการจัดการคำแนะนำเครื่องมือ

โมดูลนี้มีฟังก์ชันและอินเทอร์เฟสต่อไปนี้:
* [ITooltipServiceWrapper](#itooltipservicewrapper)
  * [addTooltip](#itooltipservicewrapperaddtooltip)
  * [ซ่อน](#itooltipservicewrapperhide)

* [อินเทอร์เฟซ](#interfaces)
  * [TooltipEventArgs](#tooltipeventargs)
  * [TooltipEnabledDataPoint](#tooltipenableddatapoint)
  * [TooltipServiceWrapperOptions](#tooltipservicewrapperoptions)
* [เหตุการณ์ Touch](#touch-events)

### `createTooltipServiceWrapper`
ฟังก์ชันนี้สร้างตัวอย่างของ ITooltipServiceWrapper

```typescript
function createTooltipServiceWrapper(tooltipService: ITooltipService, rootElement: Element, handleTouchDelay?: number,  getEventMethod?: () => MouseEvent): ITooltipServiceWrapper;
```

```ITooltipService``` พร้อมใช้งานใน [IVisualHost](https://github.com/microsoft/PowerBI-visuals-tools/blob/master/templates/visuals/.api/v2.6.0/PowerBI-visuals.d.ts#L1335)

**ตัวอย่าง**

```typescript
import { createTooltipServiceWrapper } from "powerbi-visuals-utils-tooltiputils";

export class YourVisual implements IVisual {
    // implementation of IVisual.

    constructor(options: VisualConstructorOptions) {
        createTooltipServiceWrapper(
            options.host.tooltipService,
            options.element);

        // returns: an instance of ITooltipServiceWrapper.
    }
}
```

คุณสามารถดูโค้ดตัวอย่างของวิชวลแบบกำหนดเอง [ที่นี่](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/src/gantt.ts#L391)

### `ITooltipServiceWrapper`
อินเทอร์เฟซนี้จะอธิบายวิธีการสาธารณะของ TooltipService

```typescript
interface ITooltipServiceWrapper {
    addTooltip<T>(selection: d3.Selection<any, any, any, any>, getTooltipInfoDelegate: (args: TooltipEventArgs<T>) => powerbi.extensibility.VisualTooltipDataItem[], getDataPointIdentity?: (args: TooltipEventArgs<T>) => powerbi.visuals.ISelectionId, reloadTooltipDataOnMouseMove?: boolean): void;
    hide(): void;
}
```

#### `ITooltipServiceWrapper.addTooltip`

วิธีนี้จะเพิ่มคำแนะนำเครื่องมือในการเลือกปัจจุบัน

```typescript
addTooltip<T>(selection: d3.Selection<any>, getTooltipInfoDelegate: (args: TooltipEventArgs<T>) => VisualTooltipDataItem[], getDataPointIdentity?: (args: TooltipEventArgs<T>) => ISelectionId, reloadTooltipDataOnMouseMove?: boolean): void;
```

**ตัวอย่าง**

```typescript
import { createTooltipServiceWrapper, TooltipEventArgs, ITooltipServiceWrapper, TooltipEnabledDataPoint } from "powerbi-visuals-utils-tooltiputils";

let bodyElement = d3.select("body");

let element = bodyElement
    .append("div")
    .style({
        "background-color": "green",
        "width": "150px",
        "height": "150px"
    })
    .classed("visual", true)
    .data([{
        tooltipInfo: [{
            displayName: "Power BI",
            value: 2016
        }]
    }]);

let tooltipServiceWrapper: ITooltipServiceWrapper = createTooltipServiceWrapper(tooltipService, bodyElement.get(0)); // tooltipService is from the IVisualHost.

tooltipServiceWrapper.addTooltip<TooltipEnabledDataPoint>(element, (eventArgs: TooltipEventArgs<TooltipEnabledDataPoint>) => {
    return eventArgs.data.tooltipInfo;
});

// You will see a tooltip if you mouseover the element.
```

คุณสามารถดูโค้ดตัวอย่างของวิชวลแบบกำหนดเอง [ที่นี่](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/src/gantt.ts#L2931)

โปรดตั้งใจดูตัวอย่างของการปรับแต่งคำแนะนำเครื่องมือในการแสดงผลด้วยภาพของ Gantt ที่กำหนดเอง[ที่นี่](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/src/gantt.ts#L573-L648)

### `ITooltipServiceWrapper.hide`

วิธีนี้จะซ่อนคำแนะนำเครื่องมือ

```typescript
hide(): void;
```

**ตัวอย่าง**

```typescript
import {createTooltipServiceWrapper} from "powerbi-visuals-utils-tooltiputils";

let tooltipServiceWrapper = createTooltipServiceWrapper(options.host.tooltipService, options.element); // options are from the VisualConstructorOptions.

tooltipServiceWrapper.hide();
```
### `Interfaces`
อินเทอร์เฟซนี้ถูกใช้ในระหว่างการสร้าง TooltipServiceWrapper และการใช้งาน นอกจากนี้ยังมีการกล่าวถึงในตัวอย่างจากหัวข้อก่อนหน้า[ที่นี่](#itooltipservicewrapperaddtooltip)

#### `TooltipEventArgs`
```typescript
interface TooltipEventArgs<TData> {
    data: TData;
    coordinates: number[];
    elementCoordinates: number[];
    context: HTMLElement;
    isTouchEvent: boolean;
}
```

#### `TooltipEnabledDataPoint`
```typescript
interface TooltipEnabledDataPoint {
    tooltipInfo?: powerbi.extensibility.VisualTooltipDataItem[];
}
```

#### `TooltipServiceWrapperOptions`
```typescript
interface TooltipServiceWrapperOptions {
    tooltipService: ITooltipService;
    rootElement: Element;
    handleTouchDelay: number;
    getEventMethod?: () => MouseEvent;
```

### `Touch events`

ตอนนี้คำแนะนำเครื่องมือ utils มีความสามารถในการจัดการเหตุการณ์การสัมผัสหลายอย่างที่เป็นประโยชน์สำหรับการพัฒนาอุปกรณ์เคลื่อนที่

#### `touchStartEventName`
```typescript
function touchStartEventName(): string
```
วิธีนี้จะส่งกลับชื่อเหตุการณ์ touch

#### `touchEndEventName`
```typescript
function touchEndEventName(): string
```
วิธีนี้จะส่งกลับชื่อเหตุการณ์ touch

#### `usePointerEvents`
```typescript
function usePointerEvents(): boolean
```
วิธีการนี้จะส่งกลับเป็นเหตุการณ์ touchStart ปัจจุบันที่เกี่ยวข้องกับตัวชี้หรือไม่เกี่ยวข้อง

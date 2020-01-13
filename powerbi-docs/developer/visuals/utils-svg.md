---
title: บทนำสู่การใช้ยูทิลิตี SVG ในการแสดงผลด้วย Power BI
description: บทความนี้อธิบายวิธีการใช้ยูทิลิตี้ SVG เพื่อลดความซับซ้อนของการปรับใช้ SVG สำหรับวิชวลแบบกำหนดเองของ Power BI
author: vtkalek
ms.author: asander
manager: asander
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 15398c0e8d7322e29c502f49b8c1ea0798f52afe
ms.sourcegitcommit: 4359baa43ca01b179d28ec59f4e61ba8c07ee288
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/20/2019
ms.locfileid: "75308536"
---
# <a name="svg-utils"></a>ยูทิลิตี้ SVG

SVGUtils เป็นชุดฟังก์ชันและคลาส เพื่อลดความซับซ้อนของการปรับใช้ SVG สำหรับวิชวลแบบกำหนดเองของ Power BI

## <a name="installation"></a>การติดตั้ง

หากต้องการติดตั้งแพ็คเกจ คุณควรเรียกใช้คำสั่งต่อไปนี้ในไดเรกทอรีด้วยวิชวลปัจจุบันของคุณ

```bash
npm install powerbi-visuals-utils-svgutils --save
```

## <a name="cssconstants"></a>CssConstants

โมดูล `CssConstants` มีฟังก์ชันและอินเทอร์เฟสพิเศษในการทำงานกับตัวเลือกคลาส

โมดูล `powerbi.extensibility.utils.svg.CssConstants` มีฟังก์ชันและอินเทอร์เฟสต่อไปนี้:

## <a name="classandselector"></a>ClassAndSelector

อินเทอร์เฟซนี้จะอธิบายคุณสมบัติทั่วไปของตัวเลือกคลาส

```typescript
interface ClassAndSelector {
  class: string;
  selector: string;
}
```

### <a name="createclassandselector"></a>createClassAndSelector

ฟังก์ชั้นนี้สร้างตัวอย่าง createClassAndSelector พร้อมกับชื่อของคลาสที่ตั้งไว้

```typescript
function createClassAndSelector(className: string): ClassAndSelector;
```

ตัวอย่าง:

```typescript
import { CssConstants } from "powerbi-visuals-utils-svgutils";
import createClassAndSelector = CssConstants.createClassAndSelector;
import ClassAndSelector = CssConstants.ClassAndSelector;

let divSelector: ClassAndSelector = createClassAndSelector("sample-block");

divSelector.selector === ".sample-block"; // returns: true
divSelector.class === "sample-block"; // returns: true
```

## <a name="manipulation"></a>การจัดการ

`manipulation` มีฟังก์ชันพิเศษบางอย่างที่สร้างสตริงสำหรับใช้กับคุณสมบัติการแปลง SVG

โมดูลมอบฟังก์ชันต่อไปนี้:

### <a name="translate"></a>แปล

ฟังก์ชันนี้สร้างสตริงแปลสำหรับใช้กับคุณสมบัติการแปลง SVG

```typescript
function translate(x: number, y: number): string;
```

ตัวอย่าง:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translate(100, 100);

// returns: translate(100,100)
```

### <a name="translatexwithpixels"></a>translateXWithPixels

ฟังก์ชันนี้สร้างสตริงแปลX สำหรับใช้กับคุณสมบัติการแปลง SVG

```typescript
function translateXWithPixels(x: number): string;
```

ตัวอย่าง:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translateXWithPixels(100);

// returns: translateX(100px)
```

### <a name="translatewithpixels"></a>translateWithPixels

ฟังก์ชันนี้สร้างสตริงแปลสำหรับใช้กับคุณสมบัติการแปลง SVG

```typescript
function translateWithPixels(x: number, y: number): string;
```

ตัวอย่าง:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translateWithPixels(100, 100);

// returns: translate(100px,100px)
```

### <a name="translateandrotate"></a>translateAndRotate

ฟังก์ชันนี้สร้างสตริงแปลหมุนสำหรับใช้กับคุณสมบัติการแปลง SVG

```typescript
function translateAndRotate(
  x: number,
  y: number,
  px: number,
  py: number,
  angle: number
): string;
```

ตัวอย่าง:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translateAndRotate(100, 100, 50, 50, 35);

// returns: translate(100,100) rotate(35,50,50)
```

### <a name="scale"></a>สเกล

ฟังก์ชันนี้สร้างสตริงสเกลสำหรับใช้กับคุณสมบัติการแปลง CSS

```typescript
function scale(scale: number): string;
```

ตัวอย่าง:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.scale(50);

// returns: scale(50)
```

### <a name="transformorigin"></a>transformOrigin

ฟังก์ชันนี้สร้างข้อความแปลเดิมสำหรับใช้กับคุณสมบัติการแปลง CSS

```typescript
function transformOrigin(xOffset: string, yOffset: string): string;
```

ตัวอย่าง:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.transformOrigin(5, 5);

// returns: 5 5
```

### <a name="flushalld3transitions"></a>flushAllD3Transitions

ฟังก์ชันนี้ทำให้การเปลี่ยนแปลง D3 ให้เสร็จสมบูรณ์

```typescript
function flushAllD3Transitions(): void;
```

ตัวอย่าง:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.flushAllD3Transitions();

// forces every transition of D3 to complete
```

### <a name="parsetranslatetransform"></a>parseTranslateTransform

ฟังก์ชันนี้แยกวิเคราะห์สตริงด้วยค่า "translate(x,y)"

```typescript
function parseTranslateTransform(input: string): { x: string; y: string };
```

ตัวอย่าง:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.parseTranslateTransform("translate(100px,100px)");

// returns: { "x":"100px", "y":"100px" }
```

### <a name="createarrow"></a>createArrow

ฟังก์ชันนี้สร้างลูกศร

```typescript
function createArrow(
  width: number,
  height: number,
  rotate: number
): { path: string; transform: string };
```

ตัวอย่าง:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.createArrow(10, 20, 5);

/* returns: {
    "path": "M0 0L0 20L10 10 Z",
    "transform": "rotate(5 5 10)"
}*/
```

## <a name="rect"></a>Rect

โมดูล `Rect` มีฟังก์ชันพิเศษบางอย่างในการจัดการสี่เหลี่ยมผืนผ้า

โมดูลมอบฟังก์ชันต่อไปนี้:

### <a name="getoffset"></a>getOffset

ฟังก์ชันนี้คืนค่าออฟเซตของสี่เหลี่ยมผืนผ้า

```typescript
function getOffset(rect: IRect): IPoint;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getOffset({ left: 25, top: 25, width: 100, height: 100 });

/* returns: {
    x: 25,
    y: 25
}*/
```

### <a name="getsize"></a>getSize

ฟังก์ชันนี้คืนค่าขนาดของสี่เหลี่ยมผืนผ้า

```typescript
function getSize(rect: IRect): ISize;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getSize({ left: 25, top: 25, width: 100, height: 100 });

/* returns: {
    width: 100,
    height: 100
}*/
```

### <a name="setsize"></a>setSize

ฟังก์ชันนี้เปลี่ยนขนาดสี่เหลี่ยมผืนผ้า

```typescript
function setSize(rect: IRect, value: ISize): void;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

let rectangle = { left: 25, top: 25, width: 100, height: 100 };

Rect.setSize(rectangle, { width: 250, height: 250 });

// rectangle === { left: 25, top: 25, width: 250, height: 250 }
```

### <a name="right"></a>ขวา

ฟังก์ชันนี้คืนค่าตำแหน่งขวาของสี่เหลี่ยมผืนผ้า

```typescript
function right(rect: IRect): number;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.right({ left: 25, top: 25, width: 100, height: 100 });

// returns: 125
```

### <a name="bottom"></a>ด้านล่าง

ฟังก์ชันนี้คืนค่าตำแหน่งล่างของสี่เหลี่ยมผืนผ้า

```typescript
function bottom(rect: IRect): number;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.bottom({ left: 25, top: 25, width: 100, height: 100 });

// returns: 125
```

### <a name="topleft"></a>topLeft

ฟังก์ชันนี้คืนค่าตำแหน่งมุมบนซ้ายของสี่เหลี่ยมผืนผ้า

```typescript
function topLeft(rect: IRect): IPoint;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.topLeft({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 25, y: 25 }
```

### <a name="topright"></a>topRight

ฟังก์ชันนี้คืนค่าตำแหน่งมุมบนขวาของสี่เหลี่ยมผืนผ้า

```typescript
function topRight(rect: IRect): IPoint;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.topRight({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 125, y: 25 }
```

### <a name="bottomleft"></a>bottomLeft

ฟังก์ชันนี้คืนค่าตำแหน่งล่างของสี่เหลี่ยมผืนผ้า

```typescript
function bottomLeft(rect: IRect): IPoint;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.bottomLeft({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 25, y: 125 }
```

### <a name="bottomright"></a>bottomRight

ฟังก์ชันนี้คืนค่าตำแหน่งล่างขวาของสี่เหลี่ยมผืนผ้า

```typescript
function bottomRight(rect: IRect): IPoint;
```

### <a name="example"></a>ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.bottomRight({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 125, y: 125 }
```

### <a name="clone"></a>โคลน

ฟังก์ชันนี้สร้างสำเนาของสี่เหลี่ยมผืนผ้า

```typescript
function clone(rect: IRect): IRect;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.clone({ left: 25, top: 25, width: 100, height: 100 });

/* returns: {
    left: 25, top: 25, width: 100, height: 100}
*/
```

### <a name="tostring"></a>toString

ฟังก์ชันนี้แปลงสี่เหลี่ยมผืนผ้าเป็นสตริง

```typescript
function toString(rect: IRect): string;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.toString({ left: 25, top: 25, width: 100, height: 100 });

// returns: {left:25, top:25, width:100, height:100}
```

### <a name="offset"></a>ออฟเซต

ฟังกันนี้ใช้ค่าออฟเซตที่กำหนดกับสี่เหลี่ยมผืนผ้า

```typescript
function offset(rect: IRect, offsetX: number, offsetY: number): IRect;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.offset({ left: 25, top: 25, width: 100, height: 100 }, 50, 50);

/* returns: {
    left: 75,
    top: 75,
    width: 100,
    height: 100
}*/
```

### <a name="add"></a>เพิ่ม

ฟังก์ชันนี้เพิ่มสี่เหลี่ยมผืนผ้าแรกลงในสี่เหลี่ยมที่สอง

```typescript
function add(rect: IRect, rect2: IRect): IRect;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.add(
  { left: 25, top: 25, width: 100, height: 100 },
  { left: 50, top: 50, width: 75, height: 75 }
);

/* returns: {
    left: 75,
    top: 75,
    height: 175,
    width: 175
}*/
```

### <a name="getclosestpoint"></a>getClosestPoint

ฟังก์ชันนี้คืนค่าจุดใกล้สุดบนสามเหลี่ยมกับจุดที่กำหนด

```typescript
function getClosestPoint(rect: IRect, x: number, y: number): IPoint;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getClosestPoint({ left: 0, top: 0, width: 100, height: 100 }, 50, 50);

/* returns: {
    x: 50,
    y: 50
}*/
```

### <a name="equal"></a>เท่ากับ

ฟังก์ชันนี้เปรียบเทียบสี่เหลี่ยมและคืนค่า True หากสี่เหลี่ยมนั้นเหมือนกัน

```typescript
function equal(rect1: IRect, rect2: IRect): boolean;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.equal(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 50, top: 50, width: 100, height: 100 }
);

// returns: false
```

### <a name="equalwithprecision"></a>equalWithPrecision

ฟังก์ชันนี้เปรียบเทียบโดยพิจารณาความแม่นยำของค่า

```typescript
function equalWithPrecision(rect1: IRect, rect2: IRect): boolean;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.equalWithPrecision(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 50, top: 50, width: 100, height: 100 }
);

// returns: false
```

### <a name="isempty"></a>isEmpty

ฟังก์ชันนี้ตรวจสอบว่าสี่เหลี่ยมนั้นว่างเปล่าหรือไม่

```typescript
function isEmpty(rect: IRect): boolean;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.isEmpty({ left: 0, top: 0, width: 0, height: 0 });

// returns: true
```

### <a name="containspoint"></a>containsPoint

ฟังก์ชั้นนี้ตรวจสอบว่าภายในสี่เหลี่ยมมีจุดหรือไม่

```typescript
function containsPoint(rect: IRect, point: IPoint): boolean;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.containsPoint(
  { left: 0, top: 0, width: 100, height: 100 },
  { x: 50, y: 50 }
);

// returns: true
```

### <a name="isintersecting"></a>isIntersecting

ฟังก์ชันนี้ตรวจสอบสี่เหลี่ยมซ้อนทับกันหรือไม่

```typescript
function isIntersecting(rect1: IRect, rect2: IRect): boolean;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.isIntersecting(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 0, top: 0, width: 50, height: 50 }
);

// returns: true
```

### <a name="intersect"></a>intersect

ฟังก์ชั้นนี้คืนค่าทับซ้อนของสี่เหลี่ยมผืนผ้า

```typescript
function intersect(rect1: IRect, rect2: IRect): IRect;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.intersect(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 0, top: 0, width: 50, height: 50 }
);

/* returns: {
    left: 0,
    top: 0,
    width: 50,
    height: 50
}*/
```

### <a name="combine"></a>รวม

ฟังก์ชันนี้รวมสี่เหลี่ยม

```typescript
function combine(rect1: IRect, rect2: IRect): IRect;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.combine(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 0, top: 0, width: 50, height: 120 }
);

/* returns: {
    left: 0,
    top: 0,
    width: 100,
    height: 120
}*/
```

### <a name="getcentroid"></a>getCentroid

ฟังก์ชันนี้คืนค่าออฟเซตของสี่เหลี่ยมผืนผ้า

```typescript
function getCentroid(rect: IRect): IPoint;
```

ตัวอย่าง:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getCentroid({ left: 0, top: 0, width: 100, height: 100 });

/* returns: {
    x: 50,
    y: 50
}*/
```

## <a name="pointer"></a>ตัวชี้

โมดูล `pointer` มีฟังก์ชันเพื่อให้ได้ตำแหน่งของตัวชี้

โมดูลมีฟังก์ชันต่อไปนี้:

### <a name="getcoordinates"></a>getCoordinates

ฟังก์ชันนี้คืนค่าตำแหน่งของตัวชี้

```typescript
function getCoordinates(rootNode: Element, isPointerEvent: boolean): number[];
```

ตัวอย่าง:

```typescript
import { pointer } from "powerbi-visuals-utils-svgutils";

let bodySelection = d3.select("body");

bodySelection
  .append("div")
  .style({
    width: "100px",
    height: "100px",
    "background-color": "green"
  })
  .on("click", () => {
    pointer.getCoordinates(bodySelection.node(), true);
  });

// click element, after that you will get position of the pointer
```

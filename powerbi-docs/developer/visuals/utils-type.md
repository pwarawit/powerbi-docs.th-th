---
title: บทนำสู่การใช้ยูทิลิตีชนิดในการแสดงผลด้วย Power BI
description: บทความนี้อธิบายวิธีการใช้ยูทิลิตี SVG เพื่อขยายชนิดพื้นฐานสำหรับการแสดงผลด้วย Power BI
author: vtkalek
ms.author: asander
manager: asander
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 16645dc70cc236f809a2f2977a2b2fc1a048c254
ms.sourcegitcommit: 4359baa43ca01b179d28ec59f4e61ba8c07ee288
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/20/2019
ms.locfileid: "75308559"
---
# <a name="type-utils"></a>ยูทิลิตี้ชนิด

TypeUtils คือชุดของฟังก์ชันและคลาสเพื่อขยายชนิดพื้นฐานสำหรับการแสดงผลด้วย Power BI

## <a name="installation"></a>การติดตั้ง

หากต้องการติดตั้งแพ็คเกจ คุณควรเรียกใช้คำสั่งต่อไปนี้ในไดเรกทอรีด้วยวิชวลของแบบกำหนดเอง

npm ติดตั้ง powerbi-visuals-utils-typeutils --บันทึก คำสั่งนี้ติดตั้งแพคเกจและเพิ่มแพคเกจ โดยขึ้นอยู่กับแพคเกจ json ของคุณ

## <a name="double"></a>สองครั้ง

`Double` มีความสามารถในการจัดการความแม่นยำของตัวเลข

โมดูลมอบฟังก์ชันต่อไปนี้:

### <a name="pow10"></a>pow10

ฟังก์ชันคืนค่ายกกำลัง 10

```typescript
function pow10(exp: number): number;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.pow10(25);

// returns: 1e+25
```

### <a name="log10"></a>log10

ฟังก์ชันนี้คืนค่าลอการิทึมฐาน 10 ของตัวเลข

```typescript
function log10(val: number): number;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.log10(25);

// returns: 1
```

## <a name="getprecision"></a>getPrecision

ฟังก์ชันนี้คืนค่ายกกำลัง 10 แทนคงามแม่นยำของตัวเลข

```typescript
function getPrecision(x: number, decimalDigits?: number): number;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.getPrecision(562344, 6);

// returns: 0.1
```

### <a name="equalwithprecision"></a>equalWithPrecision

ฟังก์ชันนี้ตรวจสอบว่าความแตกต่างของสองตัวเลขน้อยกว่าความแม่นยำที่กำหนดไว้หรือไม่

```typescript
function equalWithPrecision(x: number, y: number, precision?: number): boolean;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.equalWithPrecision(1, 1.005, 0.01);

// returns: true
```

### <a name="lesswithprecision"></a>lessWithPrecision

ฟังก์ชันนี้ตรวจสอบว่าค่าแรกน้อยกว่าค่าที่สองหรือไม่

```typescript
function lessWithPrecision(x: number, y: number, precision?: number): boolean;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.lessWithPrecision(0.995, 1, 0.001);

// returns: true
```

### <a name="lessorequalwithprecision"></a>lessOrEqualWithPrecision

ฟังก์ชันนี้ตรวจสอบว่าค่าแรกน้อยกว่าหรือเท่ากับค่าที่สองหรือไม่

```typescript
function lessOrEqualWithPrecision(x: number, y: number, precision?: number): boolean;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.lessOrEqualWithPrecision(1.005, 1, 0.01);

// returns: true
```

### <a name="greaterwithprecision"></a>greaterWithPrecision

ฟังก์ชันนี้ตรวจสอบว่าค่าแรกมากกว่าค่าที่สองหรือไม่

```typescript
function greaterWithPrecision(x: number, y: number, precision?: number): boolean;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.greaterWithPrecision(1, 0.995, 0.01);

// returns: false
```

### <a name="greaterorequalwithprecision"></a>greaterOrEqualWithPrecision

ฟังก์ชันนี้ตรวจสอบว่าค่าแรกมากกว่าหรือเท่ากับค่าที่สองหรือไม่

```typescript
function greaterOrEqualWithPrecision(x: number, y: number, precision?: number): boolean;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.greaterOrEqualWithPrecision(1, 1.005, 0.01);

// returns: true
```

### <a name="floorwithprecision"></a>floorWithPrecision

ฟังก์ชันนี้ปรับตัวเลขลงด้วยความแม่นยำที่ให้มา

```typescript
function floorWithPrecision(x: number, precision?: number): number;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.floorWithPrecision(5.96, 0.001);

// returns: 5
```

### <a name="ceilwithprecision"></a>ceilWithPrecision

ฟังก์ชันนี้ `ceils` ตัวเลขด้วยความแม่นยำที่ให้มา

```typescript
function ceilWithPrecision(x: number, precision?: number): number;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.ceilWithPrecision(5.06, 0.001);

// returns: 6
```

### <a name="floortoprecision"></a>floorToPrecision

ฟังก์ชันนี้ปรับตัวเลขลงไปที่ความแม่นยำที่ให้มา

```typescript
function floorToPrecision(x: number, precision?: number): number;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.floorToPrecision(5.96, 0.1);

// returns: 5.9
```

### <a name="ceiltoprecision"></a>ceilToPrecision

ฟังก์ชันนี้ `ceils` ตัวเลขไปที่ความแม่นยำที่ให้มา

```typescript
function ceilToPrecision(x: number, precision?: number): number;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.ceilToPrecision(-506, 10);

// returns: -500
```

### <a name="roundtoprecision"></a>roundToPrecision

ฟังก์ชั้นนี้ปัดเศษตัวเลขให้ตรงกับความแม่นยำที่ให้มา

```typescript
function roundToPrecision(x: number, precision?: number): number;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.roundToPrecision(596, 10);

// returns: 600
```

### <a name="ensureinrange"></a>ensureInRange

ฟังก์ชันนี้คืนค่าตัวเลขที่อยู่ระหว่างค่าต่ำสุดและค่าสูงสุด

```typescript
function ensureInRange(x: number, min: number, max: number): number;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.ensureInRange(-27.2, -10, -5);

// returns: -10
```

### <a name="round"></a>round

ฟังก์ชันนี้ปัดเศษตัวเลข

```typescript
function round(x: number): number;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.round(27.45);

// returns: 27
```

### <a name="removedecimalnoise"></a>removeDecimalNoise

ฟังก์ชันนี้นำค่าทศนิยมออก

```typescript
function removeDecimalNoise(value: number): number;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.removeDecimalNoise(21.493000000000002);

// returns: 21.493
```

### <a name="isinteger"></a>isInteger

ฟังก์ชันนี้ตรวจสอบว่าตัวเลขเป็นจำนวนจริงหรือไม่

```typescript
function isInteger(value: number): boolean;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.isInteger(21.493000000000002);

// returns: false
```

### <a name="toincrement"></a>toIncrement

ฟังก์ชันนี้เพิ่มตัวเลขตามจำนวนที่กำหนดและคืนค่าตัวเลขที่ปัดเศษแล้ว

```typescript
function toIncrement(value: number, increment: number): number;
```

ตัวอย่าง:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.toIncrement(0.6383723, 0.05);

// returns: 0.65
```

## <a name="prototype"></a>Prototype

`Prototype` มีความสามารถในการโอนถ่ายวัตถุ

โมดูลมอบฟังก์ชันต่อไปนี้:

## <a name="inherit"></a>inherit

ฟังก์ชันนี้คืนค่าวัตถุพร้อมกับวัตถุที่กำหนดให้เป็นโปโตคอล

```typescript
function inherit<T>(obj: T, extension?: (inherited: T) => void): T;
```

ตัวอย่าง:

```typescript
import { prototype } from "powerbi-visuals-utils-typeutils";
// ...

let base = { Microsoft: "Power BI" };

prototype.inherit(base);

/* returns: {
    __proto__: {
        Microsoft: "Power BI"
    }
}*/
```

## <a name="inheritsingle"></a>inheritSingle

ฟังก์ชันนี้คืนค่าวัตถุใหม่พร้อมกับวัตถุที่กำหนดให้เป็นโปรโตคอล หากไม่ได้กำหนดโปรโตคอลเท่านั้น

```typescript
function inheritSingle<T>(obj: T): T;
```

ตัวอย่าง:

```typescript
import { prototype } from "powerbi-visuals-utils-typeutils";
// ...

let base = { Microsoft: "Power BI" };

prototype.inheritSingle(base);

/* returns: {
    __proto__: {
        Microsoft: "Power BI"
    }
}*/
```

## <a name="pixelconverter"></a>PixelConverter

`PixelConverter` มีความสามารถในการเปลี่ยนพิกเซลเป็นจุด และจุดเป็นพิกเซล

โมดูลมอบฟังก์ชันต่อไปนี้:

## <a name="tostring"></a>toString

ฟังก์ชันนี้แปลงค่าพิกเซลเป็นสตริง

```typescript
function toString(px: number): string;
```

ตัวอย่าง:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.toString(25);

// returns: 25px
```

## <a name="frompoint"></a>fromPoint

ฟังก์ชันนี้แปลงค่าจุดที่กำหนดให้เป็นค่าพิกเซลและคืนค่าการแปลเป็นสตริง

```typescript
function fromPoint(pt: number): string;
```

ตัวอย่าง:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.fromPoint(8);

// returns: 33.33333333333333px
```

## <a name="frompointtopixel"></a>fromPointToPixel

ฟังก์ชันนี้แปลงค่าจุดเป็นค่าพิกเซล

```typescript
function fromPointToPixel(pt: number): number;
```

ตัวอย่าง:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.fromPointToPixel(8);

// returns: 10.666666666666666
```

## <a name="topoint"></a>toPoint

ฟังก์ชันนี้แปลงค่าพิกเซลเป็นค่าจุด

```typescript
function toPoint(px: number): number;
```

ตัวอย่าง:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.toPoint(8);

// returns: 6
```

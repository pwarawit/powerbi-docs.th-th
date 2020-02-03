---
title: บทนำสู่การใช้ยูทิลิตี้การจัดรูปแบบในวิชวล Power BI
description: บทความนี้อธิบายวิธีการใช้ยูทิลิตี้การจัดรูปแบบเพื่อจัดรูปแบบค่าและใช้การแปลเป็นภาษาท้องถิ่นกับค่าในวิชวล Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 9ae7e4b976cef2217c3742ef808a9a7063695cbc
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819479"
---
# <a name="formatting-utils"></a>ยูทิลิตี้การจัดรูปแบบ

ยูทิลิตี้การจัดรูปแบบประกอบด้วยคลาส อินเทอร์เฟซ และเมธอดการจัดรูปแบบค่า นอกจากนี้ยังประกอบด้วยเมธอด extender เพื่อประมวลผลสตริงและวัดขนาดข้อความในเอกสาร SVG/HTML

## <a name="text-measurement-service"></a>บริการการวัดข้อความ

โมดูลมอบฟังก์ชันและอินเทอร์เฟซต่อไปนี้:

### <a name="textproperties-interface"></a>อินเทอร์เฟซ TextProperties

อินเทอร์เฟซนี้จะอธิบายคุณสมบัติทั่วไปของข้อความ

```typescript
interface TextProperties {
    text?: string;
    fontFamily: string;
    fontSize: string;
    fontWeight?: string;
    fontStyle?: string;
    fontVariant?: string;
    whiteSpace?: string;
}
```

### <a name="measuresvgtextwidth"></a>measureSvgTextWidth

ฟังก์ชันนี้วัดความกว้างของข้อความด้วยคุณสมบัติข้อความ SVG ที่กำหนด

```typescript
function measureSvgTextWidth(textProperties: TextProperties, text?: string): number;
```

Example of using `measureSvgTextWidth`:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.measureSvgTextWidth(textProperties);

// returns: 194.71875
```

### <a name="measuresvgtextrect"></a>measureSvgTextRect

ฟังก์ชันนี้คืนค่า rect ด้วยคุณสมบัติข้อความ SVG ที่กำหนด

```typescript
function measureSvgTextRect(textProperties: TextProperties, text?: string): SVGRect;
```

Example of using `measureSvgTextRect`:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.measureSvgTextRect(textProperties);

// returns: { x: 0, y: -22, width: 194.71875, height: 27 }
```

### <a name="measuresvgtextheight"></a>measureSvgTextHeight

ฟังก์ชันนี้วัดความสูงของข้อความด้วยคุณสมบัติข้อความ SVG ที่กำหนด

```typescript
function measureSvgTextHeight(textProperties: TextProperties, text?: string): number;
```

Example of using `measureSvgTextHeight`:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...


let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.measureSvgTextHeight(textProperties);

// returns: 27
```

### <a name="estimatesvgtextbaselinedelta"></a>estimateSvgTextBaselineDelta

ฟังก์ชันนี้จะส่งกลับเส้นอ้างอิงของคุณสมบัติข้อความ SVG ที่กำหนด

```typescript
function estimateSvgTextBaselineDelta(textProperties: TextProperties): number;
```

ตัวอย่าง:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.estimateSvgTextBaselineDelta(textProperties);

// returns: 5
```

### <a name="estimatesvgtextheight"></a>estimateSvgTextHeight

ฟังก์ชันนี้ประมาณความสูงของข้อความด้วยคุณสมบัติข้อความ SVG ที่กำหนด

```typescript
function estimateSvgTextHeight(textProperties: TextProperties, tightFightForNumeric?: boolean): number;
```

Example of using `estimateSvgTextHeight`:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.estimateSvgTextHeight(textProperties);

// returns: 27
```

คุณสามารถดูโค้ดตัวอย่างของวิชวลแบบกำหนดเอง [ที่นี่](https://github.com/Microsoft/powerbi-visuals-sankey/blob/4d544ea145b4e15006083a3610dfead3da5f61a4/src/visual.ts#L372)

### <a name="measuresvgtextelementwidth"></a>measureSvgTextElementWidth

ฟังก์ชันนี้วัดความกว้างของ svgElement

```typescript
function measureSvgTextElementWidth(svgElement: SVGTextElement): number;
```

ตัวอย่างของการใช้ measureSvgTextElementWidth:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let svg: D3.Selection = d3.select("body").append("svg");

svg.append("text")
    .text("Microsoft PowerBI")
    .attr({
        "x": 25,
        "y": 25
    })
    .style({
        "font-family": "sans-serif",
        "font-size": "24px"
    });

let textElement: D3.Selection = svg.select("text");

textMeasurementService.measureSvgTextElementWidth(textElement.node());

// returns: 194.71875
```

### <a name="getmeasurementproperties"></a>getMeasurementProperties

ฟังก์ชันนี้ดึงข้อมูลคุณสมบัติการวัดข้อความขององค์ประกอบ DOM ที่กำหนด

```typescript
function getMeasurementProperties(element: Element): TextProperties;
```

Example of using `getMeasurementProperties`:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let element: JQuery = $(document.createElement("div"));

element.text("Microsoft PowerBI");

element.css({
    "width": 500,
    "height": 500,
    "font-family": "sans-serif",
    "font-size": "32em",
    "font-weight": "bold",
    "font-style": "italic",
    "white-space": "nowrap"
});

textMeasurementService.getMeasurementProperties(element.get(0));

/* returns: {
    fontFamily:"sans-serif",
    fontSize: "32em",
    fontStyle: "italic",
    fontVariant: "",
    fontWeight: "bold",
    text: "Microsoft PowerBI",
    whiteSpace: "nowrap"
}*/
```

### <a name="getsvgmeasurementproperties"></a>getSvgMeasurementProperties

ฟังก์ชันนี้ดึงข้อมูลคุณสมบัติการวัดข้อความขององค์ประกอบข้อความ SVG ที่กำหนด

```typescript
function getSvgMeasurementProperties(svgElement: SVGTextElement): TextProperties;
```

Example of using `getSvgMeasurementProperties`:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let svg: D3.Selection = d3.select("body").append("svg");

let textElement: D3.Selection = svg.append("text")
    .text("Microsoft PowerBI")
    .attr({
        "x": 25,
        "y": 25
    })
    .style({
        "font-family": "sans-serif",
        "font-size": "24px"
    });

textMeasurementService.getSvgMeasurementProperties(textElement.node());

/* returns: {
    "text": "Microsoft PowerBI",
    "fontFamily": "sans-serif",
    "fontSize": "24px",
    "fontWeight": "normal",
    "fontStyle": "normal",
    "fontVariant": "normal",
    "whiteSpace": "nowrap"
}*/
```

## <a name="getdivelementwidth"></a>getDivElementWidth

ฟังก์ชันนี้ส่งกลับความกว้างขององค์ประกอบ div

```typescript
function getDivElementWidth(element: JQuery): string;
```

Example of using `getDivElementWidth`:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let svg: Element = d3.select("body")
    .append("div")
    .style({
        "width": "150px",
        "height": "150px"
    })
    .node();

textMeasurementService.getDivElementWidth(svg)

// returns: 150px
```

### <a name="gettailoredtextordefault"></a>getTailoredTextOrDefault

เปรียบเทียบขนาดป้ายข้อความกับขนาดที่มีและแสดงรูปวงรีเมื่อขนาดที่มีอยู่มีขนาดเล็กกว่า

```typescript
function getTailoredTextOrDefault(textProperties: TextProperties, maxWidth: number): string;
```

Example of using `getTailoredTextOrDefault`:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI!",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.getTailoredTextOrDefault(textProperties, 100);

// returns: Micros...
```

## <a name="string-extensions"></a>ส่วนขยายของสตริง

โมดูลมอบฟังก์ชันต่อไปนี้:

## <a name="endswith"></a>endsWith

ฟังก์ชันนี้ตรวจสอบว่าสตริงลงท้ายด้วยซับสตริงหรือไม่

```typescript
function endsWith(str: string, suffix: string): boolean;
```

Example of using `endsWith`:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.endsWith("Power BI", "BI");

// returns: true
```

### <a name="equalignorecase"></a>equalIgnoreCase

ฟังก์ชันนี้เปรียบเทียบสตริงที่ ละเว้นตัวพิมพ์ใหญ่-เล็ก

```typescript
function equalIgnoreCase(a: string, b: string): boolean;
```

ตัวอย่างของการใช้ `equalIgnoreCase`:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.equalIgnoreCase("Power BI", "power bi");

// returns: true
```

### <a name="startswith"></a>startsWith

ฟังก์ชันนี้ตรวจสอบว่าสตริงเริ่มต้นด้วยซับสตริงหรือไม่

```typescript
function startsWith(a: string, b: string): boolean;
```

Example of using `startsWith`:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.startsWith("Power BI", "Power");

// returns: true
```

### <a name="contains"></a>ประกอบด้วย

ฟังก์ชันนี้ตรวจสอบว่าสตริงประกอบด้วยซับสตริงที่ระบุหรือไม่

```typescript
function contains(source: string, substring: string): boolean;
```

ตัวอย่างของการใช้เมธอด `contains`:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.contains("Microsoft Power BI Visuals", "Power BI");

// returns: true
```

### <a name="isnullorempty"></a>isNullOrEmpty

ตรวจสอบว่าสตริงเป็น null หรือไม่ได้กำหนดหรือว่างเปล่า หรือไม่

```typescript
function isNullOrEmpty(value: string): boolean;
```

ตัวอย่างของการใช้ `isNullOrEmpty`:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.isNullOrEmpty(null);

// returns: true
```

## <a name="value-formatter"></a>Value formatter

โมดูลมอบฟังก์ชัน อินเตอร์เฟส และคลาสต่อไปนี้:

## <a name="ivalueformatter"></a>IValueFormatter

อินเทอร์เฟซนี้จะอธิบายเมธอดและคุณสมบัติสาธารณะ (public) ของตัวจัดรูปแบบ

```typescript
interface IValueFormatter {
    format(value: any): string;
    displayUnit?: DisplayUnit;
    options?: ValueFormatterOptions;
}
```

### <a name="ivalueformatterformat"></a>IValueFormatter.format

เมธอดนี้จัดรูปแบบค่าที่กำหนด

```typescript
function format(value: any, format?: string, allowFormatBeautification?: boolean): string;
```

ตัวอย่างสำหรับ `IValueFormatter.format`:

#### <a name="the-thousand-formats"></a>รูปแบบพัน

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1001 });

iValueFormatter.format(5678);

// returns: "5.68K"
```

#### <a name="the-million-formats"></a>รูปแบบล้าน

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1e6 });

iValueFormatter.format(1234567890);

// returns: "1234.57M"
```

#### <a name="the-billion-formats"></a>รูปแบบพันล้าน

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1e9 });

iValueFormatter.format(1234567891236);

// returns: 1234.57bn
```

#### <a name="the-trillion-format"></a>รูปแบบล้านล้าน

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1e12 });

iValueFormatter.format(1234567891236);

// returns: 1.23T
```

#### <a name="the-exponent-format"></a>รูปแบบเลขชี้กำลัง

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ format: "E" });

iValueFormatter.format(1234567891236);

// returns: 1.234568E+012
```

### <a name="the-culture-selector"></a>ตัวเลือกวัฒนธรรม

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let valueFormatterUK = valueFormatter.create({ cultureSelector: "en-GB" });

valueFormatterUK.format(new Date(2007, 2, 3, 17, 42, 42));

// returns: 03/03/2007 17:42:42

let valueFormatterUSA = valueFormatter.create({ cultureSelector: "en-US" });

valueFormatterUSA.format(new Date(2007, 2, 3, 17, 42, 42));

// returns: 3/3/2007 5:42:42 PM
```

#### <a name="the-percentage-format"></a>รูปแบบเปอร์เซ็นต์

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ format: "0.00 %;-0.00 %;0.00 %" });

iValueFormatter.format(0.54);

// returns: 54.00 %
```

#### <a name="the-dates-format"></a>รูปแบบวันที่

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let date = new Date(2016, 10, 28, 15, 36, 0),
    iValueFormatter = valueFormatter.create({});

iValueFormatter.format(date);

// returns: 11/28/2016 3:36:00 PM
```

#### <a name="the-boolean-format"></a>รูปแบบบูลีน

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({});

iValueFormatter.format(true);

// returns: True
```

#### <a name="the-customized-precision"></a>ความแม่นยำแบบกำหนดเอง

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 0, precision: 3 });

iValueFormatter.format(3.141592653589793);

// returns: 3.142
```

คุณสามารถดูโค้ดตัวอย่างของวิชวลแบบกำหนดเอง [ที่นี่](https://github.com/Microsoft/powerbi-visuals-sankey/blob/4d544ea145b4e15006083a3610dfead3da5f61a4/src/visual.ts#L359)

## <a name="valueformatteroptions"></a>ValueFormatterOptions

อินเตอร์เฟสนี้อธิบาย `options` ของ IValueFormatter และตัวเลือกของฟังก์ชัน 'สร้าง'

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";
import ValueFormatterOptions = valueFormatter.ValueFormatterOptions;

interface ValueFormatterOptions {
    /** The format string to use. */
    format?: string;
    /** The data value. */
    value?: any;
    /** The data value. */
    value2?: any;
    /** The number of ticks. */
    tickCount?: any;
    /** The display unit system to use */
    displayUnitSystemType?: DisplayUnitSystemType;
    /** True if we are formatting single values in isolation (e.g. card), as opposed to multiple values with a common base (e.g. chart axes) */
    formatSingleValues?: boolean;
    /** True if we want to trim off unnecessary zeroes after the decimal and remove a space before the % symbol */
    allowFormatBeautification?: boolean;
    /** Specifies the maximum number of decimal places to show*/
    precision?: number;
    /** Detect axis precision based on value */
    detectAxisPrecision?: boolean;
    /** Specifies the column type of the data value */
    columnType?: ValueTypeDescriptor;
    /** Specifies the culture */
    cultureSelector?: string;
}
```

## <a name="create"></a>สร้าง

เมธอดนี้สร้างอินสแตนซ์ของ IValueFormatter

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";
import create = valueFormatter.create;

function create(options: ValueFormatterOptions): IValueFormatter;
```

### <a name="example-of-using-create"></a>ตัวอย่างของการใช้ create

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

valueFormatter.create({});

// returns: an instance of IValueFormatter.
```

## <a name="next-steps"></a>ขั้นตอนถัดไป

[เพิ่มการแปลเป็นภาษาท้องถิ่นไปยังวิชวลแบบกำหนดเอง Power BI](localization.md)  

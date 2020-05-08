---
title: บทนำสู่การใช้ยูทิลิตี้สีในการแสดงผลด้วยภาพของ Power BI
description: บทความนี้อธิบายวิธีการใช้ยูทิลิตี้สี ทำให้ง่ายต่อการใช้ชุดรูปแบบและจานสีบนจุดข้อมูลของการแสดงผลด้วยภาพของ Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 02/14/2020
ms.openlocfilehash: 8de530871739a18c1afc72cee3e0da5fc70ebb16
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "79379363"
---
# <a name="color-utils"></a>ยูทิลิตี้สี
บทความนี้จะช่วยให้คุณสามารถติดตั้ง นำเข้า และใช้คำแนะนำเครื่องมือยูทิลิตี้สี บทความนี้อธิบายวิธีการใช้ยูทิลิตี้สี ทำให้ง่ายต่อการใช้ชุดรูปแบบและจานสีบนจุดข้อมูลของการแสดงผลด้วยภาพของ Power BI

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

หากต้องการใช้ยูทิลิตี้การโต้ตอบ คุณต้องนำเข้าคอมโพเนนต์ที่จำเป็นในโค้ดต้นฉบับของวิชวล
```typescript
import { ColorHelper } from "powerbi-visuals-utils-colorutils";
```

เรียนรู้วิธีการติดตั้งและใช้ ColorUtils ในวิชวล Power BI ของคุณ:

* [คำแนะนำการใช้งาน] คำแนะนำการใช้งานนี้จะอธิบาย API สาธารณะของแพคเกจ คุณจะพบคำอธิบายและตัวอย่างสำหรับแต่ละอินเทอร์เฟซสาธารณะของแพคเกจ

แพคเกจนี้ประกอบด้วยคลาสและโมดูลต่อไปนี้:
* [ColorHelper](#colorhelper) - ช่วยในการสร้างสีที่มีความแตกต่างกันสำหรับค่าแผนภูมิของคุณ
* [colorUtils](#colorutils) - ช่วยในการแปลงรูปแบบสีของ

## `ColorHelper`
คลาส `ColorHelper` มีฟังก์ชันและวิธีการดังต่อไปนี้:

### `getColorForSeriesValue` 
วิธีนี้จะเป็นการได้สีสำหรับค่าชุดข้อมูลที่ระบุไว้ ถ้าไม่มีสีที่ชัดเจนหรือสีเริ่มต้นที่ได้รับการตั้งค่าแล้ว จะมีการจัดสรรสี จากระดับสีสำหรับชุดข้อมูลนี้
```typescript
getColorForSeriesValue(objects: IDataViewObjects, value: PrimitiveValue, themeColorName?: ThemeColorName): string;
```
#### <a name="example"></a>ตัวอย่าง
```typescript
import powerbi from "powerbi-visuals-api";
import { ColorHelper } from "powerbi-visuals-utils-colorutils";

import DataViewObjects = powerbi.DataViewObjects;

import DataViewValueColumns = powerbi.DataViewValueColumns;
import DataViewValueColumnGroup = powerbi.DataViewValueColumnGroup;
import DataViewObjectPropertyIdentifier = powerbi.DataViewObjectPropertyIdentifier;

import IVisual = powerbi.extensibility.visual.IVisual;
import IColorPalette = powerbi.extensibility.IColorPalette;
import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions;
import VisualConstructorOptions = powerbi.extensibility.visual.VisualConstructorOptions;

export class YourVisual implements IVisual {
    // Implementation of IVisual

    private colorPalette: IColorPalette;

    constructor(options: VisualConstructorOptions) {
        this.colorPalette = options.host.colorPalette;
    }

    public update(visualUpdateOptions: VisualUpdateOptions): void {
        const valueColumns: DataViewValueColumns = visualUpdateOptions.dataViews[0].categorical.values,
            grouped: DataViewValueColumnGroup[] = valueColumns.grouped(),
            defaultDataPointColor: string = "green",
            fillProp: DataViewObjectPropertyIdentifier = {
                objectName: "objectName",
                propertyName: "propertyName"
            };

        let colorHelper: ColorHelper = new ColorHelper(
            this.colorPalette,
            fillProp,
            defaultDataPointColor);

        for (let i = 0; i < grouped.length; i++) {
            let grouping: DataViewValueColumnGroup = grouped[i];

            let color = colorHelper.getColorForSeriesValue(grouping.objects, grouping.name); // returns a color of the series
        }
    }
}
```

### `getColorForMeasure`
วิธีนี้จะเป็นการรับสีสำหรับหน่วยวัดที่กำหนด
```typescript
 getColorForMeasure(objects: IDataViewObjects, measureKey: any, themeColorName?: ThemeColorName): string;
```
#### <a name="example"></a>ตัวอย่าง
```typescript
import powerbi from "powerbi-visuals-api";
import { ColorHelper } from "powerbi-visuals-utils-colorutils";

import DataViewObjects = powerbi.DataViewObjects;
import IVisual = powerbi.extensibility.visual.IVisual;
import IColorPalette = powerbi.extensibility.IColorPalette;
import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions;
import DataViewObjectPropertyIdentifier = powerbi.DataViewObjectPropertyIdentifier;
import VisualConstructorOptions = powerbi.extensibility.visual.VisualConstructorOptions;

export class YourVisual implements IVisual {
    // Implementation of IVisual

    private colorPalette: IColorPalette;

    constructor(options: VisualConstructorOptions) {
        this.colorPalette = options.host.colorPalette;
    }

    public update(visualUpdateOptions: VisualUpdateOptions): void {
        const objects: DataViewObjects = visualUpdateOptions.dataViews[0].categorical.categories[0].objects[0],
            defaultDataPointColor: string = "green",
            fillProp: DataViewObjectPropertyIdentifier = {
                objectName: "objectName",
                propertyName: "propertyName"
            };

        let colorHelper: ColorHelper = new ColorHelper(
            this.colorPalette,
            fillProp,
            defaultDataPointColor);

        let color = colorHelper.getColorForMeasure(objects, ""); // returns a color
    }
}
```

### <a name="static-normalizeselector"></a>คงที่ `normalizeSelector`
วิธีการนี้จะส่งกลับตัวเลือกปกติ
```typescript
static normalizeSelector(selector: Selector, isSingleSeries?: boolean): Selector;
```
#### <a name="example"></a>ตัวอย่าง
```typescript
import ISelectionId = powerbi.visuals.ISelectionId;
import { ColorHelper } from "powerbi-visuals-utils-colorutils";

let selectionId: ISelectionId = ...;
let selector = ColorHelper.normalizeSelector(selectionId.getSelector(), false);
```

วิธีการ`getThemeColor`และ`getHighContrastColor` ทั้งหมดที่เกี่ยวข้องกับสีธีมสีต่างๆ
นอกจากนี้`ColorHelper`และ`isHighContrast`ยังมีคุณสมบัติที่อาจมีประโยชน์สำหรับการตรวจสอบ

### `getThemeColor`
วิธีการนี้จะส่งสีของธีมกลับมา
```typescript
 getThemeColor(themeColorName?: ThemeColorName): string;
```
### `getHighContrastColor`
 วิธีการนี้จะส่งสีกลับมาสำหรับโหมดความคมชัดสูง
```typescript
getHighContrastColor(themeColorName?: ThemeColorName, defaultColor?: string): string;
```
#### <a name="example-related-to-high-contrast-mode-usage"></a>ตัวอย่างที่เกี่ยวข้องกับการใช้โหมดความคมชัดสูง:
```typescript

import { ColorHelper } from "powerbi-visuals-utils-colorutils";

export class MyVisual implements IVisual {
        private colorHelper: ColorHelper;

        private init(options: VisualConstructorOptions): void {
            this.colors = options.host.colorPalette;
            this.colorHelper = new ColorHelper(this.colors);
        } 

            private createViewport(element: HTMLElement): void {
                const fontColor: string = "#131aea";
                const axisBackgroundColor: string = this.colorHelper.getThemeColor();
                
                // some d3 code before
                d3ElementName.attr("fill", colorHelper.getHighContrastColor("foreground", fontColor);
            }
                
            public static parseSettings(dataView: DataView, colorHelper: ColorHelper): VisualSettings {
                // some code that should be applied on formatting settings
                if (colorHelper.isHighContrast) {
                        this.settings.fontColor = colorHelper.getHighContrastColor("foreground", this.settings.fontColor);
                    }
            }
}
```


## `ColorUtils`
 โมดูลมอบฟังก์ชันต่อไปนี้:

* [hexToRGBString](#hextorgbstring)
* [การหมุน](#rotate)
* [parseColorString](#parsecolorstring)
* [calculateHighlightColor](#calculatehighlightcolor)
* [createLinearColorScale](#createlinearcolorscale)
* [shadeColor](#shadecolor)
* [rgbBlend](#rgbblend)
* [channelBlend](#channelblend)
* [hexBlend](#hexblend)

### <a name="hextorgbstring"></a>hexToRGBString
แปลงสี hex เป็นสตริง RGB

```typescript
function hexToRGBString(hex: string, transparency?: number): string
```

#### <a name="example"></a>ตัวอย่าง

```typescript
import  { hexToRGBString } from "powerbi-visuals-utils-colorutils";

hexToRGBString('#112233');

// returns: "rgb(17,34,51)"
```

### <a name="rotate"></a>การหมุน
การหมุนสี RGB

```typescript
function rotate(rgbString: string, rotateFactor: number): string
```

#### <a name="example"></a>ตัวอย่าง

```typescript
import { rotate } from "powerbi-visuals-utils-colorutils";

rotate("#CC0000", 0.25); // returns: #66CC00
```

### <a name="parsecolorstring"></a>parseColorString
แยกวิเคราะห์สตริงของสีไปเป็นรูปแบบ RGB

```typescript
function parseColorString(color: string): RgbColor
```

#### <a name="example"></a>ตัวอย่าง

```typescript
import { parseColorString } from "powerbi-visuals-utils-colorutils";

parseColorString('#09f');
// returns: {R: 0, G: 153, B: 255 }

parseColorString('rgba(1, 2, 3, 1.0)');
// returns: {R: 1, G: 2, B: 3, A: 1.0 }
```

### <a name="calculatehighlightcolor"></a>calculateHighlightColor
คำนวณสีไฮไลต์จาก rgbColor ที่ยึดตาม lumianceThreshold และ delta

```typescript
function calculateHighlightColor(rgbColor: RgbColor, lumianceThreshold: number, delta: number): string
```

#### <a name="example"></a>ตัวอย่าง

```typescript
import { calculateHighlightColor } from "powerbi-visuals-utils-colorutils";

let yellow = "#FFFF00",
    yellowRGB = parseColorString(yellow);

calculateHighlightColor(yellowRGB, 0.8, 0.2);

// returns: '#CCCC00'
```

### <a name="createlinearcolorscale"></a>createLinearColorScale
ส่งสเกลสีแบบเชิงเส้นกลับสำหรับโดเมนของตัวเลขที่กำหนด

```typescript
function createLinearColorScale(domain: number[], range: string[], clamp: boolean): LinearColorScale
```

#### <a name="example"></a>ตัวอย่าง

```typescript
import { createLinearColorScale } from "powerbi-visuals-utils-colorutils";

let scale = ColorUtility.createLinearColorScale(
    [0, 1, 2, 3, 4],
    ["red", "green", "blue", "black", "yellow"],
    true);

scale(1); // returns: green
scale(10); // returns: yellow
```

### <a name="shadecolor"></a>shadeColor
แปลงนิพจน์ hex ของสตริงที่เป็นตัวเลข คำนวณเปอร์เซ็นต์และช่อง R, G, B
ใช้เปอร์เซ็นต์สำหรับแต่ละช่องและส่งกลับค่าฐานสิบหกเป็นสตริงที่มีเครื่องหมายปอนด์

```typescript
function shadeColor(color: string, percent: number): string
```

#### <a name="example"></a>ตัวอย่าง

```typescript
import { shadeColor } from "powerbi-visuals-utils-colorutils";

shadeColor('#000000', 0.1); // returns '#1a1a1a'
shadeColor('#FFFFFF', -0.5); // returns '#808080'
shadeColor('#00B8AA', -0.25); // returns '#008a80'
shadeColor('#00B8AA', 0); // returns '#00b8aa'
```

### <a name="rgbblend"></a>rgbBlend{1}
การซ้อนทับสีด้วยความทึบเหนือสีพื้นหลัง ให้ละเว้นช่องสัญญาณอัลฟ่า

```typescript
function rgbBlend(foreColor: RgbColor, opacity: number, backColor: RgbColor): RgbColor
```

#### <a name="example"></a>ตัวอย่าง

```typescript
import { rgbBlend} from "powerbi-visuals-utils-colorutils";

rgbBlend({R: 100, G: 100, B: 100}, 0.5, {R: 200, G: 200, B: 200});

// returns: {R: 150, G: 150, B: 150}
```

### <a name="channelblend"></a>channelBlend
ผสมช่องสัญญาณเดียวสำหรับสองสี

```typescript
function channelBlend(foreChannel: number, opacity: number, backChannel: number): number
```

#### <a name="example"></a>ตัวอย่าง

```typescript
import { channelBlend} from "powerbi-visuals-utils-colorutils";

channelBlend(0, 1, 255); // returns: 0
channelBlend(128, 1, 255); // returns: 128
channelBlend(255, 0, 0); // returns: 0
channelBlend(88, 0, 88); // returns: 88
```

### <a name="hexblend"></a>hexBlend
การซ้อนทับสีด้วยความทึบเหนือสีพื้นหลัง

```typescript
function hexBlend(foreColor: string, opacity: number, backColor: string): string
```

#### <a name="example"></a>ตัวอย่าง

```typescript
import { hexBlend} from "powerbi-visuals-utils-colorutils";

let yellow = "#FFFF00",
    black = "#000000",
    white = "#FFFFFF";

hexBlend(yellow, 0.5, white); // returns: "#FFFF80"
hexBlend(white, 0.5, yellow); // returns: "#FFFF80"

hexBlend(yellow, 0.5, black); // returns: "#808000"
hexBlend(black, 0.5, yellow); // returns: "#808000"
```
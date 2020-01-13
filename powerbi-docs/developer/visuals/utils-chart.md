---
title: บทนำสู่การใช้ยูทิลิตีแผนภูมิในการแสดงผลด้วย Power BI
description: บทความนี้อธิบายวิธีการใช้ยูทิลิตี้แผนภูมิเพื่อวาดแกนและคำอธิบายการแสดงผล Power BI
author: vtkalek
ms.author: asander
manager: asander
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: e67b37f73b3cea097a296f313fbfc8922b7dd945
ms.sourcegitcommit: 4359baa43ca01b179d28ec59f4e61ba8c07ee288
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/20/2019
ms.locfileid: "75308582"
---
# <a name="chart-utils"></a>ยูทิลิตี้แผนภูมิ

ChartUtils คือชุดของอินเทอร์เฟซและวิธีการในการสร้างแกน ป้ายชื่อข้อมูล และคำอธิบายแผนภูมิในการแสดงผลใน Power BI

## <a name="installation"></a>การติดตั้ง

หากต้องการติดตั้งแพ็คเกจ คุณควรเรียกใช้คำสั่งต่อไปนี้ในไดเรกทอรีด้วยวิชวลปัจจุบันของคุณ

```bash
npm install powerbi-visuals-utils-chartutils --save
```

## <a name="axis-helper"></a>ตัวช่วยแกน

ตัวช่วยแกน (วัตถุ`axis` ในยูทิลิตี้) มีฟังก์ชันเพื่อลดความซับซ้อนให้กับแกน

โมดูลมอบฟังก์ชันต่อไปนี้:

### <a name="getrecommendednumberofticksforxaxis"></a>getRecommendedNumberOfTicksForXAxis

ฟังก์ชันนี้ส่งกลับจำนวนของเครื่องหมายที่แนะนำตามความกว้างของแผนภูมิ

```typescript
function getRecommendedNumberOfTicksForXAxis(availableWidth: number): number;
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...
axis.getRecommendedNumberOfTicksForXAxis(1024);

// returns: 8
```

### <a name="getrecommendednumberofticksforyaxis"></a>getRecommendedNumberOfTicksForYAxis

ฟังก์ชันนี้ส่งกลับจำนวนของเครื่องหมายที่แนะนำตามความสูงของแผนภูมิ

```typescript
function getRecommendedNumberOfTicksForYAxis(availableWidth: number);
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...
axis.getRecommendedNumberOfTicksForYAxis(100);

// returns: 3
```

### <a name="getbestnumberofticks"></a>getBestNumberOfTicks

รับจำนวนเครื่องหมายที่เหมาะสมที่สุดโดยยึดตามค่าต่ำสุดและค่าเมตาดาต้าหน่วยวัดและจำนวนเครื่องหมายสูงสุด

```typescript
function getBestNumberOfTicks(
  min: number,
  max: number,
  valuesMetadata: DataViewMetadataColumn[],
  maxTickCount: number,
  isDateTime?: boolean
): number;
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...
var dataViewMetadataColumnWithIntegersOnly: powerbi.DataViewMetadataColumn[] = [
  {
    displayName: "col1",
    isMeasure: true,
    type: ValueType.fromDescriptor({ integer: true })
  },
  {
    displayName: "col2",
    isMeasure: true,
    type: ValueType.fromDescriptor({ integer: true })
  }
];
var actual = axis.getBestNumberOfTicks(
  0,
  3,
  dataViewMetadataColumnWithIntegersOnly,
  6
);

// returns: 4
```

### <a name="getticklabelmargins"></a>getTickLabelMargins

ฟังก์ชันนี้ส่งกลับระยะขอบสำหรับป้ายชื่อเครื่องหมาย

```typescript
function getTickLabelMargins(
  viewport: IViewport,
  yMarginLimit: number,
  textWidthMeasurer: ITextAsSVGMeasurer,
  textHeightMeasurer: ITextAsSVGMeasurer,
  axes: CartesianAxisProperties,
  bottomMarginLimit: number,
  properties: TextProperties,
  scrollbarVisible?: boolean,
  showOnRight?: boolean,
  renderXAxis?: boolean,
  renderY1Axis?: boolean,
  renderY2Axis?: boolean
): TickLabelMargins;
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

axis.getTickLabelMargins(
  plotArea,
  marginLimits.left,
  TextMeasurementService.measureSvgTextWidth,
  TextMeasurementService.estimateSvgTextHeight,
  axes,
  marginLimits.bottom,
  textProperties,
  /*scrolling*/ false,
  showY1OnRight,
  renderXAxis,
  renderY1Axis,
  renderY2Axis
);

// returns:  xMax, yLeft, yRight, stackHeigh;
```

### <a name="isordinal"></a>isOrdinal

ตรวจสอบว่าสตริงเป็น null หรือไม่ได้กำหนดหรือว่างเปล่า หรือไม่

```typescript
function isOrdinal(type: ValueTypeDescriptor): boolean;
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...
let type = ValueType.fromDescriptor({ misc: { barcode: true } });
axis.isOrdinal(type);

// returns: true
```

### <a name="isdatetime"></a>sDateTime

ตรวจสอบว่าค่าเป็น DateTime หรือไม่

```typescript
function isDateTime(type: ValueTypeDescriptor): boolean;
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

axis.isDateTime(ValueType.fromDescriptor({ dateTime: true }));

// returns: true
```

### <a name="getcategorythickness"></a>getCategoryThickness

ใช้สเกล D3 เพื่อรับความหนาของประเภทที่แท้จริง

```typescript
function getCategoryThickness(scale: any): number;
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

let range = [0, 100];
let domain = [0, 10];
let scale = d3.scale
  .linear()
  .domain(domain)
  .range(range);
let actualThickness = axis.getCategoryThickness(scale);
```

### <a name="invertordinalscale"></a>invertOrdinalScale

ฟังก์ชันนี้สลับสเกลลำดับ ถ้า x < scale.range()[0] จากนั้นจะมีการส่งกลับ scale.domain()[0]
มิฉะนั้นจะส่งกลับรายการที่ยิ่งใหญ่ที่สุดใน scale.domain() ที่ <= x

```typescript
function invertOrdinalScale(scale: d3.scale.Ordinal<any, any>, x: number);
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

let domain: number[] = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9],
  pixelSpan: number = 100,
  ordinalScale: d3.scale.ordinal = axis.createOrdinalScale(
    pixelSpan,
    domain,
    0.4
  );

axis.invertOrdinalScale(ordinalScale, 49);

// returns: 4
```

### <a name="findclosestxaxisindex"></a>findClosestXAxisIndex

ฟังก์ชันนี้จะค้นหาและส่งกลับดัชนีแกน x ที่ใกล้ที่สุด

```typescript
function findClosestXAxisIndex(
  categoryValue: number,
  categoryAxisValues: AxisHelperCategoryDataPoint[]
): number;
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

/**
 * Finds the index of the category of the given x coordinate given.
 * pointX is in non-scaled screen-space, and offsetX is in render-space.
 * offsetX does not need any scaling adjustment.
 * @param {number} pointX The mouse coordinate in screen-space, without scaling applied
 * @param {number} offsetX Any left offset in d3.scale render-space
 * @return {number}
 */
private findIndex(pointX: number, offsetX?: number): number {
    // we are using mouse coordinates that do not know about any potential CSS transform scale
    let xScale = this.scaleDetector.getScale().x;
    if (!Double.equalWithPrecision(xScale, 1.0, 0.00001)) {
        pointX = pointX / xScale;
    }
    if (offsetX) {
        pointX += offsetX;
    }

    let index = axis.invertScale(this.xAxisProperties.scale, pointX);
    if (this.data.isScalar) {
        // When we have scalar data the inverted scale produces a category value, so we need to search for the closest index.
        index = axis.findClosestXAxisIndex(index, this.data.categoryData);
    }

    return index;
}
```

### <a name="diffscaled"></a>diffScaled

ฟังก์ชันนี้จะคำนวณและส่งกลับค่าที่แตกต่างในสเกล

```typescript
function diffScaled(
  scale: d3.scale.Linear<any, any>,
  value1: any,
  value2: any
): number;
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

var scale: d3.scale.Linear<number, number>,
    range = [0, 999],
    domain = [0, 1, 2, 3, 4, 5, 6, 7, 8, 999];

scale = d3.scale.linear()
    .range(range)
    .domain(domain);

return axis.diffScaled(scale, 0, 0));

// returns: 0
```

### <a name="createdomain"></a>createDomain

ฟังก์ชันนี้จะสร้างโดเมนของค่าสำหรับแกน

```typescript
function createDomain(
  data: any[],
  axisType: ValueTypeDescriptor,
  isScalar: boolean,
  forcedScalarDomain: any[],
  ensureDomain?: NumberRange
): number[];
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

var cartesianSeries = [
  {
    data: [
      { categoryValue: 7, value: 11, categoryIndex: 0, seriesIndex: 0 },
      {
        categoryValue: 9,
        value: 9,
        categoryIndex: 1,
        seriesIndex: 0
      },
      {
        categoryValue: 15,
        value: 6,
        categoryIndex: 2,
        seriesIndex: 0
      },
      { categoryValue: 22, value: 7, categoryIndex: 3, seriesIndex: 0 }
    ]
  }
];

var domain = axis.createDomain(
  cartesianSeries,
  ValueType.fromDescriptor({ text: true }),
  false,
  []
);

// returns: [0, 1, 2, 3]
```

### <a name="getcategoryvaluetype"></a>getCategoryValueType

ฟังก์ชันนี้จะรับ `ValueType` ของคอลัมน์ประเภท ค่าเริ่มต้นคือ `Text` ถ้าไม่มีชนิด

```typescript
function getCategoryValueType(
  data: any[],
  axisType: ValueTypeDescriptor,
  isScalar: boolean,
  forcedScalarDomain: any[],
  ensureDomain?: NumberRange
): number[];
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

var cartesianSeries = [
  {
    data: [
      { categoryValue: 7, value: 11, categoryIndex: 0, seriesIndex: 0 },
      {
        categoryValue: 9,
        value: 9,
        categoryIndex: 1,
        seriesIndex: 0
      },
      {
        categoryValue: 15,
        value: 6,
        categoryIndex: 2,
        seriesIndex: 0
      },
      { categoryValue: 22, value: 7, categoryIndex: 3, seriesIndex: 0 }
    ]
  }
];

axis.getCategoryValueType(
  cartesianSeries,
  ValueType.fromDescriptor({ text: true }),
  false,
  []
);

// returns: [0, 1, 2, 3]
```

### <a name="createaxis"></a>createAxis

ฟังก์ชันนี้สร้างแกน D3 รวมทั้งสเกล สามารถอยู่ในแนวตั้งหรือแนวนอนและทั้งวันที่เวลาตัวเลขหรือข้อความ

```typescript
function createAxis(options: CreateAxisOptions): IAxisProperties;
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";
// ...

var dataPercent = [0.0, 0.33, 0.49];

var formatStringProp: powerbi.DataViewObjectPropertyIdentifier = {
  objectName: "general",
  propertyName: "formatString"
};
let metaDataColumnPercent: powerbi.DataViewMetadataColumn = {
  displayName: "Column",
  type: ValueType.fromDescriptor({ numeric: true }),
  objects: {
    general: {
      formatString: "0 %"
    }
  }
};

var os = axis.createAxis({
  pixelSpan: 100,
  dataDomain: [dataPercent[0], dataPercent[2]],
  metaDataColumn: metaDataColumnPercent,
  formatString: valueFormatter.getFormatString(
    metaDataColumnPercent,
    formatStringProp
  ),
  outerPadding: 0.5,
  isScalar: true,
  isVertical: true
});
```

### <a name="applycustomizeddomain"></a>applyCustomizedDomain

ฟังก์ชันนี้จะตั้งค่าโดเมนแบบกำหนดเองแต่ไม่เปลี่ยนแปลงเมื่อไม่มีการตั้งค่า

```typescript
function applyCustomizedDomain(customizedDomain, forcedDomain: any[]): any[];
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

let customizedDomain = [undefined, 20],
  existingDomain = [0, 10];

axis.applyCustomizedDomain(customizedDomain, existingDomain);

// returns: {0:0, 1:20}
```

### <a name="combinedomain"></a>combineDomain

ฟังก์ชันนี้รวมโดเมนที่บังคับกับโดเมนจริงถ้าหนึ่งในค่าถูกตั้งค่าไว้
ForcedDomain อยู่ในลำดับความสำคัญแรก ขยายโดเมนถ้าจุดอ้างอิงใด ๆ มที่จำเป็นต้องใช้

```typescript
function combineDomain(
  forcedDomain: any[],
  domain: any[],
  ensureDomain?: NumberRange
): any[];
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

let forcedYDomain = this.valueAxisProperties
  ? [this.valueAxisProperties["secStart"], this.valueAxisProperties["secEnd"]]
  : null;

let xDomain = [minX, maxX];

axis.combineDomain(forcedYDomain, xDomain, ensureXDomain);
```

### <a name="poweroften"></a>powerOfTen

ฟังก์ชันนี้จะระบุว่าตัวเลขคือยกกำลัง 10 หรือไม่

```typescript
function powerOfTen(d: any): boolean;
```

ตัวอย่าง:

```typescript
import { axis } from "powerbi-visuals-utils-chartutils";
// ...

axis.powerOfTen(10);

// returns: true
```

## <a name="datalabelmanager"></a>DataLabelManager

`DataLabelManager` ช่วยในการสร้างและรักษาป้ายชื่อ ซึ่งจัดเรียงองค์ประกอบป้ายชื่อโดยใช้จุดยึดหรือสี่เหลี่ยมผืนผ้า สามารถตรวจพบการตัดกัน เพื่อจัดตำแหน่งหรือซ่อนองค์ประกอบได้โดยอัตโนมัติ

คลาส `DataLabelManager` มีวิธีต่อไปนี้:

## <a name="hidecollidedlabels"></a>hideCollidedLabels

วิธีนี้จะจัดเรียงตำแหน่งป้ายชื่อและการมองเห็นบนพื้นที่ทำงานตามขนาดป้ายชื่อและการซ้อนทับกัน

```typescript
function hideCollidedLabels(
  viewport: IViewport,
  data: any[],
  layout: any,
  addTransform: boolean = false
): LabelEnabledDataPoint[];
```

ตัวอย่าง:

```typescript
let dataLabelManager = new DataLabelManager();
let filteredData = dataLabelManager.hideCollidedLabels(
  this.viewport,
  values,
  labelLayout,
  true
);
```

## <a name="isvalid"></a>IsValid

วิธีการแบบคงที่นี้จะตรวจสอบว่าสี่เหลี่ยมที่ให้ไว้ถูกต้องหรือไม่ (มีความกว้างและความสูงเป็นบวก)

```typescript
function isValid(rect: IRect): boolean;
```

ตัวอย่าง:

```typescript
let rectangle = {
  left: 150,
  top: 130,
  width: 120,
  height: 110
};

DataLabelManager.isValid(rectangle);

// returns: true
```

## <a name="datalabelutils"></a>DataLabelUtils

`DataLabelUtils` ให้ยูทิลิตี้จัดการป้ายชื่อข้อมูล

โมดูลมอบฟังก์ชัน อินเตอร์เฟส และคลาสต่อไปนี้:

### <a name="getlabelprecision"></a>getLabelPrecision

ฟังก์ชันนี้จะคำนวณความแม่นยำจากรูปแบบที่กำหนด

```typescript
function getLabelPrecision(precision: number, format: string): number;
```

### <a name="getlabelformattedtext"></a>getLabelFormattedText

ฟังก์ชันนี้ส่งกลับความแม่นยำของรูปแบบจากรูปแบบที่กำหนด

```typescript
function getLabelFormattedText(options: LabelFormattedTextOptions): string;
```

ตัวอย่าง:

```typescript
import { dataLabelUtils } from "powerbi-visuals-utils-chartutils";
// ...

let options: LabelFormattedTextOptions = {
  text: "some text",
  fontFamily: "sans",
  fontSize: "15",
  fontWeight: "normal"
};

dataLabelUtils.getLabelFormattedText(options);
```

### <a name="enumeratedatalabels"></a>enumerateDataLabels

ฟังก์ชันนี้จะส่งกลับ VisualObjectInstance สำหรับป้ายชื่อข้อมูล

```typescript
function enumerateDataLabels(
  options: VisualDataLabelsSettingsOptions
): VisualObjectInstance;
```

### <a name="enumeratecategorylabels"></a>enumerateCategoryLabels

ฟังก์ชันนี้เพิ่ม VisualObjectInstance สำหรับป้ายชื่อข้อมูลประเภทไปยังวัตถุการแจงนับ

```typescript
function enumerateCategoryLabels(
  enumeration: VisualObjectInstanceEnumerationObject,
  dataLabelsSettings: VisualDataLabelsSettings,
  withFill: boolean,
  isShowCategory: boolean = false,
  fontSize?: number
): void;
```

### <a name="createcolumnformattercachemanager"></a>createColumnFormatterCacheManager

ฟังก์ชันนี้ส่งกลับตัวจัดการแคชที่ช่วยให้สามารถเข้าถึงป้ายชื่อที่จัดรูปแบบได้อย่างรวดเร็ว

```typescript
function createColumnFormatterCacheManager(): IColumnFormatterCacheManager;
```

ตัวอย่าง:

```typescript
import { dataLabelUtils } from "powerbi-visuals-utils-chartutils";
// ...

let value: number = 200000;

labelSettings.displayUnits = 1000000;
labelSettings.precision = 1;

let formattersCache = DataLabelUtils.createColumnFormatterCacheManager();
let formatter = formattersCache.getOrCreate(null, labelSettings);
let formattedValue = formatter.format(value);

// formattedValue == "0.2M"
```

## <a name="legend-service"></a>บริการคำอธิบายแผนภูมิ

บริการ `Legend` มีอินเทอร์เฟสตัวช่วยเหลือสำหรับการสร้างและการจัดการคำอธิบายแผนภูมิ PBI สำหรับการแสดงผลแบบกำหนดเอง

โมดูลมอบฟังก์ชันและอินเทอร์เฟซต่อไปนี้:

### <a name="createlegend"></a>createLegend

ฟังก์ชันผู้ช่วยเหลือนี้ลดความซับซ้อนของการสร้างคำอธิบายแผนภูมิแบบกำหนดเองของ Power BI

```typescript
function createLegend(
  legendParentElement: HTMLElement, // top visual element, container in which legend will be created
  interactive: boolean, // indicates that legend should be interactive
  interactivityService: IInteractivityService, // reference to IInteractivityService interface which need to create legend click events
  isScrollable: boolean = false, // indicates that legend could be scrollable or not
  legendPosition: LegendPosition = LegendPosition.Top // Position of the legend inside of legendParentElement container
): ILegend;
```

ตัวอย่าง:

```typescript
public constructor(options: VisualConstructorOptions) {
    this.visualInitOptions = options;
    this.layers = [];

    var element = this.element = options.element;
    var viewport = this.currentViewport = options.viewport;
    var hostServices = options.host;

    //... some other init calls

    if (this.behavior) {
        this.interactivityService = createInteractivityService(hostServices);
    }
    this.legend = createLegend(
        element,
        options.interactivity && options.interactivity.isInteractiveLegend,
        this.interactivityService,
        true);
}
```

### <a name="ilegend"></a>ILegend

อินเทอร์เฟซนี้ใช้วิธีการทั้งหมดที่จำเป็นสำหรับการสร้างคำอธิบายแผนภูมิ

```typescript
export interface ILegend {
  getMargins(): IViewport;
  isVisible(): boolean;
  changeOrientation(orientation: LegendPosition): void; // processing legend orientation
  getOrientation(): LegendPosition; // get information about current legend orientation
  drawLegend(data: LegendData, viewport: IViewport); // all legend rendering code is placing here
  /**
   * Reset the legend by clearing it
   */
  reset(): void;
}
```

### <a name="drawlegend"></a>drawLegend

ฟังก์ชันนี้วัดความสูงของข้อความด้วยคุณสมบัติข้อความ SVG ที่กำหนด

```typescript
function drawLegend(data: LegendData, viewport: IViewport): void;
```

ตัวอย่าง:

```typescript
private renderLegend(): void {
    if (!this.isInteractive) {
        let legendObjectProperties = this.data.legendObjectProperties;
        if (legendObjectProperties) {
            let legendData = this.data.legendData;
            LegendData.update(legendData, legendObjectProperties);
            let position = <string>legendObjectProperties[legendProps.position];
            if (position)
                this.legend.changeOrientation(LegendPosition[position]);

            this.legend.drawLegend(legendData, this.parentViewport);
        } else {
            this.legend.changeOrientation(LegendPosition.Top);
            this.legend.drawLegend({ dataPoints: [] }, this.parentViewport);
        }
    }
}
```

## <a name="next-steps"></a>ขั้นตอนถัดไป

- [อ่านวิธีการใช้ InteractivityUtils เพื่อเพิ่มการเลือกลงในภาพ Power BI](utils-interactivity-selections.md)

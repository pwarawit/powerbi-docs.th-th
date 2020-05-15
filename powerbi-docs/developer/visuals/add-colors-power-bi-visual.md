---
title: เพิ่มสีลงในวิชวล Power BI ของคุณ
description: บทความนี้อธิบายวิธีการเพิ่มสีลงในวิชวล Power BI ของคุณและวิธีการจัดการกับจุดข้อมูลสำหรับวิชวลกับสี
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 03/27/2020
ms.openlocfilehash: 3f3574545d82ac11c762b7011afdc49cbe855224
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83141150"
---
# <a name="add-colors-to-your-power-bi-visuals"></a>เพิ่มสีลงในวิชวล Power BI ของคุณ

บทความนี้อธิบายวิธีการเพิ่มสีลงในวิชวลของคุณและวิธีการจัดการจุดข้อมูลสำหรับวิชวลสี

`IVisualHost` แสดงสีเป็นซึ่งหนึ่งในบริการ
โค้ดตัวอย่างในบทความนี้จะปรับเปลี่ยน [ วิชวล SampleBarChart](https://github.com/microsoft/PowerBI-visuals-sampleBarChart)
สำหรับโค้ดแหล่งที่มา โปรดดู [barChart.ts](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/master/src/barChart.ts)

หากต้องการเริ่มต้นสร้างวิชวล โปรดดู [พัฒนาวิชวล Power BI](custom-visual-develop-tutorial.md)

## <a name="add-color-to-data-points"></a>เพิ่มสีไปยังจุดข้อมูล

สีที่แตกต่างกันแสดงแทนแต่ละจุดข้อมูล
เพิ่มสีไปยัง `BarChartDataPoint`อินเทอร์เฟซ  ดังในตัวอย่างต่อไปนี้:

```typescript
/**
 * Interface for BarChart data points.
 *
 * @interface
 * @property {number} value    - Data value for point.
 * @property {string} category - Corresponding category of data value.
 * @property {string} color    - Color corresponding to data point.
 */
interface BarChartDataPoint {
    value: number;
    category: string;
    color: string;
};
```

## <a name="use-the-color-palette-service"></a>ใช้บริการจานสี

บริการ `colorPalette` จะจัดการสีที่ใช้ในวิชวลของคุณ
อินสแตนซ์ของบริการที่พร้อมใช้งานบน `IVisualHost`

กำหนดได้ในวิธีการ `update`

```typescript
constructor(options: VisualConstructorOptions) {
        this.host = options.host; // host: IVisualHost
        ...
    }

public update(options: VisualUpdateOptions) {

    let colorPalette: IColorPalette = host.colorPalette;
    ...
}
```

## <a name="assigning-color-to-data-points"></a>กำหนดสีให้กับจุดข้อมูล

ถัดไป ให้ระบุ `dataPoints`
ในตัวอย่างนี้ แต่ละ `dataPoints` ได้รวมค่า หมวดหมู่และสีไว้
นอกจากนี้ `dataPoints` ยังมีคุณสมบัติอื่นๆ

ใน `SampleBarChart` วิธีการ `visualTransform` จะย่อส่วนการคำนวณ `dataPoints`
วิธีการดังกล่าวเป็นส่วนหนึ่งของแผนภูมิแท่ง viewmodel
เนื่องจากวิธีการนั้นซ้ำผ่าน `dataPoints`การคำนวณใน`visualTransform` จึงเป็นสถานที่ที่เหมาะสมที่จะกำหนดสี ดังเช่นในโค้ดต่อไปนี้:

```typescript

public update(options: VisualUpdateOptions) {
    ....
    let viewModel: BarChartViewModel = visualTransform(options, this.host);
    ....
}

function visualTransform(options: VisualUpdateOptions, host: IVisualHost): BarChartViewModel {
    let colorPalette: IColorPalette = host.colorPalette; // host: IVisualHost
    for (let i = 0, len = Math.max(category.values.length, dataValue.values.length); i < len; i++) {
        barChartDataPoints.push({
            category: category.values[i],
            value: dataValue.values[i],
            color: colorPalette.getColor(category.values[i]).value,
        });
    }
}
```

จากนั้นใช้ข้อมูลจาก `dataPoints` บน [d3](https://d3js.org/)-การเลือก `barSelection` ภายในวิธีการ `update`:

```typescript
// This code is actual for d3 v5
// in d3 v5 for this case we should use merge() after enter() and apply changes on barSelectionMerged
this.barSelection = this.barContainer
    .selectAll('.bar')
    .data(this.barDataPoints);

const barSelectionMerged = this.barSelection
    .enter()
    .append('rect')
    .merge(<any>this.barSelection);

barSelectionMerged.classed('bar', true);

barSelectionMerged
.attr("width", xScale.bandwidth())
.attr("height", d => height - yScale(<number>d.value))
.attr("y", d => yScale(<number>d.value))
.attr("x", d => xScale(d.category))
.style("fill", (dataPoint: BarChartDataPoint) => dataPoint.color)
.style("stroke", (dataPoint: BarChartDataPoint) => dataPoint.strokeColor)
.style("stroke-width", (dataPoint: BarChartDataPoint) => `${dataPoint.strokeWidth}px`);

this.barSelection
    .exit()
    .remove();
```

## <a name="next-steps"></a>ขั้นตอนถัดไป

ในการเรียนรู้เพิ่มเติมเกี่ยวกับ Power BI ดูที่ [ความสามารถและคุณสมบัติของวิชวล Power BI](capabilities.md)

หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับการพัฒนาวิชวล Power BI โปรดดู [วิธีการแก้จุดบกพร่องของวิชวล Power BI](visuals-how-to-debug.md) และ [การแก้ไขปัญหา Power BI](power-bi-custom-visuals-troubleshoot.md)

---
title: การไฮไลต์
description: การเลือกจุดข้อมูลที่ไฮไลต์ใน Power BI Visuals
author: zBritva
ms.author: v-ilgali
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 10/31/2019
ms.openlocfilehash: bf5cd8d8ae649071b3c9cc7243f87ac3cc316c3b
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/02/2019
ms.locfileid: "74695415"
---
# <a name="highlight-data-points-in-power-bi-visuals"></a>ไฮไลต์จุดข้อมูลใน Power BI Visuals

โดยค่าเริ่มต้นเมื่อใดก็ตามที่มีการเลือกองค์ประกอบ อาร์เรย์ `values` ในวัตถุ `dataView` จะถูกกรองให้เป็นเพียงค่าที่เลือกเท่านั้น ซึ่งจะทำให้วิชวลอื่น ๆ ทั้งหมดในหน้าแสดงเป็นเพียงข้อมูลที่เลือกเท่านั้น

![ไฮไลต์ `dataview` ในลักษณะตามค่าเริ่มต้น](./media/highlight-dataview.png)

หากคุณตั้งค่าคุณสมบัติ `supportsHighlight` ใน `capabilities.json` เป็น `true` คุณจะได้รับอาร์เรย์ `values` แบบไม่มีการกรองเต็มรูปแบบพร้อมกับอาร์เรย์ `highlights` อาร์เรย์ `highlights` จะมีความยาวเท่ากับอาร์เรย์ค่าและค่าที่ไม่ได้เลือกจะถูกตั้งค่าเป็น `null` เมื่อเปิดใช้งานคุณสมบัตินี้แล้ว จึงเป็นความรับผิดชอบของวิชวลในการไฮไลต์ข้อมูลที่เหมาะสมโดยการเปรียบเทียบอาร์เรย์ `values` กับอาร์เรย์ `highlights`

![' dataview ' สนับสนุนการไฮไลต์](./media/highlight-dataview-supports.png)

ในตัวอย่าง คุณจะสังเกตเห็นว่ามี 1 แถบที่ถูกเลือก และเป็นเฉพาะค่าในอาร์เรย์ไฮไลต์ นอกจากนี้ สิ่งสำคัญคือต้องทราบว่าอาจมีตัวเลือกหลายรายการและการไฮไลต์บางส่วนด้วย ค่าที่ไฮไลต์ไว้จะแสดงในมุมมองข้อมูล

> [!Note]
> การแมปมุมมองข้อมูลแบบตารางไม่สนับสนุนคุณลักษณะการไฮไลท์

## <a name="highlight-data-points-with-categorical-data-view-mapping"></a>ไฮไลต์จุดข้อมูลด้วยการแมปมุมมองข้อมูลตามประเภท

วิชวลที่มีการแมปมุมมองข้อมูลตามประเภทมี`capabilities.json`พร้อมด้วย`"supportsHighlight": true`พารามิเตอร์ ตัวอย่างเช่น:

```json
{
    "dataRoles": [
        {
            "displayName": "Category",
            "name": "category",
            "kind": "Grouping"
        },
        {
            "displayName": "Value",
            "name": "value",
            "kind": "Measure"
        }
    ],
    "dataViewMappings": [
        {
            "categorical": {
                "categories": {
                    "for": {
                        "in": "category"
                    }
                },
                "values": {
                    "for": {
                        "in": "value"
                    }
                }
            }
        }
    ],
    "supportsHighlight": true
}
```

รหัสแหล่งข้อมูลของวิชวลเริ่มต้นหลังจากลบรหัสที่ไม่จำเป็นจะมีลักษณะดังนี้:

```typescript
"use strict";

// ... default imports list

import DataViewCategorical = powerbi.DataViewCategorical;
import DataViewCategoryColumn = powerbi.DataViewCategoryColumn;
import PrimitiveValue = powerbi.PrimitiveValue;
import DataViewValueColumn = powerbi.DataViewValueColumn;

import { VisualSettings } from "./settings";

export class Visual implements IVisual {
    private target: HTMLElement;
    private settings: VisualSettings;

    constructor(options: VisualConstructorOptions) {
        console.log('Visual constructor', options);
        this.target = options.element;
        this.host = options.host;

    }

    public update(options: VisualUpdateOptions) {
        this.settings = Visual.parseSettings(options && options.dataViews && options.dataViews[0]);
        console.log('Visual update', options);

    }

    private static parseSettings(dataView: DataView): VisualSettings {
        return <VisualSettings>VisualSettings.parse(dataView);
    }

    /**
     * This function gets called for each of the objects defined in the capabilities files and allows you to select which of the
     * objects and properties you want to expose to the users in the property pane.
     *
     */
    public enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstance[] | VisualObjectInstanceEnumerationObject {
        return VisualSettings.enumerateObjectInstances(this.settings || VisualSettings.getDefault(), options);
    }
}
```

นำเข้าอินเทอร์เฟสที่จำเป็นเพื่อประมวลผลข้อมูลจาก Power BI:

```typescript
import DataViewCategorical = powerbi.DataViewCategorical;
import DataViewCategoryColumn = powerbi.DataViewCategoryColumn;
import PrimitiveValue = powerbi.PrimitiveValue;
import DataViewValueColumn = powerbi.DataViewValueColumn;
```

สร้างองค์ประกอบ`div`ระดับสูงสำหรับค่าหมวดหมู่:

```typescript
export class Visual implements IVisual {
    private target: HTMLElement;
    private settings: VisualSettings;

    private div: HTMLDivElement; // new property

    constructor(options: VisualConstructorOptions) {
        console.log('Visual constructor', options);
        this.target = options.element;
        this.host = options.host;

        // create div element
        this.div = document.createElement("div");
        this.div.classList.add("vertical");
        this.target.appendChild(this.div);

    }
    // ...
}
```

ล้างเนื้อหาขององค์ประกอบ div ก่อนที่จะแสดงข้อมูลใหม่:

```typescript
// ...
public update(options: VisualUpdateOptions) {
    this.settings = Visual.parseSettings(options && options.dataViews && options.dataViews[0]);
    console.log('Visual update', options);

    while (this.div.firstChild) {
        this.div.removeChild(this.div.firstChild);
    }
    // ...
}
```

รับค่าหมวดหมู่และหน่วยวัดจากวัตถุ `dataView`:

```typescript
public update(options: VisualUpdateOptions) {
    this.settings = Visual.parseSettings(options && options.dataViews && options.dataViews[0]);
    console.log('Visual update', options);

    while (this.div.firstChild) {
        this.div.removeChild(this.div.firstChild);
    }

    const dataView: DataView = options.dataViews[0];
    const categoricalDataView: DataViewCategorical = dataView.categorical;
    const categories: DataViewCategoryColumn = categoricalDataView.categories[0];
    const categoryValues = categories.values;

    const measures: DataViewValueColumn = categoricalDataView.values[0];
    const measureValues = measures.values;
    const measureHighlights = measures.highlights;
    // ...
}
```

โดยที่ `categoryValues` คืออาร์เรย์ของค่าหมวดหมู่ `measureValues` เป็นอาร์เรย์ของหน่วยวัดและ `measureHighlights` คือส่วนที่ไฮไลต์ของค่า

> [!Note]
> ค่าของคุณสมบัติ `measureHighlights` อาจน้อยกว่าค่าของคุณสมบัติ `categoryValues`
> หมายความว่ามีการไฮไลต์ค่าบางส่วน

ระบุอาร์เรย์ `categoryValues` และรับค่าและไฮไลต์ที่สอดคล้องกัน:

```typescript
// ...
const measureHighlights = measures.highlights;

categoryValues.forEach((category: PrimitiveValue, index: number) => {
    const measureValue = measureValues[index];
    const measureHighlight = measureHighlights && measureHighlights[index] ? measureHighlights[index] : null;
    console.log(category, measureValue, measureHighlight);

});
```

สร้างองค์ประกอบ `div` และ `p` เพื่อแสดงและดูภาพค่ามุมมองข้อมูลใน DOM ของวิชวล:

```typescript
categoryValues.forEach((category: PrimitiveValue, index: number) => {
    const measureValue = measureValues[index];
    const measureHighlight = measureHighlights && measureHighlights[index] ? measureHighlights[index] : null;
    console.log(category, measureValue, measureHighlight);

    // div element. it contains elements to display values and visualize value as progress bar
    let div = document.createElement("div");
    div.classList.add("horizontal");
    this.div.appendChild(div);

    // div element to vizualize value of measure
    let barValue = document.createElement("div");
    barValue.style.width = +measureValue * 10 + "px";
    barValue.style.display = "flex";
    barValue.classList.add("value");

    // element to display category value
    let bp = document.createElement("p");
    bp.innerText = category.toString();

    // div element to vizualize highlight of measure
    let barHighlight = document.createElement("div");
    barHighlight.classList.add("highlight")
    barHighlight.style.backgroundColor = "blue";
    barHighlight.style.width = +measureHighlight * 10 + "px";

    // element to display highlighted value of measure
    let p = document.createElement("p");
    p.innerText = `${measureHighlight}/${measureValue}`;
    barHighlight.appendChild(bp);

    div.appendChild(barValue);

    barValue.appendChild(barHighlight);
    div.appendChild(p);
});
```

ใช้ลักษณะที่จำเป็นสำหรับองค์ประกอบเพื่อใช้ `flex box` และกำหนดสีสำหรับองค์ประกอบ div:

```css
div.vertical {
    display: flex;
    flex-direction: column;
}

div.horizontal {
    display: flex;
    flex-direction: row;
}

div.highlight {
    background-color: blue
}

div.value {
    background-color: red;
    display: flex;
}
```

ในผลลัพธ์ คุณควรมีมุมมองของวิชวลดังต่อไปนี้

![วิชวลที่มีการแมปมุมมองข้อมูลตามประเภทและการไฮไลต์](./media/dev-categorical-visual-highlight-demo.gif)

## <a name="highlight-data-points-with-matrix-data-view-mapping"></a>ไฮไลต์จุดข้อมูลด้วยการแมปมุมมองข้อมูลแบบเมทริกซ์

วิชวลที่มีการแมปมุมมองข้อมูลแบบเมทริกซ์มี`capabilities.json`พร้อมด้วย`"supportsHighlight": true`พารามิเตอร์ ตัวอย่างเช่น:

```json
{
    "dataRoles": [
        {
            "displayName": "Columns",
            "name": "columns",
            "kind": "Grouping"
        },
        {
            "displayName": "Rows",
            "name": "rows",
            "kind": "Grouping"
        },
        {
            "displayName": "Value",
            "name": "value",
            "kind": "Measure"
        }
    ],
    "dataViewMappings": [
        {
            "matrix": {
                "columns": {
                    "for": {
                        "in": "columns"
                    }
                },
                "rows": {
                    "for": {
                        "in": "rows"
                    }
                },
                "values": {
                    "for": {
                        "in": "value"
                    }
                }
            }
        }
    ],
    "supportsHighlight": true
}
```

ข้อมูลตัวอย่างในการสร้างลำดับชั้นสำหรับการแมปมุมมองข้อมูลแบบเมทริกซ์:

|   Row1   |   Row2   |   Row3   |   คอลัมน์1   |   คอลัมน์2   |   คอลัมน์3   |   ค่า   |
|-----|-----|------|-------|-------|-------|-------|
|   R1   |   R11   |   R111   |   C1   |   C11   |   C111   |   1   |
|   R1   |   R11   |   R112   |   C1   |   C11   |   C112   |   2   |
|   R1   |   R11   |   R113   |   C1   |   C11   |   C113   |   3   |
|   R1   |   R12   |   R121   |   C1   |   C12   |   C121   |   4   |
|   R1   |   R12   |   R122   |   C1   |   C12   |   C122   |   5   |
|   R1   |   R12   |   R123   |   C1   |   C12   |   C123   |   6   |
|   R1   |   R13   |   R131   |   C1   |   C13   |   C131   |   7   |
|   R1   |   R13   |   R132   |   C1   |   C13   |   C132   |   8   |
|   R1   |   R13   |   R133   |   C1   |   C13   |   C133   |   9   |
|   R2   |   R21   |   R211   |   C2   |   C21   |   C211   |   10   |
|   R2   |   R21   |   R212   |   C2   |   C21   |   C212   |   11   |
|   R2   |   R21   |   R213   |   C2   |   C21   |   C213   |   12   |
|   R2   |   R22   |   R221   |   C2   |   C22   |   C221   |   13   |
|   R2   |   R22   |   R222   |   C2   |   C22   |   C222   |   14   |
|   R2   |   R22   |   R223   |   C2   |   C22   |   C223   |   16   |
|   R2   |   R23   |   R231   |   C2   |   C23   |   C231   |   17   |
|   R2   |   R23   |   R232   |   C2   |   C23   |   C232   |   18   |
|   R2   |   R23   |   R233   |   C2   |   C23   |   C233   |   19   |

สร้างโครงการวิชวลเริ่มต้นและใช้ตัวอย่างของ `capabilities.json`

รหัสแหล่งข้อมูลของวิชวลเริ่มต้นหลังจากลบรหัสที่ไม่จำเป็นจะมีลักษณะ:

```typescript
"use strict";

// ... default imports

import { VisualSettings } from "./settings";

export class Visual implements IVisual {
    private target: HTMLElement;
    private settings: VisualSettings;


    constructor(options: VisualConstructorOptions) {
        console.log('Visual constructor', options);
        this.target = options.element;
        this.host = options.host;
    }

    public update(options: VisualUpdateOptions) {
        this.settings = Visual.parseSettings(options && options.dataViews && options.dataViews[0]);
        console.log('Visual update', options);

    }

    private static parseSettings(dataView: DataView): VisualSettings {
        return <VisualSettings>VisualSettings.parse(dataView);
    }

    /**
     * This function gets called for each of the objects defined in the capabilities files and allows you to select which of the
     * objects and properties you want to expose to the users in the property pane.
     *
     */
    public enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstance[] | VisualObjectInstanceEnumerationObject {
        return VisualSettings.enumerateObjectInstances(this.settings || VisualSettings.getDefault(), options);
    }
}
```

นำเข้าอินเทอร์เฟสที่จำเป็นเพื่อประมวลผลข้อมูลจาก Power BI:

```typescript
import DataViewMatrix = powerbi.DataViewMatrix;
import DataViewMatrixNode = powerbi.DataViewMatrixNode;
import DataViewHierarchyLevel = powerbi.DataViewHierarchyLevel;
```

สร้างองค์ประกอบ `div` สองแบบสำหรับเค้าโครงวิชวล:

```typescript
constructor(options: VisualConstructorOptions) {
    // ...
    this.rowsDiv = document.createElement("div");
    this.target.appendChild(this.rowsDiv);

    this.colsDiv = document.createElement("div");
    this.target.appendChild(this.colsDiv);
    this.target.style.overflowY = "auto";
}
```

ตรวจสอบข้อมูลในวิธีการ `update` เพื่อให้แน่ใจว่าวิชวลได้รับข้อมูล:

```typescript
public update(options: VisualUpdateOptions) {
    this.settings = Visual.parseSettings(options && options.dataViews && options.dataViews[0]);
    console.log('Visual update', options);

    const dataView: DataView = options.dataViews[0];
    const matrixDataView: DataViewMatrix = dataView.matrix;

    if (!matrixDataView ||
        !matrixDataView.columns ||
        !matrixDataView.rows ) {
        return
    }
    // ...
}
```

ล้างเนื้อหาขององค์ประกอบ `div` ก่อนที่จะแสดงข้อมูลใหม่:

```typescript
public update(options: VisualUpdateOptions) {
    // ...

    // remove old elements
    // to better performance use D3js pattern:
    // https://d3js.org/#enter-exit
    while (this.rowsDiv.firstChild) {
        this.rowsDiv.removeChild(this.rowsDiv.firstChild);
    }
    const prow = document.createElement("p");
    prow.innerText = "Rows";
    this.rowsDiv.appendChild(prow);

    while (this.colsDiv.firstChild) {
        this.colsDiv.removeChild(this.colsDiv.firstChild);
    }
    const pcol = document.createElement("p");
    pcol.innerText = "Columns";
    this.colsDiv.appendChild(pcol);
    // ...
}
```

สร้างฟังก์ชัน `treeWalker` เพื่อสำรวจโครงสร้างข้อมูลแบบเมทริกซ์:

```typescript
public update(options: VisualUpdateOptions) {
    // ...
    const treeWalker = (matrixNode: DataViewMatrixNode, index: number, levels: DataViewHierarchyLevel[], div: HTMLDivElement)  => {

    }
    // ...
}
```

โดยที่ `matrixNode` คือโหนดปัจจุบัน `levels` คือคอลัมน์เมตาดาต้าของระดับลำดับชั้นนี้ `div` - องค์ประกอบหลักสำหรับองค์ประกอบ HTML ย่อย

`treeWalker` คือฟังก์ชันแบบเรียกใช้ซ้ำ จำเป็นต้องสร้างองค์ประกอบ `div` และ `p` สำหรับข้อความเป็นส่วนหัว และเรียกใช้ฟังก์ชันสำหรับองค์ประกอบย่อยของโหนด:

```typescript
public update(options: VisualUpdateOptions) {
    // ...
    const treeWalker = (matrixNode: DataViewMatrixNode, index: number, levels: DataViewHierarchyLevel[], div: HTMLDivElement)  => {
        // ...

        if (matrixNode.children) {
            const childDiv = document.createElement("div");
            childDiv.classList.add("vertical");
            div.appendChild(childDiv);

            const p = document.createElement("p");
            const level = levels[matrixNode.level]; // get current level column metadata from current node
            p.innerText = level.sources[level.sources.length - 1].displayName; // get column name from metadata

            childDiv.appendChild(p); // add paragraph element to div element
            matrixNode.children.forEach((node, index) => treeWalker(node, levels, childDiv, ++levelIndex));
        }
    }
    // ...
}
```

เรียกใช้ฟังก์ชันสำหรับองค์ประกอบระดับสูงของคอลัมน์และแถวของโครงสร้างมุมมองข้อมูลแบบเมทริกซ์:

```typescript
public update(options: VisualUpdateOptions) {
    // ...
    const treeWalker = (matrixNode: DataViewMatrixNode, index: number, levels: DataViewHierarchyLevel[], div: HTMLDivElement)  => {
        // ...
    }
    // ...
    // remove old elements
    // ...

    // ...
    const rowRoot: DataViewMatrixNode = matrixDataView.rows.root;
    rowRoot.children.forEach((node) => treeWalker(node, matrixDataView.rows.levels, this.rowsDiv));

    const colRoot = matrixDataView.columns.root;
    colRoot.children.forEach((node) => treeWalker(node, matrixDataView.columns.levels, this.colsDiv));
}
```

สร้าง selectionID สำหรับโหนดและสร้างปุ่มเพื่อแสดงโหนด:

```typescript
public update(options: VisualUpdateOptions) {
    // ...
    const treeWalker = (matrixNode: DataViewMatrixNode, index: number, levels: DataViewHierarchyLevel[], div: HTMLDivElement)  => {
        const selectionID: ISelectionID = this.host.createSelectionIdBuilder()
            .withMatrixNode(matrixNode, levels)
            .createSelectionId();

        let nodeBlock = document.createElement("button");
        nodeBlock.innerText = matrixNode.value.toString();

        nodeBlock.addEventListener("click", (event) => {
            // call select method in the selection manager
            this.selectionManager.select(selectionID);
        });

        nodeBlock.addEventListener("contextmenu", (event) => {
            // call showContextMenu method to display context menu on the visual
            this.selectionManager.showContextMenu(selectionID, {
                x: event.clientX,
                y: event.clientY
            });
            event.preventDefault();
        });
        // ...
    }
    // ...
}
```

ขั้นตอนหลักของการใช้การไฮไลต์คือการประมวลผลอาร์เรย์เพิ่มเติมของค่า

หากคุณตรวจสอบวัตถุของโหนดเทอร์มินัล คุณจะเห็นว่าอาร์เรย์ค่ามีคุณสมบัติสองอย่างคือ ค่าและไฮไลต์:

```javascript
JSON.stringify(options.dataViews[0].matrix.rows.root.children[0].children[0].children[0], null, " ");
```

```json
{
 "level": 2,
 "levelValues": [
  {
   "value": "R233",
   "levelSourceIndex": 0
  }
 ],
 "value": "R233",
 "identity": {
  "identityIndex": 2
 },
 "values": {
  "0": {
   "value": null,
   "highlight": null
  },
  "1": {
   "value": 19,
   "highlight": 19
  }
 }
}
```

โดยที่คุณสมบัติ `value` แสดงค่าของโหนดโดยไม่ต้องใช้ตัวเลือกจากวิชวลอื่น ๆ และคุณสมบัติการไฮไลต์แสดงให้เห็นว่าเป็นส่วนหนึ่งของข้อมูลที่ถูกไฮไลต์

> [!Note]
> ค่าของคุณสมบัติ `highlight` อาจน้อยกว่าค่าของคุณสมบัติ `value`
> หมายความว่ามีการไฮไลต์ค่าบางส่วน

เพิ่มรหัสเพื่อประมวลผลอาร์เรย์ `values` ของโหนดถ้าแสดง:

```typescript
public update(options: VisualUpdateOptions) {
    // ...
    const treeWalker = (matrixNode: DataViewMatrixNode, index: number, levels: DataViewHierarchyLevel[], div: HTMLDivElement)  => {
        // ...

        if (matrixNode.values) {
            const sumOfValues = Object.keys(matrixNode.values) // get key property of object (value are 0 to N)
                .map(key => +matrixNode.values[key].value) // convert key property to number
                .reduce((prev, curr) => prev + curr) // sum of values

            let sumOfHighlights = sumOfValues;
            sumOfHighlights = Object.keys(matrixNode.values) // get key property of object (value are 0 to N)
                .map(key => matrixNode.values[key].highlight ? +matrixNode.values[key].highlight : null ) // convert key property to number if it exists
                .reduce((prev, curr) => curr ? prev + curr : null) // convert key property to number

            // create div container for value and highlighted value
            const vals = document.createElement("div");
            vals.classList.add("vertical")
            vals.classList.replace("vertical", "horizontal");
            // create paragraph element for label
            const highlighted = document.createElement("p");
            // Display complete value and highlighted value
            highlighted.innerText = `${sumOfHighlights}/${sumOfValues}`;

            // create div container for value
            const valueDiv = document.createElement("div");
            valueDiv.style.width = sumOfValues * 10 + "px";
            valueDiv.classList.add("value");

            // create div container for highlighted values
            const highlightsDiv = document.createElement("div");
            highlightsDiv.style.width = sumOfHighlights * 10 + "px";
            highlightsDiv.classList.add("highlight");
            valueDiv.appendChild(highlightsDiv);

            // append button and paragraph to div containers to parent div
            vals.appendChild(nodeBlock);
            vals.appendChild(valueDiv);
            vals.appendChild(highlighted);
            div.appendChild(vals);
        } else {
            div.appendChild(nodeBlock);
        }

        if (matrixNode.children) {
            // ...
        }
    }
    // ...
}
```

ด้วยเหตุนี้ คุณจะได้รับวิชวลที่มีปุ่มและค่า `highlighted value/default value`

![วิชวลที่มีการแมปและการไฮไลต์มุมมองข้อมูลแบบเมทริกซ์](./media/dev-matrix-visual-highlight-demo.gif)

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [อ่านเกี่ยวกับการแมปมุมมองข้อมูลแบบเมทริกซ์](dataview-mappings.md#matrix-data-mapping)

* [อ่านเกี่ยวกับความสามารถของวิชวล](capabilities.md)

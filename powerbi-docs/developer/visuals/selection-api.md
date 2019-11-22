---
title: การเลือกจุดข้อมูลการแสดงผลด้วยภาพของ Power BI
description: บทความนี้อธิบายวิธีเพิ่มหน้าเริ่มต้นไปยังการแสดงผลด้วยภาพของ Power BI
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 5f5e4769c750406a02ead656af551133fbceb738
ms.sourcegitcommit: f7b28ecbad3e51f410eff7ee4051de3652e360e8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/13/2019
ms.locfileid: "74061902"
---
# <a name="add-interactivity-into-visual-by-power-bi-visuals-selections"></a>เพิ่มการโต้ตอบลงในภาพด้วยการเลือกภาพ Power BI

Power BI มีสองวิธีในการโต้ตอบระหว่างภาพคือ - การเลือกและการกรอง ตัวอย่างด้านล่างแสดงให้เห็นถึงวิธีการเลือกรายการใดๆ ในภาพเดียวและแจ้งภาพอื่นๆ ในรายงานเกี่ยวกับสถานะการเลือกใหม่

`Selection` วัตถุที่สอดคล้องกับอินเตอร์เฟซ:

```typescript
export interface ISelectionId {
    equals(other: ISelectionId): boolean;
    includes(other: ISelectionId, ignoreHighlight?: boolean): boolean;
    getKey(): string;
    getSelector(): Selector;
    getSelectorsByColumn(): SelectorsByColumn;
    hasIdentity(): boolean;
}
```

## <a name="how-to-use-selectionmanager-to-select-data-points"></a>วิธีใช้ SelectionManager เพื่อเลือกจุดข้อมูล

วัตถุโฮสต์ภาพให้วิธีการในการสร้างอินสแตนซ์ของเครื่องมือจัดการการเลือก ตัวจัดการการเลือกที่รับผิดชอบในการเลือก เพื่อล้างการเลือกเพื่อแสดงเมนูบริบทเพื่อจัดเก็บการเลือกปัจจุบันและตรวจสอบสถานะการเลือก และตัวจัดการการเลือกมีวิธีการที่สอดคล้องกันสำหรับการดำเนินการดังกล่าว

### <a name="create-instance-of-selection-manager"></a>สร้างอินสแตนซ์ของตัวจัดการการเลือก

สำหรับการใช้ตัวจัดการการเลือก คุณจะต้องสร้างอินสแตนซ์ของตัวจัดการการเลือก โดยทั่วไป การแสดงผลด้วยภาพจะสร้างตัวจัดการการเลือกตัวอย่างใน `constructor` ของวัตถุการแสดงผลด้วยภาพ

```typescript
export class Visual implements IVisual {
    private target: HTMLElement;
    private host: IVisualHost;
    private selectionManager: ISelectionManager;
    // ...
    constructor(options: VisualConstructorOptions) {
        this.host = options.host;
        // ...
        this.selectionManager = this.host.createSelectionManager();
    }
    // ...
}
```

### <a name="create-instance-of-selection-builder"></a>สร้างอินสแตนซ์ของตัวสร้างการเลือก

เมื่อมีการสร้างอินสแตนซ์ตัวจัดการการเลือก คุณจะต้องสร้าง `selections` สำหรับแต่ละจุดข้อมูลของภาพ วัตถุโฮสต์ภาพมีวิธีการ `createSelectionIdBuilder` ในการสร้างการเลือกสำหรับแต่ละจุดข้อมูล วิธีนี้ส่งกลับอินสแตนซ์ของวัตถุที่มีอินเทอร์เฟซ `powerbi.visuals.ISelectionIdBuilder`:

```typescript
export interface ISelectionIdBuilder {
    withCategory(categoryColumn: DataViewCategoryColumn, index: number): this;
    withSeries(seriesColumn: DataViewValueColumns, valueColumn: DataViewValueColumn | DataViewValueColumnGroup): this;
    withMeasure(measureId: string): this;
    withMatrixNode(matrixNode: DataViewMatrixNode, levels: DataViewHierarchyLevel[]): this;
    withTable(table: DataViewTable, rowIndex: number): this;
    createSelectionId(): ISelectionId;
}
```

วัตถุนี้มีวิธีการที่สอดคล้องกับวิธีการสร้าง `selections` สำหรับการแมปมุมมองข้อมูลชนิดต่างๆ

> [!NOTE]
> วิธีการ`withTable`,`withMatrixNode` ได้รับการแนะนำใน  API 2.5.0 ของการแสดงผลด้วยภาพ Power BI
> ถ้าคุณจำเป็นต้องใช้ตัวเลือกสำหรับการแมปมุมมองข้อมูลของตารางหรือเมทริกซ์ที่ คุณจำเป็นต้องอัปเดต API ไปยัง 2.5.0 หรือใหม่กว่า

### <a name="create-selections-for-categorical-data-view-mapping"></a>สร้างการเลือกสำหรับการแมปมุมมองข้อมูลประเภท

มาดูกันว่าการเลือกจะแสดงบนประเภทมุมมองข้อมูลการแมปสำหรับชุดตัวอย่างอย่างไร:

| ผู้ผลิต | ชนิด | ค่า |
| - | - | - |
| ไครสเลอร์ | รถภายในประเทศ | 28883 |
| ไครสเลอร์ | รถบรรทุกภายในประเทศ | 117131 |
| ไครสเลอร์ | รถนำเข้า | 0 |
| ไครสเลอร์ | รถบรรทุกนำเข้า | 6362 |
| ฟอร์ด | รถภายในประเทศ | 50032 |
| ฟอร์ด | รถบรรทุกภายในประเทศ | 122446 |
| ฟอร์ด | รถนำเข้า | 0 |
| ฟอร์ด | รถบรรทุกนำเข้า | 0 |
| GM | รถภายในประเทศ | 65426 |
| GM | รถบรรทุกภายในประเทศ | 138122 |
| GM | รถนำเข้า | 197 |
| GM | รถบรรทุกนำเข้า | 0 |
| ฮอนด้า | รถภายในประเทศ | 51450 |
| ฮอนด้า | รถบรรทุกภายในประเทศ | 46115 |
| ฮอนด้า | รถนำเข้า | 2932 |
| ฮอนด้า | รถบรรทุกนำเข้า | 0 |
| นิสสัน | รถภายในประเทศ | 51476 |
| นิสสัน | รถบรรทุกภายในประเทศ | 47343 |
| นิสสัน | รถนำเข้า | 5485 |
| นิสสัน | รถบรรทุกนำเข้า | 1430 |
| โตโยต้า | รถภายในประเทศ | 55643 |
| โตโยต้า | รถบรรทุกภายในประเทศ | 61227 |
| โตโยต้า | รถนำเข้า | 20799 |
| โตโยต้า | รถบรรทุกนำเข้า | 23614 |

และการแสดงผลด้วยภาพใช้การแมปมุมมองข้อมูลต่อไปนี้:

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
            "displayName": "Values",
            "name": "values",
            "kind": "Measure"
        }
    ],
    "dataViewMappings": [
        {
            "categorical": {
                "categories": {
                    "for": {
                        "in": "columns"
                    }
                },
                "values": {
                    "group": {
                        "by": "rows",
                        "select": [
                            {
                                "for": {
                                    "in": "values"
                                }
                            }
                        ]
                    }
                }
            }
        }
    ]
}
```

ในตัวอย่าง `Manafacturer`คือ `columns` และ `Type` คือ `rows` มีชุดข้อมูลที่สร้างขึ้นโดยการจัดกลุ่มค่าโดย `rows` (`Type`)

และการแสดงผลด้วยภาพควรสามารถแบ่งข้อมูลด้วย `Manafacturer` และ `Type` ด้วย

ตัวอย่างเช่น เมื่อผู้ใช้เลือก `Chrysler` โดย `Manafacturer` ภาพอื่นๆ ควรแสดงข้อมูลต่อไปนี้:

| ผู้ผลิต | ชนิด | ค่า |
| - | - | - |
| **ไครสเลอร์** | รถภายในประเทศ | 28883 |
| **ไครสเลอร์** | รถบรรทุกภายในประเทศ | 117131 |
| **ไครสเลอร์** | รถนำเข้า | 0 |
| **ไครสเลอร์** | รถบรรทุกนำเข้า | 6362 |

เมื่อผู้ใช้เลือก`Import Car`โดย`Type` (เลือกข้อมูลตามชุด) ภาพอื่นๆ ควรแสดงข้อมูลต่อไปนี้:

| ผู้ผลิต | ชนิด | ค่า |
| - | - | - |
| ไครสเลอร์ | **รถนำเข้า** | 0 |
| ฟอร์ด | **รถนำเข้า** | 0 |
| GM | **รถนำเข้า** | 197 |
| ฮอนด้า | **รถนำเข้า** | 2932 |
| นิสสัน | **รถนำเข้า** | 5485 |
| โตโยต้า | **รถนำเข้า** | 20799 |

![การแสดงผลด้วยภาพที่เลือกสำหรับประเภทและชุดข้อมูล](media/visual-selections-sample.png)

จำเป็นต้องเติมตะกร้าข้อมูลด้วยภาพ

![ตะกร้าข้อมูลของภาพที่มีการเลือก](media/visual-selections-databuckets.png)

มี `Manafacturer` เป็นประเภท (คอลัมน์) `Type` เป็นชุดข้อมูล (แถว) และ `Value` เป็น `Values` สำหรับชุดข้อมูล

> [!NOTE]
> จำเป็นต้องมี `Values` สำหรับชุดข้อมูลเนื่องจากการแมปมุมมองข้อมูลตามการแสดงผลด้วยภาพคาดหวังว่า `Values` จะพบโดยข้อมูล `Rows`

#### <a name="create-selections-for-categories"></a>สร้างการเลือกสำหรับประเภท

```typescript
// categories
const categories = dataView.categorical.categories;

// create label for 'Manafacturer' column
const p = document.createElement("p") as HTMLParagraphElement;
p.innerText = categories[0].source.displayName.toString();
this.target.appendChild(p);

// get count of category elements
const categoriesCount = categories[0].values.length;

// iterate all categories to generate selection and create button elements to use selections
for (let categoryIndex = 0; categoryIndex < categoriesCount; categoryIndex++) {
    const categoryValue: powerbi.PrimitiveValue = categories[0].values[categoryIndex];

    const categorySelectionId = this.host.createSelectionIdBuilder()
        .withCategory(categories[0], categoryIndex) // we have only one category (only one `Manafacturer` column)
        .createSelectionId();
    this.dataPoints.push({
        value: categoryValue,
        selection: categorySelectionId
    });
    console.log(categorySelectionId);

    // create button element to apply selection on click
    const button = document.createElement("button") as HTMLButtonElement;
    button.value = categoryValue.toString();
    button.innerText = categoryValue.toString();
    button.addEventListener("click", () => {
        // handle click event to apply correspond selection
        this.selectionManager.select(categorySelectionId);
    });
    this.target.appendChild(button);
}
```

ในโค้ดตัวอย่างคุณจะเห็นว่าเราซ้ำทุกหมวดหมู่ และในแต่ละการวนซ้ำเราเรียก `createSelectionIdBuilder` เพื่อสร้างการเลือกถัดไปสำหรับแต่ละหมวดหมู่โดยการเรียกวิธี `withCategory` ของตัวสร้างการเลือก วิธีการ `createSelectionId` ถูกใช้เป็นวิธีการสุดท้ายในการส่งกลับวัตถุ `selection` ที่สร้างขึ้น

ในวิธีการ `withCategory` เราผ่านคอลัมน์ของ `category` ในตัวอย่าง `Manafacturer` และดัชนีขององค์ประกอบประเภท

#### <a name="create-selections-for-series"></a>สร้างการเลือกสำหรับชุดข้อมูล

```typescript
// get groupped values for series
const series: powerbi.DataViewValueColumnGroup[] = dataView.categorical.values.grouped();

// create label for 'Type' column
const p2 = document.createElement("p") as HTMLParagraphElement;
p2.innerText = dataView.categorical.values.source.displayName;
this.target.appendChild(p2);

// iterate all series to generate selection and create button elements to use selections
series.forEach( (ser: powerbi.DataViewValueColumnGroup) => {
    // create selection id for series
    const seriesSelectionId = this.host.createSelectionIdBuilder()
        .withSeries(dataView.categorical.values, ser)
        .createSelectionId();

    this.dataPoints.push({
        value: ser.name,
        selection: seriesSelectionId
    });

    // create button element to apply selection on click
    const button = document.createElement("button") as HTMLButtonElement;
    button.value =ser.name.toString();
    button.innerText = ser.name.toString();
    button.addEventListener("click", () => {
        // handle click event to apply correspond selection
        this.selectionManager.select(seriesSelectionId);
    });
    this.target.appendChild(button);
});
```

### <a name="create-selections-for-table-data-view-mapping"></a>สร้างการเลือกสำหรับการแมปมุมมองข้อมูลตาราง

ตัวอย่างของการแมปมุมมองข้อมูลตาราง

```json
{
    "dataRoles": [
        {
            "displayName": "Values",
            "name": "values",
            "kind": "GroupingOrMeasure"
        }
    ],
    "dataViewMappings": [
        {
            "table": {
                "rows": {
                    "for": {
                        "in": "values"
                    }
                }
            }
        }
    ]
}
```

ในการสร้างการเลือกสำหรับการแมปมุมมองตารางข้อมูลแต่ละแถวคุณต้องเรียกใช้วิธี `withTable` ของเครื่องมือสร้างสิ่งที่เลือก

```typescript
public update(options: VisualUpdateOptions) {
    const dataView = options.dataViews[0];
    dataView.table.rows.forEach((row: DataViewTableRow, rowIndex: number) => {
        this.target.appendChild(rowDiv);
        const selection: ISelectionId = this.host.createSelectionIdBuilder()
            .withTable(dataView.table, rowIndex)
            .createSelectionId();
    }
}
```

รหัสที่มองเห็นจะวนซ้ำแถวของตารางและแต่ละแถวเรียกวิธีตาราง `withTable` พารามิเตอร์ของวิธีการ `withTable` คือวัตถุ `table` และดัชนีของแถวตาราง

### <a name="create-selections-for-matrix-data-view-mapping"></a>สร้างการเลือกสำหรับการแมปมุมมองข้อมูลเมทริกซ์

```typescript
public update(options: VisualUpdateOptions) {
    const host = this.host;
    const rowLevels: powerbi.DataViewHierarchyLevel[] = dataView.matrix.rows.levels;
    const columnLevels: powerbi.DataViewHierarchyLevel[] = dataView.matrix.rows.levels;

    // iterate rows hierarchy
    nodeWalker(dataView.matrix.rows.root, rowLevels);
    // iterate columns hierarchy
    nodeWalker(dataView.matrix.columns.root, columnLevels);

    function nodeWalker(node: powerbi.DataViewMatrixNode, levels: powerbi.DataViewHierarchyLevel[]) {
        const nodeSelection = host.createSelectionIdBuilder().withMatrixNode(node, levels);

        if (node.children && node.children.length) {
            node.children.forEach(child => {
                nodeWalker(child, levels);
            });
        }
    }
}
```

ในตัวอย่าง `nodeWalker` เรียกซ้ำสำหรับแต่ละโหนดย่อย

`nodeWalker` สร้างวัตถุ `nodeSelection` ในการโทรแต่ละครั้ง และแต่ละ `nodeSelection` เป็นตัวแทน `selection` ของโหนดที่ตรงกัน

## <a name="select-datapoints-to-slice-other-visuals"></a>เลือกจุดข้อมูลเพื่อแบ่งภาพอื่นๆ

ในรหัสตัวอย่างของการเลือกสำหรับการแมปมุมมองข้อมูลเด็ดขาด คุณเห็นว่าเราได้สร้างตัวจัดการการคลิกสำหรับองค์ประกอบปุ่ม ตัวจัดการเรียกวิธีการ `select` ของตัวจัดการการเลือกและส่งผ่านวัตถุที่เลือก

```typescript
button.addEventListener("click", () => {
    // handle click event to apply correspond selection
    this.selectionManager.select(categorySelectionId);
});
```

อินเทอร์เฟซของวิธีการ `select` คือ

```typescript
interface ISelectionManager {
    // ...
    select(selectionId: ISelectionId | ISelectionId[], multiSelect?: boolean): IPromise<ISelectionId[]>;
    // ...
}
```

คุณสามารถดู `select` สามารถยอมรับอาร์เรย์ของการเลือกได้ ซึ่งหมายความว่าภาพของคุณสามารถเลือกหลายจุดข้อมูลได้ พารามิเตอร์ตัวที่สอง `multiSelect` รับผิดชอบการเลือกหลายรายการ ถ้าค่าเป็นจริง Power BI จะไม่ล้างสถานะการเลือกก่อนหน้าและใช้การเลือกปัจจุบันมิฉะนั้นการเลือกก่อนหน้าจะรีเซ็ต

สถานการณ์โดยทั่วไปของการใช้การจัดการ `multiSelect` ของปุ่ม CTRL สำหรับการคลิกเหตุการณ์

```typescript
button.addEventListener("click", (mouseEvent) => {
    const multiSelect = (mouseEvent as MouseEvent).ctrlKey;
    this.selectionManager.select(seriesSelectionId, multiSelect);
});
```

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [อ่านวิธีการใช้ตัวเลือกสำหรับการผูกคุณสมบัติการแสดงผลด้วยภาพกับจุดข้อมูล](objects-properties.md#objects-selector)

* [อ่านวิธีการจัดการกับการเลือกในการสลับบุ๊กมาร์ก](bookmarks-support.md#visuals-with-selection)

* [อ่านวิธีการเพิ่มเมนูบริบทสำหรับจุดข้อมูลภาพ](context-menu.md)

* [อ่านวิธีการใช้ InteractivityUtils เพื่อเพิ่มการเลือกลงในภาพ Power BI](utils-interactivity-selections.md)

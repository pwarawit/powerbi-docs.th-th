---
title: API ตัวกรองวิชวล
description: วิชวล Power BI สามารถกรองวิชวลอื่น ๆ ได้อย่างไร
author: sranins
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 50e9601faf497675ebc3f24609a856a600e3bcb1
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425056"
---
# <a name="power-bi-visual-filters-api"></a>API ตัวกรองวิชวลของ Power BI

ตัวกรอง-วิชวลช่วยให้สามารถกรองข้อมูลได้ ความแตกต่างที่สำคัญจากการเลือกคือวิชวลอื่น ๆ จะถูกกรองด้วยวิธีใดก็ได้แม้ว่าจะเน้นการสนับสนุนโดยวิชวลอื่น ๆ

เมื่อต้องการเปิดใช้งานการกรองสำหรับวิชวล วิชวลควรประกอบด้วย `filter` วัตถุในส่วน `general` ของเนื้อหา capabilities.json

```json
"objects": {
        "general": {
            "displayName": "General",
            "displayNameKey": "formattingGeneral",
            "properties": {
                "filter": {
                    "type": {
                        "filter": true
                    }
                }
            }
        }
    }
```

อินเทอร์เฟซของ API ตัวกรองจะพร้อมใช้งานใน [`powerbi-models`](https://www.npmjs.com/package/powerbi-models) แพคเกจ นอกจากนี้ แพคเกจยังประกอบด้วยคลาสที่จะสร้างอินสแตนซ์ตัวกรอง

```cmd
npm install powerbi-models --save
```

ถ้าคุณใช้เครื่องมือเวอร์ชั่นเก่า (เวอร์ชั่นน้อยกว่า 3.x.x), คุณควรรวม `powerbi-models` เข้าไปในแพคเกจวิชวล [คำแนะนำแบบสั้นเกี่ยวกับวิธีการรวมแพคเกจ](https://github.com/Microsoft/powerbi-visuals-sampleslicer/blob/master/doc/AddingAdvancedFilterAPI.md)

ตัวกรองทั้งหมดจะขยาย `IFilter` อินเทอร์เฟซ

```typescript
export interface IFilter {
    $schema: string;
    target: IFilterTarget;
}
```

`target` -เป็นคอลัมน์ตารางบนแหล่งข้อมูล

## <a name="basic-filter-api"></a>API ตัวกรองพื้นฐาน

อินเทอร์เฟซตัวกรองพื้นฐานคือ

```typescript
export interface IBasicFilter extends IFilter {
    operator: BasicFilterOperators;
    values: (string | number | boolean)[];
}
```

`operator` - เป็นการแจงนับด้วยค่า "In", "NotIn", "All"

`values` - เป็นค่าสำหรับเงื่อนไข

ตัวอย่างของตัวกรองพื้นฐาน:

```typescript
let basicFilter = {
    target: {
        column: "Col1"
    },
    operator: "In",
    values: [1,2,3]
}
```

ตัวกรองหมายถึง "ให้ข้อมูลแถวทั้งหมดที่ `col1` เท่ากับหนึ่งในค่า 1, 2 หรือ 3 แก่ฉัน"

SQL ที่เทียบเท่าคือ

```sql
SELECT * FROM table WHERE col1 IN ( 1 , 2 , 3 )
```

เมื่อต้องการสร้างตัวกรอง คุณสามารถใช้คลาส BasicFilter ใน `powerbi-models`

ถ้าคุณใช้เครื่องมือเวอร์ชั่นเก่า คุณควรมีอินสแตนซ์ของแบบจำลองในวัตถุหน้าต่างโดย`window['powerbi-models']`:

```javascript
let categories: DataViewCategoricalColumn = this.dataView.categorical.categories[0];

let target: IFilterColumnTarget = {
    table: categories.source.queryName.substr(0, categories.source.queryName.indexOf('.')),
    column: categories.source.displayName
};

let values = [ 1, 2, 3 ];

let filter: IBasicFilter = new window['powerbi-models'].BasicFilter(target, "In", values);
```

วิชวลจะเรียกใช้ตัวกรองโดยใช้เมธอด applyJsonFilter () บนอินเทอร์เฟซสำหรับโฮสต์ IVisualHost ที่กำหนดไว้สำหรับวิชวลในคอนสตรักเตอร์

```typescript
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

## <a name="advanced-filter-api"></a>API ตัวกรองขั้นสูง

[API ตัวกรองขั้นสูง](https://github.com/Microsoft/powerbi-models) จะเปิดใช้งานคิวรีการกรอง/การเลือกจุดข้อมูลของวิชวลแบบไขว้ที่ซับซ้อน ซึ่งยึดตามเกณฑ์หลายอย่าง (เช่น "น้อยกว่า", "ประกอบด้วย", "คือ", "IsBlank" เป็นต้น)

ตัวกรองได้รับการแนะนำใน Visuals API 1.7.0

API ตัวกรองขั้นสูงยังจำเป็นต้องมี `target` ที่มีชื่อ `table`และ`column` แต่ตัวดำเนินการของ API ตัวกรองขั้นสูงคือ `"And" | "Or"` 

นอกจากนี้ ตัวกรองจะใช้เงื่อนไขแทนค่าที่มีอินเทอร์เฟซ:

```typescript
interface IAdvancedFilterCondition {
    value: (string | number | boolean);
    operator: AdvancedFilterConditionOperators;
}
```

ตัวดำเนินการตามเงื่อนไขสำหรับพารามิเตอร์ `operator` คือ `"None" | "LessThan" | "LessThanOrEqual" | "GreaterThan" | "GreaterThanOrEqual" | "Contains" | "DoesNotContain" | "StartsWith" | "DoesNotStartWith" | "Is" | "IsNot" | "IsBlank" | "IsNotBlank"`

```javascript
let categories: DataViewCategoricalColumn = this.dataView.categorical.categories[0];

let target: IFilterColumnTarget = {
    table: categories.source.queryName.substr(0, categories.source.queryName.indexOf('.')), // table
    column: categories.source.displayName // col1
};

let conditions: IAdvancedFilterCondition[] = [];

conditions.push({
    operator: "LessThan",
    value: 0
});

let filter: IAdvancedFilter = new window['powerbi-models'].AdvancedFilter(target, "And", conditions);

// invoke the filter
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

SQL ที่เทียบเท่าคือ

```sql
SELECT * FROM table WHERE col1 < 0;
```

สามารถค้นหาโค้ดตัวอย่างที่สมบูรณ์ของการใช้ API ตัวกรองขั้นสูงได้ใน [`Sampleslicer visual` ที่เก็บ](https://github.com/Microsoft/powerbi-visuals-sampleslicer)

## <a name="tuple-filter-api-multi-column-filter"></a>API ตัวกรองทูเพิล (ตัวกรองหลายคอลัมน์)

API ตัวกรองทูเพิลได้รับการแนะนำใน Visuals API 2.3.0

API ตัวกรองทูเพิลคล้ายกับตัวกรองพื้นฐาน แต่จะอนุญาตให้กำหนดเงื่อนไขสำหรับหลายคอลัมน์และตารางได้

และตัวกรองมีอินเทอร์เฟซ: 

```typescript
interface ITupleFilter extends IFilter {
    $schema: string;
    filterType: FilterType;
    operator: TupleFilterOperators;
    target: ITupleFilterTarget;
    values: TupleValueType[];
}
```

`target` เป็นอาร์เรย์ของคอลัมน์ที่มีชื่อตาราง:

```typescript
declare type ITupleFilterTarget = IFilterTarget[];
```

  ตัวกรองสามารถระบุที่อยู่ของคอลัมน์จากตารางต่างๆ

`$schema` คือ "http://powerbi.com/product/schema#tuple"

`filterType` เป็น `FilterType.Tuple`

`operator` อนุญาตให้ใช้`"In"`ตัวดำเนินการเท่านั้น

`values` เป็นอาร์เรย์ของทูเพิลค่าที่แต่ละทูเพิลแสดงชุดข้อมูลที่อนุญาตหนึ่งชุดของค่าคอลัมน์เป้าหมาย 

```typescript
declare type TupleValueType = ITupleElementValue[];

interface ITupleElementValue {
    value: PrimitiveValueType
}
```

ตัวอย่างที่สมบูรณ์:

```typescript
let target: ITupleFilterTarget = [
    {
        table: "DataTable",
        column: "Team"
    },
    {
        table: "DataTable",
        column: "Value"
    }
];

let values = [
    [
        // the 1st column combination value (aka column tuple/vector value) that the filter will pass through
        {
            value: "Team1" // the value for `Team` column of `DataTable` table
        },
        {
            value: 5 // the value for `Value` column of `DataTable` table
        }
    ],
    [
        // the 2nd column combination value (aka column tuple/vector value) that the filter will pass through
        {
            value: "Team2" // the value for `Team` column of `DataTable` table
        },
        {
            value: 6 // the value for `Value` column of `DataTable` table
        }
    ]
];

let filter: ITupleFilter = {
    $schema: "http://powerbi.com/product/schema#tuple",
    filterType: FilterType.Tuple,
    operator: "In",
    target: target,
    values: values
}

// invoke the filter
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

**ลำดับของชื่อคอลัมน์และค่าของเงื่อนไขมีความสำคัญ**

SQL ที่เทียบเท่าคือ

```sql
SELECT * FROM DataTable WHERE ( Team = "Team1" AND Value = 5 ) OR ( Team = "Team2" AND Value = 6 );
```  

## <a name="restoring-json-filter-from-dataview"></a>การกู้คืนตัวกรอง JSON จาก DataView

การเริ่มต้นจากตัวกรอง API 2.2 **JSON**  สามารถที่จะกู้คืนได้จาก **VisualUpdateOptions**

```typescript
export interface VisualUpdateOptions extends extensibility.VisualUpdateOptions {
    viewport: IViewport;
    dataViews: DataView[];
    type: VisualUpdateType;
    viewMode?: ViewMode;
    editMode?: EditMode;
    operationKind?: VisualDataChangeOperationKind;
    jsonFilters?: IFilter[];
}
```

Power BI จะเรียกใช้เมธอด `update` ของวิชวลเมื่อใช้บุ๊กมาร์กการเปลี่ยนและวิชวลได้รับวัตถุ `filter` ที่สอดคล้องกัน
[อ่านเพิ่มเติมเกี่ยวกับการสนับสนุนของบุ๊กมาร์ก](bookmarks-support.md)

### <a name="sample-json-filter"></a>ตัวกรอง JSON ตัวอย่าง

![ตัวกรอง JSON ภาพหน้าจอ](./media/json-filter.png)

### <a name="clear-json-filter"></a>ล้างข้อมูลตัวกรอง JSON

API ตัวกรองยอมรับ `null` ค่าของตัวกรองเป็นรีเซ็ตหรือล้าง

```typescript
// invoke the filter
visualHost.applyJsonFilter(null, "general", "filter", FilterAction.merge);
```

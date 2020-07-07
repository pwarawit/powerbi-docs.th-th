---
title: API ตัวกรองวิชวลในวิชวล Power BI
description: บทความนี้อธิบายถึงวิธีการที่วิชวล Power BI สามารถกรองวิชวลอื่น ๆ ได้อย่างไร
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: 24e8ac32fb89db2fdc0d1f4ad3fbaffdadaf57bb
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85237420"
---
# <a name="the-visual-filters-api-in-power-bi-visuals"></a>API ตัวกรองวิชวลในวิชวล Power BI

API ตัวกรองวิชวลช่วยให้คุณสามารถกรองข้อมูลในวิชวล Power BI ได้ ความแตกต่างที่สำคัญจากการเลือกแบบอื่นคือวิชวลอื่น ๆ จะถูกกรองในทุกทางแม้จะมีการไฮไลต์ด้วยการสนับสนุนจากวิชวลอื่น

หากต้องการเปิดใช้งานการกรองสำหรับวิชวล ควรมีวัตถุ `filter` ในส่วน `general` ของ  *โค้ด capabilities.json*

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

อินเทอร์เฟซของ API ตัวกรองวิชวล[พร้อมใช้งานในแพคเกจแบบจำลอง powerbi](https://www.npmjs.com/package/powerbi-models) นอกจากนี้ แพคเกจยังประกอบด้วยคลาสที่จะสร้างอินสแตนซ์ตัวกรอง

```cmd
npm install powerbi-models --save
```

ถ้าคุณใช้เครื่องมือเวอร์ชันเก่ากว่า (เวอร์ชันก่อนหน้า 3.x.x) คุณควรรวม `powerbi-models` ไว้ในแพคเกจวิชวลด้วย สำหรับข้อมูลเพิ่มเติม โปรดดูคำแนะนำสั้น ๆ ในหัวข้อ [เพิ่ม API ตัวกรองขั้นสูงไปยังวิชวลที่กำหนดเอง](https://github.com/Microsoft/powerbi-visuals-sampleslicer/blob/master/doc/AddingAdvancedFilterAPI.md)

ตัวกรองทั้งหมดเป็นส่วนขยายอินเทอร์เฟซ `IFilter` ดังแสดงในโค้ดต่อไปนี้:

```typescript
export interface IFilter {
    $schema: string;
    target: IFilterTarget;
}
```
ที่ซึ่ง:
* `target` เป็นคอลัมน์ตารางในแหล่งข้อมูล

## <a name="the-basic-filter-api"></a>API ตัวกรองพื้นฐาน

อินเตอร์เฟซตัวกรองพื้นฐานแสดงในโค้ดต่อไปนี้:

```typescript
export interface IBasicFilter extends IFilter {
    operator: BasicFilterOperators;
    values: (string | number | boolean)[];
}
```

ที่ซึ่ง:
* `operator` เป็นการแจกแจงที่มีค่า *In*, *NotIn* และ *All*
* `values` เป็นค่าสำหรับเงื่อนไข

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

ตัวกรองหมายถึง "ให้ทุกแถวที่มี `col1` เท่ากับค่า 1, 2 หรือ 3 แก่ฉัน"

SQL ที่เทียบเท่าคือ:

```sql
SELECT * FROM table WHERE col1 IN ( 1 , 2 , 3 )
```

เมื่อต้องการสร้างตัวกรอง คุณสามารถใช้คลาส BasicFilter ใน `powerbi-models`

ถ้าคุณใช้เครื่องมือเวอร์ชันเก่ากว่า คุณควรมีอินสแตนซ์ของแบบจำลองในวัตถุหน้าต่างโดยใช้ `window['powerbi-models']` ดังที่แสดงในโค้ดต่อไปนี้:

```javascript
let categories: DataViewCategoricalColumn = this.dataView.categorical.categories[0];

let target: IFilterColumnTarget = {
    table: categories.source.queryName.substr(0, categories.source.queryName.indexOf('.')),
    column: categories.source.displayName
};

let values = [ 1, 2, 3 ];

let filter: IBasicFilter = new window['powerbi-models'].BasicFilter(target, "In", values);
```

วิชวลจะเรียกใช้ตัวกรองโดยใช้เมธอด applyJsonFilter() บนอินเตอร์เฟสโฮสต์ IVisualHost ซึ่งจัดเตรียมให้กับวิชวลในคอนสตรักเตอร์

```typescript
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

## <a name="the-advanced-filter-api"></a>API ตัวกรองขั้นสูง

[API ตัวกรองขั้นสูง](https://github.com/Microsoft/powerbi-models)เปิดใช้งานการเลือกจุดข้อมูลและคิวรีการกรองแบบไขว้วิชวลที่ซับซ้อนโดยยึดตามเกณฑ์หลายอย่าง เช่น *LessThan*, *Contains*, *Is*, *IsBlank* และอื่น ๆ)

ตัวกรองได้รับการแนะนำใน Visuals API 1.7.0

API ตัวกรองขั้นสูงยังจำเป็นต้องมี `target` ที่มีชื่อ `table` และ `column` แต่ตัวดำเนินการของ API ตัวกรองขั้นสูงคือ *And* และ *Or* 

นอกจากนี้ ตัวกรองใช้เงื่อนไขกับอินเตอร์เฟสแทนที่จะเป็นค่า:

```typescript
interface IAdvancedFilterCondition {
    value: (string | number | boolean);
    operator: AdvancedFilterConditionOperators;
}
```

ตัวดำเนินการเงื่อนไขสำหรับพารามิเตอร์ `operator` คือ *None*, *LessThan*, *LessThanOrEqual*, *GreaterThan*, *GreaterThanOrEqual*, *Contains*, *DoesNotContain*, *StartsWith*, *DoesNotStartWith*, *Is*, *IsNot*, *IsBlank* และ "IsNotBlank"`

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

SQL ที่เทียบเท่าคือ:

```sql
SELECT * FROM table WHERE col1 < 0;
```

สำหรับโค้ดตัวอย่างฉบับสมบูรณ์สำหรับการใช้ API ตัวกรองขั้นสูง โปรดไปที่ [พื้นที่เก็บข้อมูลวิชวล Sampleslicer](https://github.com/Microsoft/powerbi-visuals-sampleslicer)

## <a name="the-tuple-filter-api-multi-column-filter"></a>API ตัวกรองทูเพิล (ตัวกรองหลายคอลัมน์)

API ตัวกรองทูเพิลถูกนำมาใช้ใน Visuals API 2.3.0 ซึ่งคล้ายกับ API ตัวกรองพื้นฐาน แต่จะอนุญาตให้คุณกำหนดเงื่อนไขสำหรับหลายคอลัมน์และตารางได้

อินเตอร์เฟซตัวกรองแสดงในโค้ดต่อไปนี้: 

```typescript
interface ITupleFilter extends IFilter {
    $schema: string;
    filterType: FilterType;
    operator: TupleFilterOperators;
    target: ITupleFilterTarget;
    values: TupleValueType[];
}
```

ที่ซึ่ง:
* `target` เป็นอาร์เรย์ของคอลัมน์ที่มีชื่อตาราง:

    ```typescript
    declare type ITupleFilterTarget = IFilterTarget[];
    ```

  ตัวกรองสามารถระบุที่อยู่ของคอลัมน์จากตารางต่างๆ

* `$schema` คือ https://powerbi.com/product/schema#tuple

* `filterType` คือ *FilterType.Tuple*

* `operator` อนุญาตให้ใช้ได้เฉพาะในตัวดำเนินการ *In* เท่านั้น

* `values` เป็นอาร์เรย์ของทูเพิลค่า และแต่ละทูเพิลแสดงชุดข้อมูลที่อนุญาตหนึ่งชุดของค่าคอลัมน์เป้าหมาย 

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
        // the first column combination value (or the column tuple/vector value) that the filter will pass through
        {
            value: "Team1" // the value for the `Team` column of the `DataTable` table
        },
        {
            value: 5 // the value for the `Value` column of the `DataTable` table
        }
    ],
    [
        // the second column combination value (or the column tuple/vector value) that the filter will pass through
        {
            value: "Team2" // the value for `Team` column of `DataTable` table
        },
        {
            value: 6 // the value for `Value` column of `DataTable` table
        }
    ]
];

let filter: ITupleFilter = {
    $schema: "https://powerbi.com/product/schema#tuple",
    filterType: FilterType.Tuple,
    operator: "In",
    target: target,
    values: values
}

// invoke the filter
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

> [!IMPORTANT]
> ลำดับของชื่อคอลัมน์และค่าเงื่อนไขมีความละเอียดอ่อน

SQL ที่เทียบเท่าคือ:

```sql
SELECT * FROM DataTable WHERE ( Team = "Team1" AND Value = 5 ) OR ( Team = "Team2" AND Value = 6 );
```  

## <a name="restore-the-json-filter-from-the-data-view"></a>คืนค่าตัวกรอง JSON จากมุมมองข้อมูล

เริ่มต้นด้วย API เวอร์ชัน 2.2.0 คุณสามารถกู้คืนตัวกรอง JSON จาก *VisualUpdateOptions* ดังที่แสดงในโค้ดต่อไปนี้:

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

เมื่อคุณสลับ บุ๊กมาร์ก Power BI เรียกใช้เมธอด `update` ของวิชวล และวิชวลได้รับวัตถุ `filter` ที่สอดคล้องกัน สำหรับข้อมูลเพิ่มเติม โปรดดูที่ [เพิ่มการสนับสนุนบุ๊กมาร์กสำหรับวิชวล Power BI](bookmarks-support.md)

### <a name="sample-json-filter"></a>ตัวกรอง JSON ตัวอย่าง

โค้ดตัวกรอง JSON ตัวอย่างบางตัวจะแสดงในรูปต่อไปนี้:

![โค้ดตัวกรอง JSON](media/filter-api/json-filter.png)

### <a name="clear-the-json-filter"></a>ล้างตัวกรอง JSON

API ตัวกรองยอมรับค่า `null` ของตัวกรองเป็น *รีเซ็ต* หรือ *ล้าง*

```typescript
// invoke the filter
visualHost.applyJsonFilter(null, "general", "filter", FilterAction.merge);
```

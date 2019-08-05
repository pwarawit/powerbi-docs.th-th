---
title: การแมปมุมมองข้อมูล
description: Power BI แปลงข้อมูลก่อนส่งผ่านไปยังวิชวลอย่างไร
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: ff70b2f12921694617a736164484df1326471eea
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425194"
---
# <a name="data-view-mappings-in-power-bi-visuals"></a>การแมปมุมมองข้อมูลในวิชวลของ Power BI

`dataViewMappings`อธิบายว่าบทบาทข้อมูลเกี่ยวข้องกันอย่างไรและอนุญาตให้คุณระบุข้อกำหนดเงื่อนไขสำหรับบทบาทดังกล่าวได้
มีส่วนย่อยสำหรับ `dataMappings` แต่ละรายการ

การแมปข้อมูลแต่ละครั้งจะสร้าง `DataView` แต่ขณะนี้เราสนับสนุนการคิวรีหนึ่งครั้งต่อวิชวลเท่านั้น ดังนั้นในสถานการณ์ส่วนใหญ่คุณจะได้รับ `DataView` หนึ่งรายการเท่านั้น อย่างไรก็ตามคุณสามารถทำการแมปข้อมูลหลายรายการโดยมีเงื่อนไขต่างกันได้

```json
"dataViewMappings": [
    {
        "conditions": [ ... ],
        "categorical": { ... },
        "single": { ... },
        "table": { ... },
        "matrix": { ... }
    }
]
```

> [!NOTE]
> สิ่งสำคัญที่ต้องทราบคือว่า Power BI สร้างการแมปไปยัง DataView หากว่าและเฉพาะในกรณีที่มีการกรอกข้อมูลการแมปที่ถูกต้องลงใน `dataViewMappings` เท่านั้น

กล่าวอีกนัยหนึ่งหากมีการกำหนด `categorical` ใน `dataViewMappings` แต่การแมปอื่นเช่น `table`, `single` และอื่น ๆ จะไม่ดำเนินการ เช่นในตัวอย่างต่อไปนี้:
```json
"dataViewMappings": [
    {
        "categorical": { ... }
    }
]
```

Power BI จะสร้าง `DataView` ด้วยการแมป `categorical` ครั้งเดียว ( การแมป `table` และการแมปอื่นจะเป็น `undefined`):
```javascript
{
    "categorical": {
        "categories": [ ... ],
        "values": [ ... ]
    },
    "metadata": { ... }
}
```

## <a name="conditions"></a>เงื่อนไข

อธิบายเงื่อนไขสำหรับการแมปข้อมูลที่เฉพาะเจาะจง คุณสามารถระบุเงื่อนไขได้หลายชุดและถ้าข้อมูลตรงกับชุดของเงื่อนไขที่อธิบาย วิชวลจะยอมรับข้อมูลได้อย่างถูกต้อง

ในขณะนี้สำหรับแต่ละเขตข้อมูล คุณสามารถระบุค่าต่ำสุดและสูงสุดได้ ซึ่งแสดงถึงจำนวนของเขตข้อมูลที่สามารถผูกกับบทบาทข้อมูลนั้นได้ 

> [!NOTE]
> หากคุณละเว้นบทบาทข้อมูลในเงื่อนไข ตัวเลขในเขตข้อมูลจะเป็นเท่าใดก็ได้

### <a name="example-1"></a>ตัวอย่าง 1

คุณสามารถลากเขตข้อมูลหลายรายการลงในแต่ละบทบาทข้อมูลได้ ในตัวอย่างนี้ เราจำกัดประเภทไปยังหนึ่งเขตข้อมูลและหน่วยวัดไปยังสองเขตข้อมูล

```json
"conditions": [
    { "category": { "max": 1 }, "y": { "max": 2 } },
]
```

### <a name="example-2"></a>ตัวอย่าง 2

ในตัวอย่างนี้จำเป็นต้องตรงกับหนึ่งในสองเงื่อนไข เขตข้อมูลกลุ่มหนึ่งรายการอย่างแน่นอนและหน่วยวัดสองรายการอย่างแน่นอน หรือไม่ก็เป็นกลุ่มสองรายการอย่างแน่นอนและหน่วยวัดหนึ่งรายการอย่างแน่นอน

```json
"conditions": [
    { "category": { "min": 1, "max": 1 }, "measure": { "min": 2, "max": 2 } },
    { "category": { "min": 2, "max": 2 }, "measure": { "min": 1, "max": 1 } }
]
```

## <a name="single-data-mapping"></a>การแมปข้อมูลเดี่ยว

การแมปข้อมูลเดี่ยวเป็นรูปแบบที่ง่ายที่สุดของการแมปข้อมูล ซึ่งเป็นการยอมรับเขตข้อมูลหน่วยวัดเดียวและให้ผลรวมแก่คุณ ถ้าเขตข้อมูลเป็นตัวเลขจะให้ผลรวมแก่คุณ มิฉะนั้นจะให้จำนวนของค่าที่ไม่ซ้ำกัน

หากต้องการใช้การแมปข้อมูลเดี่ยว คุณจะต้องกำหนดชื่อของบทบาทข้อมูลที่คุณต้องการแมป การแมปนี้จะทำงานกับเขตข้อมูลหน่วยวัดเดียวเท่านั้น ถ้ามีการกำหนดเขตข้อมูลที่สองจะไม่มีการสร้างมุมมองข้อมูล ดังนั้นจึงเป็นแนวทางปฏิบัติที่ดีในการรวมเงื่อนไขที่จำกัดข้อมูลลงในเขตข้อมูลเดียว

> [!NOTE]
> การแมปข้อมูลนี้ไม่สามารถใช้ร่วมกับการแมปข้อมูลอื่นๆ ได้ ซึ่งหมายถึงการลดข้อมูลลงไปเป็นค่าตัวเลขเดียว

### <a name="example-3"></a>ตัวอย่างที่ 3

```json
"dataViewMappings": {
    "conditions": [
        { "Y": { "max": 1 } }
    ],
    "single": {
        "role": "Y"
    }
}  
```

มุมมองข้อมูลที่เกิดขึ้นจะยังคงประกอบด้วยชนิดอื่นๆ (ตาราง จัดกลุ่ม ฯลฯ) แต่การแมปแต่ละครั้งจะมีเพียงค่าเดียวเท่านั้น แนวทางปฏิบัติที่ดีที่สุดคือ เข้าถึงเพียงแค่ค่าเดียว

```JSON
{
    "dataView": [
        {
            "metadata": null,
            "categorical": null,
            "matrix": null,
            "table": null,
            "tree": null,
            "single": {
                "value": 94163140.3560001
            }
        }
    ]
}
```

## <a name="categorical-data-mapping"></a>การแมปข้อมูลจัดกลุ่ม

การแมปข้อมูลจัดกลุ่มถูกใช้เพื่อให้ได้มาซึ่งการจัดกลุ่มข้อมูลอิสระหนึ่งหรือสองรายการ

### <a name="example-4"></a>ตัวอย่างที่ 4

นี่คือข้อกำหนดจากตัวอย่างก่อนหน้าของเราใน DataRoles

```json
"dataRole":[
    {
        "displayName": "Category",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Y Axis",
        "name": "measure",
        "kind": "Measure"
    }
]
```

ในตอนนี้สำหรับการแมป:

```json
"dataViewMappings": {
    "categorical": {
        "categories": {
            "for": { "in": "category" }
        },
        "values": {
            "select": [
                { "bind": { "to": "measure" } }
            ]
        }
    }
}
```

นี่เป็นตัวอย่างที่เรียบง่ายในภาษาอังกฤษแบบธรรมดาซึ่งอ่าน "แมป `category`DataRole ของฉันเพื่อให้ข้อมูลถูกแมปไปยัง `categorical.categories` สำหรับทุกเขตข้อมูลที่ฉันลากเข้าสู่ `category` นอกจากนี้ยังแมป`measure`DataRole ของฉันไปยัง `categorical.values` อีกด้วย"

* **สำหรับ...ใน** - สำหรับรายการทั้งหมดในบทบาทข้อมูลนี้ ซึ่งรวมไว้ในการคิวรีข้อมูล
* **ผูก...ไปยัง** - สร้างผลลัพธ์เดียวกับ สำหรับ...ใน แต่คาดว่า DataRole จะมีเงื่อนไขที่จำกัดให้เป็นเขตข้อมูลเดียว

### <a name="example-5"></a>ตัวอย่างที่ 5

ในตัวอย่างนี้ เราจะใช้ DataRoles สองอันแรกจากตัวอย่างก่อนหน้านี้ นอกจากนี้ยังกำหนด `grouping` และ `measure2` ด้วย

```json
"dataRole":[
    {
        "displayName": "Category",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Y Axis",
        "name": "measure",
        "kind": "Measure"
    },
    {
        "displayName": "Grouping with",
        "name": "grouping",
        "kind": "Grouping"
    },
    {
        "displayName": "X Axis",
        "name": "measure2",
        "kind": "Grouping"
    }
]
```

ในตอนนี้สำหรับการแมป:

```json
"dataViewMappings":{
    "categorical": {
        "categories": {
            "for": { "in": "category" }
        },
        "values": {
            "group": {
                "by": "grouping",
                "select":[
                    { "bind": { "to": "measure" } },
                    { "bind": { "to": "measure2" } }
                ]
            }
        }
    }
}
```

ที่นี่ความแตกต่างสำหรับวิธีที่เราทำการแมป categorical.values เราจะพูดว่า "แมป DataRole `measure` และ `measure2` ของฉันและข้อมูลที่จะถูกจัดกลุ่มโดย DataRole `grouping`"

### <a name="example-6"></a>ตัวอย่างที่ 6

นี่คือ DataRole

```json
"dataRoles": [
    {
        "displayName": "Categories",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Measures",
        "name": "measure",
        "kind": "Measure"
    },
    {
        "displayName": "Series",
        "name": "series",
        "kind": "Measure"
    }
]
```

นี่คือ dataViewMapping

```json
"dataViewMappings": [
    {
        "categorical": {
            "categories": {
                "for": {
                    "in": "category"
                }
            },
            "values": {
                "group": {
                    "by": "series",
                    "select": [{
                            "for": {
                                "in": "measure"
                            }
                        }
                    ]
                }
            }
        }
    }
]
```

ข้อมูล `dataview` แบบจัดกลุ่มอาจมีวิชวลเป็นแบบนี้

| จัดกลุ่ม |  |  | | | |
|-----|-----|------|------|------|------|
| | ปี | 2013 | 2014 | 2015 | 2016 |
| ประเทศ | | |
| สหรัฐอเมริกา | | x | x | 125 | 100 |
| แคนาดา | | x | 50 | 200 | x |
| เม็กซิโก | | 300 | x | x | x |
| สหราชอาณาจักร | | x | x | 75 | x |

Power BI จะสร้าง dataview แบบจัดกลุ่มให้กับคุณ ซึ่งเป็นชุดของหมวดหมู่

```JSON
{
    "categorical": {
        "categories": [
            {
                "source": {...},
                "values": [
                    "Canada",
                    "Mexico",
                    "UK",
                    "USA"
                ],
                "identity": [...],
                "identityFields": [...],
            }
        ]
    }
}
```

แต่ละหมวดหมู่จะถูกแมปไปยังชุดของค่าด้วย แต่ละค่าเหล่านี้จะถูกจัดกลุ่มตามชุดข้อมูล ซึ่งเป็นปี

ตัวอย่างเช่น ยอดขายในแคนาดาปี 2013 เป็น null, ยอดขายในแคนาดาปี 2014 เป็น 50

```JSON
{
    "values": [
        {
            "source": {...},
            "values": [
                null,
                300,
                null,
                null
            ],
            "identity": [...],
        },
        {
            "source": {...},
            "values": [
                50,
                null,
                150,
                null
            ],
            "identity": [...],
        },
        {
            "source": {...},
            "values": [
                200,
                null,
                null,
                125
            ],
            "identity": [...],
        },
        {
            "source": {...},
            "values": [
                null,
                null,
                null,
                100
            ],
            "identity": [...],
        }
    ]
}
```

## <a name="table-data-mapping"></a>การแมปข้อมูลตาราง

มุมมองข้อมูลตารางเป็นการแมปข้อมูลอย่างง่าย โดยพื้นฐานแล้วเป็นรายการของจุดข้อมูลที่สามารถรวมจุดข้อมูลตัวเลขได้

### <a name="example-7"></a>ตัวอย่างที่ 7

ด้วยความสามารถที่กำหนด:

```json
"dataRoles": [
    {
        "displayName": "Values",
        "name": "values",
        "kind": "Measure"
    }
]
```

```json
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
```

ข้อมูล `dataview` แบบตารางอาจมีวิชวลเป็นแบบนี้  

| ประเทศ| ปี | ยอดขาย |
|-----|-----|------|
| สหรัฐอเมริกา | 2016 | 100 |
| สหรัฐอเมริกา | 2015 | 50 |
| แคนาดา | 2015 | 200 |
| แคนาดา | 2015 | 50 |
| เม็กซิโก | 2013 | 300 |
| สหราชอาณาจักร | 2014 | 150 |
| สหรัฐอเมริกา | 2015 | 75 |

Power BI จะสร้าง dataview แบบตารางให้กับคุณ อย่าถือว่ามีการสั่งซื้อเกิดขึ้น

```JSON
{
    "table" : {
        "columns": [...],
        "rows": [
            [
                "Canada",
                2014,
                50
            ],
            [
                "Canada",
                2015,
                200
            ],
            [
                "Mexico",
                2013,
                300
            ],
            [
                "UK",
                2014,
                150
            ],
            [
                "USA",
                2015,
                100
            ],
            [
                "USA",
                2015,
                75
            ],
            [
                "USA",
                2016,
                100
            ]
        ]
    }
}
```

คุณสามารถรวมข้อมูลได้โดยเลือกเขตข้อมูลที่ต้องการและคลิกผลรวม  

![การรวมข้อมูล](./media/data-aggregation.png)

## <a name="matrix-data-mapping"></a>การแมปข้อมูลเมทริกซ์

การแมปข้อมูลเมทริกซ์คล้ายกับการแมปข้อมูลตาราง แต่มีการแสดงแถวแบบลำดับชั้น และหนึ่งในค่า `dataRole` สามารถใช้เป็นค่าส่วนหัวของคอลัมน์

```json
{
    "dataRoles": [
        {
            "name": "Category",
            "displayName": "Category",
            "displayNameKey": "Visual_Category",
            "kind": "Grouping"
        },
        {
            "name": "Column",
            "displayName": "Column",
            "displayNameKey": "Visual_Column",
            "kind": "Grouping"
        },
        {
            "name": "Measure",
            "displayName": "Measure",
            "displayNameKey": "Visual_Values",
            "kind": "Measure"
        }
    ],
    "dataViewMappings": [
        {
            "matrix": {
                "rows": {
                    "for": {
                        "in": "Category"
                    }
                },
                "columns": {
                    "for": {
                        "in": "Column"
                    }
                },
                "values": {
                    "select": [
                        {
                            "for": {
                                "in": "Measure"
                            }
                        }
                    ]
                }
            }
        }
    ]
}
```

Power BI สร้างโครงสร้างข้อมูลแบบลำดับชั้น โหนดรากของต้นไม้ประกอบด้วยข้อมูลจากคอลัมน์แรกของบทบาทข้อมูล `Category` กับโหนดลูกจากคอลัมน์บทบาทข้อมูลที่สอง

ชุดข้อมูล:

| โหนดพ่อ | โหนดลูก | โหนดเหลน | คอลัมน์ | ค่า |
|-----|-----|------|-------|-------|
| Parent1 | Child1 | Grand child1 | Col1 | 5 |
| Parent1 | Child1 | Grand child1 | Col2 | 6 |
| Parent1 | Child1 | Grand child2 | Col1 | 7 |
| Parent1 | Child1 | Grand child2 | Col2 | 8 |
| Parent1 | Child2 | Grand child3 | Col1 | 5 |
| Parent1 | Child2 | Grand child3 | Col2 | 3 |
| Parent1 | Child2 | Grand child4 | Col1 | 4 |
| Parent1 | Child2 | Grand child4 | Col2 | 9 |
| Parent1 | Child2 | Grand child5 | Col1 | 3 |
| Parent1 | Child2 | Grand child5 | Col2 | 5 |
| Parent2 | Child3 | Grand child6 | Col1 | 1 |
| Parent2 | Child3 | Grand child6 | Col2 | 2 |
| Parent2 | Child3 | Grand child7 | Col1 | 7 |
| Parent2 | Child3 | Grand child7 | Col2 | 1 |
| Parent2 | Child3 | Grand child8 | Col1 | 10 |
| Parent2 | Child3 | Grand child8 | Col2 | 13 |

วิชวลแบบเมทริกซ์หลักของ Power BI ทำให้แสดงผลเหมือนกับตาราง

![การแสดงผลด้วยภาพแบบเมทริกซ์](./media/matrix-visual-smaple.png)

วิชวลรับโครงสร้างข้อมูลตามที่อธิบายไว้ด้านล่าง (เฉพาะสองแถวแรกที่จะแสดง):

```json
{
    "metadata": {...},
    "matrix": {
        "rows": {
            "levels": [...],
            "root": {
                "childIdentityFields": [...],
                "children": [
                    {
                        "level": 0,
                        "levelValues": [...],
                        "value": "Parent1",
                        "identity": {...},
                        "childIdentityFields": [...],
                        "children": [
                            {
                                "level": 1,
                                "levelValues": [...],
                                "value": "Child1",
                                "identity": {...},
                                "childIdentityFields": [...],
                                "children": [
                                    {
                                        "level": 2,
                                        "levelValues": [...],
                                        "value": "Grand child1",
                                        "identity": {...},
                                        "values": {
                                            "0": {
                                                "value": 5 // value for Col1
                                            },
                                            "1": {
                                                "value": 6 // value for Col2
                                            }
                                        }
                                    },
                                    ...
                                ]
                            },
                            ...
                        ]
                    },
                    ...
                ]
            }
        },
        "columns": {
            "levels": [...],
            "root": {
                "childIdentityFields": [...],
                "children": [
                    {
                        "level": 0,
                        "levelValues": [...],
                        "value": "Col1",
                        "identity": {...}
                    },
                    {
                        "level": 0,
                        "levelValues": [...],
                        "value": "Col2",
                        "identity": {...}
                    },
                    ...
                ]
            }
        },
        "valueSources": [...]
    }
}
```

## <a name="data-reduction-algorithm"></a>อัลกอริทึมในการลดข้อมูล

`DataReductionAlgorithm` สามารถใช้ได้ถ้าคุณต้องการควบคุมจำนวนข้อมูลที่ได้รับใน DataView

ตามค่าเริ่มต้นวิชวลแบบกำหนดเองทั้งหมดมี DataReductionAlgorithm บนสุดที่ใช้กับ "count" ที่ตั้งค่าเป็น 1000 dataPoints ซึ่งเทียบเท่ากับการตั้งค่าคุณสมบัติต่อไปนี้ใน capabilities.json:

```json
"dataReductionAlgorithm": {
    "top": {
        "count": 1000
    }
}
```

คุณสามารถปรับเปลี่ยนค่า 'count' เป็นค่าจำนวนเต็มใดก็ได้สูงถึง 30000 วิชวลแบบกำหนดเองที่ใช้ภาษา R สามารถรองรับได้ถึง 150000 แถว

## <a name="data-reduction-algorithm-types"></a>ประเภทของอัลกอริทึมในการลดข้อมูล

มีการตั้งค่า `DataReductionAlgorithm` สี่ประเภท:

* `top` - ถ้าคุณต้องการจำกัดข้อมูลไปยังค่าที่นำมาจากด้านบนของชุดข้อมูล ค่า "count" อันดับแรกจะถูกนำมาจากชุดข้อมูล
* `bottom` - ถ้าคุณต้องการจำกัดข้อมูลไปยังค่าที่นำมาจากด้านล่างของชุดข้อมูล ค่า "count" อันดับท้ายสุดจะถูกนำมาจากชุดข้อมูล
* `sample` - ลดชุดข้อมูลโดยอัลกอริทึมการสุ่มตัวอย่างแบบง่ายซึ่งจำกัดจำนวนรายการ "count" ซึ่งหมายความว่ามีการรวมรายการแรกและสุดท้าย และจำนวนของรายการ "count" ที่มีช่วงที่เท่ากันระหว่างจำนวนดังกล่าว
ตัวอย่างเช่นถ้าคุณได้รับชุดข้อมูล [0, 1, 2, ... 100] และ `count: 9` จากนั้นคุณจะได้รับค่าต่อไปนี้ [0, 10, 20 ... 100]
* `window` - โหลด 'หน้าต่าง' หนึ่ง datapoints ในช่วงเวลาที่มีองค์ประกอบ "count" ปัจจุบัน `top` และ `window` เทียบเท่ากัน มีงานอยู่ในระหว่างดำเนินการเพื่อรองรับการตั้งค่าหน้าต่างเต็มรูปแบบ

## <a name="data-reduction-algorithm-usage"></a>การใช้งานอัลกอริทึมในการลดข้อมูล

`DataReductionAlgorithm` สามารถใช้ในการแมปข้อมูล `dataview` แบบจัดกลุ่ม ตาราง หรือเมทริกซ์ได้

ซึ่งสามารถตั้งค่าเป็น `categories` และ/หรือส่วนกลุ่มของ `values` สำหรับการแมปข้อมูลแบบจัดกลุ่มได้

### <a name="example-8"></a>ตัวอย่างที่ 8

```json
"dataViewMappings": {
    "categorical": {
        "categories": {
            "for": { "in": "category" },
            "dataReductionAlgorithm": {
                "window": {
                    "count": 300
                }
            }  
        },
        "values": {
            "group": {
                "by": "series",
                "select": [{
                        "for": {
                            "in": "measure"
                        }
                    }
                ],
                "dataReductionAlgorithm": {
                    "top": {
                        "count": 100
                    }
                }  
            }
        }
    }
}
```

อัลกอริทึมการลดข้อมูลสามารถนำไปใช้กับส่วน `rows` ของการแมปข้อมูล `dataview` แบบตารางได้

### <a name="example-9"></a>ตัวอย่างที่ 9

```json
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                },
                "dataReductionAlgorithm": {
                    "top": {
                        "count": 2000
                    }
                } 
            }
        }
    }
]
```

อัลกอริทึมการลดข้อมูลสามารถนำไปใช้กับส่วน `rows` และ/หรือ `columns` ของการแมปข้อมูล `matrix` `dataview` ได้

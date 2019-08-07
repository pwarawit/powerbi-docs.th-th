---
title: ที่คั่นหน้า
description: วิชวล Power BI สามารถจัดการกับการสลับบุ๊กมาร์กได้
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 90e3fc73cd49a5c84a5c2acc68a8cf5e0e4aa42b
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425516"
---
# <a name="add-bookmarks-support-for-power-bi-visuals"></a>เพิ่มการสนับสนุนของบุ๊กมาร์กสำหรับวิชวล Power BI

บุ๊กมาร์กรายงานของ Power BI ช่วยให้สามารถถ่ายภาพมุมมองที่กำหนดไว้ของหน้ารายงาน สถานะตัวเลือก สถานะการกรองของวิชวล แต่จำเป็นต้องมีการดำเนินการเพิ่มเติมจากฝั่งวิชวลแบบกำหนดเองเพื่อสนับสนุนบุ๊กมาร์กและตอบสนองต่อการเปลี่ยนแปลงอย่างถูกต้อง

อ่านเพิ่มเติมเกี่ยวกับบุ๊กมาร์กใน [เอกสารประกอบ](https://docs.microsoft.com/power-bi/desktop-bookmarks)

## <a name="report-bookmarks-support-in-your-visual"></a>การสนับสนุนของบุ๊กมาร์กรายงานในวิชวลของคุณ

ถ้าวิชวลของคุณโต้ตอบกับวิชวลอื่น ๆ ให้เลือกจุดข้อมูลหรือกรองวิชวลอื่น ๆ คุณต้องคืนค่าสถานะจากคุณสมบัติ

## <a name="how-to-add-report-bookmarks-support"></a>วิธีการเพิ่มการสนับสนุนของบุ๊กมาร์กหน้ารายงาน

1. ติดตั้ง (หรืออัปเดต) util ที่จำเป็น: `powerbi-visuals-utils-interactivityutils`(https://github.com/Microsoft/PowerBI-visuals-utils-interactivityutils/) เวอร์ชัน3.0.0 หรือสูงกว่า) ซึ่งประกอบด้วยคลาสที่เพิ่มเติมเพื่อจัดการกับตัวเลือกหรือตัวกรองของสถานะ ซึ่งจำเป็นสำหรับวิชวลตัวกรองและวิชวลใด ๆ โดยใช้ `InteractivityService`

2. อัปเดต API วิชวลเป็น 1.11.0 เพื่อใช้ `registerOnSelectCallback` ในอินสแตนซ์ของ `SelectionManager` จำเป็นสำหรับวิชวลที่ไม่ใช่ตัวกรองโดยใช้ `SelectionManager` ธรรมดาแทนที่จะเป็น `InteractivityService`

### <a name="how-custom-visuals-interact-with-power-bi-in-the-report-bookmarks-scenario"></a>วิธีการที่วิชวลแบบกำหนดเองโต้ตอบกับ Power BI ในสถานการณ์ของบุ๊กมาร์กรายงาน

ให้ลองพิจารณาตัวอย่างต่อไปนี้: ผู้ใช้สร้างบุ๊กมาร์กหลายรายการในหน้ารายงานด้วยสถานะตัวเลือกที่ต่างกันในแต่ละบุ๊กมาร์ก

อันดับแรก ผู้ใช้เลือกจุดข้อมูลในวิชวลของคุณ วิชวลโต้ตอบกับ Power BI และวิชวลอื่น ๆ โดยการส่งผ่านตัวเลือกไปยังโฮสต์ จากนั้นผู้ใช้เลือก "เพิ่ม" ใน `Bookmark panel` และ Power BI จะบันทึกตัวเลือกปัจจุบันสำหรับบุ๊กมาร์กใหม่

ซึ่งเกิดขึ้นซ้ำ ๆ เมื่อผู้ใช้เปลี่ยนแปลงตัวเลือกและเพิ่มบุ๊กมาร์กใหม่
เมื่อสร้างแล้ว ผู้ใช้สามารถสลับไปมาระหว่างบุ๊กมาร์กได้

เมื่อผู้ใช้เลือกบุ๊กมาร์ก Power BI จะคืนค่าตัวกรองหรือสถานะตัวเลือกที่บันทึกไว้และส่งผ่านไปยังวิชวล วิชวลอื่น ๆ จะถูกไฮไลท์หรือกรองตามสถานะที่จัดเก็บไว้ในบุ๊กมาร์ก โฮสต์ Power BI ที่รับผิดชอบสำหรับการดำเนินการ วิชวลของคุณมีหน้าที่รับผิดชอบในการสะท้อนสถานะตัวเลือกใหม่อย่างถูกต้อง (ตัวอย่างเช่น เปลี่ยนสีของจุดข้อมูลที่แสดง)

สถานะตัวเลือกใหม่จะได้รับการสื่อสารไปยังวิชวลผ่านเมธอด `update` อาร์กิวเมนต์ `options` จะประกอบด้วยคุณสมบัติพิเศษ: `options.jsonFilters` ซึ่งเป็น JSONFilter คุณสมบัติสามารถประกอบด้วย `Advanced Filter` และ `Tuple Filter`

วิชวลควรคืนค่าตัวกรองเพื่อแสดงสถานะที่สอดคล้องกันของวิชวลสำหรับบุ๊กมาร์กที่เลือก

หรือใช้ฟังก์ชันการเรียกกลับแบบพิเศษในการเรียกใช้เมธอด `registerOnSelectCallback` ที่ลงทะเบียนไว้ของ ISelectionManager ถ้าวิชวลใช้ตัวเลือกเท่านั้น

### <a name="visuals-with-selections"></a>วิชวลที่มีตัวเลือก

ถ้าวิชวลของคุณโต้ตอบกับวิชวลอื่น ๆโดยใช้ [ตัวเลือก](https://github.com/Microsoft/PowerBI-visuals/blob/master/Tutorial/Selection.md) คุณมีสองวิธีในการเพิ่มบุ๊กมาร์ก

* คุณสามารถใช้เมธอด `FilterManager.restoreSelectionIds` ได้ถ้าคุณ  **ไม่ได้ใช้ [`InteractivityService`](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)** ก่อนในวิชวลของคุณ

* ถ้าวิชวลของคุณใช้ **[`InteractivityService`](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)** ในการจัดการตัวเลือกแล้ว คุณควรใช้เมธอด `applySelectionFromFilter` ในอินสแตนซ์ของ `InteractivityService`

#### <a name="using-iselectionmanagerregisteronselectcallback"></a>การใช้ `ISelectionManager.registerOnSelectCallback`

เมื่อผู้ใช้คลิกที่บุ๊กมาร์ก Power BI จะเรียกใช้เมธอด `callback` ของวิชวลที่มีตัวเลือกที่สอดคล้องกัน 

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        //called when a selection was set by Power BI
    });
);
```

สมมติว่าคุณมีจุดข้อมูลในวิชวลของคุณที่สร้างขึ้นในเมธอด [`'visualTransform'`](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/master/src/barChart.ts#L74)

และ `datapoints` มีลักษณะดังนี้:

```typescript
visualDataPoints.push({
    category: categorical.categories[0].values[i],
    color: getCategoricalObjectValue<Fill>(categorical.categories[0], i, 'colorSelector', 'fill', defaultColor).solid.color,
    selectionId: host.createSelectionIdBuilder()
        .withCategory(categorical.categories[0], i)
        .createSelectionId(),
    selected: false
});
```

ดังนั้นคุณจะมี `visualDataPoints` เป็นจุดข้อมูลและอาร์เรย์ `ids` ที่ส่งผ่านไปยังฟังก์ชัน `callback`

ในขั้นตอนนี้ วิชวลควรเปรียบเทียบอาร์เรย์ของ `ISelectionId[]` ที่มีตัวเลือกในอาร์เรย์ `visualDataPoints` ของคุณและทำเครื่องหมายจุดข้อมูลที่สอดคล้องกันตามที่เลือกไว้

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        visualDataPoints.forEach(dataPoint => {
            ids.forEach(bookmarkSelection => {
                if (bookmarkSelection.equals(dataPoint.selectionId)) {
                    dataPoint.selected = true;
                }
            });
        });
    });
);
```

หลังจากอัปเดตจุดข้อมูลแล้ว จุดข้อมูลเหล่านี้จะแสดงสถานะตัวเลือกปัจจุบันที่จัดเก็บไว้ในวัตถุ `filter` จากนั้นเมื่อมีการแสดงจุดข้อมูล สถานะตัวเลือกของวิชวลแบบกำหนดเองจะตรงกับสถานะของบุ๊กมาร์ก

### <a name="using-interactivityservice-for-control-selections-in-the-visual"></a>การใช้ `InteractivityService` สำหรับตัวเลือกการควบคุมในวิชวล

ถ้าวิชวลของคุณใช้ `InteractivityService` คุณไม่จำเป็นต้องมีการดำเนินการเพิ่มเติมในการสนับสนุนของบุ๊กมาร์กในวิชวลของคุณ

Util จะจัดการสถานะตัวเลือกของวิชวลเมื่อผู้ใช้เลือกบุ๊กมาร์ก

### <a name="visuals-with-filter"></a>วิชวลที่มีตัวกรอง

สมมติว่าวิชวลสร้างตัวกรองข้อมูลตามช่วงวันที่ ดังนั้นเราจะมี `startDate` และ `endDate` เป็นจุดเริ่มต้นและจุดสิ้นสุดของช่วง
วิชวลสร้างตัวกรองขั้นสูงและเรียกใช้ `applyJsonFilter` เมธอดโฮสต์เพื่อกรองข้อมูลตามเงื่อนไขที่เกี่ยวข้อง
`target` เป็นตารางสำหรับการกรอง

```typescript
import { AdvancedFilter } from "powerbi-models";

const filter: IAdvancedFilter = new AdvancedFilter(
    target,
    "And",
    {
        operator: "GreaterThanOrEqual",
        value: startDate
            ? startDate.toJSON()
            : null
    },
    {
        operator: "LessThanOrEqual",
        value: endDate
            ? endDate.toJSON()
            : null
    });

this.host.applyJsonFilter(
    filter,
    "general",
    "filter",
    (startDate && endDate)
        ? FilterAction.merge
        : FilterAction.remove
);
```

แต่ละครั้งที่ผู้ใช้คลิกบุ๊กมาร์ก วิชวลแบบกำหนดเองจะมีการเรียกใช้ `update`

วิชวลแบบกำหนดเองควรตรวจสอบตัวกรองในวัตถุ:

```typescript
const filter: IAdvancedFilter = FilterManager.restoreFilter(
    && options.jsonFilters
    && options.jsonFilters[0] as any
) as IAdvancedFilter;
```

ถ้าวัตถุ `filter` ใช่ null วิชวลควรคืนค่าเงื่อนไขตัวกรองจากวัตถุ:

```typescript
const jsonFilters: AdvancedFilter = this.options.jsonFilters as AdvancedFilter[];

if (jsonFilters
    && jsonFilters[0]
    && jsonFilters[0].conditions
    && jsonFilters[0].conditions[0]
    && jsonFilters[0].conditions[1]
) {
    const startDate: Date = new Date(`${jsonFilters[0].conditions[0].value}`);
    const endDate: Date = new Date(`${jsonFilters[0].conditions[1].value}`);

    // apply restored conditions
} else {
    // apply default settings
}
```

หลังจากนั้น วิชวลควรเปลี่ยนสถานะภายใน จุดข้อมูล และการแสดงภาพวัตถุ (บรรทัด สี่เหลี่ยม เป็นต้นว) เพื่อแสดงเงื่อนไขปัจจุบัน

> [!IMPORTANT]
> ในสถานการณ์ของบุ๊กมาร์กรายงาน วิชวลไม่ควรเรียกใช้ `applyJsonFilter` เพื่อกรองวิชวลอื่น ๆ วิชวลเหล่านั้นจะถูกกรองโดย Power BI อยู่แล้ว

วิชวลตัวแบ่งข้อมูลเส้นเวลาจะเปลี่ยนตัวเลือกช่วงเพื่อให้สอดคล้องกับช่วงข้อมูล

สำหรับข้อมูลเพิ่มเติม ให้ดู [ที่เก็บตัวแบ่งข้อมูลเส้นเวลา](https://github.com/Microsoft/powerbi-visuals-timeline/commit/606f1152f59f82b5b5a367ff3b117372d129e597?diff=unified#diff-b6ef9a9ac3a3225f8bd0de84bee0a0df)

### <a name="filter-state-to-save-visual-properties-in-bookmarks"></a>กรองสถานะเพื่อบันทึกคุณสมบัติต่าง ๆ ของวิชวลในบุ๊กมาร์ก

คุณสมบัติ `filterState` นี้ทำให้เป็นคุณสมบัติส่วนหนึ่งของการกรอง วิชวลสามารถจัดเก็บค่าที่ต่างกันในบุ๊กมาร์ก

เมื่อต้องการบันทึกค่าคุณสมบัติเป็นสถานะตัวกรอง ควรทำเครื่องหมายคุณสมบัติวัตถุเป็น `"filterState": true` ใน `capabilities.json`

ตัวอย่างเช่น: `Timeline Slicer` จะจัดเก็บค่าคุณสมบัติ `Granularity` ในตัวกรอง และช่วยให้สามารถเปลี่ยนส่วนประกอบที่มีอยู่ในการเปลี่ยนบุ๊กมาร์กโดยผู้ใช้

สำหรับข้อมูลเพิ่มเติม ให้ดู[ที่เก็บตัวแบ่งข้อมูลเส้นเวลา](https://github.com/microsoft/powerbi-visuals-timeline/commit/8b7d82dd23cd2bd71817f1bc5d1e1732347a185e#diff-290828b604cfa62f1cb310f2e90c52fdR334)

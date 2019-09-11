---
title: เพิ่มการรองรับบุ๊กมาร์กสำหรับวิชวล Power BI
description: วิชวล Power BI สามารถจัดการกับการสลับบุ๊กมาร์กได้
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: c7fb8fa6fcf8c07f0d8f466892fff8d03a492a79
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/03/2019
ms.locfileid: "70237284"
---
# <a name="add-bookmark-support-for-power-bi-visuals"></a>เพิ่มการรองรับบุ๊กมาร์กสำหรับวิชวล Power BI

ด้วยบุ๊กมาร์กรายงานของ Power BI ช่วยให้คุณสามารถจับภาพมุมมองที่กำหนดค่าไว้ของหน้ารายงาน สถานะตัวเลือก และสถานะการกรองของวิชวลได้ แต่จำเป็นต้องมีการดำเนินการเพิ่มเติมจากฝั่งวิชวลแบบกำหนดเองเพื่อสนับสนุนบุ๊กมาร์กและตอบสนองต่อการเปลี่ยนแปลงอย่างถูกต้อง

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับบุ๊กมาร์ก โปรดดูหัวข้อ [ใช้บุ๊กมาร์กเพื่อแชร์ข้อมูลเชิงลึกและสร้างเรื่องราวใน Power BI](https://docs.microsoft.com/power-bi/desktop-bookmarks)

## <a name="report-bookmarks-support-in-your-visual"></a>การสนับสนุนของบุ๊กมาร์กรายงานในวิชวลของคุณ

หากวิชวลของคุณโต้ตอบกับวิชวลอื่น เลือกจุดข้อมูล หรือกรองวิชวลอื่น ๆ คุณจะต้องคืนค่าสถานะจากคุณสมบัติ

## <a name="add-report-bookmarks-support"></a>เพิ่มการสนับสนุนของบุ๊กมาร์กหน้ารายงาน

1. ติดตั้ง (หรืออัปเดต) ยูทิลิตี้ที่จำเป็น [powerbi-visuals-utils-interactivityutils](https://github.com/Microsoft/PowerBI-visuals-utils-interactivityutils/) เวอร์ชัน 3.0.0 หรือใหม่กว่า ซึ่งประกอบด้วยคลาสเพิ่มเติมเพื่อจัดการกับตัวเลือกหรือตัวกรองของสถานะ ซึ่งจำเป็นสำหรับวิชวลตัวกรองและวิชวลใดก็ตามที่ใช้ `InteractivityService`

2. อัปเดต API ของวิชวลไปเป็นเวอร์ชัน 1.11.0 เพื่อใช้ `registerOnSelectCallback` ในอินสแตนซ์ของ `SelectionManager` ซึ่งจำเป็นสำหรับวิชวลที่ไม่ใช่ตัวกรองที่ใช้ `SelectionManager` แบบธรรมดาแทนที่จะเป็น `InteractivityService`

### <a name="how-custom-visuals-interact-with-power-bi-in-report-bookmarks"></a>วิธีการที่วิชวลแบบกำหนดเองโต้ตอบกับ Power BI ในบุ๊กมาร์กรายงาน

ลองพิจารณาสถานการณ์ต่อไปนี้: คุณต้องการสร้างบุ๊กมาร์กหลายรายการในหน้ารายงานโดยมีสถานะตัวเลือกแตกต่างกันในแต่ละบุ๊กมาร์ก

อันดับแรก คุณเลือกจุดข้อมูลในวิชวลของคุณ วิชวลโต้ตอบกับ Power BI และวิชวลอื่น ๆ โดยการส่งผ่านตัวเลือกไปยังโฮสต์ จากนั้นคุณเลือก **เพิ่ม** ในบานหน้าต่าง **บุ๊กมาร์ก** และ Power BI จะบันทึกตัวเลือกปัจจุบันสำหรับบุ๊กมาร์กใหม่

ซึ่งเกิดขึ้นซ้ำ ๆ เมื่อคุณเปลี่ยนแปลงตัวเลือกและเพิ่มบุ๊กมาร์กใหม่ หลังจากที่คุณสร้างบุ๊กมาร์กแล้ว คุณสามารถสลับไปมาระหว่างไฟล์เหล่านั้นได้

เมื่อคุณเลือกบุ๊กมาร์ก Power BI จะคืนค่าตัวกรองหรือสถานะตัวเลือกที่บันทึกไว้และส่งผ่านไปยังวิชวล วิชวลอื่น ๆ จะถูกไฮไลต์หรือกรองตามสถานะที่จัดเก็บไว้ในบุ๊กมาร์ก โฮสต์ Power BI เป็นผู้รับผิดชอบสำหรับการดำเนินการนี้ วิชวลของคุณมีหน้าที่รับผิดชอบในการสะท้อนสถานะตัวเลือกใหม่อย่างถูกต้อง (ตัวอย่างเช่น สำหรับการเปลี่ยนสีของจุดข้อมูลที่แสดง)

สถานะตัวเลือกใหม่จะได้รับการสื่อสารไปยังวิชวลผ่านเมธอด `update` อาร์กิวเมนต์ `options` ประกอบด้วยคุณสมบัติพิเศษ, `options.jsonFilters` คุณสมบัติ JSONFilter สามารถประกอบด้วย `Advanced Filter` และ `Tuple Filter`

วิชวลควรคืนค่าตัวกรองเพื่อแสดงสถานะที่สอดคล้องกันของวิชวลสำหรับบุ๊กมาร์กที่เลือก หรือถ้าวิชวลใช้ตัวเลือกเท่านั้น คุณสามารถใช้ฟังก์ชันการเรียกกลับแบบพิเศษในการเรียกใช้เมธอด `registerOnSelectCallback` ที่ลงทะเบียนไว้ของ ISelectionManager

### <a name="visuals-with-selection"></a>วิชวลที่มีตัวเลือก

ถ้าวิชวลของคุณโต้ตอบกับวิชวลอื่นโดยใช้[ตัวเลือก](https://github.com/Microsoft/PowerBI-visuals/blob/master/Tutorial/Selection.md) คุณสามารถเพิ่มบุ๊กมาร์กอย่างใดอย่างหนึ่งในสองวิธี:

* ถ้าวิชวลไม่ได้ใช้ [InteractivityService](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md) คุณสามารถใช้เมธอด `FilterManager.restoreSelectionIds`

* ถ้าวิชวลนั้นใช้ [InteractivityService](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md) เพื่อจัดการตัวเลือกเรียบร้อยแล้ว คุณควรใช้เมธอด `applySelectionFromFilter` ในอินสแตนซ์ของ `InteractivityService`

#### <a name="use-iselectionmanagerregisteronselectcallback"></a>ใช้ ISelectionManager.registerOnSelectCallback

เมื่อคุณเลือกบุ๊กมาร์ก Power BI จะเรียกใช้เมธอด `callback` ของวิชวลที่มีตัวเลือกที่สอดคล้องกัน 

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        //called when a selection was set by Power BI
    });
);
```

ให้สมมติว่าคุณมีจุดข้อมูลในวิชวลของคุณ ซึ่งถูกสร้างขึ้นในเมธอด [visualTransform](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/master/src/barChart.ts#L74)

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

ตอนนี้คุณมี `visualDataPoints` เป็นจุดข้อมูลของคุณและอาร์เรย์ `ids` ที่ส่งผ่านไปยังฟังก์ชัน `callback`

ในขั้นตอนนี้ วิชวลควรเปรียบเทียบอาร์เรย์ `ISelectionId[]` ที่มีตัวเลือกในอาร์เรย์ `visualDataPoints` ของคุณและทำเครื่องหมายจุดข้อมูลที่สอดคล้องกันตามที่เลือกไว้

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

หลังจากคุณอัปเดตจุดข้อมูลแล้ว จุดข้อมูลเหล่านี้จะแสดงสถานะตัวเลือกปัจจุบันที่จัดเก็บอยู่ในออบเจ็กต์ `filter` จากนั้นเมื่อมีการแสดงผลจุดข้อมูล สถานะตัวเลือกของวิชวลแบบกำหนดเองจะตรงกับสถานะของบุ๊กมาร์ก

### <a name="use-interactivityservice-for-control-selections-in-the-visual"></a>ใช้ InteractivityService สำหรับตัวเลือกการควบคุมในวิชวล

ถ้าวิชวลของคุณใช้ `InteractivityService` คุณไม่จำเป็นต้องมีการดำเนินการเพิ่มเติมเพื่อสนับสนุนบุ๊กมาร์กในวิชวลของคุณ

เมื่อคุณเลือกบุ๊กมาร์ก ยูทิลิตี้จะจัดการสถานะตัวเลือกของวิชวล

### <a name="visuals-with-a-filter"></a>วิชวลที่มีตัวกรอง

สมมติว่าวิชวลสร้างตัวกรองข้อมูลตามช่วงวันที่ คุณมี `startDate` และ `endDate` เป็นวันที่เริ่มต้นและสิ้นสุดของช่วง

วิชวลสร้างตัวกรองขั้นสูงและเรียกใช้เมธอด `applyJsonFilter` ของโฮสต์เพื่อกรองข้อมูลตามเงื่อนไขที่เกี่ยวข้อง

เป้าหมายคือตารางที่ใช้สำหรับการกรอง

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

แต่ละครั้งที่คุณเลือกบุ๊กมาร์ก วิชวลแบบกำหนดเองจะมีการเรียกใช้ `update`

วิชวลแบบกำหนดเองควรตรวจสอบตัวกรองในวัตถุ:

```typescript
const filter: IAdvancedFilter = FilterManager.restoreFilter(
    && options.jsonFilters
    && options.jsonFilters[0] as any
) as IAdvancedFilter;
```

ถ้าออบเจ็กต์ `filter` ไม่เป็นค่า null วิชวลควรคืนค่าเงื่อนไขตัวกรองจากออบเจ็กต์:

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

หลังจากนั้น วิชวลควรเปลี่ยนแปลงสถานะภายในเพื่อสะท้อนถึงเงื่อนไขปัจจุบัน สถานะภายในประกอบด้วยออบเจ็กต์จุดข้อมูลและการแสดงผลข้อมูลด้วยภาพ (เส้น สี่เหลี่ยม และอื่นๆ)

> [!IMPORTANT]
> ในสถานการณ์ของบุ๊กมาร์กรายงาน วิชวลไม่ควรเรียกใช้ `applyJsonFilter` เพื่อกรองวิชวลอื่น ๆ วิชวลเหล่านั้นจะถูกกรองโดย Power BI อยู่แล้ว

วิชวลตัวแบ่งข้อมูลเส้นเวลาจะเปลี่ยนตัวเลือกช่วงเพื่อให้สอดคล้องกับช่วงข้อมูล

สำหรับข้อมูลเพิ่มเติม ให้ดู [ที่เก็บตัวแบ่งข้อมูลเส้นเวลา](https://github.com/Microsoft/powerbi-visuals-timeline/commit/606f1152f59f82b5b5a367ff3b117372d129e597?diff=unified#diff-b6ef9a9ac3a3225f8bd0de84bee0a0df)

### <a name="filter-the-state-to-save-visual-properties-in-bookmarks"></a>กรองสถานะเพื่อบันทึกคุณสมบัติต่าง ๆ ของวิชวลในบุ๊กมาร์ก

คุณสมบัติ `filterState` นี้ทำให้เป็นคุณสมบัติส่วนหนึ่งของการกรอง วิชวลสามารถจัดเก็บค่าที่ต่างกันในบุ๊กมาร์กได้หลากหลาย

หากต้องการบันทึกค่าคุณสมบัติเป็นสถานะตัวกรอง ให้ทำเครื่องหมายคุณสมบัติออบเจ็กต์เป็น `"filterState": true` ในไฟล์ *capabilities.json*

ตัวอย่างเช่น ตัวแบ่งข้อมูลเส้นเวลาจะเก็บค่าคุณสมบัติ `Granularity` ในตัวกรอง ซึ่งช่วยให้หน่วยย่อยที่สุด (Granularity) ในปัจจุบันสามารถเปลี่ยนแปลงได้เมื่อคุณเปลี่ยนบุ๊กมาร์ก

สำหรับข้อมูลเพิ่มเติม ให้ดู [ที่เก็บตัวแบ่งข้อมูลเส้นเวลา](https://github.com/microsoft/powerbi-visuals-timeline/commit/8b7d82dd23cd2bd71817f1bc5d1e1732347a185e#diff-290828b604cfa62f1cb310f2e90c52fdR334)

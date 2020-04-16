---
title: คำแนะนำเครื่องมือในวิชวล Power BI
description: บทความนี้อธิบายถึงวิธีการที่คุณสามารถแสดงคำแนะนำเครื่องมือในวิชวล Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 04/09/2020
ms.openlocfilehash: 3896d5d4698f815b5bce53dd80639ff6de975257
ms.sourcegitcommit: 915cb7d8088deb0d9d86f3b15dfb4f6f5b1b869c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/10/2020
ms.locfileid: "81006215"
---
# <a name="tooltips-in-power-bi-visuals"></a>คำแนะนำเครื่องมือในวิชวล Power BI

ขณะนี้วิชวลสามารถใช้ประโยชน์จากการสนับสนุนคำแนะนำเครื่องมือของ Power BI ได้แล้ว คำแนะนำเครื่องมือ Power BI จะจัดการการโต้ตอบต่อไปนี้:

* แสดงคำแนะนำเครื่องมือ
* ซ่อนคำแนะนำเครื่องมือ
* ย้ายคำแนะนำเครื่องมือ

คำแนะนำเครื่องมือสามารถแสดงองค์ประกอบที่เป็นข้อความพร้อมชื่อเรื่อง ค่าในสีที่กำหนดไว้ และความทึบไว้ในชุดพิกัดที่ระบุได้ ข้อมูลนี้จะถูกกำหนดไว้สำหรับ API และโฮสต์ Power BI จะแสดงผลในลักษณะเดียวกันกับที่แสดงคำแนะนำเครื่องมือสำหรับวิชวลต้นฉบับ

คำแนะนำเครื่องมือในแผนภูมิแท่งตัวอย่างจะแสดงในรูปภาพต่อไปนี้:

![คำแนะนำเครื่องมือแผนภูมิแท่งตัวอย่าง](media/add-tooltips/tooltips-in-samplebarchart.png)

คำแนะนำเครื่องมือก่อนหน้านี้แสดงหมวดหมู่และค่าของแท่งเดียว คุณสามารถขยายคำแนะนำเครื่องมือเดียวเพื่อแสดงหลายค่าได้

## <a name="manage-tooltips"></a>จัดการคำแนะนำเครื่องมือ

อินเทอร์เฟซที่คุณจัดการคำแนะนำเครื่องมือคือ "ITooltipService" ซึ่งอินเทอร์เฟซใช้เพื่อแจ้งโฮสต์ว่าจำเป็นต้องแสดง ลบ หรือย้ายคำแนะนำเครื่องมือ

```typescript
    interface ITooltipService {
        enabled(): boolean;
        show(options: TooltipShowOptions): void;
        move(options: TooltipMoveOptions): void;
        hide(options: TooltipHideOptions): void;
    }
```

วิชวลของคุณต้องรอการติดต่อจากกิจกรรมการใช้งานของเมาส์ภายในวิชวล และเรียกใช้ผู้รับมอบสิทธิ์ `show()`, `move()` และ`hide()` คนตามที่จำเป็นด้วยเนื้อหาที่เหมาะสมที่เติมใน `Tooltip****Options` ออบเจ็กต์
`TooltipShowOptions` และ `TooltipHideOptions` จะกำหนดสิ่งที่จะแสดงและวิธีการทำงานในกิจกรรมเหล่านี้ตามลำดับ

เนื่องจากการเรียกใช้วิธีการเหล่านี้เกี่ยวข้องกับกิจกรรมของผู้ใช้ เช่น กิจกรรมการย้ายเมาส์หรือการสัมผัส ซึ่งถือเป็นความคิดที่ดีที่จะสร้างตัวรอรับการติดต่อสำหรับกิจกรรมเหล่านี้ซึ่งจะเรียกใช้งานสมาชิก `TooltipService` รายตามลำดับ
การรวมตัวอย่างของเราในคลาสที่เรียกว่า `TooltipServiceWrapper`

### <a name="the-tooltipservicewrapper-class"></a>คลาส TooltipServiceWrapper

แนวคิดพื้นฐานที่อยู่เบื้องหลังคลาสนี้คือการระงับอินสแตนซ์ของ `TooltipService` การรอรับติดต่อจากกิจกรรมการใช้งานของเมาส์ D3 ผ่านองค์ประกอบที่เกี่ยวข้องและการเรียกใช้งานองค์ประกอบ `show()` และ `hide()` เมื่อจำเป็น

คลาสจะระงับและจัดการสถานะและตรรกะใดก็ตามที่เกี่ยวข้องสำหรับกิจกรรมณ์เหล่านี้ ซึ่งโดยส่วนใหญ่จะเปลี่ยนการอินเทอร์เฟซกับรหัส D3 พื้นฐานให้เหมาะสม การอินเทอร์เฟซและการแปลง D3 อยู่นอกขอบเขตสำหรับบทความนี้

คุณสามารถค้นหารหัสตัวอย่างฉบับสมบูรณ์ได้ใน [พื้นที่เก็บวิชวล SampleBarChart](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/981b021612d7b333adffe9f723ab27783c76fb14)

### <a name="create-tooltipservicewrapper"></a>สร้าง TooltipServiceWrapper

ตอนนี้ คอนสตรักเตอร์ของแผนภูมิแท่งมีสมาชิก `TooltipServiceWrapper` หนึ่งราย ซึ่งมีการสร้างอินสแตนซ์ในคอนสตรักเตอร์ด้วยอินสแตนซ์ `tooltipService` ของโฮสต์

```typescript
        private tooltipServiceWrapper: ITooltipServiceWrapper;

        this.tooltipServiceWrapper = createTooltipServiceWrapper(this.host.tooltipService, options.element);
```

คลาส `TooltipServiceWrapper` จะระงับ อินสแตนซ์ `tooltipService` ซึ่งเป็นองค์ประกอบของ D3 ระดับสูงของวิชวลและพารามิเตอร์การสัมผัส

```typescript
    class TooltipServiceWrapper implements ITooltipServiceWrapper {
        private handleTouchTimeoutId: number;
        private visualHostTooltipService: ITooltipService;
        private rootElement: Element;
        private handleTouchDelay: number;

        constructor(tooltipService: ITooltipService, rootElement: Element, handleTouchDelay: number) {
            this.visualHostTooltipService = tooltipService;
            this.handleTouchDelay = handleTouchDelay;
            this.rootElement = rootElement;
        }
        .
        .
        .
    }
```

จุดเข้าใช้งานเดียวสำหรับคลาสนี้เพื่อลงทะเบียนตัวรอรับการติดต่อของกิจกรรม `addTooltip` เมธอด

### <a name="the-addtooltip-method"></a>เมธอด addTooltip

```typescript
        public addTooltip<T>(
            selection: d3.Selection<Element>,
            getTooltipInfoDelegate: (args: TooltipEventArgs<T>) => VisualTooltipDataItem[],
            getDataPointIdentity: (args: TooltipEventArgs<T>) => ISelectionId,
            reloadTooltipDataOnMouseMove?: boolean): void {

            if (!selection || !this.visualHostTooltipService.enabled()) {
                return;
            }
        ...
        ...
        }
```

* **การเลือก: d3.Selection<Element>** : องค์ประกอบ d3 ที่จัดการคำแนะนำเครื่องมือ

* **getTooltipInfoDelegate: (args: TooltipEventArgs<T>) => VisualTooltipDataItem[]** : การมอบสิทธิ์สำหรับการเติมเนื้อหาคำแนะนำเครื่องมือ (สิ่งที่จะแสดง) ต่อบริบท

* **getDataPointIdentity: (args: TooltipEventArgs<T>) => ISelectionId**: การมอบสิทธิ์สำหรับการเรียกใช้ ID จุดข้อมูล (ไม่ได้ใช้ในตัวอย่างนี้) 

* **reloadTooltipDataOnMouseMove? boolean**: บูลีนที่ระบุว่าจะรีเฟรชข้อมูลคำแนะนำเครื่องมือในระหว่างกิจกรรม MouseMove (ไม่ได้ใช้ในตัวอย่างนี้)

ในขณะที่คุณสามารถดูได้ `addTooltip` จะออกจากระบบโดยไม่มีการดำเนินการถ้าปิดใช้งาน `tooltipService` อยู่หรือไม่มีการเลือกที่แท้จริง

### <a name="call-the-show-method-to-display-a-tooltip"></a>เรียกใช้เมธอดการแสดงเพื่อแสดงคำแนะนำเครื่องมือ

เมธอด `addTooltip` ถัดไปจะรอรับติดต่อจากกิจกรรม `mouseover` ของ D3 ดังแสดงในโค้ดต่อไปนี้:

```typescript
        ...
        ...
        selection.on("mouseover.tooltip", () => {
            // Ignore mouseover while handling touch events
            if (!this.canDisplayTooltip(d3.event))
                return;

            let tooltipEventArgs = this.makeTooltipEventArgs<T>(rootNode, true, false);
            if (!tooltipEventArgs)
                return;

            let tooltipInfo = getTooltipInfoDelegate(tooltipEventArgs);
            if (tooltipInfo == null)
                return;

            let selectionId = getDataPointIdentity(tooltipEventArgs);

            this.visualHostTooltipService.show({
                coordinates: tooltipEventArgs.coordinates,
                isTouchEvent: false,
                dataItems: tooltipInfo,
                identities: selectionId ? [selectionId] : [],
            });
        });
```

* **makeTooltipEventArgs**: แยกบริบทจากองค์ประกอบที่เลือกของ D3 เป็น tooltipEventArgs ซึ่งจะคำนวณพิกัดเช่นกัน

* **getTooltipInfoDelegate**: จากนั้นสร้างเนื้อหาของคำแนะนำเครื่องมือจาก tooltipEventArgs ซึ่งเป็นการเรียกกลับไปยังคลาส BarChart เพราะว่าเป็นตรรกะของวิชวล นี่คือเนื้อหาข้อความจริงที่จะแสดงในคำแนะนำเครื่องมือ

* **getDataPointIdentity**: ไม่ได้ใช้ในตัวอย่างนี้

* **this.visualHostTooltipService.show**: การเรียกเพื่อแสดงคำแนะนำเครื่องมือ  

สามารถพบการจัดการเพิ่มเติมได้ในตัวอย่างสำหรับกิจกรรม `mouseout` และ `mousemove`

สำหรับข้อมูลเพิ่มเติม ให้ดู [ที่เก็บวิชวล SampleBarChart](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/981b021612d7b333adffe9f723ab27783c76fb14)

### <a name="populate-the-tooltip-content-by-the-gettooltipdata-method"></a>เติมเนื้อหาคำแนะนำเครื่องมือตามเมธอด getTooltipData

คลาส BarChart ถูกเพิ่มเข้ามาพร้อมกับสมาชิก `getTooltipData` ที่เพียงแค่แยก `category`, `value` และ `color`ของจุดข้อมูลเป็นองค์ประกอบของ VisualTooltipDataItem []

```typescript
        private static getTooltipData(value: any): VisualTooltipDataItem[] {
            return [{
                displayName: value.category,
                value: value.value.toString(),
                color: value.color,
                header: 'ToolTip Title'
            }];
        }
```

ในการนำไปใช้งานก่อนหน้านี้ สมาชิก `header` แต่คุณสามารถใช้สำหรับการดำเนินการที่ซับซ้อนมากขึ้น ซึ่งจำเป็นต้องมีข้อมูลแบบไดนามิก คุณสามารถเติมข้อมูล `VisualTooltipDataItem[]` ที่มีมากกว่าหนึ่งองค์ประกอบได้ ซึ่งจะเพิ่มหลายบรรทัดในคำแนะนำเครื่องมือ จะมีประโยชน์ในวิชวล เช่น แผนภูมิแท่งแบบเรียงซ้อน ซึ่งคำแนะนำเครื่องมืออาจแสดงข้อมูลจากมากกว่าจุดข้อมูลเดียว

### <a name="call-the-addtooltip-method"></a>เรียกใช้เมธอด addTooltip

ขั้นตอนสุดท้ายคือการเรียกใช้เมธอด `addTooltip` เมื่อข้อมูลจริงอาจเปลี่ยนแปลง การเรียกใช้นี้เกิดขึ้นในเมธอด `BarChart.update()` การเรียกใช้ถูกสร้างขึ้นเพื่อตรวจสอบการเลือกองค์ประกอบ 'แท่ง' ทั้งหมด ซึ่งส่งผ่านเฉพาะ `BarChart.getTooltipData()` ดังที่กล่าวถึงข้างต้นเท่านั้น

```typescript
        this.tooltipServiceWrapper.addTooltip(this.barContainer.selectAll('.bar'),
            (tooltipEvent: TooltipEventArgs<number>) => BarChart.getTooltipData(tooltipEvent.data),
            (tooltipEvent: TooltipEventArgs<number>) => null);
```

## <a name="add-report-page-tooltips"></a>เพิ่มคำแนะนำเครื่องมือของหน้ารายงาน

หากต้องการเพิ่มคำแนะนำเครื่องมือของหน้ารายงาน คุณจะพบการเปลี่ยนแปลงส่วนใหญ่ในไฟล์ *capabilities.json*

ตัวอย่าง Schema คือ

```json
{
    "tooltips": {
        "supportedTypes": {
            "default": true,
            "canvas": true
        },
        "roles": [
            "tooltips"
        ]
    }
}
```

คุณสามารถกำหนดคำแนะนำเครื่องมือของหน้ารายงานในบานหน้าต่าง**รูปแบบ**ได้

![คำแนะนำเครื่องมือของหน้ารายงาน](media/add-tooltips/report-page-tooltips.png)

* `supportedTypes`: การกำหนดค่าคำแนะนำเครื่องมือที่วิชวลรองรับและจะปรากฏบนช่องเขตข้อมูลดังกล่าว 
   * `default`: ระบุว่ามีการสนับสนุนการผูกคำแนะนำเครื่องมือ "อัตโนมัติ" ผ่านเขตข้อมูลหรือไม่ 
   * `canvas`: ระบุว่าคำแนะนำเครื่องมือของหน้ารายงานได้รับการสนับสนุนหรือไม่

* `roles`: (เป็นทางเลือก) หลังจากกำหนดแล้ว ให้แนะนำบทบาทข้อมูลที่จะผูกไว้กับตัวเลือกคำแนะนำเครื่องมือที่เลือกในช่องเขตข้อมูลดังกล่าว

สำหรับข้อมูลเพิ่มเติม ให้ดู [คำแนะนำในการใช้งานคำแนะนำเครื่องมือของหน้ารายงาน](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#tooltips)

เมื่อต้องการแสดงคำแนะนำเครื่องมือของหน้ารายงาน หลังจากโฮสต์ Power BI เรียกใช้ `ITooltipService.Show(options: TooltipShowOptions)` หรือ `ITooltipService.Move(options: TooltipMoveOptions)` แล้วจะใช้ selectionId (คุณสมบัติ `identities` ของอาร์กิวเมนต์ `options` ก่อนหน้า) เมื่อต้องการเรียกใช้คำแนะนำเครื่องมือ SelectionId ควรแสดงข้อมูลที่เลือกไว้ (ประเภท, ชุดข้อมูล และอื่นๆ) ของรายการที่คุณวางเมาส์อยู่เหนือ

ตัวอย่างของการส่ง selectionId ไปยังการเรียกแสดงคำแนะนำเครื่องมือแสดงในโค้ดต่อไปนี้:

```typescript
    this.tooltipServiceWrapper.addTooltip(this.barContainer.selectAll('.bar'),
        (tooltipEvent: TooltipEventArgs<number>) => BarChart.getTooltipData(tooltipEvent.data),
        (tooltipEvent: TooltipEventArgs<number>) => tooltipEvent.data.selectionID);
```

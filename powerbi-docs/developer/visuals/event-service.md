---
title: เหตุการณ์การแสดงผล
description: วิชวล Power BI สามารถแจ้ง Power BI ว่าวิชวลเหล่านั้นพร้อมที่จะส่งออกไปยัง Power Point/PDF
author: Yarovinsky
ms.author: alexyar
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 46166b3503a770e033b98474fcf9240235296cc2
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425102"
---
# <a name="event-service"></a>บริการเหตุการณ์

API ใหม่ประกอบด้วยสามเมธอด (เริ่มต้น เสร็จสิ้น หรือล้มเหลว) ซึ่งควรถูกเรียกใช้ระหว่างการแสดงผล

เมื่อเริ่มต้นการแสดงผล รหัสวิชวลแบบกำหนดเองจะเรียกใช้เมธอด renderingStarted เพื่อระบุว่ากระบวนการการแสดงข้อมูลเริ่มต้นแล้ว

ถ้าการแสดงผลเสร็จสมบูรณ์ รหัสวิชวลแบบกำหนดเองจะเรียกใช้เมธอด `renderingFinished` แจ้งเตือนตัวรอรับการติดต่อทราบ (**ส่วนใหญ่ 'ส่งออกเป็น PDF' และ 'ส่งออกไปยัง PowerPoint '** ) ว่ารูปภาพของวิชวลพร้อมใช้งานแล้ว

ในกรณีที่เกิดปัญหาขึ้นระหว่างกระบวนการแสดงผลการป้องกันการแสดงภาพแบบกำหนดเองจากการดำเนินการเสร็จสมบูรณ์ รหัสวิชวลแบบกำหนดเองควรเรียกใช้เมธอด `renderingFailed` ที่แจ้งเตือนตัวรอรับการติดต่อว่ากระบวนการการแสดงข้อมูลยังไม่เสร็จสมบูรณ์ นอกจากนี้ เมธอดนี้ยังมีสตริงที่เลือกได้สำหรับสาเหตุของความล้มเหลว

## <a name="usage"></a>การใช้งาน

```typescript
export interface IVisualHost extends extensibility.IVisualHost {
    eventService: IVisualEventService ;
}

/**
 * An interface for reporting rendering events
 */
export interface IVisualEventService {
    /**
     * Should be called just before the actual rendering was started. 
     * Usually at the very start of the update method.
     *
     * @param options - the visual update options received as update parameter
     */
    renderingStarted(options: VisualUpdateOptions): void;

    /**
     * Shoudl be called immediately after finishing successfull rendering.
     * 
     * @param options - the visual update options received as update parameter
     */
    renderingFinished(options: VisualUpdateOptions): void;

    /**
     * Called when rendering failed with optional reason string
     * 
     * @param options - the visual update options received as update parameter
     * @param reason - the option failure reason string
     */
    renderingFailed(options: VisualUpdateOptions, reason?: string): void;
}
```

### <a name="simple-sample-the-visual-hasnt-any-animations-on-rendering"></a>ตัวอย่างง่าย ๆ วิชวลไม่มีภาพเคลื่อนไหวใด ๆ บนการแสดงผล

```typescript
    export class Visual implements IVisual {
        ...
        private events: IVisualEventService;
        ...

        constructor(options: VisualConstructorOptions) {
            ...
            this.events = options.host.eventService;
            ...
        }

        public update(options: VisualUpdateOptions) {
            this.events.renderingStarted(options);
            ...
            this.events.renderingFinished(options);
        }
```

### <a name="sample-the-visual-with-animation"></a>ตัวอย่าง วิชวลที่มีภาพเคลื่อนไหว

หากวิชวลมีภาพเคลื่อนไหวหรือฟังก์ชั่น async สำหรับการแสดงผล เมธอด `renderingFinished` ่ควรจะเรียกว่าหลังจากภาพเคลื่อนไหวหรือฟังก์ชั่น async ภายใน

```typescript
    export class Visual implements IVisual {
        ...
        private events: IVisualEventService;
        private element: HTMLElement;
        ...

        constructor(options: VisualConstructorOptions) {
            ...
            this.events = options.host.eventService;
            this.element = options.element;
            ...
        }

        public update(options: VisualUpdateOptions) {
            this.events.renderingStarted(options);
            ...
            // read more https://github.com/d3/d3-transition/blob/master/README.md#transition_end
            d3.select(this.element).transition().duration(100).style("opacity","0").end().then(() => {
                // renderingFinished called after transition end
                this.events.renderingFinished(options);
            });
        }
```

## <a name="rendering-events-for-visual-certification"></a>กิจกรรมการแสดงผลสำหรับการรับรองวิชวล

การสนับสนุนของกิจกรรมการแสดงผลด้วยวิชวลเป็นหนึ่งในข้อกำหนดของการรับรองวิชวล อ่านเพิ่มเติมเกี่ยวกับ [ข้อกำหนดการรับรอง](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements)

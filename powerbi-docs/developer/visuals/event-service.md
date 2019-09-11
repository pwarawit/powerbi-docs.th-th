---
title: แสดงผลเหตุการณ์ในวิชวล Power BI
description: วิชวล Power BI สามารถแจ้งเตือน Power BI ว่าวิชวลเหล่านั้นพร้อมสำหรับส่งออกไปยัง PowerPoint หรือ PDF แล้ว
author: Yarovinsky
ms.author: alexyar
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: b481ce94e5025045466a05d71e30a00f02be7ead
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/03/2019
ms.locfileid: "70237171"
---
# <a name="render-events-in-power-bi-visuals"></a>แสดงผลเหตุการณ์ในวิชวล Power BI

API ใหม่ประกอบด้วยสามเมธอด (`started`, `finished` หรือ `failed`) ซึ่งควรถูกเรียกใช้ระหว่างการแสดงผล

เมื่อการแสดงผลเริ่มต้นขึ้น โค้ดวิชวล Power BI จะเรียกใช้เมธอด `renderingStarted` เพื่อระบุว่ากระบวนการแสดงผลข้อมูลเริ่มต้นแล้ว

ถ้าการแสดงผลเสร็จสมบูรณ์ โค้ดวิชวล Power BI จะเรียกใช้เมธอด `renderingFinished` แจ้งเตือนตัวรอรับการติดต่อให้ทราบทันที (ส่วนใหญ่ *ส่งออกเป็น PDF* และ *ส่งออกเป็น PowerPoint*) ว่ารูปภาพของวิชวลพร้อมสำหรับการส่งออกแล้ว

ถ้าเกิดปัญหาขึ้นระหว่างกระบวนการ วิชวล Power BI จะถูกป้องกันไม่ให้แสดงผลได้สำเร็จ หากต้องการแจ้งตัวรอรับการติดต่อว่ากระบวนการแสดงผลยังไม่เสร็จสมบูรณ์โค้ดวิชวล Power BI ควรเรียกใช้เมธอด `renderingFailed` นอกจากนี้ เมธอดนี้ยังมีสตริงแบบเลือกได้เพื่อระบุเหตุผลสำหรับความล้มเหลว

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
     * Should be called just before the actual rendering starts, 
     * usually at the start of the update method
     *
     * @param options - the visual update options received as an update parameter
     */
    renderingStarted(options: VisualUpdateOptions): void;

    /**
     * Should be called immediately after rendering finishes successfully
     * 
     * @param options - the visual update options received as an update parameter
     */
    renderingFinished(options: VisualUpdateOptions): void;

    /**
     * Called when rendering fails, with an optional reason string
     * 
     * @param options - the visual update options received as an update parameter
     * @param reason - the optional failure reason string
     */
    renderingFailed(options: VisualUpdateOptions, reason?: string): void;
}
```

### <a name="sample-the-visual-displays-no-animations"></a>ตัวอย่าง: วิชวลไม่แสดงภาพเคลื่อนไหว

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

### <a name="sample-the-visual-displays-animations"></a>ตัวอย่าง: วิชวลแสดงภาพเคลื่อนไหว

หากวิชวลมีภาพเคลื่อนไหวหรือฟังก์ชันอะซิงโครนัสสำหรับการแสดงผล เมธอด `renderingFinished` ควรถูกเรียกหลังจากภาพเคลื่อนไหวหรือภายในฟังก์ชันอะซิงโครนัส

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
            // Learn more at https://github.com/d3/d3-transition/blob/master/README.md#transition_end
            d3.select(this.element).transition().duration(100).style("opacity","0").end().then(() => {
                // renderingFinished called after transition end
                this.events.renderingFinished(options);
            });
        }
```

## <a name="rendering-events-for-visual-certification"></a>กิจกรรมการแสดงผลสำหรับการรับรองวิชวล

ข้อกำหนดหนึ่งของใบรับรองวิชวลคือการสนับสนุนการแสดงผลเหตุการณ์ด้วยวิชวล สำหรับข้อมูลเพิ่มเติม โปรดดูหัวข้อ [ข้อกำหนดของใบรับรอง](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements)

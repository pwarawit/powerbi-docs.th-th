---
title: หน้าเริ่มต้น
description: วิธีการเพิ่มหน้าเริ่มต้นไปยังวิชวล Power BI
author: sranins
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 44cc9314b31803c97d3203d4aab846685d8f88fa
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424895"
---
# <a name="landing-page"></a>หน้าเริ่มต้น

ด้วย API 2.3.0 คุณสามารถเพิ่มหน้าเริ่มต้นไปยังวิชวลของคุณ เพื่อทำเช่นนั้น ให้เพิ่ม `supportsLandingPage` ในความสามารถและตั้งค่าเป็นจริง ซึ่งจะเตรียมใช้งานและปรับปรุงวิชวลก่อนที่จะเพิ่มข้อมูลลงไป (หมายความว่าจะไม่แสดงลายน้ำ) ดังนั้นคุณสามารถออกแบบหน้าเริ่มต้นของคุณได้เพื่อแสดงในวิชวลตราบใดที่ไม่มีข้อมูล

```typescript
export class BarChart implements IVisual {
    //...
    private element: HTMLElement;
    private isLandingPageOn: boolean;
    private LandingPageRemoved: boolean;
    private LandingPage: d3.Selection<any>;

    constructor(options: VisualConstructorOptions) {
            //...
            this.element = options.element;
            //...
    }

    public update(options: VisualUpdateOptions) {
    //...
        this.HandleLandingPage(options);
    }

    private HandleLandingPage(options: VisualUpdateOptions) {
        if(!options.dataViews || !options.dataViews.length) {
            if(!this.isLandingPageOn) {
                this.isLandingPageOn = true;
                const SampleLandingPage: Element = this.createSampleLandingPage(); //create a landing page
                this.element.appendChild(SampleLandingPage);
                this.LandingPage = d3.select(SampleLandingPage);
            }

        } else {
                if(this.isLandingPageOn && !this.LandingPageRemoved){
                    this.LandingPageRemoved = true;
                    this.LandingPage.remove();
                }
        }
    }
```

ตัวอย่าง

![สกรีนช็อตของหน้าเริ่มต้น](./media/landing-page.png)

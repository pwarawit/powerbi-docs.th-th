---
title: เพิ่มหน้าเริ่มต้น (landing page) ไปยังวิชวล Power BI ของคุณ
description: บทความนี้อธิบายวิธีเพิ่มหน้าเริ่มต้นไปยังวิชวล Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: 6f1590d5635ed6e55833350027c52379e5d7cf51
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "79379982"
---
# <a name="add-a-landing-page-to-your-power-bi-visuals"></a>เพิ่มหน้าเริ่มต้น (landing page) ไปยังวิชวล Power BI ของคุณ

ด้วย API 2.3.0 คุณสามารถเพิ่มหน้าเริ่มต้นไปยังวิชวล Power BI ของคุณได้ เมื่อต้องการทำเช่นนั้น ให้เพิ่ม `supportsLandingPage` ไปยังความสามารถและตั้งค่าเป็น จริง การดำเนินการนี้จะเริ่มต้นและอัปเดตวิชวลของคุณก่อนที่คุณจะเพิ่มข้อมูลลงไป เนื่องจากวิชวลจะไม่แสดงลายน้ำอีกต่อไป คุณสามารถออกแบบหน้าเริ่มต้นของคุณเองเพื่อให้แสดงในวิชวลได้ตราบใดที่ไม่มีข้อมูลอยู่

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

ตัวอย่างหน้าเริ่มต้นจะแสดงในรูปต่อไปนี้:

![สกรีนช็อตของหน้าเริ่มต้น](media/landing-page/app-landing-page.png)

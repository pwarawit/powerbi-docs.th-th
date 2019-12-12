---
title: การย้ายข้อมูลไปยัง powerbi-visuals-tools 3.x
description: เริ่มต้นใช้งาน powerbi-visuals-tools เวอร์ชันใหม่
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 245475feeb43ee544117aaa54969f2de1e207cd5
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/02/2019
ms.locfileid: "74696293"
---
# <a name="migrate-to-the-new-powerbi-visuals-tools-3xx"></a>ย้ายข้อมูลไปยัง powerbi-visuals-tools 3.x.x ใหม่

เริ่มต้นจากเวอร์ชัน 3 เครื่องมือการแสดงผลด้วยภาพของ Power BI จะใช้ Webpack เพื่อสร้างการแสดงผลด้วยภาพแบบกำหนดเอง
เวอร์ชันใหม่จะให้โอกาสใหม่ๆ กับนักพัฒนาในการสร้างการแสดงผลด้วยภาพ ดังนี้

* TypeScript v3.x.x โดยค่าเริ่มต้น เริ่มต้นจาก TypeScript 1.5 คำศัพท์เฉพาะมีการเปลี่ยนแปลง [อ่านเพิ่มเติมเกี่ยวกับโมดูล TypeScript](https://www.typescriptlang.org/docs/handbook/modules.html)

* รองรับโมดูล ES6 คุณไม่จำเป็นต้องใช้ [externalJS](migrate-to-new-tools.md#fix-loading-external-libraries) อีกต่อไป ให้ใช้ ES6 ในการนำเข้าแทน

* รองรับ [D3v5](https://d3js.org/) เวอร์ชันใหม่และไลบรารีจากโมดูล  ES6 อื่นๆ

* ลบขนาดแพ็คเกจ Webpack ใช้ [Tree Shaking](https://webpack.js.org/guides/tree-shaking/) เพื่อลบโค้ดที่ไม่ใช่ออก ซึ่งจะลดโค้ดของ JS และส่งผลให้คุณสามารถโหลดวิชวลได้อย่างมีประสิทธิภาพมากขึ้น

* ประสิทธิภาพของ API ที่ปรับปรุง

* ไลบรารี Globalize.js [ผสานรวม](migrate-to-new-tools.md#remove-globalizejs-library)กับ utils การจัดรูปแบบ

* เครื่องมือจะใช้ [webpack-bundle-analyzer](https://github.com/webpack-contrib/webpack-bundle-analyzer) เพื่อแสดงฐานโค้ดของวิชวล

ขั้นตอนการย้ายข้อมูลทั้งหมดสำหรับเครื่องมือ Power BI Visuals อธิบายไว้ด้านล่าง

## <a name="backward-compatibility"></a>ความเข้ากันได้ย้อนหลัง

เครื่องมือใหม่จะบันทึกความเข้ากันได้ย้อนหลังสำหรับฐานโค้ดวิชวลเก่าแต่จำเป็นต้องมีการเปลี่ยนแปลงเพิ่มเติมในการโหลดไลบรารีภายนอก

Lib ซึ่งสนับสนุนระบบโมดูลจะถูกนำเข้าเป็นโมดูล Webpack Lib และโค้ดแหล่งที่มาของวิชวลอื่นๆ ทั้งหมดจะรวมไว้ในหนึ่งโมดูล

ตัวแปรส่วนกลางเช่น JQuery และ Lodash ที่ใช้ในเครื่องมือ pbiviz ก่อนหน้านี้จะใช้ไม่ได้แล้ว ซึ่งหมายความว่าหากโค้ดวิชวลเก่าอยู่ในตัวแปรส่วนกลาง วิชวลดังกล่าวจะไม่สามารถใช้งานได้ในกรณีนี้

เครื่องมือ Power BI Visuals รุ่นก่อนหน้าจำเป็นต้องมีการกำหนดระดับวิชวลภายใต้โมดูล `powerbi.extensibility.visual`

## <a name="how-to-install-powerbi-visuals-tools"></a>วิธีการติดตั้ง powerbi-visuals-tools

สามารถติดตั้งชุดเครื่องมือใหม่ได้โดยการดำเนินการคำสั่ง

```cmd
npm install -g powerbi-visuals-tools
```

ตัวอย่างของวิชวล sampleBarChart และ[การเปลี่ยนแปลง](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/package.json#L16)ที่สอดคล้องกันใน `package.json`

```json
{
    "name": "visual",
    "version": "1.2.3",
    "scripts": {
        "pbiviz": "pbiviz",
        "start": "pbiviz start",
        "lint": "tslint -r \"node_modules/tslint-microsoft-contrib\"  \"+(src|test)/**/*.ts\"",
        "test": "pbiviz package --resources --no-minify --no-pbiviz"
    },
    "devDependencies": {
      "@types/d3": "5.0.0",
      "d3": "5.5.0",
      "powerbi-visuals-tools": "^3.1.0",
      "tslint": "^4.4.2",
      "tslint-microsoft-contrib": "^4.0.0"
    }
}
```

## <a name="how-to-install-power-bi-custom-visuals-api"></a>วิธีการติดตั้ง Power BI Custom Visuals API

powerbi-visual-tools เวอร์ชันใหม่จะไม่มีเวอร์ชัน API ทั้งหมดภายใน แต่นักพัฒนาควรติดตั้งแพ็คเกจ [`powerbi-visuals-api`](https://www.npmjs.com/package/powerbi-visuals-api) เวอร์ชันที่ต้องการแทน แพ็คเกจของเวอร์ชันจะตรงกับเวอร์ชัน API ของ Power BI Custom Visuals และจะมีการกำหนดทุกประเภทสำหรับ Power BI Custom Visuals API

เพิ่ม`powerbi-visuals-api`ไปยังการอ้างอิงของโครงการโดยใช้คำสั่งดำเนินการ`npm install --save-dev powerbi-visuals-api`
และคุณควรลบลิงก์ไปยังการกำหนดประเภทของ API เก่าออก เพราะประเภทจาก `powerbi-visuals-api` จะรวมโดยอัตโนมัติด้วย Webpack การเปลี่ยนแปลงที่สอดคล้องกันจะอยู่ในบรรทัด[นี้](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/package.json#L14)ของ `package.json`

## <a name="update-tsconfigjson"></a>อัปเดต `tsconfig.json`

หากต้องการใช้โมดูลภายนอก คุณควรสลับตัวเลือก `out` เป็น `outDir`
เลือก `"outDir": "./.tmp/build/",` แทน `"out": "./.tmp/build/visual.js",`

จำเป็นต้องดำเนินการเนื่องจากไฟล์ TypeScript จะถูกรวบรวมเป็นไฟล์ JavaScript แยกต่างหาก นี่คือเหตุผลที่คุณไม่จำเป็นต้องระบุไฟล์ visual.js เป็นเอาท์พุต

และคุณยังสามารถเปลี่ยนตัวเลือก `target` เป็น `ES6` ได้หากต้องการใช้ JavaScript ที่ทันสมัยเป็นเอาท์พุต [ไม่บังคับ](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/tsconfig.json#L6)

## <a name="update-custom-visuals-utils"></a>อัปเดต utils วิชวลแบบกำหนดเอง

หากคุณใช้ powerbi-visuals-utils](https://www.npmjs.com/search?q=powerbi-visuals-utils) อย่างใดอย่างหนึ่ง คุณควรอัปเดตให้เป็นเวอร์ชันล่าสุดด้วย

ใช้คำสั่ง `npm install powerbi-visuals-utils-<UTILNAME> --save` (ตัวอย่าง `npm install powerbi-visuals-utils-dataviewutils --save`) เพื่อดาวน์โหลดเวอร์ชันใหม่ที่มีโมดูลภายนอกของ TypeScript

คุณจะเห็นตัวอย่างใน[พื้นที่เก็บข้อมูล](https://github.com/Microsoft/powerbi-visuals-mekkochart)ของ MekkoChart
วิชวลนี้ใช้ utils ทั้งหมด

## <a name="remove-globalizejs-library"></a>ลบไลบรารี Globalize.js

[powerbi-visuals-utils-formattingutils@4.3](https://www.npmjs.com/package/powerbi-visuals-utils-formattingutils) เวอร์ชันใหม่จะมี globalize.js มาให้ทันที
คุณไม่จำเป็นต้องรวมไลบรารีนี้ในโครงการด้วยตนเอง
การแปลงภาษาที่จำเป็นทั้งหมดจะเพิ่มไปยังแพ็คเกจสุดท้ายโดยอัตโนมัติ

## <a name="fix-loading-external-libraries"></a>แก้ไขการโหลดไลบรารีภายนอก

ให้รวมไฟล์ JS ใหม่หลังจาก Lib ในแถว `externalJS` ของ `pbiviz.json` ตัวอย่าง:

```JSON
"externalJS": [
    ...
    "node_modules/lodash/lodash.min.js",
    "externalJS/init.lodash.js",
    ...
]
```

นำเข้า Lib ในแหล่งข้อมูล ตัวอย่างสำหรับ `lodash-es`

```JS
import * as _ from "lodash-es";
```

ที่ซึ่ง `_` คือตัวแปรส่วนกลางสำหรับไลบรารี `lodash`

## <a name="changes-in-the-visuals-sources"></a>การเปลี่ยนแปลงในแหล่งข้อมูลวิชวล

การเปลี่ยนแปลงหลักคือการแปลงโมดูลภายในเป็นโมดูลภายนอกเนื่องจากคุณไม่สามารถใช้โมดูลภายนอกภายในโมดูลภายในได้

การเปลี่ยนแปลงดังกล่าวอธิบายถึงการแก้ไขที่ใช้กับ Sample Bar Chart

คำอธิบายอย่างละเอียดของการเปลี่ยนแปลงอยู่ด้านล่าง

1. ลบการกำหนดโมดูลทั้งหมดออกจากแต่ละไฟล์ของโค้ด[ต้นฉบับ](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L153)

    ```typescript
    module powerbi.extensibility.visual {
        ...
    }
    ```

2. [นำเข้าการกำหนด API วิชวลแบบกำหนดเองของ Power BI](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L2)

    ```typescript
    import powerbi from "powerbi-visuals-api";
    ```

3. [นำเข้า](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L12-L23)อินเทอร์เฟซหรือคลาสที่จำเป็นจากโมดูลภายใน `powerbi`

    ```typescript
    import PrimitiveValue = powerbi.PrimitiveValue; 
    import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions; 
    import VisualConstructorOptions = powerbi.extensibility.visual.VisualConstructorOptions; 
    import IVisualHost = powerbi.extensibility.visual.IVisualHost; 
    import IColorPalette = powerbi.extensibility.IColorPalette; 
    import IVisual = powerbi.extensibility.visual.IVisual; 
    import VisualObjectInstance = powerbi.VisualObjectInstance; 
    import VisualObjectInstanceEnumeration = powerbi.VisualObjectInstanceEnumeration; 
    import EnumerateVisualObjectInstancesOptions = powerbi.EnumerateVisualObjectInstancesOptions; 
    import Fill = powerbi.Fill; 
    import VisualTooltipDataItem = powerbi.extensibility.VisualTooltipDataItem; 
    import ISelectionManager = powerbi.extensibility.ISelectionManager; 
    ```

4. [นำเข้า](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L1)ไลบรารี D3.js

    ```typescript
    import * as d3 from "d3";
    ```

    หรือนำเข้าเฉพาะโมดูลไลบรารี d3 ที่จำเป็น

    ```typescript
    import { max, min } from "d3-array";
    ```

5. [นำเข้า](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L4-L10) utils, คลาส, อินเทอร์เฟซที่กำหนดในโครงการวิชวลไปยังไฟล์ต้นฉบับหลัก

    ```typescript
    import { getLocalizedString } from "./localization/localizationHelper";
    import { getValue, getCategoricalObjectValue } from "./objectEnumerationUtility";
    import {
        ITooltipServiceWrapper,
        TooltipEventArgs,
        createTooltipServiceWrapper
    } from "./tooltipServiceWrapper";
    ```

### <a name="import-css-styles"></a>นำเข้ารูปแบบ CSS

เครื่องมือเวอร์ชันใหม่จะให้นักพัฒนานำเข้ารูปแบบ CSS, LESS ไปยังโค้ด TypeScript โดยตรง

ดังนั้น [ส่วนรูปแบบ](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/pbiviz.json#L22)ที่ใช้ก่อนหน้านี้จะถูกเพิกเฉยโดยผู้รวบรวม

หากต้องการใช้สไตล์ชีต ให้เปิดไฟล์ ts หลักและเพิ่มบรรทัดต่อไปนี้  

```typescript
import "./../style/visual.less";
```  

รูปแบบ CSS, LESS จะถูกรวบรวมโดยอัตโนมัติ  

### <a name="externaljs-section-in-pbivizjson"></a>ส่วน externalJS ใน pbiviz.json

เครื่องมือ[ไม่ต้องการ](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/pbiviz.json#L20)รายการ `externalJS` เพื่อโหลดไปยังชุดวิชวล เนื่องจาก webpack จะมี Lib ที่นำเข้าทั้งหมด

**ส่วน externalJS ใน pbivi.json ควรว่างเปล่า**

เรีกยใช้คำสั่ง `npm run package` ทั่วไปเพื่อสร้างแพ็คเกจวิชวลหรือ `npm run start` เพื่อเริ่มเซิร์ฟเวอร์นักพัฒนา

## <a name="updating-d3js-library-to-version-5"></a>อัปเดต ไลบรารี D3.js เป็นเวอร์ชัน 5

คุณจะเริ่มใช้ไลบรารี D3.js เวอร์ชันใหม่ด้วยเครื่องมือนี้

เรียกใช้คำสั่งเพื่ออัปเดต D3 ในโครงการวิชวล

`npm install --save d3@5` เพื่อติดตั้ง D3.js ใหม่

`npm install --save-dev @types/d3@5` เพื่อติดตั้งข้อกำหนดประเภทใหม่สำหรับ D3.js

มีการเปลี่ยนแปลงที่เสียหาหลายอย่างและคุณควรแก้ไขโค้ดเพื่อใช้ D3.js ใหม่

1. อินเทอร์เฟซ `d3.Selection<T>` [ถูกเปลี่ยน](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR157)เป็น `Selection<GElement extends BaseType, Datum, PElement extends BaseType, PDatum>`

2. คุณจะไม่สามารถใช้แอตทริบิวต์ต่างๆ โดนการเรียกใช้วิธีการ `attr` เพียงวิธีเดียว คุณ[ควรส่ง](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR278)แต่ละแอตทริบิวต์ในการเรียกใช้วิธีการ `attr` ที่แตกต่างกัน ซึ่ง[คล้าย](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR247)กับวิธีการ `style` เช่นกัน

3. D3.js v4 จะแนะนำวิธีการรวมแบบใหม่ โดยปกติวิธีการนี้ใช้เพื่อรวมการป้อนและอัปเดตการเลือกหลังจากการรวมข้อมูล [เรียกใช้วิธีการรวม](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/83fe8d52d362dccd0034dd8e32c94080d9376b29#diff-433142f7814fee940a0ffc98dc75bfcbR272)เพื่อใช้ d3 อย่างถูกต้อง

[อ่านเพิ่มเติม](https://github.com/d3/d3/blob/master/CHANGES.md)เกี่ยวกับการเปลี่ยนแปลงในไลบรารี D3.js

## <a name="babel"></a>Babel

เริ่มต้นจากเวอร์ชัน 3.1 เครื่องมือจะใช้ Babel ในการคอมไพล์โค้ด JS ที่ทันสมัยแบบใหม่ไปเป็น ES5 เก่าเพื่อรองรับเบราว์เซอร์ที่หลากหลาย

ตัวเลือกนี้จะเปิดใช้โดยค่าเริ่มต้น แต่คุณต้องนำเข้าแพ็คเกจ [`@babel/polyfill`](https://babeljs.io/docs/en/babel-polyfill) ด้วยตนเอง

ใช้คำสั่งเพื่อติดตั้งแพ็คเกจ

`npm install --save @babel/polyfill`

และนำเข้าแพ็คเกจในจุดเริ่มต้นของโค้ดวิชวล (ปกติจะเป็นไฟล์  'src/visual.ts')

`import "@babel/polyfill";`

อ่านเพิ่มเติมเกี่ยวกับ Babel [ในเอกสาร](https://babeljs.io/docs/en/)

สุดท้ายให้เรียกใช้ [webpack-visualizer](https://github.com/chrisbateman/webpack-visualizer) เพื่อแสดงฐานของโค้ดวิชวล  

![สถิติโค้ดวิชวล](./media/webpack-stats.png)

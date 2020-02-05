---
title: การย้ายข้อมูลไปยัง powerbi-visuals-tools เวอร์ชัน 3.x
description: เริ่มต้นใช้งาน powerbi-visuals-tools เวอร์ชันใหม่
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: d9af0ab870732990201ab3478d71fdafa9e13439
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/04/2020
ms.locfileid: "76818835"
---
# <a name="migrate-to-the-new-powerbi-visuals-tools-version-3x"></a>ย้ายข้อมูลไปยัง powerbi-visuals-tools ใหม่เวอร์ชัน 3.*x*

ใช้ Webpack เพื่อสร้างวิชวลแบบกำหนดเองโดยเริ่มต้นจากเครื่องมือการแสดงผลด้วยภาพของ Power BI เวอร์ชัน 3 (powerbi-visuals-tools หรือ `pbiviz`)
เวอร์ชันใหม่นี้นำเสนอการปรับปรุงจำนวนมากสำหรับการสร้างวิชวลให้แก่นักพัฒนา:

- TypeScript เวอร์ชัน 3.*x* ถูกใช้ตามค่าเริ่มต้น ศัพท์เฉพาะมีการเปลี่ยนแปลง โดยเริ่มตั้งแต่ TypeScript 1.5 [อ่านเพิ่มเติมเกี่ยวกับโมดูล TypeScript](https://www.typescriptlang.org/docs/handbook/modules.html)

- โมดูล ECMAScript 6 (ES6) ได้รับการสนับสนุน ใช้การนำเข้า ES6 ในขณะนี้แทนที่จะเป็น [externalJS](migrate-to-new-tools.md#configure-loading-of-external-libraries)

- รองรับเอกสารที่มีการขับเคลื่อนด้วยข้อมูล ([D3v5](https://d3js.org/)) เวอร์ชันใหม่และไลบรารีจากโมดูล ES6 อื่นๆ

- ลบขนาดแพ็คเกจ [Tree shaking](https://webpack.js.org/guides/tree-shaking/) ถูกใช้โดย Webpack เพื่อลบรหัสที่ไม่มีการใช้งานออก ซึ่งจะลดรหัส JavaScript และเพิ่มประสิทธิภาพที่ดียิ่งขึ้นในการโหลดวิชวล

- ประสิทธิภาพของ API ที่ปรับปรุง

- ไลบรารี Globalize.js [ผสานรวม](migrate-to-new-tools.md#remove-the- globalizejs-library) กับ FormattingUtils

- เครื่องมือการแสดงผลด้วยภาพของ Power BI ใช้ [webpack-bundle-analyzer](https://github.com/webpack-contrib/webpack-bundle-analyzer) เพื่อแสดงโค้ดตามภาพวิชวลดังกล่าว

บทความนี้อธิบายถึงขั้นตอนการย้ายข้อมูลทั้งหมดสำหรับเครื่องมือการแสดงผลด้วยภาพของ Power BI เวอร์ชันใหม่

## <a name="backward-compatibility"></a>ความเข้ากันได้ย้อนหลัง

เครื่องมือใหม่จะบันทึกความเข้ากันได้ย้อนหลังสำหรับฐานโค้ดวิชวลเก่า แต่จำเป็นต้องมีการเปลี่ยนแปลงเพิ่มเติมในการโหลดไลบรารีภายนอก

ไลบรารีซึ่งสนับสนุนระบบโมดูลจะถูกนำเข้าเป็นโมดูล Webpack ไลบรารีและโค้ดตันฉบับอื่น ๆ ทั้งหมดสำหรับวิชวลจะถูกรวมเข้าไว้เป็นโมดูลเดียว

ตัวแปรส่วนกลาง เช่น JQuery และ Lodash ที่ใช้ในเครื่องมือการแสดงผลด้วยภาพของ Power BI ก่อนหน้านี้จะใช้ไม่ได้แล้ว หากโค้ดเดิมสำหรับวิชวลของคุณขึ้นอยู่กับตัวแปรส่วนกลาง วิชวลดังกล่าวอาจจะไม่สามารถทำงานร่วมกับเครื่องมือใหม่ได้

เครื่องมือการแสดงผลด้วยภาพของ Power BI เวอร์ชันก่อนหน้า บังคับให้กำหนดระดับของวิชวลภายใต้โมดูล `powerbi.extensibility.visual` ด้วยเครื่องมือเวอร์ชันใหม่นี้ คุณต้องกำหนดระดับของวิชวลในไฟล์ TypeScript (.ts) หลักแทน โดยทั่วไป ไฟล์ดังกล่าวคือ `src/visual.ts`

## <a name="install-powerbi-visuals-tools"></a>ติดตั้ง powerbi-visuals-tools

เรียกใช้คำสั่งนี้เพื่อติดตั้งเครื่องมือใหม่:

```cmd
npm install -g powerbi-visuals-tools
```

โค้ดต่อไปนี้มาจากไฟล์ `package.json` ใน [ที่เก็บภาพ sampleBarChart](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/package.json#L15) หลังจากที่มีการอัปเดตโครงการวิชวลเพื่อให้สามารถทำงานร่วมกับเครื่องมือใหม่ได้:

```json
{
    "name": "visual",
    "version": "3.0.0",
    "scripts": {
        "pbiviz": "pbiviz",
        "start": "pbiviz start",
        "package": "pbiviz package",
        "lint": "tslint -r \"node_modules/tslint-microsoft-contrib\"  \"+(src|test)/**/*.ts\"",
        "test": "pbiviz package --resources --no-minify --no-pbiviz"
    },
    "devDependencies": {
        "@types/d3": "5.7.2",
        "d3": "5.12.0",
        "powerbi-visuals-api": "^2.6.1",
        "powerbi-visuals-tools": "^3.1.7",
        "powerbi-visuals-utils-dataviewutils": "^2.2.1",
        "powerbi-visuals-utils-formattingutils": "^4.4.2",
        "powerbi-visuals-utils-interactivityutils": "^5.6.0",
        "powerbi-visuals-utils-tooltiputils": "^2.3.1",
        "tslint": "^5.20.0",
        "tslint-microsoft-contrib": "^6.2.0"
    }
}
```

## <a name="install-the-power-bi-custom-visuals-api"></a>ติดตั้ง Power BI Custom Visuals API

powerbi-visuals-tools เวอร์ชันใหม่ จะไม่มีเวอร์ชัน API ทั้งหมด คุณจะต้องติดตั้งแพ็คเกจ [powerbi-visuals-api](https://www.npmjs.com/package/powerbi-visuals-api) เวอร์ชันเฉพาะแทน เลือกเวอร์ชันของแพ็คเกจที่ตรงกับเวอร์ชัน API ของวิชวลแบบกำหนดเองของ Power BI ของคุณ แพ็คเกจจะมีข้อกำหนดประเภททั้งหมดสำหรับ Power BI Custom Visuals API

เพิ่ม `powerbi-visuals-api` ไปที่การอ้างอิงโครงการของคุณของโครงการ โดยการเรียกใช้คำสั่งนี้:

```cmd
npm install --save-dev powerbi-visuals-api
```

นอกจากนี้ ให้ลบลิงก์ใด ๆ ที่เชื่อมโยงถึงข้อกำหนดประเภท API เดิม เนื่องจาก Webpack จะรวมถึงประเภทต่างๆ จาก `powerbi-visuals-api` โดยอัตโนมัติ การเปลี่ยนแปลงต่าง ๆ ที่สอดคล้องกันจะอยู่ใน [package.json](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/package.json#L14) และ [tsconfig.json](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/tsconfig.json#L14)

## <a name="update-tsconfigjson"></a>อัปเดต tsconfig.json

เมื่อต้องการใช้โมดูลภายนอก ให้เปลี่ยนตัวเลือก `out` เป็น `outDir` ตัวอย่างเช่น ใช้ `"outDir": "./.tmp/build/",` แทน `"out": "./.tmp/build/visual.js",`

การเปลี่ยนแปลงนี้เป็นเรื่องจำเป็น เนื่องจากไฟล์ TypeScript จะถูกรวบรวมเป็นไฟล์ JavaScript แบบแยกต่างหาก นี่คือเหตุผลที่คุณไม่ต้องระบุไฟล์ visual.js เป็นค่าเอาต์พุตอีกต่อไป

นอกจากนี้ คุณยังสามารถเปลี่ยนตัวเลือก `target` เป็น `ES6` ได้ หากคุณต้องการใช้ JavaScript แบบรุ่นใหม่เป็นค่าเอาต์พุต การเปลี่ยนแปลงนี้เป็นตัวเลือก[แบบไม่บังคับ](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/tsconfig.json#L7)

## <a name="update-custom-visuals-utilities"></a>อัปเดตอรรถประโยชน์ของวิชวลแบบกำหนดเอง

หากคุณใช้รายการใด ๆ ของแพ็คเกจ [powerbi-visuals-utils](https://www.npmjs.com/search?q=powerbi-visuals-utils) ให้อัปเดตเป็นเวอร์ชันล่าสุดเช่นกัน หากต้องการดำเนินการ ให้เรียกใช้คำสั่งนี้:

```cmd
npm install powerbi-visuals-utils-<UTILNAME> --save
```

ตัวอย่างเช่น เมื่อต้องการดาวน์โหลดเวอร์ชันใหม่ที่มีโมดูลภายนอกของ TypeScript ให้เรียกใช้: 

```cmd
npm install powerbi-visuals-utils-dataviewutils --save
```

ตัวอย่างเช่น วิชวลที่ใช้แพ็คเกจ `powerbi-visuals-utils` ทั้งหมด ดูที่ [ทีเ่ก็บข้อมูล MekkoChart](https://github.com/Microsoft/powerbi-visuals-mekkochart)

## <a name="remove-the-globalizejs-library"></a>ลบไลบรารี Globalize.js

เวอร์ชันใหม่ของ [powerbi-visuals-utils-formattingutils@4.3](https://www.npmjs.com/package/powerbi-visuals-utils-formattingutils) รวมถึง Globalize.js ดังนั้น คุณไม่จำเป็นต้องรวมไลบรารีนี้ด้วยตนเองในโครงการของคุณ การแปลงภาษาที่จำเป็นทั้งหมดจะเพิ่มไปยังแพ็คเกจสุดท้ายโดยอัตโนมัติ

## <a name="configure-loading-of-external-libraries"></a>กำหนดค่าการโหลดไลบรารีภายนอก

รวมไฟล์ JavaScript ใหม่หลังไลบรารีในอาร์เรย์ `externalJS` ของ `pbiviz.json` ตัวอย่างเช่น:

```JSON
"externalJS": [
    ...
    "node_modules/lodash/lodash.min.js",
    "externalJS/init.lodash.js",
    ...
]
```

นำเข้าไลบรารีต่าง ๆ ในโค้ดต้นฉบับของคุณ ตัวอย่างเช่น สำหรับ `lodash-es` ให้ใช้คำสั่งนี้:

```JS
import * as _ from "lodash-es";
```

ในตัวอย่างก่อนหน้า `_` คือตัวแปรส่วนกลางสำหรับไลบรารี `lodash`

## <a name="make-changes-in-the-sources-of-your-visuals"></a>ทำการเปลี่ยนแปลงในแหล่งข้อมูลของวิชวลของคุณ

การเปลี่ยนแปลงหลักที่คุณต้องดำเนินการคือ แปลงโมดูลภายในเป็นโมดูลภายนอก คุณไม่สามรถใช้โมดูลภายนอกภายในโมดูลภายในได้

รายละเอียดต่อไปนี้คือคำอธิบายโดยละเอียดของการเปลี่ยนแปลงที่ดำเนินการ การปรับเปลี่ยนต่าง ๆ ระบุในบริบทของตัวอย่างโค้ดวิชวลแบบกำหนดเองของแผนภูมิแท่ง:

1. ลบข้อกำหนดโมดูลทั้งหมดออกจากแต่ละไฟล์ของ[โค้ดต้นฉบับ](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbL1-L3):

    ```typescript
    module powerbi.extensibility.visual {
        ...
    }
    ```

2. [นำเข้าข้อกำหนด API ของวิชวลแบบกำหนดเองของ Power BI](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR4):

    ```typescript
    import powerbi from "powerbi-visuals-api";
    ```

3. [นำเข้าอินเทอร์เฟซหรือระดับที่จำเป็น](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR12-R35) จากโมดูลภายใน `powerbi`

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

4. [นำเข้าไลบรารี D3.js](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR2):

    ```typescript
    import * as d3 from "d3";
    ```

    หรือนำเข้าเฉพาะโมดูลไลบรารี D3 ที่จำเป็นเท่านั้น:

    ```typescript
    import { max, min } from "d3-array";
    ```

5. [นำเข้าอรรถประโยชน์ ระดับ และอินเทอรเฟซ์ที่กำหนดในโครงการวิชวล](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR38-R41) ไปยังไฟล์ต้นฉบับหลัก:

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

เวอร์ชันใหม่ของเครื่องมืออนุญาตให้คุณสามารถนำเข้ารูปแบบ `CSS` และ `Less` เป็นโค้ด TypeScript โดยตรง ขณะนี้ [ส่วนรูปแบบ](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/pbiviz.json#L21)ที่ถูกใช้ก่อนหน้านี ถูกเพิกเฉยโดยคอมไพเลอร์

เมื่อต้องการใช้สไตล์ชีตของคุณ เปิดไฟล์ TypeScript (.ts) หลัก และเพิ่มบรรทัดนี้:  

```typescript
import "./../style/visual.less";
```  

รูปแบบ `CSS` และ `Less` ของคุณจะถูกรวมเข้าด้วยกันโดยอัตโนมัติ

### <a name="externaljs-section-in-pbivizjson"></a>ส่วน externalJS ใน pbiviz.json

เครื่องมือต่าง ๆ [ไม่จำเป็นต้องใช้รายการ`externalJS`ไลบรารี](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-a1a7bbee7e7d2f9d449f4b534532bcf2R20) เพื่อโหลดเป็นไฟล์รวมวิชวล เนื่องจาก Webpack รวมไลบรารีทั้งหมดที่นำเข้าอยู่แล้ว

> [!NOTE]
> ใน `pbiviz.json` ให้ปล่อยส่วน `externalJS` ให้เว้นว่างไว้

ใช้คำสั่งทั่วไป `npm run package` เพื่อสร้างแพ็คเกจวิชวลหรือ `npm run start` เพื่อเริ่มใช้เซิร์ฟเวอร์การพัฒนา

## <a name="update-the-d3js-library-to-version-5"></a>อัปเดตไลบรารี D3.js เป็นเวอร์ชัน 5

ด้วยเครื่องมือวิชวลใหม่ คุณสามารถเริ่มต้นใช้ไลบรารี D3.js เวอร์ชันใหม่ได้เลย เรียกใช้คำสั่งเหล่านี้เพื่ออัปเดต D3 ในโครงการวิชวลของคุณ:

- `npm install --save d3@5` เพื่อติดตั้ง D3.js ใหม่

- `npm install --save-dev @types/d3@5` เพื่อติดตั้งข้อกำหนดประเภทใหม่สำหรับ D3.js

> [!IMPORTANT]
> D3 เวอร์ชัน 5 มาพร้อมกับการเปลี่ยนแปลงครั้งใหญ่มากมาย

ปรับเปลี่ยนโค้ดของคุณเพื่อทำงานร่วมกับ D3.js ใหม่ได้:

- อินเทอร์เฟซ `d3.Selection<T>` [ถูกเปลี่ยน](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR157) เป็น `Selection<GElement extends BaseType, Datum, PElement extends BaseType, PDatum>`

- คุณไม่สามารถปรับใช้แอตทริบิวต์ต่าง ๆ โดยใช้วิธีการ `attr` เพียงวิธีเดียว คุณจะต้อง[ผ่านแอตทริบิวต์แต่ละรายการในแต่ละครั้ง](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR278) เป็น `attr` แทน ทำให้การเรียกใช้ [แยกต่างหากไปยังวิธีการ `style`](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR247) ด้วยเช่นกัน

- D3.js เวอร์ชัน 4 มาพร้อมกับวิธีการ `merge` ใหม่ โดยปกติแล้ว วิธีการนี้จะถูกใช้เพื่อผสานรายการที่เลือก `enter` และ `update` หลังจากทำการรวมข้อมูลแล้ว เมื่อต้องการใช้ D3 อย่างถูกต้อง [เรียกใช้วิธีการ `merge`](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/83fe8d52d362dccd0034dd8e32c94080d9376b29#diff-433142f7814fee940a0ffc98dc75bfcbR272)

[อ่านเพิ่มเติม](https://github.com/d3/d3/blob/master/CHANGES.md)เกี่ยวกับการเปลี่ยนแปลงต่าง ๆ ในไลบรารี D3.js

## <a name="install-babel-and-core-js"></a>ติดตั้ง Babel และ core-js

เครื่องมือจะใช้ Babel ในการคอมไพล์โค้ด JavaScript แบบรุ่นใหม่เป็น ECMAScript 5 (ES5) แบบเก่า เพื่อรองรับเบราว์เซอร์ที่หลากหลาย โดยเริ่มต้นตั้งแต่เวอร์ชัน 3.1

ตัวเลือก Babel นี้จะเปิดใช้งานไว้อยู่แล้วตามค่าเริ่มต้น แต่คุณจำต้องนำเข้าแพ็คเกจ [`core-js`](https://www.npmjs.com/package/core-js) ด้วยตนเอง เรียกใช้คำสั่งนี้เพื่อติดตั้งแพ็คเกจ:

```cmd
npm install --save core-js
```

จากนั้น นำเข้าแพ็คเกจที่จุดเริ่มต้นของโค้ดวิชวล โดยทั่วไป จะเป็นไฟล์ 'src/visual.ts'

```JS
import "core-js/stable";
```

อ่านเพิ่มเติมเกี่ยวกับ Babel [ในเอกสาร](https://babeljs.io/docs/en/)

---
title: บทนำการทดสอบหน่วย
description: วิธีการเขียนการทดสอบหน่วยสำหรับโครงการวิชวล Power BI
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 06/18/2019
ms.openlocfilehash: 4b16eaad9b541bf6e5d8df49ffda99d9bbd5bbf2
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424550"
---
# <a name="tutorial-add-unit-tests-for-power-bi-visual-projects"></a>บทช่วยสอน: เพิ่มการทดสอบหน่วยสำหรับโครงการวิชวล Power BI

บทช่วยสอนนี้อธิบายขั้นตอนพื้นฐานในการเขียนการทดสอบหน่วยสำหรับวิชวล Power BI ของคุณ

ในบทช่วยสอนนี้ เราจะพิจารณา

* วิธีใช้โปรแกรมรันการทดสอบ karma.js, การทดสอบกรอบการทำงาน - jasmine.js
* วิธีใช้แพคเกจ powerbi-utils-testutils
* วิธีการตั้งค่าตัวอย่างทดสอบและการหลอกช่วยให้การทดสอบหน่วยสำหรับวิชวล Power BI ง่ายขึ้นI

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

* คุณมีโครงการวิชวล Power BI
* สภาพแวดล้อม Node.JS ที่กำหนดค่าไว้

## <a name="install-and-configure-karmajs-and-jasmine"></a>ติดตั้งและกำหนดค่า karma.js และ jasmine

เพิ่มไลบรารีที่จำเป็นลงใน package.json ที่ส่วน `devDependencies`:

```json
"@babel/polyfill": "^7.2.5",
"@types/d3": "5.5.0",
"@types/jasmine": "2.5.37",
"@types/jasmine-jquery": "1.5.28",
"@types/jquery": "2.0.41",
"@types/karma": "3.0.0",
"@types/lodash-es": "4.17.1",
"coveralls": "3.0.2",
"istanbul-instrumenter-loader": "^3.0.1",
"jasmine": "2.5.2",
"jasmine-core": "2.5.2",
"jasmine-jquery": "2.1.1",
"jquery": "3.1.1",
"karma": "3.1.1",
"karma-chrome-launcher": "2.2.0",
"karma-coverage": "1.1.2",
"karma-coverage-istanbul-reporter": "^2.0.4",
"karma-jasmine": "2.0.1",
"karma-junit-reporter": "^1.2.0",
"karma-sourcemap-loader": "^0.3.7",
"karma-typescript": "^3.0.13",
"karma-typescript-preprocessor": "0.4.0",
"karma-webpack": "3.0.5",
"puppeteer": "1.17.0",
"style-loader": "0.23.1",
"ts-loader": "5.3.0",
"ts-node": "7.0.1",
"tslint": "^5.12.0",
"webpack": "4.26.0"
```

ดูคำอธิบายด้านล่างเพื่อเรียนรู้เพิ่มเติมเกี่ยวกับแพคเกจ

บันทึก `package.json` และดำเนินการบนบรรทัดคำสั่งที่ตำแหน่งที่ตั้ง `package.json`:

```cmd
npm install
```

ตัวจัดการแพคเกจจะติดตั้งแพคเกจใหม่ทั้งหมดที่ถูกเพิ่มไปยัง `package.json`

สำหรับการรันการทดสอบหน่วย เราจำเป็นต้องกำหนดค่าโปรแกรมรันการทดสอบและ `webpack` config ตัวอย่างของ config ที่คุณสามารถค้นหาได้ที่นี่

ตัวอย่างของ `test.webpack.config.js`:

```typescript
const path = require('path');
const webpack = require("webpack");

module.exports = {
    devtool: 'source-map',
    mode: 'development',
    optimization : {
        concatenateModules: false,
        minimize: false
    },
    module: {
        rules: [
            {
                test: /\.tsx?$/,
                use: 'ts-loader',
                exclude: /node_modules/
            },
            {
                test: /\.json$/,
                loader: 'json-loader'
            },
            {
                test: /\.tsx?$/i,
                enforce: 'post',
                include: /(src)/,
                exclude: /(node_modules|resources\/js\/vendor)/,
                loader: 'istanbul-instrumenter-loader',
                options: { esModules: true }
            },
            {
                test: /\.less$/,
                use: [
                    {
                        loader: 'style-loader'
                    },
                    {
                        loader: 'css-loader'
                    },
                    {
                        loader: 'less-loader',
                        options: {
                            paths: [path.resolve(__dirname, 'node_modules')]
                        }
                    }
                ]
            }
        ]
    },
    externals: {
        "powerbi-visuals-api": '{}'
    },
    resolve: {
        extensions: ['.tsx', '.ts', '.js', '.css']
    },
    output: {
        path: path.resolve(__dirname, ".tmp/test")
    },
    plugins: [
        new webpack.ProvidePlugin({
            'powerbi-visuals-api': null
        })
    ]
};
```

ตัวอย่างของ `karma.conf.ts`

```typescript
"use strict";

const webpackConfig = require("./test.webpack.config.js");
const tsconfig = require("./test.tsconfig.json");
const path = require("path");

const testRecursivePath = "test/visualTest.ts";
const srcOriginalRecursivePath = "src/**/*.ts";
const coverageFolder = "coverage";

process.env.CHROME_BIN = require("puppeteer").executablePath();

import { Config, ConfigOptions } from "karma";

module.exports = (config: Config) => {
    config.set(<ConfigOptions>{
        mode: "development",
        browserNoActivityTimeout: 100000,
        browsers: ["ChromeHeadless"], // or Chrome to use locally installed Chrome browser
        colors: true,
        frameworks: ["jasmine"],
        reporters: [
            "progress",
            "junit",
            "coverage-istanbul"
        ],
        junitReporter: {
            outputDir: path.join(__dirname, coverageFolder),
            outputFile: "TESTS-report.xml",
            useBrowserName: false
        },
        singleRun: true,
        plugins: [
            "karma-coverage",
            "karma-typescript",
            "karma-webpack",
            "karma-jasmine",
            "karma-sourcemap-loader",
            "karma-chrome-launcher",
            "karma-junit-reporter",
            "karma-coverage-istanbul-reporter"
        ],
        files: [
            "node_modules/jquery/dist/jquery.min.js",
            "node_modules/jasmine-jquery/lib/jasmine-jquery.js",
            {
                pattern: './capabilities.json',
                watched: false,
                served: true,
                included: false
            },
            testRecursivePath,
            {
                pattern: srcOriginalRecursivePath,
                included: false,
                served: true
            }
        ],
        preprocessors: {
            [testRecursivePath]: ["webpack", "coverage"]
        },
        typescriptPreprocessor: {
            options: tsconfig.compilerOptions
        },
        coverageIstanbulReporter: {
            reports: ["html", "lcovonly", "text-summary", "cobertura"],
            dir: path.join(__dirname, coverageFolder),
            'report-config': {
                html: {
                    subdir: 'html-report'
                }
            },
            combineBrowserReports: true,
            fixWebpackSourcePaths: true,
            verbose: false
        },
        coverageReporter: {
            dir: path.join(__dirname, coverageFolder),
            reporters: [
                // reporters not supporting the `file` property
                { type: 'html', subdir: 'html-report' },
                { type: 'lcov', subdir: 'lcov' },
                // reporters supporting the `file` property, use `subdir` to directly
                // output them in the `dir` directory
                { type: 'cobertura', subdir: '.', file: 'cobertura-coverage.xml' },
                { type: 'lcovonly', subdir: '.', file: 'report-lcovonly.txt' },
                { type: 'text-summary', subdir: '.', file: 'text-summary.txt' },
            ]
        },
        mime: {
            "text/x-typescript": ["ts", "tsx"]
        },
        webpack: webpackConfig,
        webpackMiddleware: {
            stats: "errors-only"
        }
    });
};
```

คุณสามารถปรับเปลี่ยนการกำหนดค่านี้ได้ถ้าจำเป็น

การตั้งค่าบางอย่างของ `karma.conf.js`:

* `recursivePathToTests` ตัวแปรค้นหาตำแหน่งที่ตั้งของรหัสการทดสอบ

* `srcRecursivePath` ตัวแปรค้นหารหัส JS เอาท์พุทหลังจากการคอมไพล์

* `srcCssRecursivePath` ตัวแปรค้นหา CSS เอาท์พุทหลังจากการคอมไพล์ไฟล์น้อยลงด้วยสไตล์

* `srcOriginalRecursivePath` ตัวแปรค้นหารหัสต้นทางของวิชวล

* `coverageFolder` - ตัวแปรกำหนดสถานที่ที่จะสร้างรายงานความครอบคลุม

คุณสมบัติบางอย่างของ config:

* `singleRun: true` - การทดสอบทำงานบนระบบ CI และก็เพียงพอสำหรับครั้งเดียว
คุณสามารถเปลี่ยนแปลงเป็น `false` สำหรับการดีบักการทดสอบ Karma จะยังคงใช้งานเบราว์เซอร์และจะช่วยให้คุณสามารถใช้คอนโซลสำหรับการดีบัก

* `files: [...]` -ในอาร์เรย์นี้ คุณสามารถตั้งค่าไฟล์สำหรับการโหลดไปยังเบราว์เซอร์ได้
โดยทั่วไปแล้ว จะมีไฟล์ต้นฉบับ กรณีการทดสอบ, ไลบรารี (jasmine, test utils) คุณสามารถเพิ่มเพื่อแสดงรายการไฟล์อื่น ๆ ได้ถ้าคุณต้องการ

* `preprocessors` -ส่วนนี้ของ config ที่คุณกำหนดค่าการดำเนินการ ซึ่งดำเนินการก่อนการดำเนินการทดสอบหน่วย มี precompiling ของ typescript ไปยัง JS และจัดเตรียมไฟล์แมปแหล่งที่มาและสร้างรายงานความครอบคลุมของรหัส คุณสามารถปิดใช้งาน `coverage` สำหรับการดีบักการทดสอบ ความครอบคลุมจะสร้างรหัสเพิ่มเติมเพื่อตรวจสอบรหัสสำหรับความครอบคลุมการทดสอบและจะซับซ้อนการทดสอบการดีบัก

**คำอธิบายของการกำหนดค่าทั้งหมดที่คุณสามารถค้นหาใน [เอกสารประกอบ](https://karma-runner.github.io/1.0/config/configuration-file.html) ของ karma.js**

หากต้องการใช้งานที่สะดวก คุณสามารถเพิ่มคำสั่งทดสอบลงใน `scripts`:

```json
{
    "scripts": {
        "pbiviz": "pbiviz",
        "start": "pbiviz start",
        "typings":"node node_modules/typings/dist/bin.js i",
        "lint": "tslint -r \"node_modules/tslint-microsoft-contrib\"  \"+(src|test)/**/*.ts\"",
        "pretest": "pbiviz package --resources --no-minify --no-pbiviz --no-plugin",
        "test": "karma start"
    }
    ...
}
```

ดังนั้นคุณก็พร้อมที่จะเริ่มเขียนการทดสอบหน่วยของคุณ

## <a name="simple-unit-test-for-check-dom-element-of-the-visual"></a>การทดสอบหน่วยอย่างง่ายสำหรับการตรวจสอบองค์ประกอบ DOM ของวิชวล

สำหรับการทดสอบวิชวล เราต้องสร้างอินสแตนซ์ของวิชวล

### <a name="creating-visual-instance-builder"></a>การสร้างตัวสร้างอินสแตนซ์ของวิชวล

เพิ่มไฟล์ `visualBuilder.ts` ลงโฟลเดอร์ `test` ด้วยรหัสถัดไป:

```typescript
import {
    VisualBuilderBase
} from "powerbi-visuals-utils-testutils";

import {
    BarChart as VisualClass
} from "../src/visual";

import  powerbi from "powerbi-visuals-api";
import VisualConstructorOptions = powerbi.extensibility.visual.VisualConstructorOptions;

export class BarChartBuilder extends VisualBuilderBase<VisualClass> {
    constructor(width: number, height: number) {
        super(width, height);
    }

    protected build(options: VisualConstructorOptions) {
        return new VisualClass(options);
    }

    public get mainElement() {
        return this.element.children("svg.barChart");
    }
}
```

มี `build` เมธอดสำหรับการสร้างอินสแตนซ์ของวิชวลของคุณ `mainElement` เป็นเมธอดการรับซึ่งส่งกลับอินสแตนซ์ขององค์ประกอบ DOM "root" ในวิชวลของคุณ Getter เป็นตัวเลือกแต่จะทำให้การเขียนการทดสอบหน่วยง่ายขึ้น

ดังนั้นเราจึงมีตัวสร้างอินสแตนซ์ของวิชวล ลองเขียนกรณีทดสอบ ซึ่งจะเป็นกรณีทดสอบเพื่อตรวจสอบองค์ประกอบ SVG เหล่านั้นที่สร้างขึ้นเมื่อวิชวลของคุณแสดงผล

### <a name="creating-typescript-file-to-write-test-cases"></a>การสร้างไฟล์ typescript เพื่อเขียนกรณีทดสอบ

เพิ่มไฟล์ `visualTest.ts` สำหรับกรณีทดสอบด้วยรหัสเหล่านี้:

```typescript
import powerbi from "powerbi-visuals-api";

import { BarChartBuilder } from "./VisualBuilder";

import {
    BarChart as VisualClass
} from "../src/visual";

import VisualBuilder = powerbi.extensibility.visual.test.BarChartBuilder;

describe("BarChart", () => {
    let visualBuilder: VisualBuilder;
    let dataView: DataView;

    beforeEach(() => {
        visualBuilder = new VisualBuilder(500, 500);
    });

    it("root DOM element is created", () => {
        expect(visualBuilder.mainElement).toBeInDOM();
    });
});
```

มีการเรียกใช้หลายเมธอด

* [`describe`](https://jasmine.github.io/api/2.6/global.html#describe) เมธอดจะอธิบายกรณีทดสอบ ในบริบทของกรอบการทำงานของ jasmine มักเรียกว่าชุดหรือกลุ่มของข้อมูลจำเพาะ

* จะมีการเรียกใช้เมธอด `beforeEach` ก่อนการเรียกใช้แต่ละครั้งของ `it` เมธอดที่กำหนดไว้ภายในใน [`describe`](https://jasmine.github.io/api/2.6/global.html#beforeEach) เมธอด

* `it` กำหนดข้อมูลจำเพาะเดียว [`it`](https://jasmine.github.io/api/2.6/global.html#it) เมธอดต้องมีอย่างน้อยหนึ่งรายการหรือมากกว่า `expectations`

* [`expect`](https://jasmine.github.io/api/2.6/global.html#expect) - เมธอดจะสร้างความคาดหวังสำหรับข้อมูลจำเพาะ ข้อมูลจำเพาะจะเสร็จสมบูรณ์ถ้าเป็นไปตามความคาดหวังทั้งหมดโดยไม่มีความล้มเหลวใด ๆ

* `toBeInDOM` - เมธอดนี้เป็นหนึ่งในเมธอดของตัวจับคู่ เกี่ยวกับตัวจับคู่ที่มีอยู่ คุณสามารถอ่านใน[เอกสารประกอบของ](https://jasmine.github.io/api/2.6/matchers.html)กรอบการทำงานของ jasmine

**อ่านเพิ่มเติมเกี่ยวกับกรอบการทำงานของ jasmine ใน [เอกสารประกอบอย่างเป็นทางการ](https://jasmine.github.io/)**

หลังจากนั้น คุณสามารถเรียกใช้การทดสอบหน่วยโดยการพิมพ์คำสั่งในเครื่องมือบรรทัดคำสั่ง

การทดสอบนี้จะตรวจสอบว่าองค์ประกอบ SVG ระดับสูงของวิชวลถูกสร้างขึ้นหรือไม่

### <a name="launch-unit-tests"></a>เปิดใช้งานการทดสอบหน่วย

เมื่อต้องการเรียกใช้การทดสอบหน่วย คุณสามารถพิมพ์คำสั่งนี้ในเครื่องมือบรรทัดคำสั่ง

```cmd
npm run test
```

`karma.js` เรียกใช้เบราว์เซอร์ chrome และจะดำเนินการตามกรณีทดสอบ

![เปิดใช้งาน KarmaJS ใน Chrome](./media/karmajs-chrome.png)

> [!NOTE]
> ต้องติดตั้ง Google Chrome ภายในเครื่อง

ในบรรทัดคำสั่ง คุณจะได้รับผลลัพธ์ต่อไปนี้:

```cmd
> karma start

23 05 2017 12:24:26.842:WARN [watcher]: Pattern "E:/WORKSPACE/PowerBI/PowerBI-visuals-sampleBarChart/data/*.csv" does not match any file.
23 05 2017 12:24:30.836:WARN [karma]: No captured browser, open http://localhost:9876/
23 05 2017 12:24:30.849:INFO [karma]: Karma v1.3.0 server started at http://localhost:9876/
23 05 2017 12:24:30.850:INFO [launcher]: Launching browser Chrome with unlimited concurrency
23 05 2017 12:24:31.059:INFO [launcher]: Starting browser Chrome
23 05 2017 12:24:33.160:INFO [Chrome 58.0.3029 (Windows 10 0.0.0)]: Connected on socket /#2meR6hjXFmsE_fjiAAAA with id 5875251
Chrome 58.0.3029 (Windows 10 0.0.0): Executed 1 of 1 SUCCESS (0.194 secs / 0.011 secs)

=============================== Coverage summary ===============================
Statements   : 27.43% ( 65/237 )
Branches     : 19.84% ( 25/126 )
Functions    : 43.86% ( 25/57 )
Lines        : 20.85% ( 44/211 )
================================================================================
```

### <a name="how-to-add-static-data-for-unit-tests"></a>วิธีการเพิ่มข้อมูลแบบคงที่สำหรับการทดสอบหน่วย

สร้างไฟล์ `visualData.ts` ในโฟลเดอร์ `test` ด้วยรหัสเหล่านี้:

```typescript
import powerbi from "powerbi-visuals-api";
import DataView = powerbi.DataView;

import {
    testDataViewBuilder,
    getRandomNumbers
} from "powerbi-visuals-utils-testutils";

export class SampleBarChartDataBuilder extends TestDataViewBuilder {
    public static CategoryColumn: string = "category";
    public static MeasureColumn: string = "measure";

    public constructor() {
        super();
        ...
    }

    public getDataView(columnNames?: string[]): DataView {
        let dateView: any = this.createCategoricalDataViewBuilder([
            ...
        ],
        [
            ...
        ], columnNames).build();

        // there's client side computed maxValue
        let maxLocal = 0;
        this.valuesMeasure.forEach((item) => {
                if (item > maxLocal) {
                    maxLocal = item;
                }
        });
        (<any>dataView).categorical.values[0].maxLocal = maxLocal;
    }
}
```

คลาส`SampleBarChartDataBuilder` จะขยาย `TestDataViewBuilder` และใช้เมธอดที่เป็นนามธรรม`getDataView`

เมื่อคุณใส่ข้อมูลลงในบักเก็ตเขตข้อมูล Power BI สร้างวัตถุ `dataview` ตามประเภทที่ยึดตามข้อมูลของคุณ

![บักเก็ตเขตข้อมูล](./media/fields-buckets.png)

ในการทดสอบหน่วย คุณไม่มีฟังก์ชันหลักของ Power BI เพื่อที่จะทำซ้ำ แต่คุณจำเป็นต้องแมปข้อมูลแบบคงที่ของคุณไปยัง `dataview` ตามประเภท และคลาส `TestDataViewBuilder` จะช่วยเหลือคุณในนั้น

[อ่านเพิ่มเติมเกี่ยวกับ DataViewMapping](https://github.com/Microsoft/PowerBI-visuals/blob/master/Capabilities/DataViewMappings.md)

ในเมธอด `getDataView` คุณเพียงแค่เรียกใช้เมธอด `createCategoricalDataViewBuilder` ด้วยข้อมูลของคุณ

ใน `sampleBarChart` วิชวล [capabilities.json](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/master/capabilities.json#L2) คุณมีวัตถุ dataRoles และ dataViewMapping:

```json
"dataRoles": [
    {
        "displayName": "Category Data",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Measure Data",
        "name": "measure",
        "kind": "Measure"
    }
],
"dataViewMappings": [
    {
        "conditions": [
            {
                "category": {
                    "max": 1
                },
                "measure": {
                    "max": 1
                }
            }
        ],
        "categorical": {
            "categories": {
                "for": {
                    "in": "category"
                }
            },
            "values": {
                "select": [
                    {
                        "bind": {
                            "to": "measure"
                        }
                    }
                ]
            }
        }
    }
],
```

เมื่อต้องการสร้างการแมปเดียวกัน คุณจะต้องตั้งค่าพารามิเตอร์ต่อไปนี้เป็นเมธอด `createCategoricalDataViewBuilder`:

```typescript
([
    {
        source: {
            displayName: "Category",
            queryName: SampleBarChartData.ColumnCategory,
            type: ValueType.fromDescriptor({ text: true }),
            roles: {
                Category: true
            },
        },
        values: this.valuesCategory
    }
],
[
    {
        source: {
            displayName: "Measure",
            isMeasure: true,
            queryName: SampleBarChartData.MeasureColumn,
            type: ValueType.fromDescriptor({ numeric: true }),
            roles: {
                Measure: true
            },
        },
        values: this.valuesMeasure
    },
], columnNames)
```

ที่`this.valuesCategory`อาร์เรย์ของประเภท

```ts
public valuesCategory: string[] = ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"];
```

และอาร์เรย์ `this.valuesMeasure`ของหน่วยวัดสำหรับแต่ละประเภท ตัวอย่าง:

```ts
public valuesMeasure: number[] = [742731.43, 162066.43, 283085.78, 300263.49, 376074.57, 814724.34, 570921.34];
```

ตอนนี้ คุณสามารถใช้คลาส `SampleBarChartDataBuilder` ในการทดสอบหน่วยของคุณ

กำหนดคลาส `ValueType` ในแพคเกจ `powerbi-visuals-utils-testutils` แล้ว และเมธอด `createCategoricalDataViewBuilder` จำเป็นต้องมีไลบรารี `lodash`

เพิ่มแพคเกจเหล่านี้ในการขึ้นต่อกัน

ใน `package.json` ที่ส่วน `devDependencies`

```json
"lodash-es": "4.17.1",
"powerbi-visuals-utils-testutils": "2.2.0"
```

เรียกใช้

```cmd
npm install
```

เพื่อติดตั้งไลบรารี `lodash-es`

ในตอนนี้ คุณสามารถเรียกใช้การทดสอบหน่วยอีกครั้ง คุณต้องได้รับผลลัพธ์นี้

```cmd
> karma start

23 05 2017 16:19:54.318:WARN [watcher]: Pattern "E:/WORKSPACE/PowerBI/PowerBI-visuals-sampleBarChart/data/*.csv" does not match any file.
23 05 2017 16:19:58.333:WARN [karma]: No captured browser, open http://localhost:9876/
23 05 2017 16:19:58.346:INFO [karma]: Karma v1.3.0 server started at http://localhost:9876/
23 05 2017 16:19:58.346:INFO [launcher]: Launching browser Chrome with unlimited concurrency
23 05 2017 16:19:58.394:INFO [launcher]: Starting browser Chrome
23 05 2017 16:19:59.873:INFO [Chrome 58.0.3029 (Windows 10 0.0.0)]: Connected on socket /#NcNTAGH9hWfGMCuEAAAA with id 3551106
Chrome 58.0.3029 (Windows 10 0.0.0): Executed 1 of 1 SUCCESS (1.266 secs / 1.052 secs)

=============================== Coverage summary ===============================
Statements   : 56.72% ( 135/238 )
Branches     : 32.54% ( 41/126 )
Functions    : 66.67% ( 38/57 )
Lines        : 52.83% ( 112/212 )
================================================================================
```

และคุณต้องดูการเริ่มต้นใช้งานเบราว์เซอร์ Chrome ด้วยวิชวลของคุณ

![UT จะเปิดใช้งานใน Chrome](./media/karmajs-chrome-ut-runned.png)

ใส่ใจกับการสรุปความครอบคลุมเพิ่มขึ้น เปิด `coverage\index.html` เพื่อเรียนรู้เพิ่มเติมเกี่ยวกับความครอบคลุมของรหัสปัจจุบัน

![ดัชนีความครอบคลุมของ UT](./media/code-coverage-index.png)

หรือในขอบเขต`src`ของโฟลเดอร์

![ความครอบคลุมของโฟลเดอร์ src](./media/code-coverage-src-folder.png)

ในขอบเขตของไฟล์ คุณสามารถดูที่รหัสต้นทาง `Coverage` utils จะทำเครื่องหมายพื้นหลังของแถวเป็นสีแดงถ้าไม่มีการใช้งานรหัสในระหว่างการดำเนินการทดสอบหน่วย

![ความครอบคลุมของรหัสของไฟล์ visual.ts](./media/code-coverage-visual-src.png)

> [!IMPORTANT]
> แต่ความครอบคลุมของรหัสไม่ได้หมายความว่าคุณมีความครอบคลุมของวิชวลที่มีประสิทธิภาพ หนึ่งการทดสอบหน่วยอย่างง่ายที่กำหนดไว้มากกว่า 96 % ของความครอบคลุมใน `src\visual.ts`

## <a name="next-steps"></a>ขั้นตอนถัดไป

เมื่อวิชวลของคุณพร้อมแล้ว คุณสามารถส่งวิชวลไปยังการเผยแพร่ได้

[อ่านเพิ่มเติมเกี่ยวกับการเผยแพร่วิชวลไปยัง AppSource](../office-store.md)

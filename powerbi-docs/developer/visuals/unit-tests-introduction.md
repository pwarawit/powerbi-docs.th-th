---
title: ความรู้เบื้องต้นเกี่ยวกับการทดสอบหน่วยสำหรับโครงการวิชวล Power BI
description: บทความนี้อธิบายวิธีเขียนการทดสอบการทดสอบหน่วยสำหรับโครงการวิชวล Power BI
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 06/18/2019
ms.openlocfilehash: f0040ef53fbbce8c7133e5f645bcbddb0bbfadea
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/03/2019
ms.locfileid: "70236721"
---
# <a name="tutorial-add-unit-tests-for-power-bi-visual-projects"></a>บทช่วยสอน: เพิ่มการทดสอบหน่วยสำหรับโครงการวิชวล Power BI

บทความนี้อธิบายพื้นฐานของการเขียนการทดสอบหน่วยสำหรับโครงการวิชวล Power BI ของคุณ รวมถึงวิธีการ:

* ตั้งค่าเฟรมเวิร์กการทดสอบสำหรับตัวเรียกใช้การทดสอบ Karma JavaScript และ Jasmine
* ใช้แพคเกจ powerbi-visuals-utils-testutils
* ใช้ตัวอย่างทดสอบและการหลอกเพื่อช่วยให้การทดสอบหน่วยสำหรับวิชวล Power BI ทำได้ง่ายขึ้นI

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

* โครงการวิชวล Power BI ที่ติดตั้งแล้ว
* สภาพแวดล้อม Node.JS ที่กำหนดค่าไว้แล้ว

## <a name="install-and-configure-the-karma-javascript-test-runner-and-jasmine"></a>ติดตั้งและกำหนดค่าตัวเรียกใช้การทดสอบ Karma JavaScript และ Jasmine

เพิ่มไลบรารีที่จำเป็นเข้ากับไฟล์ *package.json* ในส่วน `devDependencies`:

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

ดูหากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับแพคเกจ ให้ดูคำอธิบายที่

บันทึกไฟล์ *package.json* และที่ตำแหน่ง `package.json` ให้เรียกใช้คำสั่งต่อไปนี้:

```cmd
npm install
```

ตัวจัดการแพกเกจติดตั้งแพกเกจใหม่ทั้งหมดที่เพิ่มไปยัง *package.json*

เมื่อต้องการเรียกใช้การทดสอบหน่วย ให้กำหนดค่าตัวเรียกใช้การทดสอบและการกำหนดค่า `webpack`

โค้ดต่อไปนี้เป็นตัวอย่างของไฟล์ *test.webpack.config.js*:

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

โค้ดต่อไปนี้เป็นตัวอย่างของไฟล์ *karma.conf.ts*:

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

ถ้าจำเป็น คุณสามารถปรับเปลี่ยนการกำหนดค่านี้ได้

โค้ดใน *karma.conf.js* ประกอบด้วยตัวแปรดังต่อไปนี้:

* `recursivePathToTests`: ค้นหาตำแหน่งโค้ดทดสอบ

* `srcRecursivePath`: ค้นหาตำแหน่งโค้ด JavaScript ผลลัพธ์หลังจากการคอมไพล์

* `srcCssRecursivePath`: ค้นหาตำแหน่ง CSS ผลลัพธ์หลังจากการคอมไพล์ไฟล์น้อยลงด้วยสไตล์

* `srcOriginalRecursivePath`: ค้นหาตำแหน่งซอสโค้ดของวิชวลของคุณ

* `coverageFolder`: กำหนดตำแหน่งที่จะสร้างรายงานความครอบคลุม

ไฟล์การกำหนดค่าประกอบด้วยคุณสมบัติต่อไปนี้:

* `singleRun: true`: มีการเรียกใช้การทดสอบบนระบบการบูรณาการอย่างต่อเนื่อง (CI) หรือสามารถเรียกใช้ได้ครั้งเดียว คุณสามารถเปลี่ยนการตั้งค่าเป็น *false* สำหรับการดีบักการทดสอบของคุณ Karma ช่วยให้เบราว์เซอร์ทำงานอย่างต่อเนื่องเพื่อให้คุณสามารถใช้คอนโซลสำหรับการดีบักได้

* `files: [...]`: ในอาร์เรย์นี้ คุณสามารถระบุไฟล์ที่จะโหลดไปยังเบราว์เซอร์ได้ โดยทั่วไปแล้วจะมีไฟล์ต้นฉบับ กรณีการทดสอบ ไลบรารี (Jasmine, ยูทิลิตี้การทดสอบ) คุณสามารถเพิ่มไฟล์เพิ่มเติมลงในรายการได้ตามความจำเป็น

* `preprocessors`: ในส่วนนี้คุณกำหนดค่าการดำเนินการที่เรียกใช้ก่อนที่จะเรียกใช้การทดสอบหน่วย พวกเขาทำการพรีคอมไพล์ typescript ไปยัง JavaScript เตรียมไฟล์แมปต้นฉบับ และสร้างรายงานความครอบคลุมของโค้ด คุณสามารถปิดใช้งาน `coverage` เมื่อคุณดีบักการทดสอบของคุณ ความครอบคลุมจะสร้างโค้ดเพิ่มเติมเพื่อตรวจสอบโค้ดสำหรับความครอบคลุมในการทดสอบ ซึ่งจะทำให้การทดสอบการดีบักซับซ้อน

สำหรับคำอธิบายของการกำหนดค่า Karma ทั้งหมดให้ไปที่หน้า[ไฟล์การกำหนดค่า Karma](https://karma-runner.github.io/1.0/config/configuration-file.html)

เพื่อความสะดวกของคุณ คุณสามารถเพิ่มคำสั่งทดสอบลงใน `scripts`:

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

ดังนั้น ตอนนี้คุณก็พร้อมที่จะเริ่มเขียนการทดสอบหน่วยของคุณแล้ว

## <a name="check-the-dom-element-of-the-visual"></a>ตรวจสอบองค์ประกอบ DOM ของวิชวล

สำหรับการทดสอบวิชวล เราต้องสร้างอินสแตนซ์ของวิชวลก่อน

### <a name="create-a-visual-instance-builder"></a>สร้างตัวสร้างอินสแตนซ์ของวิชวล

เพิ่มไฟล์ *visualBuilder.ts* ไปยังโฟลเดอร์ *test* โดยใช้โค้ดดังต่อไปนี้:

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

มี `build` เมธอดสำหรับการสร้างอินสแตนซ์ของวิชวลของคุณ `mainElement` เป็นเมธอดการรับ ซึ่งส่งกลับอินสแตนซ์ขององค์ประกอบแบบจำลองอ็อบเจกต์เอกสาร (DOM) "root" ในวิชวลของคุณ Getter เป็นตัวเลือกที่จะใช้หรือไม่ใช้ก็ได้ แต่จะทำให้การเขียนการทดสอบหน่วยง่ายขึ้น

ขณะนี้คุณมีการสร้างอินสแตนซ์ของวิชวลของคุณแล้ว ลองเขียนกรณีทดสอบ กรณีทดสอบจะตรวจสอบองค์ประกอบ SVG ที่สร้างขึ้นเมื่อแสดงวิชวลของคุณ

### <a name="create-a-typescript-file-to-write-test-cases"></a>สร้างไฟล์ typescript เพื่อเขียนกรณีทดสอบ

เพิ่มไฟล์ *visualTest.ts* สำหรับกรณีทดสอบโดยใช้โค้ดดังต่อไปนี้:

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

มีการเรียกใช้เมธอดหลายวิธี:

* [`describe`](https://jasmine.github.io/api/2.6/global.html#describe): อธิบายกรณีทดสอบ ในบริบทของเฟรมเวิร์ก Jasmine ซึ่งมักจะอธิบายชุดหรือกลุ่มของรายละเอียดจำเพาะ

* `beforeEach`: ถูกเรียกก่อนการเรียกใช้เมธอด `it` แต่ละครั้งซึ่งกำหนดไว้ในเมธอด [`describe`](https://jasmine.github.io/api/2.6/global.html#beforeEach)

* [`it`](https://jasmine.github.io/api/2.6/global.html#it): กำหนดรายละเอียดจำเพาะเดียว เมธอด `it` ควรมี `expectations` อย่างน้อยหนึ่งรายการหรือมากกว่า

* [`expect`](https://jasmine.github.io/api/2.6/global.html#expect): สร้างความคาดหวังสำหรับรายละเอียดจำเพาะ รายละเอียดจำเพาะะเสร็จสมบูรณ์ถ้าเป็นไปตามความคาดหวังทั้งหมดโดยไม่มีความล้มเหลวใดเกิดขึ้น

* `toBeInDOM`: หนึ่งในเมธอด *matchers* สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ matchers โปรดดู [Jasmine Namespace: matchers](https://jasmine.github.io/api/2.6/matchers.html)

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ Jasmine โปรดดูที่หน้า [เอกสารประกอบสำหรับเฟรมเวิร์ก Jasmine](https://jasmine.github.io/)

### <a name="launch-unit-tests"></a>เปิดใช้งานการทดสอบหน่วย

การทดสอบนี้จะตรวจสอบว่าองค์ประกอบ SVG ระดับสูงของวิชวลถูกสร้างขึ้นหรือไม่ เมื่อต้องการเรียกใช้การทดสอบหน่วย ให้ป้อนคำสั่งนี้ในเครื่องมือประเภทคอมมานด์ไลน์:

```cmd
npm run test
```

`karma.js` เรียกใช้กรณีทดสอบในเบราว์เซอร์ Chrome

![Karma JavaScript เปิดใน Chrome แล้ว](./media/karmajs-chrome.png)

> [!NOTE]
> คุณต้องติดตั้ง Google Chrome ภายในเครื่อง

ในหน้าต่างคอมมานด์ไลน์ (Command Line) คุณจะได้รับผลลัพธ์ต่อไปนี้:

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

สร้างไฟล์ *visualData.ts* ไปยังโฟลเดอร์ *test* โดยใช้โค้ดดังต่อไปนี้:

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

คลาส `SampleBarChartDataBuilder` จะขยาย `TestDataViewBuilder` และใช้เมธอดที่อยู่ในคลาสนามธรรม `getDataView`

เมื่อคุณใส่ข้อมูลลงในบักเก็ตเขตข้อมูล Power BI สร้างออบเจ็กต์ `dataview` แบบจัดกลุ่มที่ขึ้นอยู่กับข้อมูลของคุณ

![บักเก็ตเขตข้อมูล](./media/fields-buckets.png)

ในการทดสอบหน่วย คุณไม่มีฟังก์ชันหลักของ Power BI เพื่อที่จะทำซ้ำข้อมูล แต่คุณจำเป็นต้องแมปข้อมูลแบบสแตติกของคุณไปยัง `dataview` แบบจัดกลุ่ม คลาส `TestDataViewBuilder` สามารถช่วยคุณในการแมปได้

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการแมปมุมมองข้อมูล โปรดดูที่ [DataViewMappings](https://github.com/Microsoft/PowerBI-visuals/blob/master/Capabilities/DataViewMappings.md)

ในเมธอด `getDataView` ให้คุณเรียกใช้เมธอด `createCategoricalDataViewBuilder` ด้วยข้อมูลของคุณ

ในไฟล์ [capabilities.json](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/master/capabilities.json#L2) ของวิชวล `sampleBarChart` คุณมีออบเจ็กต์ dataRoles และ dataViewMapping:

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

โดยที่ `this.valuesCategory` เป็นอาร์เรย์ของหมวดหมู่:

```ts
public valuesCategory: string[] = ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"];
```

และ `this.valuesMeasure` เป็นอาร์เรย์ของหน่วยวัดสำหรับแต่ละหมวดหมู่:

```ts
public valuesMeasure: number[] = [742731.43, 162066.43, 283085.78, 300263.49, 376074.57, 814724.34, 570921.34];
```

ตอนนี้ คุณสามารถใช้คลาส `SampleBarChartDataBuilder` ในการทดสอบหน่วยของคุณได้แล้ว

คลาส `ValueType` จะถูกกำหนดไว้ในแพกเกจ powerbi-visuals-utils-testutils และเมธอด `createCategoricalDataViewBuilder` จำเป็นต้องมีไลบรารี `lodash`

เพิ่มแพคเกจเหล่านี้ไปยังการขึ้นต่อกัน (dependencies)

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

ในตอนนี้ คุณสามารถเรียกใช้การทดสอบหน่วยอีกครั้ง คุณต้องได้รับผลลัพธ์ต่อไปนี้:

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

วิชวลของคุณจะเปิดขึ้นในเบราว์เซอร์ Chrome ดังที่แสดง:

![UT จะเปิดใช้งานใน Chrome](./media/karmajs-chrome-ut-runned.png)

รายงานสรุปแสดงให้เห็นว่าความครอบคลุมได้เพิ่มขึ้น หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับความครอบคลุมของโค้ดในปัจจุบัน ให้เปิด `coverage\index.html`

![ดัชนีความครอบคลุมของ UT](./media/code-coverage-index.png)

หรือดูที่ขอบเขตของโฟลเดอร์ `src`:

![ความครอบคลุมของโฟลเดอร์ src](./media/code-coverage-src-folder.png)

ในขอบเขตของไฟล์ คุณสามารถดูที่ซอสโค้ดได้ ยูทิลิตี้ `Coverage` จะเน้นแถวเป็นสีแดงหากไม่ได้ดำเนินการโค้ดบางอย่างในระหว่างการทดสอบหน่วย

![ความครอบคลุมของโค้ดในไฟล์ visual.ts](./media/code-coverage-visual-src.png)

> [!IMPORTANT]
> การครอบคลุมโค้ดไม่ได้หมายความว่าคุณมีค่าความครอบคลุมฟังก์ชันการทำงานของวิชวลที่มีประสิทธิภาพ การทดสอบหน่วยอย่างหนึ่งครั้งให้ความครอบคลุมมากกว่า 96 เปอร์เซ็นต์ใน `src\visual.ts`

## <a name="next-steps"></a>ขั้นตอนถัดไป

เมื่อวิชวลของคุณพร้อมแล้ว คุณสามารถส่งวิชวลสำหรับการเผยแพร่ได้ สำหรับข้อมูลเพิ่มเติม โปรดดู[เผยแพร่วิชวลแบบกำหนดเองลงใน AppSource](../office-store.md)

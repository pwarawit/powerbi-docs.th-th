---
title: บทนำสู่การใช้ Utils การทดสอบในวิชวล Power BI
description: บทความนี้อธิบายวิธีการใช้ Utils การทดสอบทำให้การทดสอบง่ายขึ้นและการใช้วิธีเฉพาะในการทดสอบหน่วยสำหรับวิชวล Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 02/14/2020
ms.openlocfilehash: c50ad894b2e1f5eb838abdd4442f473f8bcbbb10
ms.sourcegitcommit: 1059c6222458f189fb5301dcb689dad2b2c00bc1
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/28/2020
ms.locfileid: "82196617"
---
# <a name="power-bi-visuals-test-utils"></a>Utils การทดสอบวิชวล Power BI

บทความนี้จะช่วยคุณในการติดตั้ง นำเข้า และใช้ Utils การทดสอบวิชวล Power BI ยูทิลิตี้ทดสอบเหล่านี้สามารถใช้สำหรับการทดสอบหน่วย และรวม การทดสอบและวิธีการสำหรับองค์ประกอบต่าง ๆ เช่น มุมมองข้อมูล การเลือก และแบบแผนสี

## <a name="requirements"></a>ข้อกำหนด

หากต้องการใช้แพคเกจนี้ คุณจะต้องทำการติดตั้งต่อไปนี้:

* [node.js](https://nodejs.org) ขอแนะนำให้ใช้เวอร์ชัน LTS
* [npm](https://www.npmjs.com/) เวอร์ชัน 3.0.0 หรือสูงกว่า
* แพคเกจ [PowerBI-visuals-tools](https://github.com/Microsoft/PowerBI-visuals-tools)

## <a name="installation"></a>การติดตั้ง

หากต้องการติดตั้ง Utils การทดสอบและเพิ่มการขึ้นต่อกันของแพคเกจ *package.json* ให้เรียกใช้คำสั่งต่อไปนี้จากไดเรกทอรีวิชวล Power BI ของคุณ:

```bash
npm install powerbi-visuals-utils-testutils --save
```

ต่อไปนี้จะให้คำอธิบายและตัวอย่างเกี่ยวกับ API สาธารณะของ Utils การทดสอบ

## <a name="visualbuilderbase"></a>VisualBuilderBase

ใช้โดย **VisualBuilder** ในหน่วยการทดสอบด้วยวิธีการที่ใช้บ่อยที่สุด `build`, `update` และ `updateRenderTimeout` 

วิธีการ `build` จะแสดงอินสแตนซ์ที่สร้างขึ้นของวิชวล

จำเป็นต้องมีวิธีการ `enumerateObjectInstances` และ `updateEnumerateObjectInstancesRenderTimeout` ในการตรวจสอบการเปลี่ยนแปลงบนตัวเลือกการจัดรูปแบบและบักเก็ต

```typescript
abstract class VisualBuilderBase<T extends IVisual> {
    element: JQuery;
    viewport: IViewport;
    visualHost: IVisualHost;
    protected visual: T;
    constructor(width?: number, height?: number, guid?: string, element?: JQuery);
    protected abstract build(options: VisualConstructorOptions): T;
     nit(): void;
    destroy(): void;
    update(dataView: DataView[] | DataView): void;
    updateRenderTimeout(dataViews: DataView[] | DataView, fn: Function, timeout?: number): number;
    updateEnumerateObjectInstancesRenderTimeout(dataViews: DataView[] | DataView, options: EnumerateVisualObjectInstancesOptions, fn: (enumeration: VisualObjectInstance[]) => void, timeout?: number): number;
    updateFlushAllD3Transitions(dataViews: DataView[] | DataView): void;
    updateflushAllD3TransitionsRenderTimeout(dataViews: DataView[] | DataView, fn: Function, timeout?: number): number;
    enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstance[];
}
```

> [!NOTE]
> สำหรับตัวอย่างเพิ่มเติม ให้ดู [การเขียนการทดสอบหน่วย VisualBuilderBase](./unit-tests-introduction.md#create-a-visual-instance-builder) และ[สถานการณ์สมมติ VisualBuilderBase ในการใช้งานจริง](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/test/visualBuilder.ts)

## <a name="dataviewbuilder"></a>DataViewBuilder

ใช้โดย **TestDataViewBuilder**โมดูลนี้แสดงคลาส **CategoricalDataViewBuilder** ที่ใช้ในวิธีการ `createCategoricalDataViewBuilder` นอกจากนี้ยังระบุอินเทอร์เฟซและวิธีการที่จำเป็นสำหรับการทำงานกับ**DataView**ที่ทดสอบแล้วในหน่วยการทดสอบ

* `withValues` เพิ่มคอลัมน์ชุดข้อมูลคงที่และ `withGroupedValues` เพิ่มคอลัมน์ชุดข้อมูลแบบไดนามิก

  ไม่ต้องใช้ทั้งชุดข้อมูลแบบไดนามิกและชุดข้อมูลแบบคงที่ในวิชวล **DataViewCategorical** คุณสามารถใช้ได้ทั้งสองอย่างในคิวรี **DataViewCategorical** ซึ่ง **DataViewTransform**  ถูกคาดหวังว่าจะแยกออกเป็นวัตถุ **DataViewCategorical** ของวิชวลที่แยกต่างหาก

* `build` แสดง DataView พร้อมด้วยเมตาดาต้าและ DataViewCategorical

  `build` แสดง **ที่ไม่ได้กำหนดไว้**ถ้าการรวมของพารามิเตอร์ไม่ถูกต้องเช่น รวมทั้งชุดข้อมูลแบบไดนามิกและคงที่เมื่อสร้าง **DataView** ของวิชวล

```typescript
class CategoricalDataViewBuilder implements IDataViewBuilderCategorical {
    withCategory(options: DataViewBuilderCategoryColumnOptions): IDataViewBuilderCategorical;
    withCategories(categories: DataViewCategoryColumn[]): IDataViewBuilderCategorical;
    withValues(options: DataViewBuilderValuesOptions): IDataViewBuilderCategorical;
    withGroupedValues(options: DataViewBuilderGroupedValuesOptions): IDataViewBuilderCategorical;
    build(): DataView;
}

function createCategoricalDataViewBuilder(): IDataViewBuilderCategorical;
```

## <a name="testdataviewbuilder"></a>TestDataViewBuilder

ใช้สำหรับการสร้าง **VisualData** ในการทดสอบหน่วย เมื่อข้อมูลถูกใส่เข้าไปในบักเก็ตเขตข้อมูล Power BI จะสร้างวัตถุ **DataView** ตามประเภทที่ยึดตามข้อมูล **TestDataViewBuilder** ช่วยจำลองการสร้าง **DataView**ตามประเภท

```typescript
abstract class TestDataViewBuilder {
    static DataViewName: string;
    private aggregateFunction;
    static setDefaultQueryName(source: DataViewMetadataColumn): DataViewMetadataColumn;
    static getDataViewBuilderColumnIdentitySources(options: TestDataViewBuilderColumnOptions[] | TestDataViewBuilderColumnOptions): DataViewBuilderColumnIdentitySource[];
    static getValuesTable(categories?: DataViewCategoryColumn[], values?: DataViewValueColumn[]): any[][];
    static createDataViewBuilderColumnOptions(categoriesColumns: (TestDataViewBuilderCategoryColumnOptions | TestDataViewBuilderCategoryColumnOptions[])[], valuesColumns: (DataViewBuilderValuesColumnOptions | DataViewBuilderValuesColumnOptions[])[], filter?: (options: TestDataViewBuilderColumnOptions) => boolean, customizeColumns?: CustomizeColumnFn): DataViewBuilderAllColumnOptions;
    static setUpDataViewBuilderColumnOptions(options: DataViewBuilderAllColumnOptions, aggregateFunction: (array: number[]) => number): DataViewBuilderAllColumnOptions;
    static setUpDataView(dataView: DataView, options: DataViewBuilderAllColumnOptions): DataView;
    protected createCategoricalDataViewBuilder(categoriesColumns: (TestDataViewBuilderCategoryColumnOptions | TestDataViewBuilderCategoryColumnOptions[])[], valuesColumns: (DataViewBuilderValuesColumnOptions | DataViewBuilderValuesColumnOptions[])[], columnNames: string[], customizeColumns?: CustomizeColumnFn): IDataViewBuilderCategorical;
    abstract getDataView(columnNames?: string[]): DataView;
}
```

  ต่อไปนี้เป็นรายการอินเทอร์เฟซที่ใช้บ่อยที่สุดเมื่อสร้าง `testDataView`:

  ```typescript
  interface TestDataViewBuilderColumnOptions extends DataViewBuilderColumnOptions {
      values: any[];
  }

  interface TestDataViewBuilderCategoryColumnOptions extends TestDataViewBuilderColumnOptions {
      objects?: DataViewObjects[];
      isGroup?: boolean;
  }

  interface DataViewBuilderColumnOptions {
      source: DataViewMetadataColumn;
  }

  interface DataViewBuilderSeriesData {
      values: PrimitiveValue[];
      highlights?: PrimitiveValue[];
      /** Client-computed maximum value for a column. */
      maxLocal?: any;
      /** Client-computed maximum value for a column. */
      minLocal?: any;
  }

  interface DataViewBuilderColumnIdentitySource {
      fields: any[];
      identities?: CustomVisualOpaqueIdentity[];
  }
  ```
   
> [!NOTE]
> สำหรับตัวอย่างเพิ่มเติม ให้ดู [การเขียนการทดสอบหน่วย TestDataViewBuilder ](./unit-tests-introduction.md#how-to-add-static-data-for-unit-tests) และ[สถานการณ์สมมติ TestDataViewBuilder ในการใช้งานจริง](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/test/visualData.ts)

## <a name="mocks"></a>การทดสอบ

### <a name="mockivisualhost"></a>MockIVisualHost

ใช้ **IVisualHost** เพื่อทดสอบวิชวล Power BI โดยไม่มีการขึ้นต่อกันภายนอกเช่น เฟรมเวิร์ก Power BI

วิธีการที่เป็นประโยชน์ประกอบด้วย `createSelectionIdBuilder`, `createSelectionManager`, `createLocalizationManager` และคุณสมบัติ Getter

```typescript
import powerbi from "powerbi-visuals-api";

import VisualObjectInstancesToPersist = powerbi.VisualObjectInstancesToPersist;
import ISelectionIdBuilder = powerbi.visuals.ISelectionIdBuilder;
import ISelectionManager = powerbi.extensibility.ISelectionManager;
import IColorPalette = powerbi.extensibility.IColorPalette;
import IVisualEventService = powerbi.extensibility.IVisualEventService;
import ITooltipService = powerbi.extensibility.ITooltipService;
import IVisualHost = powerbi.extensibility.visual.IVisualHost;

class MockIVisualHost implements IVisualHost {
      constructor(
          colorPalette?: IColorPalette,
          selectionManager?: ISelectionManager,
          tooltipServiceInstance?: ITooltipService,
          localeInstance?: MockILocale,
          allowInteractionsInstance?: MockIAllowInteractions,
          localizationManager?: powerbi.extensibility.ILocalizationManager,
          telemetryService?: powerbi.extensibility.ITelemetryService,
          authService?: powerbi.extensibility.IAuthenticationService,
          storageService?: ILocalVisualStorageService,
          eventService?: IVisualEventService);
      createSelectionIdBuilder(): ISelectionIdBuilder;
      createSelectionManager(): ISelectionManager;
      createLocalizationManager(): ILocalizationManager;
      colorPalette: IColorPalette;
      locale: string;
      telemetry: ITelemetryService;
      tooltipService: ITooltipService;
      allowInteractios: boolean;
      storageService: ILocalVisualStorageService;
      eventService: IVisualEventService;
      persistProperties(changes: VisualObjectInstancesToPersist): void;
}
```
   
- `createVisualHost` สร้างและแสดงอินสแตนซ์ของ **IVisualHost** จริง ๆ แล้วคือ **MockIVisualHost**
  ```typescript
  function createVisualHost(locale?: Object, allowInteractions?: boolean, colors?: IColorInfo[], isEnabled?: boolean, displayNames?: any, token?: string): IVisualHost;
  ```

    ตัวอย่าง:
    ```typescript
    import { createVisualHost } from "powerbi-visuals-utils-testutils"

    let host: IVisualHost = createVisualHost();
    ```

> [!IMPORTANT]
> **MockIVisualHost** เป็นการดำเนินการหลอกของ **IVisualHost** และควรใช้กับหน่วยการทดสอบเท่านั้น

### <a name="mockicolorpalette"></a>MockIColorPalette

ใช้ **IColorPalette** เพื่อทดสอบวิชวล Power BI โดยไม่มีการขึ้นต่อกันภายนอกเช่น เฟรมเวิร์ก Power BI

**MockIColorPalette** มีคุณสมบัติที่เป็นประโยชน์สำหรับการตรวจสอบแบบแผนสี หรือโหมดความคมชัดสูงในการทดสอบหน่วย

  ```typescript
  import powerbi from "powerbi-visuals-api";
  import IColorPalette = powerbi.extensibility.ISandboxExtendedColorPalette;
  import IColorInfo = powerbi.IColorInfo;

  class MockIColorPalette implements IColorPalette {
      constructor(colors?: IColorInfo[]);
      getColor(key: string): IColorInfo;
      reset(): IColorPalette;
      isHighContrastMode: boolean;
      foreground: {value: string};
      foregroundLight: {value: string};
      ...
      background: {value: string};
      backgroundLight: {value: string};
      ...
      shapeStroke: {value: string};
  }
  ```
  - `createColorPalette` สร้างและแสดงอินสแตนซ์ของ **IColorPalette** จริง ๆ แล้วคือ **MockIColorPalette**
    ```typescript
    function createColorPalette(colors?: IColorInfo[]): IColorPalette;
    ```

    ตัวอย่าง:
    ```typescript
    import { createColorPalette } from "powerbi-visuals-utils-testutils"

    let colorPalette: IColorPalette = createColorPalette();
    ```
    
> [!IMPORTANT]
> **MockIColorPalette** เป็นการดำเนินการหลอกของ  **IColorPalette** และควรใช้กับหน่วยการทดสอบเท่านั้น

### <a name="mockiselectionid"></a>MockISelectionId

ใช้ **ISelectionId** เพื่อทดสอบวิชวล Power BI โดยไม่มีการขึ้นต่อกันภายนอกเช่น เฟรมเวิร์ก Power BI

  ```typescript
  import powerbi from "powerbi-visuals-api";
  import Selector = powerbi.data.Selector;
  import ISelectionId = powerbi.visuals.ISelectionId;

  class MockISelectionId implements ISelectionId {
      constructor(key: string);
      equals(other: ISelectionId): boolean;
      includes(other: ISelectionId, ignoreHighlight?: boolean): boolean;
      getKey(): string;
      getSelector(): Selector;
      getSelectorsByColumn(): Selector;
      hasIdentity(): boolean;
  }
  ```

  - `createSelectionId` สร้างและแสดงอินสแตนซ์ของ **ISelectionId** จริง ๆ แล้วคือ **MockISelectionId**
    ```typescript
    function createSelectionId(key?: string): ISelectionId;
    ```

    ตัวอย่าง:
    ```typescript
    import { createColorPalette } from "powerbi-visuals-utils-testutils"

    let selectionId: ISelectionId = createSelectionId();
    ```
    
> [!NOTE]
> **MockISelectionId** เป็นการดำเนินการหลอกของ  **ISelectionId** และควรใช้กับหน่วยการทดสอบเท่านั้น

### <a name="mockiselectionidbuilder"></a>MockISelectionIdBuilder

ใช้ **ISelectionIdBuilder** เพื่อทดสอบวิชวล Power BI โดยไม่มีการขึ้นต่อกันภายนอกเช่น เฟรมเวิร์ก Power BI 

  ```typescript
  import DataViewCategoryColumn = powerbi.DataViewCategoryColumn;
  import DataViewValueColumn = powerbi.DataViewValueColumn;
  import DataViewValueColumnGroup = powerbi.DataViewValueColumnGroup;
  import DataViewValueColumns = powerbi.DataViewValueColumns;
  import ISelectionIdBuilder = powerbi.visuals.ISelectionIdBuilder;
  import ISelectionId = powerbi.visuals.ISelectionId;

  class MockISelectionIdBuilder implements ISelectionIdBuilder {
      withCategory(categoryColumn: DataViewCategoryColumn, index: number): this;
      withSeries(seriesColumn: DataViewValueColumns, valueColumn: DataViewValueColumn | DataViewValueColumnGroup): this;
      withMeasure(measureId: string): this;
      createSelectionId(): ISelectionId;
      withMatrixNode(matrixNode: DataViewMatrixNode, levels: DataViewHierarchyLevel[]): this;
      withTable(table: DataViewTable, rowIndex: number): this;
  }
  ```

  - `createSelectionIdBuilder` สร้างและแสดงอินสแตนซ์ของ **ISelectionIdBuilder** จริง ๆ แล้วคือ **MockISelectionIdBuilder**
    ```typescript
    function createSelectionIdBuilder(): ISelectionIdBuilder;
    ```

    ตัวอย่าง:
    ```typescript
    import { selectionIdBuilder } from "powerbi-visuals-utils-testutils";

    let selectionIdBuilder = createSelectionIdBuilder();
    ```

> [!NOTE]
> **MockISelectionIdBuilder** เป็นการดำเนินการหลอกของ  **ISelectionIdBuilder** และควรใช้กับหน่วยการทดสอบเท่านั้น

### <a name="mockiselectionmanager"></a>MockISelectionManager

ใช้ **ISelectionManager** เพื่อทดสอบวิชวล Power BI โดยไม่มีการขึ้นต่อกันภายนอกเช่น เฟรมเวิร์ก Power BI 

  ```typescript
  import powerbi from "powerbi-visuals-api";
  import IPromise = powerbi.IPromise;
  import ISelectionId = powerbi.visuals.ISelectionId;
  import ISelectionManager = powerbi.extensibility.ISelectionManager;

  class MockISelectionManager implements ISelectionManager {
      select(selectionId: ISelectionId | ISelectionId[], multiSelect?: boolean): IPromise<ISelectionId[]>;
      hasSelection(): boolean;
      clear(): IPromise<{}>;
      getSelectionIds(): ISelectionId[];
      containsSelection(id: ISelectionId): boolean;
      showContextMenu(selectionId: ISelectionId, position: IPoint): IPromise<{}>;
      registerOnSelectCallback(callback: (ids: ISelectionId[]) => void): void;
      simutateSelection(selections: ISelectionId[]): void;
  }
  ```

  - `createSelectionManager` สร้างและแสดงอินสแตนซ์ของ **ISelectionManager** จริง ๆ แล้วคือ **MockISelectionManager**
    ```typescript
    function createSelectionManager(): ISelectionManager
    ```

    ตัวอย่าง:
    ```typescript
    import { createSelectionManager } from "powerbi-visuals-utils-testutils";

    let selectionManager: ISelectionManager = createSelectionManager();
    ```

> [!NOTE]
> **MockISelectionManager** เป็นการดำเนินการหลอกของ  **ISelectionManager** และควรใช้กับหน่วยการทดสอบเท่านั้น

### <a name="mockilocale"></a>MockILocale

  ตั้งค่าภาษาและเปลี่ยนแปลงภาษาสำหรับความต้องการของคุณในระหว่างกระบวนการทดสอบหน่วย
  ```typescript
  class MockILocale {
      constructor(locales?: Object): void; // Default locales are en-US and ru-RU 
      locale(key: string): void;// setter property
      locale(): string; // getter property
  }
  ```
  - `createLocale` สร้างและแสดงอินสแตนซ์ของ **MockILocale**
    ```typescript
    funciton createLocale(locales?: Object): MockILocale;
    ```

### <a name="mockitooltipservice"></a><a id="mockitooltipservice"></a> MockITooltipService
จำลอง `TooltipService` และเรียกใช้สำหรับความต้องการของคุณในระหว่างกระบวนการทดสอบหน่วย
  ```typescript
  class MockITooltipService implements ITooltipService {
      constructor(isEnabled: boolean = true);
      enabled(): boolean;
      show(options: TooltipShowOptions): void;
      move(options: TooltipMoveOptions): void;
      hide(options: TooltipHideOptions): void;
  }
  ```
  - `createTooltipService` สร้างและแสดงอินสแตนซ์ของ **MockITooltipService**
    ```typescript
    function createTooltipService(isEnabled?: boolean): ITooltipService;
    ```

### <a name="mockiallowinteractions"></a>MockIAllowInteractions

```typescript
export class MockIAllowInteractions {
    constructor(public isEnabled?: boolean); // false by default
}
```
  - `createAllowInteractions` สร้างและแสดงอินสแตนซ์ของ **MockIAllowInteractions**
    ```typescript
    function createAllowInteractions(isEnabled?: boolean): MockIAllowInteractions;
    ```

### <a name="mockilocalizationmanager"></a><a id="mockilocalizationmanager"></a> MockILocalizationManager
มีความสามารถพื้นฐานของ **LocalizationManager** ซึ่งจำเป็นสำหรับการทดสอบหน่วย
```typescript
class MockILocalizationManager implements ILocalizationManager {
    constructor(displayNames: {[key: string]: string});
    getDisplayName(key: string): string; // returns default or setted displayNames for localized elements
}
```
  - `createLocalizationManager` สร้างและแสดงอินสแตนซ์ของ **ILocalizationManager**จริง ๆ แล้วคือ **MockILocalizationManager**
    ```typescript
    function createLocalizationManager(displayNames?: any): ILocalizationManager;
    ```

    ตัวอย่าง:
    ```typescript
    import { createLocalizationManager } from "powerbi-visuals-utils-testutils";
    let localizationManagerMock: ILocalizationManager = createLocalizationManager();
    ```

### <a name="mockitelemetryservice"></a>MockITelemetryService
จำลองการใช้งาน **TelemetryService**
```typescript
class MockITelemetryService implements ITelemetryService {
    instanceId: string;
    trace(veType: powerbi.VisualEventType, payload?: string) {
    }
}
```
  การสร้าง `MockITelemetryService`
    ```typescript
    function createTelemetryService(): ITelemetryService;
    ```
### <a name="mockiauthenticationservice"></a>MockIAuthenticationService
จำลองการทำงานของ **AuthenticationService** โดยการกำหนดโทเค็น AAD ที่ทดสอบแล้ว
```typescript
class MockIAuthenticationService implements IAuthenticationService  {
    constructor(token: string);
    getAADToken(visualId?: string): powerbi.IPromise<string>
}
```
  - `createAuthenticationService` สร้างและแสดงอินสแตนซ์ของ **IAuthenticationService**จริง ๆ แล้วคือ **MockIAuthenticationService**
    ```typescript
    function createAuthenticationService(token?: string): IAuthenticationService;
    ```

### <a name="mockistorageservice"></a>MockIStorageService
ช่วยให้คุณสามารถใช้ **ILocalVisualStorageService** กับลักษณะการทำงานเดียวกันกับ **LocalStorage**
```typescript
class MockIStorageService implements ILocalVisualStorageService {
  get(key: string): IPromise<string>;
  set(key: string, data: string): IPromise<number>;
  remove(key: string): void;
}
```
  - `createStorageService` สร้างและแสดงอินสแตนซ์ของ **ILocalVisualStorageService** จริง ๆ แล้วคือ **MockIStorageService**
    ```typescript
    function createStorageService(): ILocalVisualStorageService;
    ```

### <a name="mockieventservice"></a>MockIEventService
```typescript
import powerbi from "powerbi-visuals-api";
import IVisualEventService = powerbi.extensibility.IVisualEventService;
import VisualUpdateOptions = powerbi.extensibility.VisualUpdateOptions;

class MockIEventService implements IVisualEventService {
      renderingStarted(options: VisualUpdateOptions): void;
      renderingFinished(options: VisualUpdateOptions): void;
      renderingFailed(options: VisualUpdateOptions, reason?: string): void;
}
```
  - `createEventService` สร้างและแสดงอินสแตนซ์ของ **IVisualEventService**จริง ๆ แล้วคือ **MockIEventService**
    ```typescript
    function createEventService(): IVisualEventService;
    ```

## <a name="utils"></a>Utils

Utils ประกอบด้วยวิธีการของตัวช่วยเหลือสำหรับการทดสอบหน่วยของ Power BI ที่รวมถึงตัวช่วยเหลือที่เกี่ยวข้องกับสี ตัวเลข และเหตุการณ์

- `renderTimeout`แสดงไทม์เอาต์
  ```typescript
  function renderTimeout(fn: Function, timeout: number = DefaultWaitForRender): number
  ```

- `testDom` ช่วยตั้งค่าการแข่งขันในการทดสอบหน่วย
  ```typescript
  function testDom(height: number | string, width: number | string): JQuery
  ```
  ตัวอย่าง:
  ```typescript
  import { testDom }  from "powerbi-visuals-utils-testutils";
  describe("testDom", () => {
      it("should return an element", () => {
          let element: JQuery = testDom(500, 500);
          expect(element.get(0)).toBeDefined();
      });
  });
  ```

### <a name="color-related-helper-methods"></a>วิธีการของตัวช่วยเหลือที่เกี่ยวข้องกับสี

- `getSolidColorStructuralObject`
  ```typescript
  function getSolidColorStructuralObject(color: string): any
  ```
  แสดงโครงสร้างต่อไปนี้:

  ```json
  { solid: { color: color } }
  ```

- `assertColorsMatch` เปรียบเทียบวัตถุ **RgbColor** ที่แยกวิเคราะห์จากสตริงที่ป้อนเข้า
  ```typescript
  function assertColorsMatch(actual: string, expected: string, invert: boolean = false): boolean
  ```

- `parseColorString`แยกวิเคราะห์สีจากสตริงที่ป้อนข้อมูลและแสดงในอินเทอร์เฟซที่ระบุ **RgbColor**
  ```typescript
  function parseColorString(color: string): RgbColor
  ```

### <a name="number-related-helper-methods"></a>วิธีการของตัวช่วยเหลือที่เกี่ยวข้องกับตัวเลข

- `getRandomNumbers` สร้างตัวเลขสุ่มโดยใช้ค่าต่ำสุดและค่าสูงสุด คุณสามารถระบุ `exceptionList` และให้ฟังก์ชันสำหรับการเปลี่ยนแปลงผลลัพธ์ได้
  ```typescript
  function getRandomNumber(
      min: number,
      max: number,
      exceptionList?: number[],
      changeResult: (value: any) => number = x => x): number
  ```

- `getRandomNumbers` แสดงอาร์เรย์ของตัวเลขสุ่มที่สร้างขึ้นโดยวิธีการ `getRandomNumber` ด้วยค่าต่ำสุดและค่าสูงสุดที่ระบุ
  ```typescript
  function getRandomNumbers(count: number, min: number = 0, max: number = 1): number[]
  ```

### <a name="event-related-helper-methods"></a>วิธีการของตัวช่วยเหลือที่เกี่ยวข้องกับเหตุการณ์
วิธีการต่อไปนี้จะถูกเขียนขึ้นสำหรับการจำลองเหตุการณ์ของเว็บเพจในการทดสอบหน่วย

- `clickElement` จำลองการคลิกที่องค์ประกอบที่ระบุ
  ```typescript
  function clickElement(element: JQuery, ctrlKey: boolean = false): void
  ```

- `createTouch` แสดงวัตถุ**การสัมผัส** เพื่อช่วยในการจำลองเหตุการณ์การสัมผัส
  ```typescript
  function createTouch(x: number, y: number, element: JQuery, id: number = 0): Touch
  ```

- `createTouchesList` แสดงรายการของเหตุการณ์ **การสัมผัส**แบบจำลอง
  ```typescript
  function createTouchesList(touches: Touch[]): TouchList
  ```

- `createContextMenuEvent` แสดง **MouseEvent**
  ```typescript
  function createContextMenuEvent(x: number, y: number): MouseEvent
  ```

- `createMouseEvent` สร้างและแสดง **MouseEvent**
  ```typescript
  function createMouseEvent(
      mouseEventType: MouseEventType,
      eventType: ClickEventType,
      x: number,
      y: number,
      button: number = 0): MouseEvent
  ```

- `createTouchEndEvent`
  ```typescript
  function createTouchEndEvent(touchList?: TouchList): UIEvent
  ```

- `createTouchMoveEvent`
  ```typescript
  function createTouchMoveEvent(touchList?: TouchList): UIEvent
  ```

- `createTouchStartEvent`
  ```typescript
  function createTouchStartEvent(touchList?: TouchList): UIEvent
  ```

### <a name="d3-event-related-helper-methods"></a>วิธีการของตัวช่วยเหลือที่เกี่ยวข้องกับเหตุการณ์ D3

วิธีการต่อไปนี้จะใช้ในการจำลองเหตุการณ์ D3 ในการทดสอบหน่วย

- `flushAllD3Transitions` บังคับการเปลี่ยนแปลง D3 ทั้งหมดให้เสร็จสมบูรณ์

  ```typescript
  function flushAllD3Transitions()
  ```
  
  > [!NOTE]
  > ตามปกติ การเปลี่ยนช่วงการหน่วงเวลาศูนย์จะดำเนินการหลังจากการหน่วงเวลาแบบทันที (< 10 ms) แต่อาจทำให้เกิดการกะพริบแบบสั้นๆ ถ้าเบราว์เซอร์แสดงหน้าสองครั้ง หนึ่งครั้งที่จุดสิ้นสุดของการวนรอบเหตุการณ์แรก แล้วอีกครั้งในการเรียกกลับตัวจับเวลาครั้งแรก
  >
  > กระพริบเหล่านี้จะเห็นได้ชัดขึ้นใน IE และมี Webviews จำนวนมาก และไม่แนะนำสำหรับ iOS
  > 
  > ด้วยการล้างข้อมูลคิวตัวจับเวลาที่จุดสิ้นสุดของการวนรอบเหตุการณ์แรกคุณ สามารถเรียกใช้การเปลี่ยนการหน่วงเวลาศูนย์ใด ๆ ได้ทันทีและหลีกเลี่ยงการกะพริบ

นอกจากนี้ยังรวมวิธีการต่อไปนี้:
```typescript
function d3Click(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3MouseUp(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3MouseDown(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3MouseOver(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3MouseMove(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3MouseOut(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3KeyEvent(element: JQuery, typeArg: string, keyArg: string, keyCode: number): void
function d3TouchStart(element: JQuery, touchList?: TouchList): void
function d3TouchMove(element: JQuery, touchList?: TouchList): void
function d3TouchEnd(element: JQuery, touchList?: TouchList): void
function d3ContextMenu(element: JQuery, x: number, y: number): void
```

### <a name="helper-interfaces"></a>อินเทอร์เฟซตัวช่วยเหลือ
อินเทอร์เฟซและการแจกแจงต่อไปนี้จะใช้ในฟังก์ชันตัวช่วยเหลือ

```typescript
interface RgbColor {
    R: number;
    G: number;
    B: number;
    A?: number; 
}

enum ClickEventType {
    Default = 0,
    CtrlKey = 1,
    AltKey = 2,
    ShiftKey = 4,
    MetaKey = 8,
}

enum MouseEventType {
    click,
    mousedown,
    mouseup,
    mouseover,
    mousemove,
    mouseout,
}
```

## <a name="next-steps"></a>ขั้นตอนถัดไป

เมื่อต้องการเขียนการทดสอบหน่วยสำหรับวิชวล Power BI ที่ใช้ Webpack และdkiทดสอบหน่วยด้วย `karma` และ `jasmine` โปรดดูตัวอย่าง [บทช่วยสอน: เพิ่มการทดสอบหน่วยสำหรับโครงการวิชวล Power BI ](./unit-tests-introduction.md)

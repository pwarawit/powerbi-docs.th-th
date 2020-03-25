---
title: การรองรับโหมดความคมชัดสูงในวิชวล Power BI
description: บทความนี้อธิบายวิธีการเพิ่มการรองรับโหมดความคมชัดสูงไปยังวิชวล Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 9372187ae1fdfac27f6b3e7267a1c0622c063464
ms.sourcegitcommit: 2c798b97fdb02b4bf4e74cf05442a4b01dc5cbab
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/21/2020
ms.locfileid: "80114347"
---
# <a name="high-contrast-mode-support-in-power-bi-visuals"></a>การรองรับโหมดความคมชัดสูงในวิชวล Power BI

การตั้งค่า*ความคมชัดสูง*ของ Windows ทำให้ข้อความและแอปสามารถดูได้ง่ายขึ้นโดยการแสดงสีที่แตกต่างกันมากขึ้น บทความนี้อธิบายวิธีการเพิ่มการรองรับโหมดความคมชัดสูงไปยังวิชวล Power BI สำหรับข้อมูลเพิ่มเติม โปรดดูที่ [การรองรับโหมดความคมชัดสูงในวิชวล Power BI](https://powerbi.microsoft.com/blog/power-bi-desktop-june-2018-feature-summary/#highContrast)

หากต้องการดูการนำการรองรับโหมดความคมชัดสูงไปใช้งาน โปรดไปที่ [พื้นที่เก็บข้อมูลวิชวล PowerBI-visuals-sampleBarChart](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/61011c82b66ca0d3321868f1d089c65101ca42e6)

## <a name="on-initialization"></a>เกี่ยวกับการเตรียมใช้งาน

สมาชิก colorPalette ของ `options.host` มีคุณสมบัติหลายอย่างสำหรับโหมดความคมชัดสูง ใช้คุณสมบัติเหล่านี้เพื่อตรวจสอบว่าโหมดความคมชัดสูงเปิดใช้งานอยู่หรือไม่ และถ้าเปิดอยู่ สีอะไรที่จะใช้

### <a name="detect-that-power-bi-is-in-high-contrast-mode"></a>ตรวจพบว่า Power BI อยู่ในโหมดความคมชัดสูง

ถ้า`host.colorPalette.isHighContrast` เป็น`true` โหมดความคมชัดสูงมีการใช้งานอยู่และวิชวลควรวาดตัวเองตามลำดับ

### <a name="get-high-contrast-colors"></a>รับสีที่มีความคมชัดสูง

ในโหมดความคมชัดสูง วิชวลของคุณควรจำกัดตัวเองเป็นการตั้งค่าดังต่อไปนี้:

* **สีพื้นหน้า** ใช้ในการวาดเส้น ไอคอน ข้อความ และเค้าร่างหรือการเติมรูปร่าง
* **สีพื้นหลัง** ใช้สำหรับพื้นหลังและเป็นสีเติมของรูปร่างที่มีการระบุไว้
* **สีที่เลือกไว้สำหรับเบื้องหน้า**  จะใช้เพื่อระบุองค์ประกอบที่เลือกหรือที่ใช้งานอยู่
* **สีของการเชื่อมโยงหลายมิติ** จะใช้เฉพาะกับข้อความที่เชื่อมโยงหลายมิติ

> [!NOTE]
> หากจำเป็นต้องใช้สีทุติยภูมิ อาจใช้สีพื้นหน้ากับความทึบแสงบางอย่าง (วิชวลแบบดั้งเดิมของ Power BI ใช้ความทึบ 40%) ใช้การดำเนินการนี้เพื่อให้สามารถดูรายละเอียดของวิชวลได้ง่ายขึ้น

ในระหว่างการเตรียมใช้งาน คุณสามารถจัดเก็บค่าดังต่อไปนี้:

```typescript
private isHighContrast: boolean;

private foregroundColor: string;
private backgroundColor: string;
private foregroundSelectedColor: string;
private hyperlinkColor: string;
//...

constructor(options: VisualConstructorOptions) {
    this.host = options.host;
    let colorPalette: ISandboxExtendedColorPalette = host.colorPalette;
    //...
    this.isHighContrast = colorPalette.isHighContrast;
    if (this.isHighContrast) {
        this.foregroundColor = colorPalette.foreground.value;
        this.backgroundColor = colorPalette.background.value;
        this.foregroundSelectedColor = colorPalette.foregroundSelected.value;
        this.hyperlinkColor = colorPalette.hyperlink.value;
    }
```

หรือคุณสามารถจัดเก็บออบเจ็กต์ `host` ในระหว่างการเตรียมใช้งานและเข้าถึงคุณสมบัติ `colorPalette` ที่เกี่ยวข้องในระหว่างการอัปเดตได้

## <a name="on-update"></a>ในการอัปเดต

การใช้งานที่เฉพาะเจาะจงของการรองรับความคมชัดสูงจะแตกต่างในแต่ละวิชวล และขึ้นอยู่กับรายละเอียดของการออกแบบกราฟิก เพื่อให้ง่ายต่อการแยกความแตกต่างของรายละเอียดที่สำคัญด้วยสีที่จำกัด โดยทั่วไป โหมดความคมชัดสูงจะต้องมีการออกแบบที่แตกต่างกันเล็กน้อยกว่าค่าเริ่มต้น

วิชวลแบบดั้งเดิมของ Power BI เป็นไปตามแนวทางเหล่านี้:

* จุดข้อมูลทั้งหมดใช้สีเดียวกัน (พื้นหน้า)
* ข้อความ แกน ลูกศร เส้น และอื่น ๆ ทั้งหมดใช้สีพื้นหน้า
* รูปร่างหนาจะวาดเป็นเค้าร่างด้วยเส้นขีดหนา (อย่างน้อยสองพิกเซล) และการเติมสีพื้นหลัง
* เมื่อจุดข้อมูลมีความเกี่ยวข้องกัน จุดข้อมูลจะแตกต่างตามรูปร่างเครื่องหมายที่แตกต่างกัน และเส้นข้อมูลมีความแตกต่างกันตามการลงเส้นประที่แตกต่างกัน
* เมื่อไฮไลท์องค์ประกอบข้อมูล องค์ประกอบอื่น ๆ ทั้งหมดเปลี่ยนความทึบของตนเป็น 40%
* สำหรับตัวแบ่งส่วนข้อมูล องค์ประกอบตัวกรองที่ใช้งานอยู่จะใช้สีที่เลือกไว้สำหรับเบื้องหน้า

ในแผนภูมิแท่งตัวอย่างต่อไปนี้ ตัวอย่างเช่น แถบทั้งหมดจะถูกวาดด้วยโครงร่างเบื้องหน้าที่หนาขนาดสองพิกเซลและการเติมพื้นหลัง เปรียบเทียบลักษณะที่ปรากฏกับสีเริ่มต้นและธีมสองแบบที่มีความคมชัดสูง:

![แผนภูมิแท่งตัวอย่างโดยใช้สีมาตรฐาน ](media/high-contrast-support/hc-samplebarchart-standard.png)
![ แผนภูมิแท่งตัวอย่างโดยใช้ธีมสี *Dark #2* ](media/high-contrast-support/hc-samplebarchart-dark2.png)
![แผนภูมิแท่งสีตัวอย่างโดยใช้ธีมสี *White*](media/high-contrast-support/hc-samplebarchart-white.png)

ส่วนถัดไปแสดงตำแหน่งเดียวในฟังก์ชัน `visualTransform` ที่มีการเปลี่ยนแปลงเพื่อรองรับความคมชัดสูง ซึ่งเรียกว่าเป็นส่วนหนึ่งของการแสดงผลระหว่างการอัปเดต

### <a name="before"></a>ก่อน

```typescript
for (let i = 0, len = Math.max(category.values.length, dataValue.values.length); i < len; i++) {
    let defaultColor: Fill = {
        solid: {
            color: colorPalette.getColor(category.values[i] + '').value
        }
    };

    barChartDataPoints.push({
        category: category.values[i] + '',
        value: dataValue.values[i],
        color: getCategoricalObjectValue<Fill>(category, i, 'colorSelector', 'fill', defaultColor).solid.color,
        selectionId: host.createSelectionIdBuilder()
            .withCategory(category, i)
            .createSelectionId()
    });
}
```

### <a name="after"></a>หลังจาก

```typescript
for (let i = 0, len = Math.max(category.values.length, dataValue.values.length); i < len; i++) {
    const color: string = getColumnColorByIndex(category, i, colorPalette);

    const selectionId: ISelectionId = host.createSelectionIdBuilder()
        .withCategory(category, i)
        .createSelectionId();

    barChartDataPoints.push({
        color,
        strokeColor,
        strokeWidth,
        selectionId,
        value: dataValue.values[i],
        category: `${category.values[i]}`,
    });
}

//...

function getColumnColorByIndex(
    category: DataViewCategoryColumn,
    index: number,
    colorPalette: ISandboxExtendedColorPalette,
): string {
    if (colorPalette.isHighContrast) {
        return colorPalette.background.value;
    }

    const defaultColor: Fill = {
        solid: {
            color: colorPalette.getColor(`${category.values[index]}`).value,
        }
    };

    return getCategoricalObjectValue<Fill>(category, index, 'colorSelector', 'fill', defaultColor).solid.color;
}
```

---
title: ทำความเข้าใจเกี่ยวกับการแมปมุมมองข้อมูลในวิชวล Power BI
description: บทความนี้อธิบายวิธีการที่ Power BI แปลงข้อมูลก่อนส่งผ่านไปเป็นวิชวล
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: fece594fa6236f01c707f0b84ddca977fb32dede
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83349298"
---
# <a name="add-the-locale-in-power-bi-for-power-bi-visuals"></a>เพิ่มตำแหน่งที่ตั้งใน Power BI สำหรับวิชวล Power BI

วิชวลสามารถเรียกใช้ตำแหน่งที่ตั้งใน Power BI เพื่อแปลเนื้อหาให้เป็นภาษาที่เกี่ยวข้อง

อ่านเพิ่มเติมเกี่ยวกับ [ภาษาและประเทศ/ภูมิภาคที่รองรับสำหรับ Power BI](./../../fundamentals/supported-languages-countries-regions.md)

ตัวอย่างเช่น รับตำแหน่งที่ตั้งในวิชวลแผนภูมิแท่งตัวอย่าง

![การแปลวิชวลแผนภูมิแท่งตัวอย่างให้เป็นภาษาท้องถิ่น](media/localization/locale-in-samplebarchart.png)

แผนภูมิแท่งเหล่านี้แต่ละอันถูกสร้างขึ้นตามตำแหน่งที่ตั้งที่แตกต่างกัน (อังกฤษ บาสก์ และฮินดี) และจะแสดงในคำแนะนำเครื่องมื

> [!NOTE]
> ตัวจัดการการแปลเป็นภาษาท้องถิ่นในรหัสของวิชวลรองรับ API 1.10.0 และเวอร์ชันที่สูงกว่า

## <a name="get-the-locale"></a>รับตำแหน่งที่ตั้ง

`locale` ถูกส่งผ่านเป็นสตริงระหว่างการเตรียมใช้งานของวิชวล ถ้ามีการเปลี่ยนแปลงตำแหน่งที่ตั้งใน Power BI จะมีการสร้างวิชวลอีกครั้งด้วยตำแหน่งที่ตั้งใหม่ คุณสามารถค้นหารหัสตัวอย่างฉบับสมบูรณ์ได้ที่ SampleBarChart with Locale

ตอนนี้ คอนสตรักเตอร์ BarChart มีสมาชิกตำแหน่งที่ตั้ง ซึ่งมีการสร้างอินสแตนซ์ในคอนสตรักเตอร์ด้วยอินสแตนซ์ตำแหน่งที่ตั้งของโฮสต์

```typescript
private locale: string;
...
this.locale = options.host.locale;
```

ตำแหน่งที่ตั้งที่ได้รับการสนับสนุน:

สตริงของตำแหน่งที่ตั้ง | Language
--------------|----------------------
ar-SA | العربية (อาหรับ)
bg-BG | български (บัลแกเรีย)
ca-ES | català (คาตาลัน)
cs-CZ | čeština (เช็ก)
da-DK | dansk (เดนมาร์ก)
de-DE | Deutsche (เยอรมัน)
el-GR | ελληνικά (กรีก)
en-US | English (อังกฤษ)
es-ES | español service (สเปน)
et-EE | eesti (เอสโตเนีย)
eU-ES | Euskal (บาสก์)
fi-FI | suomi (ฟินแลนด์)
fr-FR | français (ฝรั่งเศส)
gl-ES | galego (กาลิเชีย)
he-IL | עברית (ฮิบรู)
hi-IN | हिन्दी (ฮินดี)
hr-HR | hrvatski (โครเอเชีย)
hu-HU | magyar (ฮังการี)
id-ID | Bahasa Indonesia (อินโดนีเซีย)
it-IT | italiano (อิตาลี)
ja-JP | 日本の (ญี่ปุ่น)
kk-KZ | Қазақ (คาซัคสถาน)
ko-KR | 한국의 (เกาหลี)
lt-LT | Lietuvos (ลิทัวเนีย)
lv-LV | Latvijas (ลัตเวีย)
ms-MY | Bahasa Melayu (มลายู)
nb-NO | norsk (นอร์เวย์)
nl-NL | Nederlands (ดัตช์)
pl-PL | polski (โปแลนด์)
pt-BR | português (โปรตุเกส)
pt-PT | português (โปรตุเกส)
ro-RO | românesc (โรมาเนีย)
ru-RU | русский (รัสเซีย)
sk-SK | slovenský (สโลวาเกีย)
sl-SI | slovenský (สโลเวเนีย)
sr-Cyrl-RS | српски (เซอร์เบีย)
sr-Latn-RS | srpski (เซอร์เบีย)
sv-SE | svenska (สวีเดน)
th-TH | ไทย (ภาษาไทย)
tr-TR | Türk (ตุรกี)
uk-UA | український (ยูเครน)
vi-VN | tiếng Việt (เวียดนาม)
zh-CN | 中国 (จีนแบบย่อ)
zh-TW | 中國 (จีนแบบดั้งเดิม)

> [!NOTE]
> ใน PowerBI Desktop คุณสมบัติของตำแหน่งที่ตั้งจะมีภาษาของ PowerBI Desktop ติดตั้งอยู่ด้วย

## <a name="localizing-the-property-pane-for-power-bi-visuals"></a>แปลบานหน้าต่างคุณสมบัติสำหรับวิชวล Power BI ให้เป็นภาษาท้องถิ่น

เขตข้อมูลในบานหน้าต่างคุณสมบัติสามารถเป็นภาษาท้องถิ่นเพื่อมอบประสบการณ์การใช้งานแบบบูรณาการรวมและสอดคล้องกันมากขึ้น ซึ่งทำให้วิชวลแบบกำหนดเองของคุณนั้นทำงานเหมือนกับวิชวลหลักอื่นๆ ของ Power BI

ตัวอย่างเช่น วิชวลแบบกำหนดเองที่ยังไม่ได้แปลเป็นภาษาท้องถิ่นที่สร้างขึ้นโดยใช้คำสั่ง `pbiviz new` จะแสดงเขตข้อมูลต่อไปนี้ในบานหน้าต่างคุณสมบัติ:

![การแปลบานหน้าต่างคุณสมบัติให้เป็นภาษาท้องถิ่น](media/localization/property-pane.png)

ทั้งข้อมูลหมวดหมู่และข้อมูลหน่วยวัดถูกกำหนดไว้ในไฟล์ capabilities.json เป็น `displayName`

## <a name="how-to-localize-capabilities"></a>วิธีการแปลความสามารถให้เป็นภาษาท้องถิ่น

ก่อนอื่นให้เพิ่มคีย์ชื่อที่แสดงให้กับชื่อที่แสดงทั้งหมดที่คุณต้องการแปลความสามารถของคุณให้เป็นภาษาท้องถิ่น ในตัวอย่างนี้:

```json
{
    "dataRoles": [
        {
            "displayName": "Category Data",
            "displayNameKey": "VisualCategoryDataNameKey1",
            "name": "category",
            "kind": "Grouping"
        },
        {
            "displayName": "Measure Data",
            "displayNameKey": "VisualMeasureDataNameKey2",
            "name": "measure",
            "kind": "Measure"
        }
    ]
}
```

จากนั้นเพิ่มไดเรกทอรีที่เรียกว่า stringResources ไดเรกทอรีจะประกอบด้วยไฟล์ทรัพยากรสตริงที่แตกต่างกันทั้งหมดของคุณโดยยึดตามตำแหน่งที่ตั้งที่คุณต้องการให้วิชวลของคุณสนับสนุน ในส่วนของไดเรกทอรีนี้ คุณจะต้องเพิ่มไฟล์ JSON สำหรับทุกตำแหน่งที่ตั้งที่คุณต้องการสนับสนุน ไฟล์เหล่านั้นประกอบด้วยข้อมูลตำแหน่งที่ตั้ง และค่าสตริงที่เป็นภาษาท้องถิ่นสำหรับทุก displayNameKey ที่คุณต้องการแทนที่

ในตัวอย่างของเรา สมมติว่าเราต้องการสนับสนุนภาษาอาหรับและฮิบรู เราจะต้องเพิ่มไฟล์ JSON สองไฟล์ด้วยวิธีต่อไปนี้:

![สตริงการแปลเป็นภาษาท้องถิ่นในโฟลเดอร์ทรัพยากรสตริง](media/localization/stringresources-files.png)

ไฟล์ JSON ทุกไฟล์กำหนดตำแหน่งที่ตั้งเดียว (ไฟล์นี้จะต้องเป็นหนึ่งในตำแหน่งที่ตั้งจากรายการที่ได้รับการสนับสนุนด้านบน) โดยมีค่าสตริงสำหรับคีย์ชื่อที่แสดงที่ต้องการ ในตัวอย่างของเรา ไฟล์ทรัพยากรสตริงภาษาฮิบรูจะมีลักษณะดังต่อไปนี้:

```json
{
    "locale": "he-IL",
    "values": {
        "VisualCategoryDataNameKey1": "קטגוריה",
        "VisualMeasureDataNameKey2": "יחידות מידה"
    }
}
```

ขั้นตอนที่จำเป็นทั้งหมดในการใช้ตัวจัดการการแปลเป็นภาษาท้องถิ่นจะอธิบายไว้ด้านล่าง

> [!NOTE]
> ในขณะนี้ การแปลเป็นภาษาท้องถิ่นไม่รองรับการดีบักวิชวล dev

## <a name="setup-environment"></a>สภาพแวดล้อมการตั้งค่า

### <a name="desktop"></a>เดสก์ท็อป

สำหรับการใช้งานบนเดสก์ท็อป ให้ดาวน์โหลด Power BI desktop เวอร์ชันที่แปลเป็นภาษาท้องถิ่นจาก https://powerbi.microsoft.com

### <a name="web-service"></a>บริการบนเว็บ

ถ้าคุณใช้เว็บไคลเอ็นต์ (เบราว์เซอร์) ในบริการ ให้เปลี่ยนภาษาของคุณในการตั้งค่า:

![การแปลเป็นภาษาท้องถิ่นในบริการบนเว็บ](media/localization/webservice-settings.png)

## <a name="resource-file"></a>ไฟล์ทรัพยากร

เพิ่มไฟล์ resources.resjson ไปยังโฟลเดอร์ที่มีชื่อเป็นตำแหน่งที่ตั้งที่คุณจะใช้งานภายในโฟลเดอร์ stringResources ซึ่งคือ en-US และ ru-RU ในตัวอย่างของเรา

![ไฟล์ resjson ใหม่](media/localization/new-resjson.png)

หลังจากนั้น ให้เพิ่มสตริงการแปลเป็นภาษาท้องถิ่นทั้งหมดที่คุณจะใช้ลงในไฟล์ resources.resjson ซึ่งคุณเพิ่มไว้แล้วในขั้นตอนก่อนหน้า

```json
{
    ...
    "Role_Legend": "Обозначения",
    "Role_task": "Задача",
    "Role_StartDate": "Дата начала",
    "Role_Duration": "Длительность"
    ...
}
```

ตัวอย่างนี้เป็นไฟล์ resources.resjson เวอร์ชัน en-US:

```json
{
    ...
    "Role_Legend": "Legend",
    "Role_task": "Task",
    "Role_StartDate": "Start date",
    "Role_Duration": "Duration"
    ...
}
```

อินสแตนซ์ LocalizationManager ใหม่สร้างอินสแตนซ์ของ LocalizationManager ในโค้ดของวิชวลดังต่อไปนี้

```typescript
private localizationManager: ILocalizationManager;

constructor(options: VisualConstructorOptions) {
    this.localizationManager = options.host.createLocalizationManager();
}
```

## <a name="localizationmanager-usage-sample"></a>ตัวอย่างการใช้ localizationManager

ตอนนี้คุณสามารถเรียกใช้ฟังก์ชัน getDisplayName ของตัวจัดการการแปลเป็นภาษาท้องถิ่นด้วยอาร์กิวเมนต์คีย์สตริงที่คุณกำหนดไว้ใน resources.resjson เพื่อรับสตริงที่ต้องการที่ใดก็ได้ภายในโค้ดของคุณ:

```typescript
let legend: string = this.localization.getDisplayName("Role_Legend");
```

ซึ่งส่งกลับ "Legend" สำหรับ en-US และ "Обозначения" สำหรับ ru-RU

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [โปรดอ่าน วิธีการใช้ยูทิลิตี้การจัดรูปแบบเพื่อการจัดรูปแบบที่แปลเป็นภาษาท้องถิ่น](utils-formatting.md)

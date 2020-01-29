---
title: โครงสร้างของโครงการแสดงผล Power BI
description: บทความนี้อธิบายเกี่ยวกับโฟลเดอร์และโครงสร้างไฟล์ของโครงการวิชวล Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 01/12/2020
ms.openlocfilehash: 16e7a317102602ffb4faf04da0ed2cae588a2a4d
ms.sourcegitcommit: 052df769e6ace7b9848493cde9f618d6a2ae7df9
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/14/2020
ms.locfileid: "75925533"
---
# <a name="power-bi-visual-project-structure"></a>โครงสร้างของโครงการแสดงผล Power BI

วิธีที่ดีที่สุดในการเริ่มต้นสร้างวิชวล Power BI ใหม่คือการใช้เครื่องมือวิชวล Power BI [.pbiviz](https://www.npmjs.com/package/powerbi-visuals-tools)

ในการสร้างวิชวลใหม่ ให้นำทางไปยังไดเรกทอรีที่คุณต้องการให้วิชวล Power BI เข้าไปอยู่ และเรียกคำสั่งใช้งาน:

`pbiviz new <visual project name>`

เรียกใช้งานคำสั่งนี้สร้างโฟลเดอร์วิชวล Power BI ที่ประกอบด้วยไฟล์ต่อไปนี้:

```markdown
project
├───.vscode
│   ├───launch.json
│   └───settings.json
├───assets
│   └───icon.png
├───node_modules
├───src
│   ├───settings.ts
│   └───visual.ts
├───style
│   └───visual.less
├───capabilities.json
├───package-lock.json
├───package.json
├───pbiviz.json
├───tsconfig.json
└───tslint.json
```

## <a name="folder-and-file-description"></a>คำอธิบายโฟลเดอร์และไฟล์

ส่วนนี้แสดงข้อมูลสำหรับแต่ละโฟลเดอร์และไฟล์ในไดเรกทอรีที่เครื่องมือวิชวล Power BI  **pbiciz** สร้าง  

### <a name="vscode"></a>.vscode

โฟลเดอร์นี้ประกอบด้วยการตั้งค่าโปรเจคโค้ด VS

ในการกำหนดค่าพื้นที่ทำงานของคุณ แก้ไขไฟล์ `.vscode/settings.json`

สำหรับข้อมูลเพิ่มเติม ดู [การตั้งค่าผู้ใช้และพื้นที่ทำงาน](https://code.visualstudio.com/docs/getstarted/settings)

### <a name="assets"></a>สินทรัพย์

โฟลเดอร์นี้ประกอบด้วยไฟล์ `icon.png`

เครื่องมือวิชวล Power BI ใช้ไฟล์นี้เป็นไอคอนวิชวล Power BI ใหม่ ในแผงการแสดงภาพของ Power BI

<!--- ![Visualization pane](./media/visualization-pane-analytics-tab.png) --->

### <a name="src"></a>src

โฟลเดอร์นี้ประกอบด้วยโค้ดแหล่งที่มาของวิชวล

ในโฟลเดอร์นี้เครื่องมือวิชวล Power BI จะสร้างไฟล์ต่อไปนี้:
* `visual.ts` - โค้ดแหล่งที่มาหลักของวิชวล
* `settings.ts` - โค้ดการตั้งค่าของวิชวล คลาสในไฟล์มีอินเทอร์เฟซสำหรับการกำหนด [คุณสมบัติของวิชวล](./objects-properties.md#properties)ของคุณ

### <a name="style"></a>ลักษณะ

โฟลเดอร์นี้ประกอบด้วยไฟล์ `visual.less` ซึ่งมีลักษณะของวิชวล

### <a name="capabilitiesjson"></a>capabilities.json

ไฟล์นี้ประกอบด้วยคุณสมบัติและการตั้งค่าหลัก (หรือ [ความสามารถ](./capabilities.md)) สำหรับวิชวล อนุญาตให้วิชวลทำการสนับสนุนฟีเจอร์ วัตถุ คุณสมบัติ และ [มุมมองการดูข้อมูล](./dataview-mappings.md)

### <a name="package-lockjson"></a>package-lock.json

ไฟล์นี้สร้างขึ้นมาโดยอัตโนมัติสำหรับการดำเนินการใดๆ ที่ *npm* ปรับเปลี่ยน `node_modules` แผนผังต้นไม้หรือ `package.json` ไฟล์

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับไฟล์นี้ ให้ดูเอกสารกำกับโปรแกรมทางการของ [npm-package-lock.json](https://docs.npmjs.com/files/package-lock.json)

### <a name="packagejson"></a>package.json

ไฟล์นี้อธิบายเกี่ยวกับแพคเกจโครงการ สิ่งนี้ประกอบด้วยข้อมูลเกี่ยวกับโครงการ เช่น ผู้เขียน คำอธิบายและการขึ้นต่อกันของโครงการ

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับไฟล์นี้ ให้ดูเอกสารกำกับโปรแกรมทางการของ [npm-package-lock.json](https://docs.npmjs.com/files/package.json.html)

### <a name="pbivizjson"></a>pbiviz.json

ไฟล์นี้ประกอบด้วยเมตาดาต้าวิชวล

ในการดูตัวอย่าง `pbiviz.json` ไฟล์ที่มีข้อคิดเห็นที่อธิบายรายการเมตาดาต้า ให้ดูที่ส่วน[รายการเมตาดาต้า](#metadata-entries)

### <a name="tsconfigjson"></a>tsconfig.json

ไฟล์การกำหนดค่าสำหรับ [TypeScript](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html).

ไฟล์นี้ต้องประกอบด้วยเส้นทางไปยังแฟ้ม **\*.ts** ที่มีชั้นหลักของวิชวลตั้งอยู่ ที่ระบุเฉพาะใน `visualClassName` คุณสมบัติใน `pbiviz.json` ไฟล์

### <a name="tslintjson"></a>tslint.json

ไฟล์นี้ประกอบด้วย [การกำหนดค่า TSLint](https://palantir.github.io/tslint/usage/configuration/)

## <a name="metadata-entries"></a>รายการเมตาดาต้า

ข้อคิดเห็นในคำบรรยายโค้ดต่อไปนี้จากไฟล์ `pbiviz.json`ที่อธิบายรายการเมตาดาต้า

> [!NOTE]
> * จากรุ่น 3.x.x ของ **เครื่องมือ** pbiciz`externalJS` ไม่ได้รับการสนับสนุน
> * การสนับสนุนตามท้องถิ่น [ให้เพิ่ม Power BI ที่ระบุวิชวลของคุณ](./localization.md)

```json
{
  "visual": {
     // The visual's internal name.
    "name": "<visual project name>",

    // The visual's display name.
    "displayName": "<visual project name>",

    // The visual's unique ID.
    "guid": "<visual project name>23D8B823CF134D3AA7CC0A5D63B20B7F",

    // The name of the visual's main class. Power BI creates the instance of this class to start using the visual in a Power BI report.
    "visualClassName": "Visual",

    // The visual's version number.
    "version": "1.0.0",
    
    // The visual's description (optional)
    "description": "",

    // A URL linking to the visual's support page (optional).
    "supportUrl": "",

    // A link to the source code available from GitHub (optional).
    "gitHubUrl": ""
  },
  // The version of the Power BI API the visual is using.
  "apiVersion": "2.6.0",

  // The name of the visual's author and email.
  "author": { "name": "", "email": "" },

  // 'icon' holds the path to the icon file in the assets folder; the visual's display icon.
  "assets": { "icon": "assets/icon.png" },

  // Contains the paths for JS libraries used in the visual.
  // Note: externalJS' isn't used in the Power BI visuals tool version 3.x.x or higher.
  "externalJS": null,

  // The path to the 'visual.less' style file.
  "style": "style/visual.less",

  // The path to the `capabilities.json` file.
  "capabilities": "capabilities.json",

  // The path to the `dependencies.json` file which contains information about R packages used in R based visuals.
  "dependencies": null,

  // An array of paths to files with localizations.
  "stringResources": []
}
```

## <a name="next-steps"></a>ขั้นตอนถัดไป

* ในการเข้าใจการโต้ตอบระหว่างวิชวล ผู้ใช้และ Power BI ดู [แนวคิดวิชวลของ Power BI](./power-bi-visuals-concept.md)

* เริ่มต้นการพัฒนาวิชวล Power BI ของคุณเองตั้งแต่เริ่มต้น โดยใช้ [ด้วยคำแนะนำทีละขั้นตอน](./custom-visual-develop-tutorial.md)
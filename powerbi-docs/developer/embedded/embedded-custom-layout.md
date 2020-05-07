---
title: เค้าโครงแบบกำหนดเอง ด้วยเนื้อหา Power BI แบบฝังตัว
description: เรียนรู้เกี่ยวกับเค้าโครงแบบกำหนดเองเมื่อมีการฝังเนื้อหา Power BI ลงในแอปพลิเคชันของคุณ
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: reference
ms.date: 12/19/2017
ms.openlocfilehash: e114c208093c9f3401c43e9ea44502e65d6d84fd
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "79493215"
---
# <a name="custom-layouts"></a>เค้าโครงแบบกำหนดเอง

ใช้เค้าโครงแบบกำหนดเอง เพื่อฝังรายงานที่มีเค้าโครงที่ต่างจากรายงานต้นฉบับ การกำหนดเค้าโครงใหม่ แตกต่างกันออกไประหว่าง กำหนดแค่ขนาดหน้าเท่านั้น ไปจนถึงการควบคุมขนาด หรือตำแหน่ง และการมองเห็นของวิชวล

เมื่อต้องการกำหนดเค้าโครงแบบกำหนดเอง นิยามวัตถุเค้าโครงแบบกำหนดเอง และส่งต่อไปยังวัตถุการตั้งค่า ที่อยู่ในการกำหนดค่าฝังตัว นอกจากนี้ ให้ตั้งค่า LayoutType ให้เป็น Custom เมื่อต้องการเรียนรู้เพิ่มเติม ดู[รายละเอียดการกำหนดค่าฝังตัว](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details)

```javascript
var embedConfig = {
    ...
    settings: {
            layoutType: models.LayoutType.Custom,
            customLayout: {...}
    }
};
```

## <a name="object-definition"></a>นิยามของวัตถุ

```javascript
interface ICustomLayout {
  pageSize?: IPageSize;
  displayOption?: DisplayOption;
  pagesLayout?: PagesLayout;
}

enum PageSizeType {
  Widescreen,
  Standard,
  Letter,
  Custom
}
interface IPageSize {
  type: PageSizeType;
}
interface ICustomPageSize extends IPageSize {
  width?: number;
  height?: number;
}

enum DisplayOption {
  FitToPage,
  FitToWidth,
  ActualSize
}
```

- `pageSize`: ใช้ขนาดหน้า เพื่อควบคุมขนาดพื้นที่ทำงาน (นั่นคือ พื้นที่สีขาวในรายงาน)
- `displayOptions`: ค่าที่เป็นไปได้คือ: FitToWidth, FitToPage หรือ ActualSize ใช้ควบคุมวิธีการปรับขนาดพื้นที่ทำงานให้พอดีกับ iframe
- `pagesLayout`: ควบคุมเค้าโครงสำหรับแต่ละวิชวล ดู PagesLayout สำหรับรายละเอียดเพิ่มเติม

## <a name="pages-layout"></a>เค้าโครงหน้า

การนิยามวัตถุเค้าโครงหน้า คือการกำหนดเค้าโครงสำหรับแต่ละหน้า และในแต่ละหน้า คุณกำหนดเค้าโครงสำหรับแต่ละวิชวล
PageLayout ไม่มีก็ได้ ถ้าคุณไม่กำหนดเค้าโครงสำหรับหน้า เค้าโครงเริ่มต้น (ซึ่งจะได้ถูกบันทึกในรายงานแล้ว) จะถูกนำไปใช้

pagesLayout คือ การแมปจากชื่อหน้าไปยังวัตถุ PageLayout นิยาม:

```javascript
type PagesLayout = { [key: string]: IPageLayout; };
```

PageLayout ประกอบด้วยแมปเค้าโครงวิชวล ที่แมปแต่ละวิชวลไปยังวัตถุเค้าโครงวิชวล:

```javascript
interface IPageLayout {
  visualsLayout: { [key: string]: IVisualLayout; };
}
```

## <a name="visual-layout"></a>เค้าโครงวิชวล

เพื่อนิยามเค้าโครงวิชวล ส่งผ่าน ตำแหน่ง, ขนาด และสถานะมองเห็นใหม่

```javascript
interface IVisualLayout {
  x?: number;
  y?: number;
  z?: number;
  width?: number;
  height?: number;
  displayState?: IVisualContainerDisplayState;
}

interface IVisualContainerDisplayState {
  mode: VisualContainerDisplayMode;
}

enum VisualContainerDisplayMode {
  Visible,
  Hidden
}
```

- `x,y,z`: กำหนดตำแหน่งใหม่ของวิชวล
- `width`, height: กำหนดขนาดของวิชวลใหม่
- `displayState`: กำหนดมองเห็นของวิชวล

## <a name="update-layout"></a>ปรับปรุงเค้าโครง

คุณสามารถใช้เมธอด updateSettings เพื่อปรับปรุงเค้าโครงรายงานเวลาใดก็ได้ เมื่อได้โหลดรายงานแล้ว ดู[ปรับปรุงการตั้งค่า](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Update-Settings)

## <a name="code-example"></a>ตัวอย่างรหัส

```javascript
// Get models. models contains enums that can be used.
var models = window['powerbi-client'].models;

var embedConfiguration = {
    type: 'report',
    id: '5dac7a4a-4452-46b3-99f6-a25915e0fe55',
    embedUrl: 'https://app.powerbi.com/reportEmbed',
    tokenType: models.TokenType.Embed,
    accessToken: 'H4...rf',
    settings: {
            layoutType: models.LayoutType.Custom,
            customLayout: {
                pageSize: {
                    type: models.PageSizeType.Custom,
                    width: 1600,
                    height: 1200
                }
            },
            displayOption: models.DisplayOption.ActualSize,
            pagesLayout: {
                "ReportSection1" : {
                    visualsLayout: {
                        "VisualContainer1": {
                            x: 1,
                            y: 1,
                            z: 1,
                            width: 400,
                            height: 300,
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Visible
                            }
                        },
                        "VisualContainer2": {
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Hidden
                            }
                        },
                    }
                }
            }
        }
    }
};

// Get a reference to the embedded report HTML element
var embedContainer = document.getElementById('embedContainer');

// Embed the report and display it within the div container.
var report = powerbi.embed(embedContainer, embedConfiguration);
```

## <a name="see-also"></a>ดูเพิ่มเติมที่

[ฝังตัวแดชบอร์ด รายงาน และไทล์ Power BI ของคุณ](embed-sample-for-customers.md)   
[ถามชุมชน Power BI](https://community.powerbi.com/)

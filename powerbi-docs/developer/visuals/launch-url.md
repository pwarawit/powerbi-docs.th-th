---
title: สร้าง URL เปิดใช้งาน
description: บทความนี้อธิบายวิธีเปิด URL บนแท็บใหม่โดยใช้วิชวล Power BI
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 7dff03f0ad192e0598c677d41709447fbdc0688d
ms.sourcegitcommit: 549401b0e1fad15c3603fe7f14b9494141fbb100
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/14/2019
ms.locfileid: "72307327"
---
# <a name="create-a-launch-url"></a>สร้าง URL เปิดใช้งาน

ด้วยการสร้าง URL เปิดใช้งาน คุณสามารถเปิดแท็บเบราว์เซอร์ใหม่ (หรือหน้าต่าง) โดยการกำหนดงานที่แท้จริงให้กับ Power BI

## <a name="sample"></a>ตัวอย่าง

```typescript
   this.host.launchUrl('https://powerbi.microsoft.com');
```

## <a name="usage"></a>การใช้งาน

ใช้การเรียกใช้ `host.launchUrl()` API ซึ่งเปลี่ยน URL ปลายทางของคุณเป็นอาร์กิวเมนต์ของสตริง:

```typescript
this.host.launchUrl('http://some.link.net');
```

## <a name="restrictions"></a>ข้อจำกัด

* ใช้เส้นทางแบบสัมบูรณ์เท่านั้น ไม่ใช่เส้นทางแบบสัมพัทธ์ ตัวอย่างเช่น ใช้เส้นทางแบบสัมบูรณ์ เช่น `http://some.link.net/subfolder/page.html` เส้นทางแบบสัมพัทธ์ `/page.html` จะไม่ถูกเปิดขึ้น

* ปัจจุบัน รองรับเฉพาะโปรโตคอล *HTTP* และ *HTTPS* เท่านั้น หลีกเลี่ยง *FTP*, *MAILTO* และอื่นๆ

## <a name="best-practices"></a>แนวทางปฏิบัติที่ดีที่สุด

* โดยปกติแล้วจะเป็นวิธีการดีที่สุดที่จะเปิดลิงก์เพื่อเป็นการตอบสนองต่อการดำเนินการที่ชัดเจนของผู้ใช้เท่านั้น ทำให้ผู้ใช้เข้าใจได้ง่ายว่าการคลิกที่ลิงก์หรือปุ่มจะส่งผลให้เกิดการเปิดแท็บใหม่ การทริกเกอร์ `launchUrl()` การโทรโดยไม่มีการดำเนินการของผู้ใช้หรือเป็นผลข้างเคียงของการดำเนินการที่แตกต่างกันอาจทำให้ผู้ใช้เกิดความสับสนหรือหงุดหงิด

* หากลิงก์ไม่จำเป็นต่อการทำงานที่เหมาะสมของวิชวล เราขอแนะนำว่าคุณควรให้วิธีการปิดใช้งานและซ่อนลิงก์แก่ผู้เขียนรายงาน คำแนะนำนี้มีความเกี่ยวข้องโดยเฉพาะอย่างยิ่งสำหรับกรณีการใช้ Power BI แบบพิเศษ เช่น การฝังรายงานในแอปพลิเคชันบุคคลที่สามหรือการเผยแพร่ไปยังเว็บ

* หลีกเลี่ยงการทริกเกอร์ `launchUrl()` ซึ่งเรียกใช้จากภายในการวนรอบ ฟังก์ชันของวิชวล `update`หรือรหัสที่เกิดซ้ำบ่อยอื่นๆ

## <a name="a-step-by-step-example"></a>ตัวอย่างแบบทีละขั้นตอน

### <a name="add-a-link-launching-element"></a>เพิ่มองค์ประกอบการเปิดใช้ลิงก์

บรรทัดต่อไปนี้ถูกเพิ่มไปยังฟังก์ชัน`constructor`ของวิชวล:

```typescript
    this.helpLinkElement = this.createHelpLinkElement();
    options.element.appendChild(this.helpLinkElement);
```

ฟังก์ชันส่วนตัวที่สร้างและใส่องค์ประกอบของจุดยึดถูกเพิ่มเข้ามา:

```typescript
private createHelpLinkElement(): Element {
    let linkElement = document.createElement("a");
    linkElement.textContent = "?";
    linkElement.setAttribute("title", "Open documentation");
    linkElement.setAttribute("class", "helpLink");
    linkElement.addEventListener("click", () => {
        this.host.launchUrl("https://docs.microsoft.com/power-bi/developer/visuals/custom-visual-develop-tutorial");
    });
    return linkElement;
};
```

ในท้ายที่สุด รายการในไฟล์ *visual.less* จะกำหนดสไตล์สำหรับองค์ประกอบของลิงก์:

```less
.helpLink {
    position: absolute;
    top: 0px;
    right: 12px;
    display: block;
    width: 20px;
    height: 20px;
    border: 2px solid #80B0E0;
    border-radius: 20px;
    color: #80B0E0;
    text-align: center;
    font-size: 16px;
    line-height: 20px;
    background-color: #FFFFFF;
    transition: all 900ms ease;

    &:hover {
        background-color: #DDEEFF;
        color: #5080B0;
        border-color: #5080B0;
        transition: all 250ms ease;
    }

    &.hidden {
        display: none;
    }
}
```

### <a name="add-a-toggling-mechanism"></a>เพิ่มกลไกการสลับ

เมื่อต้องการเพิ่มกลไกการสลับ คุณจำเป็นต้องเพิ่มออบเจ็กต์สแตติกเพื่อให้ผู้เขียนรายงานสามารถสลับการมองเห็นองค์ประกอบลิงก์ได้ (ค่าเริ่มต้นถูกตั้งเป็น *ซ่อน*) สำหรับข้อมูลเพิ่มเติม ให้ดู[บทช่วยสอนเรื่องออบเจ็กต์สแตติก](https://microsoft.github.io/PowerBI-visuals/docs/concepts/objects-and-properties)

ออบเจ็กต์สแตติกแบบบูลีน `showHelpLink` ถูกเพิ่มไปยังรายการออบเจ็กต์ของไฟล์ *capabilities.json* ดังที่แสดงในโค้ดต่อไปนี้:

```typescript
"objects": {
    "generalView": {
            "displayName": "General View",
            "properties":
                "showHelpLink": {
                    "displayName": "Show Help Button",
                    "type": {
                        "bool": true
                    }
                }
            }
        }
    }
```

![เปิดใช้งานการสลับ URL](./media/launchurl-toggle.png)

และในฟังก์ชัน`update`ของวิชวล มีการเพิ่มบรรทัดต่อไปนี้:

```typescript
if (settings.generalView.showHelpLink) {
    this.helpLinkElement.classList.remove("hidden");
} else {
    this.helpLinkElement.classList.add("hidden");
}
```

คลาส *ที่ซ่อนอยู่* จะถูกกำหนดไว้ในไฟล์ *visual.less* เพื่อควบคุมการแสดงผลขององค์ประกอบ

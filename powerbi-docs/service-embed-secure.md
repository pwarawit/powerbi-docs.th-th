---
title: ฝังรายงานในพอร์ทัลความปลอดภัยหรือเว็บไซต์
description: Power BI ฝังคุณลักษณะผู้ใช้เปิดใช้งานได้อย่างง่ายดาย และฝังรายงานในพอร์ทัลเว็บภายใน
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2019
LocalizationGroup: Share your work
ms.openlocfilehash: bf9d7bcdf6ddaf7d0063843a5314233989b2dadd
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222239"
---
# <a name="embed-a-report-in-a-secure-portal-or-website"></a>ฝังรายงานในพอร์ทัลความปลอดภัยหรือเว็บไซต์

ด้วยใหม่**ฝัง**รายงานตัวเลือกสำหรับ Power BI คุณสามารถได้อย่างง่ายดาย และปลอดภัยฝังรายงานในพอร์ทัลเว็บภายใน พอร์ทัลเหล่านี้อาจ**ระบบคลาวด์**หรือ**โฮสต์ภายในองค์กร**เช่น SharePoint 2019 เท่านั้น รายงานที่ฝังตัวคำนึงถึงทั้งหมดรายการสิทธิ์และข้อมูลความปลอดภัยผ่าน[ระดับแถวความปลอดภัย (RLS)](service-admin-rls.md) ซึ่งจะมีไม่มีโค้ดฝังตัวลงในเว็บไซต์ใด ๆ ที่ยอมรับ URL หรือ iFrame 

การ**ฝัง**ตัวเลือกการสนับสนุน[ตัวกรอง URL](service-url-filters.md)และการตั้งค่า URL ซึ่งอนุญาตให้คุณสามารถรวมเข้ากับพอร์ทัลโดยใช้วิธีการโค้ดต่ำที่จำเป็นต้องมีเฉพาะพื้นฐาน HTML และ JavaScript ความรู้

## <a name="how-to-embed-power-bi-reports-into-portals"></a>วิธีการ**ฝัง**รายงาน Power BI ลงในพอร์ทัล

1. ใหม่**ฝัง**ตัวเลือกจะพร้อมใช้งานบนการ**ไฟล์**เมนูสำหรับรายงานในบริการ Power BI

    ![ตัวเลือกดรอปดาวน์ของตัวเลือกแบบฝังการรักษาความปลอดภัย](media/service-embed-secure/secure-embed-drop-down-menu.png)

2. เลือกคำ**ฝัง**ตัวเลือกเพื่อเปิดกล่องโต้ตอบที่มีการเชื่อมโยงและ iFrame ที่คุณสามารถใช้เพื่อฝังรายงานได้อย่างปลอดภัย

    ![ฝังกล่องโต้ตอบตัวเลือก](media/service-embed-secure/secure-embed-code-dialog.png)

3. ไม่ว่าผู้ใช้เปิด URL รายงานโดยตรง หรือหนึ่งฝังในพอร์ทัลเว็บ เข้าถึงรายงานจำเป็นต้องรับรองความถูกต้อง หน้าจอต่อไปนี้ปรากฏขึ้นถ้าผู้ใช้ได้ไม่เข้าสู่ระบบ Power BI ในเซสชันของเบราว์เซอร์ของพวกเขา เมื่อพวกเขาเลือก**เข้าสู่ระบบ**หน้าต่างเบราว์เซอร์ใหม่หรือ tab ไม่สามารถเปิดได้ มีการตรวจสอบตัวบล็อกป็อปอัพถ้าพวกเขาไม่ได้รับพร้อมท์เพื่อลงชื่อเข้าใช้

    ![โปรดลงชื่อเข้าใช้เพื่อดูรายงานนี้](media/service-embed-secure/secure-embed-sign-in.png)

4. หลังจากที่ผู้ใช้มีการลงชื่อเข้าใช้ รายงานเปิด แสดงข้อมูล และอนุญาตให้นำทางในหน้าและตั้งค่าตัวกรอง เฉพาะผู้ใช้ที่มีสิทธิ์ในการดูว่าใครสามารถดูรายงานใน Power BI ทั้งหมด[ระดับแถวความปลอดภัย (RLS)](service-admin-rls.md)กฎจะยังนำไปใช้ สุดท้ายนี้ ผู้ใช้จะต้องมีงสิทธิ์อย่างถูกต้อง – ไม่ว่าพวกเขาต้องการให้สิทธิ์การใช้งาน Power BI Pro หรือรายงานต้องอยู่ในพื้นที่ทำงานที่อยู่ในความจุ Power BI Premium ก็ตาม ผู้ใช้จำเป็นต้องลงชื่อเข้าใช้ในแต่ละครั้งที่พวกเขาเปิดหน้าต่างเบราว์เซอร์ใหม่ อย่างไรก็ตาม เมื่อลงชื่อเข้าใช้ รายงานอื่น ๆ โหลดโดยอัตโนมัติ

    ![รายงานฝังตัว](media/service-embed-secure/secure-embed-report.png)

5. เมื่อใช้ iFrame คุณอาจจำเป็นต้องแก้ไข**ความสูง**และ**ความกว้าง**เพื่อให้พอดีกับหน้าเว็บไซต์ของคุณได้

    ![ตั้งค่าความสูงและความกว้าง](media/service-embed-secure/secure-embed-size.png)

## <a name="granting-report-access"></a>สิทธิ์การเข้าถึงรายงาน

การ**ฝัง**ตัวเลือกไม่อนุญาตให้ผู้ใช้สามารถดูรายงาน ดูสิทธิ์จะถูกตั้งค่าในบริการ Power BI

ในบริการ Power BI คุณสามารถแชร์รายงานแบบฝังตัวกับผู้ใช้ที่จำเป็นต้องเข้าถึง ถ้าคุณกำลังใช้กลุ่ม Office 365 คุณสามารถสร้างรายการผู้ใช้เป็นสมาชิกพื้นที่ทำงานแอป สำหรับข้อมูลเพิ่มเติม ดูวิธีการ[จัดการพื้นที่ทำงานของแอปใน Power BI และ Office 365](service-manage-app-workspace-in-power-bi-and-office-365.md)

## <a name="licensing"></a>สิทธิ์การใช้งาน

เมื่อต้องดูรายงานแบบฝังตัว ผู้ใช้จำเป็นทั้งสองใบอนุญาต Power BI Pro หรือเนื้อหาจำเป็นต้องอยู่ในพื้นที่ทำงานที่อยู่ในการ[Power BI Premium ความจุ (EM หรือ P SKU)](service-admin-premium-purchase.md)

## <a name="customize-your-embed-experience-using-url-settings"></a>กำหนดการใช้งานการฝังตัวของคุณโดยใช้การตั้งค่า URL

คุณสามารถกำหนดประสบการณ์การใช้งานของผู้ใช้ใช้การตั้งค่าที่ป้อน URL ฝัง ใน iFrame ระบุ คุณสามารถปรับปรุงของ URL **src**ตั้งค่าได้

| คุณสมบัติ  | คำอธิบาย  |  |  |  |
|--------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|---|---|
| pageName  | คุณสามารถใช้**pageName**พารามิเตอร์สตริการตั้งค่าหน้ารายงานใดเพื่อเปิดแบบสอบถามได้ คุณสามารถค้นหาค่านี้ส่วนท้ายของ URL ของรายงานเมื่อดูรายงานในบริการ Power BI ดังที่แสดงด้านล่าง |  |  |  |
| ตัวกรอง URL  | คุณสามารถใช้[ตัวกรอง URL](service-url-filters.md)ใน URL ฝัง คุณได้รับจาก UI Power BI เพื่อกรองเนื้อหาฝังตัวได้ วิธีนี้คุณสามารถสร้างการรวมรหัสแบบต่ำด้วยการใช้งาน HTML และ JavaScript ขั้นพื้นฐานเท่านั้น  |  |  |  |

## <a name="set-which-page-opens-for-an-embedded-report"></a>ตั้งค่าหน้าซึ่งเปิดขึ้นสำหรับรายงานฝังตัว 

คุณสามารถค้นหาคำ**pageName**ค่าที่ท้ายของ URL ของรายงานเมื่อดูรายงานในบริการ Power BI ได้

1. เปิดรายงานจากบริการ Power BI ในเว็บเบราว์เซอร์ของคุณ และจากนั้น คัดลอก URL แถบที่อยู่

    ![ส่วนรายงาน](media/service-embed-secure/secure-embed-report-section.png)

2. ผนวกการตั้งค่า**pageName**เป็น URL

    ![ผนวก pageName](media/service-embed-secure/secure-embed-append-page-name.png)

## <a name="filter-report-content-using-url-filters"></a>กรองเนื้อหารายงานโดยใช้ตัวกรอง URL 

คุณสามารถใช้[ตัวกรอง URL](service-url-filters.md)เพื่อให้มุมมองรายงานที่แตกต่างกันได้ ตัวอย่างเช่น URL ด้านล่างจะกรองรายงานเพื่อแสดงข้อมูลสำหรับอุตสาหกรรมพลังงาน

ใช้ชุดของ**pageName**และ[ตัวกรอง URL](service-url-filters.md)จะทำให้มีประสิทธิภาพมากขึ้น คุณสามารถสร้างประสบการณ์การใช้งานที่ใช้ HTML และ JavaScript พื้นฐานได้

ตัวอย่าง นี่คือปุ่มคุณสามารถเพิ่มไปยังหน้า HTML:

```html
<button class="textLarge" onclick='show("ReportSection", "Energy");' style="display: inline-block;">Show Energy</button>
```

เมื่อเลือก ปุ่มเรียกใช้ฟังก์ชันการอัปเด iFrame ด้วยการอัปเดต URL ซึ่งรวมถึงตัวกรองอุตสาหกรรมพลังงาน

```javascript
function show(pageName, filterValue)

{

var newUrl = baseUrl + "&pageName=" + pageName;

if(null != filterValue && "" != filterValue)

{

newUrl += "&$filter=Industries/Industry eq '" + filterValue + "'";

}

//Assumes there’s an iFrame on the page with id=”iFrame”

var report = document.getElementById("iFrame")

report.src = newUrl;

}
```

![ตัวกรอง](media/service-embed-secure/secure-embed-filter.png)

คุณสามารถเพิ่มปุ่มได้มากเท่าที่คุณต้องการเพื่อสร้างประสบการณ์ที่กำหนดเองแบบรหัสต่ำ 

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด

* ไม่สนับสนุนผู้เยี่ยมชมภายนอก ด้วย Azure เพื่อธุรกิจ (B2B)

* ฝังการรักษาความปลอดภัยสำหรับรายงานที่เผยแพร่ไปยังบริการ Power BI

* ผู้ใช้จำเป็นต้องลงชื่อเข้าใช้เพื่อดูรายงานเมื่อใดก็ ตามพวกเขาเปิดหน้าต่างเบราว์เซอร์ใหม่

* เบราว์เซอร์บางชนิดจำเป็นต้องรีเฟรชหน้าหลังจากลงชื่อเข้าใช้ใน โดยเฉพาะอย่างยิ่งเมื่อใช้โหมด InPrivate หรือ Incognito

* ให้มีประสบการณ์การลงชื่อเข้าใช้ครั้งเดียว ใช้ฝังตัวในตัวเลือก SharePoint Online หรือสร้างการรวมแบบกำหนดเองโดยใช้[ผู้ใช้เป็นเจ้าของข้อมูล](developer/embed-sample-for-your-organization.md)วิธีฝัง 

* ความสามารถในการรับรองความถูกต้องโดยอัตโนมัติที่มาพร้อมกับการ**ฝัง**ตัวเลือกที่ไม่ทำงานกับ Power BI JavaScript API ใช้ Power BI JavaScript API ตัว[ผู้ใช้เป็นเจ้าของข้อมูล](developer/embed-sample-for-your-organization.md)วิธีฝัง 

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [วิธีการแชร์งานของคุณใน Power BI](service-how-to-collaborate-distribute-dashboards-reports.md)

* [กรองรายงานโดยใช้พารามิเตอร์สตริงของแบบสอบถามใน URL](service-url-filters.md)

* [ฝัง ด้วย web part รายงานใน SharePoint Online](service-embed-report-spo.md)

* [เผยแพร่ไปยังเว็บจาก Power BI](service-publish-to-web.md)
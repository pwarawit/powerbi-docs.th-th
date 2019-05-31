---
title: สร้างการเชื่อมโยงไปยังตำแหน่งที่ตั้งเฉพาะในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
description: เรียนรู้วิธีการสร้างการเชื่อมโยงโดยตรงไปยังแดชบอร์ด ไทล์ หรือรายงานในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ที่ระบุด้วย Uniform Resource Identifier (URI)
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 04/24/2019
ms.author: mshenhav
ms.openlocfilehash: 4e09b10e38b018f8e5572343b343a243ace3bf81
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906529"
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>สร้างการเชื่อมโยงไปยังตำแหน่งที่ตั้งเฉพาะในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
คุณสามารถใช้การเชื่อมโยงโดยตรงเข้าถึงรายการที่เฉพาะเจาะจงใน Power BI: รายงาน แดชบอร์ด และไทล์

มีสถานการณ์สองส่วนใหญ่สำหรับการใช้ลิงก์ใน Power BI Mobile: 

* เมื่อต้องเปิด Power BI จาก**ภายนอกแอ**และอยู่บนเนื้อหาที่เฉพาะเจาะจง (รายงาน/แดชบอร์ด/แอ) ซึ่งมักเป็นสถานการณ์การรวม เมื่อคุณต้องการเปิด Power BI Mobile จากแอปอื่น 
* เมื่อต้องการ**นำทาง**ภายใน Power BI นี่คือโดยปกติแล้วเมื่อคุณต้องการสร้างการนำทางแบบกำหนดเองใน Power BI


## <a name="use-links-from-outside-of-power-bi"></a>ใช้การเชื่อมโยงจากภายนอก Power BI
เมื่อคุณใช้การเชื่อมโยงจากภายนอกแอป Power BI คุณต้องการตรวจสอบให้แน่ใจว่า ได้จะเปิด โดยแอ และ ถ้าแอไม่ได้ติดตั้ง บนอุปกรณ์ จาก นั้น เพื่อให้ผู้ใช้สามารถติดตั้ง เราได้สร้างรูปแบบพิเศษลิงก์เพื่อสนับสนุนว่า รูปแบบนี้เชื่อมโยง จะตรวจสอบ ว่าอุปกรณ์ใช้แอปเพื่อเปิดลิงก์ ถ้าไม่ได้ติดตั้งแอปบนอุปกรณ์ จะมีผู้ใช้ไปยังร้านค้าเพื่อให้

ลิงก์ควรเริ่มต้น ด้วยต่อไปนี้  
```html
https://app.powerbi.com/Redirect?[**QUERYPARAMS**]
```

> [!IMPORTANT]
> ถ้าเนื้อหาของคุณถูกโฮสต์ในศูนย์ข้อมูลพิเศษเช่น Goverment จีน และอื่น ๆ ลิงก์ควรเริ่ม ด้วยที่อยู่ด้านขวาของ Power BI เช่น`app.powerbigov.us`หรือ`app.powerbi.cn`   
>


การ**PARAMS แบบสอบถาม**คือ:
* **การดำเนินการ**(บังคับ) = OpenApp / OpenDashboard / OpenTile / OpenReport
* **appId** =ถ้าคุณต้องการเปิดรายงานหรือแดชบอร์ดที่เป็นส่วนหนึ่งของแอป 
* **groupObjectId** =ถ้าคุณต้องการเปิดรายงานหรือแดชบอร์ดที่เป็นส่วนหนึ่งของพื้นที่ทำงาน (แต่ไม่ฉันพื้นที่ทำงาน)
* **dashboardObjectId** = ID ออปเจ็กต์ของแดชบอร์ด (ถ้าการดำเนินการคือ OpenDashboard หรือ OpenTile)
* **reportObjectId** = ID ออปเจ็กต์ของรายงาน (ถ้าการดำเนินการคือ OpenReport)
* **tileObjectId** = ID ออบเจ็กต์ไทล์ (ถ้าการดำเนินการคือ OpenTile)
* **reportPage** =ถ้าคุณต้องการเปิดรายงานเฉพาะส่วน (ถ้าการดำเนินการคือ OpenReport)
* **ctid** = ID องค์กรรายการ (ที่เกี่ยวข้องสำหรับสถานการณ์สมมติ B2B ซึ่งสามารถละเว้นได้ถ้ารายการอยู่ในองค์กรของผู้ใช้)

**ตัวอย่าง:**

* ลิงก์เปิดแอป 
  ```html
  https://app.powerbi.com/Redirect?action=OpenApp&appId=appidguid&ctid=organizationid
  ```

* เปิดแดชบอร์ดที่เป็นส่วนหนึ่งของแอป 
  ```html
  https://app.powerbi.com/Redirect?action=OpenDashboard&appId=**appidguid**&dashboardObjectId=**dashboardidguid**&ctid=**organizationid**
  ```

* เปิดรายงานที่เป็นส่วนหนึ่งของพื้นที่ทำงาน
  ```html
  https://app.powerbi.com/Redirect?Action=OpenReport&reportObjectId=**reportidguid**&groupObjectId=**groupidguid**&reportPage=**ReportSectionName**
  ```

### <a name="how-to-get-the-right-link-format"></a>วิธีการรับรูปแบบลิงก์ด้านขวา

#### <a name="links-of-apps-and-items-in-app"></a>ลิงก์แอปและรายการในแอป

สำหรับ**แอป และรายงาน และแดชบอร์ดที่เป็นส่วนหนึ่งของแอ**คือวิธีง่ายที่สุดในการรับลิงก์ ไปยังพื้นที่ทำงานแอป และเลือก "อัปเดตแอปฯ" ซึ่งจะเปิดประสบการณ์การใช้งาน "เผยแพร่แอ" และในแท็บ Access คุณจะพบการ**ลิงก์**ส่วน ขยายว่า ส่วนและคุณจะเห็นรายการของแอป และเนื้อหาทั้งหมดลิงก์ที่สามารถใช้เพื่อเข้าถึงได้โดยตรง

![Power BI เผยแพร่ลิงก์แอป ](./media/mobile-apps-links/mobile-link-copy-app-links.png)

#### <a name="links-of-items-not-in-app"></a>ลิงก์รายการไม่ได้อยู่ในแอป 

สำหรับรายงานและแดชบอร์ดที่ไม่เป็นส่วนหนึ่งของแอป คุณจำเป็นต้องแยกรหัสจาก URL ของรายการ

ตัวอย่าง เพื่อค้นหาอักขระ 36 **แดชบอร์ด**ID วัตถุ การนำทางไปยังแดชบอร์ดนั้นในบริการ Power BI 

```html
https://app.powerbi.com/groups/me/dashboards/**dashboard guid comes here**?ctid=**organization id comes here**`
```

เมื่อต้องการค้นหาอักขระ 36 **รายงาน**ID วัตถุ การนำทางไปยังรายงานในบริการ Power BI
นี่คือตัวอย่างของรายงานจาก "My Workspace"

```html
https://app.powerbi.com/groups/me/reports/**report guid comes here**/ReportSection3?ctid=**organization id comes here**`
```
URL ด้านบนยังประกอบด้วยหน้ารายงานที่ระบุ **"ReportSection3"**

นี่คือตัวอย่างของรายงานจากพื้นที่ทำงาน (ไม่ My Workspace)

```html
https://app.powerbi.com/groups/**groupid comes here**/reports/**reportid comes here**/ReportSection1?ctid=**organizationid comes here**
```

## <a name="use-links-inside-power-bi"></a>ใช้การเชื่อมโยงภายใน Power BI

ลิงก์ภายใน Power BI กำลังทำงานในแอปสำหรับอุปกรณ์เคลื่อนที่แน่นอนเช่นเดียวกับบริการ Power BI

ถ้าคุณต้องการเพิ่มการเชื่อมโยงกับรายงานของคุณที่ชี้ไปยังอีกรายการ Power BI คุณสามารถเพียงแค่คัดลอกที่รายการ URL จากแถบที่อยู่เบราว์เซอร์ อ่านเพิ่มเติมเกี่ยวกับ[วิธีการเพิ่มไฮเปอร์ลิงก์ไปยังกล่องข้อความในรายงาน](https://docs.microsoft.com/power-bi/service-add-hyperlink-to-text-box)

## <a name="use-report-url-with-filter"></a>ใช้ URL ของรายงาน ด้วยตัวกรอง
เหมือนกับบริการ Power BI, Power BI Mobile apps ยังสนับสนุน URL รายงานที่ประกอบด้วยพารามิเตอร์แบบสอบถามตัวกรอง คุณสามารถเปิดรายงานในแอป Power BI Mobile และกรองเพื่อระบุสถานะ ตัวอย่าง URL นี้เปิดรายงานยอดขาย และกรองตามเขต

```html
https://app.powerbi.com/groups/me/reports/**report guid comes here**/ReportSection3?ctid=**organization id comes here**&filter=Store/Territory eq 'NC'
```

อ่านเพิ่มเติมบน[วิธีการสร้างพารามิเตอร์แบบสอบถามเพื่อกรองรายงาน](https://docs.microsoft.com/power-bi/service-url-filters)

## <a name="next-steps"></a>ขั้นตอนถัดไป
คำติชมของคุณจะช่วยให้เราตัดสินใจว่าสิ่งใดควรดำเนินการในอนาคต ดังนั้นอย่าลืมลงคะแนนให้กับคุณลักษณะอื่นๆ ที่คุณต้องการเห็นในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ 

* [แอป Power BI สำหรับอุปกรณ์เคลื่อนที่](mobile-apps-for-mobile-devices.md)
* ติดตาม@MSPowerBIบน Twitter
* เข้าร่วมการสนทนาที่[ชุมชน Power BI](http://community.powerbi.com/)
* [Power BI คืออะไร](../../power-bi-overview.md)


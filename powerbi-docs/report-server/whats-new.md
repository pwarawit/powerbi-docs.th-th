---
title: มีอะไรใหม่ใน Power BI Report Server
description: เรียนรู้ว่ามีอะไรใหม่ใน Power BI Report Server ส่วนนี้จะครอบคลุมถึงพื้นที่คุณลักษณะเฉพาะหลักๆ และถูกอัปเดตเมื่อมีการเผยแพร่รายการใหม่
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/22/2019
ms.openlocfilehash: 27f08b9922508866f190fc41848cb77031a91c6b
ms.sourcegitcommit: 5e83fa6c93a0bc6599f76cc070fb0e5c1fce0082
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/13/2019
ms.locfileid: "56216803"
---
# <a name="whats-new-in-power-bi-report-server"></a>มีอะไรใหม่ใน Power BI Report Server

เรียนรู้ว่ามีอะไรใหม่ใน Power BI Report Server บทความนี้เป็นเรื่องพีเจอร์หลัก ๆ และจะได้รับการอัปเดตเมื่อมีการเผยแพร่ฟีเจอร์ใหม่

เมื่อต้องการดาวน์โหลด Power BI Report Server เวอร์ชันล่าสุดและ Power BI Desktop ซึ่งปรับให้เหมาะสมที่สุดกับ Power BI Report Server ไปที่ [การรายงานภายในองค์กรกับ Power BI Report Server](https://powerbi.microsoft.com/report-server/)

สำหรับข้อมูล "มีอะไรใหม่" ที่เกี่ยวข้อง ดู:

* [มีอะไรใหม่ในบริการ Power BI](../service-whats-new.md)
* [มีอะไรใหม่ใน Power BI Desktop](../desktop-latest-update.md)
* [มีอะไรใหม่ในแอปอุปกรณ์เคลื่อนที่สำหรับ Power BI](../consumer/mobile/mobile-whats-new-in-the-mobile-apps.md)

## <a name="january-2019"></a>มกราคม 2019

สนับสนุนคุณลักษณะเหล่านี้ในรายงาน Power BI:

[**ความปลอดภัยระดับแถว** ](row-level-security-report-server.md)การตั้งค่าความปลอดภัยระดับแถว (RLS) กับเซิร์ฟเวอร์รายงาน Power BI สามารถจำกัดการเข้าถึงข้อมูลสำหรับผู้ใช้ที่กำหนด ตัวกรองจำกัดการเข้าถึงข้อมูลในระดับแถว และคุณสามารถกำหนดตัวกรองภายในบทบาทได้

[**ขยาย และยุบบนส่วนหัวของแถวเมทริกซ์** ](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2018-feature-summary/#expandCollapse)เราได้เพิ่มความสามารถในการขยายและยุบส่วนหัวของแถวแต่ละแถวซึ่งเป็นหนึ่งในคุณสมบัติด้านวิชวลที่ได้รับการร้องขอมากที่สุด

[**คัดลอก และวางระหว่างไฟล์.pbix** ](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2018-feature-summary/#copyPaste)คุณสามารถคัดลอกวิชวลระหว่างไฟล์ .pbix จากเมนูบริบทของวิชวลหรือด้วยแป้นพิมพ์ลัด Ctrl + C มาตรฐาน และวางลงในรายงานอื่นด้วย Ctrl + V

[**เส้นบอกแนวสำหรับการจัดแนวแบบสมาร์ท** ](https://powerbi.microsoft.com/blog/power-bi-desktop-december-2018-feature-summary/#smartGuides)คุณเห็นเส้นบอกแนวสำหรับการจัดแนวแบบสมาร์ทเมื่อย้ายวัตถุบนหน้ารายงานของคุณ เช่น คุณเห็นใน PowerPoint เพื่อช่วยให้คุณสามารถจัดแนวทุกอย่างบนหน้าของคุณได้ คุณเห็นเส้นบอกแนวแบบสมาร์ททุกครั้งที่คุณลาก หรือปรับขนาดบางอย่างบนหน้าของคุณ เมื่อคุณย้ายวัตถุที่อยู่ใกล้วัตถุอื่นมันจะถูกจัดวางในตำแหน่งที่สอดคล้องกับวัตถุอื่น

**คุณลักษณะความสามารถในการเข้าถึงได้**มีรายการคุณลักษณะความสามารถในการเข้าถึงได้ที่มากเกินไป: ตัวอย่างเช่น [สนับสนุนการเข้าถึงบานหน้าต่างรายการเขตข้อมูล](https://powerbi.microsoft.com/blog/power-bi-desktop-december-2018-feature-summary/#fieldList) บานหน้าต่างรายการเขตข้อมูลจะสามารถเข้าถึงได้เต็มรูปแบบ คุณสามารถนำทางไปรอบ ๆ บานหน้าต่างโดยใช้เพียงแป้นพิมพ์และโปรแกรมอ่านหน้าจอของคุณและใช้เมนูบริบทเพื่อเพิ่มเขตข้อมูลลงในหน้ารายงานของคุณ

### <a name="administrator-settings"></a>การตั้งค่าโดยผู้ดูแลระบบ

ผู้ดูแลระบบสามารถตั้งค่าคุณสมบัติต่อไปนี้ในคุณสมบัติขั้นสูง SSMS สำหรับเซิร์ฟเวอร์ฟาร์ม:

**AllowedResourceExtensionsForUpload** กำหนดส่วนขยายของทรัพยากรที่สามารถอัปโหลดไปยังเซิร์ฟเวอร์รายงาน ส่วนขยายสำหรับชนิดไฟล์ที่มีอยู่ภายใน เช่น &ast;.rdl และ&ast;.pbix ไม่จำเป็นต้องรวม ค่าเริ่มต้นคือ “&ast;, &ast;.xml, &ast;.xsd, &ast;.xsl, &ast;.png, &ast;.gif, &ast;.jpg, &ast;.tif, &ast;.jpeg, &ast;.tiff, &ast;.bmp, &ast;.pdf, &ast;.svg, &ast;.rtf, &ast;.txt, &ast;.doc, &ast;.docx, &ast;.pps, &ast;.ppt, &ast;.pptx” 

**SupportedHyperlinkSchemes** ตั้งค่ารายการที่คั่นด้วยเครื่องหมายจุลภาคของโครงร่าง URI ที่อนุญาตให้กำหนดบนแอ็คชันการเชื่อมโยงหลายมิติที่อนุญาตให้เรนเดอร์หรือ“ &ast;” เพื่อเปิดใช้งานโครงร่างการเชื่อมโยงหลายมิติทั้งหมด ตัวอย่าง ตั้งค่า "http, https" อนุญาตให้เชื่อมโยงหลายมิติไปยัง "https://www contoso.com" แต่จะเป็นเอาเชื่อมโยงหลายมิติไปยัง "mailto:bill@contoso.com" หรือ "javascript:window.open ('www.contoso.com', '_blank')" ออก ค่าเริ่มต้นในตอนนี้คือ “&ast;”

## <a name="august-2018"></a>สิงหาคม 2018

สิงหาคม 2018 เป็นเดือนที่มีการเพิ่มฟีเจอร์ใหม่หลายตัวในเวอร์ชัน Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI ต่อไปนี้จะเป็นการแจกแจงข้อมูลตามพื้นที่:

- [การรายงาน](#reporting)
- [การวิเคราะห์](#analytics)
- [สร้างรูปแบบข้อมูล](#modeling)

### <a name="highlights-of-the-august-2018-release"></a>ประเด็นสำคัญของรุ่นเผยแพร่เดือนสิงหาคม 2018

จากฟีเจอร์ใหม่หลายตัวที่มีให้บริการทั้งหมด ฟีเจอร์เหล่านี้มีความโดดเด่นเป็นที่น่าสนใจโดยเฉพาะ สำหรับข้อมูลเพิ่มเติม ดู[โพสต์ในบล็อก](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/)

#### <a name="report-theming"></a>ธีมรายงาน

มีการเพิ่มธีมรายงานในเซิร์ฟเวอร์รายงาน Power BI รุ่นที่เผยแพร่ในเดือนสิงหาคม 2018 ซึ่งจะทำให้คุณสามารถให้สีรายงานของคุณได้อย่างรวดเร็วเพื่อให้เข้ากับธีมหรือตราสินค้าของบริษัท เมื่อคุณนำเข้าธีม แผนภูมิทั้งหมดของคุณจะอัปเดตโดยอัตโนมัติเพื่อใช้สีของธีม และคุณสามารถเข้าถึงสีของธีมได้จากจานสี คุณสามารถอัปโหลดไฟล์ธีมโดยใช้ตัวเลือก**นำเข้าธีม**ใต้ปุ่ม**สลับธีม**

ไฟล์ธีมเป็นไฟล์ JSON ที่มีสีคุณต้องการให้เราใช้ในรายงานของคุณพร้อมกับการจัดรูปแบบในค่าเริ่มต้นที่คุณต้องการนำไปใช้กับภาพทั้งหมด
นี่คือตัวอย่างธีม JSON อย่างง่าย ๆ ที่เพิ่งอัปเดตสีเริ่มต้นของรายงาน:

```json
{
"name": "waveform",
"dataColors": [ "#31B6FD", "#4584D3", "#5BD078", "#A5D028", "#F5C040", "#05E0DB", "#3153FD", "#4C45D3", "#5BD0B0", "#54D028", "#D0F540", "#057BE0" ],
"background":"#FFFFFF",
"foreground": "#F2F2F2",
"tableAccent":"#5BD078"
}
```

#### <a name="conditional-formatting-by-a-different-field"></a>การจัดรูปแบบตามเงื่อนไขด้วยเขตข้อมูลอื่น

ความสามารถในการจัดรูปแบบคอลัมน์ตามเขตข้อมูลอื่นคือการปรับปรุงที่สำคัญหนึ่งของการจัดรูปแบบตามเงื่อนไข

#### <a name="conditional-formatting-by-values"></a>การจัดรูปแบบตามเงื่อนไขด้วยค่า

การจัดรูปแบบตามเงื่อนไขชนิดใหม่อย่างหนึ่งคือ**จัดรูปแบบด้วยค่าของเขตข้อมูล** การจัดรูปแบบด้วยค่าเขตข้อมูลช่วยให้คุณใช้หน่วยวัดหรือคอลัมน์ที่ระบุสีด้วยค่า รหัสฐานสิบหกหรือชื่อ และใช้สีนั้นเป็นสีพื้นหลังหรือสีแบบอักษร

#### <a name="report-page-tooltips"></a>เคล็ดลับเครื่องมือหน้ารายงาน

ฟีเจอร์เคล็ดลับเครื่องมือหน้ารายงานจะรวมอยู่ในอับเดตเดือนสิงหาคม 2018 ของเซิร์ฟเวอร์รายงาน Power BI ฟีเจอร์นี้ช่วยให้คุณออกแบบหน้ารายงานเพื่อใช้เป็นเคล็ดลับเครื่องมือแบบกำหนดเองสำหรับภาพอื่น ๆ ในรายงานของคุณ

#### <a name="log-axis-improvements"></a>การปรับปรุงแกนลอการิทึม

เราได้ปรับปรุงแกนลอการิทึมในแผนภูมิ Cartesian ของคุณ ในตอนนี้ คุณควรสามารถเลือกมาตราส่วนลอการิทึมสำหรับแกนตัวเลขของแผนภูมิ Cartesian รวมถึงแผนภูมิผสม เมื่อคุณมีข้อมูลที่เป็นบวกทั้งหมด หรือเป็นลบทั้งหมด

#### <a name="sap-hana-sso-direct-query"></a>คิวรีโดยตรง SAP HANA SSO

ขณะนี้ คิวรีโดยตรง SAP HANA SSO ด้วย Kerberos พร้อมใช้งานในรายงาน Power BI

>[!Note]
>สถานการณ์นี้ใช้ได้เมื่อถือว่า SAP HANA เป็นแหล่งข้อมูลเชิงสัมพันธ์กับรายงานที่คุณได้สร้างไว้ใน Power BI Desktop เท่านั้น  เมื่อต้องการเปิดใช้งาน คิวรีโดยตรง SAP HANA SSO ใน Power BI Desktop ในเมนู DirectQuery ภายใต้ตัวเลือก เลือก "ถือ SAP HANA เป็นแหล่งข้อมูลเชิงสัมพันธ์" และคลิกตกลง

#### <a name="custom-visuals"></a>ภาพที่กำหนดเอง

- เวอร์ชันของ API ที่ส่งไปพร้อมกับรุ่นนี้คือ 1.13.0

- ตอนนี้ ภาพแบบกำหนดเองสามารถกลับไปเป็นรุ่นก่อนหน้าที่เข้ากันได้กับรุ่นปัจจุบันของ API ของเซิร์ฟเวอร์ (ถ้ามี)

### <a name="reporting"></a>การรายงาน 

- [ธีมรายงาน](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#theming)
- [ปุ่มเพื่อดำเนินการกระทำ](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#buttons)
- [ลักษณะเส้นของแผนภูมิผสม](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLines)
- [ปรับปรุงการจัดเรียงในค่าเริ่มต้นสำหรับภาพ](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sort)
- [ตัวแบ่งส่วนข้อมูลตัวเลข](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#numericSlicer)
- [ซิงค์ตัวแบ่งส่วนข้อมูลขั้นสูง](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerSync)
- [ปรับปรุงแกนลอการิทึ่ม](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#logAxis)
- [ตัวเลือกป้ายชื่อข้อมูลสำหรับแผนภูมิกรวย](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#funnelChart)
- [ตั้งค่าความกว้างของเส้นให้เป็นศูนย์](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#lineStroke)
- [สนับสนุนความคมชัดสูงสำหรับรายงาน](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#highContrast)
- [ตัวควบคุมรัศมีของโดนัท](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#donutRadius)
- [ตัวควบคุมตำแหน่งป้ายกำกับรายละเอียดของแผนภูมิวงกลมและโดนัท](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#detailLabels)
- [จัดรูปแบบป้ายข้อมูลแยกต่างหากสำหรับแต่ละหน่วยวัดในแผนภูมิผสม](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#comboLabels)
- [หัวข้อภาพใหม่ที่มีความยืดหยุ่นและมีการจัดรูปแบบมากขึ้น](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#visualHeader)
- [จัดรูปแบบวอลเปเปอร์](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#wallpaper)
- [เคล็ดลับเครื่องมือสำหรับตารางและเมทริกซ์](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tableTooltips)
- [ปิดเคล็ดลับเครื่องมือสำหรับภาพ](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#tooltips)
- [การเข้าถึงตัวแบ่งส่วนข้อมูล](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicerAccessibility)
- [ปรับปรุงบานหน้าต่างจัดรูปแบบ](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#formattingPane)
- [สนับสนุนรูปแบบขั้นบรรทัดสำหรับแผนภูมิเส้นและแผนภูมิผสม](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#steppedLine)
- [ปรับปรุงการใช้งานการเรียงลำดับ](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#sorting)
- [พิมพ์รายงานด้วยการส่งออกเป็น PDF (ใน Power BI Desktop)](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#print)
- [สร้างกลุ่มที่คั่นหน้า](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#bookmarks)
- [รายงานตัวแบ่งส่วนข้อมูลใหม่](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#slicer)
- [เคล็ดลับเครื่องมือหน้ารายงาน](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#reportPageTooltips)

### <a name="analytics"></a>การวิเคราะห์

- [ฟังก์ชัน DAX ใหม่: COMBINEVALUES()](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#combineValues)
- [เข้าถึงรายละเอียดหน่วยวัด](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#measureDrillthrough)
- [จัดรูปแบบตามเงื่อนไขด้วยเขตข้อมูลอื่น](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingField)
- [จัดรูปแบบตามเงื่อนไขด้วยค่า](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#conditionalFormattingValue)

### <a name="modeling"></a>การวางรูปแบบ

- [กรองและเรียงลำดับในมุมมองข้อมูล](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#filterAndSort)
- [ปรับปรุงตำแหน่งการจัดรูปแบบ](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#locale)
- [ประเภทข้อมูลสำหรับหน่วย วัด](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dataCategory)
- [ฟังก์ชัน DAX ทางสถิติ](https://powerbi.microsoft.com/blog/power-bi-report-server-update-august-2018/#dax)

## <a name="may-2018"></a>พฤษภาคม 2018

### <a name="configure-power-bi-ios-mobile-apps-for-report-servers-remotely"></a>กำหนดค่าการเข้าถึงเซิร์ฟเวอร์รายงานจากระยะไกล สำหรับแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ iOS

ในฐานะที่เป็นผู้ดูแลระบบ IT คุณสามารถใช้เครื่องมือ MDM ขององค์กรคุณเพื่อกำหนดค่าการเข้าถึงเซิร์ฟเวอร์รายงาน ของแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ iOS จากระยะไกลได้ ดู [กำหนดค่าแอปสำหรับอุปกรณ์เคลื่อนที่ iOS ของ Power BI สำหรับการเข้าถึงไปยังเซิร์ฟเวอร์รายงานจากระยะไกล](configure-powerbi-mobile-apps-remote.md) สำหรับรายละเอียด

## <a name="march-2018"></a>มีนาคม 2018

ในเดือนมีนาคม 2018 จะเห็นได้ว่า มีคุณลักษณะใหมหลายอย่างมากที่เพิ่มเข้ามาใน Power BI Desktop เวอร์ชันที่ปรับให้เหมาะสำหรับ Power BI Report Server ต่อไปนี้จะเป็นการแจกแจงข้อมูลตามพื้นที่:

- [การแสดงผลด้วยภาพ](#visuals-updates)
- [การรายงาน](#reporting)
- [การวิเคราะห์](#analytics)
- [ประสิทธิภาพการทำงาน](#performance)
- [เซิร์ฟเวอร์รายงาน](#report-server)
- [อื่นๆ](#other-improvements)

### <a name="highlights-of-the-march-2018-release"></a>ประเด็นสำคัญของรุ่นเผยแพร่เดือนมีนาคม 2018

จากฟีเจอร์ใหม่หลายตัวที่มีให้บริการทั้งหมด ฟีเจอร์เหล่านี้มีความโดดเด่นเป็นที่น่าสนใจโดยเฉพาะ

#### <a name="rule-based-conditional-formatting-for-table-and-matrixhttpspowerbimicrosoftcomblogpower-bi-desktop-november-2017-feature-summaryconditionalformatting"></a>[การจัดรูปแบบตามเงื่อนไขตามกฏสำหรับตารางและเมทริกซ์](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#conditionalFormatting)

สร้างกฎเพื่อใส่สีีพื้นหลังหรือแบบอักษรของคอลัมน์ตามเงื่อนไขโดยเป็นไปตามตรรกะธุรกิจเฉพาะในตารางหรือเมทริกซ์ของคุณ

#### <a name="show-and-hide-pageshttpspowerbimicrosoftcomblogpower-bi-desktop-january-2018-feature-summaryhidepages"></a>[แสดงหรือซ่อนหน้า](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#hidePages)

คุณต้องการให้ผู้อ่านสามารถเข้าถึงรายงานของคุณ แต่มีบางหน้ายังไม่ค่อยเสร็จสมบูรณ์ ในตอนนี้ คุณสามารถซ่อนหน้าเหล่านี้ไว้จนกว่าจะพร้อม หรือคุณสามารถซ่อนหน้าเหล่านี้จากการนำทางปกติ และผู้อ่านสามารถเข้าถึงหน้าโดยการสร้างบุ๊กมาร์กหรือเข้าถึงรายละเอียด

#### <a name="bookmarkinghttpspowerbimicrosoftcomblogpower-bi-desktop-march-2018-feature-summarybookmarking"></a>[การสร้างบุ๊กมาร์ก](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#bookmarking)

เมื่อพูดถึงการสร้างบุ๊กมาร์ก จะมีการสร้างบุ๊กมาร์กเพื่อบอกเล่าเรื่องราวพร้อมกับข้อมูลในรายงานของคุณ

- [การเน้นไขว้สำหรับบุ๊กมาร์ก](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkCrossHighlighting): บุ๊กมาร์กจะรักษาและแสดงสถานะเน้นไขว้ของหน้ารายงานในเวลาที่คุณสร้างบุ๊กมาร์ก
- [ความยืดหยุ่นของบุ๊กมาร์กเพิ่มเติม](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#bookmarkFlexibility): บุ๊กมาร์กสะท้อนให้เห็นคุณสมบัติที่คุณตั้งค่าในรายงานและมีผลต่อการแสดงผลด้วยภาพที่เลือกเท่านั้น

#### <a name="multi-select-data-points-across-multiple-chartshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarycrosshighlight"></a>[จุดข้อมูลที่เลือกได้หลายจุดในหลายแผนภูมิ](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#crosshighlight)

เลือกจุดข้อมูลหลายจุดในหลายแผนภูมิและมีการใช้การกรองแบบไขว้กับทั้งหน้า

#### <a name="sync-slicers-across-multiple-pages-of-your-reporthttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summarysyncslicers"></a>[ซิงค์ตัวแบ่งส่วนข้อมูลในหลาย ๆ หน้ารายงานของคุณ](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#syncSlicers)

ตัวแบ่งส่วนข้อมูลสามารถนำไปใช้กับรายงานหนึ่งหน้า สองหน้าหรือมากกว่านั้น

#### <a name="quick-measureshttpspowerbimicrosoftcomblogpower-bi-desktop-february-2018-feature-summaryquickmeasures"></a>[หน่วยวัดด่วน](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#quickMeasures) 

สร้างหน่วยวัดใหมตามหน่วยวัดที่มีอยู่แล้วและคอลัมน์ตัวเลขในตาราง

#### <a name="drilling-down-filters-other-visualshttpspowerbimicrosoftcomblogpower-bi-desktop-december-feature-summarydrillfiltersothervisuals"></a>[การใช้ตัวกรองเจาะลึกลงในการแสดงผลด้วยภาพอื่น ๆ ](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)

เมื่อคุณเจาะลึกลงไปในประเภททกำหนดในการแสดงผลด้วยแบบหนึ่ง คุณจะสามารถกรองการแสดงผลด้วยภาพทั้งหมดบนหน้าตามประเภทเดียวกันนั้น

### <a name="visuals-updates"></a>การอัปเดตการแสดงผลด้วยภาพ

- [การจัดแนวเซลล์สำหรับตารางและเมทริกซ์](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#alignment)
- [หน่วยแสดงและการควบคุมความแม่นยำสำหรับคอลัมน์ตารางและเมทริกซ์](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#displayUnits)
- [ป้ายชื่อข้อมูลที่ยาวเกินไปสำหรับแผนภูมิแท่งและคอลัมน์แผนภูมิ](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#overflow)
- [ควบคุมสีพื้นหลังของป้ายชื่อข้อมูลสำหรับการแสดงผลด้วยภาพแบบคาร์ทีเซียนและแผนที่](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#dataLabelBackground)
- [ตัวควบคุมช่องว่างภายในแท่ง/คอลัมน์](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#padding)
- [เพิ่มพื้นที่ที่ใช้สำหรับป้ายชื่อแกนในแผนภูมิ](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#axisSize)
- [กระจายการแสดงผลด้วยภาพจากการจัดกลุ่มแกน x และ y](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#scatterChart)
- [การสุ่มตัวอย่างความหนาแน่นสูงสำหรับแผนที่ตามละติจูดและลองจิจูด](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#highDensityMaps)
- [ตัวแบ่งส่วนข้อมูลแบบตอบสนอง](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#responsive)
- [เพิ่มวันที่ของจุดยึดตัวแบ่งส่วนข้อมูลวันที่แบบสัมพัทธ์](https://powerbi.microsoft.com/blog/power-bi-desktop-january-2018-feature-summary/#anchorDate)

### <a name="reporting"></a>การรายงาน

- [ปิดส่วนหัวของการแสดงผลด้วยภาพในโหมดอ่านสำหรับรายงานอ่าน](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualHeader)
- [ตัวเลือกรายงานสำหรับแหล่งข้อมูลแบบช้า](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#slowDataSource)
- [การวางตำแหน่งการแสดงผลด้วยภาพที่เป็นค่าเริ่มต้นที่ดียิ่งขึ้น](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#visualPlacement)
- [ควบคุมการจัดลำดับการแสดงผลด้วยภาพผ่านบานหน้าต่างการเลือก](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#selectionPane)
- [ล็อกวัตถุบนรายงานของคุณ](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#lock)
- [ค้นหาบานหน้าต่างการจัดรูปแบบและการวิเคราะห์](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#search)
- [บานหน้าต่างคุณสมบัติเขตข้อมูลและคำอธิบายเขตข้อมูล](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#fieldPropertiesPane)

### <a name="analytics"></a>การวิเคราะห์

- [UTCNOW() และ UTCTODAY()](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#utcDAX)
- [ทำเครื่องหมายตารางวันที่แบบกำหนดเอง](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#customDateTable)
- [ใช้ตัวกรองเจาะลึกลงในการแสดงผลด้วยภาพอื่น ๆ ](https://powerbi.microsoft.com/blog/power-bi-desktop-december-feature-summary/#drillFiltersOtherVisuals)
- [การจัดรูปแบบระดับเซลล์สำหรับแบบจำลอง AS หลายมิติสำหรับการ์ดแบบหลายแถว](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#cellLevelFormatting)

### <a name="performance"></a>ประสิทธิภาพการทำงาน

- [การปรับปรุงประสิทธิภาพการกรอง](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#filtering)
- [การปรับปรุงประสิทธิภาพ DirectQuery](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#dqPerf)
- [เปิดและบันทึกการปรับปรุงประสิทธิภาพการทำงาน](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#savePerf)
- [การปรับปรุง “แสดงรายการโดยไม่มีข้อมูล”](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#showItemsWithNoData)

### <a name="report-server"></a>เซิร์ฟเวอร์รายงาน

#### <a name="export-to-accessible-pdf"></a>ส่งออกเป็น PDF ที่สามารถเข้าถึงได้

เมื่อคุณส่งออกรายงานแบบแบ่งหน้าแล้ว (RDL) เป็น PDF ในตอนนี้ คุณก็สามารถรับไฟล์ PDF ที่สามารถเข้าถึงได้/ติดแท็กไว้ ซึ่งมีขนาดใหญ่ แต่อ่านและนำทางได้ง่ายขึ้นสำหรับโปรแกรมอ่านหน้าจอและเทคโนโลยีช่วยเหลืออื่น ๆ คุณเปิดใช้งาน PDF ที่สามารถเข้าถึงได้โดยการตั้งค่า **AccessiblePDF** การตั้งค่าข้อมูลอุปกรณให้เป็น **True** ดู[การตั้งค่าข้อมูลอุปกรณ์ PDF](https://docs.microsoft.com/sql/reporting-services/pdf-device-information-settings)และ[การเปลี่ยนแปลงการตั้งค่าข้อมูลอุปกรณ์](https://docs.microsoft.com/sql/reporting-services/customize-rendering-extension-parameters-in-rsreportserver-config#changing-device-information-settings)

### <a name="other-improvements"></a>การปรับปรุงอื่น ๆ

- [การปรับปรุงโดยเพิ่มคอลัมน์จากตัวอย่าง](https://powerbi.microsoft.com/blog/power-bi-desktop-november-2017-feature-summary/#addColumnFromExamples)
- [ลิงก์ด่วนของบริการให้คำปรึกษา](https://powerbi.microsoft.com/blog/power-bi-desktop-february-2018-feature-summary/#consultingServices)
- [การรายงานข้อผิดพลาดทปรับปรุงแล้ว](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#errors)
- [ดูข้อผิดพลาดก่อนหน้านี้ที่คุณพบ](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#viewErrors)

## <a name="october-2017"></a>ตุลาคม 2017

### <a name="power-bi-report-data-sources"></a>แหล่งข้อมูลรายงาน Power BI

รายงาน Power BI ใน Power BI Report Server สามารถเชื่อมต่อกับแหล่งข้อมูลที่หลากหลายได้ คุณสามารถนำเข้าข้อมูลและการจัดกำหนดการการรีเฟรชข้อมูลหรือสอบถามได้โดยตรงโดยใช้ DirectQuery หรือการเชื่อมต่อแบบสดกับ SQL Server Analysis Services ดูรายการแหล่งข้อมูลที่สนับสนุนการรีเฟรชตามกำหนดการและแหบ่งข้อมูลเหล่านั้นที่สนับสนุน DirectQuery ใน “แหล่งข้อมูลรายงาน Power BI ใน Power BI Report Server”

### <a name="scheduled-data-refresh-for-imported-data"></a>การรีเฟรชข้อมูลที่จัดกำหนดการแล้วสำหรับข้อมูลที่นำเข้า

ในเซิร์ฟเวอร์รายงาน Power BI คุณสามารถตั้งค่ารีเฟรชข้อมูลตามกำหนดเวลาเพื่อปรับให้ข้อมูลทันสมัยในรายงาน Power BI โดยใช้รูปแบบข้อมูลฝังตัวแทนที่จะใช้การเชื่อมต่อสด หรือ DirectQuery ด้วยการนำเข้าข้อมูลโดยใช้แบบจำลองแบบฝัง จึงไม่ได้เชื่อมต่อจากแหล่งข้อมูลต้นฉบับ จำเป็นต้องไมีการอัปเดตเพื่อให้ข้อมูลใหม่ล่าสุดอยู่เสมอ และการรีเฟรชตามกำหนดการเป็นวิธีสำหรับทำเช่นนั้น อ่านเพิ่มเติมเกี่ยวกับ "การรีเฟรชตามกำหนดการสำหรับรายงาน Power BI ใน Power BI Report Server"

### <a name="editing-power-bi-reports-from-the-server"></a>การแก้ไขรายงาน Power BI จากเซิร์ฟเวอร์

คุณสามารถเปิดและแก้ไขไฟล์รายงาน Power BI (.pbix) จากเซิร์ฟเวอร์ได้ แต่คุณต้องกลับมาที่ไฟล์ต้นฉบับที่อัปโหลด  ซึ่งหมายความว่า **ถ้ามีการรีเฟรชข้อมูลโดยเซิร์ฟเวอร์ ข้อมูลก็จะไม่ถูกรีเฟรชเมื่อคุณเปิดไฟล์ครั้งแรก** คุณจำเป็นต้องรีเฟรชข้อมูลด้วยตนเองภายในเครื่องเพื่อดูการเปลี่ยนแปลง

### <a name="large-file-uploaddownload"></a>การอัปโหลด/การดาวน์โหลดไฟล์ขนาดใหญ่

คุณสามารถอัปโหลดไฟล์ที่มีขนาดสูงสุด 2 GB แม้ว่าตามค่าเริ่มต้น ขีดจำกัดนี้จะถูกตั้งค่าไว้ที่ 1 GB ในการตั้งค่าเซิร์ฟเวอร์รายงานใน SQL Server Management Studio (SSMS) ก็ตาม  ไฟล์เหล่านี้จะถูกจัดเก็บไว้ในฐานข้อมูลเช่นเดียวกับที่มีไว้สำหรับ SharePoint และไม่จำเป็นต้องมีการกำหนดค่าพิเศษสำหรับแค็ตตาล็อก SQL Server  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>การเข้าถึงชุดข้อมูลที่ใช้ร่วมกันเป็นฟีด OData

คุณสามารถเข้าถึงชุดข้อมูลที่ใช้ร่วมกันจาก Power BI Desktop ด้วยฟีด OData สำหรับข้อมูลเพิ่มเติม ดู [การเข้าถึงชุดข้อมูลที่ใช้ร่วมกันเป็นฟีด OData ในเซิร์ฟเวอร์รายงาน Power BI](access-dataset-odata.md)

### <a name="scale-out"></a>การปรับมาตราส่วนออก

การเผยแพร่นี้สนับสนุนการปรับมาตราส่วนออก ใช้ตัวสร้างสมดุลการโหลด และตั้งค่าความสัมพันธ์เซิร์ฟเวอร์สำหรับประสบการณ์การใช้งานที่ดีที่สุด โปรดทราบว่า สถานการณ์สมมติยังไม่ได้ปรับให้เหมาะสมสำหรับการปรับมาตราส่วนออก ดังนั้น คุณจึงเห็นแบบจำลองที่อาจเป็นรูปถอดแบบในหลายโหนด สถานการณ์สมมติจะทำงานได้โดยไม่มี Network Load Balancer และเซสชันการตรึง อย่างไรก็ตาม คุณจะไม่เพียงแต่จะเห็นการใช้งานหน่วยความจำมากเกินไปทั่วโหนดเนื่องจากแบบจำลองถูกโหลด N ครั้งเท่านั้น แต่ประสิทธิภาพการทำงานจะช้าในระหว่างการเชื่อมต่อเนื่องจากแบบจำลองจะเป็นสตรีมตามที่ไปถึงโหนดใหม่ในระหว่างคำขอด้วย  

### <a name="administrator-settings"></a>การตั้งค่าโดยผู้ดูแลระบบ

ผู้ดูแลระบบสามารถตั้งค่าคุณสมบัติต่อไปนี้ในคุณสมบัติขั้นสูง SSMS สำหรับเซิร์ฟเวอร์ฟาร์ม:

* เปิดใช้งานวิชวลแบบกำหนดค่าเอง: True/False จริง/เท็จ
* เปิดใช้งานแบบจำลองรายงาน Power BI แบบฝังตัว: จริง/เท็จ
* เปิดใช้งานการนำออกข้อมูลจากรายงาน Power BI: จริง/เท็จ
* MaxFileSizeMb: ค่าเริ่มต้นในตอนนี้คือ 1000
* ModelCleanupCycleMinutes: ความถี่ในการตรวจสอบเพื่อขับแบบจำลองจากหน่วยความจำ
* ModelExpirationMinutes: ระยะเวลาจนกว่าแบบจำลองหมดอายุ และขับออกไปตามครั้งที่ใช้ล่าสุด
* ScheduleRefreshTimeoutMinutes: การรีเฟรชข้อมูลจะใช้เวลานานแค่ไหนสำหรับแต่ละรูปแบบ ตามค่าเริ่มต้น เป็นเวลาสองชั่วโมง  ไม่มีขีดจำกัดสูงสุด

**ไฟล์กำหนดค่า rsreportserver.config**

```xml
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>API นักพัฒนา

API นักพัฒนา (REST API) ซึ่งเริ่มนำมาใช้สำหรับ SSRS 2017 ได้มีการขยายต่อยอดสำหรับ Power BI Report Server เพื่อทำงานกับทั้งไฟล์ Excel และไฟล์ .pbix กรณีใช้งานที่เป็นไปได้กรณัหนึ่งก็คือ การใช้โปรแกรมดาวน์โหลดไฟล์จากเซิร์ฟเวอร์ รีเฟรชและเผยแพร่ไฟล์เหล่านั้น นี่คือวิธีเดียวที่จะรีเฟรชสมุดงาน Excel ที่มีแบบจำลอง PowerPivot เป็นต้น

โปรดสังเกตว่า มี API ที่แยกต่างหากใหม่สำหรับไฟล์ขนาดใหญ่ซึ่งจะอัปเดตในเวอร์ชัน Power BI Report Server ของ Swagger 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>SQL Server Analysis Services (SSAS) และพื้นที่หน่วยความจำ Power BI Report Server

ในขณะนี้ Power BI Report Server เป็นโฮสต์ของ SQL Server Analysis Services (SSAS) ภายใน ทั้งนี้ ไม่ได้เฉพาะเจาะจงอยู่ที่การรีเฟรชตามกำหนดการ การเป็นโฮสตของ์ SSAS สามารถเพิ่มพื้นที่หน่วยความจำเซิร์ฟเวอร์รายงานได้อย่างมาก ไฟล์กำหนดค่า AS.ini จะพร้อมใช้งานบนโหนดเซิร์ฟเวอร์ ดังนั้น ถ้าคุณคุ้นเคยกับ SSAS คุณอาจต้องการอัปเดตการตั้งค่ารวมถึงขีดจำกัดหน่วยความจำสูงสุดและการแคชดิสก์และอื่น ๆ ดู [คุณสมบัติเซิร์ฟเวอร์ใน Analysis Services](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services) สำหรับรายละเอียด

### <a name="viewing-and-interacting-with-excel-workbooks"></a>การดูและโต้ตอบกับสมุดงาน Excel

Excel และ Power BI ประกอบด้วยพอร์ตโฟลิโอของเครื่องมือที่พิเศษเฉพาะในอุตสาหกรรม สิ่งเหล่านี้จะร่วมกันช่วยให้นักวิเคราะห์ธุรกิจสามารถรวบรวม กำหนดรูปร่าง วิเคราะห์และใช้ภาพในการสำรวจข้อมูลของพวกเขาได้ง่ายยิ่งขึ้น นอกเหนือจากการดูรายงาน Power BI ในพอร์ทัลของเว็บแล้ว ตอนนี้ผู้ใช้ธุรกิจยังสามารถทำเช่นเดียวกันกับสมุดงาน Excel ในPower BI Report Server โดยมีตำแหน่งที่ตั้งเดียวสำหรับเผยแพร่ข้อมูล และดูเนื้อหา Microsoft BI ของพวกเขาในแบบบริการตัวเอง

เราได้เผยแพร่ [บทสรุปเกี่ยวกับวิธีการเพิ่ม Office Online Server (OOS) ไปยังสภาพแวดล้อมการแสดงตัวอย่างของ Power BI Report Server](excel-oos.md) ลูกค้าที่มีบัญชี Volume Licensing สามารถดาวน์โหลด OOS ได้จาก Volume License Servicing Center โดยไม่มีค่าใช้จ่าย และจะมีฟังก์ชันดูเท่านั้น เมื่อกำหนดค่แล้วา ผู้ใช้สามารถดูและโต้ตอบกับสมุดงาน Excel ซึ่ง:

* ไม่มีการอิงตามแหล่งข้อมูลภายนอก
* มีการเชื่อมต่อแบบสดกับแหล่งข้อมูล SQL Server Analysis Services ภายนอก
* มีแบบจำลองข้อมูล PowerPivot

### <a name="support-for-new-table-and-matrix-visuals"></a>สนับสนุนการแสดงผลด้วยภาพตารางและเมทริกซ์ใหม่

ในขณะนี้ Power BI Report Server สนับสนุนการแสดงผลด้วยภาพตารางและเมทริกซ์ใหม่ เมื่อต้องสร้างรายงานโดยใช้การแสดงผลด้วยภาพเหล่านี้ คุณจะต้องใช้การเผยแพร่ Power BI Desktop ที่อัปเดตแล้วสำหรับการเผยแพรในเดือนตุลาคม 2017 จะไม่สามารถติดตั้งกับ Power BI Desktop รุ่นเผยแพร่ (เดือนมิถุนายน 2017) สำหรับ Power BI Desktop เวอร์ชันล่าสุดบน [หน้าดาวน์โหลดของ Power BI Report Server](https://powerbi.microsoft.com/report-server/) เลือก**ตัวเลือกการดาวน์โหลดขั้นสูง**

## <a name="june-2017"></a>มิถุนายน 2017

* Power BI Report Server พร้อมใช้งานโดยทั่วไปแล้ว (GA)

## <a name="may-2017"></a>พฤษภาคม 2017

* การแสดงตัวอย่าง Power BI Report Server พร้อมใช้งานแล้ว
* ความสามารถในการเผยแพร่รายงาน Power BI ภายในองค์กร
  * สนับสนุนภาพแบบกำหนดเอง
  * สนับสนุน**การเชื่อมต่อสดของ Analysis Services** กับแหล่งข้อมูลเพิ่มเติมที่จะเข้ามาเท่านั้น
  * แอปอุปกรณ์เคลื่อนที่ Power BI ทีอัปเดตเพื่อแสดงรายงาน Power BI ที่โฮสต์ใน Power BI Report Server
* การทำงานร่วมกันในรายงานที่มีข้อคิดเห็นซึ่งได้รับการปรับปรุงแล้ว

## <a name="next-steps"></a>ขั้นตอนถัดไป

ลองตรวจสอบแหล่งข้อมูลเหล่านี้ เพื่อให้คุณทันกับคุณลักษณะใหม ๆ ใน Power BI Report Server

* [Microsoft Power BI บล็อก](https://powerbi.microsoft.com/blog/)
* [SQL Server Reporting Services ที่บล็อกของทีม](https://blogs.msdn.microsoft.com/sqlrsteamblog/)
* [YouTube ช่อง Guy in a Cube](https://aka.ms/guyinacube)

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](https://community.powerbi.com/)
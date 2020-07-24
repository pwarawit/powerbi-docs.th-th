---
title: การใช้เครื่องมือภายนอกใน Power BI (ตัวอย่าง)
description: ขยายการใช้ Power BI Desktop ด้วยเครื่องมือภายนอก
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/15/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 4d752a49587e611c3f42de3f40c68437f36fe3a9
ms.sourcegitcommit: 11deeccf596e9bb8f22615276a152614f7579f35
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/16/2020
ms.locfileid: "86411940"
---
# <a name="using-external-tools-in-power-bi-desktop-preview"></a>การใช้เครื่องมือภายนอกใน Power BI Desktop (ตัวอย่าง)

เริ่มต้นด้วยการเผยแพร่เดือนกรกฎาคม 2020 ของ Power BI Desktop คุณสามารถใช้เครื่องมือภายนอกเพื่อให้สามารถทำงานเพิ่มเติมและให้ค่าแก่ Power BI Desktop ได้ การสนับสนุนสำหรับเครื่องมือภายนอกช่วยให้คุณสามารถใช้ประโยชน์จากความหลากหลายของเครื่องมือชุมชนสำหรับ Analysis Services สำหรับผู้เชียวชาญด้าน BI การเพิ่มประสิทธิภาพการทำงานของคิวรี/นิพจน์ DAXและการเขียน และการจัดการวงจรของแอปพลิเคชัน (ALM)

ริบบอน**เครื่องมือภายนอก**ใน Power BI Desktop ประกอบด้วยปุ่มสำหรับเครื่องมือภายนอกที่ติดตั้งอยู่บนเครื่องและลงทะเบียนด้วย Power BI Desktop เครื่องมือภายนอกที่เปิดใช้งานจาก Power BI Desktop จะเชื่อมต่อกับกลไกจัดการ Analysis Services โดยอัตโนมัติซึ่งทำงานเป็นส่วนหนึ่งของ Power BI Desktop ให้ประสบการณ์ที่ราบรื่นสำหรับผู้ใช้

![ริบบอนเครื่องมือภายนอกใน Power BI Desktop](media/desktop-external-tools/desktop-external-tools-01.png)

ส่วนต่อไปนี้อธิบายการดำเนินการที่ได้รับการสนับสนุนโดยเครื่องมือภายนอก รายการเครื่องมือที่แนะนำที่รวมอยู่ใน Power BI Desktop และคำแนะนำเกี่ยวกับวิธีการลงทะเบียนเครื่องมือเพิ่มเติม

## <a name="supported-write-operations"></a>การดำเนินการเขียนที่รองรับ

เครื่องมือภายนอกสามารถเชื่อมต่อกับชุดข้อมูล Power BI Desktop (แบบจำลอง Analysis Services) เพื่อแก้ไขวัตถุต่อไปนี้ การแก้ไขไฟล์แม่แบบ Power BI Desktop (PBIT) ไม่ได้รับการสนับสนุน

* [หน่วยวัด](https://docs.microsoft.com/analysis-services/tabular-models/measures-ssas-tabular)สำหรับการคำนวณ
* [กลุ่มการคำนวณ](https://docs.microsoft.com/analysis-services/tabular-models/calculation-groups)สำหรับการคำนวณความสามารถในการนำกลับมาใช้ใหม่ในแบบจำลองที่ซับซ้อน
* [มุมมอง](https://docs.microsoft.com/analysis-services/tabular-models/perspectives-ssas-tabular)เพื่อกำหนดมุมมองเฉพาะของโดเมนธุรกิจของชุดข้อมูลเมตาดาต้า

การจัดการการแปลเมตาดาต้าโดยใช้เครื่องมือภายนอกอาจเป็นไปได้แต่ไม่ได้รับการสนับสนุนในเวอร์ชันตัวอย่างนี้ ถ้าตำแหน่งที่ตั้งของผู้ใช้ปัจจุบันเป็นภาษาที่ได้รับการแปล การแก้ไขวัตถุในรายการเขตข้อมูลจะทำงานอย่างไม่ถูกต้องโดยใช้ Power BI Desktop เวอร์ชันปัจจุบัน 

มีปัญหาที่ทราบเมื่อคุณสร้างรายงานเทียบกับแบบจำลองที่มีการกำหนดกลุ่มการคำนวณ ถ้ากลุ่มการคำนวณกำหนดรูปแบบแบบไดนามิกโดยขึ้นอยู่กับการคำนวณ/หน่วยวัดที่เลือก การจัดรูปแบบดังกล่าวจะพร้อมใช้งานในตาราง เมทริกซ์ และการ์ด

คุณสามารถเข้าถึงเมตาดาต้าของชุดข้อมูลแบบ[จำลองวัตถุแบบตาราง](https://docs.microsoft.com/analysis-services/tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo)ทั้งหมดสำหรับวัตถุประสงค์แบบอ่านอย่างเดียว แต่ไม่มีวัตถุที่ครอบคลุมอยู่ในรายการที่อธิบายไว้ในบทความ [จำลองวัตถุแบบตาราง](https://docs.microsoft.com/analysis-services/tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo)ซึ่งยังไม่ได้รับการรองรับสำหรับการแก้ไขในอินสแตนซ์ Power BI Desktop Analysis Services


## <a name="featured-external-tools"></a>เครื่องมือภายนอกที่แนะนำ

เครื่องมือชุมชนแหล่งข้อมูแบบเปิดลต่อไปนี้ทำงานร่วมกับ Power BI Desktop ตัวติดตั้งที่เกี่ยวข้องของเครื่องมือแต่ละรายการจะลงทะเบียนด้วย Power BI Desktop เมื่อติดตั้ง:

* ตัวแก้ไขตาราง
* DAX Studio
* ALM Toolkit

มาดูที่เครื่องมือแต่ละอย่างเหล่านั้นตามลำดับกัน

### <a name="tabular-editor"></a>ตัวแก้ไขตาราง

คุณสามารถติดตั้ง[ตัวแก้ไขตาราง](https://tabulareditor.com/)จากลิงก์ต่อไปนี้: [เว็บไซต์ตัวแก้ไขตาราง](https://tabulareditor.com/)

ตัวแก้ไขตารางช่วยให้ผู้เชี่ยวชาญ BI สามารถสร้างรักษาและจัดการแบบจำลองตารางโดยใช้ตัวแก้ไขที่ง่ายและใช้พื้นที่ไม่มาก มุมมองแบบลำดับชั้นแสดงวัตถุทั้งหมดในโมเดลตารางของคุณ ซึ่งจัดระเบียบโดยการแสดงโฟลเดอร์พร้อมรองรับการแก้ไขคุณสมบัติแบบเลือกได้หลายรายการและการเน้นไวยากรณ์ DAX

![สกรีนช็อตของตัวแก้ไขตาราง](media/desktop-external-tools/desktop-external-tools-02.png)

รหัสแหล่งที่มาสำหรับตัวแก้ไขแบบตารางสามารถพบได้ในที่เก็บ GitHub ต่อไปนี้: [ตัวแก้ไขตารางใน GitHub](https://github.com/otykier/TabularEditor)

ผู้สร้างเครื่องมือหลักสำหรับตัวแก้ไขตารางคือ [Daniel Otykier](https://www.linkedin.com/in/daniel-otykier-2231876)


### <a name="dax-studio"></a>DAX Studio

คุณสามารถติดตั้ง [DAX Studio](https://daxstudio.org) จากการลิงก์ต่อไปนี้: [เว็บไซต์ DAX Studio](https://daxstudio.org)

DAX Studio เป็นที่รู้จักสำหรับเครื่องมือที่สมบูรณ์สำหรับการสร้าง การวินิจฉัย การปรับแต่งประสิทธิภาพ และการวิเคราะห์ DAX คุณลักษณะต่างๆ ประกอบด้วยการค้นหาวัตถุ การติดตามแบบรวม การแยกย่อยการประมวลผลคิวรีด้วยสถิติโดยละเอียด การเน้นไวยากรณ์และการจัดรูปแบบของ DAX รูปภาพต่อไปนี้แสดงหน้าจอ Dax Studio 

![สกรีนช็อตของ DAX Studio](media/desktop-external-tools/desktop-external-tools-03.png)

รหัสแหล่งที่มาสำหรับ DAX Studio สามารถพบได้ในที่เก็บ GitHub ต่อไปนี้: [DAX Studio ใน GitHub](https://github.com/DaxStudio/DaxStudio)

ผู้สร้างเครื่องมือหลักสำหรับ DAX Studio คือ [Darren Gosbell](https://www.linkedin.com/in/darrengosbell)

### <a name="alm-toolkit"></a>ALM Toolkit

คุณสามารถติดตั้ง [ALM Toolkit](http://alm-toolkit.com) จากลิงก์ต่อไปนี้: [เว็บไซต์ ALM Toolkit](http://alm-toolkit.com)

ALM Toolkit เป็นเครื่องมือการเปรียบเทียบ Schema สำหรับชุดข้อมูล Power BI ซึ่งใช้บ่อยที่สุดสำหรับสถานการณ์การจัดการวงจรชีวิตของแอปพลิเคชัน (ALM) คุณสามารถทำการปรับใช้ในสภาพแวดล้อมและรักษาข้อมูลในอดีตที่มีการรีเฟรชแบบเพิ่มหน่วยได้โดยตรง คุณสามารถเปรียบเทียบและผสานไฟล์เมตาดาต้า สาขา และที่เก็บได้ด้วย ALM Toolkit คุณยังสามารถนำข้อกำหนดทั่วไปมาใช้ใหม่ระหว่างชุดข้อมูลได้อีกด้วย

![สกรีนช็อตของ  ALM Toolkit](media/desktop-external-tools/desktop-external-tools-04.png)

รหัสแหล่งที่มาสำหรับ  ALM Toolkit สามารถพบได้ในที่เก็บ GitHub ต่อไปนี้: [ALM Toolkit ใน GitHub](https://github.com/microsoft/analysis-services)

ผู้สร้างเครื่องมือหลักสำหรับ ALM Toolkit คือ [Christian Wade](https://www.linkedin.com/in/christianwade1)


## <a name="how-to-register-external-tools"></a>วิธีการลงทะเบียนเครื่องมือภายนอก

ถ้าต้องการลงทะเบียนเครื่องมือภายนอกอื่นๆ ด้วย Power BI Desktop ให้สร้างไฟล์ JSON ที่มีเนื้อหาดังต่อไปนี้:

```json
{
    "name": "<tool name>",
    "description": "<tool description>",
    "path": "<tool executable path>",
    "arguments": "<optional command line arguments>",
    "iconData": "image/png;base64,<encoded png icon data>"
}
```

รายการต่อไปนี้อธิบายรายการขององค์ประกอบในไฟล์ JSON:
 
* **ชื่อ:** ระบุชื่อสำหรับเครื่องมือซึ่งจะปรากฏเป็นคำบรรยายปุ่มในริบบอนเครื่องมือภายนอกใน Power BI Desktop
* **คำอธิบาย:** (ไม่บังคับ) ใส่คำอธิบายซึ่งจะปรากฏเป็นคำแนะนำเครื่องมือบนปุ่มริบบอนอุปกรณ์ภายนอกใน Power BI Desktop
* **เส้นทาง:** ใส่เส้นทางที่ถูกต้องแบบเต็มในไฟล์ปฏิบัติการของเครื่องมือ
* **อาร์กิวเมนต์:** (ไม่บังคับ) ใส่สตริงของอาร์กิวเมนต์บรรทัดคำสั่งที่ควรจะเปิดใช้งานเครื่องมือ คุณอาจใช้ตัวยึดต่อไปนี้ได้:
    * **% server%:** แทนที่ด้วยชื่อเซิร์ฟเวอร์และหมายเลขพอร์ตของอินสแตนซ์ภายในเครื่องของ Analysis Services Tabular สำหรับแบบจำลองข้อมูลที่นำเข้า/DirectQuery
    * **%database%:** แทนที่ด้วยชื่อฐานข้อมูลของแบบจำลองที่โฮสต์ในอินสแตนซ์ภายในเครื่องของ Analysis Services Tabular สำหรับแบบจำลองข้อมูลที่นำเข้า/DirectQuery
* **iconData:** ใส่ข้อมูลรูปภาพซึ่งจะแสดงเป็นไอคอนปุ่มในริบบอนเครื่องมือภายนอกใน Power BI Desktop สตริงควรได้รับการจัดรูปแบบตามไวยากรณ์สำหรับ  URI ข้อมูลโดยไม่มีคำนำหน้า "data:"
 
ตั้งชื่อไฟล์ `"<tool name>.pbitool.json"` และวางในโฟลเดอร์ต่อไปนี้:

* `%commonprogramfiles%\Microsoft Shared\Power BI Desktop\External Tools`

สำหรับระบบ 64 บิต ให้วางไฟล์ในโฟลเดอร์ต่อไปนี้:

* **Program Files (x86)\Common Files\Microsoft Shared\Power BI Desktop\External Tools**

ไฟล์ในตำแหน่งที่ตั้งที่ระบุด้วยส่วนขยาย **.pbitool.json** จะโหลดโดย Power BI Desktop เมื่อเริ่มต้นใช้งาน


## <a name="next-steps"></a>ขั้นตอนถัดไป

คุณอาจสนใจบทความต่อไปนี้:

* [ใช้การเข้าถึงรายละเอียดแบบข้ามรายงานในรายงาน Power BI](desktop-cross-report-drill-through.md)
* [การใช้ตัวแบ่งส่วนข้อมูล Power BI Desktop](../visuals/power-bi-visualization-slicers.md)



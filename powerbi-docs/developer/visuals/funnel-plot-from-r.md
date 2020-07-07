---
title: สร้างแผนภูมิกรวยจากสคริปต์ R ไปยังวิชวล R
description: บทความนี้อธิบายวิธีการสร้างแผนภูมิกรวยจากสคริปต์ R ไปยังวิชวล R Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 04/02/2020
ms.openlocfilehash: cbc8f6366e23aa7fbfb447bbfe56909c09f3e3fd
ms.sourcegitcommit: caf60154a092f88617eb177bc34fb784f2365962
ms.contentlocale: th-TH
ms.lasthandoff: 06/25/2020
ms.locfileid: "85354489"
---
# <a name="tutorial-build-a-funnel-plot-from-r-script-to-r-visual"></a>บทช่วยสอน: สร้างแผนภูมิกรวยจากสคริปต์ R ไปยังวิชวล R
บทความนี้จะอธิบายวิธีสร้างแผนภูมิกรวยโดยใช้สคริปต์ R ในวิชวล R เป็นขั้นเป็นตอน

ในบทความนี้คุณเรียนรู้วิธีสร้าง:

> [!div class="checklist"]
>
> * สคริปต์ R สำหรับ RStudio
> * วิชวล R ใน Power BI
> * วิชวลที่ขับเคลื่อนด้วย R *แบบใช้ PNG* ใน Power BI
> * วิชวลที่ขับเคลื่อนด้วย R *แบบใช้ HTML* ใน Power BI

แผนภูมิกรวยช่วยให้การใช้ แปล และแสดงปริมาณการเปลี่ยนแปลงที่คาดไว้ทำได้อย่างง่ายดาย **กรวย**ถูกสร้างขึ้นโดยใช้ขีดจำกัดความเชื่อมั่นและค่าผิดปกติจะแสดงเป็นจุดด้านนอกกรวย

ในตัวอย่างนี้ เราใช้แผนภูมิกรวยเพื่อเปรียบเทียบและวิเคราะห์ข้อมูลชุดต่างๆ  

> [!NOTE]
> ไฟล์ต้นฉบับพร้อมใช้งานสำหรับการดาวน์โหลดภายใต้แต่ละชุดของขั้นตอน

## <a name="build-an-r-script-with-dataset"></a>สร้างสคริปต์ R ที่มีชุดข้อมูล

1. ดาวน์โหลด [สคริปต์ R น้อยที่สุด](https://github.com/microsoft/PowerBI-visuals/raw/master/RVisualTutorial/TutorialFunnelPlot/chapter1_R/script_R_v1_00.r) และตารางข้อมูล [dataset.csv](https://github.com/microsoft/PowerBI-visuals/raw/master/RVisualTutorial/TutorialFunnelPlot/chapter1_R/dataset.csv)

1. ถัดไป แก้ไขสคริปต์เพื่อทำมิเรอร์ [สคริปต์นี้](https://github.com/microsoft/PowerBI-visuals/raw/master/RVisualTutorial/TutorialFunnelPlot/chapter1_R/script_R_v1_01.r) สิ่งนี้เพิ่มการจัดการข้อผิดพลาดของอินพุตและพารามิเตอร์ผู้ใช้เพื่อควบคุมลักษณะที่ปรากฏของกราฟ

## <a name="build-a-report"></a>สร้างรายงาน

ถัดไป แก้ไขสคริปต์เพื่อทำมิเรอร์ [สคริปต์นี้](https://github.com/microsoft/PowerBI-visuals/raw/master/RVisualTutorial/TutorialFunnelPlot/chapter2_Rvisual/script_RV_v2_00.r) การดำเนินการนี้จะโหลด *dataset.csv* แทนที่จะเป็น *read.csv* ลงในพื้นที่ทำงานของ Power BI desktop และสร้างตาราง **Cancer Mortality** ดูผลลัพธ์ใน[ไฟล์ PBIX](https://github.com/microsoft/PowerBI-visuals/raw/master/RVisualTutorial/TutorialFunnelPlot/chapter2_Rvisual/funnelPlot_Rvisual.pbix) ต่อไปนี้

> [!NOTE]
> `dataset` เป็นชื่อแบบฮาร์ดโค้ดสำหรับการป้อนค่า `data.frame` ของวิชวล R 

## <a name="create-an-r-powered-visual-and-package-in-r-code"></a>สร้างวิชวลและแพคเกจที่ขับเคลื่อนด้วย R ใน R code

1. ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าได้ [ติดตั้งเครื่องมือ PBIVIZ](./custom-visual-develop-tutorial.md#installing-packages)

1. เรียกใช้คำสั่งต่อไปนี้เพื่อสร้างวิชวลที่ขับเคลื่อนด้วย R ใหม่:

   ```bash
   pbiviz new funnel-visual -t rvisual
   cd funnel-visual
   npm install 
   pbiviz package
   ```

   คำสั่งนี้สร้างโฟลเดอร์ *วิชวลกรวย* ด้วยวิชวลเทมเพลตเริ่มต้น (`-t` สำหรับ**เทมเพลต**) PBIVIZ สามารถพบได้ในโฟลเดอร์ *dist*, โค้ด R ภายในไฟล์ *script.r* ลองนำเข้าลงใน Power BI และดูว่าเกิดอะไรขึ้น

1. แก้ไขไฟล์ *script.r* และแทนที่เนื้อหาด้วยสคริปต์ก่อนหน้าของคุณ

1. แก้ไข *capabilities.json* และแทนที่ `Values` สตริงด้วย `dataset` การดำเนินการนี้จะแทนที่ชื่อ "บทบาท" ในเทมเพลตเหมือนในโค้ด R

   ![ก่อนเทียบกับหลัง](./samples/funnel-plot/chapter-3/funnel-r-visual-v01/capabilities-changes.PNG)

1. *(ไม่บังคับ)* แก้ไข *dependencies.json* และเพิ่มส่วนสำหรับแต่ละแพคเกจ R ที่จำเป็นโดยสคริปต์ R การดำเนินการนี้จะเป็นการบอกให้ Power BI นำเข้าแพคเกจเหล่านี้โดยอัตโนมัติเมื่อมีการโหลดวิชวลเป็นครั้งแรก

   ![ก่อนเทียบกับหลัง](./samples/funnel-plot/chapter-3/funnel-r-visual-v01/dependencies-changes.PNG)

1. บรรจุวิชวลเป็นแพคเกจอีกครั้งโดยใช้คำสั่ง `pbiviz package` และลองนำเข้าไปยัง Power BI

> [!NOTE]
> ดู [PBIX](https://github.com/microsoft/PowerBI-visuals/raw/master/RVisualTutorial/TutorialFunnelPlot/chapter3-RCustomVisual/funnelPlot_RCustomVisual.pbix) และ [โค้ดต้นฉบับ](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v01/) สำหรับการดาวน์โหลด

## <a name="make-r-based-visual-improvements"></a>สร้างการปรับปรุงวิชวลแบบใช้ R

วิชวลยังไม่เป็นมิตรต่อผู้ใช้เพราะผู้ใช้จะต้องทราบลำดับของคอลัมน์ในตารางอินพุต

1. แบ่งเขตข้อมูลอินพุต `dataset` ออกเป็นสามเขตข้อมูล (บทบาท): `Population`, `Number`และ `Tooltips`

   ![CV01to02](./media/funnel-plot/diagram-one.PNG)

1. แก้ไข *capabilities.json* และแทนที่บทบาท `dataset` ด้วยบทบาทใหม่สามบทบาทหรือดาวน์โหลด [capabilities.json](https://github.com/microsoft/PowerBI-visuals/raw/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v02/capabilities.json)

   คุณจะต้องอัปเดตส่วน: `dataRoles` และ `dataViewMappings`ซึ่งกำหนดชื่อ ชนิด คำแนะนำเครื่องมือ และคอลัมน์สูงสุดสำหรับแต่ละเขตข้อมูลป้อนเข้า

   ![ก่อนและหลัง](./samples/funnel-plot/chapter-3/funnel-r-visual-v02/capabilities-before-vs-after.png)
   
   สำหรับข้อมูลเพิ่มเติม ให้ดู [capabilities](./capabilities.md)

1. แก้ไข *script.r* เพื่อรองรับ `Population`, `Number` และ `Tooltips` ให้เป็นกรอบข้อมูลอินพุตแทนที่จะเป็น `dataset` หรือดาวน์โหลด [script.r](https://github.com/microsoft/PowerBI-visuals/raw/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v02/script.r)

   ![สคริปต์](./samples/funnel-plot/chapter-3/funnel-r-visual-v02/script-r-before-vs-after.png)

   > [!TIP]
   > หากต้องการทำตามการเปลี่ยนแปลงในสคริปต์ R ให้ค้นหาบล็อกข้อคิดเห็น: 
   > 
   > ```r
   > #RVIZ_IN_PBI_GUIDE:BEGIN: Added to enable visual fields
   > ...
   > #RVIZ_IN_PBI_GUIDE:END: Added to enable visual fields
   > 
   > #RVIZ_IN_PBI_GUIDE:BEGIN: Removed to enable visual fields 
   > ...
   > #RVIZ_IN_PBI_GUIDE:BEGIN: Removed to enable visual fields
   > ```

1. บรรจุวิชวลเป็นแพคเกจอีกครั้งโดยใช้คำสั่ง `pbiviz package` และลองนำเข้าไปยัง Power BI

> [!NOTE]
> ดู [PBIX](https://github.com/microsoft/PowerBI-visuals/raw/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelPlot_RCustomVisual.pbix) และ [โค้ดต้นฉบับ](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v02) สำหรับการดาวน์โหลด

## <a name="add-user-parameters"></a>เพิ่มพารามิเตอร์ผู้ใช้

1. เพิ่มความสามารถสำหรับผู้ใช้ในการควบคุมสีและขนาดขององค์ประกอบวิชวล รวมถึงพารามิเตอร์ภายในจาก UI

   ![CV02to03](./media/funnel-plot/diagram-two.PNG)

1. แก้ไข *capabilities.json* และอัปเดตส่วน `objects` ที่นี่เรากำหนดชื่อ คำแนะนำเครื่องมือ และชนิดของแต่ละพารามิเตอร์ และยังตัดสินใจเลือกพาร์ติชันของพารามิเตอร์ลงในกลุ่ม (สามกลุ่มในกรณีนี้)

   ดาวน์โหลด [capabilities.json](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v03/capabilities.json) ดู [คุณสมบุติวัตถุ](./objects-properties.md) สำหรับข้อมูลเพิ่มเติม

   ![ความสามารถ](./samples/funnel-plot/chapter-3/funnel-r-visual-v03/capabilities-before-after.PNG)

1. แก้ไข *src/settings.ts* เพื่อมิเรอร์ [settings.ts นี้](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v03/src/settings.ts) ไฟล์นี้จะถูกเขียนใน TypeScript  

   ที่นี่คุณจะพบบล็อกของโค้ดสองรายการที่เพิ่มเข้าไปเพื่อ:
   - ประกาศอินเทอร์เฟซใหม่เพื่อเก็บค่าคุณสมบัติ
   - กำหนดคุณสมบัติสมาชิกและค่าเริ่มต้น

   ![การตั้งค่า](./samples/funnel-plot/chapter-3/funnel-r-visual-v03/settings-ts-before-after.PNG)

1. แก้ไข *script.r* เพื่อมิเรอร์ [script.r นี้](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v03/script.r) ซึ่งเพิ่มการสนับสนุนสำหรับพารามิเตอร์ใน UI โดยการเพิ่มการเรียก `if.exists` ต่อพารามิเตอร์ผู้ใช้

   > [!TIP]
   > หากต้องการทำตามการเปลี่ยนแปลงในสคริปต์ R ให้ค้นหาความคิดเห็น:
   >
   > ```r
   > #RVIZ_IN_PBI_GUIDE:BEGIN:Added to enable user parameters
   >  ...
   > #RVIZ_IN_PBI_GUIDE:END:Added to enable user parameters
   >
   > #RVIZ_IN_PBI_GUIDE:BEGIN:Removed to enable user parameters 
   >  ...
   > #RVIZ_IN_PBI_GUIDE:END:Removed to enable user parameters
   > ```

   ![สคริปต์ก่อนและหลัง](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v03/script_r_before_after_1.png)

   คุณสามารถตัดสินใจที่จะไม่เปิดเผยพารามิเตอร์ไปยัง UI อย่างที่เราทำ  

1. บรรจุวิชวลเป็นแพคเกจอีกครั้งโดยใช้คำสั่ง `pbiviz package` และลองนำเข้าไปยัง Power BI

> [!NOTE]
> ดู [PBIX](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelPlot_RCustomVisual.pbix) และ [โค้ดต้นฉบับ](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter3_RCustomVisual/funnelRvisual_v03/) สำหรับการดาวน์โหลด

> [!TIP]
> ต่อไปนี้เราได้เพิ่มพารามิเตอร์ของหลายชนิด (บูลีน, ตัวเลข, สตริงและสี) ทั้งหมดในครั้งเดียว สำหรับกรณีอย่างง่าย โปรดดู [ตัวอย่างนี้](https://github.com/Microsoft/PowerBI-visuals/blob/master/RVisualTutorial/PropertiesPane.md) เกี่ยวกับวิธีการเพิ่มพารามิเตอร์เดียว 

## <a name="convert-visual-to-rhtml-based-visual"></a>แปลงวิชวลเป็นวิชวลแบบใช้ RHTML

เนื่องจากวิชวลที่แสดงนั้นเป็นแบบ PNG จึงไม่ตอบสนองต่อการเลื่อนเมาส์ ไม่สามารถซูมเข้าและอื่นๆ ได้ ดังนั้นเราจำเป็นต้องแปลงเป็นวิชวลแบบใช้ HTML เราจะสร้างเทมเพลตการวิชวลแบบ HTML ที่ขับเคลื่อนด้วย R ที่ว่างเปล่า จากนั้นคัดลอกสคริปต์บางอย่างจากโครงการแบบใช้ PNG

1. เรียกใช้คำสั่ง:

   ```bash
   pbiviz new funnel-visual-HTML -t rhtml
   cd funnel-visual-HTML
   npm install 
   pbiviz package
   ```

1. เปิด *capabilities.json* และบันทึกบรรทัด `"scriptOutputType":"html"`

1. เปิด *dependencies.json* และบันทึกชื่อของแพคเกจ R ที่อยู่ในรายการ

1. เปิด *script.r* และบันทึกโครงสร้าง คุณสามารถเปิดและเรียกใช้ใน RStudio ได้เนื่องจากไม่ได้ใช้อินพุตภายนอก 

   การดำเนินการนี้จะเป็นการสร้างและบันทึก *out.html* ไฟล์นี้มีอยู่ในตัวเอง (โดยไม่มีการอ้างอิงภายนอก) และกำหนดกราฟิกภายในวิดเจ็ต HTML 

   > [!IMPORTANT]
   > สำหรับผู้ใช้ `htmlWidgets`, อรรถประโยชน์ R จะปรากฏใน [โฟลเดอร์ r_files](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/funnelRHTMLvisual_v01/r_files) เพื่อช่วยในการแปลงวัตถุ `plotly` หรือ `widget` ลงใน HTML ที่มีทุกอย่างพร้อมในตัว 
   > 
   > วิชวลที่ขับเคลื่อนด้วย R เวอร์ชันนี้ยังสนับสนุนคำสั่ง `source` (แตกต่างจากวิชวลชนิดก่อนหน้า) เพื่อทำให้โค้ดของคุณอ่านได้ง่ายยิ่งขึ้น   
 
1. แทนที่ *capabilities.json* ด้วย *capabilities.json* จากขั้นตอนก่อนหน้านี้ หรือดาวน์โหลด [capabilities.json](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/funnelRHTMLvisual_v01/capabilities.json)

   โปรดจดจำไว้ว่า:

   `"scriptOutputType": "html"`

1. ผสานรวม *script.r* เวอร์ชันล่าสุดกับ *script.r* จากเทมเพลตหรือดาวน์โหลด [script.r](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/funnelRHTMLvisual_v01/script.r)

   สคริปต์ใหม่ใช้แพคเกจ `plotly` เพื่อแปลงวัตถุ **ggplot** ลงในวัตถุ **plotly** แล้วแพคเกจ `htmlWidgets` เพื่อบันทึกไปยังไฟล์ HTML 

   ฟังก์ชันอรรถประโยชน์ส่วนใหญ่จะถูกย้ายไปยัง [_r_files/utils.r_](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/funnelRHTMLvisual_v01/r_files/utils.r) และมีการเพิ่มฟังก์ชัน `generateNiceTooltips` สำหรับลักษณะที่ปรากฏของวัตถุ **plotly**

   ![1](./samples/funnel-plot/chapter-4/RHTML-v01/script-before-after-1.PNG)
   
   ![2](./samples/funnel-plot/chapter-4/RHTML-v01/script-before-after-2.PNG)

   > [!TIP]
   > หากต้องการทำตามการเปลี่ยนแปลงในสคริปต์ R ให้ค้นหาความคิดเห็น:
   > 
   > ```r
   > #RVIZ_IN_PBI_GUIDE:BEGIN:Added to create HTML-based 
   >  ...
   > #RVIZ_IN_PBI_GUIDE:BEGIN:Added to create HTML-based
   >
   > #RVIZ_IN_PBI_GUIDE:BEGIN:Removed to create HTML-based  
   > ...
   > #RVIZ_IN_PBI_GUIDE:BEGIN:Removed to create HTML-based
   > ```

1. ผสาน *dependencies.json* เวอร์ชันล่าสุดกับ *dependencies.json* จากเทมเพลต เพื่อรวมการอ้างอิงแพคเกจ R ใหม่หรือดาวน์โหลด [dependencies.json](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/funnelRHTMLvisual_v01/dependencies.json)

1. แก้ไข *src/settings.ts* ด้วยวิธีเดียวกันจากขั้นตอนก่อนหน้านี้

1. บรรจุวิชวลเป็นแพคเกจอีกครั้งโดยใช้คำสั่ง `pbiviz package` และลองนำเข้าไปยัง Power BI

> [!NOTE]
> ดู [PBIX และโค้ดต้นฉบับ](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/funnelRHTMLvisual_v01) สำหรับการดาวน์โหลด

## <a name="build-additional-examples"></a>สร้างตัวอย่างเพิ่มเติม

1. เรียกใช้คำสั่งต่อไปนี้เพื่อสร้างโครงการว่างเปล่า: 

   ```bash
   pbiviz new example -t rhtml
   cd example
   npm install 
   pbiviz package
   ```

1. รับโค้ดจาก [การแสดง](http://www.htmlwidgets.org/showcase_networkD3.html) และทำการเปลี่ยนแปลงที่เน้นไว้:

   ![การเปลี่ยนแปลงที่เน้น](./media/funnel-plot/diagram-three.PNG)

1. แทนที่ *script.r* ของเทมเพลตคุณ และเรียกใช้ `pbiviz package` อีกครั้ง ตอนนี้วิชวลจะรวมอยู่ในรายงาน Power BI ของคุณ!

## <a name="tips-and-tricks"></a>คำแนะนำและเคล็ดลับ

* เราขอแนะนำให้นักพัฒนาแก้ไข *pbiviz.json* เพื่อจัดเก็บเมตาดาต้าที่ถูกต้อง เช่น **เวอร์ชัน** **อีเมล** **ชื่อ** **ชนิดสิทธิการใช้งาน** และอื่นๆ

   > [!IMPORTANT]
   > เขตข้อมูล **guid** เป็นรหัสเฉพาะสำหรับวิชวล ถ้าคุณสร้างโครงการใหม่สำหรับแต่ละวิชวล GUID จะแตกต่างกันด้วย ซึ่งจะเหมือนกับการใช้โครงการเก่าที่คัดลอกไปยังวิชวลใหม่ซึ่งคุณไม่ควรทำ

* แก้ไข [*assets/icon.png*](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/funnelRHTMLvisual_v01/assets/icon.png) เพื่อสร้างไอคอนเฉพาะสำหรับวิชวลของคุณ 

* เมื่อต้องการตรวจแก้จุดบกพร่อง R code ใน RStudio โดยใช้ข้อมูลเดียวกันกับในรายงาน Power BI ของคุณ ให้เพิ่มสิ่งต่อไปนี้ลงในจุดเริ่มต้นของสคริปต์ R (แก้ไขตัวแปร `fileRda`):

   ```r
   #DEBUG in RStudio
   fileRda = "C:/Users/yourUserName/Temp/tempData.Rda"
   if(file.exists(dirname(fileRda)))
   {
     if(Sys.getenv("RSTUDIO")!="")
       load(file= fileRda)
     else
       save(list = ls(all.names = TRUE), file=fileRda)
   }
   ```

   สิ่งนี้ช่วยประหยัดสภาพแวดล้อมจากรายงาน Power BI และโหลดลงใน RStudio 

* คุณไม่จำเป็นต้องพัฒนาวิชวลที่ขับเคลื่อนด้วย R จากจุดเริ่มต้นด้วยโค้ดที่พร้อมใช้งานบน [GitHub](https://github.com/Microsoft?utf8=%E2%9C%93&q=PowerBI&type=&language=R) คุณสามารถเลือกวิชวลเพื่อใช้เป็นเทมเพลตและคัดลอกโค้ดลงในโครงการใหม่ได้

   ตัวอย่างเช่น ลองใช้ [วิชวล spline แบบกำหนดเอง](https://github.com/Microsoft/PowerBI-visuals-spline)

* แต่ละวิชวล R จะใช้ตัวดำเนินการ `unique` กับตารางข้อมูลอินพุต หากต้องการหลีกเลี่ยงการลบแถวที่เหมือนกัน ให้พิจารณาเพิ่มเขตข้อมูลอินพุตพิเศษด้วย ID ที่ไม่ซ้ำกันและละเว้นในโค้ด R   

* ถ้าคุณมีบัญชี Power BI ให้ใช้บริการ Power BI เพื่อพัฒนาวิชวล [on-the-fly](/PowerBI-visuals/docs/step-by-step-lab/creating-a-custom-visual/#testing-the-custom-visual) แทนที่จะบรรจุเป็นแพคเกจอีกครั้งด้วยคำสั่ง `pbiviz package`

### <a name="html-widgets-gallery"></a>แกลเลอรีวิดเจ็ต HTML
สำรวจวิชวลใน[แกลเลอรีวิดเจ็ต HTML](http://gallery.htmlwidgets.org/) สำหรับการใช้งานในวิชวลถัดไปของคุณ เพื่อทำให้สิ่งต่างๆ เป็นเรื่องง่าย เราได้สร้าง [ที่เก็บโครงการของวิชวล](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/multipleRHTML) พร้อมวิชวล HTML แบบโต้ตอบมากกว่า 20 รายการให้เลือก!

> [!TIP]
> เพื่อสลับระหว่างวิดเจ็ต html ให้ใช้**รูปแบบ** > **การตั้งค่า** > **ชนิด** ลองใช้งานด้วย [ไฟล์ .PBIX นี้](https://github.com/Microsoft/PowerBI-visuals/tree/master/RVisualTutorial/TutorialFunnelPlot/chapter4_RHTMLCustomVisual/multipleRHTML/assets/sample.pbix) 

#### <a name="to-use-a-sample-for-your-visual"></a>เมื่อต้องการใช้ตัวอย่างสำหรับวิชวลของคุณ

1. ดาวน์โหลดทั้งโฟลเดอร์
1. แก้ไข *script.r* และ *dependencies.json* เพื่อเก็บวิดเจ็ตเพียงหนึ่งเดียวเท่านั้น
1. แก้ไข *capabilities.json* และ *settings.ts* เพื่อเอาตัวเลือก `Type` ออก
1. เปลี่ยน `const updateHTMLHead: boolean = true;` เป็น `false` ใน *visual.ts* *(เพื่อประสิทธิภาพการทำงานที่ดีขึ้น)*
1. เปลี่ยนเมตาดาต้าใน *pbiviz.json* ซึ่งสำคัญมากที่สุดเขตข้อมูล `guid`
1. บรรจุเป็นแพคเกจอีกครั้งและดำเนินการต่อเพื่อปรับแต่งวิชวลตามที่ต้องการ 

![CV02to03](./media/funnel-plot/diagram-four.PNG)

![CV02to03](./media/funnel-plot/diagram-five.PNG)

> [!NOTE]
> บริการไม่ได้สนับสนุนวิดเจ็ตทั้งหมดในโครงการนี้

## <a name="next-steps"></a>ขั้นตอนถัดไป

เมื่อต้องการเรียนรู้เพิ่มเติม โปรดดูบทช่วยสอนเพิ่มเติมเกี่ยวกับการ [วิชวล Power BI](./custom-visual-develop-tutorial.md) และ [วิชวล R](/power-bi/visuals/service-r-visuals)

เรียนรู้วิธีการ [พัฒนาและส่งวิชวล](https://powerbi.microsoft.com/documentation/powerbi-developer-office-store/) ไปยัง [Office Store (แกลเลอรี่)](https://store.office.com/appshome.aspx?ui=en-US&rs=en-US&ad=US&clickedfilter=OfficeProductFilter%3aPowerBI&productgroup=PowerBI) หรือสำหรับตัวอย่างเพิ่มเติม โปรดดู [การแสดงสคริปต์ R](https://community.powerbi.com/t5/R-Script-Showcase/bd-p/RVisuals)

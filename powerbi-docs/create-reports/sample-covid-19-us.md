---
title: ตัวอย่างการติดตาม COVID-19 สำหรับรัฐของสหรัฐอเมริกาและรัฐบาลในท้องถิ่น
description: ดาวน์โหลดและแก้ไขรายงานตัวอย่างกับรัฐและข้อมูลท้องถิ่นของสหรัฐอเมริกาสำหรับ COVID-19 การแพร่ระบาด
author: LukaszPawlowski-MS
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/31/2020
ms.author: lukaszp
LocalizationGroup: Samples
ms.openlocfilehash: 432312b5ceb7632e0249d1d7dda6158bf97d0224
ms.sourcegitcommit: 3c51431d85793b71f378c4b0b74483dfdd8411b3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/31/2020
ms.locfileid: "80472071"
---
# <a name="covid-19-tracking-sample-for-us-state-and-local-governments"></a>ตัวอย่างการติดตาม COVID-19 สำหรับรัฐของสหรัฐอเมริกาและรัฐบาลในท้องถิ่น

ทีม Power BI ได้สร้างตัวอย่างการติดตาม COVID 19 ที่ช่วยให้รัฐและรัฐบาลในท้องถิ่นสามารถเผยแพร่หรือกำหนดรายงานแบบโต้ตอบเกี่ยวกับ COVID-19 ได้ Using Power BI Desktop, they can analyze and visualize COVID-19 data  to keep their communities informed  at the city, county, state, and national levels. จากนั้นใช้ Power BI เผยแพร่ไปยังเว็บพวกเขาสามารถแชร์รายงานแบบสาธารณะเพื่อแจ้งให้ประชาชนทราบ บทความมีสามตัวเลือกที่แตกต่างกันสำหรับการใช้การแสดงภาพแบบโต้ตอบ Power BI ในเนื้อเรื่องสาธารณะบล็อกหรือเว็บไซต์ของคุณเอง

:::image type="content" source="media/sample-covid-19-us/covid-19-us-tracking-sample.png" alt-text="COVID-19 sample with US data":::

บทความนี้ครอบคลุมถึงวิธีการ:

- คัดลอกโค้ดฝังตัวและใส่ลงในเว็บไซต์ของคุณเอง 
- ทำการกำหนดเองเช่นการจัดรูปแบบสถานะที่ระบุ
- เผยแพร่ไปยังบริการ Power BI
- เผยแพร่ไปยังเว็บ 
- Mash up ข้อมูลนี้กับข้อมูลจากแหล่งอื่น 

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะสามารถเริ่มต้นใช้งาน Power BI เพื่อบอกเล่าเรื่องราวของคุณคุณจำเป็นต้องมีข้อกำหนดเบื้องต้นเหล่านี้:

- ดาวน์โหลดตัวอย่างใน [Power BI Desktop](https://powerbi.microsoft.com/desktop/)
- [ลงทะเบียนสำหรับบริการของ Power BI](https://powerbi.microsoft.com/get-started/)

## <a name="option-1-pre-built-embed-code"></a>ตัวเลือกที่ 1: โค้ดฝังตัวที่สร้างไว้ล่วงหน้า

Microsoft ได้เผยแพร่รายงานตัวอย่างและสร้างโค้ดฝังตัวที่เผยแพร่ไปยังเว็บ คุณสามารถใช้โค้ดฝังตัวเพื่อฝังตัวอย่างที่สมบูรณ์รวมถึงมุมมองของชาติและดูรายละเอียดแนวลึกไปยังระดับรัฐและเขตในเว็บไซต์ของคุณเอง ก่อนที่จะเผยแพร่ข้อมูลนี้เราขอแนะนำให้ตรวจทาน การปฏิเสธความรับ[ผิด](#disclaimers)ชอบ

เมื่อต้องการรวมกราฟิกแบบโต้ตอบบนไซต์ของคุณให้คัดลอกและวางโค้ดฝังตัวต่อไปนี้ไปยังตำแหน่งที่คุณต้องการให้กราฟิกแสดงบนเว็บเพจของคุณ  

```
<iframe width="800" height="600" src="https://app.powerbi.com/view?r=eyJrIjoiMmI2ZjExMzItZTcwNy00YmUwLWFlMTAtYTUxYzVjODZmYjA5IiwidCI6ImMxMzZlZWMwLWZlOTItNDVlMC1iZWFlLTQ2OTg0OTczZTIzMiIsImMiOjF9" frameborder="0" allowFullScreen="true"></iframe>
```

โค้ดฝังตัวเป็นองค์ประกอบ iFrame ของ HTML ที่คุณสามารถแทรกลงในเพจ HTML ใดๆได้ ปรับความกว้างและความสูงของ iFrame ให้พอดีภายในไซต์ของคุณ รายงานตัวอย่างถูกสร้างขึ้นที่สัดส่วน16:9 ดังนั้นเลือกขนาดที่รักษามิตินี้ When implemented correctly, the graphic appears without any extra grey borders. It is useful to [review the iFrame sizing tips and tricks](https://docs.microsoft.com/power-bi/service-publish-to-web#tips-and-tricks-for-iframe-height-and-width) when making these changes.

## <a name="option-2-customize-the-sample-power-bi-file"></a>ตัวเลือกที่ 2: Customize the sample Power BI file

The Power BI file contains the data and interactive graphic in a .pbix file format you can edit in Power BI Desktop.  

การกำหนดเองทั่วไปคือการกรองรายงานไปยังสถานะที่ระบุและจากนั้นสร้างโค้ดฝังตัวสำหรับการเผยแพร่ไปยังเว็บของคุณเองสำหรับรายงานแบบกำหนดเองของคุณ

ข้อมูล USAFacts มีให้ภายใต้สิทธิ์การใช้งาน Creative Commons License ที่ต้องระบุแหล่งที่มา Before publishing this data, review the [disclaimers](#disclaimers).

หากต้องการเริ่มต้นใช้งาน [ดาวน์โหลดไฟล์ .pbix (ที่นี่)](https://go.microsoft.com/fwlink/?linkid=2125058)

### <a name="update-your-report"></a>เลือกรายงานของคุณ 

1. ดาวน์โหลดเวอร์ชันล่าสุดของแอปฟรี [Power BI Desktop](https://powerbi.microsoft.com/desktop/)ถ้าคุณยังไม่ได้ใช้งาน 

2. ดาวน์โหลดไฟล์ [Retail Analysis sample .pbix](https://go.microsoft.com/fwlink/?linkid=2125058) แล้วเปิดใน Power BI Desktop

3. หากต้องการกรองรายงานของคุณในเฉพาะรัฐ ให้เลือกลูกศรเพื่อขยายบานหน้าต่างตัวกรอง

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-filters-pane.png" alt-text="ขยายบานหน้าต่างตัวกรอง":::

4. เลือกรัฐที่คุณสนใจ 

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-filter-selection.png" alt-text="เลือกรัฐ":::

5. หากต้องการบันทึกไฟล์ของคุณ ให้เลือก **ไฟล์** > **บันทึก** 

### <a name="refresh-your-report"></a>รีเฟรชรายงานของคุณ 

1. เลือกปุ่ม **รีเฟรช**

    :::image type="content" source="media/sample-covid-19-us/power-bi-desktop-refresh-button.png" alt-text="ปุ่มรีเฟรช":::

2. เลือก **แบบไม่ระบุชื่อ**  > **เชื่อมต่อ** 

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-azure-blob.png" alt-text="เลือกแบบไม่ระบุชื่อ":::

 
3. เลือก **ละเว้นระดับความเป็นส่วนตัว**ถ้าแสดง > **บันทึก** 

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-privacy-levels.png" alt-text="เลือกระดับความเป็นส่วนตัว":::

### <a name="publish-your-report-to-the-power-bi-service"></a>จากนั้น คุณจะเผยแพร่รายงานไปยังบริการของ Power BI

เมื่อคุณปรับแต่งรายงานตามความต้องการของคุณแล้ว [ให้ทำตามขั้นตอนที่อธิบายไว้ที่นี่เพื่อเผยแพร่รายงานของคุณ](../desktop-upload-desktop-files.md) ไปยังบริการ Power BI

### <a name="configure-scheduled-refresh"></a>กำหนดค่าการรีเฟรชตามกำหนดเวลา

เมื่อต้องการให้ข้อมูลในรายงานให้เป็นปัจจุบัน คุณสามารถ [กำหนดค่าการรีเฟรชตามกำหนดการ](../refresh-scheduled-refresh.md) หลังจากที่คุณได้เผยแพร่รายงานของคุณ

เมื่อคุณทำตามขั้นตอน ให้เลือกตัวเลือกต่อไปนี้:

1. วิธีการรับรองความถูกต้องข้อมูลประจำตัวของแหล่งข้อมูล: ไม่ระบุชื่อ
2. การตั้งค่าระดับความเป็นส่วนตัวสำหรับแหล่งข้อมูลนี้: สาธารณะ

เมื่อต้องการทดสอบการตั้งค่าการรีเฟรชของคุณ เลือก [ตัวเลือกรีเฟรชตอนนี้ที่พร้อมใช้งานจากรายการชุดข้อมูล](../refresh-data.md#data-refresh)

ข้อมูลที่รีเฟรชจะถูกโหลดในแต่ละครั้งที่มีการเรียกใช้กำหนดการ โปรดทราบว่าข้อมูลพื้นฐานนั้นจัดทำโดย USAFacts และอาจไม่มีการอัปเดตบ่อยเท่ากำหนดการรีเฟรชของคุณ ตรวจสอบ [เว็บไซต์ USAFacts](https://usafacts.org/visualizations/coronavirus-covid-19-spread-map/)  เพื่อตรวจสอบเมื่อข้อมูลเบื้องต้นได้รับการอัปเดตล่าสุด 

ถ้าคุณต้องการเผยแพร่รายงานแบบกำหนดเองบนเว็บไซต์ของคุณ จะเป็นการดีที่สุดที่จะกำหนดค่าการรีเฟรชตามกำหนดเวลาของคุณเพื่อให้ทำงานได้อย่างน้อยบ่อยครั้งเท่าการอัปเดตข้อมูล USAFacts เนื่องจาก USAFacts อาจรีเฟรชข้อมูลของพวกเขาในเวลาที่แตกต่างกันในแต่ละวันคุณอาจต้องการกำหนดค่ารีเฟรชหลายครั้งในแต่ละวัน 

### <a name="create-a-publish-to-web-embed-code"></a>สร้างโค้ดแบบฝังตัวที่เผยแพร่ไปยังเว็บ 

เมื่อต้องการฝังรายงานแบบกำหนดเองของคุณในเว็บไซต์ของคุณเอง ให้ทำตามคำแนะนำสำหรับวิธีการ [สร้างโค้ดแบบฝังตัวที่มีการเผยแพร่ในเว็บของคุณเอง](../service-publish-to-web.md#how-to-use-publish-to-web)

เมื่อคุณเผยแพร่โค้ดแบบฝังตัวของคุณแล้ว คุณสามารถใช้ iFrame ในกล่องโต้ตอบการยืนยันเพื่อฝังในเว็บไซต์ของคุณ

ถ้าคุณทำการเปลี่ยนแปลงไปยังรายงานใน Power BI Desktop คุณสามารถเผยแพร่และแทนที่รายงานที่มีอยู่ในบริการ Power BI ได้ โค้ดแบบฝังตัวไม่มีการเปลี่ยนแปลง ใช้เวลาประมาณหนึ่งชั่วโมงในการเปลี่ยนแปลงรายงานหรือข้อมูลรีเฟรชเพื่อให้ปรากฏบนเว็บไซต์ของคุณ 

## <a name="option-3-mash-up-data-from-another-source"></a>ตัวเลือกที่ 3: Mash up ข้อมูลจากแหล่งอื่น 

คุณยังสามารถ mash up ข้อมูลในรายงานนี้ด้วยข้อมูลจากแหล่งอื่นได้อีกด้วย ตัวอย่างต่อไปนี้จะยึดตามข้อมูลจาก [มหาวิทยาลัยจอนส์ฮอปกินส์](https://github.com/CSSEGISandData/COVID-19) ก่อนที่จะเผยแพร่ข้อมูลนี้เราขอแนะนำให้ตรวจทาน การปฏิเสธความรับ[ผิด](#disclaimers)ชอบ

1. เลือก **รับข้อมูล** > **เว็บ**

    :::image type="content" source="media/sample-covid-19-us/power-bi-desktop-get-data.png" alt-text="ปุ่มรับข้อมูล":::

2. กรอก URL ต่อไปนี้:

    ```
    https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_confirmed_global.csv
    ```

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-from-web.png" alt-text="เลือกข้อมูลจากเว็บ":::

3. เลือก**ตกลง** 

    > [!NOTE]
    > ลิงก์ที่เผยแพร่โดยมหาวิทยาลัยจอนส์ฮอปกินส์สามารถเปลี่ยนแปลงได้ ตรวจสอบ [หน้า GitHub จอห์นฮอปกินส์](https://github.com/CSSEGISandData/COVID-19) สำหรับข้อมูลล่าสุด

4. เลือก **โหลด** เพื่อโหลดชุดข้อมูลสำหรับกรณีที่ได้รับการยืนยันทั้งหมดทั่วโลก  

    :::image type="content" source="media/sample-covid-19-us/power-bi-covid-19-load-data.png" alt-text="โหลดข้อมูลจากเว็บ":::

    บทความนี้ [เชื่อมต่อกับเว็บเพจต่างๆจาก](../desktop-connect-to-web.md)Power BI Desktop ให้ข้อมูลเพิ่มเติมเกี่ยวกับการโหลดข้อมูลจากเว็บ
    
จากนั้นคุณสามารถใช้ Power BI Desktop เพื่อแสดงภาพข้อมูลได้ สุดท้ายให้ใช้ขั้นตอนใน **ตัวเลือก 2:** [เผยแพร่รายงานของคุณไปยังบริการ Power BI](#publish-your-report-to-the-power-bi-service)  เพื่อเผยแพร่รายงานและสร้างโค้ดแบบฝังตัวแบบกำหนดเอง 


## <a name="about-the-data-source-for-this-report"></a>เกี่ยวกับแหล่งข้อมูลสำหรับรายงานนนี้
รายงานแบบโต้ตอบนี้จะรวมข้อมูลจากศูนย์ควบคุมและป้องกันโรค (CDC) รวมถึงหน่วยงานด้านสาธารณสุขของรัฐและระดับท้องถิ่น ข้อมูลระดับเขตได้รับการยืนยันโดยอ้างอิงจากหน่วยงานของรัฐและท้องถิ่นโดยตรง (ลิงก์)

ข้อมูลจัดหาโดย USAFacts เนื่องจากความถี่ของการอัปเดตข้อมูล จึงอาจไม่สามารถแสดงจำนวนที่แน่นอนที่รายงานโดยหน่วยงานราชการหรือสื่อข่าวสาร สำหรับข้อมูลเพิ่มเติมหรือดาวน์โหลดข้อมูล โปรดเยี่ยมชม [เว็บไซต์ USAFacts](https://usafacts.org/visualizations/coronavirus-covid-19-spread-map/) 

## <a name="disclaimers"></a>ผิด

รายงานและข้อมูลนี้มีให้ "ตามสภาพ" "พร้อมข้อผิดพลาดทั้งหมด" และไม่มีการรับประกันใดๆ Microsoft ไม่มีการรับประกันหรือการการันตีที่ระบุไว้อย่างชัดเจน และไม่รับผิดชอบต่อการรับประกันโดยนัยทั้งหมด ซึ่งรวมถึงอรรถประโยชน์ในเชิงพาณิชย์ ความเหมาะสมสำหรับวัตถุประสงค์เฉพาะกิจ และการไม่ละเมิดลิขสิทธิ์

ข้อมูล USAFacts อยู่ภายใต้สิทธิ์การใช้งาน Creative Commons License หากต้องการใช้งาน ให้อ้างอิง USAFacts เป็นผู้ให้บริการข้อมูลและเชื่อมโยงกลับไปยัง USAFacts สำหรับขั้นตอนการระบุแหล่งที่มาโดยละเอียด โปรดดูส่วน **#MadewithUSAFacts** ของหน้า USAFacts [ ไวรัสโคโรนาในสหรัฐอเมริกา: การจัดทำแผนที่แสดงการแพร่ระบาดของ COVID-19 ในรัฐและประเทศต่างๆ ](https://usafacts.org/visualizations/coronavirus-covid-19-spread-map/)

ข้อมูลจากมหาวิทยาลัยจอนส์ฮอปกินส์เป็นลิขสิทธิ์ของ 2020 Johns Hopkins University,  All rights reserved ข้อมูลมีให้บริการแก่สาธารณะ เพื่อจุดประสงค์ทางการศึกษาการวิจัยทางวิชาการเท่านั้น นี่คือ [ข้อตกลงการใช้งาน](https://github.com/CSSEGISandData/COVID-19/blob/master/README.md) ฉบับเต็ม ของข้อมูลที่แสดงในตัวอย่าง mashup สามารถดูข้อมูลเพิ่มเติมได้จาก [เว็บไซต์ของมหาวิทยาลัยจอนส์ฮอปกินส์](https://coronavirus.jhu.edu/map-faq.html)

## <a name="next-steps"></a>ขั้นตอนถัดไป

[รับตัวอย่างสำหรับ Power BI](../sample-datasets.md)
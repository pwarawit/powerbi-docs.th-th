---
title: Power BI ส่วนจัดแสดง Power BI ที่ผ่านการรับรอง
description: ข้อกำหนดและกระบวนการที่จะส่งวิชวลแบบกำหนดเองเพื่อผ่านการรับรอง และรายการของส่วนการจัดแสดง Power BI ที่ผ่านการรับรองแล้ว
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 05/9/2019
ms.openlocfilehash: c6ecb2eb2346940a22bbd6b7bff5ca0138faa290
ms.sourcegitcommit: 08b73af260ded51daaa6749338cb85db2eab587f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/15/2019
ms.locfileid: "74102605"
---
# <a name="get-a-power-bi-visual-certified"></a>รับการรับรองส่วนการจัดแสดง Power BI

## <a name="what-are-_certified_-power-bi-visuals"></a>ส่วนการจัดแสดง Power BI **_ที่ผ่านการรับรอง_** คืออะไร

ส่วนการจัดแสดง Power BI ที่ได้รับการรับรองคือวิชวลใน **Marketplace** ที่ตรงตามข้อกำหนดรหัส**ที่ระบุไว้** ซึ่งผ่านการทดสอบและได้รับอนุมัติจาก**ทีม Microsoft Power BI team** แล้ว เมื่อวิชวลแบบกำหนดเองที่ได้รับการรับรองแล้ว จะมีคุณลักษณะเพิ่มเติม เช่น คุณสามารถ[ส่งออกไปยัง PowerPoint](../consumer/end-user-powerpoint.md) และคุณสามารถแสดงวิชวลในอีเมลเมื่อผู้ใช้[สมัครใช้งานในหน้ารายงาน](../consumer/end-user-subscribe.md)

**ส่วนการจัดแสดง Power BI ที่ได้รับการรับรอง**ใช้งานเหมือนกับ[ส่วนการจัดแสดง Power BI มาตรฐาน](power-bi-custom-visuals.md) คุณสามารถเพิ่มส่วนการจัดแสดง Power BI ที่ได้รับการรับรองไปยัง**บริการ Power BI**, **รายงาน Power BI Desktop** และดูด้วย **Power BI mobile** และ **Power BI Embedded**  ได้

มีการออกแบบการทดสอบที่ทำขึ้นเพื่อตรวจสอบวิชวลที่ไม่ได้เข้าถึงบริการหรือทรัพยากรภายนอก **Microsoft** *ไม่ใช่*ผู้จัดทำส่วนการจัดแสดง Power BI จากภายนอก และขอแนะนำให้ลูกค้าติดต่อกับผู้จัดทำโดยตรงเพื่อยืนยันฟังก์ชั่นการทำงานของส่วนการจัดแสดงดังกล่าว

ขั้นตอนการรับรองเป็นกระบวนการทางเลือกและขึ้นอยู่กับนักพัฒนาซอฟต์แวร์ที่จะตัดสินใจว่าต้องการให้วิชวลใน marketplace ผ่านการรับรองหรือไม่  

**ส่วนจัดแสดง Power BI ที่ไม่มีการรับรอง**จะได้หมายความว่าไม่ปลอดภัยเสมอไป วิชวลบางอันไม่ผ่านการรับรองเนื่องจากไม่สอดคล้องกับ [ข้อกำหนดในการรับรอง](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements) ตัวอย่างเช่น การเชื่อมต่อกับบริการภายนอก เช่น วิชวลแผนที่หรือวิชวลที่ใช้ไลบรารีเชิงพาณิชย์

คุณเป็นนักพัฒนาเว็บ และสนใจสร้างการแสดงภาพของคุณเอง และเพิ่มเข้าไปใน  **[Microsoft AppSource](https://appsource.microsoft.com)** หรือไม่ ดู  **[การพัฒนาวิชวลแบบกำหนดเองสำหรับ Power BI เพื่อเรียนรู้วิธีการ](visuals/custom-visual-develop-tutorial.md)**

## <a name="removal-of-power-bi-certified-power-bi-visuals"></a>การลบ Power BI ส่วนการจัดแสดง Power BI ที่ได้รับการรับรอง

Microsoft สามารถลบวิชวลออกจาก [รายการที่ผ่านการรับรอง](#list-of-power-bi-visuals-that-have-been-certified) ตามดุลพินิจของ Microsoft

## <a name="getting-a-custom-visualcertified"></a>การทำให้วิชวลแบบกำหนดเองผ่านการรับรอง

### <a name="certification-requirements"></a>ข้อบังคับสำหรับการรับรอง

หากต้องการให้วิชวลแบบกำหนดเองผ่าน[การรับรอง](#get-a-power-bi-visual-certified) ตรวจสอบว่าวิชวลแบบกำหนดเองของคุณสอดคล้องกับข้อกำหนดด้านล่าง ดังนี้  

* ต้องได้รับอนุมัติจาก Microsoft AppSource วิชวลแบบกำหนดเองของคุณควรอยู่ใน [marketplace](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) ของเรา
* วิชวลแบบกำหนดเอง ต้องเขียนด้วย **API รุ่น 2.5** หรือสูงกว่า
* ทีม Power BI สามารถตรวจสอบพื้นที่เก็บโค้ดได้ (ตัวอย่างเช่น ซอร์สโค้ด (JavaSCript หรือ TypeScript) ในรูปแบบที่มนุษย์สามารถอ่านได้ ซึ่งส่งให้เราผ่าน GitHub)

    >[!Note]
    > คุณไม่ต้องแชร์โค้ดของคุณกับ Github ในรูปแบบสาธารณะ
* ข้อกำหนดของที่เก็บรหัส:
   * ต้องมีชุดไฟล์อย่างน้อยดังนี้:
      * .gitignore
      * capabilities.json
      * pbiviz.json
      * package.json
      * package-lock.json
      * tsconfig.json
   * ต้องไม่มีโฟลเดอร์ node_modules (เพิ่ม node_modules ไฟล์ gitingore)
   * **ติดตั้ง npm** คำสั่งต้องไม่ส่งข้อผิดพลาดใดๆ กลับมา
   * **การตรวจสอบ npm**  คำสั่งต้องไม่ส่งกลับคำเตือนใดๆ ที่มีระดับสูงหรือระดับปานกลาง
   * **pbiviz package**คำสั่งต้องไม่ส่งข้อผิดพลาดใดๆ กลับมา
   * ต้องรวม [TSlint จาก Microsoft ](https://www.npmjs.com/package/tslint-microsoft-contrib) โดยไม่มีการกำหนดค่าที่แทนที่และคำสั่งนี้ต้องไม่ส่งกลับข้อผิดพลาดที่ไม่เป็นขุย
   * แพคเกจที่มีการคอมไพล์ของวิชวลแบบกำหนดเองต้องตรงกับแพคเกจที่ส่ง (md5 แฮชของทั้งสองแฟ้มควรเท่ากัน)
* ข้อกำหนดของ Source Code:
   * วิชวลต้องสนับสนุน [การเรนเดอร์อีเวนท์ API](https://microsoft.github.io/PowerBI-visuals/docs/how-to-guide/rendering-events/)
   * ตรวจสอบให้แน่ใจว่าไม่มีการเรียกใช้โค้ดตามอำเภอใจ/dynamic (bad: eval () ไม่ปลอดภัยในการใช้ settimeout (), requestAnimationFrame (), setinterval (ฟังก์ชันบางอย่างที่มีการป้อนข้อมูลของผู้ใช้), เรียกใช้การป้อนข้อมูล/ข้อมูลผู้ใช้)
   * ตรวจสอบให้แน่ใจว่ามีการจัดการ DOM อย่างปลอดภัย (bad: innerHTML, D3. html (< การป้อนข้อมูลผู้ใช้/data > บางรายการ) ให้จัดการให้ถูกต้องสำหรับการป้อนข้อมูลของผู้ใช้ก่อนที่จะเพิ่มลงใน DOM
   * ตรวจสอบให้แน่ใจว่าไม่มีข้อผิดพลาด/ข้อยกเว้น javascript ในคอนโซลของเบราว์เซอร์สำหรับข้อมูลป้อนเข้าใดๆ ผู้ใช้อาจใช้วิชวลของคุณด้วยข้อมูลที่ไม่คาดคิดในช่วงที่แตกต่างกันดังนั้นวิชวลจะต้องไม่ล้มเหลว คุณสามารถใช้รายงานตัวอย่าง [ตัวอย่างรายงานนี้](https://github.com/Microsoft/PowerBI-visuals/raw/gh-pages/assets/reports/large_data.pbix) เป็นชุดข้อมูลทดสอบ

* ถ้าคุณสมบัติใดๆในความสามารถมีการเปลี่ยนแปลง json ตรวจสอบให้แน่ใจว่าพวกเขาไม่ได้แบ่งรายงานของผู้ใช้ที่มีอยู่

* ตรวจสอบให้แน่ใจว่าภาพที่สอดคล้องกับ [คู่มือการใช้งานสำหรับวิชวล Power BI](./guidelines-powerbi-visuals.md#guidelines-for-power-bi-visuals-with-additional-purchases) **ไม่อนุญาตให้ใช้ลายน้ำ**

* ใช้เฉพาะคอมโพเนนต์ OSS สาธารณะที่ตรวจทานได้ (ไลบรารี JS หรือ TypeScript ที่เป็นแบบสาธารณะ) ซอร์สโค้ดมีอยู่สำหรับการตรวจสอบและไม่มีช่องโหว่ที่รู้จัก) เราไม่สามารถยืนยันความถูกต้องของวิชวลแบบกำหนดเองโดยใช้องค์ประกอบเชิงพาณิชย์ได้

* ไม่สามารถเข้าถึงบริการหรือแหล่งข้อมูลภายนอก ซึ่งรวมถึงแต่ไม่จำกัดเพียง ไม่มีคำขอ HTTP/S หรือ WebSocket ออกจาก Power BI ไปยังบริการใดๆ 

> [!TIP]
> เราขอแนะนำให้คุณใช้ EsLint กับชุดกฎความปลอดภัยเริ่มต้น เพื่อทำการตรวจสอบรหัสของคุณก่อนส่งมาให้เรา

## <a name="process-for-submitting-a-custom-visual-for-certification"></a>กระบวนการการส่งวิชวลแบบกำหนดเองไปขอการรับรอง

เมื่อต้องการส่งวิชวลแบบกำหนดเองไปขอการรับรอง:

1. ส่งอีเมลไปยังทีมสนับสนุนส่วนการจัดแสดง Power BI ของ Power BI (pbicvsupport@microsoft.com) ในอีเมล ให้ระบุข้อมูลต่อไปนี้:
    * ชื่อเรื่อง: คำขอการรับรองวิชวล
    * เชื่อมโยงไปยังพื้นที่เก็บบน GitHub ที่มีการโฮสต์ซอร์สโค้ดที่มนุษย์สามารถอ่านได้
    * [ยึดตามข้อกำหนดที่ให้](#certification-requirements)
    * ผ่านการตรวจทานโค้ด

2. ทีมงานส่วนการจัดแสดง Power BI ของ Microsoft จะแจ้งให้คุณทราบเมื่อวิชวลแบบกำหนดเองของคุณได้รับการรับรอง และถูกเพิ่มลงใน[รายการวิชวลที่ผ่านการรับรองแล้ว](#list-of-power-bi-visuals-that-have-been-certified) หรือถูกปฏิเสธพร้อมกับรายงานปัญหาที่ต้องแก้ไข เป็นความรับผิดชอบของนักพัฒนาที่ต้องเปิดช่องทางการติดต่อสื่อสารกับ Microsoft และปรับปรุงวิชวลที่ผ่านการรับรองแล้ว ถ้าจำเป็น

## <a name="list-of-power-bi-visuals-that-have-been-certified"></a>รายการส่วนการจัดแสดง Power BI ที่ผ่านการรับรองแล้ว

| ลิงก์ไปยัง AppSource | ลิงก์ไปยังวิดีโอ |
| --- | --- |
| [ระบบ 3AG - แผนภูมิแท่งที่มีความแปรปรวนแบบสัมพัทธ์](https://appsource.microsoft.com/en/product/power-bi-visuals/WA104381912) | |
| [ระบบ 3AG - แผนภูมิคอลัมน์ที่มีความแปรปรวนแบบสัมพัทธ์](https://appsource.microsoft.com/product/power-bi-visuals/WA104381803) | |
| [Advanced Donut Visual](https://appsource.microsoft.com/product/power-bi-visuals/WA104381941) | |
| [Advanced Network Visualization](https://appsource.microsoft.com/product/power-bi-visuals/WA104381942) | |
| [Advanced TimeSeries Visual](https://appsource.microsoft.com/product/power-bi-visuals/WA104381943) | |
| [Advanced Combo Visual](https://appsource.microsoft.com/product/power-bi-visuals/WA104381944) | |
| [Aster Plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759) | |
| [Beyondsoft Calendar](https://appsource.microsoft.com/product/power-bi-visuals/WA104381096) | |
| [Bowtie Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838) | [วิดีโอ](https://youtu.be/So5xKMSpVJI) |
| [Box and Whisker chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831) | |
| [Box and Whisker chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381351) | [วิดีโอ](https://youtu.be/JoHaFLfhXdo) |
| [Brick Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380836) | [วิดีโอ](https://youtu.be/hA3DOsvn2xY) |
| [Bubble Chart by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381340) | |
| [Bullet Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755) | [วิดีโอ](https://youtu.be/AOlsFYkfkcw) |
| [Bullet Chart by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380953) | [วิดีโอ](https://youtu.be/mtvUNl9bMjA) |
| [Calendar by Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146) | |
| [Candlestick by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380952) | [วิดีโอ](https://youtu.be/nT_18gyRxPo) |
| [Card with States by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380967) | |
| [Chiclet Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380756) | |
| [Chord](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761) | [วิดีโอ](https://youtu.be/AQvd2FhRyCI) |
| [Circular Gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837) | [วิดีโอ](https://youtu.be/9NHXALkBXuY) |
| [Cluster Map](https://appsource.microsoft.com/product/power-bi-visuals/WA104380806) | |
| [Cylindrical Gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874) | [วิดีโอ](https://youtu.be/DgdoWi7Gcxo) |
| [Dial Gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184) | |
| [Dot Plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104380760) | |
| [Dot Plot by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380949) | [วิดีโอ](https://youtu.be/By16pX9KT40) |
| [Drilldown Cartogram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381045) | |
| [Drilldown Choropleth](https://appsource.microsoft.com/product/power-bi-visuals/WA104381044) | |
| [Drill-down column chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380857) | [วิดีโอ](https://youtu.be/lBy2gQQ5YsQ) |
| [Drill-down column chart for time based data](https://appsource.microsoft.com/product/power-bi-visuals/WA104380881) | [วิดีโอ](https://youtu.be/T_mRou18vx0) |
| [Drill-down donut chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858) | [วิดีโอ](https://youtu.be/AUVFrSHmPeo) |
| [Dual KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104380774) | |
| [Dynamic Tooltip by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380983) | [วิดีโอ](https://youtu.be/Z-tl97BpEr0) |
| [Enhanced Scatter](https://appsource.microsoft.com/product/power-bi-visuals/WA104380762) | [วิดีโอ](https://youtu.be/xCfM0cjM4do) |
| [Enlighten Aquarium](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112) | |
| [Enlighten Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380960) | |
| [Enlighten Stack Shuffle](https://appsource.microsoft.com/product/power-bi-visuals/WA104380849) | |
| [Enlighten Waffle Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380850) | |
| [กรองตามรายการของ Devscope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381413) | [วิดีโอ](https://youtu.be/RetEWGwBu0I) |
| [Force-Directed Graph](https://appsource.microsoft.com/product/power-bi-visuals/WA104380764) | [วิดีโอ](https://youtu.be/YsTa7uyJ4sg) |
| [Funnel with Source by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381334) | [วิดีโอ](https://youtu.be/R_EcimsLI8U) |
| [Gantt](https://appsource.microsoft.com/product/power-bi-visuals/WA104380765) | [วิดีโอ](https://youtu.be/qJ7s_KrGiUU) |
| [Gantt Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381364) | [วิดีโอ](https://youtu.be/vJLV9JRCpI8) |
| [Globe Data Bars](https://appsource.microsoft.com/product/power-bi-visuals/WA104381344) | |
| [Grid by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380825) | [วิดีโอ](https://youtu.be/VOPoDJgZfOY) |
| [Hierarchy Chart by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381333) | [วิดีโอ](https://youtu.be/0ZGzJaq_KT4) |
| [Histogram Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380776) | |
| [Histogram with points by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381032) | [วิดีโอ](https://youtu.be/-ILF--wExrw) |
| [Horizontal Funnel by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846) | [วิดีโอ](https://youtu.be/SudZei68PPo) |
| [Image by CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381297) | |
| [Image Grid](https://appsource.microsoft.com/product/power-bi-visuals/WA104381355) | |
| [Infographic Designer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380898) | |
| [KPI Chart by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381432) | |
| [KPI Column by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380996) | [วิดีโอ](https://youtu.be/rU0xoOlIq1U) |
| [KPI Grid โดย MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380947) | [วิดีโอ](https://youtu.be/dM4PvZh71V0) |
| [KPI Indicator](https://appsource.microsoft.com/product/power-bi-visuals/WA104380832) | |
| [KPI Ticker by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380946) | [วิดีโอ](https://youtu.be/cudG4gsZ2V8) |
| [Linear Gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821) | [วิดีโอ](https://youtu.be/7_jFaM30dkc) |
| [LineDot Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380766) | |
| [Mekko Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785) | [วิดีโอ](https://youtu.be/90FLCKpgicA) |
| [หลาย KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381763) | |
| [ภาพรวม โดย CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381477) | |
| [Play Axis (Dynamic Slicer)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380981) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) | [วิดีโอ](https://youtu.be/IvfIP3E6-1Q) |
| [Power KPI Matrix](https://appsource.microsoft.com/product/power-bi-visuals/WA104381299) | [วิดีโอ](https://youtu.be/1enze8pcGzY) |
| [Pulse Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381006) | [วิดีโอ](https://youtu.be/DQWdcQtjDVw) |
| [Quadrant Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381011) | [วิดีโอ](https://youtu.be/ppBnyhqWNC0) |
| [Radar Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380771) | |
| [Ring Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824) | [วิดีโอ](https://youtu.be/pDToHDFHnq8) |
| [Rotating Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381007) | [วิดีโอ](https://youtu.be/d5xBCMmb3hU) |
| [Sankey Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380777) | [วิดีโอ](https://youtu.be/WWP9wVUHGaA) |
| [Scatter Chart by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381703) | |
| [Scroller](https://appsource.microsoft.com/product/power-bi-visuals/WA104381018) | |
| [Smart Filter by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380859) | [วิดีโอ](https://youtu.be/gcJsDDRQq28) |
| [Sparkline by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910) | [วิดีโอ](https://youtu.be/0m3Vnvso9tY) |
| [Graph](https://appsource.microsoft.com/product/power-bi-visuals/WA104380772) | |
| [Sunburst](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767) | |
| [Synoptic Panel by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380873) | |
| [Table Heatmap](https://appsource.microsoft.com/product/power-bi-visuals/WA104380818) | |
| [Tachometer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380937) | [วิดีโอ](https://youtu.be/C3OXdETbS9o) |
| [Text Filter](https://appsource.microsoft.com/product/power-bi-visuals/WA104381309) | |
| [Text Wrapper by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826) | |
| [Thermometer by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847) | [วิดีโอ](https://youtu.be/SPX9mgrAdBc) |
| [ตัวแบ่งเวลา](https://appsource.microsoft.com/product/power-bi-visuals/WA104380798) | |
| [Timeline Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380786) | [วิดีโอ](https://youtu.be/ozMtZ4_NZ10) |
| [ไทม์ไลน์ โดย CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381427) | [วิดีโอ](https://youtu.be/szNi9YgXFJc) |
| [Tornado chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380768) | [วิดีโอ](https://www.youtube.com/watch?v=AQvd2FhRyCI) |
| [Trading Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380823) | [วิดีโอ](https://youtu.be/xhTR6y6J9Ko) |
| [Ultimate Variance](https://appsource.microsoft.com/product/power-bi-visuals/WA104381140) | [วิดีโอ](https://youtu.be/pDYF8iZxERs) |
| [Ultimate Waterfall](https://appsource.microsoft.com/product/power-bi-visuals/WA104380956) | [วิดีโอ](https://youtu.be/0BZsVCQdEkc) |
| [รายชื่อผู้ใช้ โดย CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381426) | |
| [Waffle Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049) | [วิดีโอ](https://youtu.be/1vRqYUsm3Vk) |
| [Word Cloud](https://appsource.microsoft.com/product/power-bi-visuals/WA104380752) | [วิดีโอ](https://youtu.be/AblTenl9fqo) |

## <a name="faq"></a>คำถามที่ถามบ่อย

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการแสดงผลด้วยภาพ ให้ดูที่[คำถามที่ถามบ่อยเกี่ยวกับการแสดงผลด้วยภาพที่ได้รับรองแล้ว](power-bi-custom-visuals-faq.md#certified-power-bi-visuals)

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [พัฒนาภาพแบบกำหนดเองของ Power BI](../developer/custom-visual-develop-tutorial.md)
* [รายการเพลย์ลิสต์ วิชวลแบบกำหนดเองของ Microsoft บน YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
* [การแสดงข้อมูลใน Power BI](../visuals/power-bi-report-visualizations.md)  
* [แสดงภาพแบบกำหนดเองใน Power BI](power-bi-custom-visuals.md)  
* [การเผยแพร่ส่วนการจัดแสดง Power BI ไปยัง Microsoft AppSource](../developer/office-store.md)  

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)

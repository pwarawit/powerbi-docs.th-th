---
title: ส่วนจัดแสดง Power BI ที่ผ่านการรับรอง
description: ข้อกำหนดและกระบวนการที่จะส่งวิชวลแบบกำหนดเองเพื่อผ่านการรับรอง และรายการของส่วนการจัดแสดง Power BI ที่ผ่านการรับรองแล้ว
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 12/02/2019
ms.openlocfilehash: 0a39496ade27cd45fae116eea92ef4b472e04582
ms.sourcegitcommit: 5bb62c630e592af561173e449fc113efd7f84808
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/11/2019
ms.locfileid: "74999755"
---
# <a name="get-a-power-bi-visual-certified"></a>รับการรับรองส่วนการจัดแสดง Power BI

ส่วนการจัดแสดง Power BI ที่ได้รับการรับรองคือวิชวลใน *Marketplace* ที่ตรงตามข้อกำหนดรหัส*ที่ระบุไว้* ซึ่งผ่านการทดสอบและได้รับอนุมัติจาก*ทีม Microsoft Power BI team* แล้ว มีการออกแบบการทดสอบที่ทำขึ้นเพื่อตรวจสอบวิชวลที่ไม่ได้เข้าถึงบริการหรือทรัพยากรภายนอก

ส่วนการจัดแสดง Power BI ที่ได้รับการรับรองและ[ส่วนการจัดแสดง Power BI มาตรฐาน](power-bi-custom-visuals.md)ใช้งานเหมือนกัน คุณสามารถเพิ่มวิชวลแบบกำหนดเองที่ได้รับการรับรองไปยัง[Power BI Desktop](../desktop-what-is-desktop.md), [บริการ Power BI ](../power-bi-service-overview.md) และดูด้วย [Power BI mobile](../consumer/mobile/mobile-apps-for-mobile-devices.md) และ [Power BI Embedded ](embedding.md) ได้

การรับรองเป็นกระบวนการที่ไม่บังคับให้ดำเนินการ ขึ้นอยู่กับนักพัฒนาจะเป็นผู้ตัดสินใจว่าพวกเขาต้องการให้การจัดแสดง Power BI ใน marketplace สมควรได้รับการรับรองหรือไม่ เมื่อการจัดแสดง Power BI ได้รับการรับรองแล้ว จะมีคุณลักษณะเพิ่มเติม เช่น คุณสามารถ[ส่งออกไปยัง PowerPoint](../consumer/end-user-powerpoint.md) หรือแสดงวิชวลในอีเมลเมื่อผู้ใช้[สมัครใช้งานในหน้ารายงาน](../consumer/end-user-subscribe.md)

ส่วนจัดแสดง Power BI ที่ยังไม่ได้รับการรับรองไม่จำเป็นต้องหมายถึงวิชวลที่ไม่ปลอดภัย วิชวลบางอันไม่ผ่านการรับรองเนื่องจากไม่สอดคล้องกับ [ข้อกำหนดในการรับรอง](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements) ตัวอย่างเช่น การเชื่อมต่อกับบริการภายนอก เช่น วิชวลแผนที่หรือวิชวลที่ใช้ไลบรารีเชิงพาณิชย์

หากคุณเป็นนักพัฒนาเว็บที่สนใจในการสร้างวิชวล Power BI ของคุณเองและต้องการเพิ่มงานของคุณไปยัง [Microsoft AppSource](https://appsource.microsoft.com) คุณสามารถเริ่มต้นใช้งานได้ในบทช่วยสอน  [Developing a Power BI visual](visuals/custom-visual-develop-tutorial.md)

> [!NOTE]
> **Microsoft***ไม่ใช่*บริษัทบุคคลที่สามที่สร้าง Power BI วิชวล เพื่อยืนยันการใช้งานอย่างเต็มประสิทธิภาพจากวิชวลบุคคลที่สามเราแนะนำให้ลูกค้าติดต่อผู้เขียนโดยตรงเพื่อยืนยันการทำงานของวิชวลดังกล่าว

> [!IMPORTANT]
> Microsoft สามารถลบ[Power BI](#list-of-power-bi-visuals-that-have-been-certified) วิชวลออกจาก รายการที่ผ่านการรับรอง ตามดุลพินิจของ Microsoft

## <a name="certification-requirements"></a>ข้อบังคับสำหรับการรับรอง

เพื่อที่จะได้รับ[การรับรอง](#get-a-power-bi-visual-certified) Power BI visual ต้องแน่ใจว่าวิชวล Power BI ของคุณเป็นไปตามกฏและข้อกำหนดที่มีรายการในส่วนนี้แล้ว 

> [!TIP]
> เราขอแนะนำให้คุณใช้ EsLint กับชุดกฎความปลอดภัยเริ่มต้น เพื่อทำการตรวจสอบรหัสของคุณก่อนส่งมาให้เรา

* Microsoft Seller Dashboard หรือได้รับการอนุมัติแล้วจาก Partner Center วิชวล Power BI ของคุณควรอยู่ใน [marketplace](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) ของเรา
* วิชวล Power BI ต้องเขียนด้วย *API รุ่น 2.5* หรือสูงกว่า
* ที่เก็บโค้ดพรัอมตรวจสอบโดยทีมงาน Power BI ยกตัวอย่างเช่น รูปแบบโค้ดต้นทางที่สามารถอ่านได้ (JavaScript or TypeScript) ต้องมีพร้อมให้เราใน GitHub.

    >[!NOTE]
    > คุณไม่ต้องแชร์โค้ดของคุณกับ Github ในรูปแบบสาธารณะ

* ข้อกำหนดของที่เก็บรหัส:
  * ต้องมีไฟล์นามสกุลเหล่านี้รวมอยู่ในนั้นด้วย:
    * .gitignore
    * capabilities.json
    * pbiviz.json
    * package.json
    * package-lock.json
    * tsconfig.json
  * ต้องไม่มีโฟลเดอร์ *node_modules* (เพิ่ม *node_modules* ไฟล์ gitingore)
  * *ติดตั้ง npm* คำสั่งต้องไม่ส่งข้อผิดพลาดใดๆ กลับมา
  * *การตรวจสอบ npm*  คำสั่งต้องไม่ส่งกลับคำเตือนใดๆ ที่มีระดับสูงหรือระดับปานกลาง
  * *pbiviz package*คำสั่งต้องไม่ส่งข้อผิดพลาดใดๆ กลับมา
  * ต้องมีไฟล์ [TSlint จาก Microsoft](https://www.npmjs.com/package/tslint-microsoft-contrib) ที่ไม่มีการตั้งค่าแทนที่ คำสั่งนี้ต้องไม่ส่งข้อ lint ผิดพลาดใดๆ กลับมา
   * แพคเกจที่มีการคอมไพล์ของวิชวล Power BI จะต้องตรงกับแพคเกจที่ส่ง (md5 แฮชของทั้งสองแฟ้มต้องเท่ากัน)
* ข้อกำหนดของ Source Code:
   * วิชวลPower BI ต้องสนับสนุน [การเรนเดอร์อีเวนท์ API](https://microsoft.github.io/PowerBI-visuals/docs/how-to-guide/rendering-events/)
   * ตรวจสอบให้แน่ใจว่าไม่มีการเรียกใช้โค้ดตามอำเภอใจ/dynamic (bad: eval () ไม่ปลอดภัยในการใช้ settimeout (), requestAnimationFrame (), setinterval (ฟังก์ชันบางอย่างที่มีการป้อนข้อมูลของผู้ใช้), เรียกใช้การป้อนข้อมูล/ข้อมูลผู้ใช้)
   * ตรวจสอบให้แน่ใจว่ามีการจัดการ DOM อย่างปลอดภัย (bad: innerHTML, D3. html (< การป้อนข้อมูลผู้ใช้/data > บางรายการ) ให้จัดการให้ถูกต้องสำหรับการป้อนข้อมูลของผู้ใช้ก่อนที่จะเพิ่มลงใน DOM
   * ตรวจสอบให้แน่ใจว่าไม่มีข้อผิดพลาดหรือข้อยกเว้น javascript ในคอนโซลของเบราว์เซอร์สำหรับข้อมูลป้อนเข้าใดๆ ผู้ใช้อาจใข้งานวิชวล Power BI ในขอบเขตข้อมูลที่ต่างกัน ดังนั้นวิชวลจะไม่สามารถล้มเหลวได้ คุณสามารถใช้ [รายงานอย่างง่าย](https://github.com/Microsoft/PowerBI-visuals/raw/gh-pages/assets/reports/large_data.pbix) นี้เป็นตัวทดสอบชุดข้อมูล

* ถ้ามีคุณสมบัติใดใน *capabilities.json* ถูกเปลี่ยน ต้องแน่ใจว่าการเปลี่ยนแปลงนั้นจะไม่กระทบต่อผู้ใช้งานคนอื่นๆ

* ต้องแน่ใจว่าวิชวล Power BI ต้องเป็นไปตาม [คู่มือสำหรับวิชวล Power BI](./guidelines-powerbi-visuals.md)
    
* โค้ดของคุณสามารถใช้องค์ประกอบ OSS ที่ตรวจสอบแล้วเท่านั้นเช่น Javascript หรือไลบราลี่ TypeScript โค้ดต้นทางจะต้องพร้อมสำหรับการตรวจสอบและต้องไม่มีค่าผิดปกติเข้ามา เราไม่สามารถยืนยันความถูกต้องของวิชวลแบบกำหนดเองโดยใช้องค์ประกอบเชิงพาณิชย์ได้

* วิชวล Power BI ต้องไม่เข้าถึงบริการหรือแหล่งข้อมูลภาพนอก ยกตัวอย่างเช่น ไม่มีการใช้ HTTP/S หรือ WebSocket ที่สามารถออกไปจาก Power BI เพื่อไปยังบริการอื่นได้ 

## <a name="submitting-a-power-bi-visual-for-certification"></a>การยื่นใบรับรองวิชวล Power BI

คุณสามารถยื่นคำร้องเพื่อให้มีการรับรองวิชวล Power BI โดยทีม Power BI ผ่าน Partner Center

>[!TIP]
>กระบวนการขอใบรับรองThe Power BI อาจใช้เวลาสักระยะ หากคุณกำลังสร้างวิชวล Power BI ใหม่ เราแนะนำให้คุณเผยแพร่วิชวล Power BI ผ่าน Partner Center ก่อนที่คุณจะขอใบรับรอง Power BI กระบวนการนี้เพื่อให้แน่ใจว่าการเผยแพร่วิชวลของคุณจะไม่ถูกเลื่อนออกไป

การยื่นคำร้องขอการรับรอง Power BI:

1. ลงชื่อเข้าใช้ใน Partner Center
2. ตรงบริเวณ **หน้าเพจภาพรวม**, ให้เลือกวิชวล Power BI ของคุณและไปยังหน้าตั้งค่า **ผลิตภัณฑ์**
3. เลือกทำเครื่องหมายในกล่องกาเครื่องหมาย **ยื่นคำร้องขอใบรับรอง Power BI**
4. ในหน้า **ตรวจสอบและเผยแพร่**ที่อยู่ในกล่องข้อความ **หมายเหตุสำหรับการขอใบรับรอง**ให้ระบุลิงก์ที่จะนำไปสู่โค้ดต้นทาง และต้องใช้ข้อมูลประจำตัวเพื่อเข้าสู่ลิงก์

>[!NOTE]
> ถ้าคุณยังอยู่ระหว่างขั้นตอนการยื่นคำร้องวิชวล Power BI และคุณต้องใช้ [แดชบอร์ดผู้ขาย](https://docs.microsoft.com/office/dev/store/use-the-seller-dashboard-to-submit-to-the-office-store) (เครื่องมือการจัดการรุ่นเก่า) ให้ตรวจสอบขั้นตอน [กระบวนการยื่นคำร้องขอใบรับรองแดชบอร์ดผู้ขาย](seller-dashboard.md#seller-dashboard-certification-submission-process)

## <a name="list-of-power-bi-visuals-that-have-been-certified"></a>รายการส่วนการจัดแสดง Power BI ที่ผ่านการรับรองแล้ว

| ลิงก์ | Video |
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

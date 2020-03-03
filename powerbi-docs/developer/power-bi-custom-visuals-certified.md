---
title: ส่วนจัดแสดง Power BI ที่ผ่านการรับรอง
description: ข้อกำหนดและกระบวนการที่จะส่งวิชวลแบบกำหนดเองสำหรับการรับรองและรายการของวิชวล Power BI ที่ผ่านการรับรอง
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 02/17/2020
ms.openlocfilehash: 52a99380f8e1afc39ddfc59a401418e61fe6ad58
ms.sourcegitcommit: ec4d2d0f52d737e8e0583f6a7b16e6fd87382510
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/28/2020
ms.locfileid: "77782409"
---
# <a name="get-a-power-bi-visual-certified"></a>รับการรับรองส่วนการจัดแสดง Power BI

วิชวล Power BI ที่ได้รับการรับรองคือวิชวล Power BI ใน [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=power-bi-visuals) ที่ตรงตามข้อกำหนดโค้ดทีม Microsoft Power BI team [แล้ว](#certification-requirements) วิชวลเหล่านี้จะได้รับการทดสอบเพื่อตรวจสอบว่าไม่สามารถเข้าถึงบริการภายนอกหรือแหล่งข้อมูล และทำตามรูปแบบการเขียนโค้ดที่ปลอดภัยและแนวทาง

เมื่อการจัดแสดง Power BI ได้รับการรับรองแล้ว จะมีคุณลักษณะเพิ่มเติม เช่น คุณสามารถ[ส่งออกไปยัง PowerPoint](../consumer/end-user-powerpoint.md) หรือแสดงวิชวลในอีเมลเมื่อผู้ใช้[สมัครใช้งานในหน้ารายงาน](../consumer/end-user-subscribe.md)

กระบวนการการรับรองที่เป็นทางเลือก วิชวล power BI ที่ไม่ได้รับการรับรองไม่จำเป็นต้องใช้วิชวล Power BI ที่ไม่ปลอดภัย วิชวล Power BI บางอันไม่ผ่านการรับรองเนื่องจากไม่สอดคล้องกับ [ข้อกำหนดในการรับรอง](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements)หนึ่งรายการหรือมากกว่านั้น สำหรับตัวอย่าง เช่น แผนที่วิชวล Power BI ที่เชื่อมต่อกับบริการภายนอกหรือวิชวล Power BI ที่ใช้ไลบรารีเชิงพาณิชย์

> [!NOTE]
> Microsoftไม่ใช่บริษัทบุคคลที่สามที่สร้าง Power BI วิชวล เพื่อยืนยันการใช้งานอย่างเต็มประสิทธิภาพจากวิชวลบุคคลที่สาม แนะนำให้ลูกค้าติดต่อผู้เขียนของวิชวลโดยตรง

## <a name="certification-requirements"></a>ข้อบังคับสำหรับการรับรอง

ในการรับ[การรับรอง](#get-a-power-bi-visual-certified) วิชวล Power BI ของคุณ ต้องแน่ใจว่าวิชวล Power BI ของคุณเป็นไปตามรายการข้อกำหนดในส่วนนี้แล้ว 

### <a name="general-requirements"></a>ข้อกำหนดทั่วไป

วิชวล Power BI ของคุณต้องได้รับการอนุมัติจากแดชบอร์ดของผู้ขายหรือศูนย์คู่ค้า เราขอแนะนำให้วิชวล Power BI ของคุณอยู่ใน [AppSource](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) แล้ว ในการเรียนสิธีเผยแพร่วิชวล Power BI ไปยัง AppSource ดู[การเผยแพร่วิชวล Power BI ไปยังศูนย์คู่ค้า](office-store.md)

ก่อนที่จะส่งวิชวล Power BI ของคุณเพื่อรับรองความถูกต้อง ตรวจสอบว่าเป็นไปตาม [แนวทางสำหรับวิชวล Power BI](./guidelines-powerbi-visuals.md)

เมื่อส่งวิชวล Power BI ให้ตรวจสอบให้แน่ใจว่าแพคเกจที่แปลแล้วตรงกับแพคเกจที่ส่งเข้าไป

### <a name="code-repository-requirements"></a>ข้อกำหนดของที่เก็บโค้ด:

แม้ว่าคุณจะไม่จำเป็นต้องแชร์รหัสของคุณใน GitHub แบบสาธารณะ การเก็บโค้ดก็จะพร้อมใช้งานสำหรับการตรวจทานโดยทีม Power BI วิธีที่ดีที่สุดในการทำเช่นนี้คือการให้แหล่งโค้ด (JavaScript หรือ TypeScript) ใน GitHub

ที่เก็บต้องมีสิ่งต่อไปนี้:
* รหัสสำหรับการแสดงผลด้วยภาพของ Power BI เดียวเท่านั้น ซึ่งไม่สามารถมีโค้ดสำหรับวิชวล Power BI หลายหรือรหัสที่ไม่เกี่ยวข้อง
* สาขาที่ชื่อว่า**ใบรับรอง** (จำเป็นต้องใช้ตัวพิมพ์เล็ก) แหล่งโค้ดในสาขานี้ต้องตรงกับแพคเกจที่ส่งไป โค้ดนี้สามารถอัปเดตได้ระหว่างขั้นตอนการส่งครั้งถัดไป ถ้าคุณกำลังส่งวิชวล Power BI ของคุณใหม่

ถ้าวิชวล Power BI ของคุณใช้แพคเกจ npm แบบส่วนตัวหรือโมดูลย่อย git คุณต้องให้การเข้าถึงที่เก็บข้อมูลเพิ่มเติมที่มีโค้ดนี้

เพื่อทำความเข้าใจวิธีการดูที่เก็บข้อมูลการแสดงผลด้วยภาพของ Power BI ให้ตรวจสอบที่เก็บ GitHub สำหรับ [แผนภูมิแท่งตัวอย่างของ Power BI](https://github.com/microsoft/PowerBI-visuals-sampleBarChartgi)

### <a name="file-requirements"></a>ข้อกำหนดไฟล์

ใช้ API รุ่นล่าสุดเพื่อเขียนวิชวล Power BI

ที่เก็บต้องมีไฟล์ต่อไปนี้:
* **gitignore**-เพิ่ม `node_modules` ไปยังแฟ้มนี้ โค้ดไม่สามารถรวมโฟลเดอร์ *node_modules* ได้
* **capabilities.json** - ถ้าคุณกำลังส่งเวอร์ชันที่ใหม่กว่าของวิชวล Power BI ของคุณด้วยการเปลี่ยนแปลงคุณสมบัติในไฟล์นี้ โปรดตรวจสอบว่าไฟล์นั้นไม่ได้แบ่งแยกรายงานสำหรับผู้ใช้ที่มีอยู่
* **pbiviz.json**
* **pbiviz.json**
* **pbiviz.json**
* **pbiviz.json**

### <a name="command-requirements"></a>ข้อกำหนดคำสั่ง

ตรวจสอบให้แน่ใจว่าคำสั่งต่อไปนี้ไม่ได้ส่งกลับข้อผิดพลาดใดๆ

* `npm install`
* `pbiviz package`
* `npm audit` - ต้องไม่ส่งกลับคำเตือนใดๆ ที่มีระดับสูงหรือระดับปานกลาง
* [TSlint จาก Microsoft](https://www.npmjs.com/package/tslint-microsoft-contrib) ที่ไม่มีการตั้งค่าแทนที่ คำสั่งนี้ต้องไม่ส่งข้อ lint ผิดพลาดใดๆ กลับมา

### <a name="compiling-requirements"></a>ข้อกำหนดตัวแปลโปรแกรม

ใช้ [เครื่องมือ-วิชวล-powerbi](https://www.npmjs.com/package/powerbi-visuals-tools) รุ่นล่าสุดเพื่อเขียนวิชวล Power BI

คุณต้องคอมไพล์วิชวล Power BI ของคุณด้วย `pbiviz package` ถ้าคุณกำลังใช้สคริปต์การสร้างของคุณเองให้  `npm run package`คำสั่งสร้างแบบกำหนดเอง



### <a name="source-code-requirements"></a>ข้อกำหนดของแหล่งโค้ด

ตรวจสอบว่าคุณได้ทำตามรายการนโยบาย [ การรับรองความถูกต้องของ Power BI](https://docs.microsoft.com/legal/marketplace/certification-policies#1200-power-bi-visuals-additional-certification) หากการส่งของคุณไม่เป็นไปตามหลักเกณฑ์เหล่านี้ อีเมลที่ใช้ในการปฏิเสธจากศูนย์คู่ค้าจะรวมถึงหมายเลขนโยบายที่แสดงรายการอยู่ในลิงก์นี้

ปฏิบัติตามข้อกำหนดของโค้ดที่แสดงด้านล่างเพื่อตรวจสอบให้แน่ใจว่าโค้ดของคุณอยู่ในแนวทางด้วยนโยบายการรับรอง Power BI  

**ที่จำเป็น**
* มีเพียงการใช้องค์ประกอบ OSS ที่ตรวจสอบแล้วเท่านั้น เช่น Javascript หรือไลบราลี่ TypeScript
* โค้ดต้องสนับสนุน [การเรนเดอร์อีเวนท์ API](./visuals/event-service.md)
* ตรวจสอบให้แน่ใจว่า DOM ได้รับการจัดการอย่างปลอดภัย ใช้สุขอนามัยสำหรับการข้อมูลที่ป้อนเข้าหรือข้อมูลของผู้ใช้ก่อนที่จะเพิ่มลงใน DOM
* สามารถใช้ [รายงานตัวอย่าง](https://github.com/Microsoft/PowerBI-visuals/raw/gh-pages/assets/reports/large_data.pbix) นี้เป็นตัวทดสอบชุดข้อมูล

**ไม่ได้รับอนุญาต**
* การเข้าถึงบริการหรือแหล่งข้อมูลภายนอก ยกตัวอย่างเช่น ไม่มีการใช้ HTTP/S หรือ WebSocket ที่สามารถออกไปจาก Power BI เพื่อไปยังบริการอื่นได้
* ใช้ `innerHTML`หรือ `D3.html(user data or user input)`
* ข้อผิดพลาด JavaScript หรือข้อยกเว้นในคอนโซลของเบราว์เซอร์สำหรับข้อมูลที่ป้อนเข้าใดๆ
* รหัสที่กำหนดเองหรือแบบไดนามิก เช่น `eval()`การใช้ที่ไม่ปลอดภัยของ `settimeout()` `requestAnimationFrame()` `setinterval(user input function)`และข้อมูลที่ป้อนเข้าหรือข้อมูลของผู้ใช้
* ทำให้ JavaScript files หรือโครงการเล็กลง

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

### <a name="private-repository-submission-process"></a>กระบวนการส่งที่เก็บแบบส่วนตัว

หากคุณกำลังใช้ที่เก็บส่วนตัวเช่น GitHub เพื่อส่งการแสดงผลด้วยภาพของ Power BI สำหรับใบรับรอง ให้ทำตามคำแนะนำในส่วนนี้
1. สร้างบัญชีใหม่สำหรับทีมการตรวจสอบความถูกต้อง
2. กำหนดค่า[การรับรองความถูกต้องแบบสองปัจจัย](https://help.github.com/github/authenticating-to-github/securing-your-account-with-two-factor-authentication-2fa)สำหรับบัญชีของคุณ
3. [สร้างชุดรหัสการกู้คืนใหม่](https://help.github.com/github/authenticating-to-github/configuring-two-factor-authentication-recovery-methods#generating-a-new-set-of-recovery-codes)
4. เมื่อส่งการแสดงผลด้วยภาพของ Power BI ของคุณ ให้ป้อนข้อมูลต่อไปนี้:
    * ลิงก์ไปยังที่เก็บ
    * ข้อมูลประจำตัวสำหรับเข้าสู่ระบบ (รวมถึงรหัสผ่าน)
    * รหัสการกู้คืน
    * สิทธิ์แบบอ่านเท่านั้นไปยังบัญชีของเรา ([pbicvsupport](https://github.com/pbicvsupport))

## <a name="certified-power-bi-visuals"></a>ส่วนจัดแสดง Power BI ที่ผ่านการรับรอง

การแสดง Power BI ที่ได้รับการรับรองจะระบุอยู่ด้านล่าง คลิกที่ลิงก์เพื่อเปิดการแสดง Power BI ใน AppSource ถ้าวิดีโอพร้อมใช้งาน คุณสามารถคลิกที่ลิงก์วิดีโอเพื่อรับชม

* [ระบบ 3AG - แผนภูมิแท่งที่มีความแปรปรวนแบบสัมบูรณ์](https://appsource.microsoft.com/product/power-bi-visuals/WA104381802)
*  [ระบบ 3AG - แผนภูมิแท่งที่มีความแปรปรวนแบบสัมพัทธ์](https://appsource.microsoft.com/product/power-bi-visuals/WA104381912)
*  [ระบบ 3AG - แผนภูมิคอลัมน์ที่มีความแปรปรวนแบบสัมพัทธ์](https://appsource.microsoft.com/product/power-bi-visuals/WA104381803)
*  [ระบบ 3AG - แผนภูมิคอลัมน์ที่มีความแปรปรวน](https://appsource.microsoft.com/product/power-bi-visuals/WA104381724)
* [Advanced Donut Visual (รุ่นเต็ม)](https://appsource.microsoft.com/product/power-bi-visuals/WA104381941)
*  [Advanced Donut Visual (รุ่นไลท์)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858)
*  [Advanced Graph Visual](https://appsource.microsoft.com/product/power-bi-visuals/WA104382086)
*  [Advanced Network Visualization](https://appsource.microsoft.com/product/power-bi-visuals/WA104381942)
*  [Advanced TimeSeries Visual (รุ่นเต็ม)](https://appsource.microsoft.com/product/power-bi-visuals/WA104381943)
*  [Aster Plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759)
*  [Beyondsoft Calendar](https://appsource.microsoft.com/product/power-bi-visuals/WA104381096)
*  [Bowtie Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838)
*  [Box and Whisker chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831)
* [Box and Whisker chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381351)
*  [Brick Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380836)
*  [Bubble Chart by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381340)
*  [Bullet Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755),  **[ลิงก์วิดีโอ](https://youtu.be/AOlsFYkfkcw)**
* [Bullet Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380755)
*  [Bullet Chart by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380953), **[ลิงก์วิดีโอ](https://youtu.be/mtvUNl9bMjA)**
* [Calendar by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381844)
*  [Calendar by Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146)
*  [Candlestick by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380952), **[ลิงก์วิดีโอ](https://youtu.be/nT_18gyRxPo)**
*  [Card with States by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380967)
*  [Chiclet Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380756)
*  [Chord](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761), **[ลิงก์วิดีโอ](https://youtu.be/AQvd2FhRyCI)**
*  [Circular Gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837)
*  [Cluster Map](https://appsource.microsoft.com/product/power-bi-visuals/WA104380806)
* [Custom Calendar by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381179)
* [Cylindrical Gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874)
*  [Dial Gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184)
[Dot Plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104380760)
*  [Dot Plot by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380949), **[ลิงก์วิดีโอ](https://youtu.be/By16pX9KT40)**
*  [Drilldown Cartogram](https://appsource.microsoft.com/product/power-bi-visuals/WA104381045)
*  [Drilldown Choropleth](https://appsource.microsoft.com/product/power-bi-visuals/WA104381044)
*  [Drill-down column chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380857), **[ลิงก์วิดีโอ](https://youtu.be/lBy2gQQ5YsQ)**
*  [Drill-down column chart for time based data](https://appsource.microsoft.com/product/power-bi-visuals/WA104380881), **[ลิงก์วิดีโอ](https://youtu.be/T_mRou18vx0)**
*  [Drill-down donut chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858), **[ลิงก์วิดีโอ](https://youtu.be/AUVFrSHmPeo)**
*  [Dual KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104380774)
*  [Dynamic Tooltip by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380983)
*  [Enhanced Scatter](https://appsource.microsoft.com/product/power-bi-visuals/WA104380762), **[ลิงก์วิดีโอ](https://youtu.be/xCfM0cjM4do)**
*  [Enlighten Aquarium](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112)
*  [Enlighten Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380960)
*  [Enlighten Stack Shuffle](https://appsource.microsoft.com/product/power-bi-visuals/WA104380849)
*  [Enlighten Waffle Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380850)
*  [Filter by List by Devscope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381413), **[ลิงก์วิดีโอ](https://youtu.be/RetEWGwBu0I)**
*  [Force-Directed Graph](https://appsource.microsoft.com/product/power-bi-visuals/WA104380764), **[ลิงก์วิดีโอ](https://youtu.be/YsTa7uyJ4sg)**
*  [Funnel with Source by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381334)
*  [Gantt](https://appsource.microsoft.com/product/power-bi-visuals/WA104380765), **[ลิงก์วิดีโอ](https://youtu.be/qJ7s_KrGiUU)**
* [Gantt Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381364)
*  [Globe Data Bars](https://appsource.microsoft.com/product/power-bi-visuals/WA104381344)
*  [Grid by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380825)
*  [Hierarchy Chart by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381333), **[ลิงก์วิดีโอ](https://youtu.be/0ZGzJaq_KT4)**
*  [Histogram Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380776)
*  [Histogram with points by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381032)
* [Horizontal bar chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381230)
*  [Horizontal Funnel by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846)
*  [Image by CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381297)
*  [Image Grid](https://appsource.microsoft.com/product/power-bi-visuals/WA104381355)
*  [Infographic Designer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380898)
*  [KPI Chart by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381432)
*  [KPI Column by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380996)
*  [KPI Grid โดย MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380947)
*  [KPI Indicator](https://appsource.microsoft.com/product/power-bi-visuals/WA104380832)
*  [KPI Ticker by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380946)
* [Linear Gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821)
*  [LineDot Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380766)
*  [Mekko Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785), **[ลิงก์วิดีโอ](https://youtu.be/90FLCKpgicA)**
*  [หลาย KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381763)
*  [ภาพรวม โดย CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381477)
*  [Play Axis (Dynamic Slicer)](https://appsource.microsoft.com/product/power-bi-visuals/WA104380981)
*  [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083), [ลิงก์วิดีโอ](https://youtu.be/IvfIP3E6-1Q)
*  [Power KPI Matrix](https://appsource.microsoft.com/product/power-bi-visuals/WA104381299), **[ลิงก์วิดีโอ](https://youtu.be/1enze8pcGzY)**
*  [Pulse Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381006), **[ลิงก์วิดีโอ](https://youtu.be/DQWdcQtjDVw)**
*  [Quadrant Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381011)
*  [Radar Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380771)
*  [Ring Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824)
*  [Rotating Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381007)
*  [Sankey Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380777), **[ลิงก์วิดีโอ](https://youtu.be/WWP9wVUHGaA)**
*  [Scatter Chart by Akvelon](https://appsource.microsoft.com/product/power-bi-visuals/WA104381703)
*  [Scroller](https://appsource.microsoft.com/product/power-bi-visuals/WA104381018)
*  [Smart Filter by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380859), **[ลิงก์วิดีโอ](https://youtu.be/gcJsDDRQq28)**
*  [Sparkline by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910), **[ลิงก์วิดีโอ](https://youtu.be/0m3Vnvso9tY)**
*  [Graph](https://appsource.microsoft.com/product/power-bi-visuals/WA104380772)
*  [Sunburst](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767)
*  [Synoptic Panel by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380873)
*  [Table Heatmap](https://appsource.microsoft.com/product/power-bi-visuals/WA104380818)
*  [Tachometer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380937), **[ลิงก์วิดีโอ](https://youtu.be/C3OXdETbS9o)**
*  [Text Filter](https://appsource.microsoft.com/product/power-bi-visuals/WA104381309)
*  [Text Wrapper by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826)
*  [Thermometer by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847)
*  [ตัวแบ่งเวลา](https://appsource.microsoft.com/product/power-bi-visuals/WA104380798)
*  [Timeline Slicer](https://appsource.microsoft.com/product/power-bi-visuals/WA104380786), **[ลิงก์วิดีโอ](https://youtu.be/ozMtZ4_NZ10)**
*  [Timeline by CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381427), [ลิงก์วิดีโอ](https://youtu.be/szNi9YgXFJc)
*  [Tornado chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380768), **[ลิงก์วิดีโอ](https://www.youtube.com/watch?v=AQvd2FhRyCI)**
*  [Trading Chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380823)
* [Ultimate KPI Card](https://appsource.microsoft.com/product/power-bi-visuals/WA104381977)
*  [Ultimate Variance](https://appsource.microsoft.com/product/power-bi-visuals/WA104381140), **[ลิงก์วิดีโอ](https://youtu.be/pDYF8iZxERs)**
*  [Ultimate Waterfall](https://appsource.microsoft.com/product/power-bi-visuals/WA104380956), **[ลิงก์วิดีโอ](https://youtu.be/0BZsVCQdEkc)**
*  [รายชื่อผู้ใช้ โดย CloudScope](https://appsource.microsoft.com/product/power-bi-visuals/WA104381426)
*  [Venn Diagram by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104381231)
*  [Violin Plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104381947)
*  [Visio Visual](https://appsource.microsoft.com/product/power-bi-visuals/WA104381132)
*  [Waffle Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049), **[ลิงก์วิดีโอ](https://youtu.be/1vRqYUsm3Vk)**
*  [Word Cloud](https://appsource.microsoft.com/product/power-bi-visuals/WA104380752), **[ลิงก์วิดีโอ](https://youtu.be/AblTenl9fqo)**

## <a name="faq"></a>คำถามที่ถามบ่อย

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการแสดงผลด้วยภาพ ให้ดูที่[คำถามที่ถามบ่อยเกี่ยวกับการแสดงผลด้วยภาพที่ได้รับรองแล้ว](power-bi-custom-visuals-faq.md#certified-power-bi-visuals)

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [พัฒนาภาพแบบกำหนดเองของ Power BI](../developer/custom-visual-develop-tutorial.md)
* [รายการเพลย์ลิสต์ วิชวลแบบกำหนดเองของ Microsoft บน YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
* [จัดรูปแบบข้อมูลใน Power BI](../visuals/power-bi-report-visualizations.md)  
* [แสดงภาพแบบกำหนดเองใน Power BI](power-bi-custom-visuals.md)  
* [การเผยแพร่ส่วนการจัดแสดง Power BI ไปยัง Microsoft AppSource](../developer/office-store.md) 
* หากคุณเป็นนักพัฒนาเว็บที่สนใจในการสร้างวิชวล Power BI ของคุณเองและต้องการเพิ่มงานของคุณไปยัง [Microsoft AppSource](https://appsource.microsoft.com) คุณสามารถเริ่มต้นใช้งานได้ในบทช่วยสอน  [Developing a Power BI visual](visuals/custom-visual-develop-tutorial.md) 

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)

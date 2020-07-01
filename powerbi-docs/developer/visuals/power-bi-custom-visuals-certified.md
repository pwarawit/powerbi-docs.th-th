---
title: ส่วนจัดแสดง Power BI ที่ผ่านการรับรอง
description: ข้อกำหนดและกระบวนการที่จะส่งวิชวลแบบกำหนดเองสำหรับการรับรองและรายการของวิชวล Power BI ที่ผ่านการรับรอง
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.topic: how-to
ms.subservice: powerbi-custom-visuals
ms.date: 03/08/2020
ms.openlocfilehash: ee79a2f74714322e6ff7b4ec965060b7c9291060
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85237450"
---
# <a name="get-a-power-bi-visual-certified"></a>รับการรับรองส่วนการจัดแสดง Power BI

วิชวล Power BI ที่ได้รับการรับรองคือวิชวล Power BI ใน [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?page=1&product=power-bi-visuals) ที่ตรงตามข้อกำหนดโค้ดทีม Microsoft Power BI team [แล้ว](#certification-requirements) วิชวลเหล่านี้จะได้รับการทดสอบเพื่อตรวจสอบว่าไม่สามารถเข้าถึงบริการภายนอกหรือแหล่งข้อมูล และทำตามรูปแบบการเขียนโค้ดที่ปลอดภัยและแนวทาง

เมื่อการจัดแสดง Power BI ได้รับการรับรองแล้ว จะมีคุณลักษณะเพิ่มเติม เช่น คุณสามารถ[ส่งออกไปยัง PowerPoint](../../consumer/end-user-powerpoint.md) หรือแสดงวิชวลในอีเมลเมื่อผู้ใช้[สมัครใช้งานในหน้ารายงาน](../../consumer/end-user-subscribe.md)

กระบวนการการรับรองที่เป็นทางเลือก วิชวล power BI ที่ไม่ได้รับการรับรองไม่จำเป็นต้องใช้วิชวล Power BI ที่ไม่ปลอดภัย การแสดงผลด้วยภาพของ Power BI บางอันไม่ผ่านการรับรองเนื่องจากไม่สอดคล้องกับ [ข้อกำหนดในการรับรอง](power-bi-custom-visuals-certified.md#certification-requirements)หนึ่งรายการหรือมากกว่านั้น สำหรับตัวอย่าง เช่น แผนที่วิชวล Power BI ที่เชื่อมต่อกับบริการภายนอกหรือวิชวล Power BI ที่ใช้ไลบรารีเชิงพาณิชย์

> [!NOTE]
> Microsoftไม่ใช่บริษัทบุคคลที่สามที่สร้าง Power BI วิชวล เพื่อยืนยันการใช้งานอย่างเต็มประสิทธิภาพจากวิชวลบุคคลที่สาม แนะนำให้ลูกค้าติดต่อผู้เขียนของวิชวลโดยตรง

## <a name="certification-requirements"></a>ข้อบังคับสำหรับการรับรอง

ในการรับ[การรับรอง](#get-a-power-bi-visual-certified) วิชวล Power BI ของคุณ ต้องแน่ใจว่าวิชวล Power BI ของคุณเป็นไปตามรายการข้อกำหนดในส่วนนี้แล้ว 

### <a name="general-requirements"></a>ข้อกำหนดทั่วไป

วิชวล Power BI ของคุณต้องได้รับการอนุมัติจากศูนย์คู่ค้า เราขอแนะนำให้วิชวล Power BI ของคุณอยู่ใน [AppSource](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) แล้ว ในการเรียนสิธีเผยแพร่วิชวล Power BI ไปยัง AppSource ดู[การเผยแพร่วิชวล Power BI ไปยังศูนย์คู่ค้า](office-store.md)

ก่อนที่จะส่งวิชวล Power BI ของคุณเพื่อรับรองความถูกต้อง ตรวจสอบว่าเป็นไปตาม [แนวทางสำหรับวิชวล Power BI](guidelines-powerbi-visuals.md)

เมื่อส่งวิชวล Power BI ให้ตรวจสอบให้แน่ใจว่าแพคเกจที่แปลแล้วตรงกับแพคเกจที่ส่งเข้าไป

### <a name="code-repository-requirements"></a>ข้อกำหนดของที่เก็บโค้ด:

แม้ว่าคุณจะไม่จำเป็นต้องแชร์รหัสของคุณใน GitHub แบบสาธารณะ การเก็บโค้ดก็จะพร้อมใช้งานสำหรับการตรวจทานโดยทีม Power BI วิธีที่ดีที่สุดในการทำเช่นนี้คือการให้แหล่งโค้ด (JavaScript หรือ TypeScript) ใน GitHub

ที่เก็บต้องมีสิ่งต่อไปนี้:
* รหัสสำหรับการแสดงผลด้วยภาพของ Power BI เดียวเท่านั้น ซึ่งไม่สามารถมีโค้ดสำหรับวิชวล Power BI หลายหรือรหัสที่ไม่เกี่ยวข้อง
* สาขาที่ชื่อว่า**ใบรับรอง** (จำเป็นต้องใช้ตัวพิมพ์เล็ก) แหล่งโค้ดในสาขานี้ต้องตรงกับแพคเกจที่ส่งไป โค้ดนี้สามารถอัปเดตได้ระหว่างขั้นตอนการส่งครั้งถัดไป ถ้าคุณกำลังส่งวิชวล Power BI ของคุณใหม่

ถ้าวิชวล Power BI ของคุณใช้แพคเกจ npm แบบส่วนตัวหรือโมดูลย่อย git คุณต้องให้การเข้าถึงที่เก็บข้อมูลเพิ่มเติมที่มีโค้ดนี้

เพื่อทำความเข้าใจวิธีการดูที่เก็บข้อมูลการแสดงผลด้วยภาพของ Power BI ให้ตรวจสอบที่เก็บ GitHub สำหรับ [แผนภูมิแท่งตัวอย่างของ Power BI](https://github.com/microsoft/PowerBI-visuals-sampleBarChart)

### <a name="file-requirements"></a>ข้อกำหนดไฟล์

ใช้ API รุ่นล่าสุดเพื่อเขียนวิชวล Power BI

ที่เก็บต้องมีไฟล์ต่อไปนี้:
* **gitignore**- เพิ่ม `node_modules` `.tmp` และ `dist` ไปยังไฟล์นี้ รหัสไม่สามารถมี *node_modules* *. tmp* หรือ*โฟลเดอร์  beta.dist* ได้
* **capabilities.json** - ถ้าคุณกำลังส่งเวอร์ชันที่ใหม่กว่าของวิชวล Power BI ของคุณด้วยการเปลี่ยนแปลงคุณสมบัติในไฟล์นี้ โปรดตรวจสอบว่าไฟล์นั้นไม่ได้แบ่งแยกรายงานสำหรับผู้ใช้ที่มีอยู่
* **pbiviz.json** 
* **pbiviz.json** การแสดงผลด้วยภาพต้องมีการติดตั้งแพคเกจต่อไปนี้:
   * ["tslint"](https://www.npmjs.com/package/tslint)- เวอร์ชัน 5.18.0 หรือใหม่กว่า
   * ["typescript"](https://www.npmjs.com/package/typescript)- เวอร์ชัน 3.0.0 หรือใหม่กว่า
   * ["tslint-microsoftcontrib"](https://www.npmjs.com/package/tslint-microsoft-contrib) - เวอร์ชัน 6.2.0 หรือใหม่กว่า
   * ไฟล์ต้องประกอบด้วยคำสั่งสำหรับการเรียกใช้ linter -  `"lint": "tslint -c tslint.json -p tsconfig.json"`
* **pbiviz.json**
* **pbiviz.json**

### <a name="command-requirements"></a>ข้อกำหนดคำสั่ง

ตรวจสอบให้แน่ใจว่าคำสั่งต่อไปนี้ไม่ได้ส่งกลับข้อผิดพลาดใดๆ

* `npm install`
* `pbiviz package`
* `npm audit` - ต้องไม่ส่งกลับคำเตือนใดๆ ที่มีระดับสูงหรือระดับปานกลาง
* [TSlint จาก Microsoft](https://www.npmjs.com/package/tslint-microsoft-contrib) ที่มี[กำหนดค่าที่จำเป็น](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/master/tslint.json) คำสั่งนี้ต้องไม่ส่งข้อ lint ผิดพลาดใดๆ กลับมา

### <a name="compiling-requirements"></a>ข้อกำหนดตัวแปลโปรแกรม

ใช้ [เครื่องมือ-วิชวล-powerbi](https://www.npmjs.com/package/powerbi-visuals-tools) รุ่นล่าสุดเพื่อเขียนวิชวล Power BI

คุณต้องคอมไพล์วิชวล Power BI ของคุณด้วย `pbiviz package` ถ้าคุณกำลังใช้สคริปต์การสร้างของคุณเองให้  `npm run package`คำสั่งสร้างแบบกำหนดเอง

### <a name="source-code-requirements"></a>ข้อกำหนดของแหล่งโค้ด

ตรวจสอบว่าคุณได้ทำตามรายการนโยบาย [ การรับรองความถูกต้องของ Power BI](https://docs.microsoft.com/legal/marketplace/certification-policies#1200-power-bi-visuals-additional-certification) หากการส่งของคุณไม่เป็นไปตามหลักเกณฑ์เหล่านี้ อีเมลที่ใช้ในการปฏิเสธจากศูนย์คู่ค้าจะรวมถึงหมายเลขนโยบายที่แสดงรายการอยู่ในลิงก์นี้

ปฏิบัติตามข้อกำหนดของโค้ดที่แสดงด้านล่างเพื่อตรวจสอบให้แน่ใจว่าโค้ดของคุณอยู่ในแนวทางด้วยนโยบายการรับรอง Power BI  

**ที่จำเป็น**
* มีเพียงการใช้องค์ประกอบ OSS ที่ตรวจสอบแล้วเท่านั้น เช่น Javascript หรือไลบราลี่ TypeScript
* โค้ดต้องสนับสนุน [การเรนเดอร์อีเวนท์ API](event-service.md)
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

## <a name="certified-power-bi-visual-badges"></a>ป้ายแสดงผลด้วยภาพ Power BI ที่ผ่านการรับรอง

เมื่อการแสดงผลด้วยภาพของ Power BI ได้รับการรับรองแล้วจะได้รับป้ายที่กำหนดซึ่งระบุว่าได้การรับรองความถูกต้อง

### <a name="certified-power-bi-visuals-in-appsource"></a>Power BI ที่ผ่านการรับรองใน AppSource

* เมื่อค้นหาออนไลน์สำหรับ[การแสดงผลด้วยภาพของ Power BI ใน AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) ป้ายสีเหลืองขนาดเล็กบนการ์ดของภาพแสดงให้เห็นว่าเป็นภาพ Power BI ที่ได้รับการรับรอง

    ![การแสดงผลด้วยภาพของ Power BI ที่ผ่านการรับรองใน AppSource](media/power-bi-custom-visuals-certified/certified-visual-yellow-small.png)

* หลังจากคลิกการ์ดการแสดงผลด้วยภาพของ Power BI  ใน AppSource ป้ายสีเหลืองชื่อ*ได้รับการรับรองจาก PBI* จะแสดงว่าการแสดงผลด้วยภาพของ Power BI นี้ได้รับการรับรอง

    ![การแสดงผลด้วยภาพของ Power BI ที่ผ่านการรับรองในหน้าแอป](media/power-bi-custom-visuals-certified/certified-visual-yellow-big.png)

### <a name="certified-power-bi-visuals-in-the-power-bi-interface"></a>การแสดงผลด้วยภาพของ Power BI ที่ผ่านการรับรองในส่วนติดต่อ Power BI

* เมื่อนำการแสดงผลด้วยภาพของ Power BI จากภายใน Power BI (Desktop หรือบริการ) ป้ายชื่อสีน้ำเงินจะแสดงว่าการแสดงผลด้วยภาพของ Power BI นี้ได้รับการรับรอง

    ![ส่วนติดต่อ Power BI การแสดงผลด้วยภาพของ Power BI ที่ผ่านการรับรอง](media/power-bi-custom-visuals-certified/certified-visual-blue.png)

* คุณสามารถแสดงการแสดงผลด้วยภาพของ Power BI ที่ได้รับการรับรองได้โดยการเลือกตัวเลือกตัวกรอง *Power BI ที่ได้รับการรับรอง*

## <a name="publication-timeline"></a>ไทม์ไลน์การเผยแพร่

การปรับใช้ใน AppSource คือกระบวนการที่อาจต้องใช้เวลาสักครู่ วิชวล Power BI พร้อมที่จะดาวน์โหลดจาก AppSource ได้เมื่อกระบวนการนี้เสร็จสมบูรณ์

### <a name="when-will-users-be-able-to-download-my-visual"></a>ผู้ใช้จะสามารถดาวน์โหลดวิชวลของฉันได้เมื่อใด

* หากคุณส่งวิชวล Power BI เป็นครั้งแรก ผู้ใช้จะสามารถดาวน์โหลดวิชวลได้ภายในสองถึงสามชั่วโมงหลังจากที่คุณได้รับอีเมลจาก AppSource

* หากคุณส่งการอัปเดตไปยังวิชวล Power BI ที่มีอยู่ ผู้ใช้จะสามารถดาวน์โหลดวิชวลได้ภายในหนึ่งเดือนหลังจากการส่งของคุณ

    >[!NOTE]
    > เขตข้อมูล*เวอร์ชัน*ใน AppSource จะอัปเดตในวันที่ Power BI ของคุณได้รับการอนุมัติโดย AppSource ประมาณหนึ่งสัปดาห์หลังจากที่คุณส่งวิชวลของคุณ ผู้ใช้จะสามารถดาวน์โหลดวิชวลที่อัปเดตแล้วได้ แต่ความสามารถที่อัปเดตแล้วจะไม่มีผล ความสามารถใหม่ของวิชวลของคุณจะส่งผลกระทบต่อรายงานของผู้ใช้หลังจากผ่านไปประมาณหนึ่งเดือน 

### <a name="when-will-my-power-bi-visual-display-a-certification-badge"></a>วิชวล Power BI ของฉันจะแสดงตัวบอกสถานะใบรับรองเมื่อใด

* หากคุณส่งวิชวล Power BI เป็นครั้งแรก ตัวบอกสถานะใบรับรองจะปรากฏขึ้นภายในหนึ่งวันหลังจากได้รับอีเมลการอนุมัติจาก AppSource

* หากคุณกำลังร้องขอการรับรองสำหรับวิชวล Power BI ที่มีอยู่ คุณจะเห็นตัวบอกสถานะใบรับรองได้ภายในหนึ่งเดือนหลังจากการส่งของคุณ

## <a name="next-steps"></a>ขั้นตอนถัดไป

* หากคุณเป็นนักพัฒนาเว็บที่สนใจในการสร้างวิชวล Power BI ของคุณเองและต้องการเพิ่มงานของคุณไปยัง [Microsoft AppSource](https://appsource.microsoft.com) คุณสามารถเริ่มต้นใช้งานได้ในบทช่วยสอน  [Developing a Power BI visual](custom-visual-develop-tutorial.md)

* สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการแสดงผลด้วยภาพ ให้ดูที่[คำถามที่ถามบ่อยเกี่ยวกับการแสดงผลด้วยภาพที่ได้รับรองแล้ว](power-bi-custom-visuals-faq.md#certified-power-bi-visuals)

* [การพัฒนาวิชวลสำหรับ Power BI](custom-visual-develop-tutorial.md)

* [รายการเพลย์ลิสต์ วิชวล Power BI ของ Microsoft บน YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)

* [วิชวลใน Power BI](power-bi-custom-visuals.md)

* [การเผยแพร่ส่วนการจัดแสดง Power BI ไปยัง Microsoft AppSource](office-store.md)

* มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)
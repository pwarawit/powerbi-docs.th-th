---
title: วิชวลใน Power BI
description: การแสดงข้อมูลแบบกำหนดเองใน Power BI
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/15/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: a8b1be9157fa34e9ed4c987628f0b67624b4c826
ms.sourcegitcommit: 549401b0e1fad15c3603fe7f14b9494141fbb100
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/14/2019
ms.locfileid: "72307471"
---
# <a name="visuals-in-power-bi"></a>วิชวลใน Power BI

เมื่อสร้างหรือแก้ไขรายงาน Power BI คุณสามารถใช้ภาพได้หลายประเภท แสดงไอคอนสำหรับภาพเหล่านี้จะปรากฎขึ้นในบานหน้าต่าง **การจัดรูปแบบการแสดงข้อมูล** ชุดของภาพเหล่านี้จะมีให้มาอยู่แล้วเมื่อคุณดาวน์โหลด[Power BI Desktop](https://powerbi.microsoft.com/desktop/) หรือเปิด [บริการของ Power BI](https://app.powerbi.com)

![การจัดรูปแบบการแสดงข้อมูล](media/power-bi-custom-visuals/power-bi-visualizations.png)

อย่างไรก็ตาม คุณไม่ได้ถูกจำกัดเฉพาะภาพชุดนี้ ถ้าคุณเลือกจุดไข่ปลา (...) ที่ด้านล่าง แหล่งข้อมูลอื่นของภาพในรายงานจะพร้อมใช้งาน -*ส่วนแสดงผล Power BI*

นักพัฒนาจะจัดทำส่วนแสดงผล Power BI โดยใช้ SKD ส่วนแสดงผล Power BI ภาพเหล่านี้ช่วยให้ผู้ใช้ทางธุรกิจสามารถดูข้อมูลในแบบที่เหมาะกับธุรกิจของพวกเขามากที่สุด ผู้เขียนรายงานสามารถนำเข้าไฟล์ภาพแบบกำหนดเองลงใส่ในรายงานและใช้งานได้เช่นเดียวกับภาพอื่น ๆ ใน Power BI ส่วนแสดงผล Power BI เป็นส่วนประกอบอันดับแรกใน Power BI และสามารถกรอง เน้น แก้ไข แชร์ และอื่น ๆ ได้

ส่วนแสดงผล Power BI สามารถนำไปปรับใช้ได้สามวิธี:

* ไฟล์วิชวลแบบกำหนดเอง
* การแสดงผลด้วยภาพขององค์กร
* วิชวลจาก Marketplace

## <a name="custom-visual-files"></a>ไฟล์วิชวลแบบกำหนดเอง

ส่วนแสดงผล Power BI เป็นแพคเกจที่รวมเอาโค้ดสำหรับการนำเสนอข้อมูลที่ให้บริการในภาพ ทุกคนสามารถสร้างภาพแบบกำหนดเองและรวมภาพนั้นเป็นไฟล์ `.pbiviz` เดียวที่สามารถนำเข้าไปในรายงาน Power BI

> [!WARNING]
> ภาพแบบกำหนดเองสามารถมีโค้ด ซึ่งมีความเสี่ยงด้านความปลอดภัยหรือความเป็นส่วนตัว ตรวจสอบให้แน่ใจว่าคุณเชื่อถือผู้เขียนและแหล่งข้อมูลภาพแบบกำหนดเองก่อนที่จะนำเข้าไปยังรายงานของคุณ

## <a name="organizational-visuals"></a>การแสดงผลด้วยภาพขององค์กร

ผู้ดูแลระบบ Power BI อนุมัติ และปรับใช้ส่วนแสดงผล Power BI ลงในองค์กรของพวกเขา ซึ่งผู้เขียนรายงานสามารถค้นหา ปรับปรุง และใช้ได้อย่างง่ายดาย ผู้ดูแลระบบสามารถจัดการ (ตัวอย่าง อัปเดตเวอร์ชัน ปิดใช้งาน/เปิดใช้งาน) ภาพเหล่านี้ได้อย่างง่ายดาย

 [อ่านเพิ่มเติมเกี่ยวกับการแสดงผลด้วยภาพขององค์กร](power-bi-custom-visuals-organization.md)

## <a name="marketplace-visuals"></a>วิชวลจาก Marketplace

สมาชิกในชุมชนและ Microsoft ได้มอบส่วนแสดงผล Power BI ของพวกเขาเพื่อประโยชน์สาธารณะ และเผยแพร่ทางตลาดการค้า [AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) คุณสามารถดาวน์โหลดภาพเหล่านี้และเพิ่มลงในรายงาน Power BI ของคุณได้ Microsoft ได้รับการทดสอบและอนุมัติส่วนแสดงผล Power BI เหล่านี้ทั้งหมด ทั้งฟังก์ชันการใช้งานและคุณภาพ

AppSource [คืออะไร?](developer/office-store.md) ซึ่งเป็นที่ที่คุณสามารถค้นหาแอป add-in และส่วนขยายสำหรับซอฟต์แวร์ Microsoft ของคุณ AppSource เชื่อมต่อผู้ใช้ของผลิตภัณฑ์ เช่น Office 365, Azure, Dynamics 365, Cortana และ Power BI นับล้านคน ไปยังโซลูชันที่ช่วยให้พวกเขาทำงานสำเร็จได้อย่างมีประสิทธิภาพขึ้น เข้าใจได้ลึกซึ้งขึ้น หรือสวยงามขึ้นกว่าที่เคย

### <a name="certified-visuals"></a>วิชวลที่ผ่านการรับรองแล้ว

ภาพของ Power BI ที่ผ่านการรับรอง เป็นภาพจากตลาดการค้าที่ผ่านการทดสอบที่เข้มงวดเรื่องคุณภาพ และรองรับการใช้งานเพิ่มเติม เช่น[การสมัครใช้งานทางอีเมล](service-report-subscribe.md)และ[การส่งออกไปยัง PowerPoint](service-publish-to-powerpoint.md)
เมื่อต้องการดูรายการของส่วนแสดงผล Power BI ที่ผ่านการรับรอง หรือต้องการส่งวิชวลของคุณเอง ให้ดู [ส่วนแสดงผล Power BI ที่ผ่านการรับรองแล้ว](power-bi-custom-visuals-certified.md)

คุณเป็นนักพัฒนาเว็บ และสนใจสร้างวิชวลของคุณเอง และเพิ่มเข้าไปใน AppSource หรือไม่ ดู[การพัฒนาวิชวลแบบกำหนดเองสำหรับ Power BI](developer/visuals/custom-visual-develop-tutorial.md) และเรียนรู้วิธีการ[เผยแพร่วิชวลแบบกำหนดเองไปยัง AppSource](developer/office-store.md)

### <a name="import-a-custom-visual-from-a-file"></a>นำเข้าภาพที่กำหนดเองจากไฟล์

1. เลือกจุดไข่ปลาจากด้านล่างของบานหน้าต่าง **การจัดรูปแบบการแสดงข้อมูล**

    ![visualizations2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. จากรายการดรอปดาวน์ เลือก**นำเข้าจากไฟล์**

    ![นำเข้าจากไฟล์](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

3. จากเมนู **เปิด**ไฟล์ เลือกไฟล์ที่คุณต้องการนำเข้า`.pbiviz`และจ**ากนั้นเลือกเปิด** ไอคอนภาพแบบกำหนดเองจะถูกเพิ่มไปยังด้านล่างของบานหน้าต่าง **การจัดรูปแบบการแสดงข้อมูล** และพร้อมใช้งานในรายงานของคุณ

    ![cv ที่นำเข้าแล้ว](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="import-organizational-visuals"></a>นำเข้าการแสดงผลด้วยภาพขององค์กร

1. เลือกจุดไข่ปลาจากด้านล่างของบานหน้าต่าง **การจัดรูปแบบการแสดงข้อมูล**

    ![แสดงภาพองค์กร 1](media/power-bi-custom-visuals/power-bi-visual-org-01.png)

2. จากรายการดรอปดาวน์ เลือก**นำเข้าจาก marketplace**

    ![แสดงภาพองค์กร 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. เลือก**องค์กรของฉัน**จากเมนบนแท็บด้านบน

    ![แสดงภาพองค์กร 3](media/power-bi-custom-visuals/power-bi-visual-org-03.png)

4. เลื่อนผ่านรายการเพื่อการค้นหาวิชวลที่จะนำเข้า

    ![แสดงภาพองค์กร 4](media/power-bi-custom-visuals/power-bi-visual-org-04.png)

5. นำเข้าภาพแบบกำหนดเองโดยเลือกที่ปุ่ม **เพิ่ม** ไอคอนจะถูกเพิ่มไปยังด้านล่างของบานหน้าต่าง **การจัดรูปแบบการแสดงข้อมูล** และพร้อมใช้งานในรายงานของคุณ

    ![แสดงภาพองค์กร 5](media/power-bi-custom-visuals/power-bi-visual-org-05.png)

## <a name="download-or-import-power-bi-visuals-from-microsoft-appsource"></a>ดาวน์โหลด หรือนำเข้าส่วนการแสดงผล Power BI จาก Microsoft AppSource

คุณมีสองตัวเลือกสำหรับการดาวน์โหลด และการนำเข้าส่วนการแสดงผล Power BI โดยสามารถทำจากใน Power BI และจากเว็บไซต์ [AppSource](https://appsource.microsoft.com/)

### <a name="import-power-bi-visuals-from-within-power-bi"></a>นำเข้าส่วนการแสดงผล Power BI จากใน Power BI

1. เลือกจุดไข่ปลาจากด้านล่างของบานหน้าต่าง **การจัดรูปแบบการแสดงข้อมูล**

    ![การจัดรูปแบบการแสดงข้อมูล 2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. จากรายการดรอปดาวน์ เลือก**นำเข้าจาก marketplace**

    ![แสดงภาพองค์กร 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. เลื่อนผ่านรายการเพื่อการค้นหาวิชวลที่จะนำเข้า

    ![นำเข้าวิชวล](media/power-bi-custom-visuals/power-bi-import-visual.png)

4. ถ้าต้องการเรียนรู้เพิ่มเติมเกี่ยวกับวิชวล ให้ไฮไลท์และเลือกมัน

    ![เลือก](media/power-bi-custom-visuals/power-bi-select.png)

5. บนหน้ารายละเอียด คุณสามารถดูภาพหน้าจอ วิดีโอ คำอธิบายโดยละเอียด และอื่น ๆ

    ![Synoptic](media/power-bi-custom-visuals/power-bi-synoptic.png)

6. เลื่อนไปด้านล่างเพื่อดูการรีวิว

    ![รีวิว](media/power-bi-custom-visuals/power-bi-reviews.png)

7. นำเข้าภาพแบบกำหนดเองโดยเลือกที่ปุ่ม **เพิ่ม** ไอคอนจะถูกเพิ่มไปยังด้านล่างของบานหน้าต่าง **การจัดรูปแบบการแสดงข้อมูล** และพร้อมใช้งานในรายงานของคุณ

    ![วิชวลที่นำเข้า](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="download-and-import-power-bi-visuals-from-microsoft-appsource"></a>ดาวน์โหลดและนำเข้าส่วนการแสดงผล Power BI จาก Microsoft AppSource

1. เริ่มจาก [Microsoft AppSource](https://appsource.microsoft.com) และเลือกแท็บสำหรับ**แอป**

    ![AppSource](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. ไปยัง[หน้าผลลัพธ์แอป](https://appsource.microsoft.com/marketplace/apps) คุณสามารถดูแอปอันดับต้น ๆ ในแต่ละประเภท รวมถึง *แอป Power BI* เราจะค้นหาส่วนการแสดงผล Power BI โดยเลือก **ภาพ Power BI** จากรายการนำทางด้านซ้ายมือเพื่อจำกัดผลลัพธ์ให้แคบลง

    ![วิชวล AppSource](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. AppSource แสดงไทล์สำหรับวิชวลแบบกำหนดเองแต่ละตัว  แต่ละไทล์มีสแนปช็อตของภาพแบบกำหนดเองพร้อมคำอธิบายสั้น ๆ และลิงก์สำหรับดาวน์โหลด เมื่อต้องการดูรายละเอียดเพิ่มเติม ให้เลือกไทล์

    ![เลือกวิชวลแบบกำหนดเอง](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. บนหน้ารายละเอียด คุณสามารถดูภาพหน้าจอ วิดีโอ คำอธิบายโดยละเอียด และอื่น ๆ ดาวน์โหลดภาพแบบกำหนดเองโดยการเลือก**รับทันที**และยอมรับข้อกำหนดการใช้

    ![รับ AppSource](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. เลือกลิงก์เพื่อดาวน์โหลดวิชวลแบบกำหนดเอง

    ![ดาวน์โหลด](media/power-bi-custom-visuals/powerbi-custom-download.png)

    หน้าดาวน์โหลดยังบอกวิธีการนำเข้าภาพแบบกำหนดเองลงใน Power BI Desktop และบริการของ Power BI

    คุณยังสามารถดาวน์โหลดรายงานตัวอย่างการใช้วิชวลแบบกำหนดเอง ที่ใช้แสดงขีดความสามารถของมัน

    ![ลองตัวอย่าง](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. บันทึกไฟล์ `.pbiviz` และจากนั้นเปิด Power BI

7. นำเข้าไฟล์ `.pbiviz` ลงในรายงานของคุณ (ดูส่วน [นำเข้าภาพแบบกำหนดเองจากไฟล์](#import-a-custom-visual-from-a-file) ด้านบน)

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด

* วิชวลแบบกำหนดเองจะถูกเพิ่มเฉพาะในรายงานที่นำเข้า ถ้าคุณต้องการใช้วิชวลในรายงานอื่น คุณจำเป็นต้องนำเข้าในรายงานนั้นด้วยเช่นกัน เมื่อรายงานที่มีวิชวลแบบกำหนดเอง ถูกบันทึกโดยใช้ตัวเลือก **บันทึกเป็น** สำเนาของวิชวลแบบกำหนดเองจะถูกบันทึกไปกับรายงานใหม่

* ถ้าคุณไม่เห็นบานหน้าต่าง **การจัดรูปแบบการแสดงข้อมูล** แสดงว่าคุณไม่มีสิทธิการแก้ไขรายงาน  คุณสามารถเพิ่มส่วนการแสดงผล Power BI ได้เฉพาะเมื่อคุณสามารถแก้ไขรายงานเท่านั้น ไม่ใช่เมื่อรายงานนั้นได้ถูกแชร์ให้คุณ

## <a name="troubleshoot"></a>การแก้ไขปัญหา

แก้ไขปัญหาได้ตามหัวข้อ [การแก้ไขปัญหาส่วนการแสดงผล Power BI ของคุณ](power-bi-custom-visuals-troubleshoot.md)

## <a name="faq"></a>คำถามที่ถามบ่อย

สำหรับข้อมูลเพิ่มเติมและคำตอบที่คุณอยากรู้ โปรดเยี่ยมชม[คำถามที่ถามบ่อยเกี่ยวกับ Power BI ส่วนการแสดงผล Power BI](power-bi-custom-visuals-faq.md#organizational-visuals)

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [การจัดรูปแบบการแสดงข้อมูลในรายงาน Power BI](visuals/power-bi-report-visualizations.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)

---
title: การแสดงข้อมูลแบบกำหนดเองใน Power BI
description: การแสดงข้อมูลแบบกำหนดเองใน Power BI
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 11/06/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: 4d38cf108a4c2e863811cfee68fc2d0b95c1990e
ms.sourcegitcommit: 88ae40a25ea54ef7153885dd04ef57d12522d4e1
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/04/2019
ms.locfileid: "54056052"
---
# <a name="custom-visuals-in-power-bi"></a>วิชวลแบบกำหนดเองใน Power BI

เมื่อสร้าง หรือแก้ไขรายงาน Power BI มีการแสดงข้อมูลเป็นภาพ หรือวิชวล มากมายหลายชนิด พร้อมให้คุณใช้งาน วิชวลเหล่านี้จะแสดงในบานหน้าต่าง**การจัดรูปแบบการแสดงข้อมูล** เมื่อคุณดาวน์โหลด Power BI Desktop หรือเปิดบริการ Power BI (app.powerbi.com) ชุดของวิชวลนี้จะมีให้มาอยู่แล้ว

![การจัดรูปแบบการแสดงข้อมูล](media/power-bi-custom-visuals/power-bi-visualizations.png)

แต่คุณไม่ได้จำกัดเพียงวิชวลชุดนี้ เมื่อเลือกที่จุดไข่ปลา จะเปิดกว้างไปยังแหล่งของวิชวลอื่น นั่นก็คือ: *วิชวลแบบกำหนดเอง*

วิชวลแบบกำหนดเองสร้างขึ้นโดยนักพัฒนา โดยใช้ SDK วิชวลแบบกำหนดเอง เพื่อเปิดโอกาสให้ผู้ใช้ทางธุรกิจ เห็นข้อมูลของพวกเขาในรูปแบบที่เหมาะกับงานที่สุด ผู้สร้างรายงานสามารถนำเข้าไฟล์วิชวลแบบกำหนดเอง ลงใส่ในรายงานและใช้งานได้เช่นเดียวกับวิชวลอื่น ๆ ใน Power BI ภาพแบบกำหนดเองเป็นพลเมืองชั้นแรกใน Power BI และคุณสามารถ กรอง เน้น แก้ไข แชร์ และอื่น ๆ ภาพนั้นได้

วิชวลแบบกำหนดเองสามารถอยู่ในรูปของการใช้งานสามอย่าง

* ไฟล์วิชวลแบบกำหนดเอง
* วิชวลองค์กร
* วิชวลจาก Marketplace

## <a name="custom-visual-files"></a>ไฟล์วิชวลแบบกำหนดเอง

วิชวลแบบกำหนดเองเป็นแพคเกจที่รวมเอาโค้ดสำหรับนำเสนอข้อมูลที่ส่งไปให้มัน ทุกคนสามารถสร้างภาพแบบกำหนดเองและแพคเกจภาพนั้นเป็นไฟล์ `.pbiviz` เดียว ที่สามารถนำเข้าไปในรายงาน Power BI

> [!WARNING]
> วิชวลแบบกำหนดเองอาจมีรหัสซึ่งมีความเสี่ยงเรื่องความปลอดภัยหรือความเป็นส่วนตัว ดังนั้นคุณต้องเชื่อถือในผู้เขียนและที่มาของวิชวลแบบกำหนดเอง ก่อนที่จะการนำเข้าลงในรายงานของคุณ

## <a name="organization-visuals"></a>วิชวลองค์กร

ผู้ดูแลระบบ Power BI สามารถนำวิชวลแบบกำหนดเองมาลงในองค์กรของพวกเขา เพื่อให้ผู้สร้างรายงานสามารถค้นหา และใช้วิชวลแบบกำหนดเองที่ผู้ดูแลระบบอนุมัติให้ใช้ภายในองค์กร ผู้ดูแลมีวิธีควบคุมวิชวลแบบกำหนดเองที่จะนำมาใช้ในองค์กร และมีวิธีง่าย ๆ ในการจัดการ (เช่น ปรับปรุงเวอร์ชัน ปิด/เปิดใช้งาน) วิชวลเหล่า ส่วนผู้สร้างรายงาน ก็มีวิธีง่าย ๆ ที่จะค้นหาวิชวลที่มีเฉพาะในองค์กร และมีการสนับสนุนการอัปเดตวิชวลเหล่านั้นอย่างราบรื่น

ถ้าต้องการข้อมูลเพิ่มเติมเกี่ยวกับวิชวลแบบกำหนดเองระดับองค์กร [อ่านเพิ่มเติมเกี่ยวกับวิชวลองค์กร](power-bi-custom-visuals-organization.md)

## <a name="marketplace-visuals"></a>วิชวลจาก Marketplace

สมาชิกในชุมชน ตลอดจน Microsoft ได้มอบวิชวลแบบกำหนดเองของพวกเขาเพื่อประโยชน์สาธารณะ และเผยแพร่ทาง [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals) marketplace วิชวลเหล่านี้สามารถดาวน์โหลด และเพิ่มลงรายงาน Power BI วิชวลแบบกำหนดเองเหล่านี้ทั้งหมด ได้รับการทดสอบและอนุมัติโดย Microsoft ทั้งฟังก์ชันการใช้งานและคุณภาพ

AppSource [คืออะไร?](developer/office-store.md) เป็นที่ค้นหาแอป, add-in และส่วนขยายสำหรับซอฟต์แวร์ Microsoft ของคุณ [AppSource](https://appsource.microsoft.com/en-us/) เชื่อมต่อผู้ใช้ของผลิตภัณฑ์ เช่น Office 365, Azure, Dynamics 365, Cortana และ Power BI นับล้านคน ไปยังโซลูชันที่ช่วยให้พวกเขาทำงานสำเร็จ ได้อย่างมีประสิทธิภาพขึ้น เข้าใจได้ลึกซึ้งขึ้น หรือสวยงามขึ้นกว่าที่เคย

### <a name="certified-visuals"></a>วิชวลที่ผ่านการรับรองแล้ว

วิชวลของ Power BI ที่ผ่านการรับรอง เป็นวิชวลจาก Marketplace ที่ผ่านการทดสอบที่เข้มงวดเรื่องคุณภาพ และรองรับการใช้งานเพิ่มเติม เช่น[การสมัครสมาชิกอีเมล](https://docs.microsoft.com/power-bi/service-report-subscribe)และ[การส่งออกไปยัง PowerPoint](https://docs.microsoft.com/power-bi/service-publish-to-powerpoint).
เมื่อต้องการดูรายการของวิชวลแบบกำหนดเองได้ที่ผ่านการรับรอง หรือต้องการส่งวิชวลของคุณเอง ให้ดู [วิชวลแบบกำหนดเองที่ผ่านการรับรองแล้ว](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified)

คุณเป็นนักพัฒนาเว็บ และสนใจสร้างวิชวลของคุณเอง และเพิ่มเข้าไปใน AppSource หรือไม่ ดู[การพัฒนาวิชวลแบบกำหนดเองสำหรับ Power BI](developer/custom-visual-develop-tutorial.md) และเรียนรู้วิธีการ[เผยแพร่วิชวลแบบกำหนดเองไปยัง AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals)

### <a name="import-a-custom-visual-from-a-file"></a>นำเข้าภาพที่กำหนดเองจากไฟล์

1. เลือกจุดไข่ปลาจากด้านล่างของบานหน้าต่าง การจัดรูปแบบการแสดงข้อมูล

    ![visualizations2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. จากรายการดรอปดาวน์ เลือก**นำเข้าจากไฟล์**

    ![นำเข้าจากไฟล์](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

3. จากเมนูเปิดไฟล์ เลือก`.pbiviz`ไฟล์ที่คุณต้องการนำเข้า และจากนั้น เลือกเปิด ไอคอนสำหรับวิชวลแบบกำหนดเองจะถูกเพิ่มไปยังด้านล่างของบานหน้าต่าง การจัดรูปแบบการแสดงข้อมูล และพร้อมใช้งานในรายงานของคุณ

    ![cv ที่นำเข้าแล้ว](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="import-organization-visuals"></a>นำเข้าวิชวลองค์กร

1. เลือกจุดไข่ปลาจากด้านล่างของบานหน้าต่าง การจัดรูปแบบการแสดงข้อมูล

    ![แสดงภาพองค์กร 1](media/power-bi-custom-visuals/power-bi-visual-org-01.png)

2. จากรายการดรอปดาวน์ เลือกนำเข้าจาก marketplace

    ![แสดงภาพองค์กร 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. เลือก**องค์กรของฉัน**จากเมนบนแท็บด้านบน

    ![แสดงภาพองค์กร 3](media/power-bi-custom-visuals/power-bi-visual-org-03.png)

4. เลื่อนผ่านรายการเพื่อการค้นหาวิชวลที่จะนำเข้า

    ![แสดงภาพองค์กร 4](media/power-bi-custom-visuals/power-bi-visual-org-04.png)

5. นำเข้าวิชวลแบบกำหนดเอง โดยเลือกที่ปุ่ม**เพิ่ม** ไอคอนสำหรับวิชวลแบบกำหนดเองจะถูกเพิ่มไปยังด้านล่างของบานหน้าต่าง การจัดรูปแบบการแสดงข้อมูล และพร้อมใช้งานในรายงานของคุณ

    ![แสดงภาพองค์กร 5](media/power-bi-custom-visuals/power-bi-visual-org-05.png)

## <a name="download-or-import-custom-visuals-from-microsoft-appsource"></a>ดาวน์โหลด หรือนำเข้าวิชวลแบบกำหนดเองจาก Microsoft AppSource

คุณมีสองตัวเลือกสำหรับการดาวน์โหลด และการนำเข้าวิชวลแบบกำหนดเอง โดยสามารถทำจากใน Power BI และจากเว็บไซต์ AppSource

### <a name="import-custom-visuals-from-within-power-bi"></a>นำเข้าวิชวลแบบกำหนดเองจากภายใน Power BI

1. เลือกจุดไข่ปลาจากด้านล่างของบานหน้าต่าง การจัดรูปแบบการแสดงข้อมูล

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

7. นำเข้าวิชวลแบบกำหนดเอง โดยเลือกที่ปุ่ม เพิ่ม ไอคอนสำหรับวิชวลแบบกำหนดเองจะถูกเพิ่มไปยังด้านล่างของบานหน้าต่าง การจัดรูปแบบการแสดงข้อมูล และพร้อมใช้งานในรายงานของคุณ

    ![วิชวลที่นำเข้า](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="download-and-import-custom-visuals-from-microsoft-appsource"></a>ดาวน์โหลด และนำเข้าวิชวลแบบกำหนดเองจาก Microsoft AppSource

1. เริ่มจาก [Microsoft AppSource](https://appsource.microsoft.com) และเลือกแท็บสำหรับ**แอป** 

    ![AppSource](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. ไปยัง[หน้าผลลัพธ์แอป](https://appsource.microsoft.com/en-us/marketplace/apps) คุณสามารถดูแอปอันดับต้น ๆ ในแต่ละประเภท รวมถึง *แอป Power BI* แต่เรากำลังค้นหาวิชวลแบบกำหนดเอง เราจะจำกัดการค้นหาให้แคบลงโดยเลือก **วิชวล Power BI** จากรายการนำทางด้านซ้ายมือ

    ![วิชวล AppSource](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. AppSource แสดงไทล์สำหรับวิชวลแบบกำหนดเองแต่ละตัว  แต่ละไทล์มีสแนปช็อตของวิชวลแบบกำหนดเอง ให้คำอธิบายสั้น ๆ และมีลิงก์สำหรับดาวน์โหลด เมื่อต้องการดูรายละเอียดเพิ่มเติม ให้เลือกไทล์

    ![เลือกวิชวลแบบกำหนดเอง](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. บนหน้ารายละเอียด คุณสามารถดูภาพหน้าจอ วิดีโอ คำอธิบายโดยละเอียด และอื่น ๆ ดาวน์โหลดภาพแบบกำหนดเองโดยการเลือก**รับทันที**และยอมรับข้อกำหนดการใช้

    ![รับ AppSource](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. เลือกลิงก์เพื่อดาวน์โหลดวิชวลแบบกำหนดเอง

    ![ดาวน์โหลด](media/power-bi-custom-visuals/powerbi-custom-download.png)

    หน้าดาวน์โหลดยังบอกวิธีการนำเข้าวิชวลแบบกำหนดเองลงใน Power BI Desktop และบริการของ Power BI

    คุณยังสามารถดาวน์โหลดรายงานตัวอย่างการใช้วิชวลแบบกำหนดเอง ที่ใช้แสดงขีดความสามารถของมัน

    ![ลองตัวอย่าง](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. บันทึกไฟล์ ‘.pbiviz’ และจากนั้นเปิด Power BI

7. นำเข้าไฟล์ ‘.pbiviz’ ลงในรายงานของคุณ (ดูที่หัวข้อ [นำเข้าวิชวลแบบกำหนดเองจากส่วนไฟล์](#import-a-custom-visuals-from-a-file) ด้านบน)

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด

* วิชวลแบบกำหนดเองจะถูกเพิ่มเฉพาะในรายงานที่นำเข้า ถ้าคุณต้องการใช้วิชวลในรายงานอื่น คุณจำเป็นต้องนำเข้าในรายงานนั้นด้วยเช่นกัน เมื่อรายงานที่มีวิชวลแบบกำหนดเอง ถูกบันทึกโดยใช้ตัวเลือก **บันทึกเป็น** สำเนาของวิชวลแบบกำหนดเองจะถูกบันทึกไปกับรายงานใหม่

* ถ้าคุณไม่เห็นบานหน้าต่าง **การจัดรูปแบบการแสดงข้อมูล** แสดงว่าคุณไม่มีสิทธิ์การแก้ไขรายงาน  คุณสามารถเพิ่มวิชวลแบบกำหนดเองได้ ก็ต่อเมื่อคุณสามารถแก้ไขรายงานเท่านั้น ไม่ใช่เมื่อรายงานนั้นได้ถูกแชร์ให้คุณ

## <a name="troubleshoot"></a>การแก้ไขปัญหา

สำหรับข้อมูลเกี่ยวกับการแก้ไข เยี่ยมชม [แก้ไขปัญหาวิชวลแบบกำหนดเองของ Power BI ของคุณ](power-bi-custom-visuals-troubleshoot.md)

## <a name="faq"></a>คำถามที่ถามบ่อย

สำหรับข้อมูลเพิ่มเติมและคำตอบที่คุณอยากรู้ โปรดเยี่ยมชม[คำถามที่ถามบ่อยเกี่ยวกับวิชวลแบบกำหนดเองของ Power BI](power-bi-custom-visuals-faq.md#organizational-custom-visuals)

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)

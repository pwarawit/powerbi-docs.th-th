---
title: วิชวลแบบกำหนดเองใน Power BI
description: การแสดงข้อมูลแบบกำหนดเองใน Power BI
author: sranins
ms.author: rasala
manager: kfile
ms.reviewer: maghan
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/15/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: 3fd2f3e47c9b6dd2144ed5a66d45e65a00c5b92e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051256"
---
# <a name="custom-visuals-in-power-bi"></a>วิชวลแบบกำหนดเองใน Power BI

เมื่อสร้าง หรือแก้ไขรายงาน Power BI คุณสามารถใช้ชนิดต่าง ๆ ของภาพ แสดงไอคอนสำหรับวิชวลเหล่านี้ในการ**แสดงภาพ**บานหน้าต่าง ภาพเหล่านี้มาทำแพคเกจล่วงหน้าเมื่อคุณดาวน์โหลด[Power BI Desktop](https://powerbi.microsoft.com/desktop/)หรือเปิดการ[บริการ Power BI](https://app.powerbi.com)

![การจัดรูปแบบการแสดงข้อมูล](media/power-bi-custom-visuals/power-bi-visualizations.png)

อย่างไรก็ตาม คุณไม่จำกัดชุดของวิชวลนี้ ถ้าคุณเลือกจุดไข่ปลา (...) ที่ด้านล่าง แหล่งอื่นของวิชวลในรายงานจะพร้อมใช้งาน -*วิชวลแบบกำหนดเอง*

นักพัฒนาสร้างวิชวลแบบกำหนดเองโดยใช้ SDK วิชวลแบบกำหนดเอง ภาพเหล่านี้เปิดใช้งานผู้ใช้ทางธุรกิจเพื่อดูข้อมูลของพวกเขาในวิธีที่ดีที่สุดเหมาะกับธุรกิจของพวกเขา ผู้เขียนรายงานสามารถนำเข้าไฟล์วิชวลแบบกำหนดเองลงในรายงานของพวกเขา และใช้กับที่ทำกับวิชวล Power BI อื่น ๆ วิชวลแบบกำหนดเองเป็นพลเมืองคลาแรกใน Power BI และคุณสามารถ กรอง เน้น แก้ไข แชร์ และอื่น ๆ

วิชวลแบบกำหนดเองถูกปรับใช้ในสามวิธี:

* ไฟล์วิชวลแบบกำหนดเอง
* การแสดงผลด้วยภาพขององค์กร
* วิชวลจาก Marketplace

## <a name="custom-visual-files"></a>ไฟล์วิชวลแบบกำหนดเอง

วิชวลแบบกำหนดเองเป็นแพคเกจที่รวมเอาโค้ดสำหรับข้อมูลบริการได้ ทุกคนสามารถสร้างวิชวลแบบกำหนดเอง และแพคเกจเป็นเดียว`.pbiviz`แฟ้ม แล้วนำเข้าลงในรายงาน Power BI ได้

> [!WARNING]
> วิชวลแบบกำหนดเองอาจมีรหัสซึ่ง มีความปลอดภัยหรือความเสี่ยงด้านความเป็นส่วนตัว ตรวจสอบให้แน่ใจว่า คุณเชื่อถือผู้เขียนและแหล่งภาพแบบกำหนดเองก่อนที่จะนำเข้าไปยังรายงานของคุณ

## <a name="organizational-visuals"></a>การแสดงผลด้วยภาพขององค์กร

ผู้ดูแลระบบ power BI อนุมัติ และปรับใช้วิชวลแบบกำหนดเองลงในองค์กรของพวกเขา ซึ่งผู้เขียนรายงานสามารถค้นหา ปรับปรุง และใช้ ผู้ดูแลระบบสามารถจัดการได้อย่างง่ายดาย (ตัวอย่าง อัปเดตเวอร์ชัน ปิดใช้งาน/เปิดใช้งาน) วิชวลเหล่านี้ได้

 [อ่านเพิ่มเติมเกี่ยวกับรูปภาพขององค์กร](power-bi-custom-visuals-organization.md)

## <a name="marketplace-visuals"></a>วิชวลจาก Marketplace

สมาชิกในชุมชน Microsoft มีมอบวิชวลแบบกำหนดเองสำหรับสิทธิประโยชน์สาธารณะ และเผยแพร่ไปยัง[AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) marketplace คุณสามารถดาวน์โหลดเหล่านี้วิชวลเพิ่มลงในรายงาน Power BI ของคุณได้ Microsoft มีทดสอบ และอนุมัติเหล่านี้วิชวลแบบกำหนดเองสำหรับฟังก์ชันการทำงานและคุณภาพ

AppSource [คืออะไร?](developer/office-store.md) ตำแหน่งคุณสามารถค้นหาแอป add-in และส่วนขยายสำหรับซอฟต์แวร์ Microsoft ของคุณได้ [AppSource](https://appsource.microsoft.com/)ล้านของผู้ใช้ ของผลิตภัณฑ์เช่น Office 365, Azure, Dynamics 365, Cortana และ Power BI เพื่อแก้ไขปัญหาที่ช่วยในการทำงานให้สำเร็จได้อย่างมีประสิทธิภาพ insightfully เพิ่มเติม และสวยงาม กว่าที่เคยเชื่อมต่อ

### <a name="certified-visuals"></a>วิชวลที่ผ่านการรับรองแล้ว

Power BI ได้รับการรับรองวิชวลเป็นวิชวลจาก marketplace ที่ผ่านไปทดสอบคุณภาพตอบเพิ่มเติม และได้รับการสนับสนุนในสถานการณ์สมมติเพิ่มเติม เช่น[สมัครสมาชิกอีเมล](https://docs.microsoft.com/power-bi/service-report-subscribe)และ[ส่งไปยัง PowerPoint](https://docs.microsoft.com/power-bi/service-publish-to-powerpoint).
เมื่อต้องการดูรายการของวิชวลแบบกำหนดเองได้ที่ผ่านการรับรอง หรือต้องการส่งวิชวลของคุณเอง ให้ดู [วิชวลแบบกำหนดเองที่ผ่านการรับรองแล้ว](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified)

คุณเป็นนักพัฒนาเว็บ และสนใจสร้างวิชวลของคุณเอง และเพิ่มเข้าไปใน AppSource หรือไม่ ดู[พัฒนาวิชวลแบบกำหนดเองของ Power BI](developer/custom-visual-develop-tutorial.md)และเรียนรู้วิธีการ[เผยแพร่วิชวลแบบกำหนดเองไปยัง AppSource](https://docs.microsoft.com/power-bi/developer/office-store)

### <a name="import-a-custom-visual-from-a-file"></a>นำเข้าภาพที่กำหนดเองจากไฟล์

1. เลือกจุดไข่ปลาจากด้านล่างของคำ**แสดงภาพ**บานหน้าต่าง

    ![visualizations2](media/power-bi-custom-visuals/power-bi-visualizations2.png)

2. จากรายการดรอปดาวน์ เลือก**นำเข้าจากไฟล์**

    ![นำเข้าจากไฟล์](media/power-bi-custom-visuals/power-bi-custom-visual-import-from-file.png)

3. จากเมนูไฟล์เปิด เลือกแบบ`.pbiviz`ไฟล์ที่คุณต้อง การนำเข้าแล้ว เลือก**เปิด** ไอคอนของวิชวลแบบกำหนดเองจะถูกเพิ่มไปยังด้านล่างของของคุณ**แสดงภาพ**บานหน้าต่างนั้น และจะพร้อมใช้งานในรายงานของคุณ

    ![cv ที่นำเข้าแล้ว](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="import-organizational-visuals"></a>นำเข้าการแสดงผลด้วยภาพขององค์กร

1. เลือกจุดไข่ปลาจากด้านล่างของคำ**แสดงภาพ**บานหน้าต่าง

    ![แสดงภาพองค์กร 1](media/power-bi-custom-visuals/power-bi-visual-org-01.png)

2. จากรายการดรอปดาวน์ เลือก**นำเข้าจาก marketplace**

    ![แสดงภาพองค์กร 2](media/power-bi-custom-visuals/power-bi-visual-org-02.png)

3. เลือก**องค์กรของฉัน**จากเมนบนแท็บด้านบน

    ![แสดงภาพองค์กร 3](media/power-bi-custom-visuals/power-bi-visual-org-03.png)

4. เลื่อนผ่านรายการเพื่อการค้นหาวิชวลที่จะนำเข้า

    ![แสดงภาพองค์กร 4](media/power-bi-custom-visuals/power-bi-visual-org-04.png)

5. เลือก**เพิ่ม**การนำเข้าวิชวลแบบกำหนดเอง ไอคอนจะถูกเพิ่มไปยังด้านล่างของของคุณ**แสดงภาพ**บานหน้าต่างนั้น และจะพร้อมใช้งานในรายงานของคุณ

    ![แสดงภาพองค์กร 5](media/power-bi-custom-visuals/power-bi-visual-org-05.png)

## <a name="download-or-import-custom-visuals-from-microsoft-appsource"></a>ดาวน์โหลด หรือนำเข้าวิชวลแบบกำหนดเองจาก Microsoft AppSource

คุณมีสองตัวเลือกสำหรับการดาวน์โหลด และนำเข้าวิชวลแบบกำหนดเอง: จากภาย ใน Power BI และจาก[เว็บไซต์ AppSource](https://appsource.microsoft.com/)

### <a name="import-custom-visuals-from-within-power-bi"></a>นำเข้าวิชวลแบบกำหนดเองจากภายใน Power BI

1. เลือกจุดไข่ปลาจากด้านล่างของคำ**แสดงภาพ**บานหน้าต่าง

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

7. เลือก**เพิ่ม**การนำเข้าวิชวลแบบกำหนดเอง ไอคอนจะถูกเพิ่มไปยังด้านล่างของของคุณ**แสดงภาพ**บานหน้าต่างนั้น และจะพร้อมใช้งานในรายงานของคุณ

    ![วิชวลที่นำเข้า](media/power-bi-custom-visuals/power-bi-custom-visual-imported.png)

### <a name="download-and-import-custom-visuals-from-microsoft-appsource"></a>ดาวน์โหลด และนำเข้าวิชวลแบบกำหนดเองจาก Microsoft AppSource

1. เริ่มจาก [Microsoft AppSource](https://appsource.microsoft.com) และเลือกแท็บสำหรับ**แอป**

    ![AppSource](media/power-bi-custom-visuals/power-bi-appsource-apps.png)

2. ไปยัง[หน้าผลลัพธ์แอป](https://appsource.microsoft.com/marketplace/apps) คุณสามารถดูแอปอันดับต้น ๆ ในแต่ละประเภท รวมถึง *แอป Power BI* เรากำลังค้นหาวิชวลแบบกำหนดเอง ดังนั้นเราเลือก**วิชวล Power BI**จากรายการนำทางด้านซ้ายเพื่อจำกัดผลลัพธ์

    ![วิชวล AppSource](media/power-bi-custom-visuals/power-bi-appsource-visuals.png)

3. AppSource แสดงไทล์สำหรับวิชวลแบบกำหนดเองแต่ละตัว  แต่ละไทล์มีสแนปช็อตภาพแบบกำหนดเอง ด้วยคำอธิบายสั้น ๆ และลิงก์ดาวน์โหลด เมื่อต้องการดูรายละเอียดเพิ่มเติม ให้เลือกไทล์

    ![เลือกวิชวลแบบกำหนดเอง](media/power-bi-custom-visuals/powerbi-custom-select-visual.png)

4. บนหน้ารายละเอียด คุณสามารถดูภาพหน้าจอ วิดีโอ คำอธิบายโดยละเอียด และอื่น ๆ เลือก**รับทันที**เพื่อดาวน์โหลดวิชวลแบบกำหนดเอง และยอมรับเงื่อนไขการใช้แล้ว

    ![รับ AppSource](media/power-bi-custom-visuals/power-bi-appsource-get.png)

5. เลือกลิงก์เพื่อดาวน์โหลดวิชวลแบบกำหนดเอง

    ![ดาวน์โหลด](media/power-bi-custom-visuals/powerbi-custom-download.png)

    หน้าดาวน์โหลดยังมีคำแนะนำเกี่ยวกับวิธีการนำเข้าวิชวลแบบกำหนดเองลงใน Power BI Desktop และบริการของ Power BI

    คุณยังสามารถดาวน์โหลดรายงานตัวอย่างการใช้วิชวลแบบกำหนดเอง ที่ใช้แสดงขีดความสามารถของมัน

    ![ลองตัวอย่าง](media/power-bi-custom-visuals/powerbi-custom-try-sample.png)

6. บันทึกการ`.pbiviz`ไฟล์ จากนั้น เปิด Power BI

7. นำเข้า`.pbiviz`ไฟล์ลงในรายงานของคุณ (ดูส่วน [นำเข้าภาพแบบกำหนดเองจากไฟล์](#import-a-custom-visual-from-a-file) ด้านบน)

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด

* วิชวลแบบกำหนดเองจะถูกเพิ่มเฉพาะในรายงานที่นำเข้า ถ้าคุณต้องการใช้วิชวลในรายงานอื่น คุณจำเป็นต้องนำเข้าในรายงานนั้นด้วยเช่นกัน เมื่อรายงานที่มีวิชวลแบบกำหนดเอง ถูกบันทึกโดยใช้ตัวเลือก **บันทึกเป็น** สำเนาของวิชวลแบบกำหนดเองจะถูกบันทึกไปกับรายงานใหม่

* ถ้าคุณไม่เห็นตัว**แสดงภาพ**บานหน้าต่าง ซึ่งหมายความว่า คุณไม่มีสิทธิ์แก้ไขรายงาน  คุณสามารถเพิ่มวิชวลแบบกำหนดเองได้ ก็ต่อเมื่อคุณสามารถแก้ไขรายงานเท่านั้น ไม่ใช่เมื่อรายงานนั้นได้ถูกแชร์ให้คุณ

## <a name="troubleshoot"></a>การแก้ไขปัญหา

เมื่อต้องการแก้ไข[แก้ไขปัญหาวิชวลแบบกำหนดเองของ Power BI ของคุณ](power-bi-custom-visuals-troubleshoot.md)

## <a name="faq"></a>คำถามที่ถามบ่อย

สำหรับข้อมูลเพิ่มเติมและคำตอบที่คุณอยากรู้ โปรดเยี่ยมชม[คำถามที่ถามบ่อยเกี่ยวกับวิชวลแบบกำหนดเองของ Power BI](power-bi-custom-visuals-faq.md#organizational-custom-visuals)

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [แสดงภาพในรายงาน Power BI](visuals/power-bi-report-visualizations.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)

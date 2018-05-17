---
title: ภาพรวมของโครงการชุดเนื้อหาบริการของ Power BI
description: โครงการการรับรองชุดเนื้อหา
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/20/2018
ms.author: maghan
ms.openlocfilehash: 2cc78b3d2a877e465d5f4bdc67f501b7de87f88e
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/09/2018
---
# <a name="overview-of-the-power-bi-service-content-pack-program"></a>ภาพรวมของโครงการชุดเนื้อหาบริการของ Power BI
ชุดเนื้อหาคือ ชุดของเนื้อหาสำเร็จรูป ที่ให้ผู้ใช้สามารถรับข้อมูลเชิงลึกจากแหล่งข้อมูลได้ในทันที ชุดเนื้อหามักจะเน้นไปยังสถานการณ์ทางธุรกิจที่เฉพาะเจาะจง ให้ข้อมูลเชิงลึกสำหรับบทบาท โดเมน หรือเวิร์กโฟลว์

ISV สามารถสร้างเทมเพลตชุดเนื้อหาที่ให้ลูกค้าเชื่อมต่อ และสร้างอินสแตนซ์ด้วยบัญชีของพวกเขา ในฐานะเป็นผู้เชี่ยวชาญโดเมน พวกเขาสามารถปลดล็อกข้อมูลในลักษณะที่ผู้ใช้งานทางธุรกิจสามารถบริเภคได้อย่างง่ายดาย ชุดเนื้อให้การตรวจสอบและวิเคราะห์ที่เป็นเฉพาะกิจ แก่ลูกค้าของคุณโดยไม่ต้องลงทุนโครงสร้างพื้นฐานของระบบรายงานมากนัก 

เทมเพลตของชุดเนื้อหาที่ ISV เหล่านี้สร้างขึ้น สามารถส่งไปให้ทีม Power BI เพื่อให้เผยแพร่ทางสาธารณะ ในแกลเลอรีชุดเนื้อหา Power BI (app.powerbi.com/getdata/services) และบน Microsoft AppSource (appsource.microsoft.com) ตัวอย่างประสบการณ์การใช้งานชุดเนื้อหาสาธารณะสามารถดูได้จาก[ที่นี่](template-content-pack-experience.md)

## <a name="overview"></a>ภาพรวม
ขั้นตอนทั่วไปเพื่อพัฒนา และส่งเทมเพลตชุดเนื้อหา มีอยู่ด้วยกันหลายขั้นตอน

 ![กระบวนการ](media/service-content-pack-overview/developer-content-pack-overview.png)

1. [ตรวจทานข้อกำหนดต่าง ๆ](#requirements) เพื่อให้แน่ใจว่าคุณได้ทำตามข้อกำหนดเหล่านั้น
2. [สร้างเนื้อหา](template-content-pack-authoring.md#queries)ใน Power BI Desktop
3. [สร้างแดชบอร์ด](template-content-pack-authoring.md#dashboard)ใน PowerBI.com
4. [ทดสอบชุดเนื้อหา](template-content-pack-testing.md)ด้วยตัวคุณเองภายในองค์กรของคุณ
5. [ส่ง](template-content-pack-testing.md#submission)เนื้อหาไปยัง Power BI สำหรับการเผยแพร่

<a name="requirements"></a>

## <a name="requirements"></a>ข้อกำหนด
เพื่อสร้างและส่งชุดเนื้อหาที่จะเผยแพร่ในบริการของ PowerBI และ AppSource คุณต้องทำตามเงื่อนไขต่อไปนี้:

* คุณมีแอปพลิเคชัน SaaS ที่ใช้โดยผู้ใช้ทางธุรกิจ
* แอปพลิเคชัน SaaS ของคุณมีข้อมูลที่ผู้ใช้สามารถแสดงใน Power BI
* แอปพลิเคชัน SaaS ของคุณมี API ที่สามารถเข้าถึงผ่านทางอินเทอร์เน็ตสาธารณะ ในอุดมคติแล้ว API จะเป็น API ที่อยู่บนพื้นฐาน REST หรือฟีด OData ชุดเนื้อหา Power BI สนับสนุนการรับรองความถูกต้องหลายชนิด เช่นการรับรองความถูกต้องพื้นฐาน, OAuth 2.0 และ คีย์ API 
* แอปพลิเคชัน SaaS ของคุณจะได้รับอนุมัติสำหรับการเผยแพร่ชุดเนื้อหา ส่งคำร้องขอของคุณไปที่ pbiservicesapps@microsoft.com เราจะตรวจทานแต่ละผลงานที่ส่ง เรื่องความเกี่ยวข้องและการใช้งานที่คาดไว้ 
* ข้อตกลงคู่ค้าที่มีการลงนาม คุณจะทำเช่นนั้นใน[ขั้นตอนการส่ง](template-content-pack-testing.md#submission)

โปรดดูส่วน[การเขียน](template-content-pack-authoring.md) สำหรับรายละเอียดเพิ่มเติมเกี่ยวกับข้อกำหนดด้านเทคนิค

## <a name="business-scenario"></a>สถานการณ์ทางธุรกิจ
ชุดเนื้อหาให้ข้อมูลเชิงลึกและเมตริกที่เน้นไปยังสถานการณ์เฉพาะทางธุรกิจ ความเข้าใจกลุ่มเป้าหมายของคุณ และประโยชน์ที่พวกเขาจะได้รับจากชุดเนื้อหา จะช่วยให้แน่ใจว่าผู้ใช้ของคุณจะประสบความสำเร็จด้วยชุดเนื้อหาของคุณ

### <a name="tips"></a>เคล็ดลับ
* ค้นให้เจอ กลุ่มเป้าหมายและงานที่พวกเขากำลังพยายามทำให้สำเร็จ  
* พุ่งเป้าไปยังช่วงเวลาที่กำหนด (ล่าสุด 90 วัน) หรือผลลัพธ์ N ค่าล่าสุด  
* นำเข้าตาราง/คอลัมน์ที่เกี่ยวข้องกับสถานการณ์ของคุณเท่านั้น  
* พิจารณาเสนอชุดเนื้อหามากกว่าหนึ่งชุด สำหรับสถานการณ์ที่แตกต่างกัน  

## <a name="frequently-asked-questions"></a>คำถามที่ถามบ่อย
**ฉัน ในฐานะเป็นบุคคลที่สาม สามารถสร้างเป็นชุดเนื้อหาสำหรับบริการของ Power BI เพื่อใช้โปรแกรมประยุกต์ SaaS ที่ฉันไม่ได้เป็นเจ้าของได้หรือไม่?**

เราจำเป็นต้องมีการลงนามใน ข้อตกลงคู่ค้า กับเจ้าของแอปพลิเคชัน SaaS ก่อนที่จะเผยแพร่ชุดเนื้อหาในบริการ ในฐานะเป็นบุคคลสาม คุณจะต้องจัดให้มีการลงนามในข้อตกลงคู่ค้ากับเจ้าของแอปพลิเคชัน SaaS

**ฉันไม่มี API สาธารณะสำหรับนักพัฒนา สำหรับบริการของฉัน ฉันยังสามารถสร้างชุดเนื้อหาบริการของ Power BI ที่ดึงข้อมูลจากที่เก็บข้อมูลโดยตรงได้หรือไม่?**

ไม่ ชุดเนื้อหาบริการของ Power BI จำเป็นต้องมี API สำหรับนักพัฒนาที่สามารถเข้าถึงผ่านทางอินเทอร์เน็ตสาธารณะได้

**API ชนิดไหนที่ได้รับการสนับสนุนโดยบริการชุดเนื้อหา และมีการรับรองความถูกต้องชนิดไหนที่ทำงานด้วยกันได้?**

ชุดเนื้อหาบริการของ Power BI สนับสนุน REST API หรือฟีด OData ใด ๆ Power BI สามารถทำงานกับการรับรองความถูกต้องหลายชนิด รวมไปถึงการรับรองความถูกต้องพื้นฐาน, OAuth2.0 และ คีย์ API ของเว็บ รายละเอียดเพิ่มเติมเกี่ยวกับข้อกำหนดด้านเทคนิค ในบทความ[การเขียน](template-content-pack-authoring.md#dashboard)

**ฉันมีชุดเนื้อหาที่เผยแพร่ไปแล้วใน Power BI วิธีฉันสามารถอัปเดตชุดเนื้อหาได้อย่างไร?**

ชุดเนื้อหาที่เผยแพร่แล้วสามารถอัปเดตได้เดือนละครั้ง คำขอการอัปเดตที่ส่งไปยัง [pbiservicesapps@microsoft.com](mailto:pbiservicesapps@microsoft.com) ก่อนวันสุดท้ายของเดือนปัจจุบัน จะเผยแพร่ในสัปดาห์แรกของเดือนถัดไป

**ฉันมีคำถามเพิ่มเติมเกี่ยวกับชุดเนื้อหาบริการ ฉันสามารถติดต่อคุณได้อย่างไร?**

อีเมลคำถามของคุณมาหาเราได้ที่ [pbiservicesapps@microsoft.com](mailto:pbiservicesapps@microsoft.com)

## <a name="support"></a>ฝ่ายสนับสนุน
สำหรับการสนับสนุนในระหว่างการพัฒนา โปรดไปที่ [https://powerbi.microsoft.com/support](https://powerbi.microsoft.com/support) ที่นี่มาการตรวจสอบและจัดการอยู่ตลอด ปัญหาของลูกค้าจะไปถึงทีมงานที่เกี่ยวข้องได้อย่างรวดเร็ว

## <a name="next-step"></a>ขั้นตอนถัดไป
[การเขียน](template-content-pack-authoring.md)

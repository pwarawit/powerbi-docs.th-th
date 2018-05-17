---
title: คำถามที่ถามบ่อยเกี่ยวกับ Power BI Embedded
description: เรียกดูรายการของคำถามที่ถามบ่อยและคำตอบเกี่ยวกับ Power BI Embedded
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
ms.date: 03/07/2018
ms.author: maghan
ms.openlocfilehash: 52ff1095c063be867354a23e0e8e4908a4b4e1d7
ms.sourcegitcommit: ee5d044db99e253c27816e0ea6bdeb9e39a2cf41
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/08/2018
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>คำถามที่ถามบ่อยเกี่ยวกับ Power BI Embedded

* ถ้าคุณมีคำถามอื่น [ลองถามชุมชน Power BI](http://community.powerbi.com/)
* ยังคงมีปัญหาใช่หรือไม่? โปรดไป[หน้าการสนับสนุน Power BI](https://powerbi.microsoft.com/support/)

## <a name="general"></a>ทั่วไป

### <a name="what-is-power-bi-embedded"></a>Power BI Embedded คืออะไร?

Microsoft Power BI Embedded อนุญาตให้นักพัฒนาแอปพลิเคชัน ฝังตัวรายงาน แดชบอร์ด และไทล์ อันน่าทึ่งและโต้ตอบได้ ลงในแอปพลิเคชัน โดยไม่ต้องเสียเวลาและค่าใช้จ่ายพัฒนาการแสดงภาพและการควบคุมของตัวเองใหม่ทั้งหมด

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>ใครคือกลุ่มเป้าหมายสำหรับ Power BI Embedded?

นักพัฒนาและบริษัทซอฟต์แวร์ ที่สร้างแอปพลิเคชันของตนเองที่เรียกกันว่า ผู้จัดจำหน่ายซอฟต์แวร์อิสระ (ISV)

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Power BI Embedded แตกต่างจากบริการของ Power BI อย่างไร?

Power BI Embedded มีไว้สำหรับ ISV หรือนักพัฒนาที่กำลังสร้างแอปพลิเคชัน และต้องการฝังวิชวลลงในแอปพลิเคชันเหล่านั้น เพื่อช่วยให้ลูกค้าของพวกเขาตัดสินใจโดยไม่ต้องการสร้างโซลูชันการวิเคราะห์ขึ้นมาใหม่ทั้งหมด การฝังตัวการวิเคราะห์ ช่วยให้ผู้ใช้ทางธุรกิจเข้าถึงข้อมูลธุรกิจ และดำเนิการนคิวรี เพื่อสร้างข้อมูลเชิงลึกด้วยข้อมูลนี้ภายในแอปพลิเคชัน

Power BI ทางกลับกัน คือ โซลูชันการให้บริการซอฟต์แวร์การวิเคราะห์ ที่ช่วยให้องค์กรของพวกเขามีภาพเดียวกันสำหรับข้อมูลทางธุรกิจที่สำคัญที่สุดของพวกเขา

### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>อะไรคือความแตกต่างระหว่าง Power BI Premium และ Power BI Embedded?

Power BI Premium มีความจุที่ปรับให้เหมาะกับองค์กร ที่ต้องการโซลูชัน BI ที่สมบูรณ์ ที่ให้มุมมองเดียวกันแก่ หน่วยงาน คู่ค้า ลูกค้า และผู้จัดหาสินค้าขององค์กร Power BI Premium ช่วยให้องค์กรของคุณตัดสินใจ Power BI Premium เป็นผลิตภัณฑ์ SaaS ที่ให้ผู้ใช้สามารถบริโภคเนื้อหาผ่านทางพอร์ทัล Power BI แอปสำหรับอุปกรณ์เคลื่อนที่ และผ่านแอปที่พัฒนาขึ้นเองภายใน

Power BI Embedded มีไว้สำหรับ ISV หรือนักพัฒนาที่กำลังสร้างแอปพลิเคชัน และต้องการฝังวิชวลลงในแอปพลิเคชันเหล่านั้น Power BI Embedded ช่วยการตัดสินใจของลูกค้าคุณ เนื่องจาก Power BI Embedded ออกแบบมาสำหรับนักพัฒนาแอปพลิเคชัน ลูกค้าของแอปพลิเคชันนั้นสามารถใช้เนื้อหาที่เก็บไว้ในความจุของ Power BI Embedded รวมไปถึงทุกคนภายใน หรือภายนอกองค์กร เนื้อหาที่บรรจุใน Power BI Embedded ไม่สามารถแชร์ผ่านการ แสดงผลเว็บด่วน หรือแสดงผลด่วนไปยัง SharePoint และจะไม่สนับสนุนรายงาน SSRS

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Microsoft จะแนะนำลูกค้าอย่างไร ว่าเมื่อไรที่ลูกค้าควรซื้อ Power BI Embedded และเมื่อไรที่ควรซื้อ Power BI Premium?

คำแนะนำของ Microsoft คือ องค์กรซื้อ Power BI Premium ซึ่งเป็นโซลูชัน BI บนระบบคลาวด์ ระดับองค์กร แบบบริการตนเอง และ ISV ซื้อ Power BI Embedded ซึ่งเป็นคอมโพเนนต์การวิเคราะห์แบบฝังตัวที่ทำงานด้วยคลาวด์ อย่างไรก็ตาม ไม่มีข้อจำกัดว่าลูกค้าสามารถซื้อผลิตภัณฑ์ใดได้บ้าง

อาจมีบางกรณีที่ ISV (มักมีขนาดใหญ่) ต้องการใช้ P SKU เพื่อรับประโยชน์เพิ่มเติมของบริการ Power BI ที่รวมให้อยู่แล้ว ภายในองค์กรของพวกเขา ตลอดจนการฝังตัวในแอปพลิเคชันของพวกเขา และแน่นอน บางองค์กรอาจตัดสินใจที่จะใช้ A SKU ใน Azure ถ้าพวกเขาสนใจใช้งานเฉพาะการแอปพลิเคชันทางธุรกิจ และการฝังการวิเคราะห์ลงไปเท่านั้น และจะไม่สนใจที่ใช้บริการ Power BI ที่รวมให้อยู่แล้ว

### <a name="how-many-embed-tokens-can-i-create"></a>ฉันสามารถสร้างโทเค็นฝังตัวได้มากแค่ไหน?

โทเค็นฝังตัวด้วยสิทธิ์การใช้งาน PRO มีไว้สำหรับการพัฒนาและการทดสอบ จึงจำกัดจำนวนโทเค็นฝังตัวของบัญชีหลัก Power BI ที่สามารถสร้างขึ้นได้ คุณต้อง[ซื้อความจุ](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical)สำหรับการฝังตัวในสภาพแวดล้อมการทำงานจริง ไม่มีข้อจำกัดเกี่ยวกับจำนวนโทเค็นฝังตัวที่คุณสามารถสร้างขึ้นเมื่อซื้อความจุแล้ว

### <a name="when-will-power-bi-embedded-be-available-in-azure"></a>เมื่อไรที่ Power BI Embedded มีใน Azure?

ตอนนี้ Power BI Embedded มีให้ใช้งานแล้ว

## <a name="technical"></a>ทางเทคนิค

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>อะไรคือความแตกต่างระหว่าง A SKU ใน Azure และ EM SKU ใน Office 365

PowerBI.com เป็นโซลูชันระดับองค์กรที่มีความสามารถมากมายเช่น การทำงานร่วมกันทางสังคม การสมัครอีเมล ฯลฯ ในรูปของ SaaS

Power BI Embedded คือ ชุดของ API ที่มีให้กับนักพัฒนา เพื่อสร้างโซลูชันการวิเคราะห์แบบฝังตัวในรูปของ Platform as a Service สำหรับสถานการณ์การฝังตัวการวิเคราะห์ PowerBI.com ช่วยให้ ISV และนักพัฒนาจัดการโซลูชันการฝังตัวการวิเคราะห์ และตั้งค่าในระดับผู้เช่า

ต่อไปนี้เป็นความแตกต่างบางส่วน ที่คุณอาจใช้งานแต่ละผลิตภัณฑ์

|ลักษณะการทำงาน  |Power BI Embedded<br>(A SKU) |ความจุ Power BI Premium<br>(EM SKU)  |
|---------|---------|---------|
|ฝังวัตถุจากพื้นที่ทำงานแอป Power BI     |ความจุ Azure |ความจุ Office 365 |
|ต้องการสิทธิ์การใช้งาน Power BI เพื่อใช้รายงาน |ไม่ใช่  |ใช่ |
|ใช้รายงาน Power BI ในแอปพลิเคชันแบบฝังตัว |ใช่  |ใช่ |
|ใช้รายงาน Power BI ใน SharePoint |ไม่ใช่ |ใช่ |
|ใช้รายงาน Power BI ใน Teams |ไม่ใช่ |ใช่ |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI ในตอนนี้มี SKU สามตัวสำหรับการฝังตัว: A SKU, EM SKU และ P SKU ฉันควรซื้อแบบไหนสำหรับสถานการณ์ของฉัน?

|  |A SKU (Power BI Embedded)  |EM SKU (Power BI Premium)  |P SKU (Power BI Premium)  |
|---------|---------|---------|---------|
|การซื้อ     |พอร์ทัล Azure |Office |Office |
|ใช้กรณี |* ฝังเนื้อหาในแอปพลิเคชันของคุณเอง |* ฝังเนื้อหาในแอปพลิเคชันของคุณเอง<br>* แชร์เนื้อหากับผู้ใช้ Power BI ฟรี ภายนอก PowerBI.com และฝังไว้ในแอปพลิเคชัน SaaS อื่น ๆ (SharePoint, Teams) |* ฝังเนื้อหาในแอปพลิเคชันของคุณเอง<br>* แชร์เนื้อหากับผู้ใช้ Power BI ฟรี ภายนอก PowerBI.com และฝังไว้ในแอปพลิเคชัน SaaS อื่น ๆ (SharePoint, Teams)<br>* แชร์เนื้อหากับผู้ใช้ Power BI ฟรี ผ่าน PowerBI.com  |
|การเรียกเก็บเงิน |รายชั่วโมง |รายเดือน |รายเดือน |
|ข้อผูกมัด  |ไม่มีข้อผูกมัด |รายปี  |รายเดือน/รายปี |
|ความแตกต่าง |มีความยือหยุ่มเต็มที่ - สามารถสเกลขึ้น/ลง, หยุด/ทำงานต่อ ทรัพยากรในพอร์ทัล Azure หรือผ่าน API  |สามารถใช้เพื่อฝังเนื้อหาใน SharePoint Online และ Microsoft Teams |รวมการฝังในแอปพลิเคชัน และการใช้บริการของ Power BI ในความจุเดียวกัน |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>ข้อกำหนดเบื้องต้นเพื่อสร้างความจุ PBIE ใน Azure คืออะไร?

- คุณจำเป็นต้องลงชื่อเข้าใช้ไดเรกทอรีขององค์กรของคุณ (บัญชีผู้ใช้ MSA จะไม่ได้รับการสนับสนุน)
- คุณจำเป็นต้องมีผู้เช่า Power BI เช่น มีผู้ใช้อย่างน้อยหนึ่งคนในไดเรกทอรีของคุณลงทะเบียนกับ Power BI 
- คุณต้องมีการสมัครใช้งาน Azure ในไดเรกทอรีขององค์กรของคุณ

### <a name="how-can-i-monitor-capacity-consumption"></a>ฉันสามารถตรวจสอบปริมาณการใช้ความจุได้อย่างไร?

การตรวจสอบผ่าน Azure อยู่ในแผนงานระยะใกล้ ทรัพยากร Azure, Power BI Embedded จะรวม KPI สำหรับตรวจสอบ ที่จะแสดงสถานะและปริมาณการใช้งาน

### <a name="will-my-capacity-scale-automatically-to-adjust-to-the-consumption-of-my-app"></a>ความจุของฉันจะปรับตามปริมาณการใช้แอปของฉันได้ตามอัตโนมัติหรือไม่?

ขณะนี้ยังไม่มีการ scale โดยอัตโนมัติ แต่ APIs ทั้งหมดสามารถ scale ได้ทุกเวลา

### <a name="what-is-the-authentication-model-for-power-bi-embedded"></a>อะไรคือรูปแบบการรับรองความถูกต้องสำหรับ Power BI Embedded?

Power BI Embedded จะยังคงใช้ Azure AD สำหรับการรับรองความถูกต้องของผู้ใช้หลัก (ผู้ใช้ Power BI Pro ที่ได้รับการกำหนดสิทธิ์) และการรับรองความถูกต้องแอปพลิเคชันภายใน Power BI

การรับรองความถูกต้องและการอนุญาตของผู้ใช้แอปพลิเคชัน จะพัฒนาโดย ISV โดยที่ ISV สามารถสร้างการรับรองความถูกต้องของตนเองสำหรับแอปพลิเคชันของพวกเขา

ถ้าคุณมีผู้เช่า Azure AD อยู่แล้ว คุณสามารถใช้ไดเรกทอรีที่มีอยู่ หรือสร้างผู้เช่า Azure AD ใหม่สำหรับความปลอดภัยของเนื้อหาในแอปพลิเคชันแบบฝังตัว

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Power BI Embedded แตกต่างจากบริการอื่น ๆ ของ Azure อย่างไร?

ISV/นักพัฒนาต้องมีบัญชี Power BI ก่อนที่จะซื้อ Power BI Embedded ใน Azure ภูมิภาคการปรับใช้งาน Power BI Embedded ของคุณถูกกำหนดโดยบัญชี Power BI ของคุณ จัดการทรัพยากร Power BI Embedded ของคุณใน Azure เพื่อ:

* Scale up/down
* เพิ่มผู้ดูแลความจุ
* หยุดบริการ/ทำงานต่อ

ใช้ PowerBI.com เพื่อกำหนด/ยกเลิก การกำหนดพื้นที่ทำงานให้กับความจุ Power BI Embedded ของคุณ

### <a name="what-deploy-regions-are-supported"></a>ภูมิภาคใดที่ได้รับการสนับสนุน?

Australia Southeast, Brazil South, Canada Central, East US 2, India West, Japan East, North Central US, North Europe, South Central US, Southeast Asia, UK South, West Europe, West US และ West US 2

### <a name="what-type-of-content-pack-data-can-be-embedded"></a>ข้อมูลชุดเนื้อหาชนิดใดบ้างที่สามารถฝังตัวได้?

**แดชบอร์ด**และ**ไทล์**ที่สร้างจากชุดข้อมูลชุดเนื้อหา*ไม่สามารถ*ฝังตัวได้ แต่**รายงาน**ซึ่งสร้างขึ้นจากชุดข้อมูลชุดเนื้อหา*สามารถ*ฝังตัวได้

## <a name="licensing"></a>สิทธิ์การใช้งาน

### <a name="how-do-i-purchase-power-bi-embedded"></a>ฉันซื้อ Power BI Embedded ได้อย่างไร

Power BI Embedded มีให้ผ่านทาง Azure

### <a name="how-power-bi-embedded-be-metered"></a>วัดปริมาณการใช้ Power BI Embedded อย่างไร?

Power BI Embedded จะวัดเป็นรายชั่วโมง

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>ปริมาณการใช้ Power BI Embedded แสดงขึ้นมาบนใบเรียกเก็บเงินของฉันได้อย่างไร?

Power BI Embedded เรียกเก็บเงินตามอัตรารายชั่วโมง ขึ้นกับชนิดของโหนดที่ปรับใช้ โปรดทราบว่า ตราบใดที่ทรัพยากรของคุณยังเปิดใช้งาน คุณจะถูกเรียกเก็บเงินแม้ว่าจะไม่มีการใช้งานก็ตาม เพื่อหยุดการเรียกเก็บเงิน คุณต้องหยุดทรัพยากรของคุณชั่วคราว การหยุดสามารถทำ ผ่าน Azure หรือผ่าน ARM API

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-of-the-benefits-of-power-bi-embedded-in-azure"></a>เกิดอะไรขึ้นถ้าฉันซื้อ Power BI Premium แล้ว และตอนนี้ฉันต้องการคุณสมบัติบางประการของ Power BI Embedded ใน Azure

ลูกค้าจะยังคงต้องชำระเงินสำหรับการซื้อ Power BI Premium ใด ๆ ที่มีอยู่ จนกว่าจะถึงจุดสิ้นสุตตามข้อตกลงปัจจุบัน จากนั้นก็สามารถเปลี่ยนการซื้อ Power BI Premium ตามความจำเป็นเมื่อถึงเวลานั้น

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>ฉันยังต้องซื้อ Power BI Premium เพื่อเข้าถึง Power BI Embedded หรือไม่?

ไม่ Power BI Embedded รวมความจุ Azure ที่คุณต้องปรับใช้ และแจกจ่ายโซลูชันของคุณไปยังลูกค้า

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>ใครต้องมีสิทธิ์การใช้งาน Power BI Pro สำหรับ Power BI Embedded และทำไม?

นักวิเคราะห์ใด ๆ ที่ต้องเพิ่มรายงานไปยังพื้นที่ทำงาน Power BI, นักพัฒนาใด ๆ ที่ต้องใช้ REST API, ผู้ดูแลผู้เช่าใด ๆ ที่จำเป็นต้องจัดการผู้เช่า Power BI และกำลังการผลิต จะต้องมีสิทธิ์การใช้งาน Power BI Pro

เนื่องจาก Power BI Embedded อนุญาตให้ใช้ พอร์ทัล Power BI สำหรับการจัดการ และตรวจสอบเนื้อหาแบบฝังตัว สิทธิ์การใช้งาน Power BI Pro เป็นสิ่งจำเป็นเพื่อรับรองความถูกต้องแอปภายใน PowerBI.com เพื่อเข้าถึงรายงานในเก็บข้อมูลที่ถูกต้อง

### <a name="can-i-get-started-for-free"></a>ฉันสามารถเริ่มต้นใช้งานฟรีได้หรือไม่?

ได้ คุณสามารถใช้[เครดิต Azure](https://azure.microsoft.com/free/) ของคุณสำหรับ Power BI Embedded ได้

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>ฉันสามารถทดลองใช้ Power BI Embedded ใน Azure ได้หรือไม่?

เนื่องจาก Power BI Embedded เป็นส่วนหนึ่งของ Azure คุณสามารถใช้บริการด้วย[เครดิตจำนวน 200 ดอลลาร์สหรัฐฯ ที่คุณได้รับตอนลงทะเบียนสำหรับ Azure](https://azure.microsoft.com/free/)

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>อะไรคือข้อผูกมัดการซื้อสำหรับ Power BI Embedded? 

ลูกค้าอาจเปลี่ยนแปลงการใช้งานของพวกเขาเป็นรายชั่วโมง ไม่มีข้อผูกมัดรายเดือน หรือรายปี สำหรับบริการ Power BI Embedded

### <a name="where-is-power-bi-embedded-available-us-government-germany-china-what-is-the-timing"></a>ที่ไหนบ้างที่ Power BI Embedded มีให้ใช้งานได้แล้ว? รัฐบาลสหรัฐอเมริกา? เยอรมนี? จีน? กำหนดเวลาคืออะไร?

Power BI Embedded พร้อมให้ใช้ในงานคลาวด์เชิงพาณิชย์ Azure และในระบบคลาวด์ของรัฐบาลสหรัฐอเมริกา  Sovereign cloud สำหรับประเทศเยอรมนีและจีน จะถูกเพิ่มในอนาคต

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Power BI Embedded มีให้สำหรับองค์กรไม่แสวงหากำไร และสถานศึกษาหรือไม่?

องค์กรที่ไม่แสวงหากำไร และสถานศึกษาสามารถซื้อ Azure ได้ ไม่มีราคาพิเศษสำหรับลูกค้า Azure ชนิดเหล่านี้

คำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)

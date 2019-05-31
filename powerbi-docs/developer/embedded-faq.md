---
title: คำถามที่ถามบ่อยเกี่ยวกับ Power BI Embedded
description: เรียกดูรายการของคำถามที่ถามบ่อยและคำตอบเกี่ยวกับ Power BI Embedded
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/22/2019
ms.openlocfilehash: 1bdc31d550573b926d45776307b8fcade95f0dc0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222169"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>คำถามที่ถามบ่อยเกี่ยวกับ Power BI Embedded

* ถ้าคุณมีคำถามอื่น [ลองถามชุมชน Power BI](http://community.powerbi.com/)
* ยังคงมีปัญหาใช่หรือไม่? โปรดเยี่ยมชม[หน้าการสนับสนุน Power BI](https://powerbi.microsoft.com/support/)

## <a name="general"></a>ทั่วไป

### <a name="what-is-power-bi-embedded"></a>Power BI Embedded คืออะไร?

[Microsoft Power BI Embedded (PBIE)](azure-pbie-what-is-power-bi-embedded.md)ช่วยให้นักพัฒนาแอปพลิเคชันเพื่อฝังรายงานอันน่าทึ่ง โต้ตอบลงในแอปพลิเคชันของพวกเขา โดยไม่ต้องสร้างการแสดงภาพข้อมูลและตัวควบคุมตั้งแต่เริ่มต้นของตนเอง

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>ใครคือกลุ่มเป้าหมายสำหรับ Power BI Embedded?

นักพัฒนาและบริษัทซอฟต์แวร์ ผู้จำหน่ายซอฟต์แวร์ที่เรียกว่าอิสระ (Isv), เขียนโค้ดแอปพลิเคชัน

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Power BI Embedded แตกต่างจากบริการของ Power BI อย่างไร?

Power BI คือโซลูชันการให้บริการซอฟต์แวร์การวิเคราะห์ ที่ช่วยให้องค์กรของพวกเขามีภาพเดียวกันสำหรับข้อมูลทางธุรกิจที่สำคัญที่สุดของพวกเขา

Microsoft พัฒนา Power BI Embedded สำหรับ Isv อาจต้องการฝังวิชวลลงในแอปพลิเคชันของพวกเขาเพื่อช่วยให้ลูกค้าของพวกเขาทำการตัดสินใจการวิเคราะห์ ซึ่ง spares Isv การสร้างโซลูชันการวิเคราะห์ของตนเองด้วยตนเอง [ฝังตัวการวิเคราะห์](embedding.md)ช่วยให้ผู้ใช้ทางธุรกิจสามารถเข้าถึงข้อมูลทางธุรกิจ และดำเนินการคิวรีกับเพื่อสร้างข้อมูลเชิงลึกภายในแอปพลิเคชัน


### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>อะไรคือความแตกต่างระหว่าง Power BI Premium และ Power BI Embedded?

Power BI Premium คือ ความจุสินค้าองค์กรที่ต้องการโซลูชัน BI สมบูรณ์ที่มีมุมมองเดียวองค์กร คู่ค้า ลูกค้า และผู้จำหน่าย Power BI Premium ช่วยให้องค์กรของคุณตัดสินใจ Power BI Premium เป็นผลิตภัณฑ์ SaaS ที่อนุญาตให้ผู้ใช้สามารถบริโภคเนื้อหา ผ่าน แอปสำหรับอุปกรณ์เคลื่อน พัฒนาภายในแอป หรือ ในพอร์ทัล Power BI

Power BI Embedded มีไว้สำหรับ Isv ที่ต้องการฝังวิชวลลงในแอปพลิเคชันของพวกเขา Power BI Embedded ช่วยการตัดสินใจของลูกค้าคุณ เนื่องจาก Power BI Embedded ออกแบบมาสำหรับนักพัฒนาแอปพลิเคชัน ลูกค้าของแอปพลิเคชันนั้นสามารถใช้เนื้อหาที่เก็บไว้ในความจุของ Power BI Embedded รวมไปถึงทุกคนภายใน หรือภายนอกองค์กร คุณไม่สามารถใช้ Power BI Embedded ความจุเนื้อหาผ่านทางภายในคลิกเดียวเผยแพร่ไปยังเว็บ หรือภายในคลิกเดียวเผยแพร่ไปยัง SharePoint ได้

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Microsoft จะแนะนำลูกค้าอย่างไร ว่าเมื่อไหร่ที่ลูกค้าควรซื้อ Power BI Embedded Premium เทียบกับ Power BI Embedded

Microsoft แนะนำให้ องค์กรซื้อ Power BI Premium การระดับองค์กร โซลูชัน BI แบบบริการตนเอง cloud เราขอแนะนำ Isv ซื้อ Power BI Embedded สำหรับคอมโพเนนต์ของระบบคลาวด์วิเคราะห์แบบฝังตัว อย่างไรก็ตาม ลูกค้ามีไม่มีข้อจำกัดในการซื้อผลิตภัณฑ์ใด

อาจมีบางกรณีที่ ISV (มักมีขนาดใหญ่), นอกเหนือจากแอฝัง ต้องการใช้ P SKU เพื่อรับประโยชน์เพิ่มเติมของบริการ Power BI รวมให้อยู่แล้วภายในองค์กรของพวกเขา บางองค์กรอาจตัดสินใจที่จะใช้ A SKU ใน Azure หากพวกเขาสนใจเฉพาะการสร้างแอปพลิเคชันทางธุรกิจ และการฝังการวิเคราะห์ลงไป และไม่สนใจที่จะใช้บริการ Power BI ที่รวมให้อยู่แล้ว

### <a name="how-many-embed-tokens-can-i-create"></a>ฉันสามารถสร้างโทเค็นฝังตัวได้มากแค่ไหน?

ฝังโทเค็นกับสิทธิ์การใช้งาน PRO มีไว้สำหรับการพัฒนาและการทดสอบ จึงบัญชีหลัก Power BI หรือ[บริการหลัก](embed-service-principal.md)สามารถสร้างโทเค็นจำนวนจำกัดได้ [ซื้อความจุ](#technical)สำหรับการฝังตัวในสภาพแวดล้อมการทำงานจริง ไม่มีการจำกัดจำนวนฝังคุณสามารถสร้างเมื่อคุณซื้อความจุโทเค็นได้ ไปยัง[คุณลักษณะที่มี](https://docs.microsoft.com/rest/api/power-bi/availablefeatures) เพื่อตรวจสอบค่าการใช้งาน ที่สามารถบอกได้ว่าปัจจุบันมีการใช้งานฝังตัวแล้วกี่เปอร์เซ็นต์

## <a name="technical"></a>ทางเทคนิค

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>อะไรคือความแตกต่างระหว่าง A SKU ใน Azure และ EM SKU ใน Office 365

PowerBI.com เป็นองค์กรซอฟต์แวร์โซลูชันบริการ (SaaS) ที่มีความสามารถมากมายเช่นเครือข่ายสังคมทำงานร่วมกัน การสมัครใช้งานอีเมล และคุณลักษณะอื่น ๆ PowerBI.com ช่วยให้ Isv จัดการโซลูชันวิเคราะห์แบบฝังตัวของพวกเขาเนื้อหา และการตั้งค่าระดับผู้เช่า

Power BI Embedded คือ แพลตฟอร์เป็นบริการ (PaaS) ตั้งค่าของ Api ที่นักพัฒนาสามารถใช้เพื่อสร้างโซลูชันการวิเคราะห์แบบฝังตัว

ต่อไปนี้เป็นรายการบางส่วนของความแตกต่างของคุณลักษณะ

| ฟีเจอร์ | Power BI Embedded | ความจุ Power BI Premium | ความจุ Power BI Premium |
|----------------------------------------------------------------------------------|-------------------|---------------------------|---------------------------|
|   | (A SKU) | (EM SKUs) | (P SKUs) |
| อาร์ทิแฟกต์แบบฝังตัวจากพื้นที่ทำงานแอป Power BI | ความจุ Azure | ความจุ Office 365 | ความจุ Office 365 |
| ใช้รายงาน Power BI ในแอปพลิเคชันแบบฝังตัว | ใช่ | ใช่ | ใช่ |
| ใช้รายงาน Power BI ใน SharePoint | ไม่ใช่ | ใช่ | ใช่ |
| ใช้รายงาน Power BI ใน Dynamics | ไม่ใช่ | ใช่ | ใช่ |
| ใช้รายงาน Power BI ใน Teams (ไม่รวมแอปสำหรับอุปกรณ์เคลื่อนที่) | ไม่ใช่ | ใช่ | ใช่ |
| เข้าถึงเนื้อหาที่มีใบอนุญาต Power BI ฟรีใน Powerbi.com และ Power BI mobile | ไม่ใช่ | ไม่ใช่ | ใช่ |
| เข้าถึงเนื้อหาด้วยสิทธิ์การใช้งาน Power BI ฟรีที่ฝังในแอป MS Office | ไม่ใช่ | ใช่ | ใช่ |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI ในตอนนี้มี SKU สามตัวสำหรับการฝังตัว: A SKU, EM SKU และ P SKU ฉันควรซื้อแบบไหนสำหรับสถานการณ์ของฉัน?

|  |A SKU (Power BI Embedded)  |EM SKU (Power BI Premium)  |P SKU (Power BI Premium)  |
|---------|---------|---------|---------|
|การซื้อ  |พอร์ทัล Azure |Office |Office |
|ใช้กรณี | ฝังเนื้อหาในแอปพลิเคชันของคุณเอง | <li> ฝังเนื้อหาในแอปพลิเคชันของคุณเอง <br><br><br> <li> ฝังเนื้อหาในแอปพลิเคชัน MS Office: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [ทีม (ไม่รวมแอปสำหรับอุปกรณ์เคลื่อนที่)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) | <li> ฝังเนื้อหาในแอปพลิเคชันของคุณเอง <br><br><br> <li> ฝังเนื้อหาในแอปพลิเคชัน MS Office: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [ทีม (ไม่รวมแอปสำหรับอุปกรณ์เคลื่อนที่)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) <br><br><br> <li> แชร์เนื้อหากับผู้ใช้ Power BI ผ่าน [บริการ Power BI](https://powerbi.microsoft.com/)  |
|การเรียกเก็บเงิน |รายชั่วโมง |รายเดือน |รายเดือน |
|ข้อผูกมัด  |ไม่มีข้อผูกมัด |รายปี  |รายเดือน/รายปี |
|ความแตกต่าง |มีความยือหยุ่มเต็มที่ - สามารถสเกลขึ้น/ลง, หยุด/ทำงานต่อ ทรัพยากรในพอร์ทัล Azure หรือผ่าน API  |คุณสามารถใช้เพื่อฝังเนื้อหาใน SharePoint Online และ Microsoft Teams (ไม่รวมแอป) |รวมการฝังในแอปพลิเคชัน และการใช้บริการของ Power BI ในความจุเดียวกัน |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>ข้อกำหนดเบื้องต้นเพื่อสร้างความจุ PBIE ใน Azure คืออะไร?

* ลงชื่อเข้าใช้ในไดเรกทอรีขององค์กร (ไม่สนับสนุนบัญชี Microsoft)
* คุณจำเป็นต้องมีผู้เช่า Power BI นั่นคือ ผู้ใช้อย่างน้อยหนึ่งในไดเรกทอรีของคุณได้ลงทะเบียนสำหรับ Power BI 
* คุณต้องมีการสมัครใช้งาน Azure ในไดเรกทอรีขององค์กรของคุณ

### <a name="how-can-i-monitor-power-bi-embedded-capacity-consumption"></a>ฉันสามารถตรวจสอบปริมาณการใช้ความจุของ Power BI Embedded ได้อย่างไร

* ใช้[พอร์ทัลผู้ดูแลระบบ Power BI](../service-admin-portal.md#power-bi-embedded)

* ดาวน์โหลด[แอปเมตริก](https://review.docs.microsoft.com/power-bi/service-admin-premium-monitor-capacity)ใน Power BI

* ใช้[การบันทึกการวินิจฉัย Azure](azure-pbie-diag-logs.md)

### <a name="can-my-capacity-scale-automatically-to-adjust-to-my-app-consumption"></a>สามารถความจุของฉันปรับมาตราส่วนโดยอัตโนมัติเพื่อปรับปริมาณการใช้แอปของฉันได้อย่างไร

ในขณะที่มีอยู่ไม่อัตโนมัติมาตราส่วนเดี๋ยวนี้ Api ทั้งหมดจะพร้อมใช้งานการปรับขนาดได้ทุกเวลา

### <a name="why-creatingscalingresuming-a-capacity-results-in-putting-the-capacity-into-a-suspended-state"></a>ทำไม การสร้าง/ปรับขนาด/กลับมาใช้ความจุทำให้ความจุอยู่ในสถานะถูกระงับชั่วคราว?

เตรียมใช้งานความจุที่ (สเกล/ประวัติย่อ/สร้าง) อาจล้มเหลว คุณสามารถใช้ API รายละเอียดได้รับการตรวจสอบความจุ ProvisioningState: [ความจุ - รับรายละเอียด](https://docs.microsoft.com/rest/api/power-bi-embedded/capacities/getdetails)

### <a name="can-i-only-create-power-bi-embedded-capacities-in-a-specific-region"></a>ฉันสามารถสร้างความจุแบบฝังตัวของ Power BI ในพื้นที่เฉพาะได้หรือไม่

ด้วยคุณลักษณะ[หลายภูมิศาสตร์ (ตัวอย่าง)](embedded-multi-geo.md) คุณสามารถซื้อ[ความจุแบบฝังตัวของ Power BI](azure-pbie-create-capacity.md) ในภูมิภาคอื่นนอกจากตำแหน่งที่ตั้งหลักของผู้เช่า Power BI ของคุณ

### <a name="how-can-i-find-my-pbi-tenant-region"></a>ฉันจะหาภูมิภาคของฉันผู้เช่า PBI ได้อย่างไร

คุณสามารถใช้พอร์ทัล PBI เพื่อค้นหาผู้เช่า PBI ภูมิภาคของคุณ

[https://app.powerbi.com/](https://app.powerbi.com/) > ? เกี่ยวกับ Power BI

![เกี่ยวกับ ภูมิภาคผู้เช่า](media/embedded-faq/about-01.png)
![Power BI](media/embedded-faq/tenant-location-01.png)

### <a name="what-does-the-cloud-solution-provider-csp-channel-support"></a>แชนเนล Cloud Solution Provider (CSP) สนับสนุนอะไรได้หรือไม่

* คุณสามารถสร้าง PBIE ให้ผู้เช่าของคุณด้วยการสมัครใช้งานชนิด CSP
* บัญชีคู่ค้าสามารถลงชื่อเข้าใช้ในนามผู้เช่าของลูกค้า และซื้อ PBIE สำหรับผู้เช่าของลูกค้า กำหนดให้ผู้ใช้ที่เป็นผู้เช่าของลูกค้าเป็นผู้ดูแลความจุ Power BI

### <a name="why-do-i-get-an-unsupported-account-message"></a>เหตุใดฉันจึงได้รับข้อความว่า เป็นบัญชีที่ไม่สนับสนุน

Power BI ให้คุณต้องลงทะเบียนด้วยบัญชีผู้ใช้ขององค์กร พยายามลงทะเบียนสำหรับ Power BI โดยใช้บัญชี Microsoft ไม่ได้รับการสนับสนุน

### <a name="can-i-use-apis-to-create-and-manage-azure-capacities"></a>ฉันสามารถใช้ Api เพื่อสร้าง และจัดการความจุ Azure หรือไม่

ใช่ มี cmdlet ของ Powershell และ Azure Resource Manager REST Api คุณสามารถใช้เพื่อสร้าง และจัดการทรัพยากร PBIE

* [Rest Api ที่](https://docs.microsoft.com/rest/api/power-bi-embedded/)
* [Cmdlet ของ Powershell](https://docs.microsoft.com/powershell/module/azurerm.powerbiembedded/)

### <a name="what-is-the-pbi-embedded-dedicated-capacity-role-in-a-pbi-embedded-solution"></a>บทบาทความจุเฉพาะของ PBI ฝังตัว ในโซลูชัน PBI ฝังตัวคืออะไร?

เมื่อต้องการ[เลื่อนระดับโซลูชันของคุณไปยังการผลิต](embed-sample-for-customers.md#move-to-production)คุณจำเป็นต้องกำหนดเนื้อหา Power BI (พื้นที่ทำงานแอป) แอปพลิเคชันของคุณใช้ความจุ Power BI Embedded (A SKU)

### <a name="in-what-azure-regions-is-pbi-embedded-available"></a>ภูมิภาคใด Azure PBI ฝังตัวที่สามารถใช้งานได้อย่างไร

[PAM](https://ecosystemmanager.azurewebsites.net/home) (EcoManager) - ดูตัวจัดการความพร้อมใช้งานผลิตภัณฑ์

ภูมิภาคที่พร้อมใช้งาน (16 - ภูมิภาคเดียวกันกับ Power BI)

* สหรัฐอเมริกา (6) - สหรัฐอเมริกาตะวันออก สหรัฐอเมริกาตะวันออก 2 สหรัฐอเมริกากลางเหนือ สหรัฐอเมริกากลางใต้สหรัฐอเมริกาตะวันตก สหรัฐอเมริกาตะวันตก 2
* ยุโรป (2) - ยุโรปเหนือ ยุโรปตะวันตก
* เอเชียแปซิฟิก (2) - เอเชียตะวันออกเฉียงใต้ เอเชียตะวันออก
* บราซิล (1) - บราซิลใต้
* ญี่ปุ่น (1) - ญี่ปุ่นตะวันออก
* ออสเตรเลีย (1) - ออสเตรเลียตะวันออกเฉียงใต้
* อินเดีย (1) - อินเดียตะวันตก
* แคนาดา (1) - กลางแคนาดา
* สหราชอาณาจักร (1) - สหราชอาณาจักรใต้

### <a name="what-is-power-bi-embeddeds-authentication-model"></a>Power BI Embedded ของแบบจำลองรับรองความถูกต้องคืออะไร

Power BI Embedded ยังคงใช้ Azure AD สำหรับการรับรองความถูกต้องผู้ใช้หลัก (กำหนด Power BI Pro สิทธิ์การใช้งานผู้ใช้) หรือด้วย[บริการหลัก](embed-service-principal.md)สำหรับการรับรองความถูกต้องแอปพลิเคชันภายใน Power BI  

 ISV สามารถดำเนินการรับรองความถูกต้องและการอนุญาตสำหรับแอปพลิเคชันของตนเอง

คุณสามารถใช้ไดเรกทอรีที่มีอยู่ของคุณถ้าคุณมีผู้เช่า Azure AD คุณยังสามารถสร้างใหม่ผู้เช่า Azure AD สำหรับความปลอดภัยของเนื้อหาแอปพลิเคชันแบบฝังตัวได้

เพื่อรับโทเค็น AAD คุณสามารถใช้ไลบรารี [Azure Active Directory Authentication ตัวใดตัวหนึ่ง](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) ไลบรารีเหล่านี้เป็นไลบรารีไคลเอ็นต์ ที่พร้อมใช้งานบนหลายแพลตฟอร์ม

### <a name="my-application-already-uses-aad-for-user-authentication-how-can-we-use-this-identity-when-authenticating-to-power-bi-in-a-user-owns-data-scenario"></a>แอปพลิเคชันของฉันใช้ AAD สำหรับการรับรองความถูกต้องผู้ใช้แล้ว เราสามารถใช้ข้อมูลประจำตัวนี้เมื่อรับรองความถูกต้องไปยัง Power BI ในสถานการณ์ "ผู้ใช้เป็นเจ้าของข้อมูล" ได้อย่างไร?

เป็นมาตรฐาน OAuth ในนามของโฟลว์ (<https://docs.microsoft.com/azure/active-directory/develop/web-api>) คุณจำเป็นต้องกำหนดค่าแอปพลิเคชันของคุณให้ใช้สิทธิ์ของบริการ (มีขอบเขตจำเป็น) Power BI เมื่อคุณต้องการโทเค็นผู้ใช้แอปของคุณ คุณเพียงแค่เรียกไปยัง API AcquireTokenAsync ADAL ที่ใช้เข้าถึงผู้ใช้โทเค็น และระบุ URL ทรัพยากร Power BI เป็น ID ทรัพยากร:

```csharp
var context = new AD.AuthenticationContext(authorityUrl);
var userAssertion = new AD.UserAssertion(userAccessToken);
var clientAssertion = new AD.ClientAssertionCertificate(MyAppId, MyAppCertificate)
var authenticationResult = await context.AcquireTokenAsync(resourceId, clientAssertion, userAssertion);
```

### <a name="what-object-id-is-the-service-principal-object-id"></a>ID อ็อบเจ็กต์หลักบริการคือ ID วัตถุอะไร

การ*ID ออบเจ็กต์*จากหน้าจอหลักของแอลงทะเบียนเป็น ID ออบเจ็กต์สำหรับแอป

พบ ID ในวัตถุ*แอปพลิเคชันในไดเรกทอรีภายในเครื่องที่มีจัดการ > คุณสมบัติ*ส่วนคือ ID อ็อบเจ็กต์หลักของบริการที่คุณจำเป็นต้องใช้ ID วัตถุนี้เป็น การอ้างอิงหลักเกณฑ์การบริการสำหรับการดำเนินการ หรือทำการเปลี่ยนแปลงวัตถุที่ให้บริการหลักรหัส เช่นใช้หลักเกณฑ์การบริการเป็นผู้ดูแลระบบพื้นที่ทำงาน

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Power BI Embedded แตกต่างจากบริการอื่น ๆ ของ Azure อย่างไร?

คุณต้องมีบัญชี Power BI ก่อนซื้อ Power BI Embedded ใน Azure ภูมิภาคของคุณ Power BI Embedded ปรับใช้กำหนดบัญชี Power BI ของคุณ จัดการทรัพยากร Power BI Embedded ของคุณใน Azure เพื่อ:

* Scale up/down
* เพิ่มผู้ดูแลความจุ
* บริการหยุดชั่วคราว/ประวัติย่อ

ใช้ PowerBI.com เพื่อกำหนด/ยกเลิก การกำหนดพื้นที่ทำงานให้กับความจุ Power BI Embedded ของคุณ

### <a name="what-are-the-supported-deploy-regions"></a>รับการสนับสนุนคือภูมิภาคได้อย่างไร

Australia Southeast, Brazil South, Canada Central, East US 2, India West, Japan East, North Central US, North Europe, South Central US, Southeast Asia, UK South, West Europe, West US และ West US 2

### <a name="what-content-pack-data-types-can-you-embed"></a>คุณสามารถฝังข้อมูลชนิดใดชุดเนื้อหา

คุณ*ไม่สามารถ*ฝัง**แดชบอร์ด**และ**ไทล์**ซึ่งสร้างขึ้นจากชุดข้อมูลชุดเนื้อหาได้ อย่างไรก็ตาม คุณ*สามารถ*ฝัง**รายงาน**ซึ่งสร้างขึ้นจากชุดข้อมูลชุดเนื้อหาได้

### <a name="what-is-the-difference-between-using-row-level-security-rls-vs-javascript-filters"></a>อะไรคือความแตกต่างระหว่างการใช้เปรียบเทียบกับการรักษาความปลอดภัยระดับแถว (RLS) ตัวกรอง JavaScript?

ซึ่งมักสับสนรอบ ๆ เมื่อใช้ RLS เมื่อเทียบกับตัวกรอง JavaScript เนื่องจากวิธีหนึ่งคือเกี่ยวกับการควบคุมสิ่งที่ ผู้ใช้ที่ระบุสามารถเห็น และอื่น ๆ เกี่ยวกับมุมมองของผู้ใช้ที่ปรับให้เหมาะสม

สำหรับ RLS นักพัฒนา ISV ควบคุมกรองให้เป็นส่วนหนึ่งของการสร้างแบบจำลองข้อมูล และสร้างโทเค็นฝังตัว ดังนั้นผู้ใช้งานปลายทางจึงจะได้เห็นข้อมูลเฉพาะสิ่งที่ ISV อนุญาตให้เห็นเท่านั้น ในกรณีนี้ ผู้ใช้สามารถเลือกดูข้อมูลที่อยู่ภายใต้สิ่งที่ถูกกรองมาแล้วเท่านั้น แต่จะไม่ได้รับอนุญาตหรือไม่สามารถดูข้อมูลที่อยู่นอกเหนือการกำหนดค่าโดย RLS ได้

สำหรับไคลเอ็นต์กรอง (JavaScript), ISV อาจตัดสินใจว่า ผู้ใช้เห็นในมุมมองเริ่มต้น แต่พวกเขาไม่สามารถควบคุมการเปลี่ยนแปลงที่ผู้ใช้ปลายทางอาจนำไปใช้กับมุมมองเอง เนื่องจากผู้ใช้รหัสไคลเอ็นต์ Javascript สามารถทริกเกอร์ข้อมูลกรอง backend จะไม่ถูกพิจารณาความปลอดภัย

อ้างอิงข้อมูลเพิ่มเติมเกี่ยวกับ[RLS กับตัวกรอง JavaScript](embedded-row-level-security.md#using-rls-vs-javascript-filters)

### <a name="how-do-i-manage-permissions-for-service-principals-with-power-bi"></a>ฉันสามารถจัดการสิทธิ์สำหรับบริการหลักด้วย Power BI ได้อย่างไร

เมื่อคุณเปิดใช้งาน[บริการหลัก](embed-service-principal.md)ไปใช้กับ Power BI สิทธิ์ AD ของแอปพลิเคชันไม่มีผลบังคับใช้อีกต่อไป มีจัดการสิทธิ์ของแอปพลิเคชันแล้วผ่านทางพอร์ทัลผู้ดูแลระบบ Power BI

บริการหลักได้รับสิทธิ์สำหรับการตั้งค่าผู้เช่า Power BI ทั้งหมดจากกลุ่มความปลอดภัยของพวกเขา เมื่อต้องการจำกัดสิทธิ์ สร้างกลุ่มความปลอดภัยเฉพาะสำหรับบริการหลัก และเพิ่มไปยัง**เว้นกลุ่มความปลอดภัยเฉพาะ**รายการสำหรับการตั้งค่า Power BI ที่เกี่ยวข้อง เปิดใช้งาน

สถานการณ์นี้มีความสำคัญเมื่อคุณเพิ่มบริการหลักเป็น**ผู้ดูแลระบบ**ในพื้นที่ทำงานใหม่ที่คุณสร้างขึ้น คุณสามารถจัดการงานนี้ผ่าน[API](https://docs.microsoft.com/rest/api/power-bi/groups/addgroupuser)หรือด้วยบริการของ Power BI ได้

### <a name="when-to-use-an-application-id-vs-a-service-principal-object-id"></a>เมื่อไหร่ที่ต้องใช้ ID แอปพลิเคชันเทียบกับ ID ออบเจ็กต์ของบริการหลัก

**[ID แอปพลิเคชัน](embed-sample-for-customers.md#application-id)** ถูกใช้เพื่อสร้างโทเค็นการเข้าถึงเมื่อส่งผ่าน ID แอปพลิเคชันสำหรับการรับรองความถูกต้อง

เมื่อต้องการอ้างอิงบริการหลักสำหรับการดำเนินการ หรือทำการเปลี่ยนแปลงที่คุณใช **[ID ออบเจ็กต์ของบริการหลัก](embed-service-principal.md#how-to-get-the-service-principal-object-id)** — เช่น การใช้บริการหลักเป็นผู้ดูแลระบบในพื้นที่ทำงาน

### <a name="can-you-manage-an-on-premises-data-gateway-with-service-principal"></a>คุณสามารถจัดการเกตเวย์ข้อมูลภายในองค์กรด้วยบริการหลักได้หรือไม่

คุณไม่สามารถจัดการเกตเวย์ข้อมูลภายในองค์กร (เกตเวย์ข้อมูล) โดยใช้[บริการหลัก](embed-service-principal.md)เช่น คุณสามารถทำได้ด้วยบัญชีหลัก

ด้วยบัญชีหลัก คุณสามารถติดตั้งเกตเวย์ข้อมูล เพิ่มผู้ใช้ไปยังเกตเวย์ เชื่อมต่อกับแหล่งข้อมูล และทำงานดูแลระบบอื่น ๆ

ด้วยบริการหลัก คุณสามารถกำหนดค่า[การรักษาความปลอดภัยระดับแถว (RLS)](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal-preview) โดยใช้แหล่งข้อมูลการเชื่อมต่อแบบสดภายในองค์กรของ SQL Server Analysis Services (SSAS) ด้วยวิธีนี้ คุณสามารถจัดการผู้ใช้และการเข้าถึงข้อมูลของพวกเขาใน SSAS เมื่อรวมเข้ากับ**Power BI Embedded** โดยใช้บริการ

### <a name="can-you-sign-into-the-power-bi-service-with-service-principal"></a>คุณสามารถลงชื่อเข้าบริการ Power BI ด้วยบริการหลักได้หรือไม่

ไม่ คุณไม่สามารถลงชื่อเข้าใช้ Power BI ด้วยบริการหลัก

นอกจากนี้ คุณยังไม่สามารถใช้เนื้อหาในฐานะที่เป็นผู้ใช้ในแอปพลิเคชันภายนอก (SaaS แบบฝังตัว) เฉพาะเมื่อคุณสร้างโทเค็นแบบฝังตัว

### <a name="what-are-the-best-practices-to-improve-performance"></a>อะไรคือแนวทางปฏิบัติที่ดีที่สุดเพื่อปรับปรุงประสิทธิภาพการทำงาน?

[ประสิทธิภาพการทำงานของ Power BI Embedded](embedded-performance-best-practices.md)

## <a name="licensing"></a>สิทธิ์การใช้งาน

### <a name="how-do-i-purchase-power-bi-embedded"></a>ฉันซื้อ Power BI Embedded ได้อย่างไร

Power BI Embedded มีให้ผ่านทาง Azure

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-power-bi-embedded-in-azure-benefits"></a>เกิดอะไรขึ้นถ้าฉันซื้อ Power BI Premium เรียบร้อยแล้ว และตอนนี้ ฉันต้องบาง Power BI Embedded ใน Azure ประโยชน์

ลูกค้ายังคงต้องชำระเงินสำหรับการซื้อ Power BI Premium ใด ๆ ที่มีอยู่จนถึงจุดสิ้นสุดของคำข้อตกลงปัจจุบันของพวกเขาแล้ว ตอน อาจสลับของพวกเขาซื้อ Power BI Premium เท่าที่จำเป็น

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>ฉันยังต้องซื้อ Power BI Premium เพื่อเข้าถึง Power BI Embedded หรือไม่?

ไม่ Power BI Embedded รวมความจุ Azure ที่คุณต้องปรับใช้ และแจกจ่ายโซลูชันของคุณไปยังลูกค้า

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>อะไรคือข้อผูกมัดการซื้อสำหรับ Power BI Embedded?

ลูกค้าอาจเปลี่ยนแปลงการใช้งานของพวกเขาเป็นรายชั่วโมง ไม่มีข้อผูกมัดรายเดือน หรือรายปีสำหรับบริการ Power BI Embedded ได้

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>ปริมาณการใช้ Power BI Embedded แสดงขึ้นมาบนใบเรียกเก็บเงินของฉันได้อย่างไร?

Power BI Embedded เรียกเก็บเงินตามอัตรารายชั่วโมง ขึ้นกับชนิดของโหนดที่ปรับใช้ คุณถูกเรียกเก็บเงินตราบใดที่ทรัพยากรของคุณทำงานอยู่ แม้ว่ามีการใช้งานไม่ คุณจำเป็นต้องหยุดทรัพยากรของคุณเมื่อต้องหยุดการเรียกเก็บเงิน

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>ใครต้องมีสิทธิ์การใช้งาน Power BI Pro สำหรับ Power BI Embedded และทำไม?

คุณต้องการให้สิทธิ์การใช้งาน Power BI Pro หรือ[บริการหลัก](embed-service-principal.md)วิธีใช้ REST Api การเพิ่มรายงานไปยังพื้นที่ทำงาน Power BI นักวิเคราะห์จำเป็นต้องมีสิทธิ์การใช้งาน Power BI Pro หรือบริการหลัก การจัดการผู้เช่า Power BI และกำลังการผลิต ผู้ดูแลระบบจำเป็นต้องมีสิทธิ์การใช้งาน Power BI Pro

เนื่องจาก Power BI Embedded อนุญาตให้ใช้พอร์ทัล Power BI สำหรับการจัดการ และตรวจสอบเนื้อหาแบบฝังตัว สิทธิ์การใช้งาน Power BI Pro จำเป็นต้องรับรองความถูกต้องแอปภายใน PowerBI.com เพื่อเข้าถึงรายงานในเก็บข้อมูลถูก

อย่างไรก็ตาม สำหรับ[สร้าง/แก้ไขรายงานแบบฝังตัว](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Create-Report-in-Embed-View)ภายในของแอปพลิเคชันของคุณ ผู้ใช้ปลายทางไม่จำเป็นต้องมีใบอนุญาต Pro เนื่องจากผู้ใช้ไม่ต้องเป็นผู้ใช้ Power BI

### <a name="can-i-get-started-for-free"></a>ฉันสามารถเริ่มต้นใช้งานฟรีได้หรือไม่?

ได้ คุณสามารถใช้[เครดิต Azure](https://azure.microsoft.com/free/) ของคุณสำหรับ Power BI Embedded ได้

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>ฉันสามารถทดลองใช้ Power BI Embedded ใน Azure ได้หรือไม่?

เนื่องจาก Power BI Embedded เป็นส่วนหนึ่งของ Azure จำเป็นต้องใช้บริการด้วยการ[เครดิตจำนวน 200 ดอลลาร์ สหรัฐฯ ที่ได้รับเมื่อลงทะเบียนสำหรับ Azure](https://azure.microsoft.com/free/)

### <a name="is-power-bi-embedded-available-for-national-clouds-us-government-germany-china"></a>Power BI Embedded มีสำหรับบริการคลาวด์แห่งชาติ (รัฐบาลสหรัฐ, เยอรมนี, จีน) หรือไม่?

Power BI Embedded จะพร้อมใช้งานสำหรับ[ระบบคลาวด์ของชาติ](embed-sample-for-customers-national-clouds.md)

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Power BI Embedded มีให้สำหรับองค์กรไม่แสวงหากำไร และสถานศึกษาหรือไม่?

ไม่ Azure พิเศษราคาสำหรับเอนทิตีที่ไม่แสวงหากำไร และสถานศึกษาได้

## <a name="power-bi-workspace-collection"></a>คอลเลกชันพื้นที่ทำงาน Power BI

### <a name="what-is-power-bi-workspace-collection"></a>คอลเลกชันพื้นที่ทำงาน Power BI คืออะไร?

**Power BI Workspace Collection** (**Power BI Embedded**รุ่น 1) เป็นโซลูชันที่ยึดตามการ**Power BI Workspace Collection**ทรัพยากร Azure โซลูชันนี้ช่วยให้คุณสามารถสร้างแอปพลิเคชัน **Power BI Embedded** สำหรับลูกค้าของคุณโดยใช้เนื้อหา Power BI ภายใต้ โซลูชัน**Power BI Workspace Collection** API เฉพาะและคอลเลกชันคีย์พื้นที่ทำงานเพื่อตรวจสอบสิทธิ์แอ็พพลิเคชันกับ Power BI

### <a name="can-i-migrate-from-power-bi-workspace-collection-to-power-bi-embedded"></a>ฉันสามารถย้ายจากคอลเลกชันพื้นที่ทำงาน Power BI ไปยัง Power BI Embedded ได้หรือไม่?

1. คุณสามารถใช้เครื่องมือการย้ายเพื่อโคลนเนื้อหา**คอลเลกชันพื้นที่ทำงานของ Power BI** ไปยัง Power BI - https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded#content-migration ได้

2. เริ่มต้นด้วยแอปพลิเคชัน POC **Power BI Embedded** ที่ใช้เนื้อหา Power BI

3. เมื่อคุณพร้อมสำหรับการใช้งานจริง ซื้อความจุเฉพาะของ **Power BI Embedded** และกำหนดเนื้อหา Power BI (พื้นที่ทำงาน) ของคุณลงในความจุนั้น

    > [!Note]
    > คุณยังสามารถใช้**คอลเลกชันพื้นที่ทำงานของ Power BI** ต่อ ขณะที่สร้างโซลูชัน **Power BI Embedded** ไปพร้อม ๆ กันได้ เมื่อคุณพร้อม คุณสามารถย้ายลูกค้าของคุณไปยังโซลูชัน **Power BI Embedded** ใหม่ และถอนโซลูชัน**คอลเลกชันพื้นที่ทำงานของ Power BI** ได้

สำหรับข้อมูลเพิ่มเติม โปรดอ้างอิง[วิธีการย้ายเนื้อหาคอลเลกชันพื้นที่ทำงานของ Power BI ไปยัง Power BI Embedded](https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded)

### <a name="is-power-bi-workspace-collection-on-a-deprecation-path"></a>Power BI Workspace Collection อยู่บนเส้นทางไม่สนับสนุนหรือไม่

ใช่ แต่ลูกค้าที่กำลังใช้**Power BI Workspace Collection**โซลูชันสามารถใช้งานต่อจนกว่าจะไม่สนับสนุนได้ ลูกค้ายังสามารถสร้างคอลเลกชันพื้นที่ทำงานใหม่ และสร้างแอปพลิเคชัน **Power BI Embedded** ที่ยังใช้โซลูชัน**คอลเลกชันพื้นที่ทำงานของ Power BI** ได้

อย่างไรก็ตาม ซึ่งยังหมายความ ว่า ไม่ได้เพิ่มคุณลักษณะใหม่ใด ๆ**Power BI Workspace Collection**โซลูชัน เราขอแนะนำให้ลูกค้าเมื่อต้องการวางแผนการย้ายไปยัง**Power BI Embedded**โซลูชัน

### <a name="when-is-power-bi-workspace-collection-support-discontinued"></a>เมื่อไรที่คอลเลกชันพื้นที่ทำงาน Power BI จะยกเลิกการสนับสนุน?

ลูกค้าที่กำลังใช้โซลูชัน**คอลเลกชันพื้นที่ทำงาน Power BI** อยู่ สามารถใช้งานต่อจนถึงปลายเดือนมิถุนายน 2018 หรือจนถึงจุดสิ้นสุดของข้อตกลงการสนับสนุนของพวกเขา

### <a name="in-what-regions-can-i-create-a-pbi-workspace-collection"></a>ในภูมิภาคใดบ้างฉันสามารถสร้างคอลเลกชันพื้นที่ทำงาน PBI ได้อย่างไร

ภูมิภาคที่มี ได้แก่ Australia Southeast, Brazil South, Canada Central, East US 2, Japan East, North Central US, North Europe, South Central US, Southeast Asia, UK South, West Europe, West India และ West US

### <a name="why-should-i-migrate-from-pbi-workspace-collection-to-power-bi-embedded"></a>ทำไมฉันถึงต้องย้ายจากคอลเลกชันพื้นที่ทำงาน PBI ไปยัง Power BI Embedded?

มีบางใหม่**Power BI Embedded**โซลูชันคุณลักษณะและความสามารถที่คุณไม่สามารถทำได้ด้วย**Power BI Workspace Collection**

ตัวอย่างของคุณลักษณะ ได้แก่:
* แหล่งข้อมูล PBI ทั้งหมดที่ได้รับการสนับสนุน สองเท่านั้น**Power BI Workspace Collection**ได้รับการสนับสนุนแหล่งข้อมูล 
* คุณลักษณะใหม่ ๆ เช่น Q&A การรีเฟรชบุ๊กมาร์ก การฝังหน้าแดชบอร์ดและเมนูแบบกำหนดเอง และเมนูที่กำหนดเองจะได้รับการสนับสนุนเฉพาะในโซลูชัน **Power BI Embedded**
* รูปแบบการเรียกเก็บเงินตามความจุ

## <a name="embedding-setup-tool"></a>เครื่องมือตั้งค่าการฝังตัว

### <a name="what-is-the-embedding-setup-tool"></a>อะไรคือเครื่องมือตั้งค่าการฝังตัว

[เครื่องมือตั้งค่าการฝังตัว](https://aka.ms/embedsetup) ช่วยให้คุณสามารถเริ่มต้นใช้งานได้อย่างรวดเร็ว และดาวน์โหลดแอปพลิเคชันตัวอย่างเพื่อเริ่มต้นการฝังตัวด้วย Power BI

### <a name="which-solution-should-i-choose"></a>ฉันควรจะเลือกโซลูชันใด?

* [การฝังตัวสำหรับลูกค้าของคุณ](embedding.md#embedding-for-your-customers) จะมอบความสามารถในการฝังแดชบอร์ดและรายงานสำหรับผู้ใช้ที่ไม่มีบัญชี Power BI เรียกใช้โซลูชัน[การฝังตัวสำหรับลูกค้าของคุณ](https://aka.ms/embedsetup/AppOwnsData)
* [การฝังตัวสำหรับองค์กรของคุณ](embedding.md#embedding-for-your-organization) ให้คุณสามารถขยายบริการของ Power BI เรียกใช้โซลูชัน[การฝังตัวสำหรับองค์กรของคุณ](https://aka.ms/embedsetup/UserOwnsData)

### <a name="ive-downloaded-the-sample-app-which-solution-do-i-choose"></a>ฉันได้ดาวน์โหลดแอปตัวอย่างแล้ว ฉันควรจะเลือกโซลูชันใด?

ถ้าคุณกำลังทำงานกับประสบการณ์**ฝังตัวสำหรับลูกค้าของคุณ** บันทึกและคลายการบีบอัดไฟล์ *PowerBI-Developer-Samples.zip* จากนั้น เปิดโฟลเดอร์ *PowerBI-Developer-Samples-master\App Owns Data* และเรียกใช้ไฟล์ *PowerBIEmbedded_AppOwnsData.sln*

ถ้าคุณกำลังทำงานกับประสบการณ์**ฝังตัวสำหรับองค์กรของคุณ** บันทึกและคลายการบีบอัดไฟล์ *PowerBI-Developer-Samples.zip* จากนั้น เปิดโฟลเดอร์ *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app* และเรียกใช้ไฟล์ *pbi-saas-embed-report.sln*

### <a name="how-can-i-edit-my-registered-application"></a>ฉันสามารถแก้ไขแอปพลิเคชันของฉันที่ลงทะเบียนแล้วได้อย่างไร?

หากต้องการเรียนรู้วิธีการแก้ไขแอปพลิเคชัน  Azure AD ที่ลงทะเบียนไว้ โปรดดู [เริ่มต้นใช้งานด่วน: อัปเดตแอปพลิเคชันใน  Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-update-azure-ad-app)

### <a name="how-can-i-edit-my-power-bi-user-profile-or-data"></a>ฉันสามารถแก้ไขโปรไฟล์หรือข้อมูลผู้ใช้ Power BI ของฉันได้อย่างไร?

คุณสามารถเรียนรู้วิธีการแก้ไขข้อมูล Power BI ของคุณได้[ที่นี่](https://docs.microsoft.com/power-bi/service-basic-concepts)

สำหรับข้อมูลเพิ่มเติม ดู[การแก้ไขปัญหาแอปพลิเคชันแบบฝังตัวของคุณ](embedded-troubleshoot.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)

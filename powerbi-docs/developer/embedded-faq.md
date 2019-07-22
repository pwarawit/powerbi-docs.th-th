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
ms.date: 05/27/2019
ms.openlocfilehash: af3c22197e4d6783787bd72c9cf010bf6db64bc1
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/16/2019
ms.locfileid: "68270977"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>คำถามที่ถามบ่อยเกี่ยวกับ Power BI Embedded

* ถ้าคุณมีคำถามอื่น [ลองถามชุมชน Power BI](http://community.powerbi.com/)
* ยังคงมีปัญหาใช่หรือไม่? โปรดเยี่ยมชม[หน้าการสนับสนุน Power BI](https://powerbi.microsoft.com/support/)

## <a name="general"></a>ทั่วไป

### <a name="what-is-power-bi-embedded"></a>Power BI Embedded คืออะไร?

[Microsoft Power BI Embedded (PBIE)](azure-pbie-what-is-power-bi-embedded.md)อนุญาตให้นักพัฒนาแอปพลิเคชันฝังรายงานที่โต้ตอบได้อย่างน่าทึ่งลงในแอปพลิเคชัน โดยไม่ต้องสร้างภาพและการควบคุมของตัวเองใหม่ทั้งหมด

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>ใครคือกลุ่มเป้าหมายสำหรับ Power BI Embedded?

นักพัฒนาและบริษัทซอฟต์แวร์ หรือที่เรียกกันว่า ผู้จัดจำหน่ายซอฟต์แวร์อิสระ (ISV) แอปพลิเคชันการเข้ารหัส

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Power BI Embedded แตกต่างจากบริการของ Power BI อย่างไร?

Power BI คือโซลูชันการให้บริการซอฟต์แวร์การวิเคราะห์ ที่ช่วยให้องค์กรของพวกเขามีภาพเดียวกันสำหรับข้อมูลทางธุรกิจที่สำคัญที่สุดของพวกเขา

Microsoft ที่พัฒนา Power BI Embedded สำหรับ ISV อาจต้องการฝังภาพลงในแอปพลิเคชันของตนเพื่อช่วยให้ลูกค้าสามารถทำการตัดสินใจเชิงวิเคราะห์ได้ ส่วนนี้จะช่วยให้ ISV ไม่ต้องสร้างโซลูชันการวิเคราะห์ของตนเอง [การวิเคราะห์ที่ฝังตัว](embedding.md) ช่วยให้ผู้ใช้ทางธุรกิจสามารถเข้าถึงข้อมูลธุรกิจ และดำเนินการสอบถามเพื่อสร้างข้อมูลเชิงลึกภายในแอปพลิเคชัน


### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>อะไรคือความแตกต่างระหว่าง Power BI Premium และ Power BI Embedded?

Power BI Premium มีความจุที่ปรับให้เหมาะกับองค์กร ที่ต้องการโซลูชัน BI ที่สมบูรณ์ ที่ให้มุมมองเดียวกันแก่ หน่วยงาน คู่ค้า ลูกค้า และผู้จัดหาสินค้าขององค์กร Power BI Premium ช่วยให้องค์กรของคุณตัดสินใจ Power BI Premium เป็นผลิตภัณฑ์ SaaS ที่ให้ผู้ใช้สามารถใช้เนื้อหาผ่านทางแอปสำหรับอุปกรณ์เคลื่อนที่ แอปที่พัฒนาขึ้นเองภายใน หรือที่พอร์ทัล Power BI

Power BI Embedded มีไว้สำหรับ ISV ที่ต้องการฝังภาพลงในแอปพลิเคชันของตน Power BI Embedded ช่วยการตัดสินใจของลูกค้าคุณ เนื่องจาก Power BI Embedded ออกแบบมาสำหรับนักพัฒนาแอปพลิเคชัน ลูกค้าของแอปพลิเคชันนั้นสามารถใช้เนื้อหาที่เก็บไว้ในความจุของ Power BI Embedded รวมไปถึงทุกคนภายใน หรือภายนอกองค์กร คุณไม่สามารถแชร์เนื้อหาความจุใน Power BI Embedded ผ่านการ การเผยแพร่ไปยังเว็บแบบคลิกเดียว หรือการเผยแพร่ไปยัง SharePoint แบบคลิกเดียว

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Microsoft จะแนะนำลูกค้าอย่างไร ว่าเมื่อไหร่ที่ลูกค้าควรซื้อ Power BI Embedded Premium เทียบกับ Power BI Embedded

Microsoft แนะนำให้องค์กรซื้อ Power BI Premium ซึ่งเป็นโซลูชัน BI ระบบคลาวด์แบบบริการตนเองในระดับองค์กร เราขอแนะนำให้ ISV ซื้อ Power BI Embedded สำหรับคอมโพเนนต์การวิเคราะห์ที่ฝังตัวระบบคลาวด์วิเคราะห์ อย่างไรก็ตาม ลูกค้าไม่มีข้อจำกัดในการซื้อผลิตภัณฑ์ใด ๆ

อาจมีบางกรณีที่ ISV (มักมีขนาดใหญ่) ต้องการใช้ P SKU เพื่อรับประโยชน์เพิ่มเติมของบริการของ Power BI ที่รวมให้อยู่แล้วภายในองค์กรของพวกเขา นอกเหนือจากการฝังแอป บางองค์กรอาจตัดสินใจที่จะใช้ A SKU ใน Azure หากพวกเขาสนใจเฉพาะการสร้างแอปพลิเคชันทางธุรกิจ และการฝังการวิเคราะห์ลงไป และไม่สนใจที่จะใช้บริการ Power BI ที่รวมให้อยู่แล้ว

### <a name="how-many-embed-tokens-can-i-create"></a>ฉันสามารถสร้างโทเค็นฝังตัวได้มากแค่ไหน?

โทเค็นแบบฝังตัวที่มีใบอนุญาต PRO มีไว้สำหรับทดสอบการพัฒนา ดังนั้น บัญชีหลัก Power BI หรือ[โครงร่างสำคัญของบริการ](embed-service-principal.md) จึงสามารถสร้างจำนวนโทเค็นฝังตัวได้อย่างจำกัดเท่านั้น [ซื้อความจุ](#technical)สำหรับการฝังตัวในสภาพแวดล้อมการทำงานจริง ไม่มีข้อจำกัดเกี่ยวกับจำนวนโทเค็นฝังตัวที่คุณสามารถสร้างขึ้นเมื่อซื้อความจุแล้ว ไปยัง[คุณลักษณะที่มี](https://docs.microsoft.com/rest/api/power-bi/availablefeatures) เพื่อตรวจสอบค่าการใช้งาน ที่สามารถบอกได้ว่าปัจจุบันมีการใช้งานฝังตัวแล้วกี่เปอร์เซ็นต์

## <a name="technical"></a>ทางเทคนิค

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>อะไรคือความแตกต่างระหว่าง A SKU ใน Azure และ EM SKU ใน Office 365

PowerBI.com เป็นโซลูชันซอฟต์แวร์ที่เป็นบริการ (Software as a Service, SaaS) ระดับองค์กรที่มีความสามารถมากมาย เช่น การทำงานร่วมกันทางสังคม การสมัครใช้งานอีเมล และคุณสมบัติอื่น ๆ PowerBI.com ช่วย ISV จัดการเนื้อหาโซลูชันการวิเคราะห์ที่ฝังตัว และตั้งค่าในระดับผู้เช่า

Power BI Embedded คือ ชุดแพลตฟอร์มที่เป็นบริการ (Platform as a Service, PaaS) ของ API ที่นักพัฒนาสามารถสร้างโซลูชันการวิเคราะห์ที่ฝังตัวได้

ต่อไปนี้เป็นรายการความต่างของคุณลักษณะบางส่วน

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
|ความแตกต่าง |มีความยือหยุ่มเต็มที่ - สามารถสเกลขึ้น/ลง, หยุด/ทำงานต่อ ทรัพยากรในพอร์ทัล Azure หรือผ่าน API  |คุณสามารถใช้เพื่อฝังเนื้อหาใน SharePoint Online และ Microsoft Teams ได้ (ไม่รวมแอปสำหรับอุปกรณ์เคลื่อนที่) |รวมการฝังในแอปพลิเคชัน และการใช้บริการของ Power BI ในความจุเดียวกัน |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>ข้อกำหนดเบื้องต้นเพื่อสร้างความจุ PBIE ใน Azure คืออะไร?

* ลงชื่อเข้าใช้ไดเรกทอรีขององค์กรของคุณ (ไม่รองรับบัญชี Microsoft)
* คุณจำเป็นต้องมีผู้เช่า Power BI อย่างน้อยหนึ่งคนในไดเรกทอรีของคุณลงทะเบียนสำหรับ Power BI 
* คุณต้องมีการสมัครใช้งาน Azure ในไดเรกทอรีขององค์กรของคุณ

### <a name="how-can-i-monitor-power-bi-embedded-capacity-consumption"></a>ฉันสามารถตรวจสอบปริมาณการใช้ความจุของ Power BI Embedded ได้อย่างไร

* ใช้[พอร์ทัลผู้ดูแลระบบ Power BI](../service-admin-portal.md#power-bi-embedded)

* ดาวน์โหลด[แอปเมตริก](https://docs.microsoft.com/power-bi/service-admin-premium-monitor-capacity)ใน Power BI

* ใช้[การบันทึกการวินิจฉัย Azure](azure-pbie-diag-logs.md)

### <a name="can-my-capacity-scale-automatically-to-adjust-to-my-app-consumption"></a>ความจุของฉันสามารถปรับตามปริมาณการใช้แอปของฉันได้ตามอัตโนมัติหรือไม่

ขณะนี้ยังไม่มีการปรับขนาดโดยอัตโนมัติ แต่ API ทั้งหมดสามารถปรับขนาดได้ทุกเวลา

### <a name="why-creatingscalingresuming-a-capacity-results-in-putting-the-capacity-into-a-suspended-state"></a>ทำไม การสร้าง/ปรับขนาด/กลับมาใช้ความจุทำให้ความจุอยู่ในสถานะถูกระงับชั่วคราว?

การจัดความจุ (ปรับขนาด/กลับมาใช้/สร้าง) อาจล้มเหลว คุณสามารถใช้ API รับรายละเอียดเพื่อตรวจสอบสถานะการจัดความจุได้: [ความจุ - รับรายละเอียด](https://docs.microsoft.com/rest/api/power-bi-embedded/capacities/getdetails)

### <a name="can-i-only-create-power-bi-embedded-capacities-in-a-specific-region"></a>ฉันสามารถสร้างความจุแบบฝังตัวของ Power BI ในพื้นที่เฉพาะได้หรือไม่

ด้วยคุณลักษณะ[หลายภูมิศาสตร์ (ตัวอย่าง)](embedded-multi-geo.md) คุณสามารถซื้อ[ความจุแบบฝังตัวของ Power BI](azure-pbie-create-capacity.md) ในภูมิภาคอื่นนอกจากตำแหน่งที่ตั้งหลักของผู้เช่า Power BI ของคุณ

### <a name="why-cant-i-see-a-workspace-although-i-have-permissions"></a>ทำไมฉันจึงไม่เห็นพื้นที่ทำงานแม้ว่าฉันมีสิทธิ์ก็ตาม

เมื่อผู้ใช้ได้รับสิทธิ์ในพื้นที่ทำงาน แอป หรือวัตถุ สิทธิ์นั้นอาจยังไม่พร้อมใช้งานทันทีผ่านการเรียกใช้ API
ผลลัพธ์อาจเป็นวัตถุหายไปในการตอบสนอง API 'ได้รับ' หรือข้อผิดพลาดเมื่อพยายามใช้วัตถุ
ผู้ใช้สามารถแก้ไขปัญหานี้ได้โดยการเรียกใช้ [refreshUserPermissions API](https://docs.microsoft.com/rest/api/power-bi/users/refreshuserpermissions) ซึ่งจะอัปเดตสิทธิ์ของผู้ใช้


### <a name="how-can-i-find-my-pbi-tenant-region"></a>ฉันสามารถค้นหาภูมิภาคผู้เช่า PBI ของฉันได้อย่างไร

คุณสามารถใช้พอร์ทัล PBI เพื่อค้นหาภูมิภาคผู้เช่า PBI ของคุณได้

[https://app.powerbi.com/](https://app.powerbi.com/ ) > ? เกี่ยวกับ Power BI

![เกี่ยวกับ ภูมิภาคผู้เช่า](media/embedded-faq/about-01.png)
![Power BI](media/embedded-faq/tenant-location-01.png)

### <a name="what-does-the-cloud-solution-provider-csp-channel-support"></a>สิ่งที่ได้รับการสนับสนุนช่อง Cloud Solution Provide (CSP) คืออะไร

* คุณสามารถสร้าง PBIE ให้ผู้เช่าของคุณด้วยการสมัครใช้งานชนิด CSP
* บัญชีคู่ค้าสามารถลงชื่อเข้าใช้ในนามผู้เช่าของลูกค้า และซื้อ PBIE สำหรับผู้เช่าของลูกค้า กำหนดให้ผู้ใช้ที่เป็นผู้เช่าของลูกค้าเป็นผู้ดูแลความจุ Power BI

### <a name="why-do-i-get-an-unsupported-account-message"></a>เหตุใดฉันจึงได้รับข้อความว่า เป็นบัญชีที่ไม่สนับสนุน

Power BI ให้คุณต้องลงทะเบียนด้วยบัญชีผู้ใช้ขององค์กร ไม่รองรับการลงทะเบียน Power BI โดยใช้บัญชี Microsoft

### <a name="can-i-use-apis-to-create-and-manage-azure-capacities"></a>ฉันสามารถใช้ API สร้างและจัดการความจุ Azure ได้หรือไม่

มีทั้ง Powershell cmdlets และ Azure Resource Manager REST APIs ที่คุณสามารถใช้สร้างและจัดการทรัพยากร PBIE

* [REST API](https://docs.microsoft.com/rest/api/power-bi-embedded/) 
* [cmdlets ของ Powershell](https://docs.microsoft.com/powershell/module/azurerm.powerbiembedded/)

### <a name="what-is-the-pbi-embedded-dedicated-capacity-role-in-a-pbi-embedded-solution"></a>บทบาทความจุเฉพาะของ PBI ฝังตัว ในโซลูชัน PBI ฝังตัวคืออะไร?

หากต้องการ [เลื่อนระดับโซลูชันของคุณเป็นการผลิต](embed-sample-for-customers.md#move-to-production) คุณต้องกำหนดเนื้อหาของ Power BI (พื้นที่ทำงานแอป) ที่แอปพลิเคชันของคุณใช้กับความจุ Power BI Embedded (A SKU)

### <a name="in-what-azure-regions-is-pbi-embedded-available"></a>ภูมิภาค Azure ใดที่การฝัง PBI สามารถใช้งานได้

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

### <a name="what-is-power-bi-embeddeds-authentication-model"></a>รูปแบบการรับรองความถูกต้องของ Power BI Embedded คืออะไร

Power BI Embedded ยังคงใช้ Azure AD สำหรับการรับรองความถูกต้องของผู้ใช้หลัก (ผู้ใช้ Power BI Pro ที่ได้รับการกำหนดสิทธิ์) หรือด้วย[บริการหลัก](embed-service-principal.md) และการรับรองความถูกต้องแอปพลิเคชันภายใน Power BI  

 ISV สามารถดำเนินการรับรองความถูกต้องและการอนุญาตแอปพลิเคชันของตนได้

คุณสามารถใช้ไดเรกทอรีที่มีอยู่ของคุณ ถ้าคุณมีผู้เช่า Azure AD อยู่แล้ว คุณยังสามารถสร้างผู้เช่า Azure AD ใหม่สำหรับความปลอดภัยของเนื้อหาแอปพลิเคชันแบบฝังตัวได้

เพื่อรับโทเค็น AAD คุณสามารถใช้ไลบรารี [Azure Active Directory Authentication ตัวใดตัวหนึ่ง](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) ไลบรารีเหล่านี้เป็นไลบรารีไคลเอ็นต์ ที่พร้อมใช้งานบนหลายแพลตฟอร์ม

### <a name="my-application-already-uses-aad-for-user-authentication-how-can-we-use-this-identity-when-authenticating-to-power-bi-in-a-user-owns-data-scenario"></a>แอปพลิเคชันของฉันใช้ AAD สำหรับการรับรองความถูกต้องผู้ใช้แล้ว เราสามารถใช้ข้อมูลประจำตัวนี้เมื่อรับรองความถูกต้องไปยัง Power BI ในสถานการณ์ "ผู้ใช้เป็นเจ้าของข้อมูล" ได้อย่างไร?

ถือเป็นโฟลว์ในนามของผู้ใช้ OAuth มาตรฐาน (<https://docs.microsoft.com/azure/active-directory/develop/web-api>) คุณจะต้องกำหนดค่าแอปพลิเคชันเพื่อร้องขอสิทธิ์ในบริการของ Power BI (ตามขอบเขตที่ต้องการ) เมื่อมีโทเค็นผู้ใช้ในแอปแล้ว คุณเพียงแค่ใช้โทเค็นการเข้าใช้ของผู้ใช้เรียกไปยัง API AcquireTokenAsync ADAL และระบุ URL ทรัพยากร Power BI เป็น ID ทรัพยากร:

```csharp
var context = new AD.AuthenticationContext(authorityUrl);
var userAssertion = new AD.UserAssertion(userAccessToken);
var clientAssertion = new AD.ClientAssertionCertificate(MyAppId, MyAppCertificate)
var authenticationResult = await context.AcquireTokenAsync(resourceId, clientAssertion, userAssertion);
```

### <a name="what-object-id-is-the-service-principal-object-id"></a>ID ออบเจ็กต์ใดที่เป็น ID ออบเจ็กต์ของโครงร่างสำคัญของบริการ

*ID ออบเจ็กต์*จากหน้าจอหลักของแอปที่ลงทะเบียนเป็น ID ออบเจ็กต์สำหรับแอป

ID ออบเจ็กต์ที่พบในส่วน *แอปพลิเคชันที่จัดการในไดเรกทอรีภายใน > คุณสมบัติ* คือ ID ็อบเจ็กต์หลักของโครงร่างสำคัญของบริการที่คุณต้องใช้ ID ออบเจ็กต์นี้ใช้เพื่ออ้างอิงโครงร่างสำคัญของบริการเพื่อดำเนินการ หรือทำการเปลี่ยนแปลง ID ออบเจ็กต์ของโครงร่างสำคัญของบริการ เช่น การใช้โครงร่างสำคัญของบริการในฐานะผู้ดูแลระบบไปยังพื้นที่ทำงาน

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Power BI Embedded แตกต่างจากบริการอื่น ๆ ของ Azure อย่างไร?

คุณต้องมีบัญชี Power BI ก่อนที่จะซื้อ Power BI Embedded ใน Azure ภูมิภาคที่ปรับใช้งาน Power BI Embedded ของคุณจะกำหนดบัญชี Power BI ของคุณ จัดการทรัพยากร Power BI Embedded ของคุณใน Azure เพื่อ:

* Scale up/down
* เพิ่มผู้ดูแลความจุ
* หยุดบริการ/ทำงานต่อ

ใช้ PowerBI.com เพื่อกำหนด/ยกเลิก การกำหนดพื้นที่ทำงานให้กับความจุ Power BI Embedded ของคุณ

### <a name="what-content-pack-data-types-can-you-embed"></a>คุณสามารถฝังข้อมูลชนิดใดของชุดเนื้อหา

คุณ*ไม่สามารถ*ฝัง**แดชบอร์ด**และ**ไทล์**ที่สร้างขึ้นจากชุดข้อมูลของชุดเนื้อหาได้ อย่างไรก็ตาม คุณ*สามารถ*ฝัง**รายงาน**ที่สร้างขึ้นจากชุดข้อมูลของชุดเนื้อหาได้

### <a name="what-is-the-difference-between-using-row-level-security-rls-vs-javascript-filters"></a>อะไรคือความแตกต่างระหว่างการใช้ความปลอดภัยระดับแถว (Row-level security, RLS) เปรียบเทียบกับ ตัวกรอง JavaScript?

มักจะมีความสับสนเกี่ยวกับเวลาที่จะใช้ RLS กับตัวกรอง JavaScript สาเหตุเพราะวิธีหนึ่งเน้นควบคุมการมองเห็นของผู้ใช้ที่ถูกระบุเฉพาะ และอีกอันหนึ่งเน้นเกี่ยวกับการปรับมุมมองของผู้ใช้ให้เหมาะสม

สำหรับ RLS นักพัฒนา ISV ควบคุมกรองให้เป็นส่วนหนึ่งของการสร้างแบบจำลองข้อมูล และสร้างโทเค็นฝังตัว ดังนั้นผู้ใช้งานปลายทางจึงจะได้เห็นข้อมูลเฉพาะสิ่งที่ ISV อนุญาตให้เห็นเท่านั้น ในกรณีนี้ ผู้ใช้สามารถเลือกดูข้อมูลที่อยู่ภายใต้สิ่งที่ถูกกรองมาแล้วเท่านั้น แต่จะไม่ได้รับอนุญาตหรือไม่สามารถดูข้อมูลที่อยู่นอกเหนือการกำหนดค่าโดย RLS ได้

สำหรับการกรองจากฝั่งลูกค้า (JavaScript) ISV อาจตัดสินใจว่า ผู้ใช้ปลายทางควรเห็นอะไรตั้งแต่เริ่มต้นการดูข้อมูล แต่ไม่สามารถควบคุมการเปลี่ยนแปลงที่ผู้ใช้ปลายทางอาจนำไปใช้กับมุมมองเอง เนื่องจากรหัสไคลเอ็นต์ Javascript สำหรับผู้ใช้สามารถทริกเกอร์การกรองข้อมูลที่ Backend ได้ กรณีนี้จะไม่พิจารณาว่ามีความปลอดภัย

อ้างอิงข้อมูลเพิ่มเติมเกี่ยวกับ[RLS กับตัวกรอง JavaScript](embedded-row-level-security.md#using-rls-vs-javascript-filters)

### <a name="how-do-i-manage-permissions-for-service-principals-with-power-bi"></a>ฉันสามารถจัดการสิทธิ์สำหรับบริการหลักด้วย Power BI ได้อย่างไร

เมื่อคุณเปิดใช้งาน[โครงร่างสำคัญของบริการ](embed-service-principal.md)ที่จะใช้กับ Power BI สิทธิ์ AD ของแอปพลิเคชันจะไม่มีผลบังคับใช้อีกต่อไป มีจัดการสิทธิ์ของแอปพลิเคชันแล้วผ่านทางพอร์ทัลผู้ดูแลระบบ Power BI

บริการหลักได้รับสิทธิ์สำหรับการตั้งค่าผู้เช่า Power BI ทั้งหมดจากกลุ่มความปลอดภัยของพวกเขา เมื่อต้องการจำกัดสิทธิ์ ให้สร้างกลุ่มความปลอดภัยเฉพาะสำหรับบริการหลัก และเพิ่มลงในรายการ **ยกเว้นกลุ่มความปลอดภัยเฉพาะ** สำหรับการตั้งค่า Power BI ที่เกี่ยวข้องที่เปิดใช้งาน

สถานการณ์นี้มีความสำคัญเมื่อคุณเพิ่มบริการหลักเป็น**ผู้ดูแลระบบ**ในพื้นที่ทำงานใหม่ที่คุณสร้างขึ้น คุณสามารถจัดการงานนี้ผ่าน[API](https://docs.microsoft.com/rest/api/power-bi/groups/addgroupuser)หรือด้วยบริการของ Power BI ได้

### <a name="when-to-use-an-application-id-vs-a-service-principal-object-id"></a>เมื่อไหร่ที่ต้องใช้ ID แอปพลิเคชันเทียบกับ ID ออบเจ็กต์ของบริการหลัก

**[ID แอปพลิเคชัน](embed-sample-for-customers.md#application-id)** ถูกใช้เพื่อสร้างโทเค็นการเข้าถึงเมื่อส่งผ่าน ID แอปพลิเคชันสำหรับการรับรองความถูกต้อง

เมื่อต้องการอ้างอิงบริการหลักสำหรับการดำเนินการ หรือทำการเปลี่ยนแปลงที่คุณใช **[ID ออบเจ็กต์ของบริการหลัก](embed-service-principal.md#how-to-get-the-service-principal-object-id)** — เช่น การใช้บริการหลักเป็นผู้ดูแลระบบในพื้นที่ทำงาน

### <a name="can-you-manage-an-on-premises-data-gateway-with-service-principal"></a>คุณสามารถจัดการเกตเวย์ข้อมูลภายในองค์กรด้วยบริการหลักได้หรือไม่

คุณไม่สามารถจัดการเกตเวย์ข้อมูลภายในองค์กร (เกตเวย์ข้อมูล) โดยใช้[บริการหลัก](embed-service-principal.md)เช่น คุณสามารถทำได้ด้วยบัญชีหลัก

ด้วยบัญชีหลัก คุณสามารถติดตั้งเกตเวย์ข้อมูล เพิ่มผู้ใช้ไปยังเกตเวย์ เชื่อมต่อกับแหล่งข้อมูล และทำงานดูแลระบบอื่น ๆ

ด้วยบริการหลัก คุณสามารถกำหนดค่า[การรักษาความปลอดภัยระดับแถว (RLS)](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal) โดยใช้แหล่งข้อมูลการเชื่อมต่อแบบสดภายในองค์กรของ SQL Server Analysis Services (SSAS) ด้วยวิธีนี้ คุณสามารถจัดการผู้ใช้และการเข้าถึงข้อมูลของพวกเขาใน SSAS เมื่อรวมเข้ากับ**Power BI Embedded** โดยใช้บริการ

### <a name="can-you-sign-into-the-power-bi-service-with-service-principal"></a>คุณสามารถลงชื่อเข้าบริการ Power BI ด้วยบริการหลักได้หรือไม่

ไม่ คุณไม่สามารถลงชื่อเข้าใช้ Power BI ด้วยบริการหลัก

นอกจากนี้ คุณยังไม่สามารถใช้เนื้อหาในฐานะที่เป็นผู้ใช้ในแอปพลิเคชันภายนอก (SaaS แบบฝังตัว) เฉพาะเมื่อคุณสร้างโทเค็นแบบฝังตัว

### <a name="what-are-the-best-practices-to-improve-performance"></a>อะไรคือแนวทางปฏิบัติที่ดีที่สุดเพื่อปรับปรุงประสิทธิภาพการทำงาน?

[ประสิทธิภาพการทำงานของ Power BI Embedded](embedded-performance-best-practices.md)

## <a name="licensing"></a>สิทธิ์การใช้งาน

### <a name="how-do-i-purchase-power-bi-embedded"></a>ฉันซื้อ Power BI Embedded ได้อย่างไร

Power BI Embedded มีให้ผ่านทาง Azure

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-power-bi-embedded-in-azure-benefits"></a>เกิดอะไรขึ้นถ้าฉันซื้อ Power BI Premium แล้ว และตอนนี้ฉันต้องการคุณสมบัติบางประการของ Power BI Embedded ใน Azure

ลูกค้าจะยังคงต้องชำระเงินสำหรับการซื้อ Power BI Premium ใด ๆ ที่มีอยู่ จนกว่าจะถึงจุดสิ้นสุตตามข้อตกลงปัจจุบัน จากนั้นก็สามารถเปลี่ยนการซื้อ Power BI Premium ตามความจำเป็นเมื่อถึงเวลานั้น

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>ฉันยังต้องซื้อ Power BI Premium เพื่อเข้าถึง Power BI Embedded หรือไม่?

ไม่ Power BI Embedded รวมความจุ Azure ที่คุณต้องปรับใช้ และแจกจ่ายโซลูชันของคุณไปยังลูกค้า

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>อะไรคือข้อผูกมัดการซื้อสำหรับ Power BI Embedded?

ลูกค้าอาจเปลี่ยนแปลงการใช้งานของพวกเขาเป็นรายชั่วโมง ไม่มีข้อผูกมัดรายเดือน หรือรายปี สำหรับบริการ Power BI Embedded

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>ปริมาณการใช้ Power BI Embedded แสดงขึ้นมาบนใบเรียกเก็บเงินของฉันได้อย่างไร?

Power BI Embedded เรียกเก็บเงินตามอัตรารายชั่วโมง ขึ้นกับชนิดของโหนดที่ปรับใช้ ตราบใดที่ทรัพยากรของคุณยังเปิดใช้งาน คุณจะถูกเรียกเก็บเงินแม้ว่าจะไม่มีการใช้งานก็ตาม คุณจะต้องหยุดทรัพยากรของคุณเพื่อหยุดการเรียกเก็บเงิน

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>ใครต้องมีสิทธิ์การใช้งาน Power BI Pro สำหรับ Power BI Embedded และทำไม?

คุณต้องมีสิทธิการใช้งาน Power BI Pro หรือ[โครงร่างสำคัญของบริการ](embed-service-principal.md)เพื่อใช้ REST API หากต้องการเพิ่มรายงานไปยังพื้นที่ทำงาน Power BI นักวิเคราะห์จะต้องมีสิทธิการใช้งาน Power BI Pro หรือโครงร่างสำคัญของบริการ หากต้องการจัดการผู้เช่า Power BI และความจุ ผู้ดูแลระบบจะต้องมีสิทธิการใช้งาน Power BI Pro

เนื่องจาก Power BI Embedded อนุญาตให้ใช้พอร์ทัล Power BI สำหรับการจัดการ และตรวจสอบเนื้อหาแบบฝังตัว สิทธิ์การใช้งาน Power BI Pro เป็นสิ่งจำเป็นเพื่อรับรองความถูกต้องของแอปภายใน PowerBI.com เพื่อเข้าถึงรายงานในเก็บข้อมูลที่ถูกต้อง

อย่างไรก็ตาม สำหรับ[สร้าง/แก้ไขรายงานแบบฝังตัว](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Create-Report-in-Embed-View)ภายในของแอปพลิเคชันของคุณ ผู้ใช้ปลายทางไม่จำเป็นต้องมีใบอนุญาต Pro เนื่องจากผู้ใช้ไม่ต้องเป็นผู้ใช้ Power BI

### <a name="can-i-get-started-for-free"></a>ฉันสามารถเริ่มต้นใช้งานฟรีได้หรือไม่?

ได้ คุณสามารถใช้[เครดิต Azure](https://azure.microsoft.com/free/) ของคุณสำหรับ Power BI Embedded ได้

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>ฉันสามารถทดลองใช้ Power BI Embedded ใน Azure ได้หรือไม่?

เนื่องจาก Power BI Embedded เป็นส่วนหนึ่งของ Azure คุณสามารถใช้บริการด้วย[เครดิตจำนวน 200 ดอลลาร์สหรัฐฯ ที่คุณได้รับตอนลงทะเบียนสำหรับ Azure](https://azure.microsoft.com/free/)

### <a name="is-power-bi-embedded-available-for-national-clouds-us-government-germany-china"></a>Power BI Embedded มีสำหรับบริการคลาวด์แห่งชาติ (รัฐบาลสหรัฐ, เยอรมนี, จีน) หรือไม่?

Power BI Embedded จะพร้อมใช้งานสำหรับ [บริการคลาวด์แห่งชาติ](embed-sample-for-customers-national-clouds.md)

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Power BI Embedded มีให้สำหรับองค์กรไม่แสวงหากำไร และสถานศึกษาหรือไม่?

ไม่มีการกำหนดราคา Azure พิเศษสำหรับสถานศึกษาที่ไม่แสวงหากำไร

## <a name="power-bi-workspace-collection"></a>คอลเลกชันพื้นที่ทำงาน Power BI

### <a name="what-is-power-bi-workspace-collection"></a>คอลเลกชันพื้นที่ทำงาน Power BI คืออะไร?

**คอลเลกชันพื้นที่ทำงาน Power BI** (**Power BI Embedded**รุ่น 1) เป็นโซลูชันที่มาจาก**คอลเลกชันพื้นที่ทำงานของ Power BI** ของทรัพยากร Azure โซลูชันนี้ช่วยให้คุณสามารถสร้างแอปพลิเคชัน **Power BI Embedded** สำหรับลูกค้าของคุณโดยใช้เนื้อหา Power BI ภายใต้ โซลูชัน**Power BI Workspace Collection** API เฉพาะและคอลเลกชันคีย์พื้นที่ทำงานเพื่อตรวจสอบสิทธิ์แอ็พพลิเคชันกับ Power BI

### <a name="can-i-migrate-from-power-bi-workspace-collection-to-power-bi-embedded"></a>ฉันสามารถย้ายจากคอลเลกชันพื้นที่ทำงาน Power BI ไปยัง Power BI Embedded ได้หรือไม่?

1. คุณสามารถใช้เครื่องมือการย้ายเพื่อโคลนเนื้อหา**คอลเลกชันพื้นที่ทำงานของ Power BI** ไปยัง Power BI - https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded#content-migration ได้

2. เริ่มต้นด้วยแอปพลิเคชัน POC **Power BI Embedded** ที่ใช้เนื้อหา Power BI

3. เมื่อคุณพร้อมสำหรับการใช้งานจริง ซื้อความจุเฉพาะของ **Power BI Embedded** และกำหนดเนื้อหา Power BI (พื้นที่ทำงาน) ของคุณลงในความจุนั้น

    > [!Note]
    > คุณยังสามารถใช้**คอลเลกชันพื้นที่ทำงานของ Power BI** ต่อ ขณะที่สร้างโซลูชัน **Power BI Embedded** ไปพร้อม ๆ กันได้ เมื่อคุณพร้อม คุณสามารถย้ายลูกค้าของคุณไปยังโซลูชัน **Power BI Embedded** ใหม่ และถอนโซลูชัน**คอลเลกชันพื้นที่ทำงานของ Power BI** ได้

สำหรับข้อมูลเพิ่มเติม โปรดอ้างอิง[วิธีการย้ายเนื้อหาคอลเลกชันพื้นที่ทำงานของ Power BI ไปยัง Power BI Embedded](https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded)

### <a name="is-power-bi-workspace-collection-on-a-deprecation-path"></a>คอลเลกชันพื้นที่ทำงานของ Power BI อยู่ในเส้นทางที่ยกเลิกการสนับสนุนหรือไม่

ใช่ แต่ลูกค้าที่กำลังใช้โซลูชัน**คอลเลกชันพื้นที่ทำงานของ Power BI** อยู่ สามารถใช้ได้จนกว่าจะถูกยกเลิก ลูกค้ายังสามารถสร้างคอลเลกชันพื้นที่ทำงานใหม่ และสร้างแอปพลิเคชัน **Power BI Embedded** ที่ยังใช้โซลูชัน**คอลเลกชันพื้นที่ทำงานของ Power BI** ได้

อย่างไรก็ตาม กรณียังหมายความว่า ไม่มีการเพิ่มคุณลักษณะใหม่ใด ๆ ในโซลูชัน**คอลเลกชันพื้นที่ทำงาน Power BI** เราขอแนะนำให้ลูกค้าวางแผนการโยกย้ายไปยังโซลูชัน **Power BI Embedded** ใหม่

### <a name="when-is-power-bi-workspace-collection-support-discontinued"></a>เมื่อไรที่คอลเลกชันพื้นที่ทำงาน Power BI จะยกเลิกการสนับสนุน?

ลูกค้าที่กำลังใช้โซลูชัน**คอลเลกชันพื้นที่ทำงาน Power BI** อยู่ สามารถใช้งานต่อจนถึงปลายเดือนมิถุนายน 2018 หรือจนถึงจุดสิ้นสุดของข้อตกลงการสนับสนุนของพวกเขา

### <a name="in-what-regions-can-i-create-a-pbi-workspace-collection"></a>ภูมิภาคใดที่ฉันสามารถสร้างคอลเลกชันพื้นที่ทำงาน PBI ได้

ภูมิภาคที่มี ได้แก่ Australia Southeast, Brazil South, Canada Central, East US 2, Japan East, North Central US, North Europe, South Central US, Southeast Asia, UK South, West Europe, West India และ West US

### <a name="why-should-i-migrate-from-pbi-workspace-collection-to-power-bi-embedded"></a>ทำไมฉันถึงต้องย้ายจากคอลเลกชันพื้นที่ทำงาน PBI ไปยัง Power BI Embedded?

มีคุณลักษณะใหม่บางอย่างและความจุในโซลูชัน **Power BI Embedded** ที่คุณไม่สามารถทำได้ด้วย**คอลเลกชันพื้นที่ทำงานของ Power BI**

ตัวอย่างของคุณลักษณะ ได้แก่:
* รองรับแหล่งข้อมูล PBI ทั้งหมด รองรับเฉพาะแหล่งข้อมูล**คอลเลกชันพื้นที่ทำงาน Power BI** สองรายการเท่านั้น 
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

---
title: การป้องกันข้อมูลใน Power BI
description: เรียนรู้วิธีการป้องกันข้อมูลใน Power BI
author: paulinbar
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/21/2020
ms.author: painbar
LocalizationGroup: Data from files
ms.openlocfilehash: fa969f8f738cf09e9e01e284de8f60e2fd8ce9ab
ms.sourcegitcommit: cd64ddd3a6888253dca3b2e3fe24ed8bb9b66bc6
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/03/2020
ms.locfileid: "84315683"
---
# <a name="data-protection-in-power-bi"></a>การป้องกันข้อมูลใน Power BI

องค์กรสมัยใหม่มีข้อบังคับและข้อกำหนดทางธุรกิจที่เข้มงวดเกี่ยวกับวิธีจัดการและปกป้องข้อมูลที่มีความละเอียดอ่อน เพื่อให้การควบคุมและการเปิดเผยข้อมูลดังกล่าว Power BI สามารถทำงานร่วมกับ Microsoft Information Protection และ Microsoft Cloud App Security ซึ่งจะช่วยให้คุณสามารถ:
* ใช้ [ป้ายชื่อระดับความลับ](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels?view=o365-worldwide)ของ Microsoft Information Protection เพื่อจัดหมวดหมู่และติดป้ายเนื้อหา (แดชบอร์ด รายงาน ชุดข้อมูล และกระแสข้อมูล) ในบริการของ Power BI โดยใช้อนุกรมวิธานเดียวกันกับที่ใช้ในการจัดหมวดหมู่และป้องกันไฟล์ใน Office 365
* ใช้ป้ายชื่อระดับความลับของ Microsoft Information Protection และการป้องกันข้อมูลเมื่อมีการส่งออกไปยังไฟล์ Excel, PowerPoint หรือ PDF
* ใช้ Microsoft Cloud App Security เพื่อตรวจสอบกิจกรรมใน Power BI ตรวจสอบปัญหาด้านความปลอดภัย และป้องกันเนื้อหาใน Power BI ด้วยการควบคุมการเข้าถึงแอปแบบมีเงื่อนไขของ Microsoft Cloud App Security

**หมายเหตุสำคัญ**
* การติดป้ายชื่อระดับความลับ **ไม่** ส่งผลกระทบต่อการเข้าถึงเนื้อหาภายใน Power BI – การเข้าถึงเนื้อหาภายใน Power BI ได้รับการจัดการโดยสิทธิ์การใช้งาน Power BI เท่านั้น ในขณะที่ป้ายชื่อมองเห็นได้ การตั้งค่าการเข้ารหัสลับใดก็ตามที่เกี่ยวข้อง (กำหนดค่าแล้วใน [ศูนย์ความปลอดภัยของ Microsoft 365](https://security.microsoft.com/) หรือ[ศูนย์การปฏิบัติตามกฎระเบียบของ Microsoft 365](https://compliance.microsoft.com/)) จะไม่ถูกนำไปใช้ ป้ายชื่อดังกล่าวจะถูกนำไปใช้กับข้อมูลที่ถูกส่งออกไปยังไฟล์ Excel, PowerPoint และ PDF เท่านั้น
* ป้ายชื่อระดับความลับและการเข้ารหัสลับไฟล์**จะไม่ถูก**นำไปใช้ในเส้นทางการส่งออกอื่นนอกเหนือจากการส่งออกไปยัง Excel, PowerPoint และ PDF ผู้ดูแลระบบผู้เช่า Power BI สามารถปิดใช้งานเส้นทางการส่งออกใดก็ตามหรือทั้งหมดที่ไม่สนับสนุนการใช้งานป้ายชื่อระดับความลับและการตั้งค่าการเข้ารหัสลับไฟล์ที่เกี่ยวข้อง

## <a name="sensitivity-labels-in-power-bi"></a>ป้ายชื่อระดับความลับใน Power BI

ป้ายชื่อระดับความลับจะถูกสร้างขึ้นและจัดการใน [ศูนย์ความปลอดภัยของ Microsoft 365](https://security.microsoft.com/) หรือ [ศูนย์การปฏิบัติตามข้อบังคับ Microsoft 365](https://compliance.microsoft.com/)

เมื่อต้องการเข้าถึงป้ายชื่อระดับความลับในศูนย์ใดศูนย์หนึ่งเหล่านี้ให้ไปที่ **การจัดประเภท > ป้ายชื่อระดับความลับ** ป้ายชื่อระดับความลับเหล่านี้สามารถใช้ได้กับบริการหลายอย่างของ Microsoft เช่น Azure Information Protection, แอป Office และบริการ Office 365

> [!Important]
> หากองค์กรของคุณใช้ป้ายชื่อระดับความลับของ Azure Information Protection คุณจะต้อง[ย้าย](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)ป้ายชื่อไปยังหนึ่งในบริการที่ระบุไว้ก่อนหน้านี้เพื่อให้สามารถใช้ป้ายชื่อใน Power BI ได้

> [!NOTE]
> ป้ายชื่อระดับความลับยังรองรับเฉพาะผู้เช่าในระบบคลาวด์สาธารณะเท่านั้น และไม่รองรับสำหรับผู้เช่าในระบบคลาวด์ เช่น Sovereign Cloud

## <a name="how-sensitivity-labels-work-in-power-bi"></a>ป้ายชื่อระดับความลับทำงานใน Power BI ได้อย่างไร

เมื่อคุณนำป้ายชื่อระดับความลับไปใช้กับแดชบอร์ด รายงาน ชุดข้อมูล และกระแสข้อมูลของ Power BI จะคล้ายกับการใช้แท็กกับแหล่งข้อมูลดังกล่าวมีประโยชน์ดังต่อไปนี้:
* **แบบปรับแต่งได้** - คุณสามารถสร้างหมวดหมู่สำหรับเนื้อหาที่ละเอียดอ่อนในระดับที่แตกต่างกันในองค์กรของคุณ เช่น ส่วนบุคคล สาธารณะ ทั่วไป เป็นความลับ และเป็นความลับสูง
* **ข้อความชัดเจน** - เนื่องจากป้ายชื่อเป็นข้อความที่ชัดเจน จึงเป็นเรื่องง่ายสำหรับผู้ใช้ที่จะเข้าใจวิธีการปฏิบัติต่อเนื้อหาตามแนวทางของป้ายชื่อระดับความลับ
* **ถาวร** -  หลังจากใช้งานป้ายชื่อระดับความลับกับเนื้อหา ป้ายชื่อจะรวมเข้ากับเนื้อหาดังกล่าวเมื่อมีการส่งออกไปยังไฟล์ Excel, PowerPoint และ PDF และเป็นข้อมูลพื้นฐานสำหรับการใช้และบังคับใช้นโยบาย

ซึ่งหมายความว่าป้ายชื่อระดับความลับเกิดขึ้นหลังเนื้อหาเมื่อมีการส่งออกไปยังไฟล์ Excel, PowerPoint และ PDF และเป็นข้อมูลพื้นฐานสำหรับการใช้และบังคับใช้นโยบาย

ผู้ดูแลผู้เช่า Power BI สามารถควบคุม [ส่งออกไปยัง Excel](service-admin-portal.md#export-to-excel) และ [ส่งออกไปยัง PowerPoint และ PDF](service-admin-portal.md#export-reports-as-powerpoint-presentations-or-pdf-documents) ใน [พอร์ทัลผู้ดูแลระบบ Power BI](service-admin-portal.md)

## <a name="sensitivity-label-example"></a>ตัวอย่างป้ายชื่อระดับความลับ

นี่คือตัวอย่างแบบย่อเพื่อแสดงวิธีการทำงานของป้ายชื่อระดับความลับใน Power BI
1. ในบริการของ Power BI มีการใช้ป้ายชื่อระดับความลับ**เป็นความลับสูง** กับรายงาน

   ![ป้ายชื่อระดับความลับในมุมมองรายการ](media/service-security-data-protection-overview/sensitivity-labels-overview-01.png)
   
1. เมื่อมีการส่งออกข้อมูลจากรายงานนี้ไปยังไฟล์ Excel ป้ายชื่อระดับความลับและการป้องกันจะถูกนำไปใช้กับไฟล์ Excel ที่ส่งออกด้วย

   ![ป้ายชื่อระดับความลับจะติดไปกับเนื้อหา](media/service-security-data-protection-overview/sensitivity-labels-overview-02.png)

ในแอปพลิเคชัน Microsoft Office ป้ายชื่อระดับความลับจะปรากฏเป็นแท็กในอีเมลหรือเอกสาร คล้ายกับที่แสดงในภาพด้านบน นอกจากนี้ คุณยังสามารถกำหนดหมวดหมู่ให้กับเนื้อหา (เช่น สติกเกอร์) ที่ยังคงติดอยู่และติดไปกับเนื้อหาตามที่มีการใช้งานและแบ่งปันผ่าน Power BI คุณสามารถใช้การจัดหมวดหมู่นี้เพื่อสร้างรายงานการใช้งานและดูข้อมูลกิจกรรมสำหรับเนื้อหาที่ละเอียดอ่อนของคุณ จากข้อมูลนี้คุณสามารถเลือกในภายหลังได้ตลอดเวลาเพื่อใช้การตั้งค่าการป้องกัน

## <a name="requirements-for-using-sensitivity-labels-in-power-bi"></a>ข้อกำหนดสำหรับการใช้ป้ายชื่อระดับความลับใน Power BI

ก่อนที่จะเปิดและใช้งานป้ายชื่อระดับความลับของคุณใน Power BI คุณต้องดำเนินการข้อกำหนดเบื้องต้นต่อไปนี้ให้เสร็จสมบูรณ์ก่อน:
* ตรวจสอบให้แน่ใจว่ามีการกำหนดป้ายชื่อระดับความลับใน [ศูนย์ความปลอดภัยของ Microsoft 365](https://security.microsoft.com/) หรือ [ศูนย์การปฏิบัติตามข้อบังคับ Microsoft 365](https://compliance.microsoft.com/)
* [เปิดใช้งานป้ายชื่อระดับความลับ](service-security-enable-data-sensitivity-labels.md)ใน Power BI
* ตรวจสอบให้แน่ใจว่าผู้ใช้มี[สิทธิการใช้งานที่เหมาะสม](#licensing)
* ถ้าใช้ Microsoft Cloud App Security กับ Power BI ตรวจสอบให้แน่ใจว่ามี [การให้สิทธิการใช้งานที่เหมาะสม](service-security-using-microsoft-cloud-app-security-controls.md#cloud-app-security-licensing)

## <a name="protect-content-using-microsoft-cloud-app-security"></a>ป้องกันเนื้อหาโดยใช้ Microsoft Cloud App Security

คุณสามารถป้องกันเนื้อหาใน Power BI ไม่ให้มีการรั่วไหลที่ไม่ได้ตั้งใจหรือการละเมิดได้โดยใช้ Microsoft Cloud App Security เมื่อตั้งค่าและกำหนดค่า Microsoft Cloud App Security แล้ว ผู้ดูแลระบบความปลอดภัยสามารถตรวจสอบการเข้าถึงและกิจกรรมของผู้ใช้ ทำการวิเคราะห์ความเสี่ยงแบบเรียลไทม์ และตั้งค่าตัวควบคุมเฉพาะป้ายชื่อได้

ตัวอย่างเช่น องค์กรสามารถใช้ Microsoft Cloud App Security เพื่อกำหนดค่านโยบายที่ป้องกันไม่ให้ผู้ใช้ดาวน์โหลดข้อมูลที่ละเอียดอ่อนจาก Power BI ไปยังอุปกรณ์ที่ไม่มีการจัดการได้ การกำหนดค่าดังกล่าวช่วยให้ผู้ใช้ยังคงทำงานได้อย่างมีประสิทธิภาพและเชื่อมต่อกับ Power BI ได้จากทุกแห่ง ในขณะที่การใช้ Microsoft Cloud App Security ยังช่วยป้องกันไม่ประสิทธิภาพการทำงานของระบบลดลงจากการดำเนินการของผู้ใช้ในแบบเรียลไทม์ด้วย

**ข้อกำหนด**

ก่อนที่ป้ายชื่อระดับความลับของคุณจะสามารถใช้ Microsoft Cloud App Security ได้ คุณต้องปฏิบัติตามข้อกำหนดเบื้องต้นต่อไปนี้:
* ต้องเปิดใช้งาน Cloud App Security และ Azure Information Protection [สำหรับผู้เช่าของคุณ](https://docs.microsoft.com/cloud-app-security/azip-integration)
* แอป [ต้องเชื่อมต่อกับ Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps)

## <a name="licensing"></a>สิทธิ์การใช้งาน

* การดูหรือใช้ป้ายชื่อระดับความลับ Microsoft Information Protection ใน Power BI ต้องมีสิทธิ์การใช้งานของ Azure Information Protection แบบ Premium P1 หรือ Premium P2 คุณสามารถซื้อ Microsoft Azure Information Protection แบบสแตนด์อโลนหรือผ่านหนึ่งในชุดโปรแกรมการอนุญาตให้ใช้สิทธิของ Microsoft ได้ โปรดดู [การกำหนดราคา Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection/) สำหรับรายละเอียด
* การดูและการใช้ป้ายชื่อในแอป Office มี[ข้อกำหนดเรื่องสิทธิ์การใช้งาน](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels#subscription-and-licensing-requirements-for-sensitivity-labels)
* หากต้องการนำป้ายชื่อระดับความลับไปใช้กับเนื้อหา Power BI ผู้ใช้จะต้องมีสิทธิ์การใช้งาน Power BI Pro นอกเหนือจากหนึ่งในสิทธิ์การใช้งาน Azure Information Protection ที่กล่าวถึงข้างต้น
* คุณต้องมี[สิทธิการใช้งานที่จำเป็นสำหรับการ Microsoft Cloud App Security](https://docs.microsoft.com/power-bi/admin/service-security-using-microsoft-cloud-app-security-controls#microsoft-cloud-app-security-licensing) หากคุณจะใช้เพื่อปกป้องเนื้อหา Power BI จากการรั่วไหลและการละเมิดที่ไม่ได้ตั้งใจ

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด

รายการต่อไปนี้แสดงข้อจำกัดบางอย่างของป้ายชื่อระดับความลับใน Power BI:

**ทั่วไป**
* ป้ายชื่อระดับความลับสามารถใช้ได้เฉพาะบนแดชบอร์ด รายงาน ชุดข้อมูล และกระแสข้อมูลเท่านั้น ในปัจจุบัน ป้ายชื่อระดับความลับยังไม่สามารถใช้ได้สำหรับ [รายงานที่มีการแบ่งหน้า](../paginated-reports/report-builder-power-bi.md) และสมุดงาน
* ป้ายชื่อระดับความลับบนแอสเซท Power BI สามารถมองเห็นได้ในรายการพื้นที่ทำงาน สายข้อมูล รายการโปรด ล่าสุด และมุมมองแอป ในขณะนี้ป้ายชื่อจะไม่สามารถมองเห็นได้ในมุมมอง "แบ่งปันแล้วกับฉัน" อย่างไรก็ตาม โปรดทราบว่าป้ายชื่อที่ใช้กับแอสเซท Power BI แม้ว่าจะไม่สามารถมองเห็นได้ จะยังคงอยู่ในข้อมูลที่ส่งออกไปเป็นไฟล์ Excel, PowerPoint และ PDF เสมอ
* ป้ายชื่อระดับความลับได้รับการรองรับสำหรับผู้เช่าในระบบคลาวด์ (สาธารณะ) ส่วนกลางเท่านั้น ป้ายชื่อระดับความลับไม่ได้รับการรองรับสำหรับผู้เช่าในระบบคลาวด์อื่นๆ
* ไม่รองรับป้ายชื่อระดับความลับของข้อมูลสำหรับแอปเทมเพลต ป้ายชื่อระดับความลับที่ตั้งค่าโดยผู้สร้างแอปเทมเพลตจะถูกลบออกเเมื่อมีการแยกและติดตั้งแอป และป้ายชื่อระดับความลับที่เพิ่มไปยังอาร์ทิแฟกต์ในแอปเทมเพลตที่ติดตั้งโดยผู้บริโภคแอปสูญหายไป (ตั้งค่าใหม่เป็นไม่มีอะไร) เมื่อมีการอัปเดตแอป
* Power BI ไม่รองรับป้ายชื่อระดับความลับของประเภทการป้องกัน [Do Not Forward](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels?view=o365-worldwide#let-users-assign-permissions), [ผู้ใช้กำหนดเอง](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels?view=o365-worldwide#let-users-assign-permissions) และ [HYOK](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions) ประเภทการป้องกันแบบ Do Not Forward และผู้ใช้กำหนดเองหมายถึงป้ายชื่อที่กำหนดใน[ศูนย์ความปลอดภัยของ Microsoft 365](https://security.microsoft.com/) หรือ[ศูนย์ควบคุมการปฏิบัติตามข้อบังคับของ Microsoft 365](https://compliance.microsoft.com/)
* ไม่แนะนำให้ผู้ใช้สามารถใช้ป้ายชื่อหลักใน Power BI ได้ ถ้ามีการใช้ป้ายชื่อหลักกับเนื้อหา การส่งออกข้อมูลจากเนื้อหานั้นไปยังไฟล์ (Excel, PowerPoint และ PDF) จะล้มเหลว ดู [ป้ายชื่อย่อย (การจัดกลุ่มป้ายชื่อ)](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels?view=o365-worldwide#sublabels-grouping-labels)

**ส่งออก**
* ตัวควบคุมป้ายชื่อและการป้องกันจะถูกบังคับใช้เฉพาะเมื่อมีการส่งออกข้อมูลไปยังไฟล์ Excel, PowerPoint และ PDF ป้ายชื่อและการป้องกันไม่ได้ถูกบังคับใช้เมื่อมีการส่งออกข้อมูลไปยังไฟล์ .csv หรือ .pbix, Analyze ใน Excel หรือเส้นทางการส่งออกอื่นๆ
* การใช้ป้ายชื่อระดับความลับและการป้องกันกับไฟล์ที่ส่งออกจะไม่เพิ่มเครื่องหมายเนื้อหาไปยังไฟล์ อย่างไรก็ตาม ถ้ามีการกำหนดค่าป้ายชื่อเพื่อใช้เครื่องหมายเนื้อหา ดังนั้นเครื่องหมายเนื้อหาดังกล่าวจะถูกนำไปใช้โดยอัตโนมัติโดยไคลเอ็นต์การติดป้ายแบบรวมของ Azure Information Protection เมื่อเปิดไฟล์ในแอป Office desktop การทำเครื่องหมายเนื้อหาจะไม่ถูกนำไปใช้โดยอัตโนมัติเมื่อคุณใช้การติดป้ายชื่อที่มีอยู่ภายในสำหรับเดสก์ท็อป อุปกรณ์เคลื่อนที่ หรือเว็บแอป โปรดดู [เมื่อแอป Office ใช้การทำเครื่องหมายเนื้อหาและการเข้ารหัสลับ](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-office-apps?view=o365-worldwide#when-office-apps-apply-content-marking-and-encryption) สำหรับรายละเอียดเพิ่มเติม
* ผู้ใช้ที่ส่งออกไฟล์จาก Power BI มีสิทธิ์ในการเข้าถึงและการแก้ไขไฟล์นั้นตามการตั้งค่าป้ายชื่อระดับความลับ ผู้ใช้ที่ส่งออกข้อมูลไม่ได้รับสิทธิ์การเป็นเจ้าของสำหรับไฟล์ดังกล่าว
* การส่งออกจะล้มเหลวถ้าไม่สามารถนำป้ายชื่อไปใช้ได้เมื่อมีการส่งออกข้อมูลไปยังไฟล์ หากต้องการตรวจสอบว่าการส่งออกล้มเหลวเนื่องจากไม่สามารถใช้ป้ายชื่อได้ ให้คลิกที่ชื่อรายงานหรือแดชบอร์ดที่กึ่งกลางของแถบชื่อเรื่องและดูว่า "ไม่สามารถโหลดป้ายชื่อระดับความลับได้" ในดร็อปดาวน์ข้อมูลที่เปิดขึ้น ซึ่งอาจเกิดขึ้นได้ถ้าป้ายชื่อที่ใช้ได้รับการยกเลิกการเผยแพร่หรือถูกลบโดยผู้ดูแลระบบความปลอดภัย หรือเป็นผลมาจากปัญหาระบบชั่วคราว


## <a name="next-steps"></a>ขั้นตอนถัดไป

บทความนี้แสดงภาพรวมของการป้องกันข้อมูลใน Power BI บทความต่อไปนี้แสดงรายละเอียดเพิ่มเติมเกี่ยวกับการป้องกันข้อมูลใน Power BI 

* [เปิดใช้งานป้ายชื่อระดับความลับของข้อมูลใน Power BI](service-security-enable-data-sensitivity-labels.md)
* [ใช้ป้ายชื่อระดับความลับของข้อมูลใน Power BI](../collaborate-share/service-security-apply-data-sensitivity-labels.md)
* [ใช้ตัวควบคุม Microsoft Cloud App Security ใน Power BI](service-security-using-microsoft-cloud-app-security-controls.md)
* [รายงานเมตริกการป้องกันข้อมูล](service-security-data-protection-metrics-report.md)
---
title: การจัดการ Power BI - คำถามที่ถามบ่อย (FAQ)
description: เรียนรู้คำตอบของคำถามที่ถามบ่อยเกี่ยวกับการลงทะเบียน Power BI การจัดการผู้เช่า และงานอื่น ๆ สำหรับการดูแลระบบ
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 11/28/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 60ac0a944b1eb54ab998fbf25cb5fb79d6dddbe6
ms.sourcegitcommit: 833cf1252807721fb1b3000487bd032bfd6c8c98
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/04/2018
ms.locfileid: "48271911"
---
# <a name="administering-power-bi---frequently-asked-questions-faq"></a>การจัดการ Power BI - คำถามที่ถามบ่อย (FAQ)

บทความนี้ตอบคำถามที่ถามบ่อยสำหรับการดูแลระบบ Power BI สำหรับภาพรวมของการดูแลระบบ Power BI ดู[การดูแลระบบ Power BI คืออะไร?](service-admin-administering-power-bi-in-your-organization.md)

## <a name="whats-in-this-article"></a>สิ่งที่อยู่ในบทความนี้
**ลงทะเบียนใช้งาน Power BI**

* [ผู้ใช้สามารถลงทะเบียนเข้าใช้ Power BI ได้อย่างไร?](#how-do-users-sign-up-for-power-bi)
* [ผู้ใช้แต่ละคนในองค์กรของฉันจะลงทะเบียนได้อย่างไร?](#how-do-individual-users-in-my-organization-sign-up)
* [ฉันจะป้องกันไม่ให้ผู้ใช้เข้าร่วมผู้เช่า Office 365 ของฉันที่มีอยู่ได้อย่างไร?](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)
* [ฉันจะอนุญาตให้ผู้ใช้เข้าร่วมผู้เช่า Office 365 ของฉันที่มีอยู่ได้อย่างไร?](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)
* [ฉันจะตรวจพิสูจน์ได้อย่างไรถ้าฉันมีบล็อกในผู้เช่า?](#how-do-i-verify-if-i-have-the-block-on-in-the-tenant)
* [ฉันจะป้องกันไม่ให้ผู้ใช้ปัจจุบันของฉันเริ่มใช้ Power BI ได้อย่างไร?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [ฉันจะอนุญาตให้ผู้ใช้ปัจจุบันของฉันลงทะเบียนสำหรับ Power BI ได้อย่างไร?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

**การดูแลระบบ Power BI**

* [วิธีนี้จะเปลี่ยนวิธีที่ฉันจัดการข้อมูลประจำตัวสำหรับผู้ใช้ต่าง ๆ ในองค์กรของฉันในปัจจุบันได้อย่างไร?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [เราจะจัดการกับ Power BI ได้อย่างไร?](#how-do-we-manage-power-bi)
* [อะไรคือกระบวนการจัดการผู้เช่าที่สร้างโดย Microsoft สำหรับผู้ใช้ของฉัน?](#what-is-the-process-to-manage-a-tenant-created-by-Microsoft-for-my-users)
* [ถ้าฉันมีหลายโดเมน ฉันสามารถควบคุมผู้เช่า Office 365 ที่มีการเพิ่มผู้ใช้เข้าไปได้อย่างไร?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)
* [ฉันจะลบ Power BI สำหรับผู้ใช้ที่ลงทะเบียนแล้วได้อย่างไร?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [ฉันจะทราบได้อย่างไรเมื่อมีผู้ใช้ใหม่เข้าร่วมในผู้เช่าของฉัน?](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [ฉันควรเตรียมพร้อมสำหรับสิ่งอื่น ๆ เพิ่มเติมอีกหรือไม่?](#are-there-any-additional-things-i-should-be-prepared-for)
* [ผู้เช่า Power BI ของฉันอยู่ที่ไหน?](#where-is-my-power-bi-tenant-located)
* [Power BI SLA (ข้อตกลงระดับบริการ [Service Level Agreement]) คืออะไร?](#what-is-the-power-bi-sla)

**การรักษาความปลอดภัยใน Power BI**

* [Power BI ตรงตามข้อกำหนดการปฏิบัติตามกฎระเบียบของชาติ ภูมิภาค และข้อกำหนดเฉพาะสำหรับอุตสาหกรรมหรือไม่?](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)
* [การรักษาความปลอดภัยทำงานอย่างไรใน Power BI?](#how-does-security-work-in-power-bi)

## <a name="sign-up-for-power-bi"></a>ลงทะเบียนใช้งาน Power BI
### <a name="how-do-users-sign-up-for-power-bi"></a>ผู้ใช้จะลงทะเบียนสำหรับ Power BI ได้อย่างไร?
คุณสามารถลงทะเบียนสำหรับ Power BI ได้ผ่าน[เว็บไซต์ Power BI](https://powerbi.microsoft.com) นอกจากนี้ คุณยังสามารถลงทะเบียนผ่านหน้าบริการซื้อขายบนศูนย์การดูแลระบบ Office 365 ได้ เมื่อผู้ดูแลระบบลงทะเบียนสำหรับ Power BI พวกเขาสามารถกำหนดสิทธิ์การใช้งานของผู้ใช้ต่าง ๆ ที่ควรมีสิทธิ์เข้าใช้งานได้

นอกจากนี้ ผู้ใช้งานแต่ละคนในองค์กรของคุณอาจสามารถลงทะเบียนสำหรับ Power BI ผ่าน[เว็บไซต์ Power BI](https://powerbi.microsoft.com)ได้ เมื่อผู้ใช้ในองค์กรของคุณลงทะเบียนสำหรับ Power BI จะมีการกำหนดสิทธิ์การใช้งาน Power BI ให้ผู้ใช้รายนั้นโดยอัตโนมัติ [เรียนรู้เพิ่มเติม](service-self-service-signup-for-power-bi.md)

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>ผู้ใช้แต่ละคนในองค์กรของฉันจะลงทะเบียนได้อย่างไร?
มีสามสถานการณ์ที่อาจนำไปใช้กับผู้ใช้ในองค์กรของคุณ:

สถานการณ์ที่ 1: องค์กรของคุณมีสภาพแวดล้อม Office 365 อยู่แล้ว และผู้ใช้ที่ลงทะเบียนสำหรับ Power BI มีบัญชีผู้ใช้ Office 365 อยู่แล้ว
ในสถานการณ์นี้ ถ้าผู้ใช้มีบัญชีที่ทำงานหรือบัญชีโรงเรียนอยู่แล้วในผู้เช่า (ตัวอย่างเช่น contoso.com) แต่ยังไม่มี Power BI, Microsoft จะเพียงแค่เปิดใช้งานแผนสำหรับบัญชีผู้ใช้นั้น และผู้ใช้จะได้รับแจ้งเกี่ยวกับวิธีการใช้บริการ Power BI โดยอัตโนมัติ

สถานการณ์ที่ 2: องค์กรของคุณมีสภาพแวดล้อม Office 365 อยู่แล้ว และผู้ใช้ที่ลงทะเบียนสำหรับ Power BI ไม่มีบัญชีผู้ใช้ Office 365
ในสถานการณ์นี้ ผู้ใช้มีที่อยู่อีเมลในโดเมนขององค์กรของคุณ (ตัวอย่างเช่น contoso.com) แต่ยังไม่มีบัญชีผู้ใช้ Office 365 ในกรณีนี้ ผู้ใช้สามารถลงทะเบียนสำหรับ Power BI ได้ และจะได้รับบัญชีผู้ใช้โดยอัตโนมัติ ซึ่นี่งช่วยให้ผู้ใช้เข้าถึงบริการ Power BI ได้ ตัวอย่างเช่น ถ้าพนักงานชื่อว่า Nancy ใช้อีเมลที่ทำงานของเธอ (ตัวอย่างเช่นNancy@contoso.com) เพื่อลงทะเบียน Microsoft จะเพิ่ม Nancy เป็นผู้ใช้ในสภาพแวดล้อม Office 365 ของ Contoso และเปิดใช้งาน Power BI สำหรับบัญชีผู้ใช้นั้นโดยอัตโนมัติ

สถานการณ์ที่ 3: องค์กรของคุณไม่มีสภาพแวดล้อม Office 365 ที่เชื่อมต่อกับโดเมนอีเมลของคุณ
ไม่มีการดำเนินการดูแลระบบที่องค์กรของคุณจำเป็นต้องดำเนินการเพื่อใช้ประโยชน์จาก Power BI ผู้ใช้จะถูกเพิ่มไปยังไดเรกทอรีผู้ใช้เฉพาะระบบคลาวด์ใหม่ และคุณจะมีตัวเลือกในการเข้าควบคุมในฐานะผู้ดูแลระบบผู้เช่าและจัดการเหล่านี้

> [!IMPORTANT]
> หากองค์กรของคุณมีหลายโดเมนอีเมล และคุณต้องการให้ส่วนขยายที่อยู่อีเมลทั้งหมดอยู่ในผู้เช่าเดียวกัน เพิ่มโดเมนที่อยู่อีเมลทั้งหมดไปยังผู้เช่า Azure Active Directory ก่อนที่ผู้ใช้จะลงทะเบียน ไม่มีกลไกอัตโนมัติใดในการย้ายผู้ใช้ไปทั่วผู้เช่าหลังจากที่มีการสร้างขึ้นแล้ว สำหรับข้อมูลเพิ่มเติมเกี่ยวกับกระบวนการนี้ ดู[ถ้าฉันมีหลายโดเมน ฉันสามารถควบคุมผู้เช่า Office 365 ที่มีการเพิ่มผู้ใช้เข้าไปได้อย่างไร?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)ในภายหลังในบทความนี้ และ[เพิ่มโดเมนของคุณไปยัง Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)ออนไลน์ได้
> 
> 

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>ฉันจะป้องกันไม่ให้ผู้ใช้เข้าร่วมผู้เช่า Office 365 ของฉันที่มีอยู่ได้อย่างไร?
มีหลายขั้นตอนที่คุณสามารถใช้ได้ในฐานะผู้ดูแลระบบเพื่อป้องกันไม่ให้ผู้ใช้เข้าร่วมผู้เช่า Office 365 ของคุณที่มีอยู่ได้ ถ้าคุณบล็อกรายการนี้ ความพยายามของผู้ใช้ในการลงทะเบียนจะล้มเหลว และผู้ใช้จะถูกนำไปยังการติดต่อผู้ดูแลระบบขององค์กรของผู้ใช้เอง คุณไม่ต้องทำซ้ำกระบวนการนี้ถ้าคุณได้ปิดใช้งานการแจกจ่ายสิทธิ์การใช้งานโดยอัตโนมัติแล้ว (เช่น Office 365 สำหรับการศึกษาสำหรับนักเรียน คณะ และเจ้าหน้าที่)

ขั้นตอนเหล่านี้จำเป็นต้องใช้ Windows PowerShell เมื่อต้องการเริ่มต้นใช้งาน Windows PowerShell ดู[คำแนะนำการเริ่มต้นใช้งาน PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=286814)

การดำเนินการขั้นตอนต่อไปนี้ คุณต้องติดตั้งเวอร์ชัน 64 บิตล่าสุดของ [Azure Active Directory Module สำหรับ Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297)

หลังจากที่คุณเลือกลิงก์ เลือก**เรียกใช้**เพื่อเปิดใช้งานแพ็คเกจตัวติดตั้ง

**ปิดใช้งานการเข้าร่วมผู้เช่าโดยอัตโนมัติ**: ใช้คำสั่ง Windows PowerShell นี้เพื่อป้องกันไม่ให้ผู้ใช้ใหม่เข้าร่วมผู้เช่าที่มีการจัดการ:

* การปิดใช้งานการเข้าร่วมผู้เช่าโดยอัตโนมัติสำหรับผู้ใช้ใหม่:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $false
* การเปิดใช้งานการเข้าร่วมผู้เช่าโดยอัตโนมัติสำหรับผู้ใช้ใหม่:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

> [!NOTE]
> การบล็อกนี้ป้องกันไม่ให้ผู้ใช้ใหม่ในองค์กรของคุณลงทะเบียนสำหรับ Power BI ผู้ใช้ที่ลงทะเบียนใช้ Power BI ก่อนการปิดใช้งานการลงทะเบียนใหม่สำหรับองค์กรของคุณ จะยังคงมีสิทธิ์ในการใช้งานอยู่ ดูหัวข้อ [ฉันสามารถลบสิทธิ์การใช้งานได้อย่างไร?] สำหรับคำแนะนำเกี่ยวกับวิธีที่คุณสามารถลบการเข้าใช้งาน Power BI ของผู้ใช้ที่ได้ลงทะเบียนสำหรับบริการนี้
> 
> 

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>ฉันจะอนุญาตให้ผู้ใช้เข้าร่วมผู้เช่า Office 365 ของฉันที่มีอยู่ได้อย่างไร?
เมื่อต้องการอนุญาตให้ผู้ใช้เข้าร่วมผู้เช่าของคุณ เรียกใช้คำสั่งตรงข้ามตามที่อธิบายไว้ในคำถาม่ด้านบน

การดำเนินการขั้นตอนต่อไปนี้ คุณต้องติดตั้งเวอร์ชัน 64 บิตล่าสุดของ [Azure Active Directory Module สำหรับ Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297)

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

### <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>ฉันจะตรวจพิสูจน์ได้อย่างไรถ้าฉันมีบล็อกในผู้เช่า?
ใช้สคริปต์ PowerShell ต่อไปนี้

การดำเนินการขั้นตอนต่อไปนี้ คุณต้องติดตั้งเวอร์ชัน 64 บิตล่าสุดของ [Azure Active Directory Module สำหรับ Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297)

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Get-MsolCompanyInformation | fl allow*

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>ฉันจะป้องกันไม่ให้ผู้ใช้ปัจจุบันของฉันเริ่มใช้ Power BI ได้อย่างไร?
มีหลายขั้นตอนที่คุณสามารถใช้ได้ในฐานะผู้ดูแลระบบเพื่อป้องกันไม่ให้ผู้ใช้ลงทะเบียนสำหรับ Power BI ถ้าคุณบล็อกรายการนี้ ความพยายามของผู้ใช้ในการลงทะเบียนจะล้มเหลว และผู้ใช้จะถูกนำไปยังการติดต่อผู้ดูแลระบบขององค์กรของผู้ใช้เอง คุณไม่ต้องทำซ้ำกระบวนการนี้ถ้าคุณได้ปิดใช้งานการแจกจ่ายสิทธิ์การใช้งานโดยอัตโนมัติแล้ว (เช่น Office 365 สำหรับการศึกษาสำหรับนักเรียน คณะ และเจ้าหน้าที่) [เรียนรู้เพิ่มเติม](service-admin-licensing-organization.md#enable-or-disable-individual-user-sign-up-in-azure-active-directory)

การตั้งค่า AAD ซึ่งควบคุมสิ่งนี้คือ **AllowAdHocSubscriptions** ผู้เช่าส่วนใหญ่จะมีการตั้งค่านี้ให้เป็นจริง ซึ่งหมายความว่า ถูกเปิดใช้งาน ถ้าคุณซื้อ Power BI ผ่านคู่ค้า อาจมีการตั้งค่าเป็นเท็จตามค่าเริ่มต้น ซึ่งหมายความว่า ถูกปิดใช้งาน

การดำเนินการขั้นตอนต่อไปนี้ คุณต้องติดตั้งเวอร์ชัน 64 บิตล่าสุดของ [Azure Active Directory Module สำหรับ Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297)

1. คุณจำเป็นต้องลงชื่อเข้าใช้ Azure Active Directory โดยใช้ข้อมูลประจำตัว Office 365 ของคุณ บรรทัดแรกจะถามข้อมูลประจำตัวของคุณ บรรทัดที่สองจะเชื่อมต่อกับ Azure Active Directory
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. ในทันทีที่คุณลงชื่อเข้าใช้ คุณสามารถออกคำสั่งต่อไปนี้เพื่อดูสิ่งที่ผู้เช่าของคุณกำหนดค่าไว้ในขณะนี้
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. คุณสามารถทำให้คำสั่งนี้เปิดใช้งาน ($true) หรือปิดใช้งาน AllowAdHocSubscriptions ($false) ได้
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> ค่าสถานะ AllowAdHocSubscriptions ถูกใช้เพื่อควบคุมความสามารถของผู้ใช้มากมายในองค์กรของคุณ รวมถึงความสามารถสำหรับผู้ใช้เพื่อลงทะเบียนสำหรับบริการ Azure Rights Management การเปลี่ยนธงนี้จะมีผลกระทบต่อความสามารถเหล่านี้ทั้งหมด
> 
> 

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>ฉันจะอนุญาตให้ผู้ใช้ปัจจุบันของฉันลงทะเบียนสำหรับ Power BI ได้อย่างไร?
เมื่อต้องการอนุญาตให้ผู้ใช้ปัจจุบันของคุณลงทะเบียนสำหรับ Power BI ได้ เรียกใช้คำสั่งที่แสดงสำหรับคำถามด้านบน แต่ส่งผ่าน true แทนจะเป็น false

การดำเนินการขั้นตอนต่อไปนี้ คุณต้องติดตั้งเวอร์ชัน 64 บิตล่าสุดของ [Azure Active Directory Module สำหรับ Windows PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=236297)

1. คุณจำเป็นต้องลงชื่อเข้าใช้ Azure Active Directory โดยใช้ข้อมูลประจำตัว Office 365 ของคุณ บรรทัดแรกจะถามข้อมูลประจำตัวของคุณ บรรทัดที่สองจะเชื่อมต่อกับ Azure Active Directory
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. ในทันทีที่คุณลงชื่อเข้าใช้ คุณสามารถออกคำสั่งต่อไปนี้เพื่อดูสิ่งที่ผู้เช่าของคุณกำหนดค่าไว้ในขณะนี้
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. คุณสามารถทำให้คำสั่งนี้เปิดใช้งาน ($true) หรือปิดใช้งาน AllowAdHocSubscriptions ($false) ได้
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> ค่าสถานะ AllowAdHocSubscriptions ถูกใช้เพื่อควบคุมความสามารถของผู้ใช้มากมายในองค์กรของคุณ รวมถึงความสามารถสำหรับผู้ใช้เพื่อลงทะเบียนสำหรับบริการ Azure Rights Management การเปลี่ยนธงนี้จะมีผลกระทบต่อความสามารถเหล่านี้ทั้งหมด
> 
> 

## <a name="administration-of-power-bi"></a>การดูแลระบบ Power BI
### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>วิธีนี้จะเปลี่ยนวิธีที่ฉันจัดการข้อมูลประจำตัวสำหรับผู้ใช้ต่าง ๆ ในองค์กรของฉันในปัจจุบันได้อย่างไร?
ถ้าองค์กรของคุณมีสภาพแวดล้อม Office 365 อยู่แล้ว และผู้ใช้ทั้งหมดในองค์กรของคุณมีบัญชีผู้ใช้ Office 365 การจัดการข้อมูลประจำตัวจะไม่เปลี่ยนแปลง

หากองค์กรของคุณมีสภาพแวดล้อม Office 365 อยู่แล้ว แต่ไม่ใช่ผู้ใช้ทั้งหมดในองค์กรของคุณที่มีบัญชีผู้ใช้ Office 365 เราจะสร้างผู้ใช้หนึ่งในผู้เช่าและมอบหมายสิทธิ์การใช้งานตามงาน หรือโรงเรียน ที่อยู่อีเมลของผู้ใช้ ซึ่งหมายความว่า จำนวนผู้ใช้ที่คุณกำลังจัดการในช่วงเวลาหนึ่ง ๆ จะขยายเพิ่มขึ้นตามผู้ใช้ในองค์กรของคุณที่ลงทะเบียนสำหรับบริการดังกล่าว

ถ้าองค์กรของคุณมีสภาพแวดล้อม Office 365 ที่เชื่อมต่อกับโดเมนอีเมลของคุณ จะไม่มีการเปลี่ยนแปลงวิธีการที่คุณจัดการข้อมูลประจำตัว ผู้ใช้จะถูกเพิ่มไปยังไดเรกทอรีผู้ใช้เฉพาะระบบคลาวด์ใหม่ และคุณจะมีตัวเลือกในการเข้าควบคุมในฐานะผู้ดูแลระบบผู้เช่าและจัดการเหล่านี้

### <a name="how-do-we-manage-power-bi"></a>เราจะจัดการกับ Power BI ได้อย่างไร?
Power BI มีพอร์ทัลผู้ดูแลระบบที่ช่วยให้คุณสามารถดูสถิติการใช้งาน มีลิงก์ไปยังศูนย์การดูแลระบบ Office 365 เพื่อจัดการผู้ใช้และกลุ่มต่าง ๆ และความสามารถในการควบคุมการตั้งค่าที่หลากหลายสำหรับผู้เช่า 

> [!NOTE]
> บัญชีของคุณจำเป็นต้องได้รับการทำเครื่องหมายให้เป็น**ผู้ดูแลระบบส่วนกลาง**ภายใน Office 365 หรือ Azure Active Directory หรือต้องได้รับการกำหนดบทบาทผู้ดูแลระบบบริการ Power BI เพื่อเข้าถึงพอร์ทัลผู้ดูแลระบบ Power BI โปรดดูที่[การทำความเข้าใจเกี่ยวกับบทบาทผู้ดูแลระบบ Power BI](service-admin-role.md)เพื่อศึกษาข้อมูลเพิ่มเติมเกี่ยวกับบทบาทผู้ดูแลระบบบริการ Power BI
> 
> 

สำหรับข้อมูลเพิ่มเติม ดู[พอร์ทัลผู้ดูแลระบบของ Power BI](service-admin-portal.md)

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>อะไรคือกระบวนการจัดการผู้เช่าที่สร้างโดย Microsoft สำหรับผู้ใช้ของฉัน?
ถ้าผู้เช่าถูกสร้างขึ้นโดย Microsoft คุณสามารถอ้างสิทธิ์ และจัดการผู้เช่านั้นได้โดยทำตามขั้นตอนเหล่านี้:

1. เข้าร่วมผู้เช่าโดยการลงทะเบียนสำหรับ Power BI โดยใช้โดเมนที่อยู่อีเมลที่ตรงกับโดเมนผู้เช่าที่คุณต้องการจัดการ ตัวอย่างเช่น ถ้าไมโครซอฟท์สร้างผู้เช่า contoso.com คุณจะต้องเข้าร่วมผู้เช่าดังกล่าวด้วยที่อยู่อีเมลที่ลงท้ายด้วย@contoso.com
2. ควบคุมการอ้างสิทธิ์ผู้ดูแลระบบโดยการยืนยันความเป็นเจ้าของโดเมน: เมื่อคุณอยู่ในผู้เช่า คุณสามารถเลื่อนระดับตัวคุณเองให้อยู่ในบทบาท*ผู้ดูแลระบบส่วนกลาง* โดยการยืนยันความเป็นเจ้าของโดเมนได้ ในการทำเช่นนั้น ทำตามขั้นตอนเหล่านี้:
   
   1. ไปที่[https://portal.office.com](https://portal.office.com)
   2. เลือกไอคอนตัวเปิดใช้แอฯที่มุมบนซ้าย แล้วเลือก**ผู้ดูแลระบบ**
   3. อ่านคำแนะนำที่หน้า**การเป็นผู้ดูแลระบบ** จากนั้น เลือก**ใช่ ฉันต้องเป็นผู้ดูแลระบบ**
      
      > [!NOTE]
      > ถ้าตัวเลือกนี้ไม่ปรากฏขึ้น หมายความว่ามีผู้ดูแลระบบ Office 365 อยู่แล้ว
      > 
      > 

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>ถ้าฉันมีหลายโดเมน ฉันสามารถควบคุมผู้เช่า Office 365 ที่มีการเพิ่มผู้ใช้เข้าไปได้อย่างไร?
ถ้าคุณไม่ทำอะไร ผู้เช่าจะถูกสร้างขึ้นสำหรับแต่ละโดเมนอีเมลของผู้ใช้และโดเมนย่อย

ถ้าคุณต้องการให้ผู้ใช้ทั้งหมดอยู่ในผู้เช่าเดียวกันโดยไม่คำนึงถึงนามสกุลที่อยู่อีเมลของพวกเขา:

* สร้างผู้เช่าเป้าหมายล่วงหน้า หรือใช้ผู้เช่าที่มีอยู่แล้ว และเพิ่มโดเมนและโดเมนย่อยทั้งหมดที่มีอยู่ที่คุณต้องการให้รวมเข้าภายในผู้เช่านั้น จากนั้น ผู้ใช้ทั้งหมดที่มีที่อยู่อีเมลที่ลงท้ายด้วยโดเมนและโดเมนย่อยเหล่านั้นจะเข้าร่วมในผู้เช่าเป้าหมายโดยอัตโนมัติเมื่อพวกเขาลงทะเบียน

> [!IMPORTANT]
> ไม่มีกลไกอัตโนมัติใดที่สนับสนุนในการย้ายผู้ใช้ไปทั่วผู้เช่าเมื่อมีการสร้างผู้ใช้ขึ้นแล้ว เมื่อต้องการเรียนรู้เกี่ยวกับการเพิ่มโดเมนสำหรับผู้เช่า Office 365 เดียว ดู[เพิ่มผู้ใช้และโดเมนของคุณไปยัง Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)
> 
> 

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>ฉันจะลบ Power BI สำหรับผู้ใช้ที่ลงทะเบียนแล้วได้อย่างไร?
ถ้าผู้ใช้ลงทะเบียนสำหรับ Power BI แล้วแต่คุณไม่ต้องการให้ผู้ใช้ดังกล่าวมีสิทธิ์เข้าถึง Power BI อีกต่อไป คุณสามารถลบสิทธิ์การใช้งาน Power BI สำหรับผู้ใช้รายนั้นได้

1. นำทางไปยังศูนย์ดูแลระบบ Office 365
2. ในแถบนำทางด้านซ้าย เลือก**ผู้ใช้** > **ผู้ใช้ที่ใช้งานอยู่**
3. ค้นหาผู้ใช้ที่คุณต้องการลบสิทธิ์การใช้งาน จากนั้นเลือกชื่อของผู้ใช้ > **แก้ไข**
4. บนหน้ารายละเอียดผู้ใช้ เลือก**สิทธิ์การใช้งาน**ในแถบนำทางด้านซ้าย
5. ยกเลิกการเลือก**Power BI (ฟรี)** หรือ**Power BI Pro** ซึ่งขึ้นอยู่กับสิทธิ์การใช้งานที่นำไปใช้กับบัญชีของพวกเขา
6. เลือก**บันทึก**

> [!NOTE]
> คุณสามารถดำเนินการจัดการสิทธิ์การใช้งานเป็นกลุ่มกับผู้ใช้ได้เช่นกัน ในการทำเช่นนั้น เลือกผู้ใช้หลายคน และเลือก**แก้ไข**
> 
> 

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>ฉันจะทราบได้อย่างไรเมื่อมีผู้ใช้ใหม่เข้าร่วมในผู้เช่าของฉัน?
ผู้ใช้ที่เข้าร่วมผู้เช่าของคุณโดยเป็นส่วนหนึ่งของโปรแกรมนี้ จะได้รับการกำหนดสิทธิ์การใช้งานเฉพาะที่คุณสามารถกรองได้ภายในพื้นที่ผู้ใช้ในแดชบอร์ดผู้ดูแลระบบของคุณ

เมื่อต้องสร้างมุมมองใหม่นี้ ในศูนย์การดูแลระบบ Office 365 ไปยัง**ผู้ใช้** > **ผู้ใช้ที่ใช้งานอยู่**และที่เมนู**เลือกมุมมอง** เลือก**มุมมองใหม่** ตั้งชื่อมุมมองของคุณใหม่ และใต้**สิทธิ์การใช้งานที่มอบหมาย** เลือก**Power BI (ฟรี)** หรือ**Power BI Pro** คุณสามารถมีได้เพียงหนึ่งสิทธิ์การใช้งานที่เลือกต่อหนึ่งมุมมอง ถ้าคุณมีทั้งสิทธิ์การใช้งาน**Power BI (ฟรี)** และ**Power BI Pro** ในองค์กรของคุณ คุณจะต้องสร้างสองมุมมอง เมื่อมีการสร้างมุมมองใหม่ คุณจะสามารถดูผู้ใช้ทั้งหมดในผู้เช่าของคุณที่มีการลงทะเบียนในโปรแกรมนี้ได้

### <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>ฉันควรเตรียมพร้อมสำหรับสิ่งอื่น ๆ เพิ่มเติมอีกหรือไม่?
คุณอาจประสบกับการเพิ่มคำขอตั้งค่ารหัสผ่านใหม่ สำหรับข้อมูลเกี่ยวกับกระบวนการนี้ ดู[การตั้งค่ารหัสผ่านของผู้ใช้ใหม่](https://support.office.com/article/Reset-a-users-password-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c)

คุณสามารถลบผู้ใช้จากผู้เช่าของคุณได้ผ่านกระบวนการมาตรฐานในศูนย์การดูแลระบบ Office 365 อย่างไรก็ตาม ถ้าผู้ใช้ดังกล่าวยังคงมีที่อยู่อีเมลที่ใช้งานอยู่จากองค์กรของคุณ ผู้ใช้เหล่านี้จะสามารถเข้าร่วมอิีกครั้งได้ เว้นแต่ว่าคุณบล็อกผู้ใช้ทั้งหมดไม่ให็เข้าร่วม

### <a name="where-is-my-power-bi-tenant-located"></a>ผู้เช่า Power BI ของฉันอยู่ที่ไหน?
เมื่อต้องการเรียนรู้วิธีการค้นหาตำแหน่งที่ตั้งของผู้เช่า Power BI ของคุณ หรือที่เรียกว่าขอบเขตข้อมูล ดู[ผู้เช่า Power BI ของฉันอยู่ที่ไหน?](service-admin-where-is-my-tenant-located.md)

### <a name="what-is-the-power-bi-sla"></a>Power BI SLA คืออะไร?
สำหรับข้อมูลเกี่ยวกับ Power BI SLA (ข้อตกลงระดับบริการ) ดูบทความ[ข้อกำหนดสิทธิ์การใช้งานและเอกสารประกอบ](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37)ในหัวข้อ**การให้สิทธิ์**ของเว็บไซต์ Microsoft Licensing

## <a name="security-in-power-bi"></a>การรักษาความปลอดภัยใน Power BI
### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Power BI ตรงตามข้อกำหนดการปฏิบัติตามกฎระเบียบของชาติ ภูมิภาค และข้อกำหนดเฉพาะสำหรับอุตสาหกรรมหรือไม่?
เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับการปฏิบัติตามกฎระเบียบ Power BI ดู[ศูนย์ความเชื่อถือ Microsoft](http://go.microsoft.com/fwlink/?LinkId=785324)

### <a name="how-does-security-work-in-power-bi"></a>การรักษาความปลอดภัยทำงานอย่างไรใน Power BI?
Power BI ถูกสร้างขึ้นมาบนพื้นฐานของ Office 365 ซึ่งจะสร้างขึ้นบนบริการ Azure เช่น Azure Active Directory สำหรับภาพรวมสถาปัตยกรรมของ Power BI ดู[การรักษาความปลอดภัย Power BI](service-admin-power-bi-security.md) 

## <a name="next-steps"></a>ขั้นตอนถัดไป
[พอร์ทัลผู้ดูแล Power BI](service-admin-portal.md)  
[ทำความเข้าใจเกี่ยวกับบทบาทผู้ดูแลระบบ Power BI](service-admin-role.md)  
[ลงชื่อสมัครใช้ Power BI แบบบริการตนเอง](service-self-service-signup-for-power-bi.md)  
[ซื้อ Power BI Pro](service-admin-purchasing-power-bi-pro.md)  
[Power BI Premium คืออะไร?](service-premium.md)  
[วิธีการซื้อ Power BI Premium](service-admin-premium-purchase.md)  
[การจัดการบัญชีผู้ใช้ Office 365](https://technet.microsoft.com/library/office-365-user-account-management.aspx)  
[การจัดการกลุ่ม Office 365](https://support.office.com/Article/Find-help-about-Groups-in-Office-365-7a9b321f-b76a-4d53-b98b-a2b0b7946de1)  
[จัดการกลุ่มของคุณใน Power BI และ Office 365](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[เอกสารทางเทคนิคของ Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)
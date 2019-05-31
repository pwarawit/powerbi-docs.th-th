---
title: การจัดการ Power BI - คำถามที่ถามบ่อย (FAQ)
description: เรียนรู้คำตอบสำหรับคำถามที่ถามบ่อยใน Power BI ลงทะเบียน จัดการผู้เช่า และการดูแลอื่น ๆ
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 2e51017333a940bd9d7838e6a903c1a66ce2e342
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100780"
---
# <a name="administering-power-bi---frequently-asked-questions-faq"></a>การจัดการ Power BI - คำถามที่ถามบ่อย (FAQ)

บทความนี้ตอบคำถามที่ถามบ่อยสำหรับการดูแลระบบ Power BI สำหรับภาพรวมของการดูแลระบบ Power BI ดู[การดูแลระบบ Power BI คืออะไร?](service-admin-administering-power-bi-in-your-organization.md)

## <a name="whats-in-this-article"></a>สิ่งที่อยู่ในบทความนี้

### <a name="sign-up-for-power-bi-section"></a>ลงทะเบียนใช้งานส่วน Power BI

* [การใช้ PowerShell](#using-powershell)
* [ผู้ใช้สามารถลงทะเบียนเข้าใช้ Power BI ได้อย่างไร?](#how-do-users-sign-up-for-power-bi)
* [ผู้ใช้แต่ละคนในองค์กรของฉันจะลงทะเบียนได้อย่างไร?](#how-do-individual-users-in-my-organization-sign-up)
* [ฉันจะป้องกันไม่ให้ผู้ใช้เข้าร่วมผู้เช่า Office 365 ของฉันที่มีอยู่ได้อย่างไร?](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)
* [ฉันจะอนุญาตให้ผู้ใช้เข้าร่วมผู้เช่า Office 365 ของฉันที่มีอยู่ได้อย่างไร?](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)
* [How do I ตรวจสอบว่า ฉันมีบล็อกในผู้เช่าได้อย่างไร](#how-do-i-check-if-i-have-the-block-on-in-the-tenant)
* [ฉันจะป้องกันไม่ให้ผู้ใช้ปัจจุบันของฉันเริ่มใช้ Power BI ได้อย่างไร?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [ฉันจะอนุญาตให้ผู้ใช้ปัจจุบันของฉันลงทะเบียนสำหรับ Power BI ได้อย่างไร?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

### <a name="administration-of-power-bi-section"></a>ส่วนการดูแลระบบของ Power BI

* [วิธีนี้จะเปลี่ยนวิธีที่ฉันจัดการข้อมูลประจำตัวสำหรับผู้ใช้ต่าง ๆ ในองค์กรของฉันในปัจจุบันได้อย่างไร?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [เราจะจัดการกับ Power BI ได้อย่างไร?](#how-do-we-manage-power-bi)
* [อะไรคือกระบวนการจัดการผู้เช่าที่สร้างโดย Microsoft สำหรับผู้ใช้ของฉัน?](#what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users)
* [ถ้าฉันมีหลายโดเมน ฉันสามารถควบคุมผู้เช่า Office 365 ที่ได้รับการเพิ่มผู้ใช้หรือไม่](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to)
* [ฉันจะลบ Power BI สำหรับผู้ใช้ที่ลงทะเบียนแล้วได้อย่างไร?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [ฉันจะทราบได้อย่างไรเมื่อมีผู้ใช้ใหม่เข้าร่วมในผู้เช่าของฉัน?](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [มีสิ่งต่าง ๆ เพิ่มเติมใด ๆ ที่ฉันควรเตรียมพร้อมสำหรับ](#are-there-any-additional-things-i-should-prepare-for)
* [ผู้เช่า Power BI ของฉันอยู่ที่ไหน?](#where-is-my-power-bi-tenant-located)
* [Power BI SLA (ข้อตกลงระดับบริการ [Service Level Agreement]) คืออะไร?](#what-is-the-power-bi-sla)
* [Power BI จัดการกับความพร้อมใช้งานสูงและการเฟลโอเวอร์ได้อย่างไร](#how-does-power-bi-handle-high-availability-and-failover)

### <a name="security-in-power-bi-section"></a>ส่วนการรักษาความปลอดภัยใน Power BI

* [Power BI ตรงตามข้อกำหนดการปฏิบัติตามกฎระเบียบของชาติ ภูมิภาค และข้อกำหนดเฉพาะสำหรับอุตสาหกรรมหรือไม่?](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)
* [การรักษาความปลอดภัยทำงานอย่างไรใน Power BI?](#how-does-security-work-in-power-bi)

## <a name="sign-up-for-power-bi"></a>ลงทะเบียนใช้งาน Power BI

### <a name="using-powershell"></a>ใช้ PowerShell

บางขั้นตอนในส่วนนี้จำเป็นต้องมีสคริปต์ Windows PowerShell หากคุณไม่คุ้นเคยกับ PowerShell เราขอแนะนำ [คู่มือเริ่มต้นใช้งาน PowerShell](http://go.microsoft.com/fwlink/p/?LinkID=286814) หากต้องการเรียกใช้สคริปต์ ก่อนอื่นให้ติดตั้งเวอร์ชัน 64 บิตล่าสุดของ [Azure Active Directory PowerShell สำหรับกราฟ](/powershell/azure/active-directory/)

### <a name="how-do-users-sign-up-for-power-bi"></a>ผู้ใช้จะลงทะเบียนสำหรับ Power BI ได้อย่างไร?

ในฐานะผู้ดูแลระบบ คุณสามารถลงทะเบียนสำหรับ Power BI ผ่านการ[เว็บไซต์ Power BI](https://powerbi.microsoft.com)หรือ[ซื้อบริการ](https://admin.microsoft.com/AdminPortal/Home#/catalog)หน้าบนศูนย์การจัดการ Microsoft 365 ได้ เมื่อผู้ดูแลระบบที่ลงทะเบียนสำหรับ Power BI พวกเขาสามารถกำหนดสิทธิ์การใช้งานสำหรับผู้ใช้ที่ควรมีสิทธิ์เข้าถึง

นอกจากนี้ ผู้ใช้งานแต่ละคนในองค์กรของคุณอาจสามารถลงทะเบียนสำหรับ Power BI ผ่าน[เว็บไซต์ Power BI](https://powerbi.microsoft.com)ได้ เมื่อผู้ใช้ในองค์กรของคุณที่ลงทะเบียนสำหรับ Power BI บริการการกำหนดสิทธิ์การใช้งาน Power BI โดยอัตโนมัติไปยังผู้ใช้ สำหรับข้อมูลเพิ่มเติม ดู[ลงทะเบียนสำหรับ Power BI เป็นรายบุคคล](service-self-service-signup-for-power-bi.md)และ[Power BI สิทธิ์การใช้งานในองค์กรของคุณ](service-admin-licensing-organization.md)

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>ผู้ใช้แต่ละคนในองค์กรของฉันจะลงทะเบียนได้อย่างไร?

มีสามสถานการณ์ที่อาจนำไปใช้กับผู้ใช้ในองค์กรของคุณ:

* **สถานการณ์ที่ 1**: องค์กรของคุณมีสภาพแวดล้อม Office 365 อยู่แล้ว และผู้ใช้ที่ลงทะเบียนใช้งาน Power BI มีบัญชี Office 365 อยู่แล้ว
    ในสถานการณ์นี้ ถ้าผู้ใช้ทำงานที่มีอยู่แล้ว หรือบัญชีโรงเรียนในผู้เช่า (ตัวอย่าง contoso.com) แต่ไม่ ได้มี Power BI, Microsoft เพียงแค่เปิดใช้งานแผนสำหรับบัญชีนั้น ผู้ใช้โดยอัตโนมัติได้รับการแจ้งเตือน ด้วยข้อมูลเกี่ยวกับวิธีการใช้บริการของ Power BI

* **สถานการณ์ที่ 2**: องค์กรของคุณมีสภาพแวดล้อม Office 365 อยู่แล้ว แต่ผู้ใช้ที่ลงทะเบียนใช้งาน Power BI ไม่มีบัญชี Office 365
    ในสถานการณ์นี้ ผู้ใช้มีที่อยู่อีเมลในโดเมนขององค์กรของคุณ (ตัวอย่าง contoso.com) แต่ยังไม่มีบัญชีผู้ใช้ Office 365 ในกรณีนี้ ผู้ใช้สามารถลงทะเบียนใช้งาน Power BI ได้ และจะได้รับบัญชีโดยอัตโนมัติ การดำเนินการนี้ช่วยให้ผู้ใช้เข้าถึงบริการของ Power BI ตัวอย่าง ถ้าพนักงานชื่อว่า Nancy ใช้ ทำงานของเธออยู่อีเมล (เช่นnancy@contoso.com) เพื่อลงทะเบียน Microsoft โดยอัตโนมัติเพิ่ม Nancy เป็นผู้ใช้ในสภาพแวดล้อม Office 365 ของ Contoso และเปิดใช้งาน Power BI สำหรับบัญชีนั้น

* **สถานการณ์ที่ 3**: องค์กรของคุณไม่มีสภาพแวดล้อม Office 365 ที่เชื่อมต่อกับโดเมนอีเมลของคุณ
    ไม่มีการดำเนินการดูแลระบบที่จำเป็นสำหรับองค์กรของคุณเพื่อใช้ประโยชน์จาก Power BI ได้ บริการการเพิ่มผู้ใช้กับไดเรกทอรีผู้ใช้ใหม่ cloud เท่านั้น คุณยังสามารถเลือกที่จะยกระดับเป็นผู้ดูแลระบบผู้เช่า และจัดการ

> [!IMPORTANT]
> หากองค์กรของคุณมีหลายโดเมนอีเมล และคุณต้องการให้ส่วนขยายที่อยู่อีเมลทั้งหมดอยู่ในผู้เช่าเดียวกัน เพิ่มโดเมนที่อยู่อีเมลทั้งหมดไปยังผู้เช่า Azure Active Directory ก่อนที่ผู้ใช้จะลงทะเบียน เมื่อคุณสร้างผู้ใช้ จะไม่มีกลไกอัตโนมัติเมื่อต้องย้ายผู้ใช้ข้ามผู้เช่า สำหรับข้อมูลเพิ่มเติมเกี่ยวกับกระบวนการนี้ ดู[ถ้าฉันมีหลายโดเมน ฉันสามารถควบคุมผู้เช่า Office 365 ที่ได้รับการเพิ่มผู้ใช้หรือไม่](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to)ในภายหลังในบทความนี้ และ[เพิ่มโดเมนใน Office 365](/office365/admin/setup/add-domain/)ได้

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>ฉันจะป้องกันไม่ให้ผู้ใช้เข้าร่วมผู้เช่า Office 365 ของฉันที่มีอยู่ได้อย่างไร?

มีหลายขั้นตอนที่คุณสามารถใช้ได้ในฐานะผู้ดูแลระบบเพื่อป้องกันไม่ให้ผู้ใช้เข้าร่วมผู้เช่า Office 365 ของคุณที่มีอยู่ได้ ถ้าคุณบล็อกการเข้าถึง ความพยายามของผู้ใช้ในการลงทะเบียนล้มเหลว และข้อความปรากฏขึ้นที่ คือสั่งให้ติดต่อผู้ดูแลระบบขององค์กรของพวกเขา คุณไม่จำเป็นต้องทำซ้ำกระบวนการนี้ถ้าคุณมีอยู่แล้วปิดใช้งานการแจกจ่ายสิทธิ์การใช้งานโดยอัตโนมัติ (ตัวอย่าง ผ่าน Office 365 สำหรับการศึกษาสำหรับนักเรียน คณะ และเจ้าหน้าที่)

ใช้สคริปต์ PowerShell ต่อไปนี้เพื่อป้องกันไม่ให้ผู้ใช้ใหม่เข้าร่วมผู้เช่าที่ได้รับการจัดการ ([เรียนรู้เพิ่มเติมเกี่ยวกับ PowerShell][1])

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Set-MsolCompanySettings -AllowEmailVerifiedUsers $false
```

> [!NOTE]
> การบล็อกการเข้าถึงจะป้องกันไม่ให้ผู้ใช้ใหม่ในองค์กรของคุณลงทะเบียนใช้งาน Power BI ผู้ใช้ที่ลงทะเบียนใช้งาน Power BI ก่อนการปิดใช้งานการลงทะเบียนใหม่สำหรับองค์กรของคุณ จะยังคงมีสิทธิ์ในการใช้งานอยู่ หากต้องการเอาผู้ใช้ออก ดู [ฉันจะลบ Power BI สำหรับผู้ใช้ที่ลงทะเบียนแล้วได้อย่างไร?](#how-do-i-remove-power-bi-for-users-that-already-signed-up) ภายหลังในบทความนี้

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>ฉันจะอนุญาตให้ผู้ใช้เข้าร่วมผู้เช่า Office 365 ของฉันที่มีอยู่ได้อย่างไร?

ใช้สคริปต์ PowerShell ต่อไปนี้เพื่อแจ้งให้ผู้ใช้ใหม่เข้าร่วมผู้เช่าที่มีการจัดการ ([เรียนรู้เพิ่มเติมเกี่ยวกับ PowerShell][1])

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Set-MsolCompanySettings -AllowEmailVerifiedUsers $true
```

### <a name="how-do-i-check-if-i-have-the-block-on-in-the-tenant"></a>How do I ตรวจสอบว่า ฉันมีบล็อกในผู้เช่าได้อย่างไร

ใช้สคริปต์ PowerShell ต่อไปนี้เพื่อตรวจสอบการตั้งค่า *AllowEmailVerifiedUsers* ควรเป็นเท็จ ([เรียนรู้เพิ่มเติมเกี่ยวกับ PowerShell][1])

```powershell
$msolcred = get-credential
connect-msolservice -credential $msolcred

Get-MsolCompanyInformation | fl allow*
```

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>ฉันจะป้องกันไม่ให้ผู้ใช้ปัจจุบันของฉันเริ่มใช้ Power BI ได้อย่างไร?

การตั้งค่า Azure AD ที่ควบคุมสิ่งนี้คือ **AllowAdHocSubscriptions** ผู้เช่าส่วนใหญ่มีซึ่งตั้งค่าเป็น true ซึ่งหมายความว่า จะเปิดใช้งาน ถ้าคุณซื้อ Power BI ผ่านคู่ค้า นี้อาจถูกตั้งค่าเป็น false ซึ่งหมายความว่า ถูกปิดใช้งาน

ใช้สคริปต์ PowerShell ต่อไปนี้เพื่อปิดใช้งานการสมัครใช้งานเฉพาะกิจ ([เรียนรู้เพิ่มเติมเกี่ยวกับ PowerShell][1])

1. ลงชื่อเข้าใช้ Azure Active Directory โดยใช้ข้อมูลประจำตัวสำหรับ Office 365 ของคุณ บรรทัดแรกของข้อความสคริปต์ PowerShell ต่อไปนี้ปรากฏขึ้นเพื่อให้คุณใส่ข้อมูลประจำตัวของคุณ บรรทัดที่สองจะเชื่อมต่อกับ Azure Active Directory

    ```powershell
     $msolcred = get-credential
     connect-msolservice -credential $msolcred
    ```

   ![สกรีนช็อตของ Azure Active Directory ลงชื่อเข้าใช้ผ่านทาง PowerShell](media/service-admin-licensing-organization/azure-ad-sign-in.png)

1. เมื่อคุณลงชื่อเข้าใช้ เรียกใช้คำสั่งต่อไปนี้เพื่อดูว่าผู้เช่าของคุณถูกตั้งค่า

    ```powershell
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
    ```

1. เรียกใช้คำสั่งต่อไปนี้เพื่อเปิดใช้งาน (`$true`) หรือปิดใช้งาน (`$false`) **AllowAdHocSubscriptions**

    ```powershell
     Set-MsolCompanySettings -AllowAdHocSubscriptions $false
    ```

> [!NOTE]
> ใช้**AllowAdHocSubscriptions**ค่าสถานะเพื่อควบคุมความสามารถของผู้ใช้หลายในองค์กรของคุณ รวมถึงความสามารถสำหรับผู้ใช้ลงทะเบียนสำหรับบริการ Azure Rights Management การเปลี่ยนธงนี้จะมีผลกระทบต่อความสามารถเหล่านี้ทั้งหมด

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>ฉันจะอนุญาตให้ผู้ใช้ปัจจุบันของฉันลงทะเบียนสำหรับ Power BI ได้อย่างไร?

เมื่อต้องการอนุญาตให้ผู้ใช้ที่มีอยู่ของคุณลงทะเบียนสำหรับ Power BI เรียกใช้คำสั่งที่แสดงสำหรับคำถามก่อนหน้า แต่ส่ง`$true`แทน`$false`ในขั้นตอนสุดท้าย

## <a name="administration-of-power-bi"></a>การดูแลระบบ Power BI

### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>วิธีนี้จะเปลี่ยนวิธีที่ฉันจัดการข้อมูลประจำตัวสำหรับผู้ใช้ต่าง ๆ ในองค์กรของฉันในปัจจุบันได้อย่างไร?

มีสามสถานการณ์ที่อาจนำไปใช้กับผู้ใช้ในองค์กรของคุณ:

* **สถานการณ์ที่ 1**: ถ้าองค์กรของคุณมีสภาพแวดล้อม Office 365 ที่มีอยู่ และผู้ใช้ทั้งหมดในองค์กรของคุณมีบัญชี Office 365 จะไม่เปลี่ยนแปลงในวิธีที่คุณจัดการข้อมูลประจำตัว

* **สถานการณ์ที่ 2**: ถ้าองค์กรของคุณมีสภาพแวดล้อม Office 365 ที่มีอยู่ แต่ผู้ใช้ไม่ทั้งหมดในองค์กรของคุณมีบัญชี Office 365 เราสร้างผู้ใช้ในผู้เช่า และมอบหมายสิทธิ์การใช้งานที่ยึดตามการทำงานของผู้ใช้หรือที่อยู่อีเมลของโรงเรียน

    ผล จำนวนผู้ใช้ที่คุณกำลังจัดการในช่วงเวลาหนึ่ง ๆ ขยาย ตามผู้ใช้ในองค์กรของคุณลงทะเบียนสำหรับบริการ

* **สถานการณ์ที่ 3**: ถ้าองค์กรของคุณไม่มีสภาพแวดล้อม Office 365 ที่เชื่อมต่อกับโดเมนของคุณอีเมล จะไม่เปลี่ยนแปลงในวิธีที่คุณจัดการข้อมูลประจำตัว

    บริการการเพิ่มผู้ใช้กับไดเรกทอรีผู้ใช้ใหม่ cloud เท่านั้น ยัง คุณสามารถเลือกที่จะยกระดับเป็นผู้ดูแลระบบผู้เช่า และจัดการ

### <a name="how-do-we-manage-power-bi"></a>เราจะจัดการกับ Power BI ได้อย่างไร?

Power BI มีพอร์ทัลของผู้ดูแลระบบที่ช่วยให้คุณสามารถดูสถิติการใช้งาน มีลิงก์ไปยังศูนย์การจัดการ Microsoft 365 เพื่อจัดการผู้ใช้และกลุ่ม และมีความสามารถในการควบคุมการตั้งค่าผู้เช่าจำนวนมาก

เมื่อต้องใช้พอร์ทัลผู้ดูแลระบบ Power BI คุณต้องมาทำเครื่องหมายเป็นบัญชีของคุณ**ผู้ดูแลระบบส่วนกลาง**ภายใน Office 365 หรือ Azure Active Directory หรือบุคคลอื่นต้องกำหนดบทบาทผู้ดูแลระบบบริการ Power BI ให้บัญชีผู้ใช้ของคุณ สำหรับข้อมูลเพิ่มเติม ดู[ทำความเข้าใจเกี่ยวกับบทบาทผู้ดูแลระบบ Power BI](service-admin-role.md)และ[พอร์ทัลผู้ดูแลระบบ Power BI](service-admin-portal.md)

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>อะไรคือกระบวนการจัดการผู้เช่าที่สร้างโดย Microsoft สำหรับผู้ใช้ของฉัน?

เมื่อผู้ใช้แบบบริการตนเองที่ลงทะเบียนสำหรับบริการระบบคลาวด์ที่ใช้ Azure AD บริการเพิ่มวิดีโอลงไม่มีการจัดการ Azure AD ไดเรกทอรียึดตามโดเมนอีเมลของของพวกเขา คุณสามารถอ้างสิทธิ์ และจัดการผู้เช่าที่ผู้อื่นสร้างขึ้นโดยใช้กระบวนการที่เรียกว่าการ*takeover ผู้ดูแลระบบ*ได้ ชนิดของ takeover ที่คุณทำขึ้นอยู่กับว่า มีที่มีอยู่ได้รับการจัดการผู้เช่าที่เชื่อมโยงกับโดเมนของคุณ:

* ใช้*การครอบครองจากภายใน*เพื่อสร้างการจัดการผู้เช่าใหม่สำหรับโดเมน

* ใช้ *การครอบครองจากภายนอก* ในการย้ายโดเมนไปยังผู้เช่าซึ่งยังใช้งานอยู่และมีการจัดการ

สำหรับข้อมูลเพิ่มเติม ดู[ครองไดเรกทอรีที่ไม่มีการจัดการเป็นผู้ดูแลระบบใน Azure Active Directory](/azure/active-directory/users-groups-roles/domains-admin-takeover)

เมื่อคุณทำการเข้าครองภายนอก บริการจะวาง Power BI ที่ถูกสร้างขึ้นก่อน takeover ในเนื้อหา[พื้นที่เก็บถาวรของ Power BI](service-admin-power-bi-archived-workspace.md) คุณจะต้องดำเนินการย้ายเนื้อหาที่คุณต้องการใช้กับผู้เช่ารายใหม่ด้วยตัวคุณเอง

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-get-added-to"></a>ถ้าฉันมีหลายโดเมน ฉันสามารถควบคุมผู้เช่า Office 365 ที่ได้รับการเพิ่มผู้ใช้หรือไม่

ถ้าคุณไม่ต้องทำอะไร บริการสร้างผู้เช่าสำหรับแต่ละโดเมนอีเมลของผู้ใช้และโดเมนย่อย ถ้าคุณต้องการให้ผู้ใช้ทั้งหมดอยู่ในผู้เช่าเดียวกันโดยไม่คำนึงถึงนามสกุลที่อยู่อีเมลของพวกเขา: สร้างผู้เช่าเป้าหมายล่วง หรือใช้ผู้เช่าที่มีอยู่ แล้ว เพิ่มโดเมนที่มีอยู่และโดเมนย่อยที่คุณต้องรวมภายในผู้เช่านั้นทั้งหมด ผู้ใช้ทุกคน มีที่อยู่อีเมลที่ลงท้าย ด้วยโดเมนและโดเมนย่อยเหล่านั้นโดยอัตโนมัติเข้าร่วมผู้เช่าเป้าหมายเมื่อพวกเขาลงทะเบียน

> [!IMPORTANT]
> เมื่อคุณสร้างผู้ใช้ ไม่มีกลไกอัตโนมัติไม่ได้รับการสนับสนุนสำหรับการย้ายผู้ใช้ข้ามผู้เช่า เมื่อต้องการเรียนรู้เกี่ยวกับการเพิ่มโดเมนสำหรับผู้เช่า Office 365 เดียว ดู[เพิ่มผู้ใช้และโดเมนของคุณไปยัง Office 365](/office365/admin/setup/add-domain/)

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>ฉันจะลบ Power BI สำหรับผู้ใช้ที่ลงทะเบียนแล้วได้อย่างไร?

หากผู้ใช้กำลังลงทะเบียนใช้งาน Power BI แต่คุณไม่ต้องการให้ผู้ใช้ดังกล่าวมีสิทธิ์เข้าถึง Power BI อีกต่อไป คุณสามารถลบสิทธิ์การใช้งาน Power BI สำหรับผู้ใช้รายนั้นได้

1. ไปที่ [ศูนย์การจัดการ Microsoft 365](https://admin.microsoft.com/AdminPortal/Home#/homepage)

1. ในแถบนำทางด้านซ้าย เลือก**ผู้ใช้** > **ผู้ใช้ที่ใช้งานอยู่**

1. ค้นหาผู้ใช้ที่คุณต้องการลบสิทธิ์การใช้งาน จากนั้นเลือกชื่อของผู้ใช้

    คุณสามารถดำเนินการจัดการสิทธิ์การใช้งานเป็นกลุ่มกับผู้ใช้ได้เช่นกัน หากต้องการดำเนินการ ให้เลือกผู้ใช้หลายคน และเลือก **แก้ไขสิทธิ์การใช้งานผลิตภัณฑ์**

1. บนหน้ารายละเอียดผู้ใช้ถัดจาก **สิทธิ์การใช้งานผลิตภัณฑ์** ให้เลือก **แก้ไข**

1. ขึ้นอยู่กับว่าสิทธิ์การใช้งานคุณสามารถใช้กับบัญชีของพวกเขา ตั้งค่า**Power BI (ฟรี)** หรือ**Power BI Pro**เพื่อ**ปิด**

1. เลือก**บันทึก**

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>ฉันจะทราบได้อย่างไรเมื่อมีผู้ใช้ใหม่เข้าร่วมในผู้เช่าของฉัน?

ผู้ใช้ที่เข้าร่วมผู้เช่าของคุณเป็นส่วนหนึ่งของโปรแกรมนี้ ได้รับมอบหมายเฉพาะสิทธิ์การใช้งานที่คุณสามารถกรองได้ภายในบานหน้าต่างผู้ใช้ที่ใช้งานของคุณในแดชบอร์ดผู้ดูแลระบบ หากต้องการสร้างมุมมองนี้ใหม่ ให้ปฏิบัติตามขั้นตอนเหล่านี้

1. ไปที่ [ศูนย์การจัดการ Microsoft 365](https://admin.microsoft.com/AdminPortal/Home#/homepage)

1. ในแถบนำทางด้านซ้าย เลือก**ผู้ใช้** > **ผู้ใช้ที่ใช้งานอยู่**

1. บนเมนู **มุมมอง** เลือก **เพิ่มมุมมองแบบกำหนดเอง**

1. ตั้งชื่อมุมมองใหม่ของคุณ และใต้ **สิทธิ์การใช้งานที่มอบหมาย** ให้เลือก **Power BI (ฟรี)** หรือ **Power BI Pro**

    คุณสามารถมีได้เพียงหนึ่งสิทธิ์การใช้งานที่เลือกต่อหนึ่งมุมมอง หากคุณมีทั้งสิทธิ์การใช้งาน **Power BI (ฟรี)** และ **Power BI Pro** ในองค์กรของคุณ คุณจะต้องสร้างสองมุมมอง

1. ใส่เงื่อนไขอื่นที่คุณต้องการ จากนั้นเลือก **เพิ่ม**

1. หลังจากที่คุณสร้างมุมมองใหม่ จะพร้อมใช้งานจาก**มุมมอง**เมนู

### <a name="are-there-any-additional-things-i-should-prepare-for"></a>มีสิ่งต่าง ๆ เพิ่มเติมใด ๆ ที่ฉันควรเตรียมพร้อมสำหรับ

คุณอาจประสบกับการเพิ่มคำขอตั้งค่ารหัสผ่านใหม่ สำหรับข้อมูลเกี่ยวกับกระบวนการนี้ ดู[รีเซ็ตรหัสผ่านของผู้ใช้](/office365/admin/add-users/reset-passwords)

คุณสามารถลบผู้ใช้จากผู้เช่าของคุณได้ผ่านกระบวนการมาตรฐานในศูนย์การดูแลระบบ Microsoft 365 อย่างไรก็ตาม หากผู้ใช้ดังกล่าวยังคงมีที่อยู่อีเมลที่ใช้งานอยู่จากองค์กรของคุณ ผู้ใช้เหล่านี้จะสามารถเข้าร่วมอีกครั้งได้ เว้นแต่ว่าคุณจะบล็อกผู้ใช้ทั้งหมดไม่ให้เข้าร่วม

### <a name="where-is-my-power-bi-tenant-located"></a>ผู้เช่า Power BI ของฉันอยู่ที่ไหน?

สำหรับข้อมูลเกี่ยวกับภูมิภาคข้อมูลผู้เช่า Power BI ของคุณอยู่ใน ดู[ผู้เช่า Power BI ของฉันอยู่ที่ไหน?](service-admin-where-is-my-tenant-located.md)

### <a name="what-is-the-power-bi-sla"></a>Power BI SLA คืออะไร?

สำหรับข้อมูลเกี่ยวกับ Power BI SLA (ข้อตกลงระดับบริการ), ดู[ข้อกำหนดสิทธิ์การใช้งานและเอกสารประกอบ](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37)บทความในการ**Licensing**ส่วนของเว็บไซต์ Microsoft Licensing

### <a name="how-does-power-bi-handle-high-availability-and-failover"></a>Power BI จัดการกับความพร้อมใช้งานสูงและการเฟลโอเวอร์ได้อย่างไร

สำหรับข้อมูลเกี่ยวกับความพร้อมใช้งานสูงและย้ายโหนดใน ดู[Power BI สูงความพร้อมใช้งาน ย้ายโหนดใน และความเสียหายกู้คืนถามที่ถามบ่อย](service-admin-failover.md)

## <a name="security-in-power-bi"></a>การรักษาความปลอดภัยใน Power BI

### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Power BI ตรงตามข้อกำหนดการปฏิบัติตามกฎระเบียบของชาติ ภูมิภาค และข้อกำหนดเฉพาะสำหรับอุตสาหกรรมหรือไม่?

เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับการปฏิบัติตามกฎระเบียบ Power BI ดู[ศูนย์ความเชื่อถือ Microsoft](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/default.aspx)

### <a name="how-does-security-work-in-power-bi"></a>การรักษาความปลอดภัยทำงานอย่างไรใน Power BI?

Microsoft สร้าง Power BI บนพื้นฐานของ Office 365 ซึ่งจะสร้างบนบริการ Azure เช่น Azure Active Directory สำหรับภาพรวมสถาปัตยกรรมของ Power BI ดู[การรักษาความปลอดภัย Power BI](service-admin-power-bi-security.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป

[พอร์ทัลผู้ดูแล Power BI](service-admin-portal.md)  
[ทำความเข้าใจเกี่ยวกับบทบาทผู้ดูแลระบบ Power BI](service-admin-role.md)  
[ลงชื่อสมัครใช้ Power BI แบบบริการตนเอง](service-self-service-signup-for-power-bi.md)  
[ซื้อ Power BI Pro](service-admin-purchasing-power-bi-pro.md)  
[Power BI Premium คืออะไร?](service-premium-what-is.md)  
[วิธีการซื้อ Power BI Premium](service-admin-premium-purchase.md)  
[เอกสารทางเทคนิคของ Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  
[จัดการกลุ่มของคุณใน Power BI และ Office 365](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[การจัดการบัญชีผู้ใช้ Office 365](/office365/servicedescriptions/office-365-platform-service-description/user-account-management/)  
[การจัดการกลุ่ม Office 365](/office365/admin/email/create-edit-or-delete-a-security-group/)  

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](http://community.powerbi.com/)

[1]: https://docs.microsoft.com/powershell/scripting/overview
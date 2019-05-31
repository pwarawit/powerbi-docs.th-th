---
title: ใช้อยู่อีเมลสำรอง
description: ใช้อยู่อีเมลสำรอง
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/23/2019
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 88432f55fc8cfeefa07b66ea68437bbb23f12531
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906655"
---
# <a name="use-an-alternate-email-address"></a>ใช้อยู่อีเมลสำรอง

เมื่อคุณลงทะเบียนใช้งาน Power BI คุณต้องให้ที่อยู่อีเมล โดยค่าเริ่มต้น Power BI จะใช้ที่อยู่นี้เพื่อส่งอัปเดตเกี่ยวกับกิจกรรมในบริการ ตัวอย่างเช่น เมื่อมีบุคคลแจ้งเชิญเพื่อใช้งานร่วมกัน ก็จะส่งไปยังที่อยู่นี้

ในบางกรณี คุณอาจต้องการส่งอีเมลเหล่านี้ไปยังที่อยู่อีเมลสำรองแทนที่อยู่อีเมลที่ใช้ลงทะเบียน บทความนี้จะอธิบายวิธีการระบุที่อยู่อีเมลสำรองใน Office 365 และ ใน PowerShell บทความนี้ยังอธิบายวิธีแก้ไขอยู่อีเม Azure Active Directory (Azure AD)

> [!NOTE]
> การระบุที่อยู่สำรองจะไม่มีผลต่อที่อยู่อีเมลที่ Power BI ใช้สำหรับอัปเดตบริการ, จดหมายข่าว และการติดต่อสื่อสารด้านการส่งเสริมการขายอื่น ๆ ติดต่อสื่อสารเหล่านั้นจะเสมอถูกส่งไปยังที่อยู่อีเมลที่คุณใช้เมื่อคุณลงทะเบียนสำหรับ Power BI

## <a name="use-office-365"></a>ใช้ Office 365

หากต้องการระบุที่อยู่สำรองใน Office 365 ให้ปฏิบัติตามขั้นตอนเหล่านี้

1. เปิด [หน้าข้อมูลส่วนบุคคล Office 365](https://portal.office.com/account/#personalinfo) ถ้าแอพร้อมท์ให้คุณ ลงชื่อเข้าใช้ ด้วยที่อยู่อีเมลและรหัสผ่านที่คุณใช้สำหรับ Power BI

1. บนเมนูทางด้านซ้าย เลือก **ข้อมูลส่วนบุคคล**

1. ในส่วน **รายละเอียดการติดต่อ** เลือก **แก้ไข**

    ถ้าคุณไม่สามารถแก้ไขรายละเอียดของคุณ ซึ่งหมายความว่า ผู้ดูแลระบบ Office 365 ของคุณจัดการที่อยู่อีเมลของคุณ ติดต่อผู้ดูแลระบบของคุณเพื่ออัปเดตที่อยู่อีเมลของคุณ

    ![รายละเอียดการติดต่อ](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)

1. ในการ**อีเมลสำรอง**เขตข้อมูล ใส่อยู่อีเมลที่คุณต้องการให้ Office 365 เพื่อใช้การอัปเดต Power BI

## <a name="use-powershell"></a>ใช้ PowerShell

หากต้องระบุที่อยู่สำรองใน PowerShell ให้ใช้คำสั่ง [Set-AzureADUser](/powershell/module/azuread/set-azureaduser/)

```powershell
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

## <a name="email-address-resolution-in-azure-ad"></a>การแก้ไขปัญหาที่อยู่อีเมลใน Azure AD

การจับภาพ Azure AD โทเค็นฝังสำหรับ Power BI คุณสามารถใช้หนึ่งในสามชนิดของที่อยู่อีเมล:

* อยู่อีเมลหลักที่เชื่อมโยงกับบัญชี Azure AD ของผู้ใช้

* ที่อยู่อีเมล UserPrincipalName (UPN)

* แอตทริบิวต์แบบอาร์เรย์อื่น ๆ ที่เก็บ *ที่อยู่อีเมล*

Power BI จะเลือกว่าจะใช้อีเมลใดจากลำดับต่อไปนี้:

1. หากแอตทริบิวต์จดหมายในออบเจ็กต์ผู้ใช้ Azure AD แสดงขึ้น แสดงว่า Power BI ใช้แอตทริบิวต์จดหมายนั้นสำหรับที่อยู่อีเมล

1. หากอีเมล UPN *ไม่* ใช่โดเมนที่อยู่อีเมล **\*onmicrosoft.com** (ข้อมูลหลังจากสัญลักษณ์ "\@") Power BI จะใช้แอตทริบิวต์จดหมายนั้นสำหรับอยู่อีเมล

1. ถ้าตัว*อื่น ๆ ที่อยู่อีเม*แอตทริบิวต์อาร์เรย์ในวัตถุผู้ใช้ Azure AD อยู่ จาก นั้น Power BI ใช้อีเมลแรกในรายการนั้น (เนื่องจากสามารถมีรายการอีเมลในแอตทริบิวต์นี้)

1. ถ้าไม่มีเงื่อนไขข้างต้นปรากฏ Power BI ใช้อยู่ UPN

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)
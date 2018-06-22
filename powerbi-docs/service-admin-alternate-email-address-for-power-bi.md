---
title: การใช้ที่อยู่อีเมลสำรอง
description: การใช้ที่อยู่อีเมลสำรอง
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/08/2018
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 5013c70e4d3998eb39e0de2a92f890417175fd62
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34240917"
---
# <a name="using-an-alternate-email-address"></a>การใช้ที่อยู่อีเมลสำรอง
ตามปกติแล้ว ที่อยู่อีเมลที่คุณใช้ในการลงทะเบียนเข้าใช้ Power BI จะเป็นที่อยู่อีเมลที่จะแจ้งให้คุณทราบถึงกิจกรรมต่าง ๆใน Power BI  ตัวอย่างเช่น เมื่อมีใครบางคนแจ้งเชิญเพื่อใช้งานร่วมกัน ก็จะส่งไปยังที่อยู่นี้

แต่บางครั้ง คุณอาจต้องการให้อีเมลเหล่านี้ส่งไปยังอยู่อีเมลสำรอง แทนที่จะเป็นอีเมลที่เคยใช้ลงทะเบียนกับ Power BI

## <a name="updating-through-office-365-personal-info-page"></a>การปรับปรุงผ่านทางหน้าข้อมูลส่วนบุคคลใน Office 365
1. ไปที่ [หน้าข้อมูลส่วนบุคคล Office 365](https://portal.office.com/account/#personalinfo) ของคุณ  ให้ลงชื่อเข้าใช้ด้วย ที่อยู่อีเมลและรหัสผ่านที่คุณใช้สำหรับ Power BI หากมีการร้องขอ
2. คลิกที่ลิงก์ แก้ไข ในรายละเอียดผู้ติดต่อ  
   
   > [!NOTE]
   > ถ้าคุณไม่เห็นลิงก์แก้ไข แสดงว่า ที่อยู่อีเมลของคุณ จัดการโดยผู้ดูแล Office 365 ของคุณ คุณต้องติดต่อพวกเขาเพื่อปรับปรุงที่อยู่อีเมลของคุณ
   > 
   > 
   
   ![](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)
3. ในช่องอีเมลสำรอง ใส่อยู่อีเมลที่คุณต้องการให้ Power BI จะส่งข้อความแจ้งให้ทราบ

> [!NOTE]
> การเปลี่ยนการตั้งค่านี้ จะไม่มีผลต่อที่อยู่อีเมล ที่ใช้ส่งการอัปเดตบริการ จดหมายข่าว และข้อความส่งเสริมการขายอื่น ๆ  ทั้งหมดนั้น จะยังคงส่งไปยังที่อยู่อีเมลที่คุณลงใช้ทะเบียน Power BI ครั้งแรกเสมอ
> 
> 

## <a name="updating-through-azure-active-directory"></a>การปรับปรุงผ่าน Azure Active Directory
เมื่อต้องการโทเค็น Active Azure Directory (AAD) สำหรับใช้ฝัง Power BI คุณสามารถใช้อีเมลที่แตกต่างกันสามชนิด อันได้แก่:

* ที่อยู่อีเมลหลักที่เชื่อมโยงกับบัญชี AAD ของผู้ใช้
* ที่อยู่อีเมล UserPrincipalName (UPN)
* ที่อยู่อีเมล ที่เก็บในแอตทริบิวต์แบบอาร์เรย์ "อื่น ๆ"

Power BI เลือกว่าจะใช้อีเมลไหนจากเงื่อนไขดังต่อไปนี้:
1.  ถ้าในวัตถุข้อมูลผู้ใช้ของผู้เช่า AAD มีแอตทริบิวต์จดหมายแล้ว Power BI จะใช้แอตทริบิวต์จดหมายนั้นสำหรับที่อยู่อีเมล
2.  ถ้าอีเมล UPN *ไม่*เป็นที่อยู่อีเมลในโดเมน  **\*onmicrosoft.com** (ข้อมูลที่อยู่หลังสัญลักษณ์ "\@") Power BI จะใช้แอตทริบิวต์จดหมายนั้นสำหรับที่อยู่อีเมล์
3.  ถ้ามี แอตทริบิวต์แบบอาร์เรย์ เก็บอีเมล "อื่น ๆ" ในวัตถุข้อมูลผู้ใช้ AAD จะใช้อีเมลแรกในรายการนั้น (เนื่องจากสามารถมีอีเมลได้หลายอีเมลในแอตทริบิวต์นี้)
4. ถ้าไม่ตรงกับเงื่อนไขทั้งหมดข้างบน จะใช้ที่อยู่ UPN

## <a name="updating-with-powershell"></a>การปรับปรุงด้วย PowerShell
คุณสามารถปรับปรุงที่อยู่อีเมลสำรองได้อีกวิธีหนึ่ง โดยผ่านทาง PowerShell สำหรับ Azure Active Directory ซึ่งสามารถทำได้ด้วยคำสั่ง [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)

```
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

สำหรับข้อมูลเพิ่มเติม ดูที่ [Azure Active Directory PowerShell เวอร์ชัน 2](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)

ถ้าคุณมีคำถามเพิ่มเติม [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


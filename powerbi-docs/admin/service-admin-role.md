---
title: ทำความเข้าใจเกี่ยวกับบทบาทผู้ดูแลระบบบริการของ Power BI
description: บทความนี้อธิบายถึงผู้ดูแลระบบบริการของ Power BI และบทบาทเฉพาะที่มีสิทธิ์ระดับผู้ดูแล
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 01/02/2020
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: a5a956f65943f557d21a942bde4be1de40a84692
ms.sourcegitcommit: 6ba7cc9afaf91229f717374bc0c12f0b8201d15e
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/16/2020
ms.locfileid: "83438211"
---
# <a name="understanding-power-bi-service-administrator-roles"></a>ทำความเข้าใจเกี่ยวกับบทบาทผู้ดูแลระบบบริการของ Power BI

ในการดูแลระบบผู้เช่า Power BI คุณต้องเป็นหนึ่งในบทบาทต่อไปนี้: ผู้ดูแลระบบ Power BI ผู้ดูแลระบบ Power Platform หรือผู้ดูแลระบบส่วนกลาง Microsoft 365 ผู้ดูแลระบบการจัดการผู้ใช้ Microsoft 365 กำหนดผู้ใช้ไปยังบทบาทผู้ดูแลระบบ Power BI หรือผู้ดูแลระบบ Power Platform ในศูนย์การจัดการ Microsoft 365 หรือโดยใช้สคริปต์ PowerShell สำหรับข้อมูลเพิ่มเติม โปรดดู [การกำหนดบทบาทให้กับบัญชีผู้ใช้ด้วย PowerShell](/office365/enterprise/powershell/assign-roles-to-user-accounts-with-office-365-powershell)

ผู้ใช้ในบทบาทผู้ดูแลระบบ Power BI และผู้ดูแลระบบ Power Platform สามารถควบคุมผู้เช่า และคุณลักษณะการจัดการผู้เช่าใน Power BI ได้เต็มรูปแบบ ยกเว้นสิทธิ์การใช้งาน ทันทีที่ผู้ใช้ถูกกำหนดสิทธิ์ ผู้ใช้จะสามารถเข้าถึง [พอร์ทัลผู้ดูแล Power BI](service-admin-portal.md) ได้ ในส่วนนั้น ผู้ใช้จะสามารถเข้าถึงการวัดปริมาณการใช้งานของผู้เช่า และสามารถควบคุมการใช้งานคุณลักษณะ Power BI ของผู้เช่าอีกได้ด้วย บทบาทผู้ดูแลระบบเหล่านี้เหมาะสำหรับผู้ใช้ที่จำเป็นต้องเข้าถึงพอร์ทัลผู้ดูแลระบบ Power BI โดยไม่ต้องให้สิทธิ์เข้าถึงการจัดการทั้งหมดของ Microsoft 365 แก่ผู้ใช้เหล่านั้น

> [!NOTE]
> ในเอกสารประกอบของ Power BI "ผู้ดูแลระบบ Power BI" หมายถึงผู้ใช้ในบทบาทผู้ดูแลระบบ Power BI หรือ Power Platform อย่างใดอย่างหนึ่ง เอกสารประกอบจะทำให้ชัดเจนขึ้นเมื่อจำเป็นต้องมีบทบาทผู้ดูแลระบบส่วนกลางของ Microsoft 365 สำหรับงาน

## <a name="limitations-and-considerations"></a>ข้อจำกัดและข้อควรพิจารณา

บทบาทผู้ดูแลระบบบริการของ Power BI และผู้ดูแลระบบ Power Platform ไม่มีความสามารถดังต่อไปนี้:

* ความสามารถในการแก้ไขผู้ใช้และสิทธิการใช้งานภายในศูนย์การจัดการ Microsoft 365

* การเข้าถึงบันทึกการตรวจสอบ สำหรับข้อมูลเพิ่มเติมดู [ติดตามกิจกรรมของผู้ใช้ใน Power BI](service-admin-auditing.md)

ความสามารถเหล่านี้จำเป็นต้องมีบทบาทผู้ดูแลระบบส่วนกลาง Microsoft 365

## <a name="assign-users-to-an-admin-role-in-the-microsoft-365-admin-center"></a>กำหนดผู้ใช้ให้กับบทบาทผู้ดูแลระบบในศูนย์การจัดการ Microsoft 365

หากต้องการกำหนดผู้ใช้ลงในบทบาทผู้ดูแลระบบในศูนย์การจัดการ Microsoft 365 ให้ปฏิบัติตามขั้นตอนเหล่านี้

1. ใน[ศูนย์การจัดการ Microsoft 365](https://portal.office.com/adminportal/home#/homepage)**ให้เลือก** >  **ผู้ใช้ผู้ใช้ที่ใช้งานอยู่**

    ![ศูนย์การจัดการ Microsoft 365](media/service-admin-role/powerbi-admin-users.png)

1. เลือกผู้ใช้ที่คุณต้องการกำหนดบทบาทให้

1. ภายใต้ **บทบาท** เลือก **จัดการบทบาท**

    ![จัดการบทบาท](media/service-admin-role/powerbi-admin-edit-roles.png)

1. ขยาย **แสดงทั้งหมดตามประเภท** จากนั้นเลือก **ผู้ดูแลระบบ Power BI** หรือ **ผู้ดูแลระบบ Power Platform**

    ![เลือกบทบาทผู้ดูแลระบบ](media/service-admin-role/powerbi-admin-role.png)

1. เลือก **บันทึกการเปลี่ยนแปลง**

## <a name="assign-users-to-the-admin-role-with-powershell"></a>กำหนดบทบาทผู้ดูแลระบบแก่ผู้ใช้ด้วย PowerShell

นอกจากนี้คุณยังสามารถกำหนดบทบาทแก่ผู้ใช้โดยใช้ PowerShell ได้เช่นกัน จัดการผู้ใช้ใน Azure Active Directory (Azure AD) หากคุณยังไม่มีโมดูล Azure AD PowerShell ให้ [ดาวน์โหลด และติดตั้งเวอร์ชันล่าสุด](https://www.powershellgallery.com/packages/AzureAD/)

1. ขั้นแรก เชื่อมต่อกับ Azure AD:
   ```
   PS C:\Windows\system32> Connect-AzureAD
   ```

1. ขั้นต่อไปคุณจะต้องได้รับ **ObjectId** สำหรับบทบาท **ผู้ดูแลบริการของ Power BI** คุณสามารถเรียกใช้ [Get-AzureADDirectoryRole](/powershell/module/azuread/get-azureaddirectoryrole) เพื่อรับ **ObjectId**

    ```
    PS C:\Windows\system32> Get-AzureADDirectoryRole

    ObjectId                             DisplayName                        Description
    --------                             -----------                        -----------
    00f79122-c45d-436d-8d4a-2c0c6ca246bf Power BI Service Administrator     Full access in the Power BI Service.
    250d1222-4bc0-4b4b-8466-5d5765d14af9 Helpdesk Administrator             Helpdesk Administrator has access to perform..
    3ddec257-efdc-423d-9d24-b7cf29e0c86b Directory Synchronization Accounts Directory Synchronization Accounts
    50daa576-896c-4bf3-a84e-1d9d1875c7a7 Company Administrator              Company Administrator role has full access t..
    6a452384-6eb9-4793-8782-f4e7313b4dfd Device Administrators              Device Administrators
    9900b7db-35d9-4e56-a8e3-c5026cac3a11 AdHoc License Administrator        Allows access manage AdHoc license.
    a3631cce-16ce-47a3-bbe1-79b9774a0570 Directory Readers                  Allows access to various read only tasks in ..
    f727e2f3-0829-41a7-8c5c-5af83c37f57b Email Verified User Creator        Allows creation of new email verified users.
    ```

    ในกรณีนี้ **ObjectId** ของบทบาทคือ 00f79122-c45d-436d-8d4a-2c0c6ca246bf

1. ถัดไป รับ **ObjectId** ของผู้ใช้ คุณสามารถหาได้ด้วย [Get-AzureADUser](/powershell/module/azuread/get-azureaduser)

    ```
    PS C:\Windows\system32> Get-AzureADUser -ObjectId 'tim@contoso.com'

    ObjectId                             DisplayName UserPrincipalName      UserType
    --------                             ----------- -----------------      --------
    6a2bfca2-98ba-413a-be61-6e4bbb8b8a4c Tim         tim@contoso.com        Member
    ```

1. เพื่อเพิ่มสมาชิกลงในบทบาท เรียกใช้ [AzureADDirectoryRoleMember](/powershell/module/azuread/add-azureaddirectoryrolemember)

    | พารามิเตอร์ | คำอธิบาย |
    | --- | --- |
    | ObjectId |ObjectId ของบทบาท |
    | RefObjectId |ObjectId ของสมาชิก |

    ```powershell
    Add-AzureADDirectoryRoleMember -ObjectId 00f79122-c45d-436d-8d4a-2c0c6ca246bf -RefObjectId 6a2bfca2-98ba-413a-be61-6e4bbb8b8a4c
    ```

## <a name="next-steps"></a>ขั้นตอนถัดไป

[การดูแล Power BI ในองค์กรของคุณ](service-admin-administering-power-bi-in-your-organization.md)  
[พอร์ทัลผู้ดูแล Power BI](service-admin-portal.md)  

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
---
title: การฝังเนื้อหา Power BI ด้วยบริการหลักและความลับของแอปพลิเคชัน
description: เรียนรู้วิธีการรับรองความถูกต้องสำหรับการวิเคราะห์แบบฝังตัวโดยใช้บริการแอปพลิเคชัน Azure Active Directory หลักและข้อมูลลับของแอปพลิเคชัน
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.custom: ''
ms.date: 05/12/2020
ms.openlocfilehash: da7db691628b0fbcfd42d6a35f99b18b4cfdcc88
ms.sourcegitcommit: cd64ddd3a6888253dca3b2e3fe24ed8bb9b66bc6
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/03/2020
ms.locfileid: "84315874"
---
# <a name="embed-power-bi-content-with-service-principal-and-an-application-secret"></a>การฝังเนื้อหา Power BI ด้วยบริการหลักและความลับของแอปพลิเคชัน

[!INCLUDE[service principal overview](../../includes/service-principal-overview.md)]

บทความนี้อธิบายการรับรองความถูกต้องของบริการหลักโดยใช้ *รหัสแอปพลิเคชัน* และ *ความลับของแอปพลิเคชัน*

>[!NOTE]
>เราขอแนะนำให้คุณรักษาความปลอดภัยบริการหลังบ้านของคุณโดยใช้ใบรับรอง แทนที่จะเป็นคีย์ลับ
>* [เรียนรู้เพิ่มเติมเกี่ยวกับการรับโทเค็นการเข้าถึงจาก Azure AD โดยใช้คีย์ลับหรือใบรับรอง](https://docs.microsoft.com/azure/architecture/multitenant-identity/client-assertion)
>* [การฝังเนื้อหา Power BI ด้วยบริการหลักและใบรับรอง](embed-service-principal-certificate.md)

## <a name="method"></a>วิธี

เมื่อต้องการใช้บริการหลักและรหัสแอปพลิเคชันที่มีการวิเคราะห์แบบฝังตัว ให้ทำตามขั้นตอนเหล่านี้:

1. สร้าง [แอป Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-application-management)

    1. สร้างความลับของแอป Azure AD
    
    2. รับ *รหัสแอปพลิเคชัน* และ *ความลับของแอปพลิเคชัน* ของแอป

    >[!NOTE]
    >ขั้นตอนเหล่านี้จะอธิบายไว้ใน **ขั้นตอนที่ 1** สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการสร้างแอป Azure AD โปรดดูบทความ [สร้างแอป Azure AD](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal)

2. สร้างกลุ่มความปลอดภัย Azure AD

3. เปิดใช้งานการตั้งค่าการจัดการบริการของ Power BI

4. เพิ่มบริการหลักไปยังพื้นที่ทำงานของคุณ

5. ฝังเนื้อหาของคุณ

> [!IMPORTANT]
> เมื่อคุณเปิดใช้งานบริการหลักที่จะใช้กับ Power BI สิทธิ์ AD ของแอปพลิเคชันไม่มีผลบังคับใช้อีกต่อไป มีจัดการสิทธิ์ของแอปพลิเคชันแล้วผ่านทางพอร์ทัลผู้ดูแลระบบ Power BI

## <a name="step-1---create-an-azure-ad-app"></a>ขั้นตอนที่ 1 - สร้าง แอป Azure AD

สร้างแอป Azure AD โดยใช้วิธีใดวิธีหนึ่งต่อไปนี้:
* สร้างแอปใน [พอร์ทัล Microsoft Azure](https://portal.azure.com/#allservices)
* สร้างแอปโดยใช้ [PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-3.6.1)

### <a name="creating-an-azure-ad-app-in-the-microsoft-azure-portal"></a>การสร้างแอป Azure AD ในพอร์ทัล Microsoft Azure

[!INCLUDE[service create app](../../includes/service-principal-create-app.md)]

7. คลิกแท็บ **ใบรับรองและความลับ**

     ![รหัสแอปพลิเคชัน](media/embed-service-principal/certificates-and-secrets.png)


8. คลิก **ความลับของไคลเอ็นต์ใหม่**

    ![ความลับของไคลเอ็นต์ใหม่](media/embed-service-principal/new-client-secret.png)

9. ในหน้าต่าง *เพิ่มความลับของไคลเอ็นต์* กรอกคำอธิบาย ระบุเวลาที่คุณต้องการให้ความลับของไคลเอ็นต์หมดอายุ จากนั้นคลิก **เพิ่ม**

10. คัดลอกและบันทึกค่า *ความลับของไคลเอ็นต์*

    ![ความลับของไคลเอ็นต์](media/embed-service-principal/client-secret-value.png)

    >[!NOTE]
    >หลังจากที่คุณออกจากหน้าต่างนี้ ค่าความลับของไคลเอ็นต์จะถูกซ่อนอยู่และคุณจะไม่สามารถดูหรือคัดลอกอีกครั้งได้

### <a name="creating-an-azure-ad-app-using-powershell"></a>การสร้างแอป Azure AD โดยใช้ PowerShell

ส่วนนี้จะประกอบด้วยสคริปต์ตัวอย่างในการสร้างแอป Azure AD ใหม่โดยใช้ [PowerShell](https://docs.microsoft.com/powershell/azure/create-azure-service-principal-azureps?view=azps-1.1.0)

```powershell
# The app ID - $app.appid
# The service principal object ID - $sp.objectId
# The app key - $key.value

# Sign in as a user that's allowed to create an app
Connect-AzureAD

# Create a new Azure AD web application
$app = New-AzureADApplication -DisplayName "testApp1" -Homepage "https://localhost:44322" -ReplyUrls "https://localhost:44322"

# Creates a service principal
$sp = New-AzureADServicePrincipal -AppId $app.AppId

# Get the service principal key
$key = New-AzureADServicePrincipalPasswordCredential -ObjectId $sp.ObjectId
```

## <a name="step-2---create-an-azure-ad-security-group"></a>ขั้นตอนที่ 2 - สร้างกลุ่มความปลอดภัย Azure AD

บริการหลักของคุณไม่มีสิทธิ์ในการเข้าถึงเนื้อหา Power BI และ API ของคุณ ในการให้สิทธิ์การเข้าถึงบริการหลัก ให้สร้างกลุ่มความปลอดภัยใน Azure AD และเพิ่มบริการหลักที่คุณสร้างไว้ในกลุ่มความปลอดภัยนั้น

มีสองวิธีในการสร้างกลุ่มความปลอดภัยใน Azure AD:
* ด้วยตนเอง (ใน Azure)
* ใช้ PowerShell

### <a name="create-a-security-group-manually"></a>สร้างกลุ่มความปลอดภัยด้วยตนเอง

หากต้องการสร้างกลุ่มความปลอดภัยใน Azure ด้วยตนเอง ให้ทำตามคำแนะนำในบทความ [สร้างกลุ่มพื้นฐานและเพิ่มสมาชิกโดยใช้ Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal) 

### <a name="create-a-security-group-using-powershell"></a>สร้างกลุ่มความปลอดภัยโดยใช้ PowerShell

ในด้านล่างจะแสดงสคริปต์ตัวอย่างในการสร้างกลุ่มความปลอดภัยใหม่ และการเพิ่มแอปไปยังกลุ่มความปลอดภัยนั้น

>[!NOTE]
>หากคุณต้องการเปิดใช้สิทธิ์การเข้าถึงบริการหลักสำหรับทั้งองค์กร โปรดข้ามขั้นตอนนี้

```powershell
# Required to sign in as a tenant admin
Connect-AzureAD

# Create an Azure AD security group
$group = New-AzureADGroup -DisplayName <Group display name> -SecurityEnabled $true -MailEnabled $false -MailNickName notSet

# Add the service principal to the group
Add-AzureADGroupMember -ObjectId $($group.ObjectId) -RefObjectId $($sp.ObjectId)
```

## <a name="step-3---enable-the-power-bi-service-admin-settings"></a>ขั้นตอนที่ 3 - เปิดใช้งานการตั้งค่าการจัดการบริการของ Power BI

เพื่อให้แอป Azure AD สามารถเข้าถึงเนื้อหา Power BI และ API ได้ ผู้ดูแลระบบ Power BI จำเป็นต้องเปิดใช้งานการเข้าถึงบริการหลักในพอร์ทัลผู้ดูแลระบบของ Power BI

เพิ่มกลุ่มความปลอดภัยที่คุณสร้างใน Azure AD สำหรับส่วนกลุ่มความปลอดภัยเฉพาะใน **การตั้งค่านักพัฒนา**

>[!IMPORTANT]
>บริการหลักมีสิทธิ์เข้าถึงการตั้งค่าผู้เช่าใดๆ ที่เปิดใช้งานอยู่ โดยจะรวมถึงกลุ่มความปลอดภัยเฉพาะหรือทั้งองค์กร ขึ้นอยู่กับการตั้งค่าผู้ดูแลระบบของคุณ
>
>เพื่อจำกัดการเข้าถึงบริการหลักของการตั้งค่าผู้เช่าเฉพาะ จะมีการอนุญาตให้เข้าถึงเพียงกลุ่มความปลอดภัยเฉพาะเท่านั้น อีกวิธีหนึ่งคือคุณสามารถสร้างกลุ่มความปลอดภัยเฉพาะสำหรับบริการหลัก และแยกออกไปจากการตั้งค่าผู้เช่าที่ต้องการได้

![พอร์ทัลผู้ดูแลระบบ](media/embed-service-principal/admin-portal.png)

## <a name="step-4---add-the-service-principal-to-your-workspace"></a>ขั้นตอนที่ 4 - เพิ่มบริการหลักไปยังพื้นที่ทำงานของคุณ

ในการเปิดใช้งานการเข้าถึงแอป Azure AD ของคุณ เช่น รายงาน แดชบอร์ด และชุดข้อมูลในบริการ Power BI ให้เพิ่มเอนทิตีบริการหลักเป็นสมาชิกหรือผู้ดูแลระบบในพื้นที่ทำงานของคุณ

>[!NOTE]
>ส่วนนี้แสดงคำแนะนำของ UI คุณยังสามารถเพิ่มบริการหลักให้กับพื้นที่ทำงานโดยใช้ [กลุ่ม - เพิ่ม API ของผู้ใช้กลุ่ม](https://docs.microsoft.com/rest/api/power-bi/groups/addgroupuser)

1. เลื่อนไปยังพื้นที่ทำงานที่คุณต้องการเปิดใช้งานการเข้าถึง และจากเมนู **เพิ่มเติม** เลือก **การเข้าถึงพื้นที่ทำงาน**

    ![การตั้งค่าพื้นที่ทำงาน](media/embed-service-principal/workspace-access.png)

2. เพิ่มบริการหลักเป็น **ผู้ดูแลระบบ** หรือ **สมาชิก** ในพื้นที่ทำงาน

    ![ผู้ดูแลระบบพื้นที่ทำงาน](media/embed-service-principal/add-service-principal-in-the-UI.png)

## <a name="step-5---embed-your-content"></a>ขั้นตอนที่ 5 - ฝังเนื้อหาของคุณ

คุณสามารถฝังเนื้อหาของคุณภายในแอปพลิเคชันตัวอย่าง หรือภายในแอปพลิเคชันของคุณเอง

* [ฝังเนื้อหาโดยใช้แอปพลิเคชันตัวอย่าง](embed-sample-for-customers.md#embed-content-using-the-sample-application)
* [ฝังเนื้อหาภายในแอปพลิเคชันของคุณ](embed-sample-for-customers.md#embed-content-within-your-application)

หลังจากที่มีการฝังเนื้อหาของคุณแล้ว คุณก็พร้อมที่จะ [ย้ายไปยังการผลิต](embed-sample-for-customers.md#move-to-production)

[!INCLUDE[service principal limitations](../../includes/service-principal-limitations.md)]

## <a name="next-steps"></a>ขั้นตอนถัดไป

>[!div class="nextstepaction"]
>[ลงทะเบียนแอป](register-app.md)

> [!div class="nextstepaction"]
>[Power BI Embedded สำหรับลูกค้าของคุณ](embed-sample-for-customers.md)

>[!div class="nextstepaction"]
>[แอปพลิเคชันและออบเจ็กต์บริการหลักใน Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals)

>[!div class="nextstepaction"]
>[ความปลอดภัยระดับแถวโดยใช้เกตเวย์ข้อมูลภายในองค์กรที่มีโครงร่างสำคัญของบริการ](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal)

>[!div class="nextstepaction"]
>[การฝังเนื้อหา Power BI ด้วยบริการหลักและใบรับรอง](embed-service-principal-certificate.md)

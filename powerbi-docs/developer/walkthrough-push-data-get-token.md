---
title: รับโทเค็นการเข้าถึงการรับรองความถูกต้อง
description: คำแนะนำการส่งข้อมูล - รับโทเค็นการเข้าถึงการรับรองความถูกต้อง
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: 4a0b0f5e7d697c137da343576d05fbcc91b4a4f7
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "65710358"
---
# <a name="step-2-get-an-authentication-access-token"></a>ขั้นตอนที่ 2: รับโทเค็นการเข้าใช้การรับรองความถูกต้อง

บทความนี้เป็นส่วนหนึ่งของคำแนะนำทีละขั้นตอนเพื่อ[ส่งข้อมูลไปยังชุดข้อมูล](walkthrough-push-data.md)

ใน**ขั้นตอนที่ 1**เป็นขั้นตอนของการส่งข้อมูลลงในชุดข้อมูล[ลงทะเบียนแอปกับ Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)คุณลงทะเบียนแอปไคลเอ็นต์ใน Azure AD ในขั้นตอนนี้ คุณจะได้รับโทเค็นการเข้าถึงการรับรองความถูกต้อง แอป Power BI จะรวมกับ**Azure AD**เพื่อให้สามารถเข้าสู่ระบบความปลอดภัยและการตรวจสอบสำหรับแอปของคุณ คุณใช้โทเค็นเพื่อรับรองความถูกต้องในการเข้าถึง**Azure AD**และเพื่อเข้าถึงแหล่งข้อมูลของ Power BI

นี่คือวิธีการรับโทเค็นการเข้าถึงการรับรองความถูกต้อง

## <a name="get-an-authentication-access-token"></a>รับโทเค็นการเข้าใช้การรับรองความถูกต้อง

> **หมายเหตุ**: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่า คุณดำเนินตามขั้นตอนก่อนหน้านี้ในการฝึกปฏิบัติ[พุชข้อมูลลงในชุดข้อมูล](walkthrough-push-data.md)แล้ว

1. ใน Visual Studio (2015 หรือใหม่กว่า), สร้างเป็น**แอปพลิเคชันคอนโซล**โครงการ
2. ติดตั้ง[ไลบรารีรับรองความถูกต้อง AD Azure สำหรับแพคเกจ .NET NuGet](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/2.22.302111727) ใช้แพคเกจนี้ หากคุณต้องการรับโทเค็นรักษาความปลอดภัยการรับรองความถูกต้องในแอป .NET นี่คือวิธีการติดตั้งแพคเกจ:

     a. ใน Visual Studio (2015 หรือใหม่กว่า), เลือก**เครื่องมือ** > **Manager แพคเกจ NuGet** > **คอนโซล Manager แพคเกจ**

     b. ใน**คอนโซลตัวจัดการแพคเกจ**ใส่แพคเกจติดตั้ง Microsoft.IdentityModel.Clients.ActiveDirectory -รุ่น 2.21.301221612.
3. เพิ่มรหัสด้านล่างลงในคลาสโปรแกรม {...}
4. แทนที่ "{ClientID }" ด้วย**ID ไคลเอ็นต์**ที่คุณได้รับเมื่อคุณลงทะเบียนแอป ดู[การลงทะเบียนแอปกับ Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)
5. หลังจากติดตั้งแพคเกจ Microsoft.IdentityModel.Clients.ActiveDirectory แล้ว เพิ่ม**การใช้ Microsoft.IdentityModel.Clients.ActiveDirectory;** ลงใน Program.cs
6. เรียกใช้แอปคอนโซล และเข้าสู่บัญชี Power BI ของคุณ คุณจะเห็นสตริงโทเค็นในหน้าต่างคอนโซล

**ตัวอย่างรหัสเพื่อรับโทเค็นรักษาความปลอดภัยการรับรองความถูกต้อง**

เพิ่มรหัสนี้ลงในโปรแกรม {...}

* ตัวแปรโทเค็นสำหรับเรียกใช้การดำเนินการ:
  
  ```csharp
  private static string token = string.Empty;
  
  static void Main(string[] args)
  {
  }
  ```
* ค่าคงที่เพื่อยกเลิก Main(string[] args):
  
  ```csharp
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```
* เพิ่มวิธีการ GetToken():

```csharp
       #region Get an authentication access token
       private static string GetToken()
       {
           // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
           // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

           //The client id that Azure AD created when you registered your client app.
           string clientID = "{Client_ID}";

           //RedirectUri you used when you register your app.
           //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
           // You can use this redirect uri for your client app
           string redirectUri = "https://login.live.com/oauth20_desktop.srf";

           //Resource Uri for Power BI API
           string resourceUri = "https://analysis.windows.net/powerbi/api";

           //OAuth2 authority Uri
           string authorityUri = "https://login.microsoftonline.net/common/";

           //Get access token:
           // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
           // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
           // To install the Active Directory Authentication Library NuGet package in Visual Studio,
           //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

           // AcquireToken will acquire an Azure access token
           // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
           AuthenticationContext authContext = new AuthenticationContext(authorityUri);
           string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

           Console.WriteLine(token);
           Console.ReadLine();

           return token;
       }

       #endregion
```

หลังจากที่คุณได้รับโทเค็นรับรองความถูกต้อง คุณสามารถเรียกการดำเนินการ Power BI ต่างๆได้ ขั้นตอนถัดไปแสดงวิธีการเรียกใช้การดำเนินการ [โพสต์ชุดข้อมูล](https://docs.microsoft.com/rest/api/power-bi/pushdatasets) เพื่อสร้างชุดข้อมูลให้สามารถพุชข้อมูลลงในแดชบอร์ด

ขั้นตอนถัดไปแสดงวิธีการ[สร้างชุดข้อมูลใน Power BI](walkthrough-push-data-create-dataset.md)

ด้านล่างนี้คือ[รายการรหัสที่เสร็จสมบูรณ์](#code)

<a name="code"/>

## <a name="complete-code-listing"></a>รายการรหัสเสร็จสมบูรณ์

```csharp
using System;
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace walkthrough_push_data
{
    class Program
    {
        private static string token = string.Empty;

        static void Main(string[] args)
        {

            //Get an authentication access token
            token = GetToken();

        }

        #region Get an authentication access token
        private static string GetToken()
        {
            // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
            // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

            //The client id that Azure AD created when you registered your client app.
            string clientID = "{Client_ID}";

            //RedirectUri you used when you register your app.
            //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
            // You can use this redirect uri for your client app
            string redirectUri = "https://login.live.com/oauth20_desktop.srf";

            //Resource Uri for Power BI API
            string resourceUri = "https://analysis.windows.net/powerbi/api";

            //OAuth2 authority Uri
            string authorityUri = "https://login.microsoftonline.com/common/";

            //Get access token:
            // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
            // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
            // To install the Active Directory Authentication Library NuGet package in Visual Studio,
            //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

            // AcquireToken will acquire an Azure access token
            // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
            AuthenticationContext authContext = new AuthenticationContext(authorityUri);
            string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

            Console.WriteLine(token);
            Console.ReadLine();

            return token;
        }

        #endregion

    }
}
```

[ขั้นตอนถัดไป >](walkthrough-push-data-create-dataset.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป

[สร้างชุดข้อมูลใน Power BI](walkthrough-push-data-create-dataset.md)  
[ลงทะเบียนแอปกับ Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)  
[ไลบรารีรับรองความถูกต้อง AD azure สำหรับแพคเกจ .NET NuGet](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[ส่งข้อมูลลงในชุดข้อมูล Power BI](walkthrough-push-data.md)  
[ภาพรวมของ Power BI REST API](overview-of-power-bi-rest-api.md)  
[การอ้างอิง Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/)  
คุณมีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)
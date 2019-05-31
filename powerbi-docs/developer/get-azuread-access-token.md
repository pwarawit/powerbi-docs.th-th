---
title: รับรองความถูกต้องของผู้ใช้ และรับโทเค็นการเข้าถึง Azure AD สำหรับแอปพลิเคชันของคุณ
description: เรียนรู้วิธีการลงทะเบียนแอปพลิเคชันใน Azure Active Directory สำหรับการใช้งานด้วยการฝังเนื้อหา Power BI
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: a38547807fbbcf3c76366f32caa46945e57ca8bc
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "65710318"
---
# <a name="get-an-azure-ad-access-token-for-your-power-bi-application"></a>รับโทเค็นการเข้าถึง Azure AD สำหรับแอปพลิเคชัน Power BI ของคุณ

รับรองความถูกต้องผู้ใช้ในแอปพลิเคชัน Power BI ของคุณ และเรียกใช้โทเค็นการเข้าถึงการใช้กับ REST API

ก่อนที่คุณจะสามารถโทรหา Power BI REST API คุณจำเป็นต้องรับ Azure Active Directory (Azure AD) **โทเค็นการเข้าถึงการรับรองความถูกต้อง**(โทเค็นการเข้าถึง) โทเค็น**การเข้าถึง**ถูกใช้เพื่ออนุญาตการเข้าถึงแอปในแดชบอร์ด ไทล์ และรายงาน **Power BI** เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับ Azure Active Directory **กระบวนการ** โทเค็นการเข้าถึง ดู[กระบวนการอนุญาตรหัสการให้สิทธิ์ Azure AD](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code)

โทเค็นการเข้าถึงจะถูกเรียกใช้แตกต่างกัน ขึ้นอยู่กับวิธีการที่คุณจะฝังเนื้อหา มีการใช้สองวิธีการที่แตกต่างกันในบทความนี้

## <a name="access-token-for-power-bi-users-user-owns-data"></a>โทเค็นการเข้าถึงสำหรับผู้ใช้ Power BI (ผู้ใช้เป็นเจ้าของข้อมูล)

ตัวอย่างนี้สำหรับเมื่อผู้ใช้ของคุณจะลงชื่อเข้าใช้ Azure AD ด้วยตนเองโดยเข้าสู่ระบบขององค์กร งานนี้จะใช้เมื่อมีการฝังเนื้อหาสำหรับผู้ใช้ Power BI ที่จะเข้าถึงเนื้อหาที่พวกเขามีสิทธิ์เข้าถึงบริการ Power BI

### <a name="get-an-authorization-code-from-azure-ad"></a>รับรหัสการให้สิทธิ์จาก Azure AD

ขั้นตอนแรกในการรับ**โทเค็นการเข้าถึง**คือการรับรหัสการให้สิทธิ์จาก**Azure AD** คุณจะต้องสร้างสตริงแบบสอบถามกับคุณสมบัติต่อไปนี้ และเปลี่ยนเส้นทางไปยัง**Azure AD**

#### <a name="authorization-code-query-string"></a>สตริงแบบสอบถามรหัสการให้สิทธิ์

```csharp
var @params = new NameValueCollection
{
    //Azure AD will return an authorization code. 
    //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
    {"response_type", "code"},

    //Client ID is used by the application to identify themselves to the users that they are requesting permissions from.
    //You get the client id when you register your Azure app.
    {"client_id", Properties.Settings.Default.ClientID},

    //Resource uri to the Power BI resource to be authorized
    // https://analysis.windows.net/powerbi/api
    {"resource", Properties.Settings.Default.PowerBiAPI},

    //After user authenticates, Azure AD will redirect back to the web app
    {"redirect_uri", "http://localhost:13526/Redirect"}
};
```

หลังจากที่คุณสร้างสตริงแบบสอบถามแล้ว เปลี่ยนเส้นทางไปยัง**Azure AD**เพื่อรับ**รหัสการให้สิทธิ์**  ด้านล่างนี้คือวิธีการ์ C# ที่สมบูรณที่จะสร้าง**รหัสการตรวจสอบ**สตริงค้นหา และเปลี่ยนเส้นทางไปยัง**Azure AD** หลังจากที่คุณมีรหัสการให้สิทธิ์ คุณจะได้รับ**โทเค็นการเข้าถึง**โดยใช้การ**รหัสการให้สิทธิ์**

ภายใน redirect.aspx.cs, จะเรียก [AuthenticationContext.AcquireTokenByAuthorizationCode](https://docs.microsoft.com/dotnet/api/microsoft.identitymodel.clients.activedirectory.authenticationcontext.acquiretokenbyauthorizationcodeasync?view=azure-dotnet#Microsoft_IdentityModel_Clients_ActiveDirectory_AuthenticationContext_AcquireTokenByAuthorizationCodeAsync_System_String_System_Uri_Microsoft_IdentityModel_Clients_ActiveDirectory_ClientCredential_System_String_) เพื่อสร้างโทเค็น

#### <a name="get-authorization-code"></a>รับรหัสการให้สิทธิ์

```csharp
protected void signInButton_Click(object sender, EventArgs e)
{
    //Create a query string
    //Create a sign-in NameValueCollection for query string
    var @params = new NameValueCollection
    {
        //Azure AD will return an authorization code. 
        //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
        {"response_type", "code"},

        //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
        //You get the client id when you register your Azure app.
        {"client_id", Properties.Settings.Default.ClientID},

        //Resource uri to the Power BI resource to be authorized
        // https://analysis.windows.net/powerbi/api
        {"resource", Properties.Settings.Default.PowerBiAPI},

        //After user authenticates, Azure AD will redirect back to the web app
        {"redirect_uri", "http://localhost:13526/Redirect"}
    };

    //Create sign-in query string
    var queryString = HttpUtility.ParseQueryString(string.Empty);
    queryString.Add(@params);

    //Redirect authority
    //Authority Uri is an Azure resource that takes a client id to get an Access token
    // AADAuthorityUri = https://login.microsoftonline.com/common/
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;
    var authUri = String.Format("{0}?{1}", authorityUri, queryString);
    Response.Redirect(authUri);
}
```

### <a name="get-an-access-token-from-authorization-code"></a>รับโทเค็นการเข้าถึงจากรหัสการให้สิทธิ์

คุณควรจะได้รับรหัสการให้สิทธิ์จาก Azure AD เมื่อ**Azure AD**เปลี่ยนเส้นทางไปยัง web app ของคุณด้วย**รหัสการให้สิทธิ์**คุณใช้**รหัสการให้สิทธิ์**เพื่อรับโทเค็นการเข้าถึง ด้านล่างนี้คือ C# ตัวอย่างที่คุณสามารถใช้ในหน้าการเปลี่ยนเส้นทางของคุณและเหตุการณ์ Page_Load สำหรับหน้า default.aspx ของคุณ

เนมสเปซ**Microsoft.IdentityModel.Clients.ActiveDirectory** สามารถดึงมาจาก[ไลบรารีการรับรองความถูกต้อง Active Directory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)แพคเกจ NuGet ได้

```powershell
Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
```

#### <a name="redirectaspxcs"></a>Redirect.aspx.cs

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{
    //Redirect uri must match the redirect_uri used when requesting Authorization code.
    string redirectUri = String.Format("{0}Redirect", Properties.Settings.Default.RedirectUrl);
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;

    // Get the auth code
    string code = Request.Params.GetValues(0)[0];

    // Get auth token from auth code
    TokenCache TC = new TokenCache();

    AuthenticationContext AC = new AuthenticationContext(authorityUri, TC);
    ClientCredential cc = new ClientCredential
        (Properties.Settings.Default.ClientID,
        Properties.Settings.Default.ClientSecret);

    AuthenticationResult AR = AC.AcquireTokenByAuthorizationCode(code, new Uri(redirectUri), cc);

    //Set Session "authResult" index string to the AuthenticationResult
    Session[_Default.authResultString] = AR;

    //Redirect back to Default.aspx
    Response.Redirect("/Default.aspx");
}
```

#### <a name="defaultaspx"></a>Default.aspx

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{

    //Test for AuthenticationResult
    if (Session[authResultString] != null)
    {
        //Get the authentication result from the session
        authResult = (AuthenticationResult)Session[authResultString];

        //Show Power BI Panel
        signInStatus.Visible = true;
        signInButton.Visible = false;

        //Set user and token from authentication result
        userLabel.Text = authResult.UserInfo.DisplayableId;
        accessTokenTextbox.Text = authResult.AccessToken;
    }
}
```

## <a name="access-token-for-non-power-bi-users-app-owns-data"></a>โทเค็นการเข้าถึงสำหรับผู้ใช้ที่ไม่ใช่ Power BI (แอปเป็นเจ้าของข้อมูล)

โดยทั่วไปวิธีการนี้จะใช้สำหรับแอปพลิเคชันชนิด ISV ที่แอปเป็นเจ้าของการเข้าถึงข้อมูล ผู้ใช้ไม่จำเป็นต้องเป็นผู้ใช้ Power BI และการรับรองความถูกต้องของตัวควบคุมแอปพลิเคชัน และการเข้าถึงสำหรับผู้ใช้ปลายทาง

### <a name="access-token-with-a-master-account"></a>โทเค็นการเข้าถึงด้วยบัญชีหลัก

สำหรับวิธีการนี้ คุณจะใช้บัญชี*หลัก*เดี่ยวที่เป็นผู้ใช้ Power BI Pro ข้อมูลประจำตัวสำหรับบัญชีนี้ถูกเก็บไว้กับแอปพลิเคชัน แอปพลิเคชันจะรับรองความถูกต้องกับ Azure AD ด้วยข้อมูลประจำตัวที่จัดเก็บไว้ รหัสตัวอย่างที่แสดงด้านล่างนี้มาจาก[แอปที่เป็นเจ้าของตัวอย่างข้อมูล](https://github.com/guyinacube/PowerBI-Developer-Samples)

### <a name="access-token-with-service-principal"></a>โทเค็นการเข้าถึงด้วยบริการหลัก

สำหรับวิธีนี้ คุณใช้[บริการหลัก](embed-service-principal.md)ซึ่งก็คือ**โทเค็นเฉพาะแอป** แอปพลิเคชันจะรับรองความถูกต้องกับ Azure AD ด้วยบริการหลัก รหัสตัวอย่างที่แสดงด้านล่างนี้มาจาก[แอปที่เป็นเจ้าของตัวอย่างข้อมูล](https://github.com/guyinacube/PowerBI-Developer-Samples)

#### <a name="embedservicecs"></a>EmbedService.cs

```csharp
var authenticationContext = new AuthenticationContext(AuthorityUrl);
       AuthenticationResult authenticationResult = null;
       if (AuthenticationType.Equals("MasterUser"))
       {
              // Authentication using master user credentials
              var credential = new UserPasswordCredential(Username, Password);
              authenticationResult = authenticationContext.AcquireTokenAsync(ResourceUrl, ApplicationId, credential).Result;
       }
       else
       {
             // Authentication using app credentials
             var credential = new ClientCredential(ApplicationId, ApplicationSecret);
             authenticationResult = await authenticationContext.AcquireTokenAsync(ResourceUrl, credential);
       }


m_tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");
```

## <a name="troubleshoot"></a>การแก้ไขปัญหา

* ดาวน์โหลด[Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/2.22.302111727)ถ้าคุณพบข้อ " 'AuthenticationContext' ประกอบด้วยข้อกำหนดสำหรับ 'AcquireToken' และไม่สามารถเข้าถึง 'AcquireToken' ยอมรับอาร์กิวเมนต์ตัวแรกของชนิด ' AuthenticationContext' พบ (คุณหายไปโดยการใช้คำสั่งหรือการอ้างอิงแอสเซมบลีหรือไม่) "ข้อผิดพลาดได้

## <a name="next-steps"></a>ขั้นตอนถัดไป

หลังจากที่คุณมีโทเค็นการเข้าถึง คุณจะสามารถโทรหา Power BI REST API เพื่อฝังเนื้อหา สำหรับข้อมูลเกี่ยวกับวิธีการฝังเนื้อหาของคุณ ดู[วิธีการฝังเนื้อหาของ Power BI ](embed-sample-for-customers.md#embed-content-within-your-application)

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](http://community.powerbi.com/)
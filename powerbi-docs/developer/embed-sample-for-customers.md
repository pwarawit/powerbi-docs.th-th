---
title: ฝังเนื้อหา Power BI ลงในแอปพลิเคชันสำหรับลูกค้าของคุณ
description: เรียนรู้วิธีการรวม หรือฝัง แดชบอร์ด ไทล์ หรือรายงาน ลงในเว็บแอปโดยใช้ API ของ Power BI สำหรับลูกค้าของคุณ
services: powerbi
documentationcenter: ''
author: markingmyname
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/11/2018
ms.author: maghan
ms.openlocfilehash: 779ae9a6df285b58c83021f87ed593af9ec0b3fb
ms.sourcegitcommit: 3f2f254f6e8d18137bae879ddea0784e56b66895
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/26/2018
---
# <a name="embed-a-power-bi-dashboard-tile-or-report-into-your-application"></a>ฝังแดชบอร์ด ไทล์ หรือรายงาน Power BI ลงในแอปพลิเคชันของคุณ
เรียนรู้วิธีการรวม หรือฝัง แดชบอร์ด ไทล์ หรือรายงาน ลงในเว็บแอปโดยใช้ Power BI .NET SDK พร้อมกับ Power BI JavaScript API เมื่อทำการฝังสิ่งต่างๆ สำหรับลูกค้าของคุณ นี่คือสภาพ ISV โดยทั่วไป

![แดชบอร์ดแบบฝังตัว](media/embed-sample-for-customers/powerbi-embed-dashboard.png)

เมื่อต้องการเริ่มต้นใช้งานการฝึกปฏิบัตินี้ คุณต้องมีบัญชี**Power BI Pro** ถ้าคุณไม่มีบัญชีผู้ใช้ คุณสามารถ[ลงทะเบียนเพื่อรับบัญชี Power BI ฟรี](../service-self-service-signup-for-power-bi.md)และจากนั้น ลงทะเบียนเพื่อทดลองใช้[ Power BI Pro](../service-self-service-signup-for-power-bi.md#in-service-power-bi-pro-60-day-trial) หรือคุณสามารถสร้าง [Azure Active Directory ระดับผู้เช่า](create-an-azure-active-directory-tenant.md) ด้วยตนเองเพื่อทำการทดสอบ

> [!NOTE]
> กำลังจะฝังแดชบอร์ดสำหรับองค์กรของคุณหรือไม่ ดูที่ [รวมแดชบอร์ดลงในแอปสำหรับองค์กรของคุณ](integrate-dashboard.md)
> 
> 

เมื่อต้องรวมแดชบอร์ดลงในเว็บแอป คุณใช้ **Power BI** API และ**โทเค็นการเข้าถึง**สำหรับรับรองความถูกต้องกับ Azure Active Directory (AD) เพื่อรับแดชบอร์ด หลังจากนั้น คุณโหลดแดชบอร์ดโดยใช้โทเค็นฝังตัว **Power BI** API ให้การเข้าถึงแหล่งข้อมูล **Power BI** ผ่านทางโปรแกรม สำหรับข้อมูลเพิ่มเติม ดู[ภาพรวมของ Power BI REST API](https://msdn.microsoft.com/library/dn877544.aspx), [Power BI .NET SDK](https://github.com/Microsoft/PowerBI-CSharp) และ [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

## <a name="download-the-sample"></a>ดาวน์โหลดตัวอย่าง
บทความนี้แสดงรหัสที่ใช้ในการ[ฝังตัวสำหรับตัวอย่างขององค์กรของคุณ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)บน GitHub เพื่อติดตามการฝึกปฏิบัตินี้ คุณสามารถดาวน์โหลดตัวอย่างได้

## <a name="step-1---register-an-app-in-azure-ad"></a>ขั้นตอนที่ 1: ลงทะเบียนแอปใน Azure AD
คุณจะต้องลงทะเบียนแอปพลิเคชันของคุณกับ Azure AD เพื่อเรียกใช้ REST API สำหรับข้อมูลเพิ่มเติม ดู[ลงทะเบียนแอป Azure AD เพื่อฝังเนื้อหา Power BI](register-app.md)

ถ้าคุณดาวน์โหลดตัวอย่างการ[ฝังเพื่อองค์กรของคุณ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)คุณต้องใช้ **ID ไคลเอ็นต์**ที่คุณได้หลังการลงทะเบียน เพื่อให้ตัวอย่างสามารถรับรองความถูกต้องกับ Azure AD เมื่อต้องการกำหนดค่าตัวอย่าง เปลี่ยนคำ **clientId** ในไฟล์*web.config*

## <a name="step-2---get-an-access-token-from-azure-ad"></a>ขั้นตอนที่ 2 - รับโทเค็นการเข้าถึงจาก Azure AD
ภายในแอปพลิเคชันของคุณ คุณจะต้องรับ**โทเค็นการเข้าถึง**จาก Azure AD ก่อนที่คุณสามารถเรียกใช้ Power BI REST API ได้ สำหรับข้อมูลเพิ่มเติม ดู[รับรองผู้ใช้ และรับโทเค็นการเข้าถึง Azure AD สำหรับแอป Power BI ของคุณ](get-azuread-access-token.md)

คุณสามารถดูตัวอย่างของสิ่งนี้ในงานแต่ละรายการเนื้อหาใน **Controllers\HomeController.cs** ได้

## <a name="step-3---get-a-content-item"></a>ขั้นตอนที่ 3 - รับเนื้อหา
เมื่อต้องฝังเนื้อหา Power BI ของคุณ คุณจะจำเป็นต้องทำสองสิ่งให้แน่ใจว่า การฝังตัวถูกต้อง ถึงแม้ว่าขั้นตอนเหล่านี้สามารถทำได้ใน REST API โดยตรง แอปพลิเคชันตัวอย่าง และตัวอย่างนี้จะใช้ .NET SDK

### <a name="create-the-power-bi-client-with-your-access-token"></a>สร้างไคลเอ็นต์ Power BI ด้วยโทเค็นการเข้าถึงของคุณ
ด้วยโทเค็นการเข้าถึงของคุณ คุณสามารถสร้างวัตถุไคลเอ็นต์ Power BI ของคุณ ให้คุณสามารถโต้ตอบกับ Power BI API ทำได้โดยนำ AccessToken ไปใส่ไว้ในวัตถุ *Microsoft.Rest.TokenCredentials*

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to embed items.
}
```

### <a name="get-the-content-item-you-want-to-embed"></a>รับเนื้อหาที่คุณต้องการฝังตัว
คุณใช้วัตถุไคลเอ็นต์ Power BI เพื่อดึงเอา อ้างอิงไปยังเนื้อหา ที่คุณต้องการฝังตัว คุณสามารถฝังแดชบอร์ด ไทล์ หรือรายงาน นี่คือตัวอย่างของวิธีการดึง แดชบอร์ด ไทล์ หรือรายงานจากพื้นที่ทำงานที่ระบุไว้

มีตัวอย่างนี้ให้ใน **Controllers\HomeController.cs** ของการ[ตัวอย่าง แอปเป็นเจ้าของข้อมูล](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

**แดชบอร์ด**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();
```

**ไทล์**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// To retrieve the tile, you first need to retrieve the dashboard.

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();

// Get a list of tiles from a specific dashboard
ODataResponseListTile tiles = client.Dashboards.GetTilesInGroup(GroupId, dashboard.Id);

// Get the first tile in the group.
Tile tile = tiles.Value.FirstOrDefault();
```

**รายงาน**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListReport reports = client.Reports.GetReportsInGroupAsync(GroupId);

// Get the first report in the group.
Report report = reports.Value.FirstOrDefault();
```

### <a name="create-the-embed-token"></a>สร้างโทเค็นฝังตัว
โทเค็นฝังตัว จะต้องถูกสร้างขึ้นสำหรับใช้จาก JavaScript API โทเค็นฝังตัวแต่ละตัวจะเฉพาะเจาะจงกับรายการคุณจะฝัง ซึ่งหมายความว่า ทุกครั้งที่คุณต้องการฝังเนื้อหาของ Power BI ชิ้นหนึ่ง คุณต้องสร้างโทเค็นใหม่ขึ้นมา สำหรับข้อมูลเพิ่มเติม รวมไปถึง **accessLevel** ที่จะใช้ ดู[GenerateToken API](https://msdn.microsoft.com/library/mt784614.aspx)

> [!IMPORTANT]
> เนื่องจากโทเค็นฝังตัวมีไว้สำหรับทดสอบการพัฒนาเท่านั้น จำนวนโทเค็นฝังตัวที่บัญชีหลักของ Power BI มีได้จำกัด จะ[ต้องซื้อความจุ](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical) สำหรับการใช้งานจริง ไม่มีข้อจำกัดจำนวนโทเค็นฝังตัวที่สร้างเมื่อซื้อความจุแล้ว ไปที่ [รับฟีเจอร์ที่พร้อมใช้งาน](https://msdn.microsoft.com/en-us/library/mt846473.aspx) เพื่อตรวจสอบจำนวนโทเค็นการฝังฟรีแบบต่างๆ ที่ใช้

มีตัวอย่างนี้ อยู่ใน **Controllers\HomeController.cs** ของ[ตัวอย่างการฝังตัวสำหรับองค์กรของคุณ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

ตัวอย่างต่อไปนี้ สมมุติว่ามีการสร้างคลาสสำหรับ **EmbedConfig** และ **TileEmbedConfig** อยู่ก่อนแล้ว ตัวอย่างมีให้ใน **Models\EmbedConfig.cs** และ **Models\TileEmbedConfig.cs**

**แดชบอร์ด**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Dashboards.GenerateTokenInGroup(GroupId, dashboard.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = dashboard.EmbedUrl,
    Id = dashboard.Id
};
```

**ไทล์**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token for a tile.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Tiles.GenerateTokenInGroup(GroupId, dashboard.Id, tile.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new TileEmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = tile.EmbedUrl,
    Id = tile.Id,
    dashboardId = dashboard.Id
};
```

**รายงาน**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Reports.GenerateTokenInGroup(GroupId, report.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = report.EmbedUrl,
    Id = report.Id
};
```



## <a name="step-4---load-an-item-using-javascript"></a>ขั้นตอนที่ 4 - โหลดเนื้อหาโดยใช้ JavaScript
คุณสามารถใช้ JavaScript เพื่อโหลดแดชบอร์ดลงใน องค์ประกอบ div บนเว็บเพจของคุณ ตัวอย่างนี้ใช้รูปแบบ EmbedConfig/TileEmbedConfig พร้อมกับมุมมองสำหรับแดชบอร์ด ไทล์ หรือรายงาน สำหรับตัวอย่างแบบเต็มของการใช้ JavaScript API คุณสามารถใช้ [ตัวอย่างแบบฝังตัวของ Microsoft Power BI](https://microsoft.github.io/PowerBI-JavaScript/demo)

ตัวอย่างเป็นแอปพลิเคชันแบบนี้ มีอยู่ใน[ตัวอย่างการฝังตัวสำหรับองค์กรของคุณ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

**Views\Home\EmbedDashboard.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="dashboardContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read dashboard Id from Model
    var embedDashboardId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'dashboard',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedDashboardId
    };

    // Get a reference to the embedded dashboard HTML element
    var dashboardContainer = $('#dashboardContainer')[0];

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);
</script>
```

**Views\Home\EmbedTile.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="tileContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read tile Id from Model
    var embedTileId = "@Model.Id";

    // Read dashboard Id from Model
    var embedDashboardeId = "@Model.dashboardId";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedTileId,
        dashboardId: embedDashboardeId
    };

    // Get a reference to the embedded tile HTML element
    var tileContainer = $('#tileContainer')[0];

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);
</script>
```

**Views\Home\EmbedReport.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="reportContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read report Id from Model
    var embedReportId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedReportId,
        permissions: models.Permissions.All,
        settings: {
            filterPaneEnabled: true,
            navContentPaneEnabled: true
        }
    };

    // Get a reference to the embedded report HTML element
    var reportContainer = $('#reportContainer')[0];

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);
</script>
```

## <a name="next-steps"></a>ขั้นตอนถัดไป
มีตัวอย่างแอปพลิเคชั่นอยู่บน GitHub ให้คุณได้ศึกษา ตัวอย่างต่าง ๆ ข้างบนมาจากตัวอย่างนั้น สำหรับข้อมูลเพิ่มเติม ดูการ[ฝังตัวเพื่อตัวอย่างขององค์กรของคุณ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

ข้อมูลเพิ่มเติมสำหรับ JavaScript API ดู [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


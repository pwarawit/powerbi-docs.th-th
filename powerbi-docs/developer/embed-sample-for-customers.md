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
ms.openlocfilehash: c6b9edb929934a80886874fe421f11cc7462dbd8
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/30/2018
---
# <a name="embed-a-power-bi-dashboard-tile-or-report-into-your-application"></a>ฝังแดชบอร์ด ไทล์ หรือรายงาน Power BI ลงในแอปพลิเคชันของคุณ
เรียนรู้วิธีการรวม หรือฝัง แดชบอร์ด ไทล์ หรือรายงาน ลงในเว็บแอปโดยใช้ Power BI .NET SDK พร้อมกับ Power BI JavaScript API เมื่อทำการฝังสิ่งต่างๆ สำหรับลูกค้าของคุณ นี่คือสภาพ ISV โดยทั่วไป

![แดชบอร์ดแบบฝังตัว](media/embed-sample-for-customers/powerbi-embed-dashboard.png)

เมื่อต้องการเริ่มต้นใช้งานการฝึกปฏิบัตินี้ คุณต้องมีบัญชี**Power BI Pro** ถ้าคุณไม่มีบัญชีผู้ใช้ คุณสามารถ[ลงทะเบียนเพื่อรับบัญชี Power BI ฟรี](../service-self-service-signup-for-power-bi.md)และจากนั้น ลงทะเบียนเพื่อทดลองใช้[ Power BI Pro](../service-self-service-signup-for-power-bi.md#in-service-power-bi-pro-60-day-trial) หรือคุณสามารถสร้าง [Azure Active Directory ระดับผู้เช่า](create-an-azure-active-directory-tenant.md) ด้วยตนเองเพื่อทำการทดสอบ

> [!NOTE]
> กำลังจะฝังแดชบอร์ดสำหรับองค์กรของคุณหรือไม่ ดู[รวมแดชบอร์ดลงในแอปสำหรับองค์กรของคุณ](integrate-dashboard.md)
> 
> 

เมื่อต้องรวมแดชบอร์ดลงในเว็บแอป คุณต้องใช้ **Power BI** API และ**โทเค็นการเข้าถึง**การตรวจสอบ Azure Active Directory (AD) เพื่อรับแดชบอร์ด จากนั้น คุณสามารถโหลดแดชบอร์ดโดยใช้โทเค็นฝังตัว **Power BI** API ทำให้เขียนโปรแกรมในทรัพยากรบางอย่างของ **Power BI** ได้ สำหรับข้อมูลเพิ่มเติม ดู[ภาพรวมของ Power BI REST API](https://msdn.microsoft.com/library/dn877544.aspx)และ[Power BI .NET SDK ](https://github.com/Microsoft/PowerBI-CSharp)และ [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

## <a name="download-the-sample"></a>ดาวน์โหลดตัวอย่าง
บทความนี้แสดงรหัสที่ใช้ในการ[ฝังตัวสำหรับตัวอย่างขององค์กรของคุณ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)บน GitHub เพื่อติดตามการฝึกปฏิบัตินี้ คุณสามารถดาวน์โหลดตัวอย่างได้

## <a name="step-1---register-an-app-in-azure-ad"></a>ขั้นตอนที่ 1: ลงทะเบียนแอปใน Azure AD
คุณจะต้องลงทะเบียนแอปพลิเคชันของคุณกับ Azure AD เพื่อเรียกใช้ REST API สำหรับข้อมูลเพิ่มเติม ดู[ลงทะเบียนแอป Azure AD เพื่อฝังเนื้อหา Power BI](register-app.md)

ถ้าคุณดาวน์โหลดตัวอย่างการ[ฝังเพื่อองค์กรของคุณ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)คุณต้องใช้ **ID ไคลเอ็นต์**ที่คุณได้หลังการลงทะเบียน เพื่อให้ตัวอย่างสามารถรับรองความถูกต้องกับ Azure AD เมื่อต้องการกำหนดค่าตัวอย่าง เปลี่ยนคำ **clientId** ในไฟล์*web.config*

## <a name="step-2---get-an-access-token-from-azure-ad"></a>ขั้นตอนที่ 2 - รับโทเค็นการเข้าถึงจาก Azure AD
ภายในแอปพลิเคชันของคุณ คุณจะต้องรับ**โทเค็นการเข้าถึง**จาก Azure AD ก่อนที่จะสามารถเรียกใช้ Power BI REST API ได้ สำหรับข้อมูลเพิ่มเติม ดู[รับรองผู้ใช้ และรับโทเค็นการเข้าถึง Azure AD สำหรับแอป Power BI ของคุณ](get-azuread-access-token.md)

คุณสามารถดูตัวอย่างของสิ่งนี้ในงานแต่ละรายการเนื้อหาใน **Controllers\HomeController.cs** ได้

## <a name="step-3---get-a-content-item"></a>ขั้นตอนที่ 3 - รับรายการเนื้อหา
เมื่อต้องฝังเนื้อหา Power BI ของคุณ คุณจะจำเป็นต้องทำบางสิ่งให้แน่ใจว่า ได้ฝังอย่างถูกต้อง ในขณะที่ขั้นตอนเหล่านี้ทั้งหมดสามารถทำได้ด้วย REST API โดยตรง แอปพลิเคชันตัวอย่างและตัวอย่างที่นี่ี่ถูกสร้างด้วย NET SDK

### <a name="create-the-power-bi-client-with-your-access-token"></a>สร้างไคลเอ็นต์ Power BI ด้วยโทเค็นการเข้าถึงของคุณ
ด้วยโทเค็นการเข้าถึงของคุณ คุณจะสามารถสร้างวัตถุไคลเอ็นต์ Power BI ได้ซึ่งจะช่วยให้คุณสามารถโต้ตอบกับ Power BI APIs ทำสิ่งนี้ได้ โดยการตัด AccessToken ด้วยวัตถุ*Microsoft.Rest.TokenCredentials*ุ

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

### <a name="get-the-content-item-you-want-to-embed"></a>รับรายการเนื้อหาที่คุณต้องการฝัง
ใช้วัตถุไคลเอ็นต์ Power BI เพื่อเรียกใช้การอ้างอิงไปยังรายการที่คุณต้องการฝัง คุณสามารถฝังแดชบอร์ด ไทล์ หรือรายงาน นี่คือตัวอย่างของวิธีการเรียก แดชบอร์ด ไทล์ หรือแรกรายงานจากพื้นที่ทำงานที่ระบุ

ตัวอย่างนี้อยู่ใน**Controllers\HomeController.cs**ของตัวอย่าง[แอปที่เป็นเจ้าของข้อมูล](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

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
โทเค็นฝังตัวต้องถูกสร้างขึ้นซึ่งสามารถใช้งานจาก JavaScript API โทเค็นฝังตัวจะเป็นสิ่งเฉพาะสำหรับรายการที่คุณจะฝัง ซึ่งหมายความว่า เมื่อใดก็ตามที่คุณฝังเนื้อหา Power BI คุณจำเป็นต้องสร้างโทเค็นฝังตัวใหม่ สำหรับข้อมูลเพิ่มเติม ที่รวมถึงใช้ **accessLevel** ใด ดูที่[GenerateToken API](https://msdn.microsoft.com/library/mt784614.aspx)

> [!IMPORTANT]
> เนื่องจากโทเค็นการฝังมีไว้เพื่อทดสอบการพัฒนาเท่านั้น บัญชีหลักของ Power BI สามารถสร้างโทเค็นการฝังได้อย่างจำกัด หากต้องการใช้งาน [ต้องซื้อความสามารถ](https://docs.microsoft.com/power-bi/developer/embedded-faq#technical) สภาวะการฝังเพิ่อการผลิต ไม่มีข้อจำกัดการสร้างโทเค็นการฝังเมื่อซื้อความสามารถ

มีตัวอย่างนี้ใน**Controllers\HomeController.cs**ของการ[ฝังตัวอย่างข้อมูลขององค์กรของคุณ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

สิ่งนี้คาดว่ามีการสร้าง class สำหรับ**EmbedConfig**และ**TileEmbedConfig** มีตัวอย่างเหล่านี้ใน**Models\EmbedConfig.cs**และ**Models\TileEmbedConfig.cs**

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



## <a name="step-4---load-an-item-using-javascript"></a>ขั้นตอนที่ 4 - โหลดวัตถุต่างๆโดยใช้ JavaScript
คุณสามารถใช้ JavaScript เพื่อโหลดแดชบอร์ดลงในองค์ประกอบ div บนเว็บเพจของคุณ ตัวอย่างใช้โมเดล EmbedConfig/TileEmbedConfig พร้อมกับมุมมองสำหรับแดชบอร์ด ไทล์ หรือรายงาน สำหรับตัวอย่างแบบเต็มของการใช้ JavaScript API คุณสามารถใช้[ตัวอย่างของ Microsoft Power BI Embedded](https://microsoft.github.io/PowerBI-JavaScript/demo) ได้

ตัวอย่างเป็นแอปพลิเคชันนี้ที่อยู่ภายในการ[ฝังตัวเพื่อตัวอย่างขององค์กรของคุณ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

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
มีแอปตัวอย่างบน GitHub เพื่อให้คุณพิจารณา ตัวอย่างข้างต้นจะอิงกับตัวอย่างนั้น สำหรับข้อมูลเพิ่มเติม ดูการ[ฝังตัวเพื่อตัวอย่างขององค์กรของคุณ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data)

ข้อมูลเพิ่มเติมสำหรับ JavaScript API ดู [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


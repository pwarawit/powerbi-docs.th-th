---
title: รวมไทล์ Power BI ลงในแอปสำหรับองค์กรของคุณ
description: ฝึกปฏิบัติ การรวมไทล์ลงในแอป ตัวอย่างรหัส
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 02/13/2018
ms.author: maghan
ms.openlocfilehash: 6ad2138ab37b20fa16a5455ab167ec9e6b7e159c
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34288325"
---
# <a name="integrate-a-tile-into-an-app-user-owns-data"></a>รวมไทล์ลงในแอป (ผู้ใช้เป็นเจ้าของข้อมูล)
เรียนรู้วิธีการรวมหรือฝังตัวไทล์ ลงในเว็บแอปโดยใช้การเรียก REST API ตลอดจน Power BI JavaScript API เมื่อต้องการฝังตัวสำหรับองค์กรของคุณ

![ไทล์ที่ฝังตัวในเว็บแอปพลิเคชัน](media/integrate-tile/powerbi-embedded-tile.png)

เพื่อเริ่มต้นการฝึกปฏิบัตินี้ คุณต้องมีบัญชี **Power BI** ถ้าคุณยังไม่มีบัญชีผู้ใช้ คุณสามารถ[ลงทะเบียนเพื่อรับบัญชี Power BI ฟรี](../service-self-service-signup-for-power-bi.md) หรือคุณสามารถสร้าง [Azure Active Directory ระดับผู้เช่า](create-an-azure-active-directory-tenant.md)ของคุณเองเพื่อทดลองได้

> [!NOTE]
> กำลังหาวิธีฝังตัวไทล์สำหรับลูกค้าของคุณ โดยใช้โทเค็นการฝังตัวแทนหรือไม่? ดู[รวมแดชบอร์ด ไทล์ หรือรายงานลงในแอปพลิเคชันสำหรับลูกค้าของคุณ](embed-sample-for-customers.md)
> 
> 

เพื่อรวมไทล์ลงในเว็บแอป คุณใช้ **Power BI** REST API หรือ Power BI C# SDK และ**โทเค็นการเข้าถึง**การรับรองความถูกต้องของ Azure Active Directory (AD) เพื่อรับไทล์ จากนั้น คุณโหลดไทล์โดยใช้โทเค็นการเข้าถึงเดียวกัน **Power BI** API ให้การเข้าถึงทรัพยากรของ **Power BI** ผ่านทางโปรแกรม สำหรับข้อมูลเพิ่มเติม ดู[ภาพรวมของ Power BI REST API](https://msdn.microsoft.com/library/dn877544.aspx) และ [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

## <a name="download-the-sample"></a>ดาวน์โหลดตัวอย่าง
บทความนี้แสดงรหัสที่ใช้ใน [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) บน GitHub ถ้าต้องการทำตามการฝึกปฏิบัตินี้ คุณสามารถดาวน์โหลดตัวอย่างได้

## <a name="step-1---register-an-app-in-azure-ad"></a>ขั้นตอนที่ 1 - การลงทะเบียนแอปใน Azure AD
คุณจะต้องลงทะเบียนแอปพลิเคชันของคุณกับ Azure AD เพื่อเรียกใช้ REST API สำหรับข้อมูลเพิ่มเติม ดู[ลงทะเบียนแอป Azure AD เพื่อฝังเนื้อหา Power BI](register-app.md)

ถ้าคุณดาวน์โหลด [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) คุณใช้ **Client ID** และ **Client Secret** ที่คุณได้รับหลังการลงทะเบียน เพื่อให้ตัวอย่างสามารถรับรองความถูกต้องกับ Azure AD เพื่อกำหนดค่าตัวอย่าง เปลี่ยนค่า **Client ID** และ **Client Secret** ในไฟล์ *cloud.config*

![](media/integrate-tile/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>ขั้นตอนที่ 2 - รับโทเค็นการเข้าถึงจาก Azure AD
ภายในแอปพลิเคชันของคุณ คุณจะต้องรับ**โทเค็นการเข้า**จาก Azure AD ก่อนที่คุณสามารถเรียกใช้ Power BI REST API ได้ สำหรับข้อมูลเพิ่มเติม ดู[รับรองความถูกต้องผู้ใช้ และรับโทเค็นการเข้าถึง Azure AD สำหรับแอป Power BI ของคุณ](get-azuread-access-token.md)

## <a name="step-3---get-a-tile"></a>ขั้นตอนที่ 3 - รับไทล์
เพื่อรับไทล์ **Power BI** คุณใช้การดำเนินการ [รับไทล์](https://msdn.microsoft.com/library/mt465741.aspx) ที่รับรายการของไทล์ **Power BI** จากแดชบอร์ดที่ระบุ จากรายการของไทล์ คุณสามารถรับ รหัสไทล์ และ URL ที่ฝัง

คุณจำเป็นต้องดึงค่า รหัสแดชบอร์ด ก่อนถึงจะเรียกดูไทล์ได้ สำหรับข้อมูลเกี่ยวกับวิธีการดึงแดชบอร์ด ดู[รวมแดชบอร์ดลงในแอป (ผู้ใช้เป็นเจ้าของข้อมูล)](integrate-dashboard.md)

### <a name="get-tiles-using-an-access-token"></a>รับไทล์โดยใช้โทเค็นการเข้าถึง
ด้วย**โทเค็นการเข้าถึง** ที่คุณได้จาก[ขั้นตอนที่ 2](#step-2-get-an-access-token-from-azure-ad) คุณเรียกการดำเนินการ[รับไทล์](https://msdn.microsoft.com/library/mt465741.aspx)ได้ การดำเนินการ[รับไทล์](https://msdn.microsoft.com/library/mt465741.aspx) จะส่งรายการของไทล์กลับมา คุณสามารถรับไทล์เดียวจากรายการของไทล์ ด้านล่างนี้คือเมทอต C# ที่สมบูรณ์เพื่อจะรับไทล์ 

เพื่อเรียกใช้ REST API คุณต้องใส่ส่วนหัว *Authorization* ในรูปแบบ *Bearer {โทเค็นการเข้าถึง}*

#### <a name="get-tiles-with-the-rest-api"></a>รับไทล์ด้วย REST API
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a tile from a dashboard. In this sample, you get the first tile.
protected void GetTile(string dashboardId, int index)
{
    //Configure tiles request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}Dashboards/{1}/Tiles",
        baseUri,
        dashboardId)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get tiles response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBITiles tiles = JsonConvert.DeserializeObject<PBITiles>(reader.ReadToEnd());

            //Sample assumes at least one Dashboard with one Tile.
            //You could write an app that lists all tiles in a dashboard
            if (tiles.value.Length > 0)
                tileEmbedUrl.Text = tiles.value[index].embedUrl;
        }
    }
}

//Power BI Tiles used to deserialize the Get Tiles response.
public class PBITiles
{
    public PBITile[] value { get; set; }
}
public class PBITile
{
    public string id { get; set; }
    public string title { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-tiles-using-the-net-sdk"></a>รับไทล์โดยใช้ .NET SDK
คุณสามารถใช้ .NET SDK เพื่อดึงรายการแดชบอร์ดแทนการเรียกใช้ REST API โดยตรง

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get a list of dashboards your "My Workspace"
    ODataResponseListDashboard tiles = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    // Get the first tile from the above dashbaord
    ODataResponseListTile tiles = client.Dashboards.GetTiles(dashboard.Id);

    Tile tile = tiles.Value.FirstOrDefault();
}
```

## <a name="step-4---load-a-tile-using-javascript"></a>ขั้นตอนที่ 4 - โหลดไทล์โดยใช้ JavaScript
คุณสามารถใช้ JavaScript เพื่อโหลดไทล์ลงในองค์ประกอบ div บนเว็บเพจของคุณ

**Default.aspx**

```
<!-- Embed Tile-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a tile</div>

            <div>Enter an embed url for a tile from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedTileAction" value="Embed Tile" />
        </div>

        <div id="tileContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected tile.
    var el = document.getElementById("bEmbedTileAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedTile, false);
    } else {
        el.attachEvent('onclick', updateEmbedTile);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded tile if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedTile();
    }
};

// update embed tile
function updateEmbedTile() {

    // check if the embed url was selected
    var embedUrl = document.getElementById('tb_EmbedURL').value;
    if (embedUrl === "")
        return;

    // get the access token.
    accessToken = document.getElementById('MainContent_accessTokenTextbox').value;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the tile.
    var tileContainer = document.getElementById('tileContainer');

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);

    // tile.on will add an event handler which prints to Log window.
    tile.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

ถ้าคุณดาวน์โหลด และเรียกใช้ [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) ตัวอย่างจะดูคล้ายกับด้านล่างนี้

![ไทล์ที่ฝังตัวในเว็บแอปพลิเคชัน](media/integrate-tile/powerbi-embedded-tile.png)

## <a name="working-with-groups-app-workspaces"></a>การทำงานกับกลุ่ม (พื้นที่ทำงานแอป)
สำหรับการฝังตัวไทล์จากกลุ่ม (พื้นที่ทำงานแอป) คุณจะต้องการรับรายการของไทล์ที่มีอยู่ทั้งหมดภายในแดชบอร์ดของกลุ่มโดยการเรียก REST API ต่อไปนี้ เมื่อต้องการข้อมูลเพิ่มเติมเกี่ยวกับ REST API นี้ ดูที่[รับไทล์](https://msdn.microsoft.com/library/mt465741.aspx) คุณต้องมีสิทธิ์ในกลุ่มเพื่อให้คำขอส่งผลลัพธ์กลับมา

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards/{dashboard_id}/tiles
```

API ด้านบนส่งกลับรายการของไทล์ที่มี แต่ละไทล์มี คุณสมบัติ EmbedUrl ซึ่งจะถูกสร้างขึ้นไว้แล้ว เพื่อสนับสนุนการฝังตัวแบบกลุ่ม

```
https://app.powerbi.com/embed?dashboardId={dashboard_id}&tileId={tile_id}&groupId={group_id}
```

## <a name="next-steps"></a>ขั้นตอนถัดไป
[ไทล์ที่ฝังตัว](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Tile-Embed)บน Wiki PowerBI JavaScript

[Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

ตัวอย่าง [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) บน GitHub

คำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


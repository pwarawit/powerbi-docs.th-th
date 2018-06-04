---
title: รวมแดชบอร์ดลงในแอปสำหรับองค์กรของคุณ
description: เรียนรู้วิธีการรวม หรือฝังตัว แดชบอร์ดลงในเว็บแอปด้วย Power BI API
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 02/13/2018
ms.author: maghan
ms.openlocfilehash: 979b76350b9867bbc684a70bd89a82f88993e625
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34290280"
---
# <a name="integrate-a-dashboard-into-an-app-for-your-organization"></a>รวมแดชบอร์ดลงในแอปสำหรับองค์กรของคุณ
เรียนรู้วิธีการรวม หรือฝังตัว แดชบอร์ดลงในเว็บแอปโดยการเรียก REST API ตลอดจน Power BI JavaScript API เมื่อต้องการการฝังตัวสำหรับองค์กรของคุณ

![แดชบอร์ดแบบฝังตัว](media/integrate-dashboard/powerbi-embed-dashboard.png)

เพื่อเริ่มต้นการฝึกปฏิบัตินี้ คุณต้องมีบัญชี **Power BI** ถ้าคุณยังไม่มีบัญชีผู้ใช้ คุณสามารถ[ลงทะเบียนเพื่อรับบัญชี Power BI ฟรี](../service-self-service-signup-for-power-bi.md) หรือคุณสามารถสร้าง [Azure Active Directory ระดับผู้เช่า](create-an-azure-active-directory-tenant.md)เพื่อทดลองได้

> [!NOTE]
> กำลังมองหาการฝังแดชบอร์ดสำหรับลูกค้าของคุณ ด้วยการใช้โทเคนการฝังตัวแทนหรือไม่ ดู[รวมแดชบอร์ด ไทล์ หรือรายงานลงในแอปพลิเคชันสำหรับลูกค้าของคุณ](embed-sample-for-customers.md)
> 
> 

เพื่อรวมแดชบอร์ดลงในเว็บแอป คุณใช้ **Power BI** REST API หรือ Power BI C# SDK และ**โทเค็นการเข้าถึง**การรับรองความถูกต้องของ Azure Active Directory (AD) เพื่อรับแดชบอร์ด จากนั้น คุณโหลดแดชบอร์ดด้วยโทเค็นการเข้าถึงเดียวกัน **Power BI** API ให้การเข้าถึงทรัพยากรของ **Power BI** ผ่านทางโปรแกรม สำหรับข้อมูลเพิ่มเติม ดู[ภาพรวมของ Power BI REST API](https://msdn.microsoft.com/library/dn877544.aspx) และ [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

## <a name="download-the-sample"></a>ดาวน์โหลดตัวอย่าง
บทความนี้แสดงรหัสที่ใช้ใน [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) บน GitHub ถ้าต้องการทำตามการฝึกปฏิบัตินี้ คุณสามารถดาวน์โหลดตัวอย่างได้

## <a name="step-1---register-an-app-in-azure-ad"></a>ขั้นตอนที่ 1 - การลงทะเบียนแอปใน Azure AD
คุณจะต้องลงทะเบียนแอปพลิเคชันของคุณกับ Azure AD เพื่อเรียกใช้ REST API สำหรับข้อมูลเพิ่มเติม ดู[ลงทะเบียนแอป Azure AD เพื่อฝังเนื้อหา Power BI](register-app.md)

ถ้าคุณดาวน์โหลด[ตัวอย่างการรวมแดชบอร์ด](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) คุณใช้ **Client ID** และ **Client Secret** ที่คุณได้รับหลังการลงทะเบียน เพื่อให้ตัวอย่างสามารถรับรองความถูกต้องกับ Azure AD ได้ เพื่อกำหนดค่าตัวอย่าง เปลี่ยนค่า **Client ID** และ **Client Secret** ในไฟล์ *cloud.config*

![](media/integrate-dashboard/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>ขั้นตอนที่ 2 - รับโทเค็นการเข้าถึงจาก Azure AD
ภายในแอปพลิเคชันของคุณ คุณจะต้องรับ**โทเค็นการเข้า**จาก Azure AD ก่อนที่คุณสามารถเรียกใช้ Power BI REST API ได้ สำหรับข้อมูลเพิ่มเติม ดู[รับรองความถูกต้องผู้ใช้ และรับโทเค็นการเข้าถึง Azure AD สำหรับแอป Power BI ของคุณ](get-azuread-access-token.md)

## <a name="step-3---get-a-dashboard"></a>ขั้นตอนที่ 3 - รับแดชบอร์ด
เพื่อรับแดชบอร์ด **Power BI** คุณใช้การดำเนินการ[รับแดชบอร์ด](https://msdn.microsoft.com/library/mt465739.aspx) ซึ่งจะได้รายการแดชบอร์ดของ **Power BI** จากรายการแดชบอร์ด คุณสามารถรับรหัสแดชบอร์ด

![](media/integrate-dashboard/powerbi-embed-dashboard-get-dashboards.png)

### <a name="get-dashboards-using-an-access-token"></a>รับแดชบอร์ดโดยใช้โทเค็นการเข้าถึง
ด้วย**โทเค็นการเข้าถึง**ที่คุณได้ใน[ขั้นตอนที่ 2](#step-2-get-an-access-token-from-azure-ad) คุณสามารถเรียกใช้การดำเนินการ[รับแดชบอร์ด](https://msdn.microsoft.com/library/mt465739.aspx)ได้ ดำเนินการ[รับแดชบอร์ด](https://msdn.microsoft.com/library/mt465739.aspx)จะส่งรายการแดชบอร์ดกลับมา คุณสามารถรับแดชบอร์ดเดียวจากรายการแดชบอร์ดนี้ได้ ด้านล่างนี้คือเมทอต C# ที่สมบูรณ์สำหรับรับแดชบอร์ด 

เพื่อเรียกใช้ REST API คุณต้องใส่ส่วนหัว *Authorization* ในรูปแบบ *Bearer {โทเค็นการเข้าถึง}*

#### <a name="get-dashboards-with-the-rest-api"></a>รับแดชบอร์ดด้วย REST API
**Default.aspx.cs**

```
protected void getDashboardsButton_Click(object sender, EventArgs e)
{
    string responseContent = string.Empty;

    //Configure dashboards request
    System.Net.WebRequest request = System.Net.WebRequest.Create(String.Format("{0}dashboards", baseUri)) as System.Net.HttpWebRequest;
    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

    //Get dashboards response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            responseContent = reader.ReadToEnd();

            //Deserialize JSON string
            PBIDashboards PBIDashboards = JsonConvert.DeserializeObject<PBIDashboards>(responseContent);

            if (PBIDashboards != null)
            {
                var gridViewDashboards = PBIDashboards.value.Select(dashboard => new {
                    Id = dashboard.id,
                    DisplayName = dashboard.displayName,
                    EmbedUrl = dashboard.embedUrl
                });

                this.GridView1.DataSource = gridViewDashboards;
                this.GridView1.DataBind();
            }
        }
    }
}

//Power BI Dashboards used to deserialize the Get Dashboards response.
public class PBIDashboards
{
    public PBIDashboard[] value { get; set; }
}
public class PBIDashboard
{
    public string id { get; set; }
    public string displayName { get; set; }
    public string embedUrl { get; set; }
    public bool isReadOnly { get; set; }
}
```

#### <a name="get-dashboards-using-the-net-sdk"></a>รับแดชบอร์ดโดยใช้ .NET SDK
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
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    var embedUrl = dashboard.EmbedUrl
}
```

## <a name="step-4---load-a-dashboard-using-javascript"></a>ขั้นตอนที่ 4 - โหลดแดชบอร์ดโดยใช้ JavaScript
คุณสามารถใช้ JavaScript เพื่อโหลดแดชบอร์ดลงในองค์ประกอบ div บนเว็บเพจของคุณ

**Default.aspx**

```
<!-- Embed Dashboard-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a dashboard</div>

            <div>Enter an embed url for a dashboard from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedDashboardAction" value="Embed Dashboard" />
        </div>

        <div id="dashboardContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected dashboard.
    var el = document.getElementById("bEmbedDashboardAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedDashboard, false);
    } else {
        el.attachEvent('onclick', updateEmbedDashboard);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded dashboard if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedDashboard();
    }
};

// update embed dashboard
function updateEmbedDashboard() {

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
        type: 'dashboard',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the dashboard.
    var dashboardContainer = document.getElementById('dashboardContainer');

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("tileClicked", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

ถ้าคุณดาวน์โหลด และเรียกใช้[ตัวอย่างการรวมแดชบอร์ด](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) ตัวอย่างจะคล้ายกับรูปด้านล่างนี้

![](media/integrate-dashboard/powerbi-embed-dashboard.png)

## <a name="tile-clicked-events"></a>เหตุการณ์การคลิกไทล์
ในตัวอย่างด้านบน คุณอาจสังเกตเห็นว่า คุณสามารถจัดการเหตุการณ์เมื่อมีการคลิกที่ไทล์ในแดชบอร์ด สำหรับข้อมูลเพิ่มเติมเกี่ยวกับเหตุการณ์ ดู[จัดการเหตุการณ์ภายใน JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events)

```
// dashboard.on will add an event handler which prints to Log window.
dashboard.on("tileClicked", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});

// dashboard.on will add an event handler which prints to Log window.
dashboard.on("error", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Error<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});
```

ถ้าคุณดาวน์โหลด และเรียกใช้[ตัวอย่างการรวมแดชบอร์ด](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/PowerBI.com%20Integrate/integrate-dashboard-web-app) การคลิกบนไทล์จะแสดงผลข้อความใต้แดชบอร์ด ข้อความจะมีลักษณะคล้ายกับต่อไปนี้ ซึ่งจะช่วยให้คุณสามารถบันทึกการคลิกที่ไทล์ และจากนั้นนำทางผู้ใช้ไปยังตำแหน่งที่เหมาะสม

```
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "", "navigationUrl": "https://app.powerbi.com/dashboards/fcff76f9-15ff-4a8e-8242-275ac9c25b90/qna?q=count%20of%20new%20hires%20from%20July%202014%20to%20December%202014", "tileId": "0e99b45c-9b53-4920-b239-cee7d37d2369" }
---------
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "https://app.powerbi.com/reportEmbed?reportId=ab199308-80b1-4626-9823-43a84623bd9c", "navigationUrl": "https://app.powerbi.com/reports/ab199308-80b1-4626-9823-43a84623bd9c/ReportSection1", "tileId": "ffc30447-674a-4511-944f-79e182d719de", "pageName": "ReportSection1" }
---------
```

## <a name="working-with-groups-app-workspaces"></a>การทำงานกับกลุ่ม (พื้นที่ทำงานแอป)
สำหรับการฝังแดชบอร์ดจากกลุ่ม (พื้นที่ทำงานแอป) คุณจะรับรายการแดชบอร์ดที่มีทั้งหมดภายในกลุ่มโดยการเรียก REST API ต่อไปนี้ เมื่อต้องการข้อมูลเพิ่มเติมเกี่ยวกับการเรียก REST API นี้ ดู[รับแดชบอร์ด](https://msdn.microsoft.com/library/mt465739.aspx) คุณต้องมีสิทธิ์ในกลุ่มเพื่อให้คำขอส่งผลลัพธ์กลับมา

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards
```

API ด้านบนจะส่งกลับรายการของแดชบอร์ดที่มี แต่ละแดชบอร์ดมีคุณสมบัติ EmbedUrl ซึ่งถูกสร้างขึ้นแล้วเพื่อสนับสนุนการฝังตัวกลุ่ม

```
https://app.powerbi.com/dashboardEmbed?dashboardId={dashboardId}&groupId={groupId}
```

## <a name="limitations"></a>ข้อจำกัด
* ผู้ใช้ปลายทางที่เข้าถึงแดชบอร์ดแบบฝังตัวต้องมีบัญชี Power BI และมีสิทธิ์เข้าถึงแดชบอร์ด ไม่ว่าพวกเขาจะเป็นเจ้าของแดชบอร์ด หรือแดชบอร์ดที่ถูกแชร์ให้กับผู้ใช้
* ในขณะนี้ ยังไม่สนับสนุน ถามตอบ ในแดชบอร์ดแบบฝังตัว
* ข้อจำกัดชั่วคราว เมื่อมีการแชร์แดชบอร์ดกับกลุ่มความปลอดภัย ผู้ใช้ต้องเข้าถึงแดชบอร์ดใน PowerBI.com ก่อนที่พวกเขาเห็นแบบฝังตัวได้

## <a name="next-steps"></a>ขั้นตอนถัดไป
มีตัวอย่างแอปพลิเคชันบน GitHub ให้คุณได้ศึกษา ตัวอย่างต่าง ๆ ข้างบนมาจากตัวอย่างนั้น สำหรับข้อมูลเพิ่มเติม ดู [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app)

ข้อมูลเพิ่มเติมสำหรับ JavaScript API ดู [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

คำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


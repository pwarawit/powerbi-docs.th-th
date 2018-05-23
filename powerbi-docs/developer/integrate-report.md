---
title: รวมรายงาน Power BI ลงในแอปสำหรับองค์กรของคุณ
description: เรียนรู้วิธีการรวม หรือฝังรายงานลงในเว็บแอปโดยใช้ API ของ Power BI
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 10/05/2017
ms.author: maghan
ms.openlocfilehash: d2fa65587fdbd85aabd429d531b79e9e614d2f49
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/17/2018
---
# <a name="integrate-a-report-into-an-app-for-your-organization"></a>รวมรายงานลงในแอปสำหรับองค์กรของคุณ
เรียนรู้วิธีการรวม หรือฝังรายงานลงในเว็บแอปโดยใช้การเรียกใช้ REST API พร้อมกับ Power BI JavaScript API เมื่อทำการฝังสำหรับองค์กรของคุณ

![ตัวอย่างรายงานที่ฝังตัว](media/integrate-report/powerbi-embedded-report.png)

เมื่อต้องการเริ่มต้นใช้งานการฝึกปฏิบัตินี้ คุณต้องมีบัญชี**Power BI** ถ้าคุณไม่มีบัญชีผู้ใช้ คุณสามารถ[ลงทะเบียนเพื่อรับบัญชี Power BI ฟรี](../service-self-service-signup-for-power-bi.md)หรือคุณสามารถสร้าง [Azure Active Directory ระดับผู้เช่า](create-an-azure-active-directory-tenant.md)ของคุณเพื่อลองทดสอบ

> [!NOTE]
> กำลังมองหาการฝังรายงานสำหรับลูกค้าของคุณด้วยการใช้ embedtoken แทนที่จะใช้วิธีอื่นหรือไม่ ดู[รวมแดชบอร์ด ไทล์ หรือรายงานลงในแอปพลิเคชันสำหรับลูกค้าของคุณ](embed-sample-for-customers.md)
> 
> 

เมื่อต้องรวมในรายงานลงในเว็บแอป คุณต้องใช้ **Power BI** REST API หรือ Power BI C# SDK และ**โทเค็นการเข้าถึง**การตรวจสอบ Azure Active Directory (AD) เพื่อรับรายงาน จากนั้น คุณสามารถโหลดรายงานโดยใช้โทเค็นการเข้าถึงเดียวกัน **Power BI** API ทำให้เขียนโปรแกรมในทรัพยากรบางอย่างของ **Power BI** ได้ สำหรับข้อมูลเพิ่มเติม ดู[ภาพรวมของ Power BI REST API](https://msdn.microsoft.com/library/dn877544.aspx) และ [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

## <a name="download-the-sample"></a>ดาวน์โหลดตัวอย่าง
บทความนี้แสดงรหัสที่ใช้ในการ[รวมรายงานลงในแอปบนเว็บ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app)บน GitHub เพื่อติดตามการฝึกปฏิบัตินี้ คุณสามารถดาวน์โหลดตัวอย่างได้

## <a name="step-1---register-an-app-in-azure-ad"></a>ขั้นตอนที่ 1 - การลงทะเบียนแอปใน Azure AD
คุณจะต้องลงทะเบียนแอปพลิเคชันของคุณกับ Azure AD เพื่อเรียกใช้ REST API สำหรับข้อมูลเพิ่มเติม ดู[ลงทะเบียนแอป Azure AD เพื่อฝังเนื้อหา Power BI](register-app.md)

ถ้าคุณดาวน์โหลดการ[รวมรายงานลงในแอปบนเว็บ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app)คุณต้องใช้ **ID ไคลเอ็นต์** และ **Client Secret** ที่คุณได้รับหลังการลงทะเบียน เพื่อให้ตัวอย่างสามารถรับรองความถูกต้องต่อ Azure AD ได้ เพื่อกำหนดค่าตัวอย่าง เปลี่ยน **ID ไคลเอ็นต์**และ **Client Secret** ในไฟล์ *cloud.config*

![](media/integrate-report/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>ขั้นตอนที่ 2 - รับโทเค็นการเข้าถึงจาก Azure AD
ภายในแอปพลิเคชันของคุณ คุณจะต้องรับ**โทเค็นการเข้าถึง**จาก Azure AD ก่อนที่คุณสามารถเรียกใช้ Power BI REST API ได้ สำหรับข้อมูลเพิ่มเติม ดู[รับรองผู้ใช้ และรับโทเค็นการเข้าถึง Azure AD สำหรับแอป Power BI ของคุณ](get-azuread-access-token.md)

## <a name="step-3---get-a-report"></a>ขั้นตอนที่ 3 - รับรายงาน
เมื่อต้องการรับรายงาน**Power BI**คุณต้องใช้[Get Reports](https://msdn.microsoft.com/library/mt634543.aspx) operation ที่รับรายการของรายงาน**Power BI** จากรายชื่อของรายงาน คุณสามารถรับรหัสรายงานได้

### <a name="get-reports-using-an-access-token"></a>รับรายงานโดยใช้โทเค็นการเข้าถึง
ด้วยการ**โทเค็นการเข้าถึง**ที่คุณเรียกใช้ตาม[ขั้นตอนที่ 2](#step-2-get-an-access-token-from-azure-ad) คุณสามารถเรียกการดำเนินการ[รับรายงาน](https://msdn.microsoft.com/library/mt634543.aspx)ได้ [Get Reports](https://msdn.microsoft.com/library/mt634543.aspx)operation จะส่งคืนค่ารายการของรายงาน จากรายการของรายงาน คุณสามารถรับรายงานชิ้นหนึ่ง ด้านล่างนี้คือC# method ที่่สมบูรณ์ที่จะทำให้ได้รับรายงาน 

เมื่อต้องเรียก REST API คุณต้องใส่ส่วนหัวที่เป็นข้อมูลการให้สิทธิ์(*Authroization*) ในรูปแบบ *Bearer {โทเค็นการเข้าถึง}*

#### <a name="get-reports-with-the-rest-api"></a>รับรายงาน ด้วย REST API
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a Report. In this sample, you get the first Report.
protected void GetReport(int index)
{
    //Configure Reports request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}/Reports",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get Reports response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIReports Reports = JsonConvert.DeserializeObject<PBIReports>(reader.ReadToEnd());

            //Sample assumes at least one Report.
            //You could write an app that lists all Reports
            if (Reports.value.Length > 0)
            {
                var report = Reports.value[index];

                txtEmbedUrl.Text = report.embedUrl;
                txtReportId.Text = report.id;
                txtReportName.Text = report.name;
            }
        }
    }
}

//Power BI Reports used to deserialize the Get Reports response.
public class PBIReports
{
    public PBIReport[] value { get; set; }
}
public class PBIReport
{
    public string id { get; set; }
    public string name { get; set; }
    public string webUrl { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-reports-using-the-net-sdk"></a>รับรายงานโดยใช้.NET SDK
คุณสามารถใช้ .NET SDK เพื่อเรียกดูรายการของรายงานแทนที่จะเรียก REST API โดยตรง

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

## <a name="step-4---load-a-report-using-javascript"></a>ขั้นตอนที่ 4 - โหลดรายงานโดยใช้ JavaScript
คุณสามารถใช้ JavaScript เพื่อโหลดรายงานลงในองค์ประกอบ div บนเว็บเพจของคุณ

**Default.aspx**

```
<!-- Embed Report-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a report</div>

            <div>Enter an embed url for a report from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedReportAction" value="Embed Report" />
        </div>

        <div id="reportContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected report.
    var el = document.getElementById("bEmbedReportAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedReporte, false);
    } else {
        el.attachEvent('onclick', updateEmbedReport);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded report if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedReport();
    }
};

// update embed report
function updateEmbedReport() {

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
        type: 'report',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the report.
    var reportContainer = document.getElementById('reportContainer');

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);

    // report.on will add an event handler which prints to Log window.
    report.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

ถ้าคุณดาวน์โหลดและรัน[รวมรายงานในแอปบนเว็บ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app)ตัวอย่างจะมีลักษณะคล้ายกับด้านล่างนี้

![ตัวอย่างรายงานที่ฝังตัว](media/integrate-report/powerbi-embedded-report.png)

## <a name="working-with-groups-app-workspaces"></a>ทำงานกับกลุ่ม (พื้นที่ทำงานของแอป)
สำหรับการฝังรายงานหนึ่งๆจากกลุ่ม (พื้นที่ทำงานของแอป) คุณจะต้องรับรายการของรายงานที่พร้อมใช้ทั้งหมดภายในแดชบอร์ดของกลุ่มโดยการเรียกใช้ REST API ต่อไปนี้ เมื่อต้องการค้นหาข้อมูลเพิ่มเติมเกี่ยวกับการเรียกใช้ REST API นี้ ดู[Get Reports](https://msdn.microsoft.com/library/mt634543.aspx) คุณจะต้องมีสิทธิ์ในกลุ่มเพื่อขอส่งคืนค่าผลลัพธ์

```
https://api.powerbi.com/v1.0/myorg/groups/{group_id}/reports
```

API ด้านบนจะส่งกลับรายการของรายงานที่พร้อมใช้งาน แต่ละรายงานมีคุณสมบัติ EmbedUrl ซึ่งถูกสร้างขึ้นแล้วเพื่อสนับสนุนการฝังตัวในกลุ่ม

```
https://app.powerbi.com/reportEmbed?reportId={report_id}&groupId={group_id}
```

## <a name="next-steps"></a>ขั้นตอนถัดไป
มีแอปตัวอย่างบน GitHub เพื่อให้คุณพิจารณา สำหรับข้อมูลเพิ่มเติม ดู[รวมรายงานในแอปบนเว็บ](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app)

ข้อมูลเพิ่มเติมสำหรับ JavaScript API ดู [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

คำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


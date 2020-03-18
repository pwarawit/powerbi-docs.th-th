---
title: โค้ดสำหรับการโยกย้ายเนื้อหาจาก Power BI Embedded
description: ต่อไปนี้คือโค้ดบางอย่างของการดำเนินงานพื้นฐานที่จำเป็นสำหรับการโยกย้ายเนื้อหา
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: f4644ad8aa5fc0e6be1d336f66285f7d944d8e98
ms.sourcegitcommit: abc8419155dd869096368ba744883b865c5329fa
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/18/2020
ms.locfileid: "79487227"
---
# <a name="code-snippets-for-migrating-content-from-power-bi-workspace-collection"></a>โค้ดสำหรับการโยกย้ายเนื้อหาจากคอลเลกชันพื้นที่ทำงานของ Power BI

ต่อไปนี้คือโค้ดบางอย่างของการดำเนินงานพื้นฐานที่จำเป็นสำหรับการโยกย้ายเนื้อหา สำหรับขั้นตอนที่เกี่ยวข้องกับรายงานบางชนิด ดู[วิธีการโยกย้ายเนื้อหาคอลเลกชันของพื้นที่ทำงาน Power BI ไปยัง Power BI Embedded](migrate-from-powerbi-embedded.md#content-migration)

A **เครื่องมือการโยกย้าย**จะพร้อมใช้งานเพื่อให้คุณใช้เพื่อช่วยเหลือเกี่ยวกับการคัดลอกเนื้อหาจาก Power BI Embedded (PaaS) ไปยังบริการ Power BI (SaaS) โดยเฉพาะอย่างยิ่งถ้าคุณมีเนื้อหาจำนวนมาก สำหรับข้อมูลเพิ่มเติม ดู[เครื่องมือการโยกย้าย Power BI Embedded](migrate-tool.md)

รหัสด้านล่างนี้คือ ตัวอย่างที่ใช้ C# และ[Power BI .NET SDK](https://www.nuget.org/profiles/powerbi)

ตรวจสอบให้แน่ใจว่า คุณกำลังใช้ใน namespace ต่อไปนี้เพื่อดำเนินการโค้ดด้านล่าง

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V1;
using Microsoft.PowerBI.Api.V1.Models;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;
using Microsoft.Rest;
using Microsoft.Rest.Serialization;
using Newtonsoft.Json;
using Newtonsoft.Json.Linq;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Net;
using System.Net.Http;
using System.Net.Http.Headers;
using System.Text;
using System.Threading.Tasks;
```

## <a name="export-report-from-paas-workspace"></a>ส่งออกรายงานจากพื้นที่ทำงาน PaaS

```csharp
    // Create a token credentials with "AppKey" type
    var credentials = new TokenCredentials(<myAppKey==>, "AppKey");

    // Instantiate your Power BI client passing in the required credentials
    var client = new PowerBIClient(credentials);

    client.BaseUri = new Uri("https://api.powerbi.com");

    var response = client.Reports.ExportReportWithHttpMessagesAsync(<myWorkspaceCollectionName>, <myWorkspaceId>, <myReportId>);

    if (response.Result.Response.StatusCode == HttpStatusCode.OK)
    {
        var stream = response.Result.Response.Content.ReadAsStreamAsync();

        using (FileStream fileStream = File.Create(@"C:\Migration\myfile.pbix"))
        {
            stream.Result.CopyTo(fileStream);
            fileStream.Close();
        }
    }
```

## <a name="import-report-to-saas-workspace"></a>นำเข้ารายงานไปยังพื้นที่ทำงาน SaaS

```csharp
    AuthenticationContext authContext = new AuthenticationContext("https://login.microsoftonline.net/common/");
    var PBISaaSAuthResult = authContext.AcquireToken("https://analysis.windows.net/powerbi/api", <myClientId>, new Uri("urn:ietf:wg:oauth:2.0:oob"), PromptBehavior.Always);
    var credentials = new TokenCredentials(PBISaaSAuthResult.AccessToken);
    var client = new PowerBIClient(new Uri($"{"https://api.powerbi.com"}"), credentials);
    using (var file = File.Open(@"C:\Migration\myfile.pbix", FileMode.Open))
    {
        client.Imports.PostImportWithFileInGroup(<mySaaSWorkspaceId>, file, "importedreport", "Abort");
        while (true) ;
    }
```

## <a name="extract-directquery-connection-string-from-paas-report"></a>สำหรับตัวอย่าง ดูที่สตริงการเชื่อมต่อ “DirectQuery ที่แยกออก” จากรายงาน PaaS

นี่คือการปรับปรุง PBIX หลังจากการโยกย้ายไปยัง SaaS

```csharp
    // Extract connection string from PaaS - DirectQuery report
    // Create a token credentials with "AppKey" type
    var credentials = new TokenCredentials(<myAppKey==>, "AppKey");

    // Instantiate your Power BI client passing in the required credentials
    var client = new PowerBIClient(credentials);

    client.BaseUri = new Uri("https://api.powerbi.com");

    var reports = client.Reports.GetReports(<myWorkspaceCollectionName>, <myWorkspaceId>);

    Report report = reports.Value.FirstOrDefault(r => string.Equals(r.Id, <myReportId, StringComparison.OrdinalIgnoreCase));

    var datasource = client.Datasets.GetDatasources(<myWorkspaceCollectionName>, <myWorkspaceId>, report.DatasetId);
```

## <a name="update-directquery-connection-string-is-saas-workspace"></a>การอัปเดตสตริงเชื่อมต่อ DirectQuery คือ พื้นที่ทำงาน SaaS

```csharp
    public class ConnectionString
    {
        [JsonProperty(PropertyName = "connectionString")]
        public string connection { get; set; }
    }

    AuthenticationContext authContext = new AuthenticationContext("https://login.microsoftonline.net/common/");
    var PBISaaSAuthResult = authContext.AcquireToken("https://analysis.windows.net/powerbi/api",<myclient_id>, new Uri("urn:ietf:wg:oauth:2.0:oob"), PromptBehavior.Always);
    var credentials = new TokenCredentials(PBISaaSAuthResult.AccessToken);
    var client = new PowerBIClient(new Uri($"{"https://api.powerbi.com"}"), credentials);

    ConnectionString connection = new ConnectionString() { connection = "data source = <server_name>; initial catalog = <db_name>; persist security info = True; encrypt = True; trustservercertificate = False" };

    client.Datasets.SetAllConnectionsInGroup(<myWorkspaceId>, <dataset_id>, connection);
```

## <a name="set-directquery-credentials-in-saas-workspace"></a>ตั้งค่าข้อมูลประจำตัวของ DirectQuery ในพื้นที่ทำงาน SaaS

ในส่วนย่อยนี้ เราจะใช้ข้อมูลประจำตัวการเข้ารหัสลับสำหรับความสะดวกสบาย ส่งข้อมูลประจำตัวเข้ารหัสลับได้รับการสนับสนุนเช่นกัน

```csharp
    public class ConnectionString
    {
        [JsonProperty(PropertyName = "connectionString")]
        public string connection { get; set; }
    }

    public class BasicCreds
    {
        [JsonProperty(PropertyName = "username")]
        public string user { get; set; }

        [JsonProperty(PropertyName = "password")]
        public string pwd { get; set; }
    }

    var basicCreds = new BasicCreds() { user = <sqldb_username>, pwd = <sqldb_password> };
    var body = new SetCredsRequestBody() { credentialType = "Basic", basicCredentials = basicCreds };

    var url = string.Format("https://api.powerbi.com/v1.0/myorg/gateways/{0}/datasources/{1}", <gateway_id>, <datasource_id>);
    var request = new HttpRequestMessage(new HttpMethod("PATCH"), url);
    // Set authorization header from you acquired Azure AD token
    AuthenticationContext authContext = new AuthenticationContext("https://login.microsoftonline.net/common/");
    var PBISaaSAuthResult = authContext.AcquireToken("https://analysis.windows.net/powerbi/api", <myclient_id>, new Uri("urn:ietf:wg:oauth:2.0:oob"), PromptBehavior.Always);

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", PBISaaSAuthResult.AccessToken);

    request.Content = new StringContent(JsonConvert.SerializeObject(body), Encoding.UTF8, "application/json");

    HttpClient simpleClient = new HttpClient();
    var response = await simpleClient.SendAsync(request);
```

## <a name="push-dataset--report"></a>ผลักชุดข้อมูลและรายงาน

คุณจะต้องสร้างรายงานสำหรับชุดข้อมูลสร้างขึ้น

ในส่วนย่อยนี้ เราคาดว่าชุดข้อมูลที่สามารถผลักได้นั้นอยู่ในพื้นที่ทำงานภายในสภาพแวดล้อม SaaS อยู่แล้ว สำหรับข้อมูลเกี่ยวกับ push API ดูที่[ผลักข้อมูลลงในชุดข้อมูล Power BI](automation/walkthrough-push-data.md)

```csharp
    var credentials = new TokenCredentials(<Your WSC access key>, "AppKey");

    // Instantiate your Power BI client passing in the required credentials
    var client = new Microsoft.PowerBI.Api.V1.PowerBIClient(credentials);
    client.BaseUri = new Uri("https://api.powerbi.com");

    // step 1 -> create dummy dataset at PaaS workspace
    var fileStream = File.OpenRead(<Path to your dummy dataset>);
    var import = client.Imports.PostImportWithFileAsync(<Your WSC NAME>, <Your workspace ID>, fileStream, "dummyDataset");
    while (import.Result.ImportState != "Succeeded" && import.Result.ImportState != "Failed")
    {
        import = client.Imports.GetImportByIdAsync(<Your WSC NAME>, <Your workspace ID>, import.Result.Id);
        Thread.Sleep(1000);
    }
    var dummyDatasetID = import.Result.Datasets[0].Id;

    // step 2 -> clone the pushable dataset and rebind to dummy dataset
    var cloneInfo = new Microsoft.PowerBI.Api.V1.Models.CloneReportRequest("pushableReportClone",null, dummyDatasetID);
    var clone = client.Reports.CloneReportAsync(<Your WSC NAME>, <Your workspace ID>, <Your pushable report ID>, cloneInfo);
    var pushableReportCloneID = clone.Result.Id;


    // step 3 -> Download the push API clone report with the dummy dataset
    var response = client.Reports.ExportReportWithHttpMessagesAsync(<Your WSC NAME>, <Your workspace ID>, pushableReportCloneID);
    if (response.Result.Response.StatusCode == HttpStatusCode.OK)
    {
        var stream = response.Result.Response.Content.ReadAsStreamAsync();
        using (fileStream = File.Create(@"C:\Migration\PushAPIReport.pbix"))
        {
            stream.Result.CopyTo(fileStream);
            fileStream.Close();
        }
    }

    // step 4 -> Upload dummy PBIX to SaaS workspace
    AuthenticationContext authContext = new AuthenticationContext("https://login.microsoftonline.net/common/");
    var PBISaaSAuthResult = authContext.AcquireToken("https://analysis.windows.net/powerbi/api", <Your client ID>, new Uri("urn:ietf:wg:oauth:2.0:oob"), PromptBehavior.Always);
    var credentialsSaaS = new TokenCredentials(PBISaaSAuthResult.AccessToken);
    var clientSaaS = new Microsoft.PowerBI.Api.V2.PowerBIClient(new Uri($"{"https://api.powerbi.com"}"), credentialsSaaS);
    using (var file = File.Open(@"C:\Migration\PushAPIReport.pbix", FileMode.Open))
    {

        var importSaaS = clientSaaS.Imports.PostImportWithFileAsyncInGroup(<Your GroupID>, file, "importedreport1", "Abort");
        while (importSaaS.Result.ImportState != "Succeeded" && importSaaS.Result.ImportState != "Failed")
        {
            importSaaS = clientSaaS.Imports.GetImportByIdAsync(importSaaS.Result.Id);
            Thread.Sleep(1000);
        }
        var importedreport1ID = importSaaS.Result.Reports[0].Id;


        // step 5 -> Rebind report to "real" push api dataset
        var rebindInfoSaaS = new Microsoft.PowerBI.Api.V2.Models.RebindReportRequest(<Your pushable dataset  ID at power bi>);
        var rebindSaaS = clientSaaS.Reports.RebindReportInGroupWithHttpMessagesAsync(<Your GroupID>, importedreport1ID, rebindInfoSaaS);

    }
```

## <a name="next-steps"></a>ขั้นตอนถัดไป

[เครื่องมือการโยกบ้าย Power BI Embedded](migrate-tool.md)  
[การฝังด้วย Power BI](embedding.md)  
[วิธีการย้ายเนื้อหาคอลเลกชันพื้นที่ทำงานแบบฝัง Power BI ไปยัง Power BI](migrate-from-powerbi-embedded.md)  
[วิธีฝัง Power BI แดชบอร์ด รายงาน และไทล์](embedding-content.md)  
[Power BI Premium คืออะไร](../service-premium-what-is.md)  
[พื้นที่เก็บข้อมูลของ JavaScript API Git](https://github.com/Microsoft/PowerBI-JavaScript)  
[Power BI C# Git repo](https://github.com/Microsoft/PowerBI-CSharp)  
[ตัวอย่างการฝัง JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[เอกสารบรรยายแนวความคิดของ Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)

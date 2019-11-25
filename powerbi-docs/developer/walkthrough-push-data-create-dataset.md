---
title: สร้างชุดข้อมูล
description: การฝึกปฏิบัติ - พุชข้อมูลลงในชุดข้อมูล - สร้างชุดข้อมูลใน Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: 2a6c6a0e7860698ffd02625a413ca154898aab3b
ms.sourcegitcommit: c395fe83d63641e0fbd7c98e51bbab224805bbcc
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/21/2019
ms.locfileid: "74264970"
---
# <a name="step-3-create-a-dataset-in-power-bi"></a>ขั้นตอนที่ 3: สร้างชุดข้อมูลใน Power BI
บทความนี้เป็นส่วนหนึ่งของคำแนะนำทีละขั้นตอนเพื่อ[ส่งข้อมูลไปยังชุดข้อมูล](walkthrough-push-data.md)

ใน**ขั้นตอนที่ 2** ของการฝึกปฏิบัติ พุชข้อมูลลงในชุดข้อมูล เรื่อง[รับโทเคนการเข้าถึงการรับรองความถูกต้อง](walkthrough-push-data-get-token.md) คุณได้รับโทเค็นการรับรองความถูกต้องกับ **Azure AD** แล้ว ในขั้นตอนนี้ คุณจะใช้โทเค็นเพื่อเรียกการดำเนินการ [โพสต์ชุดข้อมูล](https://docs.microsoft.com/rest/api/power-bi/pushdatasets)

เพื่อเรียกไปยังทรัพยากร REST คุณใช้ url ที่ระบุตำแหน่งทรัพยากร และคุณส่งสตริง JavaScript Object Notation (JSON) ซึ่งอธิบายชุดข้อมูล ไปยังทรัพยากรของ บริการของ Power BI ทรัพยากร REST ระบุส่วนของบริการของ Power BI ที่คุณต้องการทำงานด้วย เพื่อพุชข้อมูลลงในชุดข้อมูล ทรัพยากรเป้าหมาย คือ**ชุดข้อมูล** URL ที่ระบุชุดข้อมูลคือ https://api.PowerBI.com/v1.0/myorg/datasets ถ้าคุณกำลังพุชข้อมูลภายในกลุ่ม ค่า URL คือ https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets

เพื่อรับรองความถูกต้องของการดำเนินการ Power BI REST คุณเพิ่มโทเค็นคุณที่คุณได้รับจาก[รับโทเคนการเข้าถึงการรับรองความถูกต้อง](walkthrough-push-data-get-token.md) เข้าไปในส่วนหัวของคำขอ:

เมื่อคุณเรียกใช้การดำเนินการ[โพสต์ชุดข้อมูล](https://docs.microsoft.com/rest/api/power-bi/pushdatasets) ชุดข้อมูลใหม่จะถูกสร้างขึ้น 

![](media/walkthrough-push-data-create-dataset/powerbi-developer-create-dataset.png)

นี่คือวิธีการสร้างชุดข้อมูลใน Power BI

## <a name="create-a-dataset-in-power-bi"></a>สร้างชุดข้อมูลใน Power BI
> [!NOTE]
> ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่า คุณดำเนินตามขั้นตอนก่อนหน้านี้ในการฝึกปฏิบัติ[พุชข้อมูลลงในชุดข้อมูล](walkthrough-push-data.md)แล้ว
> 
> 

1. ในโครงการแอปพลิเคชันคอนโซลที่คุณสร้างขึ้นใน[ขั้นตอนที่ 2 - รับโทเค็นการเข้าถึงการรับรองความถูกต้อง](walkthrough-push-data-get-token.md) เพิ่ม**using System.Net;** และ **using System.IO;** ลงใน Program.cs
2. ใน Program.cs เพิ่มรหัสด้านล่าง
3. เรียกใช้แอปคอนโซลนี้ และเข้าสู่ระบบด้วยบัญชี Power BI ของคุณ คุณควรเห็น **Dataset Created** ในหน้าต่างคอนโซล นอกจากนี้ คุณยังสามารถเข้าสู่ระบบไปยัง Power BI เพื่อดูชุดข้อมูลใหม่

**ตัวอย่างพุชข้อมูลลงในชุดข้อมูล**

เพิ่มรหัสนี้ลงใน Program.cs

* ใน static void Main(string[] args):
  
    ```csharp
    static void Main(string[] args)
    {
        //Get an authentication access token
        token = GetToken();
  
        //Create a dataset in Power BI
        CreateDataset();
    }
    ```
* เพิ่มเมธอด CreateDataset():
  
    ```csharp
    #region Create a dataset in Power BI
    private static void CreateDataset()
    {
        //TODO: Add using System.Net and using System.IO
  
        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "POST";
        request.ContentLength = 0;
        request.ContentType = "application/json";
  
        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));
  
        //Create dataset JSON for POST request
        string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
            "[{\"name\": \"Product\", \"columns\": " +
            "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
            "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
            "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
            "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
            "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
            "]}]}";
  
        //POST web request
        byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
        request.ContentLength = byteArray.Length;
  
        //Write JSON byte[] into a Stream
        using (Stream writer = request.GetRequestStream())
        {
            writer.Write(byteArray, 0, byteArray.Length);
  
            var response = (HttpWebResponse)request.GetResponse();
  
            Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));
  
            Console.ReadLine();
        }
    }
    #endregion
    ```

ขั้นตอนถัดไปจะแสดงวิธีการ[รับชุดข้อมูลเพื่อเพิ่มแถวลงในตาราง Power BI](walkthrough-push-data-get-datasets.md)

ด้านล่างนี้คือการ[รายการหัสที่สมบูรณ์](#code)

<a name="code"/>

## <a name="complete-code-listing"></a>รายการรหัสเสร็จสมบูรณ์

```csharp
using System;
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using System.Net;
using System.IO;

namespace walkthrough_push_data
{
    class Program
    {
        private static string token = string.Empty;

        static void Main(string[] args)
        {

            //Get an authentication access token
            token = GetToken();

            //Create a dataset in Power BI
            CreateDataset();

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


        #region Create a dataset in Power BI
        private static void CreateDataset()
        {
            //TODO: Add using System.Net and using System.IO

            string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
            //POST web request to create a dataset.
            //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
            HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
            request.KeepAlive = true;
            request.Method = "POST";
            request.ContentLength = 0;
            request.ContentType = "application/json";

            //Add token to the request header
            request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

            //Create dataset JSON for POST request
            string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
                "[{\"name\": \"Product\", \"columns\": " +
                "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
                "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
                "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
                "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
                "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
                "]}]}";

            //POST web request
            byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
            request.ContentLength = byteArray.Length;

            //Write JSON byte[] into a Stream
            using (Stream writer = request.GetRequestStream())
            {
                writer.Write(byteArray, 0, byteArray.Length);

                var response = (HttpWebResponse)request.GetResponse();

                Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));

                Console.ReadLine();
            }
        }
        #endregion
    }
}
```

[ขั้นตอนถัดไป >](walkthrough-push-data-get-datasets.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[รับชุดข้อมูลเพื่อเพิ่มแถวลงในตาราง Power BI](walkthrough-push-data-get-datasets.md)  
[รับโทเค็นการเข้าถึงการรับรองความถูกต้อง](walkthrough-push-data-get-token.md)  
[โพสต์ชุดข้อมูล](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset)  
[โพสต์ชุดข้อมูลในกลุ่ม](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdatasetingroup)  
[พุชข้อมูลลงในแดชบอร์ด Power BI](walkthrough-push-data.md)  
[ภาพรวมของ Power BI REST API](overview-of-power-bi-rest-api.md)  
[การอ้างอิง Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/)  

คุณมีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)


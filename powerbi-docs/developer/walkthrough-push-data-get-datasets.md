---
title: รับชุดข้อมูลเพื่อเพิ่มแถว
description: คำแนะนำสำหรับการส่งข้อมูล - รับชุดข้อมูลเพื่อเพิ่มแถวลงในตาราง Power BI
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: c0a70339e8336f3e7b93b40ad8a99dcb87715812
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "65710247"
---
# <a name="step-4-get-a-dataset-to-add-rows-into-a-power-bi-table"></a>ขั้นตอนที่ 4: รับชุดข้อมูลเพื่อเพิ่มแถวลงในตาราง Power BI

บทความนี้เป็นส่วนหนึ่งของคำแนะนำทีละขั้นตอนเพื่อ[ส่งข้อมูลไปยังชุดข้อมูล](walkthrough-push-data.md)

ใน**ขั้นตอนที่ 3**เป็นขั้นตอนการส่งข้อมูลไปยังชุดข้อมูล[สร้างชุดข้อมูลใน Power BI](walkthrough-push-data-create-dataset.md)คุณเรียกใช้การดำเนินการ[สร้างชุดข้อมูล](https://docs.microsoft.com/rest/api/power-bi/datasets)เพื่อสร้างชุดข้อมูลใน Power BI ในขั้นตอนนี้ ให้คุณใช้การดำเนินการ[รับชุดข้อมูล](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets)และ Newtonsoft.Json เพื่อรับรหัสชุดข้อมูล คุณสามารถใช้รหัสชุดข้อมูลในขั้นตอนที่ 4 เพื่อเพิ่มแถวไปยังชุดข้อมูล 

เมื่อต้องส่งข้อมูลไปยังชุดข้อมูล Power BI คุณจำเป็นต้องอ้างอิงตารางในชุดข้อมูล เมื่อต้องการอ้างอิงตารางในชุดข้อมูล ก่อนอื่นคุณต้องได้รับ**รหัสชุดข้อมูล** คุณจะได้รับ**รหัสชุดข้อมูล**โดยใช้การดำเนินการ[รับชุดข้อมูลจากรหัส](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasetbyid) การดำเนินการ**รับชุดข้อมูลจากรหัส** จะส่งคืนสตริง JSON ที่ประกอบด้วยรายการของชุดข้อมูลทั้งหมดใน Power BI วิธีแนะนำในการยกเลิกการจัดลำดับสตริง JSON อยู่ใน[Newtonsoft.Json](http://www.newtonsoft.com/json)

นี่คือวิธีที่คุณได้รับชุดข้อมูล

## <a name="get-a-power-bi-dataset"></a>รับชุดข้อมูล Power BI

> **หมายเหตุ**: ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่า คุณดำเนินตามขั้นตอนก่อนหน้านี้ในการฝึกปฏิบัติ[พุชข้อมูลลงในชุดข้อมูล](walkthrough-push-data.md)แล้ว

1. ในแอปพลิเคชันคอนโซลคุณสร้างในขั้นตอนที่ 2: คำแนะนำการส่งข้อมูล[รับโทเค็นการเข้าถึงการรับรองความถูกต้อง](walkthrough-push-data-get-token.md)ติดตั้งแพคเกจ Newtonsoft.Json NuGet นี่คือวิธีการติดตั้งแพคเกจ:

     ก. ใน Studio Visual 2015 เลือก**เครื่องมือ** > **ตัวจัดการแพคเกจ NuGet** > **คอนโซลตัวจัดการแพคเกจ**

     ข. ใน**คอนโซล Manager แพคเกจ**ใส่ Newtonsoft.Json แพคเกจติดตั้ง
2. หลังจากติดตั้งแพคเกจแล้ว เพิ่ม**การใช้ Newtonsoft.Json;** ไปยัง Program.cs
3. ใน Program.cs เพิ่มรหัสด้านล่างเพื่อรับ**รหัสชุดข้อมูล**
4. เรียกใช้แอปคอนโซล และเข้าสู่บัญชี Power BI ของคุณ คุณจะเห็น**รหัสชุดข้อมูล:** ตามด้วยรหัสในหน้าต่างคอนโซล

**รับตัวอย่างเป็นชุดข้อมูล**

เพิ่มรหัสนี้ลงใน Program.cs

* ค่าคงที่เพื่อยกเลิก Main(string[] args):
  
  ```csharp
  static void Main(string[] args)
  {
  
    //Get an authentication access token
    token = GetToken();
  
    //Create a dataset in Power BI
    CreateDataset();
  
    //Get a dataset to add rows into a Power BI table
    string datasetId = GetDataset();
  }
  ```
* เพิ่มวิธีการ GetDatset():
  
  ```csharp
    #region Get a dataset to add rows into a Power BI table
    private static string GetDataset()
    {
        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "GET";
        request.ContentLength = 0;
        request.ContentType = "application/json";
  
        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));
  
        string datasetId = string.Empty;
        //Get HttpWebResponse from GET request
        using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
        {
            //Get StreamReader that holds the response stream
            using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
            {
                string responseContent = reader.ReadToEnd();
  
                //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                //and add using Newtonsoft.Json
                var results = JsonConvert.DeserializeObject<dynamic>(responseContent);
  
                //Get the first id
                datasetId = results["value"][0]["id"];
  
                Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                Console.ReadLine();
  
                return datasetId;
            }
        }
    }
    #endregion
  ```

ขั้นตอนถัดไปจะแสดงวิธีการ[เพิ่มแถวลงในตาราง Power BI](walkthrough-push-data-add-rows.md)

ด้านล่างนี้คือ[รายการรหัสที่เสร็จสมบูรณ์](#code)

<a name="code"/>

## <a name="complete-code-listing"></a>รายการรหัสเสร็จสมบูรณ์

```csharp
using System;
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using System.Net;
using System.IO;
using Newtonsoft.Json;

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

            //Get a dataset to add rows into a Power BI table
            string datasetId = GetDataset();

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

        #region Get a dataset to add rows into a Power BI table
        private static string GetDataset()
        {
            string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
            //POST web request to create a dataset.
            //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
            HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
            request.KeepAlive = true;
            request.Method = "GET";
            request.ContentLength = 0;
            request.ContentType = "application/json";

            //Add token to the request header
            request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

            string datasetId = string.Empty;
            //Get HttpWebResponse from GET request
            using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
            {
                //Get StreamReader that holds the response stream
                using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
                {
                    string responseContent = reader.ReadToEnd();

                    //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                    //and add using Newtonsoft.Json
                    var results = JsonConvert.DeserializeObject<dynamic>(responseContent);

                    //Get the first id
                    datasetId = results["value"][0]["id"];

                    Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                    Console.ReadLine();

                    return datasetId;
                }
            }
        }
        #endregion
    }
}
```

[ขั้นตอนถัดไป >](walkthrough-push-data-add-rows.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป

[เพิ่มแถวลงในตาราง Power BI](walkthrough-push-data-add-rows.md)  
[Newtonsoft.Json](http://www.newtonsoft.com/json)  
[รับชุดข้อมูล](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets)  
[ส่งข้อมูลไปยัง Power BI](walkthrough-push-data.md)  
[ภาพรวมของ Power BI REST API](overview-of-power-bi-rest-api.md)  
[การอ้างอิง Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/)  

คุณมีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)
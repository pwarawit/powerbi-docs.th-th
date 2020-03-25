---
title: กำหนดค่าข้อมูลประจำตัวทางโปรแกรมสำหรับ Power BI
description: วิธีการกำหนดค่าข้อมูลประจำตัวทางโปรแกรมเมื่อดำเนินการ Power BI แบบอัตโนมัติ
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/23/2020
ms.openlocfilehash: bd7758be32d18fd3be06a7847edc7795c2b5f9e1
ms.sourcegitcommit: 2c798b97fdb02b4bf4e74cf05442a4b01dc5cbab
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/21/2020
ms.locfileid: "80114784"
---
# <a name="configure-credentials-programmatically-for-power-bi"></a>กำหนดค่าข้อมูลประจำตัวทางโปรแกรมสำหรับ Power BI

ทำตามขั้นตอนเหล่านี้เพื่อกำหนดค่าข้อมูลประจำตัวทางโปรแกรมสำหรับ Power BI

## <a name="update-credentials-flow-for-data-sources"></a>อัปเดตโฟลว์ข้อมูลประจำตัวสำหรับแหล่งข้อมูล

1. เรียกใช้ฟังก์ชัน[รับแหล่งข้อมูล](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasourcesingroup)เพื่อค้นหาแหล่งข้อมูลของชุดข้อมูล ในเนื้อหาคำตอบสำหรับแต่ละแหล่งข้อมูล มีชนิด รายละเอียดการเชื่อมต่อ เกตเวย์ และรหัสแหล่งข้อมูล

    ```csharp
    // Select a datasource
    var datasources = pbiClient.Datasets.GetDatasources(datasetId).Value;
    var datasource = datasources.First();
    ```

2. สร้างข้อมูลประจำตัวของสตริงตาม[ตัวอย่างของแหล่งข้อมูลอัปเด](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource)ทั้งนี้ขึ้นอยู่กับชนิดข้อมูลประจำตัว

    # <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

    ```csharp
    var credentials =  new BasicCredentials(username: "username", password :"*****");
    ```

    # <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

     ```csharp
    var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
    ```

    ---

2. เรียกใช้ฟังก์ชัน [รับเกตเวย์](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways)เพื่อเรียกใช้คีย์สาธารณะของเกตเวย์

    ```csharp
    var gateway = pbiClient.Gateways.GetGatewayById(datasource.GatewayId);
    ```

3. เข้ารหัสข้อมูลประจำตัว

    # <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

    ```csharp
    var credentialsEncryptor = new AsymmetricKeyEncryptor(gateway.publicKey);
    ```

    # <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

    เข้ารหัสสตริงข้อมูลประจำตัวกับคีย์สาธารณะของเกตเวย์จากขั้นตอนที่ 2 เกตเวย์เวอร์ชันที่แตกต่างกันอาจมีขนาดคีย์สาธารณะที่แตกต่างกัน อ้างอิงตัวอย่างต่อไปนี้ในรหัส SDK พร้อมใช้งานจาก[ที่เก็บ PowerBI-CSharp GitHub](https://github.com/microsoft/PowerBI-CSharp/tree/master/sdk/PowerBI.Api/Extensions):
    * [AsymmetricKeyEncryptor.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/AsymmetricKeyEncryptor.cs)
    * [Asymmetric1024KeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/Asymmetric1024KeyEncryptionHelper.cs)
    * [AsymmetricHigherKeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/AsymmetricHigherKeyEncryptionHelper.cs)
    * [AuthenticatedEncryption.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/AuthenticatedEncryption.cs) 

    ---  

4. สร้างรายละเอียดข้อมูลประจำตัวด้วยข้อมูลประจำตัวที่เข้ารหัสลับไว้

    # <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

    ใช้คลาส AssymetricKeyEncriptor ด้วยคีย์สาธารณะที่กู้คืนมาใน**ขั้นตอนที่ 3**

    ```csharp
    var credentialDetails = new CredentialDetails(
            credentials,
            PrivacyLevel.Private,
            EncryptedConnection.Encrypted,
            credentialsEncryptor);
    ```


    # <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

    ```csharp
    var credentialDetails = new CredentialDetails(
            credentials,
            CredentialTypeEnum.Basic,
            EncryptedConnectionEnum.Encrypted,
            EncryptionAlgorithmEnum.None,
            PrivacyLevelEnum.Private);
    ```

    ---

5. เรียกใช้ฟังก์ชัน[แหล่งข้อมูลอัปเดต](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource)เพื่อตั้งค่าข้อมูลประจำตัว

    ```csharp
    pbiClient.Gateways.UpdateDatasource(gatewayId, datasourceId, credentialDetails);
    ```

## <a name="configure-a-new-data-source-for-a-data-gateway"></a>กำหนดค่าแหล่งข้อมูลใหม่สำหรับเกตเวย์ข้อมูล

1. ติดตั้ง[เกตเวย์ข้อมูลภายในองค์กร](https://powerbi.microsoft.com/gateway/)บนเครื่องของคุณ

2. เรียกใช้ฟังก์ชัน [รับเกตเวย์](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways)เพื่อเรียกใช้คีย์สาธารณะและ ID ของเกตเวย์

    ```csharp
    // Select a gateway
    var gateways = pbiClient.Gateways.GetGateways().Value;
    var gateway = gateways.First();
    ```

3. สร้างรายละเอียดข้อมูลประจำตัวด้วยวิธีเดียวกับที่อธิบายไว้ใน[ อัปเดตโฟลว์ข้อมูลประจำตัวสำหรับแหล่งข้อมูล](#update-credentials-flow-for-data-sources) โดยใช้เกตเวย์คีย์สาธารณะที่กู้คืนมาใน**ขั้นตอนที่ 2**

4. สร้างเนื้อความคำขอ

    ```csharp
    var request = new PublishDatasourceToGatewayRequest(
            dataSourceType: "SQL",
            connectionDetails: "{\"server\":\"myServer\",\"database\":\"myDatabase\"}",
            credentialDetails: credentialDetails,
            dataSourceName: "my sql datasource");
    ```

5. เรียกใช้ฟังก์ชัน[สร้างแหล่งข้อมูล](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource)API

    ```csharp
    pbiClient.Gateways.CreateDatasource(gateway.Id, request);
    ```

## <a name="credential-types"></a>ชนิดข้อมูลประจำตัว

เมื่อคุณเรียกใช้งาน[สร้างแหล่งข้อมูล](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource) หรือ [อัปเดตแหล่งข้อมูล](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource)ภายใต้**เกตเวย์ภายในองค์กร**โดยใช้[Power BI Rest API](https://docs.microsoft.com/rest/api/power-bi/) ค่าข้อมูลประจำตัวที่จำเป็นต้องเข้ารหัสลับโดยใช้คีย์สาธารณะของเกตเวย์

>[!NOTE]
>.NET SDK v3 ยังสามารถเรียกใช้ตัวอย่าง .NET SDK v2 ที่แสดงด้านล่างได้

### <a name="windows-and-basic-credentials"></a>Windows และข้อมูลประจำตัวพื้นฐาน

# <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

```csharp
// Windows credentials
var credentials = new WindowsCredentials(username: "john", password: "*****");

// Or

// Basic credentials
var credentials = new BasicCredentials(username: "john", password: "*****");

var credentialsEncryptor = new AsymmetricKeyEncryptor(publicKey);
var credentialDetails = new CredentialDetails(credentials, PrivacyLevel.Private, EncryptedConnection.Encrypted, credentialsEncryptor);
```

# <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
```

---

### <a name="key-credentials"></a>ข้อมูลประจำตัวหลัก

# <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

```csharp
var credentials = new KeyCredentials("TestKey");
var credentialsEncryptor = new AsymmetricKeyEncryptor(publicKey);
var credentialDetails = new CredentialDetails(credentials, PrivacyLevel.Private, EncryptedConnection.Encrypted, credentialsEncryptor);
```

# <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"key\", \"value\":\"ec....LA=\"}]}";
```

---

**ข้อมูลประจำตัว OAuth2**

# <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

```csharp
var credentials = new OAuth2Credentials("TestToken");
var credentialsEncryptor = new AsymmetricKeyEncryptor(publicKey);
var credentialDetails = new CredentialDetails(credentials, PrivacyLevel.Private, EncryptedConnection.Encrypted, credentialsEncryptor);
```

# <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"accessToken\", \"value\":\"eyJ0....fwtQ\"}]}";
```

---

**ข้อมูลประจำตัวแบบไม่ระบุชื่อ**

# <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

```csharp
var credentials = new AnonymousCredentials();
var credentialDetails = new CredentialDetails(credentials, PrivacyLevel.Private, EncryptedConnection.NotEncrypted);
```

# <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

```csharp
var credentials = "{\"credentialData\":\"\"}";
```

---

## <a name="troubleshooting"></a>การแก้ไขปัญหา

### <a name="no-gateway-and-data-source-id-found-when-calling-get-data-sources"></a>ไม่มีเกตเวย์และข้อมูล ID ที่พบเมื่อเรียกใช้ฟังก์ชันรับแหล่งข้อมูล

ปัญหานี้หมายความว่าชุดข้อมูลไม่ได้ผูกกับเกตเวย์ เมื่อสร้างชุดข้อมูลใหม่ สำหรับการเชื่อมต่อระบบคลาวด์แต่ละระบบ แหล่งข้อมูลที่ไม่มีข้อมูลประจำตัวจะถูกสร้างขึ้นโดยอัตโนมัติบนเกตเวย์ระบบคลาวด์ของผู้ใช้ เกตเวย์นี้ถูกใช้เพื่อจัดเก็บข้อมูลประจำตัวสำหรับการเชื่อมต่อระบบคลาวด์

หลังจากที่คุณสร้างชุดข้อมูล การผูกอัตโนมัติจะดำเนินการแล้วเสร็จระหว่างชุดข้อมูลและเกตเวย์ที่เหมาะสม ซึ่งประกอบด้วยแหล่งข้อมูลที่ตรงกันสำหรับการเชื่อมต่อทั้งหมด ถ้าไม่มีเกตเวย์ดังกล่าวหรือเกตเวย์ที่เหมาะสมหลายรายการ การผูกอัตโนมัติจะล้มเหลว

หากคุณกำลังใช้ชุดข้อมูลภายในองค์กร ให้สร้างแหล่งข้อมูลในองค์กรขาดหายไปและผูกชุดข้อมูลไปยังเกตเวย์ด้วยตนเองโดยใช้ตัวเลือก[ผูกกับเกตเวย์](https://docs.microsoft.com/rest/api/power-bi/datasets/bindtogateway)

หากต้องการค้นหาเกตเวย์ที่สามารถผูกได้ โปรดใช้ฟังก์ชัน[ค้นหาเกตเวย์](https://docs.microsoft.com/rest/api/power-bi/datasets/discovergateways)
---
title: กำหนดค่าข้อมูลประจำตัวทางโปรแกรมสำหรับ Power BI
description: วิธีการกำหนดค่าข้อมูลประจำตัวทางโปรแกรมสำหรับ Power BI สำหรับระบบอัตโนมัติ
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 01/08/2020
ms.openlocfilehash: 222edd901409fa71d98308f27407838d54564834
ms.sourcegitcommit: 4b926ab5f09592680627dca1f0ba016b07a86ec0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/10/2020
ms.locfileid: "75836592"
---
# <a name="configure-credentials-programmatically-for-power-bi"></a>กำหนดค่าข้อมูลประจำตัวทางโปรแกรมสำหรับ Power BI

ทำตามขั้นตอนเหล่านี้เพื่อกำหนดค่าข้อมูลประจำตัวทางโปรแกรมสำหรับ Power BI

## <a name="configure-a-credential-flow-for-data-sources"></a>กำหนดค่าโฟลว์ข้อมูลประจำตัวสำหรับแหล่งข้อมูล

1. เรียกใช้ฟังก์ชัน[รับแหล่งข้อมูล](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasourcesingroup)เพื่อค้นหาแหล่งข้อมูลของชุดข้อมูล ในเนื้อหาคำตอบสำหรับแต่ละแหล่งข้อมูล มีชนิด รายละเอียดการเชื่อมต่อ เกตเวย์ และรหัสแหล่งข้อมูล

    ```csharp
    var datasources = pbiClient.Datasets.GetDatasources(datasetId).Value;
    var datasource = datasources.First(); // select a datasource
    ```

2. สร้างข้อมูลประจำตัวของสตริงตาม[ตัวอย่างของแหล่งข้อมูลอัปเด](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource)ทั้งนี้ขึ้นอยู่กับชนิดข้อมูลประจำตัว

    ```csharp
    var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
    ```

3. สร้างรายละเอียดข้อมูลประจำตัว

    ```csharp
    var credentialDetails = new CredentialDetails(
                    credentials,
                    CredentialTypeEnum.Basic,
                    EncryptedConnectionEnum.Encrypted,
                    EncryptionAlgorithmEnum.None,
                    PrivacyLevelEnum.Private);
    ```

4. เรียกใช้ฟังก์ชัน[แหล่งข้อมูลอัปเดต](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource)เพื่อตั้งค่าข้อมูลประจำตัวโดยใช้ ID แหล่งข้อมูลและเกตเวย์จากขั้นตอนที่ 1 และโดยใช้รายละเอียดข้อมูลประจำตัวจากขั้นตอนที่ 4

    ```csharp
    pbiClient.Gateways.UpdateDatasource(gatewayId, datasourceId, credentialDetails);
    ```

### <a name="expired-on-premises-data-source-credentials-flow"></a>โฟลว์ข้อมูลประจำตัวของแหล่งข้อมูลภายในองค์กรหมดอายุแล้ว

1. [ทำตามขั้นตอนที่ 1 และ 2 จากสถานการณ์สมมติก่อนหน้า](#configure-a-credential-flow-for-data-sources)

2. เรียกใช้ฟังก์ชัน [รับเกตเวย์](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways)เพื่อเรียกใช้คีย์สาธารณะของเกตเวย์

    ```csharp
    var gateway = pbiClient.Gateways.GetGatewayById(datasource.GatewayId);
    ```

3. เข้ารหัสสตริงข้อมูลประจำตัวกับคีย์สาธารณะของเกตเวย์ เกตเวย์เวอร์ชันที่แตกต่างกันอาจมีขนาดคีย์สาธารณะที่แตกต่างกัน
    
    โปรดดูตัวอย่างในรหัส SDK ที่มีอยู่ในที่เก็บข้อมูล PowerBI-CSharp GitHub [PowerBI-CSharp/sdk/PowerBI.Api/Extensions/V2/](https://github.com/microsoft/PowerBI-CSharp/tree/master/sdk/PowerBI.Api/Extensions/V2)
    * [AsymmetricKeyEncryptor.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricKeyEncryptor.cs)
    * [Asymmetric1024KeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/Asymmetric1024KeyEncryptionHelper.cs)
    * [AsymmetricHigherKeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricHigherKeyEncryptionHelper.cs)
    * [AuthenticatedEncryption.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AuthenticatedEncryption.cs)

4. สร้างรายละเอียดข้อมูลประจำตัวด้วยข้อมูลประจำตัวที่เข้ารหัสลับไว้

    ```csharp
    var credentialDetails = new CredentialDetails(
                    encryptedCredentials,
                    CredentialTypeEnum.Basic,
                    EncryptedConnectionEnum.Encrypted,
                    EncryptionAlgorithmEnum.RSA-OAEP,
                    PrivacyLevelEnum.Private);
    ```

5. เรียกใช้ฟังก์ชัน[แหล่งข้อมูลอัปเดต](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource)เพื่อตั้งค่าข้อมูลประจำตัว

    ```csharp
    pbiClient.Gateways.UpdateDatasource(gatewayId, datasourceId, credentialDetails);
    ```

## <a name="configure-a-new-data-source-for-a-data-gateway"></a>กำหนดค่าแหล่งข้อมูลใหม่สำหรับเกตเวย์ข้อมูล

1. ติดตั้ง[เกตเวย์ข้อมูลภายในองค์กร](https://powerbi.microsoft.com/gateway/)บนเครื่องของคุณ

2. เรียกใช้ฟังก์ชัน [รับเกตเวย์](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways)เพื่อเรียกใช้คีย์สาธารณะและ ID ของเกตเวย์

    ```csharp
    var gateways = pbiClient.Gateways.GetGateways().Value;
    var gateway = gateways.First(); // select a gateway
    ```

3. สร้างรายละเอียดข้อมูลประจำตัวเช่นในสถานการณ์สมมติก่อนหน้า โดยใช้คีย์สาธารณะของเกตเวย์ที่เรียกใช้ในขั้นตอน[โฟลว์ข้อมูลประจำตัวของแหล่งข้อมูลภายในองค์กรหมดอายุแล้ว](#expired-on-premises-data source-credentials-flow-on-premises-data-gateway)

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

## <a name="troubleshooting"></a>การแก้ไขปัญหา

### <a name="no-gateway-and-data-source-id-found-when-calling-get-data-sources"></a>ไม่มีเกตเวย์และข้อมูล ID ที่พบเมื่อเรียกใช้ฟังก์ชันรับแหล่งข้อมูล

ปัญหานี้หมายความว่าชุดข้อมูลไม่ได้ผูกกับเกตเวย์ เมื่อสร้างชุดข้อมูลใหม่ สำหรับการเชื่อมต่อระบบคลาวด์แต่ละระบบ แหล่งข้อมูลที่ไม่มีข้อมูลประจำตัวจะถูกสร้างขึ้นโดยอัตโนมัติบนเกตเวย์ระบบคลาวด์ของผู้ใช้ เกตเวย์นี้ถูกใช้เพื่อจัดเก็บข้อมูลประจำตัวสำหรับการเชื่อมต่อระบบคลาวด์

หลังจากที่คุณสร้างชุดข้อมูล การผูกอัตโนมัติจะดำเนินการแล้วเสร็จระหว่างชุดข้อมูลและเกตเวย์ที่เหมาะสม ซึ่งประกอบด้วยแหล่งข้อมูลที่ตรงกันสำหรับการเชื่อมต่อทั้งหมด ถ้าไม่มีเกตเวย์ดังกล่าวหรือเกตเวย์ที่เหมาะสมหลายรายการ การผูกอัตโนมัติจะล้มเหลว

สร้างแหล่งข้อมูลภายในองค์กรที่ขาดหายไปถ้ามี และผูกชุดข้อมูลกับเกตเวย์ด้วยตนเอง โดยการใช้[ผูกเกตเวย์](https://docs.microsoft.com/rest/api/power-bi/datasets/bindtogateway)

หากต้องการค้นหาเกตเวย์ที่สามารถผูกได้ ใช้ฟังก์ชัน[ค้นหาเกตเวย์](https://docs.microsoft.com/rest/api/power-bi/datasets/discovergateways)
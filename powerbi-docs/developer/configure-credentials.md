---
title: กำหนดค่าข้อมูลประจำตัวทางโปรแกรมสำหรับ Power BI
description: วิธีการกำหนดค่าข้อมูลประจำตัวทางโปรแกรมสำหรับ Power BI สำหรับระบบอัตโนมัติ
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/25/2019
ms.openlocfilehash: f93119a621330d673fd2cf6035e0416646bd5e6a
ms.sourcegitcommit: 244d110b28d4978f360cbece3a7c896e1a645258
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/23/2019
ms.locfileid: "61380199"
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

3. เข้ารหัสสตริงข้อมูลประจำตัวกับคีย์สาธารณะของเกตเวย์ โดยใช้อัลกอริทึมการเข้ารหัสลับ RSA

    ใช้คลาสตัวช่วยต่อไปนี้สำหรับการเข้ารหัสลับ:

    ```csharp
        public static class AsymmetricKeyEncryptionHelper
        {
            private const int SegmentLength = 85;
            private const int EncryptedLength = 128;

            /// <summary>

            /// Encrypts credentials using the RSA algorithm

            /// </summary>

            public static string EncodeCredentials(string credentialData, string publicKeyExponent, string publicKeyModulus)
            {
                using (RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(EncryptedLength * 8))
                {
                    var parameters = rsa.ExportParameters(false);

                    parameters.Exponent = Convert.FromBase64String(publicKeyExponent);

                    parameters.Modulus = Convert.FromBase64String(publicKeyModulus);

                    rsa.ImportParameters(parameters);

                    return Encrypt(credentialData, rsa);
                }
            }

             private static string Encrypt(string plainText, RSACryptoServiceProvider rsa)
            {

                byte[] plainTextArray = Encoding.UTF8.GetBytes(plainText);

                // Split the message into different segments, each segment's length is 85. So, the result may be 85,85,85,20. 

                bool hasIncompleteSegment = plainTextArray.Length % SegmentLength != 0; 

                int segmentNumber = (!hasIncompleteSegment) ? (plainTextArray.Length / SegmentLength) : ((plainTextArray.Length SegmentLength) + 1);

                byte[] encryptedData = new byte[segmentNumber * EncryptedLength];

                int encryptedDataPosition = 0;

                for (var i = 0; i < segmentNumber; i++)
                {
                    int lengthToCopy;

                    if (i == segmentNumber - 1 && hasIncompleteSegment)

                        lengthToCopy = plainTextArray.Length % SegmentLength;

                    else

                        lengthToCopy = SegmentLength;

                    var segment = new byte[lengthToCopy];

                    Array.Copy(plainTextArray, i * SegmentLength, segment, 0, lengthToCopy);

                    var segmentEncryptedResult = rsa.Encrypt(segment, true);

                    Array.Copy(segmentEncryptedResult, 0, encryptedData, encryptedDataPosition, segmentEncryptedResult.Length);

                    encryptedDataPosition += segmentEncryptedResult.Length;

                }

                return Convert.ToBase64String(encryptedData);

            }

        }

        var encryptedCredentials = AsymmetricKeyEncryptionHelper.EncodeCredentials(credentials);
    ```

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

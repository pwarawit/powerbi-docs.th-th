---
title: เข้ารหัสข้อมูลประจำตัว
description: คำแนะนำ - เข้ารหัสลับข้อมูลประจำตัวสำหรับแหล่งข้อมูลเกตเวย์ภายในองค์กร
author: mahirdiab
manager: eligr
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 04/02/2019
ms.author: mahirdiab
ms.openlocfilehash: 79ab3731abfdf972de1ee9d40456ebb0c5ebfa62
ms.sourcegitcommit: 80961ace38ff9dac6699f81fcee0f7d88a51edf4
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/13/2019
ms.locfileid: "56223524"
---
# <a name="encrypt-credentials"></a>เข้ารหัสข้อมูลประจำตัว
เมื่อคุณเรียกใช้งาน[สร้างแหล่งข้อมูล](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource) หรือ [อัปเดตแหล่งข้อมูล](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource)ภายใต้**เกตเวย์ภายในองค์กร**โดยใช้[Power BI Rest API](https://docs.microsoft.com/rest/api/power-bi/) ค่าข้อมูลประจำตัวที่จำเป็นต้องเข้ารหัสลับโดยใช้คีย์สาธารณะของเกตเวย์

ดูตัวอย่างรหัสด้านล่างวิธีการเข้ารหัสลับข้อมูลประจำตัวใน.NET

ข้อมูลประจำตัวที่ระบุในเมธอด EncodeCredentials ด้านล่าง ควรอยู่ในรูปแบบต่อไปนี้ ทั้งนี้ขึ้นอยู่กับชนิดข้อมูลประจำตัว:

**พื้นฐาน / ข้อมูลประจำตัวของ Windows**
```csharp
var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
```

**ข้อมูลประจำตัวหลัก**
```csharp
var credentials = "{\"credentialData\":[{\"name\":\"key\", \"value\":\"ec....LA=\"}]}";
```

**ข้อมูลประจำตัว OAuth2**
```csharp
var credentials = "{\"credentialData\":[{\"name\":\"accessToken\", \"value\":\"eyJ0....fwtQ\"}]}";
```


**ข้อมูลประจำตัวแบบไม่ระบุชื่อ**
```csharp
var credentials = "{\"credentialData\":\"\"}";
```

**เข้ารหัสลับข้อมูลประจำตัว**
```csharp
public static class AsymmetricKeyEncryptionHelper
{

    private const int SegmentLength = 85;
    private const int EncryptedLength = 128;

    public static string EncodeCredentials(string credentials, string publicKeyExponent, string publicKeyModulus)
    {
        using (RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(EncryptedLength * 8))
        {
            var parameters = rsa.ExportParameters(false);
            parameters.Exponent = Convert.FromBase64String(publicKeyExponent);
            parameters.Modulus = Convert.FromBase64String(publicKeyModulus);
            rsa.ImportParameters(parameters);
            return Encrypt(credentials, rsa);
        }
    }

    private static string Encrypt(string plainText, RSACryptoServiceProvider rsa)
    {
        byte[] plainTextArray = Encoding.UTF8.GetBytes(plainText);

        // Split the message into different segments, each segment's length is 85. So the result may be 85,85,85,20.
        bool hasIncompleteSegment = plainTextArray.Length % SegmentLength != 0;

        int segmentNumber = (!hasIncompleteSegment) ? (plainTextArray.Length / SegmentLength) : ((plainTextArray.Length / SegmentLength) + 1);

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
```
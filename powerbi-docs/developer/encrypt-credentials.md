---
title: เข้ารหัสข้อมูลประจำตัว
description: คำแนะนำ - เข้ารหัสลับข้อมูลประจำตัวสำหรับแหล่งข้อมูลเกตเวย์ภายในองค์กร
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 01/08/2020
ms.openlocfilehash: b1fc4a505aa993c606743eefb6e8fb8c0379317d
ms.sourcegitcommit: 4b926ab5f09592680627dca1f0ba016b07a86ec0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/10/2020
ms.locfileid: "75836621"
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

เข้ารหัสค่าข้อมูลประจำตัวโดยใช้คีย์สาธารณะของเกตเวย์ เกตเวย์เวอร์ชันที่แตกต่างกันอาจมีขนาดคีย์สาธารณะที่แตกต่างกัน

โปรดดูตัวอย่างในรหัส SDK ที่มีอยู่ในที่เก็บข้อมูล PowerBI-CSharp GitHub [PowerBI-CSharp/sdk/PowerBI.Api/Extensions/V2/](https://github.com/microsoft/PowerBI-CSharp/tree/master/sdk/PowerBI.Api/Extensions/V2)

- [AsymmetricKeyEncryptor.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricKeyEncryptor.cs)
- [Asymmetric1024KeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/Asymmetric1024KeyEncryptionHelper.cs)
- [AsymmetricHigherKeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricHigherKeyEncryptionHelper.cs)
- [AuthenticatedEncryption.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AuthenticatedEncryption.cs)
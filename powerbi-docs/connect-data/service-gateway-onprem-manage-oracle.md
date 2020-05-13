---
title: จัดการแหล่งข้อมูลของคุณ - Oracle
description: วิธีการจัดการเกตเวย์ข้อมูลภายในองค์กร และข้อมูลแหล่งข้อมูลที่เป็นของเกตเวย์นั้น ๆ
author: arthiriyer
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
ms.author: arthii
LocalizationGroup: Gateways
ms.openlocfilehash: 8bc5ec7338d8513e12fdd5de10250f5b228dad76
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83284071"
---
# <a name="manage-your-data-source---oracle"></a>จัดการแหล่งข้อมูลของคุณ - Oracle

[!INCLUDE [gateway-rewrite](../includes/gateway-rewrite.md)]

หลังจากคุณ[ติดตั้งเกตเวย์ข้อมูลภายในองค์กรแล้ว](/data-integration/gateway/service-gateway-install) คุณจำเป็นต้อง[เพิ่มแหล่งข้อมูล](service-gateway-data-sources.md#add-a-data-source)ที่สามารถใช้ได้กับเกตเวย์ดังกล่าว บทความนี้จะดูวิธีการทำงานกับเกตเวย์และแหล่งข้อมูล Oracle สำหรับการรีเฟรชตามกำหนดการหรือสำหรับ DirectQuery

## <a name="install-the-oracle-client"></a>ติดตั้ง Oracle client

หากคุณต้องการเชื่อมต่อเกตเวย์กับ Oracle server ของคุณ คุณจำเป็นต้องติดตั้งและกำหนดค่าตัวให้บริการข้อมูล Oracle สำหรับ .NET (ODP.NET) ODP.NET คือส่วนหนึ่งขององค์ประกอบการเข้าถึงข้อมูล Oracle (Oracle Data Access Components: ODAC)

สำหรับ Power BI Desktop เวอร์ชัน 32 บิต ใช้ลิงก์ต่อไปนี้เพื่อดาวน์โหลดและติดตั้ง Oracle Client เวอร์ชัน 32 บิต:

* [32-bit Oracle Data Access Components (ODAC) พร้อมเครื่องมือผู้พัฒนา Oracle สำหรับ Visual Studio (12.1.0.2.4)](https://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

สำหรับ Power BI Desktop เวอร์ชัน 64 บิต หรือสำหรับเกตเวย์ข้อมูลภายในองค์กร ใช้ลิงก์ต่อไปนี้เพื่อดาวน์โหลดและติดตั้ง Oracle Client เวอร์ชัน 64 บิต:

* [64-bit ODAC 12.2c Release 1 (12.2.0.1.0) สำหรับ Windows x64](https://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

หลังจากติดตั้งไคลเอนต์แล้ว ให้กำหนดค่าไฟล์ tnsnames.ora ของคุณด้วยข้อมูลที่เหมาะสมสำหรับฐานข้อมูลของคุณ Power BI Desktop และเกตเวย์หายไปจาก net_service_name ที่กำหนดไว้ในไฟล์ tnsnames.ora หากไม่ได้กำหนดค่า net_service_name คุณจะไม่สามารถเชื่อมต่อได้ เส้นทางตามค่าเริ่มต้นสำหรับ tnsnames.ora มีดังนี้: `[Oracle Home Directory]\Network\Admin\tnsnames.ora` สำหรับข้อมูลเพิ่มเติมเกี่ยวกับวิธีการกำหนดค่าไฟล์ tnsnames.ora ให้ดูที่[Oracle: พารามิเตอร์การตั้งชื่อภายในเครื่อง (tnsnames.ora)](https://docs.oracle.com/cd/B28359_01/network.111/b28317/tnsnames.htm)

### <a name="example-tnsnamesora-file-entry"></a>ตัวอย่างการใส่ข้อมูลไฟล์ tnsnames.ora

รูปแบบพื้นฐานของรายการข้อมูลใน tnsname.ora มีดังนี้:

```
net_service_name=
 (DESCRIPTION=
   (ADDRESS=(protocol_address_information))
   (CONNECT_DATA=
     (SERVICE_NAME=service_name)))
```

ตัวอย่างของเซิร์ฟเวอร์และข้อมูลพอร์ตที่กรอกแล้วเป็นดังนี้:

```
CONTOSO =
  (DESCRIPTION =
    (ADDRESS = (PROTOCOL = TCP)(HOST = oracleserver.contoso.com)(PORT = 1521))
    (CONNECT_DATA =
      (SERVER = DEDICATED)
      (SERVICE_NAME = CONTOSO)
    )
  )
```

## <a name="add-a-data-source"></a>เพิ่มแหล่งข้อมูล

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับวิธีการเพิ่มแหล่งข้อมูล ให้ดู[เพิ่มแหล่งข้อมูล](service-gateway-data-sources.md#add-a-data-source) ภายใต้ **ชนิดแหล่งข้อมูล** ให้เลือก **Oracle**

![เพิ่มแหล่งข้อมูล Oracle](media/service-gateway-onprem-manage-oracle/data-source-oracle.png)

หลังจากที่คุณเลือกชนิดแหล่งข้อมูล Oracle แล้ว ให้กรอกข้อมูลสำหรับแหล่งข้อมูลซึ่งรวมถึง **เซิร์ฟเวอร์** และ **ฐานข้อมูล** 

ภายใต้ **วิธีการรับรองความถูกต้อง** คุณสามารถเลือก **Windows** หรือ **พื้นฐาน** ได้ เลือก **พื้นฐาน** ถ้าคุณวางแผนเพื่อใช้บัญชีที่สร้างขึ้นภายใน Oracle แทนการรับรองความถูกต้องของ Windows จากนั้นป้อนข้อมูลประจำตัวที่จะใช้สำหรับแหล่งข้อมูลนี้

> [!NOTE]
> แบบสอบถามทั้งหมดที่ไปยังแหล่งข้อมูลจะทำงานโดยใช้ข้อมูลประจำตัวเหล่านี้ หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับวิธีการจัดเก็บข้อมูลประจำตัว ให้ดู [จัดเก็บข้อมูลประจำตัวที่เข้ารหัสไว้ในระบบคลาวด์](service-gateway-data-sources.md#store-encrypted-credentials-in-the-cloud)

![การกรอกข้อมูลในการตั้งค่าแหล่งข้อมูล](media/service-gateway-onprem-manage-oracle/data-source-oracle2.png)

หลังจากที่คุณกรอกข้อมูลทุกอย่างแล้ว ให้เลือก**เพิ่ม** คุณสามารถใช้แหล่งข้อมูลนี้สำหรับการรีเฟรชตามกำหนดการหรือ DirectQuery เทียบกับ Oracle server ที่อยู่ภายในองค์กรได้ คุณจะเห็น*การเชื่อมต่อสำเร็จ* หากการดำเนินการเสร็จสมบูรณ์แล้ว

![การแสดงสถานะการเชื่อมต่อ](media/service-gateway-onprem-manage-oracle/datasourcesettings4.png)

### <a name="advanced-settings"></a>การตั้งค่าขั้นสูง

อีกทางหนึ่งคือคุณสามารถกำหนดค่าระดับความเป็นส่วนตัวให้กับแหล่งข้อมูลของคุณ การตั้งค่านี้จะช่วยควบคุมวิธีการรวมข้อมูลได้ ซึ่งใช้ได้เฉพาะกับการรีเฟรชตามกำหนดการเท่านั้น การตั้งค่าระดับความเป็นส่วนตัวจะไม่นำไปใช้กับ DirectQuery หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับระดับความเป็นส่วนตัวสำหรับแหล่งข้อมูลของคุณ ให้ดู [ระดับความเป็นส่วนตัว (Power Query)](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)

![การตั้งค่าระดับความเป็นส่วนตัว](media/service-gateway-onprem-manage-oracle/datasourcesettings9.png)

## <a name="use-the-data-source"></a>ใช้แหล่งข้อมูล

หลังจากที่คุณสร้างแหล่งข้อมูล รายการนี้จะพร้อมใช้งานเมื่อต้องใช้ทั้งกับการเชื่อมต่อ DirectQuery หรือการเชื่อมต่อสดผ่านการรีเฟรชตามกำหนดการ

> [!WARNING]
> ชื่อเซิร์ฟเวอร์และชื่อฐานข้อมูลจะต้องตรงกับ Power BI Desktop และแหล่งข้อมูลภายในเกตเวย์ข้อมูลภายในองค์กร

การเชื่อมโยงระหว่างชุดข้อมูลของคุณและแหล่งข้อมูลภายในเกตเวย์จะเป็นไปตามชื่อเซิร์ฟเวอร์และชื่อฐานข้อมูลของคุณ ชื่อเหล่านี้ต้องตรงกัน ตัวอย่างเช่น ถ้าคุณใส่ที่อยู่ IP สำหรับชื่อเซิร์ฟเวอร์ภายใน Power BI Desktop คุณต้องใช้ที่อยู่ IP สำหรับแหล่งข้อมูลภายในการกำหนดค่าเกตเวย์ด้วยเช่นกัน นอกจากนี้ ชื่อนี้ยังต้องตรงกับนามแฝงที่กำหนดไว้ภายในแฟ้ม tnsnames.ora ด้วย สำหรับข้อมูลเพิ่มเติมเกี่ยวกับไฟล์ tnsnames.ora โปรดดู [ติดตั้ง Oracle Client](#install-the-oracle-client)

ข้อกำหนดนี้เป็นกรณีสำหรับทั้ง DirectQuery และการรีเฟรชตามกำหนดการ

### <a name="use-the-data-source-with-directquery-connections"></a>ใช้แหล่งข้อมูลที่มีการเชื่อมต่อกับ DirectQuery

ตรวจสอบให้แน่ใจว่าชื่อเซิร์ฟเวอร์และชื่อฐานข้อมูลตรงกันระหว่าง Power BI Desktop และแหล่งข้อมูลที่กำหนดค่าไว้สำหรับเกตเวย์ คุณยังต้องตรวจสอบให้แน่ใจอีกว่า ผู้ใช้ของคุณแสดงอยู่ในแท็บ**ผู้ใช้**ของแหล่งข้อมูลเพื่อเผยแพร่ชุดข้อมูล DirectQuery ตัวเลือกสำหรับ DirectQuery จะเกิดขึ้นภายใน Power BI Desktop ตอนที่คุณนำเข้าข้อมูลครั้งแรก สำหรับข้อมูลเพิ่มเติมเกี่ยวกับวิธีการใช้งาน DirectQuery โปรดดู [ใช้ DirectQuery ใน Power BI Desktop](desktop-use-directquery.md)

หลังจากที่คุณเผยแพร่ชุดข้อมูลจาก Power BI Desktop หรือ**รับข้อมูล** รายงานของคุณควรเริ่มการทำงาน ซึ่งอาจจะใช้เวลาหลายนาทีเพื่อให้การเชื่อมต่อสามารถใช้งานได้ หลังจากคุณสร้างแหล่งข้อมูลภายในเกตเวย์

### <a name="use-the-data-source-with-scheduled-refresh"></a>ใช้แหล่งข้อมูลที่มีการรีเฟรชตามกำหนดการ

ถ้าคุณอยู่ในแท็บ **ผู้ใช้** ของแหล่งข้อมูลที่กำหนดค่าไว้ภายในเกตเวย์ และชื่อเซิร์ฟเวอร์และชื่อฐานข้อมูลตรงกัน คุณจะเห็นเกตเวย์เป็นตัวเลือกเพื่อใช้กับการรีเฟรชตามกำหนดการ

![การแสดงรายชื่อผู้ใช้](media/service-gateway-onprem-manage-oracle/powerbi-gateway-enterprise-schedule-refresh.png)

## <a name="troubleshooting"></a>การแก้ไขปัญหา

คุณอาจพบข้อผิดพลาดจำนวนมากจาก Oracle เมื่อไวยากรณ์การตั้งชื่อไม่ถูกต้อง หรือไม่ได้กำหนดค่าอย่างถูกต้อง:

* ORA-12154: TNS: ไม่สามารถแก้ไขตัวระบุการเชื่อมต่อที่ระบุได้
* ORA-12514: TNS: ในขณะนี้ ตัวรอรับการติดต่อไม่รู้จักบริการที่ร้องขอในตัวอธิบายการเชื่อมต่อ
* ORA-12541: TNS: ไม่มีตัวรอรับการติดต่อ
* ORA-12170: TNS: เกิดเหตุการณ์การเชื่อมต่อหมดเวลา
* ORA-12504: TNS: ตัวรอรับการติดต่อไม่ได้รับ SERVICE_NAME ใน CONNECT_DATA

ข้อผิดพลาดเหล่านี้อาจเกิดขึ้นหากไม่ได้ติดตั้ง Oracle client หรือกำหนดค่าไม่ถูกต้อง ถ้ามีการติดตั้งอยู่แล้ว ให้ตรวจสอบว่ามีการกำหนดค่าไฟล์ tnsnames.ora อย่างถูกต้องหรือไม่ และคุณกำลังใช้ net_service_name ที่เหมาะสมหรือไม่ นอกจากนี้ คุณจะต้องตรวจสอบให้แน่ใจว่า net_service_name สำหรับเครื่องที่ใช้ Power BI Desktop และเครื่องที่ใช้งานเกตเวย์นั้นเป็นตัวเดียวกันหรือไม่ สำหรับข้อมูลเพิ่มเติม โปรดดู [ติดตั้ง Oracle Client](#install-the-oracle-client)

> [!NOTE]
> คุณอาจประสบปัญหาความเข้ากันได้ระหว่างเวอร์ชัน Oracle server และเวอร์ชัน Oracle client โดยทั่วไปแล้ว คุณต้องการให้เวอร์ชันเหล่านี้ตรงกัน

สำหรับข้อมูลการแก้ไขปัญหาเพิ่มเติมที่เกี่ยวข้องกับเกตเวย์ โปรดดู [การแก้ไขปัญหาเกตเวย์ข้อมูลในองค์กร](/data-integration/gateway/service-gateway-tshoot)

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [แก้ไขปัญหาเกตเวย์-Power BI](service-gateway-onprem-tshoot.md)
* [Power BI Premium](../admin/service-premium-what-is.md)

มีคำถามเพิ่มเติมหรือไม่ ลองถาม[ชุมชน Power BI](https://community.powerbi.com/)

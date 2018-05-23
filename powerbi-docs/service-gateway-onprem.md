---
title: เกตเวย์ข้อมูลภายในองค์กร
description: นี่คือภาพรวมของเกตเวย์ข้อมูลในองค์กรสำหรับ Power BI คุณสามารถใช้เกตเวย์นี้เพื่อทำงานกับแหล่งข้อมูล DirectQuery คุณยังสามารถใช้เกตเวย์นี้เพื่อรีเฟรชชุดข้อมูลบนระบบคลาวด์กับข้อมูลภายในองค์กร
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 03/26/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: c6c924095e3aaf4839f1c9422e027ba5373b9ad4
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/08/2018
---
# <a name="on-premises-data-gateway"></a>เกตเวย์ข้อมูลภายในองค์กร
เกตเวย์ข้อมูลภายในองค์กรทำหน้าที่เป็นสะพาน โดยให้บริการการถ่ายโอนข้อมูลที่รวดเร็วและปลอดภัยระหว่างข้อมูลภายในองค์กร (ข้อมูลที่ไม่ได้อยู่ในระบบคลาวด์) และบริการ Power BI, Microsoft Flow, Logic Apps และ PowerApps

คุณสามารถใช้เกตเวย์เดียวกับบริการอื่น ๆ ในเวลาเดียวกัน ถ้าคุณกำลังใช้ Power BI ได้เช่นเดียวกับ PowerApps สามารถใช้เกตเวย์เดียวสำหรับทั้งสองอย่าง ซึ่งจะขึ้นอยู่กับบัญชีผู้ใช้ที่คุณลงชื่อเข้าใช้

> [!NOTE]
> เกตเวย์ข้อมูลในองค์กรประมวลผลรวมข้อมูล และการเข้ารหัส transport ในทุกโหมด
> 
> 

<!-- Shared Requirements Include -->
[!INCLUDE [gateway-onprem-requirements-include](./includes/gateway-onprem-requirements-include.md)]

### <a name="limitations-of-analysis-services-live-connections"></a>ขีดจำกัดของการเชื่อมต่อแบบสดของ Analysis Services
คุณสามารถใช้การเชื่อมต่อแบบสดกับอินสแตนซ์หลายมิติ หรือแบบตาราง

| **รุ่นของเซิร์ฟเวอร์** | **SKU ที่จำเป็นต้องมี** |
| --- | --- |
| 2012 SP1 CU4 หรือใหม่กว่า |เทคโนโลยีสำหรับการรวบรวมข้อมูล จัดเก็บ วิเคราะห์ และการเข้าถึงข้อมูล รวมถึงการดูในหลากหลายมุมมอง (BI) และ SKU องค์กร |
| 2014 |เทคโนโลยีสำหรับการรวบรวมข้อมูล จัดเก็บ วิเคราะห์ และการเข้าถึงข้อมูล รวมถึงการดูในหลากหลายมุมมอง (BI) และ SKU องค์กร |
| 2016 |SKU มาตรฐาน หรือสูงกว่า |

* การจัดรูปแบบระดับเซลล์ และคุณลักษณะการแปลไม่ได้รับการสนับสนุน
* การดำเนินการและ Named Sets จะไม่แสดงใน Power BI แต่คุณยังสามารถเชื่อมต่อกับคิวบ์หลายมิติที่ยังประกอบด้วยการดำเนินการ หรือ Named Sets พร้อมสร้างภาพและรายงานได้

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-datasources-include](./includes/gateway-onprem-datasources-include.md)]

## <a name="download-and-install-the-on-premises-data-gateway"></a>ดาวน์โหลด และติดตั้งเกตเวย์ข้อมูลในองค์กร
ในการดาวน์โหลดเกตเวย์ ให้เลือก**เกตเวย์ข้อมูล**ภายใต้เมนูดาวน์โหลด ดาวน์โหลด[เกตเวย์ข้อมูลภายในองค์กร](http://go.microsoft.com/fwlink/?LinkID=820925)

![](media/service-gateway-onprem/powerbi-download-data-gateway.png)

<!-- Shared Install steps Include -->
[!INCLUDE [gateway-onprem-install-include](./includes/gateway-onprem-install-include.md)]

## <a name="install-the-gateway-in-personal-mode"></a>ติดตั้งเกตเวย์ในโหมดส่วนตัว
> [!NOTE]
> ส่วนบุคคลจะทำงานกับ Power BI เท่านั้น
> 
> 

หลังจากที่มีการติดตั้งเกตเวย์ส่วนบุคคล คุณจะต้องเปิดใช้การ**Power BI Gateway-Personal ตัวช่วยสร้างการกำหนดค่า**

![](media/service-gateway-onprem/personal-gateway-launch-configuration.png)

จากนั้นคุณจะจำเป็นต้องลงชื่อเข้า Power BI ใช้เพื่อลงทะเบียนเกตเวย์กับบริการระบบคลาวด์

![](media/service-gateway-onprem/personal-gateway-signin.png)

นอกจากนี้คุณจะจำเป็นต้องใส่ชื่อผู้ใช้ windows และรหัสผ่านที่บริการ windows จะเรียกใช้ในฐานะ คุณสามารถระบุบัญชีผู้ใช้ Windows อื่นที่แตกต่างจากของคุณ บริการเกตเวย์จะทำงานโดยใช้บัญชีนี้

![](media/service-gateway-onprem/personal-gateway-windows-service.png)

หลังจากการติดตั้งเสร็จสมบูรณ์ คุณจะต้องไปที่ชุดข้อมูลของคุณภายใน Power BI และตรวจสอบให้แน่ใจว่า มีป้อนข้อมูลประจำตัวสำหรับแหล่งข้อมูลภายในองค์กรของคุณ

<a name="credentials"></a>

## <a name="storing-encrypted-credentials-in-the-cloud"></a>จัดเก็บข้อมูลประจำตัวเข้ารหัสลับในระบบคลาวด์
เมื่อคุณเพิ่มแหล่งข้อมูลกับเกตเวย์ คุณจำเป็นต้องใส่ข้อมูลประจำตัวสำหรับแหล่งข้อมูลนั้น คิวรีทั้งหมดไปยังแหล่งข้อมูลจะทำงานโดยใช้ข้อมูลประจำตัวเหล่านี้ ข้อมูลประจำตัวถูกเข้ารหัสลับได้อย่างปลอดภัย โดยใช้การเข้ารหัสลับสมมาตรเพื่อให้พวกเขาไม่สามารถถอดรหัสในระบบคลาวด์ ก่อนที่พวกเขาจะถูกจัดเก็บในระบบคลาวด์ ข้อมูลประจำตัวถูกส่งไปยังเครื่อง เรียกใช้เกตเวย์ ภายในองค์กรที่พวกเขาจะถอดรหัสลับเมื่อมีการเข้าถึงแหล่งข้อมูล

<!-- Account and Port information -->
[!INCLUDE [gateway-onprem-accounts-ports-more](./includes/gateway-onprem-accounts-ports-more.md)]

<!-- How the gateway works -->
[!INCLUDE [gateway-onprem-how-it-works-include](./includes/gateway-onprem-how-it-works-include.md)]

## <a name="limitations-and-considerations"></a>ข้อจำกัดและข้อควรพิจารณา
* [Azure Information Protection](https://docs.microsoft.com/en-us/microsoft-365/enterprise/protect-files-with-aip
)ยังไม่ได้รับการสนับสนุนในขณะนี้
* [เข้าถึงแบบออนไลน์](https://products.office.com/en-us/access)จะไม่ได้รับการสนับสนุน

## <a name="troubleshooting"></a>การแก้ไขปัญหา
ถ้าคุณพบปัญหาเมื่อติดตั้ง และกำหนดค่าเกตเวย์ อย่าลืมดู[เกตเวย์ข้อมูลในองค์กรในการแก้ไขปัญหา](service-gateway-onprem-tshoot.md) ถ้าคุณคิดว่า คุณกำลังมีปัญหากับไฟร์วอลล์ของคุณ ดู[ไฟร์วอลล์หรือพร็อกซี](service-gateway-onprem-tshoot.md#firewall-or-proxy)ส่วนในบทความแก้ไขปัญหา

ถ้าคุณคิดว่า คุณกำลังประสบปัญหาพร็อกซี กับเกตเวย์ ดู[กำหนดค่าพร็อกซีสำหรับเกตเวย์ Power BI](service-gateway-proxy.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[จัดการแหล่งข้อมูลของคุณ - Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[จัดการแหล่งข้อมูลของคุณ - SAP HANA](service-gateway-enterprise-manage-sap.md)  
[จัดการแหล่งข้อมูลของคุณ - SQL Server](service-gateway-enterprise-manage-sql.md)  
[จัดการแหล่งข้อมูลของคุณ - Oracle](service-gateway-onprem-manage-oracle.md)  
[จัดการแหล่งข้อมูลของคุณ - นำเข้า/รีเฟรชตามตารางเวลา](service-gateway-enterprise-manage-scheduled-refresh.md)  
[เกตเวย์ข้อมูลในองค์กร เชิงลึก](service-gateway-onprem-indepth.md)  
[เกตเวย์ข้อมูลภายในองค์กร (โหมดส่วนบุคคล) - เวอร์ชันใหม่ของเกตเวย์ส่วนบุคคล](service-gateway-personal-mode.md)
[กำหนดค่าพร็อกซีสำหรับ Power BI Gateways](service-gateway-proxy.md)  
คำถามเพิ่มเติมหรือไม่ [ลองชุมชน Power BI](http://community.powerbi.com/)


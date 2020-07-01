---
title: เกตเวย์ข้อมูลในองค์กรในเชิงลึก
description: บทความนี้จะดูที่เกตเวย์ภายในองค์กรแบบเชิงลึก ซึ่งจะดูวิธีการทำงานของบริการกับ Azure Active Directory และ Active Directory ภายในเครื่องของคุณเมื่อทำงานกับ Analysis Services
author: arthiriyer
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: how-to
ms.date: 07/15/2019
ms.author: arthii
LocalizationGroup: Gateways
ms.openlocfilehash: 34cf796db212112baa8083f5b4cbf1796b465cba
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85237570"
---
# <a name="on-premises-data-gateway-in-depth"></a>เกตเวย์ข้อมูลในองค์กรในเชิงลึก

[!INCLUDE [gateway-rewrite](../includes/gateway-rewrite.md)]

เราได้ย้ายข้อมูลจากบทความนี้ไปยังหลายบทความผ่าน Power BI และเอกสารทั่วไป ทำตามลิงก์ภายใต้หัวเรื่องแต่ละรายการเพื่อค้นหาเนื้อหาที่เกี่ยวข้อง

## <a name="how-the-gateway-works"></a>เกตเวย์ทำงานอย่างไร

ดูที่[สถาปัตยกรรมเกตเวย์ข้อมูลภายในองค์กร](/data-integration/gateway/service-gateway-onprem-indepth)

## <a name="list-of-available-data-source-types"></a>รายการของชนิดแหล่งข้อมูลที่พร้อมใช้งาน

ดูที่ [จัดการแหล่งข้อมูล](service-gateway-data-sources.md)

## <a name="authentication-to-on-premises-data-sources"></a>รับรองความถูกต้องไปยังแหล่งข้อมูลภายในองค์กร

ดูที่ [การรับรองความถูกต้องไปยังแหล่งข้อมูลภายในองค์กร](/data-integration/gateway/service-gateway-onprem-indepth#authentication-to-on-premises-data-sources)

## <a name="authentication-to-a-live-analysis-services-data-source"></a>รับรองความถูกต้องไปยังแหล่งข้อมูล Analysis Services แบบออนไลน์

ดูที่ [รับรองความถูกต้องไปยังแหล่งข้อมูล Analysis Services แบบออนไลน์](service-gateway-enterprise-manage-ssas.md#authentication-to-a-live-analysis-services-data-source)

## <a name="role-based-security"></a>รักษาความปลอดภัยตามบทบาท

ดูที่ [การรักษาความปลอดภัยตามบทบาท](service-gateway-enterprise-manage-ssas.md#role-based-security)

## <a name="row-level-security"></a>รักษาความปลอดภัยระดับแถว

ดูที่ [การรักษาความปลอดภัยระดับแถว](service-gateway-enterprise-manage-ssas.md#row-level-security)

## <a name="what-about-azure-active-directory"></a>แล้ว Azure Active Directory ล่ะ?

ดูที่ [Azure Active Directory](/data-integration/gateway/service-gateway-onprem-indepth#azure-active-directory)

## <a name="how-do-i-tell-what-my-upn-is"></a>ฉันจะทราบได้อย่างไรว่า UPN ของฉันเป็นอะไร

ดูที่ [ฉันจะทราบได้อย่างไรว่า UPN ของฉันเป็นอะไร](/data-integration/gateway/service-gateway-onprem-indepth#how-do-i-tell-what-my-upn-is)

## <a name="map-user-names-for-analysis-services-data-sources"></a>แมปชื่อผู้ใช้สำหรับแหล่งข้อมูล Analysis Services

ดูที่ [แมปชื่อผู้ใช้สำหรับแหล่งข้อมูล Analysis Services](service-gateway-enterprise-manage-ssas.md#map-user-names-for-analysis-services-data-sources)

## <a name="synchronize-an-on-premises-active-directory-with-azure-active-directory"></a>รวม Active Directory ภายในองค์กรเข้ากับ Azure Active Directory

ดูที่ [รวม Active Directory ภายในองค์กรเข้ากับ Azure Active Directory](/data-integration/gateway/service-gateway-onprem-indepth#synchronize-an-on-premises-active-directory-with-azure-active-directory)

## <a name="what-to-do-next"></a>สิ่งที่ต้องทำต่อไปคืออะไร?

ดูบทความในแหล่งข้อมูล:

[จัดการแหล่งข้อมูล](service-gateway-data-sources.md)
[จัดการแหล่งข้อมูลของคุณ - Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[จัดการแหล่งข้อมูลของคุณ - SAP HANA](service-gateway-enterprise-manage-sap.md)  
[จัดการแหล่งข้อมูลของคุณ - SQL Server](service-gateway-enterprise-manage-sql.md)  
[จัดการแหล่งข้อมูลของคุณ - Oracle](service-gateway-onprem-manage-oracle.md)  
[จัดการแหล่งข้อมูลของคุณ - นำเข้า/รีเฟรชตามตารางเวลา](service-gateway-enterprise-manage-scheduled-refresh.md)  

## <a name="where-things-can-go-wrong"></a>นี่คือจุดที่สามารถเกิดข้อผิดพลาดได้

ดูที่ [แก้ไขปัญหาเกตเวย์ข้อมูลภายในองค์กร](/data-integration/gateway/service-gateway-tshoot)และ [แก้ไขปัญหาเกตเวย์ - Power BI](service-gateway-onprem-tshoot.md)

## <a name="sign-in-account"></a>ลงชื่อเข้าใช้บัญชี

ดูที่ [ลงชื่อเข้าใช้บัญชี](/data-integration/gateway/service-gateway-onprem-indepth#sign-in-account)

## <a name="windows-service-account"></a>บัญชี Windows Service

ดูที่ [เปลี่ยนบัญชีบริการของเกตเวย์ข้อมูลภายในองค์กร](/data-integration/gateway/service-gateway-service-account)

## <a name="ports"></a>พอร์ต

ดูที่ [พอร์ต](/data-integration/gateway/service-gateway-communication#ports)

## <a name="forcing-https-communication-with-azure-service-bus"></a>บังคับให้ HTTPS สื่อสารกับ Azure Service Bus

ดูที่ [บังคับใช้การสื่อสาร HTTPS กับ Azure Service Bus](/data-integration/gateway/service-gateway-communication#force-https-communication-with-azure-service-bus)

## <a name="support-for-tls-12"></a>สนับสนุน TLS 1.1/1.2

ดูที่ [TLS 1.2 สำหรับการรับส่งข้อมูลเกตเวย์](/data-integration/gateway/service-gateway-communication#tls-12-for-gateway-traffic)

## <a name="how-to-restart-the-gateway"></a>วิธีการรีสตาร์ทเกตเวย์

ดูที่ [รีสตาร์ทเกตเวย์](/data-integration/gateway/service-gateway-restart)

## <a name="next-steps"></a>ขั้นตอนถัดไป

[เกตเวย์ข้อมูลภายในองค์กรคืออะไร](service-gateway-onprem.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)
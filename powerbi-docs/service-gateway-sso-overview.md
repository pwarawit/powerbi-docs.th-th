---
title: ใช้การลงชื่อเข้าใช้ครั้งเดียว (SSO) กับแหล่งข้อมูลภายในองค์กร
description: กำหนดค่าเกตเวย์ของคุณเมื่อต้องการเปิดใช้งานการลงชื่อเข้าใช้ครั้งเดียว (SSO) จาก Power BI ไปยังแหล่งข้อมูลในองค์กร
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 10/15/2018
LocalizationGroup: Gateways
ms.openlocfilehash: bfd40c991f461e57f2f1d2de8a46b3627aa7fbc1
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54274225"
---
# <a name="overview-of-single-sign-on-sso-for-gateways-in-power-bi"></a>ภาพรวมของการลงชื่อเข้าใช้ครั้งเดียว (SSO) สำหรับเกตเวย์ใน Power BI

คุณจะได้รับการเชื่อมต่อการลงชื่อเข้าใช้ครั้งเดียวแบบไร้ร้อยต่อซึ่งทำให้รายงาน Power BI และแดชบอร์ดสามารถอัปเดตจากข้อมูลในองค์กรได้โดยการกำหนดเกตเวย์ข้อมูลในองค์กรของคุณด้วยการมอบหมายที่มีข้อจำกัดของ Kerberos หรือ Security Assertion Markup Language (SAML) เกตเวย์ข้อมูลในองค์กร จะช่วยอำนวยความสะดวกในการ SSO โดยใช้ DirectQuery เพื่อเชื่อมต่อกับแหล่งข้อมูลในองค์กร

ขณะนี้เราสนับสนุนแหล่งข้อมูลต่อไปนี้:

* SQL Server ([Kerberos](service-gateway-sso-kerberos.md))
* SAP HANA ([Kerberos](service-gateway-sso-kerberos.md) และ [SAML](service-gateway-sso-saml.md)
* SAP BW ([Kerberos](service-gateway-sso-kerberos.md))
* Teradata ([Kerberos](service-gateway-sso-kerberos.md))
* Spark ([Kerberos](service-gateway-sso-kerberos.md))
* Impala ([Kerberos](service-gateway-sso-kerberos.md))

เมื่อผู้ใช้โต้ตอบกับ รายงาน DirectQuery ในบริการของ Power BI การดำเนินงานเกี่ยวกับ ตัวกรองข้าม ชิ้น การเรียงลำดับ และการแก้ไขรายงาน อาจดำเนินการด้วยคิวรีสด กับแหล่งข้อมูลพื้นฐานภายในองค์กร  เมื่อแหล่งข้อมูลมีการกำหนดค่า SSO คิวรีจะถูกดำเนินการด้วย ข้อมูลประจำตัวของผู้ใช้ที่โต้ตอบกับ Power BI (นั่นคือ เมื่อทำผ่านเว็บ หรือแอป Power BI บนมือถือ) ดังนั้น ผู้ใช้แต่ละรายมองเห็นได้เพียงข้อมูลที่พวกเขามีสิทธิ์ในแหล่งข้อมูลพื้นฐาน – เมื่อมีการกำหนดค่า SSO จะไม่มีการแชร์แคชข้อมูลระหว่างผู้ใช้

## <a name="query-steps-when-running-sso"></a>ขั้นตอนการคิวรีเมื่อเรียกใช้ SSO

คิวรีที่ทำงานโดยใช้ SSO ประกอบด้วยสามขั้นตอน ดังที่แสดงในไดอะแกรมต่อไปนี้

![ขั้นตอนการคิวรีของ SSO](media/service-gateway-sso-overview/sso-query-steps.png)

> [!NOTE]
> SSO สำหรับ Oracle ยังไม่เปิดให้ใช้งาน ยังอยู่ระหว่างการพัฒนาและจะมาเร็ว ๆ นี้

นี่เป็นรายละเอียดเพิ่มเติมเกี่ยวกับขั้นตอนดังกล่าว:

1. สำหรับแต่ละคิวรี **บริการของ Power BI**จะบรรจุ*ชื่อหลักผู้ใช้* (UPN) เมื่อคุณส่งการร้องขอคิวรีไปยังเกตเวย์ที่กำหนดไว้

2. เกตเวย์ต้องแมปค่า UPN ของ Azure Active Directory ไปยัง ข้อมูลประจำตัวใน Active Directory ในเครื่อง

   a.  ถ้า Azure AD DirSync (หรือที่เรียกว่า*Azure AD Connect*) มีการกำหนดค่าแล้ว การแมปจะทำงานโดยอัตโนมัติในเกตเวย์

   b.  มิฉะนั้น เกตเวย์สามารถค้นหา และแมป Azure AD UPN ไปยังผู้ใช้ภายในเครื่อง โดยการค้นหากับโดเมน Active Directory ในเครื่อง

3. บริการของเกตเวย์ ปลอมตัวเป็นผู้ใช้ภายในเครื่องที่ถูกแมป เปิดการเชื่อมต่อกับฐานข้อมูลพื้นฐาน และส่งคิวรี เกตเวย์ไม่จำเป็นต้องติดตั้งบนคอมพิวเตอร์เครื่องเดียวกับฐานข้อมูล

## <a name="next-steps"></a>ขั้นตอนถัดไป

ตอนนี้คุณเข้าใจพื้นฐานของ SSO แล้ว โปรดอ่านข้อมูลโดยละเอียดเกี่ยวกับ Kerberos และ SAML:

* [การลงชื่อเข้าใช้ครั้งเดียว (SSO) - Kerberos](service-gateway-sso-kerberos.md)
* [การลงชื่อเข้าใช้ครั้งเดียว (SSO) - SAML](service-gateway-sso-saml.md)

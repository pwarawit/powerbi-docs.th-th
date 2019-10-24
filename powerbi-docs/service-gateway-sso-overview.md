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
ms.date: 07/15/2019
LocalizationGroup: Gateways
ms.openlocfilehash: b1379bb783b090362215eaf7c317bbea435d1eec
ms.sourcegitcommit: e533c65607bbba0f620fddabd6b107e5933772c1
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/11/2019
ms.locfileid: "72259930"
---
# <a name="overview-of-single-sign-on-sso-for-gateways-in-power-bi"></a>ภาพรวมของการลงชื่อเข้าใช้ครั้งเดียว (SSO) สำหรับเกตเวย์ใน Power BI

คุณจะได้รับการเชื่อมต่อการลงชื่อเข้าใช้ครั้งเดียวแบบไร้ร้อยต่อซึ่งทำให้รายงาน Power BI และแดชบอร์ดสามารถอัปเดตตามเวลาจริงจากข้อมูลในองค์กรได้โดยการกำหนดเกตเวย์ข้อมูลภายในองค์กรของคุณด้วยการมอบสิทธิ์ที่มีข้อจำกัดของ Kerberos หรือ Security Assertion Markup Language (SAML) เกตเวย์ข้อมูลภายในองค์กรจะรองรับการใช้ในการ SSO โดยใช้ DirectQuery เพื่อเชื่อมต่อกับแหล่งข้อมูลในองค์กร

ขณะนี้เราสนับสนุนแหล่งข้อมูลต่อไปนี้:

* SQL Server ([Kerberos](service-gateway-sso-kerberos.md))
* SAP HANA ([Kerberos](service-gateway-sso-kerberos.md) และ [SAML](service-gateway-sso-saml.md))
* เซิร์ฟเวอร์แอปพลิเคชัน SAP BW([Kerberos ](service-gateway-sso-kerberos.md))
* เซิร์ฟเวอร์ข้อความของ SAP BW ([Kerberos ](service-gateway-sso-kerberos.md))-การแสดงตัวอย่างสาธารณะ
* Oracle ([Kerberos ](service-gateway-sso-kerberos.md))-การแสดงตัวอย่างสาธารณะ
* Teradata ([Kerberos](service-gateway-sso-kerberos.md))
* Spark ([Kerberos](service-gateway-sso-kerberos.md))
* Impala ([Kerberos](service-gateway-sso-kerberos.md))

ขณะนี้เราไม่สนับสนุน SSO สำหรับ[นามสกุลไฟล์ M](https://github.com/microsoft/DataConnectors/blob/master/docs/m-extensions.md)

เมื่อผู้ใช้โต้ตอบกับ รายงาน DirectQuery ในบริการของ Power BI การดำเนินงานเกี่ยวกับ ตัวกรองข้าม ชิ้น การเรียงลำดับ และการแก้ไขรายงาน อาจดำเนินการด้วยคิวรีสด กับแหล่งข้อมูลพื้นฐานภายในองค์กร เมื่อแหล่งข้อมูลมีการกำหนดค่า SSO คิวรีจะถูกดำเนินการด้วย ข้อมูลประจำตัวของผู้ใช้ที่โต้ตอบกับ Power BI (นั่นคือ เมื่อทำผ่านเว็บ หรือแอป Power BI บนมือถือ) ดังนั้น ผู้ใช้แต่ละรายมองเห็นได้เพียงข้อมูลที่พวกเขามีสิทธิ์ในแหล่งข้อมูลพื้นฐาน – เมื่อมีการกำหนดค่า SSO จะไม่มีการแชร์แคชข้อมูลระหว่างผู้ใช้

## <a name="query-steps-when-running-sso"></a>ขั้นตอนการคิวรีเมื่อเรียกใช้ SSO

คิวรีที่ทำงานโดยใช้ SSO ประกอบด้วยสามขั้นตอน ดังที่แสดงในไดอะแกรมต่อไปนี้

![ขั้นตอนการคิวรีของ SSO](media/service-gateway-sso-overview/sso-query-steps.png)

นี่เป็นรายละเอียดเพิ่มเติมเกี่ยวกับขั้นตอนดังกล่าว:

1. สำหรับการสอบถามแต่ละครั้ง **บริการของ Power BI** จะรวม*ชื่อผู้ใช้หลัก* (UPN คือชื่อผู้ใช้แบบเต็มของผู้ใช้ที่เข้าสู่ระบบบริการของ Power BI ในปัจจุบัน) เมื่อส่งการร้องขอการสอบถามไปยังเกตเวย์ที่กำหนดค่าไว้

2. เกตเวย์ต้องแมปค่า UPN ของ Azure Active Directory ไปยัง ข้อมูลประจำตัวใน Active Directory ในเครื่อง

   a.  ถ้า Azure AD DirSync (หรือที่เรียกว่า*Azure AD Connect*) มีการกำหนดค่าแล้ว การแมปจะทำงานโดยอัตโนมัติในเกตเวย์

   b.  มิฉะนั้น เกตเวย์สามารถค้นหาและแมป Azure AD UPN ไปยังผู้ใช้ AD ภายในเครื่อง โดยการค้นหากับโดเมน Active Directory ในเครื่อง

3. บริการของเกตเวย์จะเลียนแบบเป็นผู้ใช้ภายในเครื่องที่ถูกแมป เปิดการเชื่อมต่อกับฐานข้อมูลเบื้องต้น และส่งคิวรี เกตเวย์ไม่จำเป็นต้องติดตั้งบนคอมพิวเตอร์เครื่องเดียวกับฐานข้อมูล

## <a name="next-steps"></a>ขั้นตอนถัดไป

ตอนนี้คุณเข้าใจพื้นฐานของ SSO ผ่านเกตเวย์แล้ว โปรดอ่านข้อมูลโดยละเอียดเกี่ยวกับ Kerberos และ SAML:

* [การลงชื่อเข้าใช้ครั้งเดียว (SSO) - Kerberos](service-gateway-sso-kerberos.md)
* [การลงชื่อเข้าใช้ครั้งเดียว (SSO) - SAML](service-gateway-sso-saml.md)

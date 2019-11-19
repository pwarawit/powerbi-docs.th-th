---
title: ภาพรวมของการลงชื่อเข้าใช้ครั้งเดียว (SSO) สำหรับเกตเวย์ใน Power BI
description: กำหนดค่าเกตเวย์ของคุณเมื่อต้องการเปิดใช้งานการลงชื่อเข้าใช้ครั้งเดียว (SSO) จาก Power BI ไปยังแหล่งข้อมูลในองค์กร
author: mgblythe
ms.author: mblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 43394e8f09327ebcb858ff5644b30daee1793444
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/09/2019
ms.locfileid: "73872377"
---
# <a name="overview-of-single-sign-on-sso-for-gateways-in-power-bi"></a>ภาพรวมของการลงชื่อเข้าใช้ครั้งเดียว (SSO) สำหรับเกตเวย์ใน Power BI

คุณสามารถเชื่อมต่อด้วยการลงชื่อเข้าใช้ครั้งเดียว ซึ่งเปิดใช้งานรายงานและแดชบอร์ดของ Power BI เพื่อปรับปรุงจากข้อมูลในองค์กรแบบเรียลไทม์ โดยการกำหนดค่าในเกตเวย์ข้อมูลในองค์กรของคุณ คุณมีตัวเลือกในการกำหนดค่าเกตเวย์ของคุณด้วยการมอบสิทธิ์แบบจำกัดของ [Kerberos](service-gateway-sso-kerberos.md) หรือ Security Assertion Markup Language ([SAML](service-gateway-sso-saml.md)) เกตเวย์ข้อมูลภายในองค์กรสนับสนุน SSO โดยใช้ [DirectQuery](desktop-directquery-about.md) ซึ่งเชื่อมต่อกับแหล่งข้อมูลในองค์กร

Power BI รองรับแหล่งข้อมูลต่อไปนี้:

* SQL Server (Kerberos)
* SAP HANA (Kerberos และ SAML)
* SAP BW Application Server (Kerberos)
* SAP BW Message Server (Kerberos) - การแสดงตัวอย่างสาธารณะ
* Oracle (Kerberos) - การแสดงตัวอย่างสาธารณะ
* Teradata (Kerberos)
* Spark (Kerberos)
* Impala (Kerberos)

ขณะนี้เราไม่สนับสนุน SSO สำหรับ[ไฟล์นามสกุล M](https://github.com/microsoft/DataConnectors/blob/master/docs/m-extensions.md)

เมื่อผู้ใช้โต้ตอบกับรายงาน DirectQuery ในบริการของ Power BI การดำเนินการแก้ไขตัวกรองข้าม แบ่งส่วน เรียงลำดับ และรายงานแต่ละครั้งอาจส่งผลต่อคิวรีต่าง ๆ ที่ดำเนินการสดกับแหล่งข้อมูลพื้นฐานภายในองค์กร เมื่อคุณกำหนดค่า SSO สำหรับแหล่งข้อมูล คิวรีจะดำเนินการภายใต้ ข้อมูลประจำตัวของผู้ใช้ที่โต้ตอบกับ Power BI (นั่นคือเมื่อทำผ่านเว็บหรือแอปสำหรับอุปกรณ์เคลื่อนที่ของ Power BI) ดังนั้น ผู้ใช้แต่ละคนจะเห็นข้อมูลที่พวกเขามีสิทธิ์ในแหล่งข้อมูลพื้นฐานอย่างแม่นยำ ด้วยการกำหนดค่าการลงชื่อเข้าใช้ครั้งเดียว จะไม่มีการแคชข้อมูลที่ใช้ร่วมกันสำหรับผู้ใช้ที่ต่างกัน

## <a name="query-steps-when-running-sso"></a>ขั้นตอนการคิวรีเมื่อเรียกใช้ SSO

คิวรีที่ทำงานโดยใช้ SSO ประกอบด้วยสามขั้นตอน ดังที่แสดงในไดอะแกรมต่อไปนี้

![ขั้นตอนการคิวรีของ SSO](media/service-gateway-sso-overview/sso-query-steps.png)

นี่เป็นรายละเอียดเพิ่มเติมเกี่ยวกับแต่ละขั้นตอน:

1. สำหรับการคิวรีแต่ละครั้ง บริการของ Power BI ประกอบด้วย*ชื่อผู้ใช้หลัก (UPN)* ซึ่งเป็นชื่อผู้ใช้แบบเต็มที่ผ่านการรับรองของผู้ใช้ที่ลงชื่อเข้าใช้บริการของ Power BI ในปัจจุบัน เมื่อส่งการร้องขอคิวรีไปยังเกตเวย์ที่กำหนดค่าไว้

2. เกตเวย์ต้องแมปค่า UPN ของ Azure Active Directory ไปยังข้อมูลประจำตัวของ Active Directory ในเครื่อง:

   a. ถ้า Azure AD DirSync (หรือที่เรียกว่า*Azure AD Connect*) มีการกำหนดค่าแล้ว การแมปจะทำงานโดยอัตโนมัติในเกตเวย์

   b.  มิฉะนั้น เกตเวย์สามารถค้นหาและแมป Azure AD UPN ไปยังผู้ใช้ AD ภายในเครื่อง โดยการค้นหากับโดเมน Active Directory ในเครื่อง

3. กระบวนการบริการเกตเวย์จะเลียนแบบเป็นผู้ใช้ภายในเครื่องที่ถูกแมป เปิดการเชื่อมต่อกับฐานข้อมูลเบื้องต้น แล้วส่งคิวรี คุณไม่จำเป็นต้องติดตั้งเกตเวย์บนคอมพิวเตอร์เครื่องเดียวกับฐานข้อมูล

## <a name="next-steps"></a>ขั้นตอนถัดไป

ตอนนี้คุณเข้าใจพื้นฐานของการเปิดใช้งาน SSO ผ่านเกตเวย์แล้ว โปรดอ่านข้อมูลโดยละเอียดเกี่ยวกับ Kerberos และ SAML:

* [การลงชื่อเข้าใช้ครั้งเดียว (SSO) - Kerberos](service-gateway-sso-kerberos.md)
* [การลงชื่อเข้าใช้ครั้งเดียว (SSO) - SAML](service-gateway-sso-saml.md)

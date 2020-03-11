---
title: ภาพรวมของการลงชื่อเข้าใช้ครั้งเดียว (SSO) สำหรับเกตเวย์ใน Power BI
description: กำหนดค่าเกตเวย์ของคุณเมื่อต้องการเปิดใช้งานการลงชื่อเข้าใช้ครั้งเดียว (SSO) จาก Power BI ไปยังแหล่งข้อมูลในองค์กร
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 5eab21418eb1028d94ba2e50ffd6e736e6226018
ms.sourcegitcommit: d65da4738f011beec8f4423085cbd483511cdfb0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/03/2020
ms.locfileid: "78237925"
---
# <a name="overview-of-single-sign-on-sso-for-gateways-in-power-bi"></a>ภาพรวมของการลงชื่อเข้าใช้ครั้งเดียว (SSO) สำหรับเกตเวย์ใน Power BI

คุณสามารถเชื่อมต่อด้วยการลงชื่อเข้าใช้ครั้งเดียว ซึ่งเปิดใช้งานรายงานและแดชบอร์ดของ Power BI เพื่อปรับปรุงจากข้อมูลในองค์กรแบบเรียลไทม์ โดยการกำหนดค่าในเกตเวย์ข้อมูลในองค์กรของคุณ คุณมีตัวเลือกในการกำหนดค่าเกตเวย์ของคุณด้วยการมอบสิทธิ์แบบจำกัดของ [Kerberos](service-gateway-sso-kerberos.md) หรือ Security Assertion Markup Language ([SAML](service-gateway-sso-saml.md)) เกตเวย์ข้อมูลภายในองค์กรสนับสนุน SSO โดยใช้ [DirectQuery](desktop-directquery-about.md) หรือสำหรับการรีเฟรช ซึ่งเชื่อมต่อกับแหล่งข้อมูลในองค์กร 

Power BI รองรับแหล่งข้อมูลต่อไปนี้:

* SQL Server (Kerberos)
* SAP HANA (Kerberos และ SAML)
* SAP BW Application Server (Kerberos)
* เซิร์ฟเวอร์ข้อความของ SAP BW (Kerberos) 
* Oracle (Kerberos) 
* Teradata (Kerberos)
* Spark (Kerberos)
* Impala (Kerberos)

ขณะนี้เราไม่สนับสนุน SSO สำหรับ[ไฟล์นามสกุล M](https://github.com/microsoft/DataConnectors/blob/master/docs/m-extensions.md)

เมื่อผู้ใช้โต้ตอบกับรายงาน DirectQuery ในบริการของ Power BI การดำเนินการแก้ไขตัวกรองข้าม แบ่งส่วน เรียงลำดับ และรายงานแต่ละครั้งอาจส่งผลต่อคิวรีต่าง ๆ ที่ดำเนินการสดกับแหล่งข้อมูลพื้นฐานภายในองค์กร เมื่อคุณกำหนดค่า SSO สำหรับแหล่งข้อมูล คิวรีจะดำเนินการภายใต้ ข้อมูลประจำตัวของผู้ใช้ที่โต้ตอบกับ Power BI (นั่นคือเมื่อทำผ่านเว็บหรือแอปสำหรับอุปกรณ์เคลื่อนที่ของ Power BI) ดังนั้น ผู้ใช้แต่ละคนจะเห็นข้อมูลที่พวกเขามีสิทธิ์ในแหล่งข้อมูลพื้นฐานอย่างแม่นยำ 

คุณยังสามารถกำหนดค่ารายงานที่ตั้งค่าสำหรับการรีเฟรชในบริการ Power BI เพื่อใช้ SSO ได้ เมื่อคุณกำหนดค่า SSO สำหรับแหล่งข้อมูลนี้แล้ว คิวรีจะดำเนินการภายใต้ข้อมูลประจำตัวของเจ้าของชุดข้อมูลภายใน Power BI ดังนั้น การรีเฟรชจะเกิดขึ้นตามสิทธิ์ของเจ้าของชุดข้อมูลในแหล่งข้อมูลพื้นฐาน ในขณะนี้การรีเฟรชโดยใช้ SSO เปิดใช้งานเฉพาะสำหรับแหล่งข้อมูลที่ใช้การมอบสิทธิ์แบบจำกัดของ [Kerberos](service-gateway-sso-kerberos.md) 

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

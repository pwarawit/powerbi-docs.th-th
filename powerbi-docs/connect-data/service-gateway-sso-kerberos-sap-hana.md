---
title: ใช้ Kerberos สำหรับลงชื่อเข้าระบบครั้งเดียว (SSO) ไปยัง SAP HANA
description: กำหนดค่าเซิร์ฟเวอร์ SAP Hana ของคุณเพื่อเปิดใช้งาน SSO จากบริการของ Power BI
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: how-to
ms.date: 10/10/2019
LocalizationGroup: Gateways
ms.openlocfilehash: eb65741a0fd65ed7df73e3012d7f07fdbeb527f1
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85235764"
---
# <a name="use-kerberos-for-single-sign-on-sso-to-sap-hana"></a>ใช้ Kerberos สำหรับลงชื่อเข้าระบบครั้งเดียว (SSO) ไปยัง SAP HANA

บทความนี้อธิบายวิธีกำหนดค่าแหล่งข้อมูล SAP HANA ของคุณเพื่อเปิดใช้งาน SSO จากบริการของ Power BI

> [!NOTE]
> ก่อนที่คุณจะพยายามรีเฟรชรายงานที่ยึดกับ SAP HANA ที่ใช้ Kerberos SSO ให้ทำตามทั้งขั้นตอนในบทความนี้และขั้นตอนใน [กำหนดค่า Kerberos SSO](service-gateway-sso-kerberos.md)

## <a name="enable-sso-for-sap-hana"></a>เปิดใช้งาน SSO สำหรับ SAP HANA

เพื่อเปิดใช้งาน SSO สำหรับ SAP HANA ให้ทำตามขั้นตอนต่อไปนี้:

1. ตรวจสอบให้แน่ใจว่า เซิร์ฟเวอร์ SAP HANA ทำงานด้วยเวอร์ชันขั้นต่ำ ซึ่งขึ้นอยู่กับระดับเซิร์ฟเวอร์แพลตฟอร์ม SAP HANA ของคุณ:
   - [HANA 2 SPS 01 Rev 012.03](https://launchpad.support.sap.com/#/notes/2557386)
   - [HANA 2 SPS 02 Rev 22](https://launchpad.support.sap.com/#/notes/2547324)
   - [HANA 1 SP 12 Rev 122.13](https://launchpad.support.sap.com/#/notes/2528439)

2. บนเครื่องเกตเวย์ ติดตั้งโปรแกรมควบคุม SAP HANA ODBC ล่าสุด เวอร์ชันขั้นต่ำคือ HANA ODBC เวอร์ชัน 2.00.020.00 ที่ออกเดือน สิงหาคม 2017

3. ตรวจสอบให้แน่ใจว่าเซิร์ฟเวอร์ SAP Hana ได้รับการกำหนดค่าสำหรับ SSO ที่ใช้ Kerberos สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการตั้งค่า SSO สำหรับ SAP HANA โดยใช้ Kerberos โปรดดู [ลงชื่อเข้าระบบครั้งเดียวโดยใช้ Kerberos](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.03/1885fad82df943c2a1974f5da0eed66d.html) ในคู่มือการรักษาความปลอดภัย SAP HANA โปรดดูลิงก์จากหน้านั้น โดยเฉพาะอย่างยิ่ง SAP Note 1837331 – HOWTO HANA DBSSO Kerberos/Active Directory

เราขอแนะนำให้ทำตามขั้นตอนเพิ่มเติมต่อไปนี้ ซึ่งสามารถเพิ่มประสิทธิภาพการปรับปรุงเล็กน้อย:

1. ในไดเรกทอรีการติดตั้งเกตเวย์ ค้นหาและเปิดไฟล์ที่มีการกำหนดค่าตามนี้: Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config.

2. ค้นหาคุณสมบัติ `FullDomainResolutionEnabled` และเปลี่ยนค่าเป็น `True`

    ```xml
    <setting name=" FullDomainResolutionEnabled " serializeAs="String">
          <value>True</value>
    </setting>
    ```

ตอนนี้ให้[เปิดใช้รายงาน Power BI](service-gateway-sso-kerberos.md#run-a-power-bi-report)

## <a name="next-steps"></a>ขั้นตอนถัดไป

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับเกตเวย์ข้อมูลภายในองค์กรและ DirectQuery ให้ดูแหล่งข้อมูลต่อไปนี้:

* [เกตเวย์ข้อมูลภายในองค์กรคืออะไร](/data-integration/gateway/service-gateway-onprem)
* [DirectQuery ใน Power BI](desktop-directquery-about.md)
* [แหล่งข้อมูลที่สนับสนุนโดย DirectQuery](power-bi-data-sources.md)
* [DirectQuery และ SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery และ SAP HANA](desktop-directquery-sap-hana.md)

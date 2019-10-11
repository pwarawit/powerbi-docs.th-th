---
title: ใช้ Kerberos สำหรับลงชื่อเข้าระบบครั้งเดียว (SSO) ไปยัง SAP HANA
description: กำหนดค่าเซิร์ฟเวอร์ SAP Hana ของคุณเพื่อเปิดใช้งาน SSO จากบริการของ Power BI
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 08/01/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 9e7bdb0ae2f1e512e3e431cf69395d601cbc7b3f
ms.sourcegitcommit: 9bf3cdcf5d8b8dd12aa1339b8910fcbc40f4cbe4
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/05/2019
ms.locfileid: "71968531"
---
# <a name="use-kerberos-for-single-sign-on-sso-to-sap-hana"></a>ใช้ Kerberos สำหรับลงชื่อเข้าระบบครั้งเดียว (SSO) ไปยัง SAP HANA

บทความนี้อธิบายวิธีกำหนดค่าแหล่งข้อมูล SAP HANA ของคุณเพื่อเปิดใช้งาน SSO จากบริการของ Power BI

> [!NOTE]
> ทำตามขั้นตอนในบทความนี้เพิ่มเติมจากขั้นตอนในการ[ตั้งค่าคอนฟิก Kerberos sso](service-gateway-sso-kerberos.md) ก่อนที่จะพยายามรีเฟรชรายงานที่ยึดกับ SAP HANA ที่อ้างอิงรายงานมาจากการใช้ Kerberos SSO

## <a name="enable-sso-for-sap-hana"></a>เปิดใช้งาน SSO สำหรับ SAP HANA

เพื่อเปิดใช้งาน SSO สำหรับ SAP HANA ให้ทำตามขั้นตอนต่อไปนี้:

* ตรวจสอบให้แน่ใจว่า เซิร์ฟเวอร์ SAP HANA ทำงานด้วยเวอร์ชันขั้นต่ำ ซึ่งขึ้นอยู่กับระดับเซิร์ฟเวอร์แพลตฟอร์ม SAP HANA ของคุณ:
  * [HANA 2 SPS 01 Rev 012.03](https://launchpad.support.sap.com/#/notes/2557386)
  * [HANA 2 SPS 02 Rev 22](https://launchpad.support.sap.com/#/notes/2547324)
  * [HANA 1 SP 12 Rev 122.13](https://launchpad.support.sap.com/#/notes/2528439)
* บนเครื่องเกตเวย์ ติดตั้งโปรแกรมควบคุม HANA ODBC ล่าสุดของ SAP  เวอร์ชันขั้นต่ำคือ HANA ODBC เวอร์ชัน 2.00.020.00 ที่ออกเดือน สิงหาคม 2017

ตรวจสอบให้แน่ใจว่าเซิร์ฟเวอร์ SAP Hana ได้รับการกำหนดค่าสำหรับ SSO ที่ใช้ Kerberos สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการตั้งค่า SSO สำหรับ SAP HANA โดยใช้ Kerberos โปรดดู [ลงชื่อเข้าระบบครั้งเดียวโดยใช้ Kerberos](https://help.sap.com/viewer/b3ee5778bc2e4a089d3299b82ec762a7/2.0.03/1885fad82df943c2a1974f5da0eed66d.html) ในคู่มือการรักษาความปลอดภัย SAP HANA โปรดดูลิงก์จากหน้านั้น โดยเฉพาะอย่างยิ่ง SAP Note 1837331 – HOWTO HANA DBSSO Kerberos/Active Directory

เราขอแนะนำให้ปฏิบัติตามขั้นตอนต่อไปนี้ซึ่งอาจทำให้การปรับปรุงประสิทธิภาพน้อยลง

1. ในไดเรกทอรีการติดตั้งเกตเวย์ ค้นหาและเปิดไฟล์ที่มีการกำหนดค่าตามนี้: *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config*.

2. ค้นหาคุณสมบัติ *FullDomainResolutionEnabled* และเปลี่ยนค่าเป็น *จริง*

    ```xml
    <setting name=" FullDomainResolutionEnabled " serializeAs="String">
          <value>True</value>
    </setting>
    ```

ตอนนี้ให้[เปิดใช้รายงาน Power BI](service-gateway-sso-kerberos.md#run-a-power-bi-report)

## <a name="next-steps"></a>ขั้นตอนถัดไป

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ**เกตเวย์ข้อมูลภายในองค์กร**และ **DirectQuery** ลองดูแหล่งข้อมูลต่อไปนี้:

* [เกตเวย์ข้อมูลภายในองค์กรคืออะไร](/data-integration/gateway/service-gateway-getting-started)
* [DirectQuery ใน Power BI](desktop-directquery-about.md)
* [แหล่งข้อมูลที่สนับสนุนโดย DirectQuery](desktop-directquery-data-sources.md)
* [DirectQuery และ SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery และ SAP HANA](desktop-directquery-sap-hana.md)

---
title: ใช้ SAML สำหรับการลงชื่อเข้าใช้ครั้งเดียว (SSO) กับแหล่งข้อมูลภายในองค์กร
description: กำหนดค่าเกตเวย์ของคุณด้วย Assertion Markup Language (SAML) เมื่อต้องการเปิดใช้งานการลงชื่อเข้าระบบครั้งเดียว (SSO) จาก Power BI กับแหล่งข้อมูลภายในองค์กร
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 10/10/2018
LocalizationGroup: Gateways
ms.openlocfilehash: 8762e575574b717965ac55d4cf32a5c925c298ab
ms.sourcegitcommit: a1b7ca499f4ca7e90421511e9dfa61a33333de35
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/10/2018
ms.locfileid: "51507795"
---
# <a name="use-security-assertion-markup-language-saml-for-single-sign-on-sso-from-power-bi-to-on-premises-data-sources"></a>ใช้ Assertion Markup Language (SAML) สำหรับการลงชื่อเข้าระบบครั้งเดียว (SSO) จาก Power BI กับแหล่งข้อมูลภายในองค์กร

ใช้ [Security Assertion Markup Language (SAML)](https://www.onelogin.com/pages/saml) เพื่อเปิดใช้งานการเชื่อมต่อการลงชื่อเข้าใช้ครั้งเดียวแบบไร้ร้อยต่อ เปิดใช้งาน SSO สำหรับรายงาน Power BI และแดชบอร์ดเพื่อรีเฟรชข้อมูลจากแหล่งข้อมูลภายในองค์กรอย่างง่ายดาย

## <a name="supported-data-sources"></a>แหล่งข้อมูลที่ได้รับการสนับสนุน

ขณะนี้เราสนับสนุน SAP HANA ที่มี SAML สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการตั้งค่าและกำหนดค่าการลงชื่อเข้าใช้ครั้งเดียวสำหรับ SAP HANA โดยใช้ SAML ดูหัวข้อ [SAML SSO for BI Platform to HANA](https://wiki.scn.sap.com/wiki/display/SAPHANA/SAML+SSO+for+BI+Platform+to+HANA) ในเอกสารประกอบ SAP HANA

เราสนับสนุนแหล่งข้อมูลเพิ่มเติมด้วย [Kerberos](service-gateway-sso-kerberos.md)

## <a name="configuring-the-gateway-and-data-source"></a>กำหนดค่าแหล่งข้อมูลและเกตเวย์

เมื่อต้องการใช้ SAML ขั้นแรกคุณต้องสร้างใบรับรองสำหรับตัวให้บริการข้อมูลประจำตัว SAML จากนั้นแมปผู้ใช้ Power BI ไปยังข้อมูลประจำตัว

1. สร้างใบรับรอง ตรวจสอบว่าคุณใช้ FQDN ของเซิร์ฟเวอร์ SAP HANA เมื่อกรอก *ชื่อทั่วไป* ใบรับรองจะหมดอายุใน 365 วัน

    ```
    openssl req -newkey rsa:2048 -nodes -keyout samltest.key -x509 -days 365 -out samltest.crt
    ```

1. ใน SAP HANA Studio คลิกขวาที่เซิร์ฟเวอร์ SAP HANA จากนั้นไปที่ **การรักษาความปลอดภัย** > **เปิดคอนโซลการรักษาความปลอดภัย** > **ตัวให้บริการข้อมูลประจำตัว SAML**  >  **ไลบรารีเข้ารหัสลับ OpenSSL**

1. เลือก **นำเข้า** ไปที่ samltest.crt แล้วนำเข้า

    ![ตัวให้บริการข้อมูลประจำตัว](media/service-gateway-sso-saml/identity-providers.png)

1. ใน SAP HANA Studio ให้เลือกโฟลเดอร์ **การรักษาความปลอดภัย**

    ![โฟลเดอร์การรักษาความปลอดภัย](media/service-gateway-sso-saml/security-folder.png)

1. ขยาย **ผู้ใช้** จากนั้นเลือกผู้ใช้ที่คุณต้องการแมปไปยังผู้ใช้ Power BI

1. เลือก **SAML** แล้ว **กำหนดค่า**

    ![กำหนดค่า SAML](media/service-gateway-sso-saml/configure-saml.png)

1. เลือกตัวให้บริการข้อมูลประจำตัวที่คุณสร้างในขั้นตอนที่ 2 สำหรับ **ข้อมูลประจำตัวภายนอก** ให้ป้อน UPN ของผู้ใช้ Power BI แล้วเลือก **เพิ่ม**

    ![เลือกตัวให้บริการข้อมูลประจำตัว](media/service-gateway-sso-saml/select-identity-provider.png)

ถัดไปให้ตรวจสอบการตั้งค่าด้วย *SAML assertion* โดยใช้ [เครื่องมือ xmlsec1](http://sgros.blogspot.com/2013/01/signing-xml-document-using-xmlsec1.html)

1. บันทึกการรับรองด้านล่างเป็น assertion-template.xml แทนที่ \<MyUserId\> ด้วย UPN ของผู้ใช้ Power BI ที่คุณป้อนในขั้นตอนที่ 7

    ```xml
    <?xml version="1.0" encoding="UTF-8" ?>
    <saml2:Assertion ID="Assertion12345789" IssueInstant="2015-07-16T04:47:49.858Z" Version="2.0" xmlns:saml2="urn:oasis:names:tc:SAML:2.0:assertion">
      <saml2:Issuer></saml2:Issuer> 
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">
        <SignedInfo>
          <CanonicalizationMethod Algorithm="http://www.w3.org/TR/2001/REC-xml-c14n-20010315"/>
          <SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#rsa-sha1"/>
          <Reference URI="">
            <Transforms>
              <Transform Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature"/>
              <Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>
            </Transforms>
            <DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>
            <DigestValue />
          </Reference>
        </SignedInfo>
        <SignatureValue />
        <KeyInfo>
          <X509Data />
        </KeyInfo>
      </Signature>
      <saml2:Subject>
        <saml2:NameID Format="urn:oasis:names:tc:SAML:1.1:nameid-format:unspecified"><MyUserId></saml2:NameID>
      </saml2:Subject>
      <saml2:Conditions NotBefore="2010-01-01T00:00:00Z" NotOnOrAfter="2050-01-01T00:00:00Z"/>
    </saml2:Assertion>
    ```

1. เรียกใช้คำสั่งต่อไปนี้ saltiest.key และ saml test.crt เป็นคีย์และใบรับรองที่คุณสร้างขึ้นในขั้นตอนที่ 1

    ```
    xmlsec1 --sign --privkey-pem samltest.key, samltest.crt --output signed.xml assertion-template.xml
    ```

1. ใน SAP HANA Studio เปิดหน้าต่างคอนโซล SQL และเรียกใช้คำสั่งต่อไปนี้ แทนที่ \<SAMLAssertion\> ด้วยเนื้อหาของ xml จากขั้นตอนก่อนหน้า

    ```SQL
    CONNECT WITH SAML ASSERTION '<SAMLAssertion>'
    ```

หากการคิวรี่เสร็จสมบูรณ์ หมายความว่าการตั้งค่า SAP HANA SAML SSO ประสบความสำเร็จ

เมื่อคุณมีใบรับรองและข้อมูลประจำตัวเรียบร้อยที่กำหนดค่าแล้ว คุณจะต้องแปลงใบรับรองเป็นรูปแบบ pfx และกำหนดค่าเครื่องเกตเวย์เพื่อใช้ใบรับรอง

1. แปลงใบรับรองเป็นรูปแบบ pfx โดยเรียกใช้คำสั่งต่อไปนี้

    ```
    openssl pkcs12 -inkey samltest.key -in samltest.crt -export -out samltest.pfx
    ```

1. คัดลอกไฟล์ pfx ไปยังเครื่องเกตเวย์:

    1. ดับเบิลคลิกที่ samltest.pfx จากนั้นเลือก **Local Machine** > **ถัดไป**

    1. ป้อนรหัสผ่าน จาก นั้นเลือก **ถัดไป**

    1. เลือก**วางใบรับรองทั้งหมดในที่เก็บต่อไปนี้** จากนั้น **เรียกดู** > **ส่วนบุคคล** > **OK**

    1. เลือก **ถัดไป** แล้ว **เสร็จสิ้น**

    ![นำเข้าใบรับรอง](media/service-gateway-sso-saml/import-certificate.png)

1. กำหนดสิทธิ์การเข้าถึงบัญชีบริการเกตเวย์ให้กับคีย์ส่วนตัวของใบรับรอง:

    1. ในเครื่องเกตเวย์ ให้เรียกใช้งาน Microsoft Management Console (MMC)

        ![เรียกใช้ MMC](media/service-gateway-sso-saml/run-mmc.png)

    1. ภายใต้ **ไฟล์** เลือก **เพิ่ม/ลบสแน็ปอิน**

        ![เพิ่มสแน็ปอิน](media/service-gateway-sso-saml/add-snap-in.png)

    1. เลือก **ใบรับรอง** > **เพิ่ม** แล้วเลือก **บัญชีคอมพิวเตอร์** > **ถัดไป**

    1. เลือก **คอมพิวเตอร์ภายในองค์กร** > **เสร็จสิ้น** > **ตกลง**

    1. ขยาย **ใบรับรอง** > **ส่วนบุคคล** > **ใบรับรอง** และค้นหาใบรับรอง

    1. คลิกขวาใบรับรอง และไปยัง **งานทั้งหมด** > **จัดการคีย์ส่วนตัว**

        ![จัดการคีย์ส่วนตัว](media/service-gateway-sso-saml/manage-private-keys.png)

    1. เพิ่มบัญชีบริการเกตเวย์ลงในรายการ ตามค่าเริ่มต้น บัญชีคือ **NT SERVICE\PBIEgwService.** คุณสามารถดูว่าบัญชีใดที่ใช้งานบริการเกตเวย์โดยใช้ **services.msc** และค้นหา **บริการเกตเวย์ข้อมูลภายในองค์กร**

        ![บริการเกตเวย์](media/service-gateway-sso-saml/gateway-service.png)

ขั้นสุดท้าย ให้ทำตามขั้นตอนต่อไปนี้เพื่อเพิ่มรหัสประจำตัวใบรับรองลงในการกำหนดค่าเกตเวย์

1. เรียกใช้คำสั่ง PowerShell ต่อไปนี้เพื่อแสดงรายการใบรับรองบนเครื่องของคุณ

    ```powershell
    Get-ChildItem -path cert:\LocalMachine\My
    ```
1. คัดลอกรหัสประจำตัวสำหรับใบรับรองที่คุณสร้างขึ้น

1. ไปที่ไดเรกทอรีเกตเวย์ซึ่งค่าเริ่มต้นอยู่ที่ C:\Program Files\On-premises data gateway

1. เปิด PowerBI.DataMovement.Pipeline.GatewayCore.dll.config และค้นหาส่วน \*SapHanaSAMLCertThumbprint\* วางในรหัสประจำตัวที่คุณคัดลอก

1. รีสตาร์ทบริการเกตเวย์

## <a name="running-a-power-bi-report"></a>การเรียกใช้รายงาน Power BI

ตอนนี้คุณสามารถใช้หน้า **จัดการเกตเวย์** ใน Power BI เพื่อกำหนดค่าแหล่งข้อมูลและใน **การตั้งค่าขั้นสูง** และเปิดใช้งาน SSO จากนั้นคุณสามารถเผยแพร่รายงานและชุดข้อมูลที่เชื่อมโยงกับแหล่งข้อมูลดังกล่าวได้

![การตั้งค่าขั้นสูง](media/service-gateway-sso-saml/advanced-settings.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการ**เกตเวย์ข้อมูลในองค์กร**และ **DirectQuery** ลองดูบทความต่อไปนี้:

* [เกตเวย์ข้อมูลภายในองค์กร](service-gateway-onprem.md)
* [DirectQuery ใน Power BI](desktop-directquery-about.md)
* [แหล่งข้อมูลที่สนับสนุนโดย DirectQuery](desktop-directquery-data-sources.md)
* [DirectQuery และ SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery และ SAP HANA](desktop-directquery-sap-hana.md)
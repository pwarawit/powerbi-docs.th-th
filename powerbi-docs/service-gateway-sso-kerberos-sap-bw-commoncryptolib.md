---
title: ใช้การลงชื่อเข้าระบบแบบครั้งเดียวของ Kerberos สำหรับ SSO ไปยัง SAP เท่ากับการใช้ CommonCryptoLib (sapcrypto.dll)
description: กำหนดค่าเซิร์ฟเวอร์ SAP BW ของคุณเพื่อเปิดใช้งาน SSO จากบริการของ Power BI โดยใช้ CommonCryptoLib (sapcrypto.dll)
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 08/01/2019
LocalizationGroup: Gateways
ms.openlocfilehash: 6c4f2b0d8856d5e68e02b9b33cf393ca85ecb580
ms.sourcegitcommit: 7a0ce2eec5bc7ac8ef94fa94434ee12a9a07705b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/18/2019
ms.locfileid: "71106296"
---
# <a name="use-kerberos-single-sign-on-for-sso-to-sap-bw-using-commoncryptolib-sapcryptodll"></a>ใช้การลงชื่อเข้าระบบแบบครั้งเดียวของ Kerberos สำหรับ SSO ไปยัง SAP เท่ากับการใช้ CommonCryptoLib (sapcrypto.dll)

บทความนี้อธิบายวิธีกำหนดค่าเซิร์ฟเวอร์ SAP BW ของคุณเพื่อเปิดใช้งาน SSO จากบริการของ Power BI โดยใช้ CommonCryptoLib (sapcrypto.dll)

> [!NOTE]
> ทำตามขั้นตอนในบทความนี้เพิ่มเติมจากขั้นตอนในการ[ตั้งค่าคอนฟิก Kerberos sso](service-gateway-sso-kerberos.md) ก่อนที่จะพยายามรีเฟรชรายงานที่ยึดกับ SAP BW ที่อ้างอิงรายงานมาจากการใช้ Kerberos SSO การใช้CommonCryptoLib เป็นคลัง SNC สามารถทำให้การเชื่อมต่อ SSO ไปยังเซอร์เวอร์แอปพลิเคชัน SAP BW และเซอร์เวอร์ข้อความ SAP BW ได้

## <a name="configure-sap-bw-server-to-enable-sso-using-commoncryptolib"></a>กำหนดค่าเซิฟเวอร์ SAP BWเพื่อเปิดการใช้งาน SSO โดยใช้ CommonCryptoLib

> [!NOTE]
> เกตเวย์ข้อมูลภายในองค์กรเป็นซอฟ์ทแวร์  64 บิท ดังนั้นจึงต้องการ CommonCryptoLib (sapcrypto.dll) เวอร์ชัน 64 บิท หากคุณมีแผนที่จะกำลังทดลองทำการเชื่อมต่อ SSO เข้ากับเซิฟเวอร์ SAP BW ใน SAP GUI ก่อนพยายามที่จะเชื่อมต่อ SSO ผ่านเกตเวย์ (แนะนำ) คุณจะต้องใช้ CommonCryptoLib เวอร์ชัน 32 บิทและซอฟ์ทแวร์ SAP GUI 32 บิท

1. ตรวจสอบให้แน่ใจว่าเซิร์ฟเวอร์ BW ได้รับการกำหนดค่าสำหรับ Kerberos SSO อย่างถูกต้องโดยใช้ CommonCryptoLib ถ้าเป็นเช่นนั้นคุณควรจะสามารถใช้ SSO เพื่อเข้าถึงเซิร์ฟเวอร์ของคุณได้ (โดยตรงหรือผ่านเซิร์ฟเวอร์ข้อความของ SAP BW) ด้วยเครื่องมือ SAP เช่น SAP GUI ที่ได้รับการกำหนดค่าให้ใช้ CommonCryptoLib สำหรับข้อมูลเพิ่มเติมเกี่ยวกับขั้นตอนการตั้งค่า ให้ดู[ SAP แบบลงชื่อเข้าระบบเพียงครั้งเดียว: รับรองความถูกต้องด้วย Kerberos/SPNEGO](https://blogs.sap.com/2017/07/27/sap-single-sign-on-authenticate-with-kerberosspnego/) เซิร์ฟเวอร์ BW จะต้องใช้ CommonCryptoLib เป็นไลบรารีของ SNC และมีชื่อ SNC ที่เริ่มต้นด้วย "CN =" เช่น "CN = BW1" สำหรับข้อมูลเพิ่มเติมเกี่ยวกับข้อกำหนดของชื่อ SNC ให้ดู[พารามิเตอร์ SNC สำหรับการกำหนดค่า Kerberos ](https://help.sap.com/viewer/df185fd53bb645b1bd99284ee4e4a750/3.0/en-US/360534094511490d91b9589d20abb49a.html) (โดยเฉพาะอย่างยิ่ง snc/ข้อมูลประจำตัว/เป็นพารามิเตอร์)

1. หากคุณยังไม่ได้ดำเนินการดังกล่าว ให้ติดตั้งเวอร์ชั่น x64 ของ [SAP .NET Connector](https://support.sap.com/en/product/connectors/msnet.html) บนคอมพิวเตอร์ที่มีการติดตั้งเกตเวย์ไว้แล้ว คุณสามารถตรวจสอบว่ามีการติดตั้งคอมโพเนนต์โดยพยายามเชื่อมต่อกับเซิร์ฟเวอร์ BW ใน Power BI Desktop หรือไม่ ถ้าคุณไม่สามารถเชื่อมต่อโดยใช้การดำเนินการ 2.0 คุณจะไม่สามารถติดตั้ง .NET Connector

1. ตรวจสอบให้แน่ใจว่า SAP Secure Login Client (SLC) ไม่ได้ทำงานบนคอมพิวเตอร์ที่มีการติดตั้งเกตเวย์ SLC จะแคชตั๋ว Kerberos ในลักษณะที่อาจรบกวนความสามารถของเกตเวย์เพื่อใช้ Kerberos สำหรับ SSO ถ้ามีการติดตั้ง SLC ให้ถอนการติดตั้งหรือตรวจสอบให้แน่ใจว่าคุณได้ออกจาก SAP Secure Login Client: คลิกขวาที่ไอคอนในถาดระบบและเลือกออกจากระบบและออกก่อนที่จะพยายามเชื่อมต่อ SSO โดยใช้เกตเวย์ SLC ไม่ได้รับการสนับสนุนสำหรับการใช้งานบนเครื่องเซิร์ฟเวอร์ของ Windows สำหรับข้อมูลเพิ่มเติม ให้ดู [SAP Note 2780475](https://launchpad.support.sap.com/#/notes/2780475) (ต้องมีผู้ใช้ s)

    ![SAP Secure Login Client](media/service-gateway-sso-kerberos/sap-secure-login-client.png)

    ถ้าคุณถอนการติดตั้ง SLC หรือเลือก **ออกจากระบบ** และ**ออก** ให้เปิดหน้าต่าง cmd และใส่ `klist purge` เพื่อล้างตั๋ว Kerberos ที่แคชไว้ก่อนที่จะพยายามเชื่อมต่อ SSO ผ่านเกตเวย์

1. ดาวน์โหลด CommonCryptoLib 64 บิท (sapcrypto.dll) เวอร์ชั่น **8.5.25 หรือมากกว่า**จาก SAP Launchpad และคัดลอกไปยังโฟลเดอร์บนเครื่องเกตเวย์ของคุณ ในไดเรกทอรีเดียวกันกับที่คุณคัดลอก sapcrypto สร้างไฟล์ที่ชื่อ sapcrypto ด้วยเนื้อหาต่อไปนี้:

    ```
    ccl/snc/enable_kerberos_in_client_role = 1
    ```

    ไฟล์ .ini มีข้อมูลการกำหนดค่าที่จำเป็นโดย CommonCryptoLib เพื่อเปิดใช้งาน SSO ในสถานการณ์เกตเวย์

    > [!NOTE]
    > ไฟล์เหล่านี้จะต้องถูกจัดเก็บไว้ในตำแหน่งที่ตั้งเดียวกัน อีกอย่างหนึ่ง _/path/to/sapcrypto/_ ควรมีทั้ง sapcrypto.ini และ sapcrypto.dll

    ทั้งผู้ใช้บริการเกตเวย์และผู้ใช้ Active Directory (AD) ที่ผู้ใช้บริการจะเลียนแบบจำเป็นต้องอ่านและใช้สิทธิ์สำหรับทั้งสองไฟล์ เราขอแนะนำการให้สิทธิ์ทั้งไฟล์. ini และ. dll กับกลุ่มผู้ใช้ที่ได้รับการรับรองความถูกต้อง สำหรับวัตถุประสงค์ในการทดสอบ คุณยังสามารถมอบสิทธิ์เหล่านี้ให้กับทั้งผู้ใช้บริการเกตเวย์และผู้ใช้ Active Directory ที่คุณจะใช้สำหรับทดการทดสอบ ในภาพหน้าจอด้านล่าง เราได้ให้สิทธิ์กับกลุ่มผู้ใช้ที่ได้รับการรับรองความถูกต้องในการ **อ่าน&amp; ใช้** สำหรับ sapcrypto.dll:

    ![ผู้ใช้ที่ได้รับการรับรองความถูกต้อง](media/service-gateway-sso-kerberos/authenticated-users.png)

1. ถ้าคุณไม่มีแหล่งข้อมูลเซิร์ฟเวอร์ SAP BW บนหน้า **จัดการเกตเวย์** ในบริการของ Power BI ให้เพิ่มแหล่งข้อมูล ถ้าคุณมีแหล่งข้อมูล BW ที่เชื่อมโยงกับเกตเวย์ที่คุณต้องการให้การเชื่อมต่อ SSO ไปยังโฟลว์เสร็จแล้ว ให้เตรียมเพื่อแก้ไข เลือก**SAP Business Warehouse** เป็น**ชนิดแหล่งข้อมูล**ถ้าคุณต้องการสร้างการเชื่อมต่อ SSO ไปยังเซิร์ฟเวอร์แอปพลิเคชัน BW ของคุณ เลือก**SAP Business Warehouse Message Server** ถ้าคุณต้องการสร้างการเชื่อมต่อ SSO ไปยังเซิร์ฟเวอร์ข้อความ BW

    สำหรับ **ไลบรารี SNC** ให้เลือกตัวแปรสภาพแวดล้อม **SNC\_LIB หรือ SNC\_LIB\_64** หรือ **กำหนดเอง** หากคุณเลือกตัวเลือก **SNC\_LIB** คุณต้องตั้งค่าของตัวแปรสภาพแวดล้อม**SNC\_LIB\_64** บนเครื่องเกตเวย์ไปยังเส้นทางสัมบูรณ์ของสำเนา 64 บิท sapcrypto.dll บนเครื่องเกตเวย์ เช่น C:\Users\Test\Desktop\sapcrypto.dll หากคุณเลือก **กำหนดเอง** วางเส้นทางสัมบูรณ์ไปยัง sapcrypto .dll ไว้ในเขตข้อมูลเส้นทางไลบรารี SNC ที่ปรากฎบนหน้า **จัดการเกตเวย์** สำหรับ**ชื่อคู่ค้า SNC** ของบริษัทให้ใส่ชื่อ SNC ของเซิร์ฟเวอร์ BW ของคุณ ภายใต้ **การตั้งค่าขั้นสูง** ตรวจสอบให้แน่ใจว่ามีการเลือก**ใช้ SSO ผ่าน Kerberos สำหรับคิวรี DirectQuery** เขตข้อมูลอื่นๆควรได้รับการเติมในขณะที่คุณกำลังสร้างการเชื่อมต่อการรับรองความถูกต้องของ Windows จาก PBI Desktop

1. สร้างตัวแปรสภาพแวดล้อมระบบ CCL\_PROFILE และชี้ที่ตัวแปรที่ sapcrypto.ini:

    ![ตัวแปรสภาพแวดล้อมระบบ CCL\_PROFILE](media/service-gateway-sso-kerberos/ccl-profile-variable.png)

    โปรดทราบว่าไฟล์ sapcrypto .dll และ .ini ต้องอยู่ในตำแหน่งเดียวกัน ในตัวอย่างที่แสดงอยู่ข้างต้นที่ sapcrypto1.ini อยู่บนเดสก์ท็อป sapcrypto.dll ควรจะอยู่บนเดสก์ท็อปเช่นกัน

1. รีสตาร์ทบริการเกตเวย์:

    ![รีสตาร์ทบริการเกตเวย์](media/service-gateway-sso-kerberos/restart-gateway-service.png)

1. [เปิดใช้รายงาน Power BI](service-gateway-sso-kerberos.md#run-a-power-bi-report)

## <a name="troubleshooting"></a>การแก้ไขปัญหา

ถ้าคุณไม่สามารถรีเฟรชรายงานในบริการของ Power BI คุณสามารถใช้การติดตามเกตเวย์ การติดตาม CPIC และการติดตาม CommonCryptoLib เพื่อช่วยในการวินิจฉัยปัญหาได้ การติดตาม CPIC และ CommonCryptoLib เป็นผลิตภัณฑ์ของ SAP ดังนั้น Microsoft จึงไม่สามารถให้การสนับสนุนโดยตรงได้ สำหรับผู้ใช้ Active Directory ที่จะได้รับสิทธิ์การเข้าถึงแบบ SSO ใน BW การกำหนดค่า Active Directory บางอย่างอาจจำเป็นต้องมีผู้ใช้ที่เป็นสมาชิกของกลุ่มผู้ดูแลระบบบนเครื่องที่มีการติดตั้งเกตเวย์

1. **รายการบันทึกเกตเวย์:** เพียงแค่สร้างปัญหาขึ้นมาใหม่ เปิด [แอปเกตเวย์](https://docs.microsoft.com/data-integration/gateway/service-gateway-app), ไปที่แท็บ **การวินิจฉัย**, และเลือก **ส่งออกรายการบันทึก** :

    ![ส่งออกรายการบันทึกเกตเวย์](media/service-gateway-sso-kerberos/export-gateway-logs.png)

1. **การติดตาม CPIC:** เมื่อต้องการเปิดใช้งานการติดตาม CPIC ให้ตั้งค่าตัวแปรสภาพแวดล้อมสองรายการ: CPIC\_TRACE and CPIC\_TRACE\_DIR. ตัวแปรแรกตั้งค่าระดับการติดตามและตัวแปรที่สองตั้งค่าไดเรกทอรีไฟล์การติดตาม ไดเรกทอรีต้องอยู่ในตำแหน่งที่สมาชิกของกลุ่มผู้ใช้ที่ได้รับการรับรองความถูกต้องสามารถเขียนถึงได้ ตั้งค่า CPIC\_TRACE เป็น 3 และ CPIC\_TRACE\_DIR เป็นไดเรกทอรีใดก็ได้ที่คุณต้องการติดตามไฟล์ที่เขียนถึง

    ![การติดตาม CPIC](media/service-gateway-sso-kerberos/cpic-tracing.png)

    สร้างปัญหาขึ้นมาใหม่และตรวจสอบว่า CPIC\_TRACE\_DIR มีไฟล์การติดตาม

1. **การติดตาม CommonCryptoLib:** เปิดการติดตาม CommonCryptoLib โดยการเพิ่มสองบรรทัดลงในไฟล์ sapcrypto.ini ที่คุณสร้างไว้ก่อนหน้านี้:

    ```
    ccl/trace/level=5
    ccl/trace/directory=<drive>:\logs\sectrace
    ```

    ตรวจสอบให้แน่ใจเพื่อเปลี่ยนตัวเลือก _ccl/trace/directory_ เป็นสมาชิกในตำแหน่งของกลุ่มผู้ใช้ที่ได้รับการรับรองความถูกต้องสามารถเขียนถึง อีกวิธีหนึ่งคือสร้างไฟล์ .ini ใหม่เพื่อเปลี่ยนลักษณะการทำงานนี้ ในไดเรกทอรีเดียวกันกับ sapcrypto.ini และ sapcrypto.dll ให้สร้างไฟล์ที่ชื่อ sectrace.ini ด้วยเนื้อหาด้านล่างนี้ แทนที่ตัวเลือกไดเรกทอรีด้วยตำแหน่งบนเครื่องของคุณที่ผู้ใช้ที่ได้รับการรับรองความถูกต้องสามารถเขียนถึง:

    ```
    LEVEL = 5

    DIRECTORY = <drive>:\logs\sectrace
    ```

    ในตอนนี้สร้างปัญหาขึ้นมาใหม่ และตรวจสอบว่าตำแหน่งที่ชี้ไปตามไดเรกทอรีมีไฟล์การติดตาม ตรวจสอบให้แน่ใจว่าได้ปิดใช้งานการติดตาม CPIC และ CCL เมื่อคุณดำเนินการเสร็จแล้ว

    สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการติดตาม CommonCryptoLib ให้ดู [SAP Note 2491573](https://launchpad.support.sap.com/#/notes/2491573) (ต้องมีผู้ใช้ s)

## <a name="next-steps"></a>ขั้นตอนถัดไป

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ**เกตเวย์ข้อมูลภายในองค์กร**และ **DirectQuery** ลองดูแหล่งข้อมูลต่อไปนี้:

* [เกตเวย์ข้อมูลภายในองค์กรคืออะไร](/data-integration/gateway/service-gateway-getting-started)
* [DirectQuery ใน Power BI](desktop-directquery-about.md)
* [แหล่งข้อมูลที่สนับสนุนโดย DirectQuery](desktop-directquery-data-sources.md)
* [DirectQuery และ SAP BW](desktop-directquery-sap-bw.md)
* [DirectQuery และ SAP HANA](desktop-directquery-sap-hana.md)

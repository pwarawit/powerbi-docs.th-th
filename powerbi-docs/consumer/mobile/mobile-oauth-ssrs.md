---
title: ใช้ OAuth เพื่อเชื่อมต่อกับเซิร์ฟเวอร์รายงาน Power BI และ SSRS
description: เรียนรู้วิธีการกำหนดค่าสภาพแวดล้อมของคุณ เพื่อสนับสนุนการรับรองความถูกต้อง OAuth ด้วยแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ เพื่อเชื่อมต่อกับ SQL Server Reporting Services 2016 หรือใหม่กว่า
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 06/07/2018
ms.openlocfilehash: 9673217cfd7c5af70bdd293e8d5df51e5e7dee07
ms.sourcegitcommit: 9278540467765043d5cb953bcdd093934c536d6d
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/03/2019
ms.locfileid: "67559075"
---
# <a name="using-oauth-to-connect-to-power-bi-report-server-and-ssrs"></a>ใช้ OAuth เพื่อเชื่อมต่อกับเซิร์ฟเวอร์รายงาน Power BI และ SSRS

เรียนรู้วิธีการกำหนดค่าสภาพแวดล้อมของคุณ เพื่อสนับสนุนการรับรองความถูกต้อง OAuth ด้วยแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ เพื่อเชื่อมต่อกับเซิร์ฟเวอร์รายงาน Power BI และ SQL Server Reporting Services 2016 หรือใหม่กว่า

![](media/mobile-oauth-ssrs/powerbi-mobile-oauth.png)

คุณสามารถใช้ OAuth เพื่อเชื่อมต่อกับเซิร์ฟเวอร์รายงาน Power BI และ Reporting Services เพื่อแสดงรายงานอุปกรณ์มือถือ หรือ KPI Windows Server 2016 มีการปรับปรุงบทบาท Web Application Proxy (WAP) เพื่ออนุญาตการรับรองความถูกต้องชนิดนี้

   > [!NOTE]
   > การดูรายงาน Power BI ที่โฮสต์อยู่ในเซิร์ฟเวอร์รายงานของ Power BI โดยใช้ WAP เพื่อตรวจสอบสิทธิ์ไม่ได้รับการสนับสนุนสำหรับแอป iOS และ Android ในขณะนี้

## <a name="requirements"></a>ข้อกำหนด

Windows Server 2016 เป็นที่ต้องการสำหรับเซิร์ฟเวอร์ Web Application Proxy (WAP) และ Active Directory Federation Services (ADFS) คุณไม่จำเป็นต้องมีโดเมนระดับการทำงาน Windows 2016

## <a name="domain-name-services-dns-configuration"></a>การกำหนดค่าบริการชื่อโดเมน (DNS)

คุณจะต้องระบุว่า URL สาธารณะคืออะไรที่จะทำให้แอป Power BI สำหรับอุปกรณ์เคลื่อนที่จะเชื่อมต่อ ตัวอย่างเช่น อาจมีลักษณะคล้ายกับต่อไปนี้

```https
https://reports.contoso.com
```

คุณจะต้องชี้ระเบียน DNS ของคุณสำหรับ**รายงาน**ไปยังที่อยู่ IP สาธารณะของเซิร์ฟเวอร์ Web Application Proxy (WAP) นอกจากนี้คุณจะจำเป็นต้องกำหนดค่าระเบียน DNS สาธารณะสำหรับเซิร์ฟเวอร์ ADFS ของคุณ ตัวอย่างเช่น คุณอาจกำหนดค่าเซิร์ฟเวอร์ ADFS ด้วย URL ต่อไปนี้

```https
https://fs.contoso.com
```

คุณจะต้องชี้ระเบียน DNS ของคุณสำหรับ **fs** ไปยังที่อยู่ IP สาธารณะของเซิร์ฟเวอร์ Web Application Proxy (WAP) เนื่องจากจะถูกประกาศเป็นส่วนหนึ่งของแอปพลิเคชัน WAP

## <a name="certificates"></a>ใบรับรอง

คุณจะต้องกำหนดค่าใบรับรองสำหรับทั้งแอปพลิเคชัน WAP และเซิร์ฟเวอร์ ADFS ใบรับรองเหล่านี้ทั้งสองต้องเป็นส่วนหนึ่งของหน่วยงานใบรับรองที่ถูกต้องที่อุปกรณ์เคลื่อนที่ของคุณรู้จัก

## <a name="reporting-services-configuration"></a>การกำหนดค่า Reporting Services

ไม่มีอะไรมากที่ต้องกำหนดค่าทางด้าน Reporting Services เราต้องการตรวจสอบให้แน่ใจว่า เรามีชื่อบริการหลักที่ถูกต้อง (SPN) เพื่อเปิดใช้งานการรับรองความถูกต้อง Kerberos ที่เหมาะสมให้เกิดขึ้น และเซิร์ฟเวอร์ Reporting Services จะถูกเปิดใช้งานสำหรับการรับรองความถูกต้องในการเจรจา

### <a name="service-principal-name-spn"></a>ชื่อบริการหลัก (SPN)

SPN เป็นตัวระบุเฉพาะสำหรับบริการที่ใช้การรับรองความถูกต้อง Kerberos คุณจะต้องตรวจสอบให้แน่ใจว่า คุณมี SPN HTTP ที่เหมาะสมสำหรับเซิร์ฟเวอร์รายงานของคุณ

สำหรับข้อมูลเกี่ยวกับวิธีการกำหนดค่าชื่อบริการหลัก (SPN) ที่เหมาะสมสำหรับเซิร์ฟเวอร์รายงานของคุณ ดู[ลงทะเบียน ชื่อบริการหลัก (SPN) สำหรับเซิร์ฟเวอร์รายงาน](https://msdn.microsoft.com/library/cc281382.aspx)

### <a name="enabling-negotiate-authentication"></a>การเปิดใช้งานการรับรองความถูกต้องในการเจรจา

ในการเปิดใช้งานเซิร์ฟเวอร์รายงานเพื่อใช้การรับรองความถูกต้อง Kerberos คุณจะต้องกำหนดค่าชนิดของการรับรองความถูกต้องของเซิร์ฟเวอร์รายงานให้เป็น RSWindowsNegotiate คุณสามารถทำได้ภายในไฟล์ rsreportserver.config

```xml
<AuthenticationTypes>  
    <RSWindowsNegotiate />  
    <RSWindowsKerberos />  
    <RSWindowsNTLM />  
</AuthenticationTypes>
```

สำหรับข้อมูลเพิ่มเติม ดู[ปรับเปลี่ยนแฟ้มการกำหนดค่า Reporting Services](https://msdn.microsoft.com/library/bb630448.aspx) และ[กำหนดค่าการรับรองความถูกต้องของ Windows บนเซิร์ฟเวอร์รายงาน](https://msdn.microsoft.com/library/cc281253.aspx)

## <a name="active-directory-federation-services-adfs-configuration"></a>การกำหนดค่า Active Directory Federation Services (ADFS)

คุณจะต้องกำหนดค่า ADFS บนเซิร์ฟเวอร์ Windows 2016 ภายในสภาพแวดล้อมของคุณ ซึ่งสามารถทำได้ผ่านตัวจัดการเซิร์ฟเวอร์ และเลือก เพิ่มบทบาทและคุณลักษณะ ด้านล่างจัดการ สำหรับข้อมูลเพิ่มเติม ดู[Active Directory Federation Services](https://technet.microsoft.com/windows-server-docs/identity/active-directory-federation-services)

### <a name="create-an-application-group"></a>สร้างกลุ่มแอปพลิเคชัน

ภายในหน้าจอการจัดการ AD FS คุณจะต้องสร้างกลุ่มแอปพลิเคชันสำหรับ Reporting Services ซึ่งจะรวมข้อมูลสำหรับแอป Power BI สำหรับอุปกรณ์เคลื่อนที่

คุณสามารถสร้างกลุ่มแอปพลิเคชัน ด้วยขั้นตอนต่อไปนี้

1. ภายในแอปการจัดการ AD FS คลิกขวา**กลุ่มแอปพลิเคชัน**และเลือก**เพิ่มกลุ่มแอปพลิเคชัน...**

   ![การเพิ่มมแอปพลิเคชัน ADFS](media/mobile-oauth-ssrs/adfs-add-application-group.png)

2. ภายในการเพิ่มตัวช่วยสร้างกลุ่มแอปพลิเคชัน ใส่**ชื่อ**สำหรับกลุ่มแอปพลิเคชันและเลือก**แอปพลิเคชันดั้งเดิมที่เข้าถึง API เว็บ**

   ![ตัวช่วยสร้างกลุ่มแอปพลิเคชัน ADFS 01](media/mobile-oauth-ssrs/adfs-application-group-wizard1.png)

3. เลือก**ถัดไป**

4. ใส่**ชื่อ**สำหรับแอปพลิเคชันที่คุณกำลังเพิ่ม 

5. ในขณะ **ID ไคลเอ็นต์**ของคุณจะถูกสร้างโดยอัตโนมัติ ใส่ใน *484d54fc-b481-4eee-9505-0258a1913020* สำหรับทั้ง iOS และ Android

6. คุณจะต้องเพิ่ม **URL ที่เปลี่ยนเส้นทาง**ต่อไปนี้:

   **รายการสำหรับ Power BI สำหรับอุปกรณ์เคลื่อนที่ – iOS:**  
   msauth://code/mspbi-adal://com.microsoft.powerbimobile  
   msauth://code/mspbi-adalms://com.microsoft.powerbimobilems  
   mspbi adal://com.microsoft.powerbimobile  
   mspbi adalms://com.microsoft.powerbimobilems

   **แอป Android เพียงต้องการสิ่งต่อไปนี้:**  
   urn:ietf:wg:oauth:2.0:oob

   ![ตัวช่วยสร้างกลุ่มแอปพลิเคชัน ADFS 02](media/mobile-oauth-ssrs/adfs-application-group-wizard2.png)
7. เลือก**ถัดไป**

8. ใส่ URL สำหรับเซิร์ฟเวอร์รายงานของคุณ URL นี้เป็น URL ภายนอกที่จะเข้าชม Web Application Proxy ของคุณ ซึ่งควรอยู่ในรูปแบบต่อไปนี้

   > [!NOTE]
   > URL นี้เป็นตัวพิมพ์ใหญ่-เล็ก

   *https://< report server url >/reports*

   ![ตัวช่วยสร้างกลุ่มแอปพลิเคชัน ADFS 03](media/mobile-oauth-ssrs/adfs-application-group-wizard3.png)
9. เลือก**ถัดไป**

10. เลือก**นโยบายการควบคุมการเข้าถึง**ที่เหมาะกับความต้องการขององค์กรของคุณ

    ![ตัวช่วยสร้างกลุ่มแอปพลิเคชัน ADFS 04](media/mobile-oauth-ssrs/adfs-application-group-wizard4.png)

11. เลือก**ถัดไป**

12. เลือก**ถัดไป**

13. เลือก**ถัดไป**

14. เลือก**ปิด**

เมื่อเสร็จสมบูรณ์ คุณควรเห็นคุณสมบัติของกลุ่มแอปพลิเคชันของคุณที่คล้ายกับต่อไปนี้

![ตัวช่วยสร้างกลุ่มแอปพลิเคชัน ADFS](media/mobile-oauth-ssrs/adfs-application-group.png)

## <a name="web-application-proxy-wap-configuration"></a>การกำหนดค่า Web Application Proxy (WAP)

คุณจะต้องเปิดใช้งานสำหรับบทบาท Windows ของ Web Application Proxy (บทบาท) บนเซิร์ฟเวอร์ในสภาพแวดล้อมของคุณ ซึ่งต้องอยู่บนเซิร์ฟเวอร์ Windows 2016 สำหรับข้อมูลเพิ่มเติม ดู [Web Application Proxy ใน Windows Server 2016 ](https://technet.microsoft.com/windows-server-docs/identity/web-application-proxy/web-application-proxy-windows-server)และ[เผยแพร่แอปพลิเคชันโดยใช้การรับรองความถูกต้องล่วงหน้า AD FS](https://technet.microsoft.com/windows-server-docs/identity/web-application-proxy/publishing-applications-using-ad-fs-preauthentication#a-namebkmk14apublish-an-application-that-uses-oauth2-such-as-a-windows-store-app)

### <a name="constrained-delegation-configuration"></a>การกำหนดค่าการมอบหมายที่มีข้อจำกัด

เพื่อการเปลี่ยนจากการรับรองความถูกต้องของ OAuth เป็นการรับรองความถูกต้องของ Windows เราจำเป็นต้องใช้การมอบหมายที่มีข้อจำกัดด้วยการเปลี่ยนโพรโทคอล นี่คือส่วนหนึ่งของการกำหนดค่า Kerberos เราได้กำหนด SPN ของ Reporting Services SPN ภายในการกำหนดค่า Reporting Services แล้ว

เราต้องกำหนดค่าการมอบหมายที่มีข้อจำกัดบนบัญชีผู้ใช้ภายในเครื่องของเซิร์ฟเวอร์ WAP ภายใน Active Directory คุณอาจจำเป็นต้องทำงานกับผู้ดูแลโดเมนถ้าคุณไม่มีสิทธิ์ใน Active Directory

ในการกำหนดค่าการมอบหมายที่มีข้อจำกัด คุณจะต้องทำต่อไปนี้

1. บนเครื่องที่มีเครื่องมือ Active Directory ติดตั้งไว้แล้ว ให้เปิดใช้**ผู้ใช้และคอมพิวเตอร์ Active Directory**

2. ค้นหาบัญชีผู้ใช้ภายในเครื่องสำหรับเซิร์ฟเวอร์ WAP ของคุณ ตามค่าเริ่มต้นจะอยู่ในคอนเทนเนอร์ของคอมพิวเตอร์

3. คลิกขวาที่เซิร์ฟเวอร์ WAP และไปที่**คุณสมบัติ**

4. เลือกแท็บ**การมอบหมาย**

5. เลือก**เชื่อถือคอมพิวเตอร์เครื่องนี้สำหรับการมอบหมายบริการที่ระบุเท่านั้น**แล้วเลือก**ใช้โพรโทคอลการรับรองความถูกต้องใด ๆ**

   ![WAP Constrained](media/mobile-oauth-ssrs/wap-contrained-delegation1.png)

   ซึ่งเป็นการตั้งค่าการมอบหมายที่มีข้อจำกัดสำหรับบัญชีผู้ใช้ภายในเครื่องของเซิร์ฟเวอร์ WAP เราจึงต้องระบุบริการที่เครื่องนี้ได้รับอนุญาตให้ผู้รับมอบสิทธิ์

6. เลือก**เพิ่ม...** ด้านล่างกล่องบริการ

   ![WAP Constrained 02](media/mobile-oauth-ssrs/wap-contrained-delegation2.png)

7. เลือก**ผู้ใช้หรือคอมพิวเตอร์...**

8. ใส่บัญชีผู้ใช้บริการที่คุณกำลังใช้สำหรับ Reporting Services นี่คือบัญชีที่คุณเพิ่ม SPN ไปภายในการกำหนดค่า Reporting Services

9. เลือก SPN สำหรับ Reporting Services จากนั้น เลือก**ตกลง**

   > [!NOTE]
   > คุณอาจเห็นเพียง NetBIOS SPN ซึ่งแท้จริงแล้วจะเลือกทั้ง NetBIOS และ FQDN SPNs ถ้ามีอยู่ทั้งสอง

   ![WAP Constrained 03](media/mobile-oauth-ssrs/wap-contrained-delegation3.png)

10. ผลลัพธ์ควรมีลักษณะคล้ายกับต่อไปนี้เมื่อมีการเลือกกล่องกาเครื่องหมาย**ขยาย**

    ![WAP Constrained 04](media/mobile-oauth-ssrs/wap-contrained-delegation4.png)

11. เลือก**ตกลง**

### <a name="add-wap-application"></a>เพิ่มแอปพลิเคชัน WAP

ในขณะที่คุณสามารถเผยแพร่แอปพลิเคชันภายในคอนโซลการจัดการการเข้าถึงรายงาน เราจะต้องสร้างแอปพลิเคชันผ่านทาง PowerShell นี่คือคำสั่งเพื่อเพิ่มแอปพลิเคชัน

```powershell
Add-WebApplicationProxyApplication -Name "Contoso Reports" -ExternalPreauthentication ADFS -ExternalUrl https://reports.contoso.com/ -ExternalCertificateThumbprint "0ff79c75a725e6f67e3e2db55bdb103efc9acb12" -BackendServerUrl http://ContosoSSRS/ -ADFSRelyingPartyName "Reporting Services - Web API" -BackendServerAuthenticationSPN "http/ContosoSSRS.contoso.com" -UseOAuthAuthentication
```

| พารามิเตอร์ | ข้อคิดเห็น |
| --- | --- |
| **ADFSRelyingPartyName** |นี่คือชื่อของ API เว็บที่คุณสร้างขึ้นให้เป็นส่วนหนึ่งของ กลุ่มแอปพลิเคชัน ภายใน ADFS |
| **ExternalCertificateThumbprint** |นี่คือใบรับรองที่จะใช้สำหรับผู้ใช้ภายนอก เป็นสิ่งสำคัญว่าใบรับรองนี้จะใช้ได้ถูกต้องบนอุปกรณ์เคลื่อนที่และมาจากผู้ออกใบรับรองที่เชื่อถือได้ |
| **BackendServerUrl** |นี่คือ URL ไปยังเซิร์ฟเวอร์รายงานจากเซิร์ฟเวอร์ WAP ถ้าเซิร์ฟเวอร์ WAP อยู่ใน DMZ คุณอาจต้องใช้ชื่อโดเมนแบบเต็ม ตรวจสอบให้แน่ใจว่าคุณสามารถเข้าชม URL นี้จากเว็บเบราว์เซอร์บนเซิร์ฟเวอร์ WAP |
| **BackendServerAuthenticationSPN** |นี่คือ SPN ที่คุณสร้างขึ้นให้เป็นส่วนหนึ่งของการกำหนดค่า Reporting Services |

### <a name="setting-integrated-authentication-for-the-wap-application"></a>ตั้งค่าการรับรองความถูกต้องรวมสำหรับแอปพลิเคชัน WAP

หลังจากที่คุณเพิ่มแอปพลิเคชัน WAP คุณจะต้องตั้งค่า BackendServerAuthenticationMode เพื่อใช้ IntegratedWindowsAuthentication เพื่อตั้งค่านี้ คุณต้องใช้ ID จากแอปพลิเคชัน WAP

```powershell
Get-WebApplicationProxyApplication “Contoso Reports” | fl
```

![](media/mobile-oauth-ssrs/wap-application-id.png)

เรียกใช้คำสั่งต่อไปนี้เพื่อตั้งค่า BackendServerAuthenticationMode โดยใช้ ID ของแอปพลิเคชัน WAP

```powershell
Set-WebApplicationProxyApplication -id 30198C7F-DDE4-0D82-E654-D369A47B1EE5 -BackendServerAuthenticationMode IntegratedWindowsAuthentication
```

![](media/mobile-oauth-ssrs/wap-application-backendauth.png)

## <a name="connecting-with-the-power-bi-mobile-app"></a>เชื่อมต่อกับแอป Power BI สำหรับอุปกรณ์เคลื่อนที่

ภายในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ คุณจะต้องเชื่อมต่อกับอินสแตนซ์ Reporting Services ของคุณ เมื่อต้องการทำเช่นนั้น ให้ใส่ **URL ภายนอก**สำหรับแอปพลิเคชัน WAP ของคุณ

![](media/mobile-oauth-ssrs/powerbi-mobile-app1.png)

เมื่อคุณเลือก**เชื่อมต่อ**คุณจะถูกนำไปยังหน้าการเข้าสู่ระบบ ADFS ของคุณ ใส่ข้อมูลประจำตัวที่ถูกต้องสำหรับโดเมนของคุณ

![](media/mobile-oauth-ssrs/powerbi-mobile-app2.png)

หลังจากที่คุณเลือก**ลงชื่อเข้าใช้**คุณจะเห็นองค์ประกอบจากเซิร์ฟเวอร์ Reporting Services ของคุณ

![](media/mobile-oauth-ssrs/powerbi-mobile-app2.png)

## <a name="multi-factor-authentication"></a>การรับรองความถูกต้องแบบหลายปัจจัย

คุณสามารถเปิดใช้งานการรับรองความถูกต้องแบบหลายปัจจัยเพื่อเปิดใช้งานความปลอดภัยเพิ่มเติมสำหรับสภาพแวดล้อมของคุณ เมื่อต้องการเรียนรู้เพิ่มเติม ดู[กำหนดค่า AD FS 2016 และ Azure MFA](https://technet.microsoft.com/windows-server-docs/identity/ad-fs/operations/configure-ad-fs-2016-and-azure-mfa)

## <a name="troubleshooting"></a>การแก้ไขปัญหา

### <a name="you-receive-the-error-failed-to-login-to-ssrs-server-verify-server-configuration"></a>คุณได้รับข้อผิดพลาดว่า ไม่สามารถเข้าสู่ระบบเซิร์ฟเวอร์ SSRS ตรวจสอบการกำหนดค่าของเซิร์ฟเวอร์

![](media/mobile-oauth-ssrs/powerbi-mobile-error.png)

คุณสามารถตั้งค่า [Fiddler](http://www.telerik.com/fiddler) เพื่อทำหน้าที่เป็นพร็อกซีสำหรับอุปกรณ์เคลื่อนที่ของคุณเพื่อดูว่าการร้องขอไปได้ไกลเท่าใด เพื่อเปิดใช้งานพร็อกซี Fiddler สำหรับอุปกรณ์โทรศัพท์ของคุณ คุณจะต้องตั้งค่า [CertMaker สำหรับ iOS และ Android](http://www.telerik.com/fiddler/add-ons) บนเครื่องที่เรียกใช้ Fiddler นี่คือ add-on จาก Telerik สำหรับ Fiddler

ถ้าการลงชื่อเข้าใช้สำเร็จเรียบร้อยเมื่อใช้ Fiddler คุณอาจมีใบรับรองที่ออกพร้อมกับแอปพลิเคชัน WAP หรือเซิร์ฟเวอร์ ADFS คุณสามารถใช้เครื่องมือ เช่น [Microsoft Message Analyzer](https://www.microsoft.com/download/details.aspx?id=44226) เพื่อตรวจสอบถ้าใบรับรองนั้นถูกต้อง

## <a name="next-steps"></a>ขั้นตอนถัดไป

[ลงทะเบียนชื่อบริการหลัก (SPN) สำหรับเซิร์ฟเวอร์รายงาน](https://msdn.microsoft.com/library/cc281382.aspx)  
[ปรับเปลี่ยนแฟ้มการกำหนดค่า Reporting Services](https://msdn.microsoft.com/library/bb630448.aspx)  
[กำหนดค่าการรับรองความถูกต้องของ Windows บนเซิร์ฟเวอร์รายงาน](https://msdn.microsoft.com/library/cc281253.aspx)  
[Active Directory Federation Services](https://technet.microsoft.com/windows-server-docs/identity/active-directory-federation-services)  
[Web Application Proxy ใน Windows Server 2016](https://technet.microsoft.com/windows-server-docs/identity/web-application-proxy/web-application-proxy-windows-server)  
[เผยแพร่แอปพลิเคชันโดยใช้การรับรองความถูกต้องล่วงหน้า AD FS](https://technet.microsoft.com/windows-server-docs/identity/web-application-proxy/publishing-applications-using-ad-fs-preauthentication#a-namebkmk14apublish-an-application-that-uses-oauth2-such-as-a-windows-store-app)  
[กำหนดค่า AD FS 2016 และ Azure MFA](https://technet.microsoft.com/windows-server-docs/identity/ad-fs/operations/configure-ad-fs-2016-and-azure-mfa)  
มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)

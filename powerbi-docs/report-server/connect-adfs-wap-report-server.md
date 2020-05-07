---
title: ใช้ Web Application Proxy และ Active Directory Federated Services - เซิร์ฟเวอร์รายงาน Power BI
description: เรียนรู้วิธีการใช้ Web Application Proxy (WAP) และ  Active Directory Federated Services (AD FS) เพื่อเชื่อมต่อกับเซิร์ฟเวอร์รายงาน Power BI และ SQL Server Reporting Services (SSRS) 2016 และใหม่กว่า
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/14/2020
ms.openlocfilehash: 2caa96aceef90ad1d25a521cbf4a3f699a2a64e0
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "76042451"
---
# <a name="use-web-application-proxy-and-active-directory-federated-services---power-bi-report-server"></a>ใช้ Web Application Proxy และ Active Directory Federated Services - เซิร์ฟเวอร์รายงาน Power BI

บทความนี้อธิบายวิธีการใช้ Web Application Proxy (WAP) และ  Active Directory Federated Services (AD FS) เพื่อเชื่อมต่อกับเซิร์ฟเวอร์รายงาน Power BI และ SQL Server Reporting Services (SSRS) 2016 และใหม่กว่า ด้วยการรวมนี้ ผู้ใช้ที่อยู่ห่างจากเครือข่ายขององค์กรสามารถเข้าถึงเซิร์ฟเวอร์รายงาน Power BI และรายงาน Reporting Services จากเบราว์เซอร์ลูกค้าของพวกเขา และได้รับการป้องกันโดยการรับรองความถูกต้องล่วงหน้าของ  AD FS สำหรับแอปสำหรับอุปกรณ์เคลื่อนที่ Power BI คุณยังจำเป็นต้อง [กำหนดค่า OAuth เพื่อเชื่อมต่อกับเซิร์ฟเวอร์รายงาน Power BI และ SSRS](../consumer/mobile/mobile-oauth-ssrs.md)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

### <a name="domain-name-services-dns-configuration"></a>การกำหนดค่าบริการชื่อโดเมน (DNS)

- กำหนด URL สาธารณะที่ผู้ใช้จะเชื่อมต่อ ควรมีลักษณะคล้ายกับตัวอย่างนี้: `https://reports.contosolab.com`
- กำหนดค่าระเบียน DNS สำหรับชื่อโฮสต์ของคุณ `reports.contosolab.com` ตัวอย่างเช่น เพื่อชี้ไปยังที่อยู่ IP สาธารณะของเซิร์ฟเวอร์ Web Application Proxy (WAP) 
- กำหนดค่า DNS สาธารณะสำหรับเซิร์ฟเวอร์ AD FS ของคุณ ตัวอย่างเช่น คุณอาจกำหนดค่าเซิร์ฟเวอร์ AD FS ด้วย URL ต่อไปนี้: `https://adfs.contosolab.com`
- กำหนดค่าระเบียน DNS ของคุณเพื่อชี้ไปยังที่อยู่ IP สาธารณะของเซิร์ฟเวอร์ Web Application Proxy (WAP) ตัวอย่างเช่น `adfs.contosolab.com` ซึ่งมีการเผยแพร่เป็นส่วนหนึ่งของแอปพลิเคชัน WAP

### <a name="certificates"></a>ใบรับรอง

คุณต้องกำหนดค่าใบรับรองสำหรับทั้งแอปพลิเคชัน WAP และเซิร์ฟเวอร์ AD FS ใบรับรองทั้งสองต้องเป็นส่วนหนึ่งของผู้มีสิทธิ์ออกใบรับรองที่ถูกต้องที่เครื่องของคุณรู้จัก

## <a name="1-configure-the-report-server"></a>1. กำหนดค่าเซิร์ฟเวอร์รายงาน

เราจำเป็นต้องตรวจสอบให้แน่ใจว่าเรามีชื่อบริการหลัก (SPN) ที่ถูกต้อง SPN ที่ถูกต้องจะเปิดใช้งานการรับรองความถูกต้อง Kerberos ที่เหมาะสมและเปิดใช้งานเซิร์ฟเวอร์รายงานสำหรับการรับรองความถูกต้องในการเจรจา

### <a name="service-principal-name-spn"></a>ชื่อบริการหลัก (SPN)

SPN เป็นตัวระบุเฉพาะสำหรับบริการที่ใช้การรับรองความถูกต้อง Kerberos ตรวจสอบให้แน่ใจว่า คุณมี SPN HTTP ที่เหมาะสมสำหรับเซิร์ฟเวอร์รายงานของคุณ

สำหรับข้อมูลเกี่ยวกับวิธีการกำหนดค่าชื่อบริการหลัก (SPN) ที่เหมาะสมสำหรับเซิร์ฟเวอร์รายงานของคุณ ดู[ลงทะเบียน ชื่อบริการหลัก (SPN) สำหรับเซิร์ฟเวอร์รายงาน](https://docs.microsoft.com/sql/reporting-services/report-server/register-a-service-principal-name-spn-for-a-report-server)

### <a name="enabling-negotiate-authentication"></a>การเปิดใช้งานการรับรองความถูกต้องในการเจรจา

ในการเปิดใช้งานเซิร์ฟเวอร์รายงานเพื่อใช้การรับรองความถูกต้อง Kerberos คุณต้องกำหนดค่าชนิดของการรับรองความถูกต้องของเซิร์ฟเวอร์รายงานให้เป็น RSWindowsNegotiate คุณสามารถกำหนดค่าได้ภายในไฟล์ rsreportserver.config

```
<AuthenticationTypes>

    <RSWindowsNegotiate />

    <RSWindowsNTLM />

</AuthenticationTypes>
```

สำหรับข้อมูลเพิ่มเติม ดู[ปรับเปลี่ยนแฟ้มการกำหนดค่า Reporting Services](https://docs.microsoft.com/sql/reporting-services/report-server/modify-a-reporting-services-configuration-file-rsreportserver-config) และ[กำหนดค่าการรับรองความถูกต้องของ Windows บนเซิร์ฟเวอร์รายงาน](https://docs.microsoft.com/sql/reporting-services/security/configure-windows-authentication-on-the-report-server)

## <a name="2-configure-active-directory-federation-services-ad-fs"></a>2. กำหนดค่า Active Directory Federation Services (AD FS) 

คุณต้องกำหนดค่า AD FS บนเซิร์ฟเวอร์ Windows 2016 ภายในสภาพแวดล้อมของคุณ การกำหนดค่าสามารถทำได้ผ่านตัวจัดการเซิร์ฟเวอร์ และการเลือกเพิ่มบทบาทและคุณลักษณะซึ่งอยู่ด้านล่างจัดการ สำหรับข้อมูลเพิ่มเติม ดู[Active Directory Federation Services](https://docs.microsoft.com/windows-server/identity/active-directory-federation-services)

บนเซิร์ฟเวอร์ AD FS ให้ใช้แอปการจัดการ AD FS ในการทำตามขั้นตอนเหล่านี้

1. คลิกขวา **ความน่าเชื่อถือของฝ่ายที่เกี่ยวช้อง** > **เพิ่มความน่าเชื่อถือของฝ่ายที่เกี่ยวข้อง**

    ![ความน่าเชื่อถือของฝ่ายที่เกี่ยวข้อง](media/connect-adfs-wap-report-server/report-server-adfs-add-relying-party-trust.png)

2. ทำตามขั้นตอนในตัวช่วยสร้าง **เพิ่มความน่าเชื่อถือของฝ่ายที่เกี่ยวข้อง** 

    เลือกตัวเลือก **ที่ไม่ได้รับการอ้างสิทธิ์** เพื่อใช้การรักษาความปลอดภัยรวมของ Windows ในฐานะกลไกการรับรองความถูกต้อง

    ![ยินดีต้อนรับตัวช่วยสร้างการเพิ่มความน่าเชื่อถือของฝ่ายที่เกี่ยวข้อง](media/connect-adfs-wap-report-server/report-server-adfs-add-relying-party-trust-welcome.png)

    กรอกชื่อที่คุณต้องการใน **ระบุชื่อที่แสดง** และเลือก **ถัดไป**
    เพิ่มตัวระบุความน่าเชื่อถือของฝ่ายที่เกี่ยวข้อง: `<ADFS\_URL>/adfs/services/trust`

    ตัวอย่างเช่น: `https://adfs.contosolab.com/adfs/services/trust`

    ![เซิร์ฟเวอร์รายงาน Power BI](media/connect-adfs-wap-report-server/report-server-adfs-configure-identifiers.png)

    เลือก **นโยบายการควบคุมการเข้าถึง** ที่เหมาะกับความต้องการขององค์กรของคุณ แล้วเลือก **ถัดไป**

    ![เลือกการควบคุมการเข้าถึง](media/connect-adfs-wap-report-server/report-server-adfs-choose-access-control.png)
    
    เลือก **ถัดไป**จากนั้นเลือก **เสร็จสิ้น** เพื่อดำเนินการตัวช่วยสร้าง **เพิ่มความน่าเชื่อถือของฝ่ายที่เกี่ยวข้อง** ให้เสร็จสมบูรณ์

    เมื่อเสร็จสมบูรณ์แล้ว คุณสมบัติของความเชื่อถือของฝ่ายที่เกี่ยวข้อง ควรมีลักษณะดังต่อไปนี้

    ![ความน่าเชื่อถือของฝ่ายที่เกี่ยวข้อง](media/connect-adfs-wap-report-server/report-server-adfs-relying-party-trusts.png)

## <a name="3-configure-web-application-proxy-wap"></a>3. กำหนดค่า Web  Application Proxy (WAP)

คุณต้องเปิดใช้งานบทบาท Windows ของ Web Application Proxy (ROLE) บนเซิร์ฟเวอร์ในสภาพแวดล้อมของคุณ ซึ่งต้องอยู่บนเซิร์ฟเวอร์ Windows 2016 สำหรับข้อมูลเพิ่มเติม ดู [Web Application Proxy ใน Windows Server 2016 ](https://docs.microsoft.com/windows-server/remote/remote-access/web-application-proxy/web-application-proxy-windows-server)และ[เผยแพร่แอปพลิเคชันโดยใช้การรับรองความถูกต้องล่วงหน้า AD FS](https://docs.microsoft.com/windows-server/remote/remote-access/web-application-proxy/Publishing-Applications-using-AD-FS-Preauthentication)

### <a name="configure-constrained-delegation"></a>กำหนดค่าการมอบหมายที่มีข้อจำกัด

เพื่อการเปลี่ยนจากการรับรองความถูกต้องของ Forms เป็นการรับรองความถูกต้องของ Windows เราจำเป็นต้องใช้การมอบหมายที่มีข้อจำกัดด้วยการเปลี่ยนโพรโทคอล ขั้นตอนนี้คือส่วนหนึ่งของการกำหนดค่า Kerberos เราได้กำหนดเซิร์ฟเวอร์รายงาน SPN ไว้ภายในการกำหนดค่าเซิร์ฟเวอร์รายงานแล้ว

เราต้องกำหนดค่าการมอบหมายที่มีข้อจำกัดบนบัญชีผู้ใช้ภายในเครื่องของเซิร์ฟเวอร์ WAP ภายใน Active Directory คุณอาจจำเป็นต้องทำงานกับผู้ดูแลโดเมนถ้าคุณไม่มีสิทธิ์ใน Active Directory

ในการกำหนดค่าการมอบหมายที่มีการจำกัด ให้ทำตามขั้นตอนเหล่านี้

1. บนเครื่องที่มีเครื่องมือ Active Directory ติดตั้งไว้แล้ว ให้เปิดใช้**ผู้ใช้และคอมพิวเตอร์ Active Directory**
2. ค้นหาบัญชีผู้ใช้ภายในเครื่องสำหรับเซิร์ฟเวอร์ WAP ของคุณ ตามค่าเริ่มต้น บัญชีผู้ใช้ดังกล่าวจะอยู่ในคอนเทนเนอร์ของ **คอมพิวเตอร์**
3. คลิกขวาที่เซิร์ฟเวอร์ WAP และไปที่ **คุณสมบัติ**
4. บนแท็บ **การมอบหมาย** เลือก **เชื่อถือคอมพิวเตอร์เครื่องนี้สำหรับการมอบหมายบริการที่ระบุไว้เท่านั้น** แล้วเลือกใช้ **โพรโทคอลการรับรองความถูกต้องใดก็ตาม**

    ![เชื่อถือคอมพิวเตอร์เครื่องนี้](media/connect-adfs-wap-report-server/report-server-adfs-delegation-use-any.png)

1. ตัวเลือกนี้ตั้งค่าการมอบหมายที่มีข้อจำกัดสำหรับบัญชีผู้ใช้ภายในเครื่องของเซิร์ฟเวอร์ WAP เราจึงต้องระบุบริการที่เครื่องนี้ได้รับอนุญาตให้ผู้รับมอบสิทธิ์
2. เลือก **เพิ่ม** ใต้กล่องบริการ

    ![AD FS เพิ่มความน่าเชื่อถือ](media/connect-adfs-wap-report-server/report-server-adfs-trust-add.png)

1. เลือก **ผู้ใช้หรือคอมพิวเตอร์**
2. กรอกบัญชีบริการที่คุณกำลังใช้สำหรับเซิร์ฟเวอร์รายงาน บัญชีนี้เป็นบัญชีเดียวกันกับที่คุณใช้ในการเพิ่ม HTTP SPN ในส่วน  [การกำหนดค่าเซิร์ฟเวอร์รายงาน](#1-configure-the-report-server) ก่อนหน้านี้ 

3. เลือก HTTP SPN สำหรับเซิร์ฟเวอร์รายงานจากนั้นเลือก **ตกลง**

    > [!NOTE]
    > คุณอาจเห็นเพียง NetBIOS SPN ซึ่งแท้จริงแล้วจะเลือกทั้ง NetBIOS และ FQDN SPNs ถ้ามีทั้งสองรายการอยู่

1. เมื่อคุณเลือกกล่องกาเครื่องหมาย **ขยาย** ผลลัพธ์ที่ออกมาควรคล้ายคลึงกับตัวอย่างต่อไปนี้

    ![คุณสมบัติ WAP](media/connect-adfs-wap-report-server/report-server-wap-properties.png)

### <a name="add-wap-application"></a>เพิ่มแอปพลิเคชัน WAP

1. บนเซิร์ฟเวอร์ Web Application Proxy เปิดคอนโซล **การจัดการการเข้าถึงระยะไกล** และเลือก **Web Application Proxy** ในบานหน้าต่างการนำทาง 

2. ในบานหน้าต่าง **งาน** เลือก **เผยแพร่**

2. บนหน้าต้อนรับ เลือก **ถัดไป**

    ![ยินดีต้อนรับสู่ Publish](media/connect-adfs-wap-report-server/report-server-welcome-publish-new-app-wizard.png)

3. บนหน้า **การรับรองความถูกต้องล่วงหน้า** เลือก **Active Directory Federation Services (AD FS)** จากนั้นเลือก **ถัดไป**

    ![การตรวจสอบล่วงหน้า](media/connect-adfs-wap-report-server/report-server-preauthentication-new-app-wizard.png)

4. เลือกการรับรองความถูกต้องล่วงหน้า **เว็บและ MSOFBA** ในขณะที่เรากำลังจะตั้งค่าเฉพาะการเข้าถึงเบราว์เซอร์สำหรับเซิร์ฟเวอร์รายงาน และไม่รวมการเข้าถึงแอปสำหรับอุปกรณ์เคลื่อนที่

    ![ลูกค้าที่ได้รับการสนับสนุน](media/connect-adfs-wap-report-server/report-server-supported-clients-publish-new-app-wizard.png)

5. เพิ่ม **ฝ่ายที่เกี่ยวข้อง**ที่เราสร้างขึ้นในเซิร์ฟเวอร์ AD FS ดังที่แสดงด้านล่างแล้วเลือก **ถัดไป**

    ![การเผยแพร่ของฝ่ายที่เกี่ยวข้อง](media/connect-adfs-wap-report-server/report-server-relying-party-publish-new-app-wizard.png)

6. ในส่วน **URL ภายนอก** ให้ใส่ URL ที่สามารถเข้าถึงได้แบบสาธารณะที่กำหนดค่าบนเซิร์ฟเวอร์ WAP เพิ่ม URL ที่กำหนดค่าด้วยเซิร์ฟเวอร์รายงาน (ตัวจัดการการกำหนดค่าเซิร์ฟเวอร์รายงาน) ตามที่แสดงด้านล่างในส่วน **URL ของเซิร์ฟเวอร์ Backend** เพิ่ม SPN ของเซิร์ฟเวอร์รายงานในส่วนของ **SPN ของ เซิร์ฟเวอร์ Backend** 

    ![การตั้งค่าการเผยแพร่](media/connect-adfs-wap-report-server/report-server-publishing-settings-new-app-wizard.png)

7. เลือก **ถัดไป** และ **เผยแพร่**
8. เรียกใช้คำสั่ง PowerShell ต่อไปนี้เพื่อตรวจสอบการกำหนดค่า WAP

    ```
    Get-WebApplicationProxyApplication "PBIRSBrowser" | FL
    ```

    ![คำสั่ง PowerShell](media/connect-adfs-wap-report-server/report-server-powershell-get-webapplication.png)

## <a name="connect-to-the-report-server-through-the-browser"></a>เชื่อมต่อไปยังเซิร์ฟเวอร์รายงานผ่านเบราว์เซอร์

จากนั้นคุณสามารถเข้าถึง URL WAP สาธารณะได้ ตัวอย่างเช่น `https://reports.contosolab.com/ReportServer` สำหรับการบริการเว็บและ `https://reports.contosolab.com/Reports` สำหรับพอร์ทัลของเว็บจากเบราว์เซอร์ เมื่อคุณได้รับการรับรองความถูกต้องสำเร็จแล้ว คุณจะสามารถเรียกดูรายงานได้

![ลงชื่อเข้าใช้ AD FS ](media/connect-adfs-wap-report-server/report-server-adfs-sign-in.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [กำหนดค่า OAuth เพื่อเชื่อมต่อกับ Power BI Server และ SSRS](../consumer/mobile/mobile-oauth-ssrs.md)
*[ เซิร์ฟเวอร์รายงาน Power BI คืออะไร](get-started.md)  

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)


---
title: ลงทะเบียนแอปเพื่อฝังเนื้อหา Power BI
description: เรียนรู้วิธีการลงทะเบียนแอปพลิเคชันภายใน Azure Active Directory สำหรับการใช้งานด้วยการฝังเนื้อหา Power BI
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 11/26/2018
ms.openlocfilehash: 96f91eefeab038419ce64e31c7b4b5755d6adf2c
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54286599"
---
# <a name="register-an-azure-ad-app-to-embed-power-bi-content"></a>ลงทะเบียนแอป Azure AD เพื่อฝังเนื้อหา Power BI

เรียนรู้วิธีการลงทะเบียนแอปพลิเคชันภายใน Azure Active Directory (Azure AD) สำหรับการใช้งานด้วยการฝังเนื้อหา Power BI

คุณลงทะเบียนแอปพลิเคชันของคุณกับ Azure AD เพื่ออนุญาตให้แอปพลิเคชันของคุณเข้าถึง Power BI REST API เมื่อคุณลงทะเบียนแอปพลิเคชันจะทำให้คุณสร้างอัตลักษณ์แอปพลิเคชันของคุณและระบุสิทธิ์ไปยังทรัพยากร Power BI REST

> [!IMPORTANT]
> ก่อนที่คุณลงทะเบียนแอป Power BI คุณต้องการ[ผู้เช่า Azure Active Directory และผู้ใช้ขององค์กร](create-an-azure-active-directory-tenant.md) ถ้าคุณยังไม่ได้ลงทะเบียนสำหรับ Power BI ด้วยผู้ใช้ในผู้เช่าของคุณ การลงทะเบียนแอปจะไม่สามารถเสร็จสมบูรณ์ได้

มีสองวิธีในการลงทะเบียนแอปพลิเคชันของคุณ วิธีแรกคือด้วย [Power BI App Registration Tool](https://dev.powerbi.com/apps/) หรือคุณสามารถทำได้โดยตรงภายในพอร์ทัล Azure Power BI App Registration Tool เป็นตัวเลือกที่ง่ายที่สุดเนื่องจากมีเขตข้อมูลเพื่อที่ต้องกรอกน้อย ใช้พอร์ทัล Azure ถ้าคุณต้องการทำการเปลี่ยนแปลงไปยังแอปของคุณ

## <a name="register-with-the-power-bi-app-registration-tool"></a>ลงทะเบียนด้วย Power BI App Registration Tool

ลงทะเบียนแอปพลิเคชันของคุณใน **Azure Active Directory** เพื่อสร้างข้อมูลประจำตัวสำหรับแอปพลิเคชันของคุณ และระบุสิทธิ์ไปยังแหล่งข้อมูล Power BI REST เมื่อคุณลงทะเบียนแอปพลิเคชัน เช่น แอปคอนโซล หรือเว็บไซต์ คุณจะได้รับตัวระบุที่แอปพลิเคชันใช้เพื่อระบุตัวตนต่อผู้ใช้ว่าพวกเขาต้องการสิทธิ์

นี่คือวิธีการลงทะเบียนแอปพลิเคชันของคุณด้วย Power BI App Registration Tool:

1. ไปยัง [dev.powerbi.com/apps](https://dev.powerbi.com/apps)
2. เลือก**ลงชื่อเข้าใช้ด้วยบัญชีของคุณที่มีอยู่**
3. ใส่**ชื่อแอป**
4. การเลือกชนิดของแอป จะขึ้นอยู่กับชนิดของแอปพลิเคชันที่คุณกำลังใช้

   * ใช้**แอปแบบดั้งเดิม**สำหรับแอปที่ทำงานบนอุปกรณ์ไคลเอ็นต์ เลือก**แอปแบบดั้งเดิม** หากคุณกำลังฝังเนื้อหาสำหรับลูกค้าของคุณ โดยไม่ต้องคำนึงถึงว่าแอปพลิเคชันจริงคืออะไร
   * ใช้**เว็บแอปฝั่งเซิร์ฟเวอร์**สำหรับเว็บแอปหรือ API เว็บ

5. ป้อนค่าสำหรับ **URL ที่เปลี่ยนเส้นทาง**และ **URL โฮมเพจ** **URL ที่เปลี่ยนเส้นทาง** ทำงานได้กับ URL ใด ๆ ที่ถูกต้อง

    **URL โฮมเพจ**จะมีเฉพาะเมื่อคุณเลือกชนิดของแอปพลิเคชันเป็น**เว็บแอปฝั่งเซิร์ฟเวอร์**

    สำหรับตัวอย่าง *การฝังตัวสำหรับลูกค้าของคุณ* และ *integrate-dashboard-web-app* **URL ที่เปลี่ยนเส้นทางคือ** `http://localhost:13526/Redirect` สำหรับตัวอย่างรายงานและไทล์ **URL ที่เปลี่ยนเส้นคือ** `http://localhost:13526/`
6. เลือก API สำหรับแอปพลิเคชันที่มีสิทธิ์เข้าถึง สำหรับข้อมูลเพิ่มเติมเกี่ยวกับสิทธิ์การเข้าถึง Power BI ดูที่[สิทธิ์ Power BI](power-bi-permissions.md)

    ![การลงทะเบียนแอป API](media/register-app/app-registration-apis.png)
7. เลือก**ลงทะเบียนแอป**

    คุณจะได้ **ID ไคลเอ็นต์** และถ้าคุณเลือก**เว็บแอปฝั่งเซิร์ฟเวอร์** จะคุณได้รับ**ข้อมูลลับเฉพาะสำหรับลูกค้า** **ID ไคลเอ็นต์**สามารถเรียกข้อมูลได้จากพอร์ทัล Azure ในภายหลังถ้าต้องการ ถ้าคุณทำ**ข้อมูลลับเฉพาะสำหรับลูกค้า**หาย คุณจำเป็นต้องสร้างใหม่ภายในพอร์ทัล Azure

8. นำทางไปยัง Azure เพื่อเลือก **ให้สิทธิ์**

   > [!Note]
   > ผู้ใช้ซึ่งอยู่ในฐานะผู้เช่าต้อง **_ได้รับสิทธิ์_** ก่อนจึงจะสามารถทำตามขั้นตอนนี้ให้สำเร็จได้

* ไปที่ Azure
* ค้นหาและเลือก **การลงทะเบียนแอป**
* เลือกแอปของคุณ
* เลือก **การตั้งค่า**
* เลือก **สิทธิ์ที่จำเป็น**
* เลือก **บริการ Power BI** เพื่อตรวจสอบสิทธิ์ที่คุณเลือกจากไซต์การลงทะเบียนแอป
* เลือก **ให้สิทธิ์**

ตอนนี้คุณสามารถใช้แอปพลิเคชันที่ลงทะเบียนไว้เป็นส่วนหนึ่งของแอปพลิเคชันแบบกำหนดเองของคุณเพื่อโต้ตอบกับบริการ Power BI

> [!IMPORTANT]
> ถ้าคุณกำลังฝังเนื้อหาสำหรับลูกค้าของคุณ คุณจำเป็นต้องกำหนดสิทธิ์เพิ่มเติมภายในพอร์ทัล Azure สำหรับข้อมูลเพิ่มเติม ดู[นำสิทธิ์ไปใช้กับแอปพลิเคชันของคุณ](#apply-permissions-to-your-application)

## <a name="register-with-the-azure-portal"></a>ลงทะเบียนกับพอร์ทัล Azure

ตัวเลือกอื่นของคุณสำหรับการลงทะเบียนแอปพลิเคชันของคุณจะทำได้โดยตรงในพอร์ทัล Azure เมื่อต้องการลงทะเบียนแอปพลิเคชันของคุณ ทำตามขั้นตอนเหล่านี้

1. ยอมรับ[เงื่อนไขของ Microsoft Power BI API](https://powerbi.microsoft.com/api-terms)
2. ลงชื่อเข้าใช้[พอร์ทัล Azure](https://portal.azure.com)
3. เลือกผู้เช่า Azure AD ของคุณ โดยการเลือกบัญชีของคุณในมุมบนขวาของหน้า
4. ในบานหน้าต่างนำทางด้านซ้าย เลือก**บริการเพิ่มเติม**เลือก**การลงทะเบียนแอป**ด้านล่าง**ความปลอดภัย + ข้อมูลประจำตัว**และเลือก**การลงทะเบียนแอปพลิเคชันใหม่**

    ![ลงทะเบียนแอปใหม่](media/register-app/azuread-new-app-registration.png)
5. ทำตามพร้อมท์และสร้างแอปพลิเคชัน์ใหม่

   * สำหรับเว็บแอปพลิเคชัน ให้ใส่ URL ลงชื่อเข้าระบบ ซึ่งเป็น URL พื้นฐานของแอปคุณ ที่ผู้ใช้สามารถลงชื่อเข้าใช้ (เช่ น `http://localhost:13526`)
   * สำหรับแอปพลิเคชันดั้งเดิม ให้ใส่ **URL ที่เปลี่ยนเส้นทางซึ่ง** Azure AD ใช้เพื่อส่งกลับการตอบสนองโทเค็น ตรวจสอบว่าได้ป้อนค่าเฉพาะให้แอปพลิเคชันของคุณ (เช่น `http://myapplication/Redirect`)

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับวิธีการลงทะเบียนแอปพลิเคชันใน Azure Active Directory ดู[การรวมแอปพลิเคชันกับ Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications)

## <a name="how-to-get-the-client-id"></a>วิธีการขอรับ ID ไคลเอ็นต์

เมื่อคุณลงทะเบียนแอปพลิเคชัน คุณจะได้รับ **ID ไคลเอ็นต์**  **ID ไคลเอ็นต์** ใช้ระบุตัวตนของแอปพลิเคชัน เมื่อร้องขอสิทธิ์กับผู้ใช้

นี่คือวิธีการขอรับ ID ไคลเอ็นต์:

1. ลงชื่อเข้าใช้[พอร์ทัล Azure](https://portal.azure.com)
2. เลือกผู้เช่า Azure AD ของคุณ โดยการเลือกบัญชีของคุณในมุมบนขวาของหน้า
3. ในบานหน้าต่างนำทางด้านซ้าย เลือก**บริการเพิ่มเติม**และเลือก**การลงทะเบียนแอป**
4. เลือกแอปพลิเคชันที่คุณต้องการเรียกใช้ ID ไคลเอ็นต์
5. คุณจะเห็น **ID แอปพลิเคชัน** ที่แสดงในรูปของ GUID นี่คือ ID ไคลเอ็นต์สำหรับแอปพลิเคชัน

    ![ID ไคลเอ็นต์ที่แสดงรายการเป็น ID แอปพลิเคชันภายในลงทะเบียนแอป](media/register-app/powerbi-embedded-app-registration-client-id.png)

## <a name="apply-permissions-to-your-application-within-azure-ad"></a>นำสิทธิ์ไปใช้กับแอปพลิเคชันของคุณภายใน Azure AD

> [!IMPORTANT]
> ส่วนนี้นำไปใช้กับแอปพลิเคชันที่**กำลังฝังเนื้อหาสำหรับองค์กรของคุณ**เท่านั้น

เปิดใช้งานสิทธิ์เพิ่มเติมให้กับแอปพลิเคชันของคุณ นอกเหนือจากสิทธิ์ที่มีในหน้าลงทะเบียนแอปพลิเคชัน คุณสามารถทำสิ่งนี้ได้ผ่านพอร์ทัล Azure AD หรือผ่านทางการเขียนโปรแกรม

คุณจะต้องเข้าสู่ระบบ ด้วยบัญชี*หลัก*ที่ใช้สำหรับฝังตัว หรือบัญชีผู้ดูแลระบบส่วนกลาง

### <a name="using-the-azure-ad-portal"></a>ใช้พอร์ทัล Azure AD

1. เรียกดู[การลงทะเบียนแอป](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade)ภายในพอร์ทัล Azure และเลือกแอปที่คุณกำลังใช้สำหรับการฝัง

    ![ลงทะเบียนแอป Azure AD](media/register-app/powerbi-embedded-azuread-registered-apps.png)
2. เลือก**สิทธิ์ที่ต้องใช้**ด้านล่าง**การเข้าถึง API**

    ![แอป AD azure จำเป็นต้องได้รับการอนุญาตก่อน](media/register-app/powerbi-embedded-azuread-app-required-permissions.png)

3. ภายใน**สิทธิ์ที่ต้องใช้**เลือก**บริการ Power BI (Power BI)**

    ![การอนุญาตของแอป 03](media/register-app/powerbi-embedded-azuread-app-permissions03.png)

   > [!NOTE]
   > ถ้าคุณสร้างแอปโดยตรงในพอร์ทัล Azure AD **บริการ Power BI (Power BI)** อาจไม่ปรากฏขึ้น ถ้าไม่ ให้เลือก **+ เพิ่ม**แล้วเลือก **1 เลือกและ API** เลือก**บริการ Power BI** ในรายการ API และเลือก **เลือก**  ถ้า**บริการ Power BI (Power BI)** ไม่พร้อมใช้งานภายใน **+ เพิ่ม** ให้ลงทะเบียนสำหรับ Power BI ด้วยผู้ใช้อย่างน้อยหนึ่งราย

4. เลือกสิทธิ์ทั้งหมดใต้**สิทธิ์ที่ได้รับมอบ** เลือกทีละตัวเลือกเพื่อบันทึกการเลือก เลือก**บันทึก**เมื่อทำเสร็จแล้ว

    ![การอนุญาตของแอป 04](media/register-app/powerbi-embedded-azuread-app-permissions04.png)
5. ภายใน**สิทธิ์ที่ต้องใช้**เลือก**ให้สิทธิ์**

    การดำเนินการ**ให้สิทธิ์** จำเป็นต้องมี*บัญชีหลัก*เพื่อหลีกเลี่ยงการถามความยินยอมโดย Azure AD ถ้าบัญชีที่ดำเนินการนี้เป็นผู้ดูแลระบบส่วนกลาง คุณมอบสิทธิ์ให้แก่ผู้ใช้ทั้งหมดภายในองค์กรของคุณสำหรับแอปพลิเคชันนี้ ถ้าบัญชีที่ดำเนินการนี้เป็น*บัญชีผู้ใช้หลัก* และไม่ใช่ผู้ดูแลระบบส่วนกลาง คุณให้สิทธิ์*บัญชีหลัก*สำหรับแอปพลิเคชันนี้เท่านั้น

    ![การให้สิทธิ์ภายในกล่องโต้ตอบสิทธิ์ที่ต้องใช้](media/register-app/powerbi-embedded-azuread-app-grant-permissions.png)

### <a name="applying-permissions-programmatically"></a>กำลังใช้สิทธิ์ผ่านทางการเขียนโปรแกรม

1. คุณจำเป็นต้องรับบริการหลัก (service principal) ที่มีอยู่แล้วภายในผู้เช่าของคุณ สำหรับข้อมูลเกี่ยวกับวิธีการดังกล่าว ดู[รับ servicePrincipal](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/serviceprincipal_get)

    คุณสามารถเรียกใช้ API *รับ servicePrincipal* โดยไม่มี {id} และจะส่ง บริการหลักทั้งหมดภายในผู้เช่า กลับมาให้คุณ
2. ตรวจสอบบริการหลักกับ ID ไคลเอ็นต์แอปของคุณที่ **appId**คุณสมบัติ

3. สร้างแผนการบริการใหม่ ถ้ายังไม่มีในแอปของคุณ

    ```json
    Post https://graph.microsoft.com/beta/servicePrincipals
    Authorization: Bearer ey..qw
    Content-Type: application/json
    {
    "accountEnabled" : true,
    "appId" : "{App_Client_ID}",
    "displayName" : "{App_DisplayName}"
    }
    ```

4. ให้สิทธิ์แอปไปยัง Power BI API

   ถ้าคุณกำลังใช้ผู้เช่าที่มีอยู่และไม่สนใจมอบสิทธิ์ในนามของผู้ใช้ที่เป็นผู้เช่าทั้งหมด คุณสามารถให้สิทธิ์กับผู้ใช้ที่ระบุโดยการแทนที่ค่าของ **contentType** ให้เป็น**หลัก**

   ค่าสำหรับ **consentType** สามารถใส่ **AllPrincipals** หรือ **Principal** อย่างใดอย่างหนึ่ง

   * **AllPrincipals** สามารถใช้ได้โดยผู้ดูแลผู้เช่าเท่านั้น เพื่อให้สิทธิ์ในนามของผู้ใช้ทั้งหมดในผู้เช่าได้
   * **Principal** จะใช้เพื่อให้สิทธิ์ในนามของผู้ใช้ที่ระบุ ในกรณีนี้ ควรเพิ่มอีกคุณสมบัติหนึ่งลงในเนื้อความของการร้องขอ - *principalId={User_ObjectId}*

     *การให้สิทธิ์*จำเป็นสำหรับบัญชีหลัก เพื่อหลีกเลี่ยงการพร้อมท์ถามความยินยอมโดย Azure AD ซึ่งไม่สามารถทำได้ เมื่อลงชื่อเข้าใช้แบบไม่โต้ตอบ

     ```json
     Post https://graph.microsoft.com/beta/OAuth2PermissionGrants
     Authorization: Bearer ey..qw
     Content-Type: application/json
     {
     "clientId":"{Service_Plan_ID}",
     "consentType":"AllPrincipals",
     "resourceId":"c78a3685-1ce7-52cd-95f7-dc5aea8ec98e",
     "scope":"Dataset.ReadWrite.All Dashboard.Read.All Report.Read.All Group.Read Group.Read.All Content.Create Metadata.View_Any Dataset.Read.All Data.Alter_Any",
     "expiryTime":"2018-03-29T14:35:32.4943409+03:00",
     "startTime":"2017-03-29T14:35:32.4933413+03:00"
     }
     ```

    **resourceId** *c78a3685-1ce7-52cd-95f7-dc5aea8ec98e* ไม่ใช่สากล แต่จะขึ้นอยู่กับผู้เช่า ค่านี้คือ objectId ของแอปพลิเคชัน "บริการของ Power BI" ในผู้เช่า AAD

    ผู้ใช้สามารถได้รับค่านี้ได้อย่างรวดเร็วในพอร์ทัล Azure:
    1. https://portal.azure.com/#blade/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/AllApps
    2. ค้นหา "บริการของ Power BI" ใน SearchBox

5. ให้สิทธิ์แอปกับ Azure Active Directory (AAD)

   ค่าสำหรับ **consentType** สามารถใส่ **AllPrincipals** หรือ **Principal** อย่างใดอย่างหนึ่ง

   * **AllPrincipals** สามารถใช้ได้โดยผู้ดูแลผู้เช่าเท่านั้น เพื่อให้สิทธิ์ในนามของผู้ใช้ทั้งหมดในผู้เช่าได้
   * **Principal** จะใช้เพื่อให้สิทธิ์ในนามของผู้ใช้ที่ระบุ ในกรณีนี้ ควรเพิ่มอีกคุณสมบัติหนึ่งลงในเนื้อความของการร้องขอ - *principalId={User_ObjectId}*

   *การให้สิทธิ์*จำเป็นสำหรับบัญชีหลัก เพื่อหลีกเลี่ยงการพร้อมท์ถามความยินยอมโดย Azure AD ซึ่งไม่สามารถทำได้ เมื่อลงชื่อเข้าใช้แบบไม่โต้ตอบ

   ```json
   Post https://graph.microsoft.com/beta/OAuth2PermissionGrants
   Authorization: Bearer ey..qw
   Content-Type: application/json
   { 
   "clientId":"{Service_Plan_ID}",
   "consentType":"AllPrincipals",
   "resourceId":"61e57743-d5cf-41ba-bd1a-2b381390a3f1",
   "scope":"User.Read Directory.AccessAsUser.All",
   "expiryTime":"2018-03-29T14:35:32.4943409+03:00",
   "startTime":"2017-03-29T14:35:32.4933413+03:00"
   }
   ```

## <a name="next-steps"></a>ขั้นตอนถัดไป

ตอนนี้ คุณได้ลงทะเบียนแอปพลิเคชันของคุณภายใน Azure AD แล้ว คุณต้องรับรองความถูกต้องของผู้ใช้ภายในแอปพลิเคชันของคุณ ดูที่[รับรองความถูกต้องผู้ใช้ และรับโทเค็นการเข้าถึง Azure AD สำหรับแอป Power BI ของคุณ](get-azuread-access-token.md)เมื่อต้องการเรียนรู้เพิ่มเติม

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)

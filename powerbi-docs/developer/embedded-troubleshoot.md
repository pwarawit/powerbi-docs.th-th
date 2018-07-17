---
title: แก้ไขปัญหาแอปพลิเคชันแบบฝังตัว
description: บทความนี้อธิบายถึงปัญหาทั่วไปที่คุณอาจพบเมื่อฝังเนื้อหาจาก Power BI
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 07/03/2018
ms.author: maghan
ms.openlocfilehash: b3c9599ea3ce01094bb75d9b036fb25b1ca7109a
ms.sourcegitcommit: 627918a704da793a45fed00cc57feced4a760395
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/10/2018
ms.locfileid: "37926570"
---
# <a name="troubleshooting-your-embedded-application"></a>แก้ไขปัญหาแอปพลิเคชันแบบฝังตัว

บทความนี้อธิบายถึงปัญหาทั่วไปที่คุณอาจพบเมื่อฝังเนื้อหาจาก Power BI

## <a name="tools-for-troubleshooting"></a>เครื่องมือสำหรับการแก้ไขปัญหา

### <a name="fiddler-trace"></a>ติดตาม Fiddler

[Fiddler](http://www.telerik.com/fiddler) เป็นเครื่องมือฟรีจาก Telerik ที่ใช้ตรวจดูการรับส่งข้อมูลใน HTTP  คุณสามารถดูการกลับไปกลับมาได้ด้วย Power BI API จากเครื่องของลูกค้า ขั้นตอนนี้อาจแสดงข้อผิดพลาดและข้อมูลอื่น ๆ ที่เกี่ยวข้อง

![ติดตาม Fiddler](../includes/media/gateway-onprem-tshoot-tools-include/fiddler.png)

### <a name="f12-in-browser-for-front-end-debugging"></a>F12 ในเบราว์เซอร์สำหรับการแก้ไขปัญหาโปรแกรมเสริมหน้า (Front end)

F12 จะเปิดใช้หน้าต่างผู้พัฒนาภายในเบราว์เซอร์ของคุณ ซึ่งมีความสามารถในการดูการรับส่งข้อมูลเครือข่ายและข้อมูลอื่น ๆ

![แก้ไขปัญหาเบราว์เซอร์ F12](media/embedded-troubleshoot/browser-f12.png)

### <a name="extracting-error-details-from-power-bi-response"></a>แยกรายละเอียดข้อผิดพลาดจากคำตอบของ Power BI

ส่วนของรหัสนี้แสดงวิธีการแยกรายละเอียดข้อผิดพลาดจากข้อยกเว้น HTTP:

```
public static string GetExceptionText(this HttpOperationException exc)
{
    var errorText = string.Format("Request: {0}\r\nStatus: {1} ({2})\r\nResponse: {3}",
    exc.Request.Content, exc.Response.StatusCode, (int)exc.Response.StatusCode, exc.Response.Content);
    if (exc.Response.Headers.ContainsKey("RequestId"))
    {
        var requestId = exc.Response.Headers["RequestId"].FirstOrDefault();
        errorText += string.Format("\r\nRequestId: {0}", requestId);
    }

    return errorText;
}
```
เราแนะนำให้บันทึกรหัสคำขอดังกล่าว (และรายละเอียดข้อผิดพลาดสำหรับการแก้ไขปัญหา)
โปรดระบุรหัสคำขอเมื่อติดต่อฝ่ายสนับสนุนของ Microsoft

## <a name="app-registration"></a>การลงทะเบียนแอปฯ

**ล้มเหลวในการลงทะเบียนแอปฯ**

ข้อความข้อผิดพลาดภายในพอร์ทัล Azure หรือหน้าการลงทะเบียนแอปฯ Power BI จะบอกถึงสิทธิ์ที่ไม่เพียงพอ เพื่อลงทะเบียนแอปพลิเคชัน คุณต้องเป็นผู้ดูแลระบบในผู้เช่า Azure AD หรือต้องเปิดใช้งานการลงทะเบียนแอปพลิเคชันสำหรับผู้ใช้ที่ไม่ใช่ผู้ดูแลระบบ

**บริการ Power BI ไม่ปรากฏในพอร์ทัล Azure เมื่อลงทะเบียนแอปฯใหม่**

ต้องมีผู้ใช้อย่างน้อยหนึ่งรายลงทะเบียนสำหรับ Power BI ถ้าคุณไม่เห็น**บริการ Power BI**แสดงอยู่ภายในรายการ API แสดงว่าไม่มีผู้ใช้ที่ลงทะเบียนสำหรับ Power BI

## <a name="rest-api"></a>API ที่เหลือ

**API เรียกให้ส่งกลับ 401**

อาจต้องมีการจับภาพ Fiddler เพื่อการตรวจสอบเพิ่มเติม ขอบเขตการอนุญาตสิทธิ์ที่จำเป็นอาจสูญหายสำหรับแอปพลิเคชันที่ลงทะเบียนไว้ภายใน Azure AD ตรวจสอบให้แน่ใจว่าขอบเขตที่จำเป็นต้องมีปรากฏอยู่ภายในการลงทะเบียนแอปฯสำหรับ Azure AD ภายในพอร์ทัล Azure

**API เรียกให้ส่งกลับ 403**

อาจต้องมีการจับภาพ Fiddler เพื่อการตรวจสอบเพิ่มเติม อาจมีหลายสาเหตุสำหรับข้อผิดพลาด 403

* ผู้ใช้มีจำนวนโทเค็นแบบฝังเกินจำนวนที่สามารถสร้างขึ้นได้ในขีดความสามารถที่ใช้ร่วมกัน คุณจำเป็นต้องซื้อขีดความสามารถ Azure เพื่อสร้างโทเค็นแบบฝัง และกำหนดพื้นที่ทำงานให้กับขีดความสามารถนั้น ดู[ขีดความสามารถในการสร้าง Power BI แบบฝังในพอร์ทัล Azure](https://docs.microsoft.com/azure/power-bi-embedded/create-capacity)
* โทเค็นรับรองความถูกต้องของ Azure AD หมดอายุแล้ว
* ผู้ใช้ที่ได้รับการรับรองความถูกต้องไม่เป็นสมาชิกของกลุ่ม (พื้นที่ทำงานของแอปฯ)
* ผู้ใช้ที่ได้รับการรับรองความถูกต้องไม่เป็นผู้ดูแลระบบของกลุ่ม (พื้นที่ทำงานของแอปฯ)
* หัวข้อการรับรองความถูกต้องอาจไม่อยู่ในรายการอย่างถูกต้อง ตรวจสอบให้แน่ใจว่าไม่มีการพิมพ์ผิด

ส่วนหลังของแอปพลิเคชันอาจจำเป็นต้องรีเฟรชโทเค็นการรับรองความถูกต้องก่อนที่จะเรียก GenerateToken

```
    GET https://wabi-us-north-central-redirect.analysis.windows.net/metadata/cluster HTTP/1.1
    Host: wabi-us-north-central-redirect.analysis.windows.net
    ...
    Authorization: Bearer eyJ0eXAiOi...
    ...
 
    HTTP/1.1 403 Forbidden
    ...
     
    {"error":{"code":"TokenExpired","message":"Access token has expired, resubmit with a new access token"}}
```

## <a name="authentication"></a>การรับรองความถูกต้อง

### <a name="authentication-failed-with-aadsts70002-or-aadsts50053"></a>การรับรองความถูกต้องล้มเหลวเนื่องจาก AADSTS70002 หรือ AADSTS50053

**(AADSTS70002: ข้อมูลประจำตัวผิดพลาด AADSTS50053: คุณได้พยายามลงชื่อเข้าใช้หลายครั้งเกินไป ด้วย ID ผู้ใช้หรือรหัสผ่านที่ไม่ถูกต้อง)**

ถ้าคุณกำลังใช้ Power BI Embedded และการรับรองความถูกต้องโดยตรงของ Azure AD และคุณได้รับข้อความที่เข้าสู่ระบบเช่น***ข้อผิดพลาด: unauthorized_client, error_description:AADSTS70002: ข้อมูลประจำตัวผิดพลาด AADSTS50053: คุณได้พยายามลงชื่อเข้าใช้หลายครั้งเกินไป ด้วย ID ผู้ใช้หรือรหัสผ่านที่ไม่ถูกต้อง***นั่นเป็นเพราะว่าการรับรองความถูกต้องโดยตรงได้ถูกปิดใช้งานในวันที่ 6/14/2018

เราขอแนะนำให้ใช้[การเข้าถึงตามเงื่อนไขของ Azure AD](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/07/azure-ad-conditional-access-support-for-blocking-legacy-auth-is-in-public-preview/)เพื่อบล็อกการรับรองความถูกต้องแบบดั้งเดิมหรือใช้[การรับรองความถูกต้องแบบพาส-ทรูของ Azure AD Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)

อย่างไรก็ตาม นั่นคือวิธีการเปลี่ยนไปใช้ [นโยบาย Azure AD ](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/configure-authentication-for-federated-users-portal#enable-direct-authentication-for-legacy-applications)ที่สามารถกำหนดว่าเป็นองค์กรหรือ[วัตถุบริการ](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-application-objects#service-principal-object)ได้

**_เราขอแนะนำให้คุณเปิดใช้งานนี้สำหรับแต่ละแอป เท่านั้น และเมื่อจำเป็นสำหรับการแก้ไขปัญหาชั่วคราวเท่านั้น_**

เมื่อต้องสร้างนโยบายนี้ คุณจำเป็นต้องเป็น**ผู้ดูแลระบบส่วนกลาง**สำหรับไดเรกทอรีที่คุณกำลังสร้างนโยบายและกำหนดสิ่งต่างๆ นี่คือสคริปต์ตัวอย่างสำหรับการสร้างนโยบาย และกำหนดนโยบายให้กับ SP สำหรับแอปพลิเคชันนี้:

1. ติดตั้ง[การแสดงโมดูล Powershell ของ Azure AD](https://docs.microsoft.com/en-us/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)

2. เรียกใช้คำสั่ง powershell แบบบรรทัดต่อบรรทัดต่อไปนี้(ทำให้แน่ใจว่า ตัวแปร $sp ไม่มีแอปพลิเคชันมากกว่า 1)

```powershell
Connect-AzureAD
```

```powershell
$sp = Get-AzureADServicePrincipal -SearchString "Name_Of_Application"
```

```powershell
$policy = New-AzureADPolicy -Definition @("{`"HomeRealmDiscoveryPolicy`":{`"AllowCloudPasswordValidation`":true}}") -DisplayName EnableDirectAuth -Type HomeRealmDiscoveryPolicy -IsOrganizationDefault $false
```

```powershell
Add-AzureADServicePrincipalPolicy -Id $sp.ObjectId -RefObjectId $policy.Id 
```

หลังจากกำหนดนโยบาย โปรดรอประมาณ 15-20 วินาทีสำหรับการเผยแพร่ก่อนการทดสอบ

**การสร้างโทเค็นล้มเหลวเมื่อให้ข้อมูลประจำตัวที่ใช้ได้**

GenerateToken สามารถล้มเหลวได้เมื่อใช้งานข้อมูลประจำตัวที่ให้มาด้วยเหตุผลสองสามประการ

* ชุดข้อมูลไม่สนับสนุนข้อมูลประจำตัวที่ใช้ได้
* ไม่ได้ระบุชื่อผู้ใช้
* ไม่ได้ระบุบทบาท
* ไม่ได้ระบุบรหัสชุดข้อมูล
* ผู้ใช้ไม่มีสิทธิ์ที่ถูกต้อง

เพื่่อตรวจสอบว่าเป็นสาเหตุใด ลองขั้นตอนต่อไปนี้

* ดำเนินการ[รับชุดข้อมูล](https://docs.microsoft.com/rest/api/power-bi/datasets) คุณสมบัติ IsEffectiveIdentityRequired เป็นจริงหรือไม่?
* ชื่อผู้ใช้เป็นข้อบังคับสำหรับ EffectiveIdentity ใด ๆ
* ถ้า IsEffectiveIdentityRolesRequired เป็นจริง ดังนั้นต้องมีบทบาท
* รหัสชุดข้อมูลเป็นข้อบังคับสำหรับ EffectiveIdentity ใด ๆ
* สำหรับ Analysis Services ผู้ใช้หลักจะต้องเป็นผู้ดูแลระบบเกตเวย์

### <a name="aadsts90094-the-grant-requires-admin-permission"></a>AADSTS90094: การอนุมัติต้องมีสิทธิ์ระดับผู้ดูแลระบบ

**_ปัญหา:_**</br>
เมื่อผู้ใช้ไม่ใช่ผู้ดูแลระบบพยายามลงชื่อเข้าใช้แอปพลิเคชันเพื่อให้ได้รับอนุมัติและให้อนุมัติได้ เธอจะได้รับข้อผิดพลาดต่อไปนี้:
* ConsentTest ต้องการสิทธิ์ในการเข้าถึงทรัพยากรในองค์กรของคุณที่ผู้ดูแลระบบเท่านั้นสามารถมอบหมายได้ โปรดขอให้ผู้ดูแลระบบให้สิทธิ์แอปนี้ก่อนที่คุณสามารถใช้งาน
* AADSTS90094: การอนุมัติต้องได้รับสิทธิ์จากผู้ดูแลระบบ

    ![การทดสอบความยินยอม](media/embedded-troubleshoot/consent-test-01.png)

ผู้ใช้ที่เป็นผู้ดูแลระบบสามารถลงชื่อเข้าใช้ และให้สิทธิ์ได้

**_สาเหตุ:_**</br>
การอนุมัติของผู้ใช้ถูกปิดใช้งานสำหรับผู้เช่า

**_แก้ไขปัญหาได้ดังนี้้:_**

*เปิดใช้งานการอนุมัติของผู้ใข้สำหรับผู้เช่าทั้งหมด (ผู้ใช้ทั้งหมด แอปพลิเคชั้นทั้งหมด)*
1. ในพอร์ทัล Azure ไปที่ "Azure Active Directory" = > "ผู้ใช้และกลุ่ม" = > "การตั้งค่าผู้ใช้"
2. เปิดใช้งานการตั้งค่า “ผู้ใช้สามารถยินยอมให้แอปเข้าถึงข้อมูลของบริษัทในนามของพวกเขา” แล้วเลือก บันทึก การเปลี่ยนแปลง

    ![การแก้ไขการทดสอบความยินยอม](media/embedded-troubleshoot/consent-test-02.png)

*ให้สิทธิ์ โดยผู้ดูแลระบบ*จะเป็นการให้สิทธิ์แอปพลิเคชันโดยผู้ดูแลระบบบ - สำหรับผู้เช่าทั้งหมด หรือ สำหรับผู้ใช้ที่ระบุ

## <a name="data-sources"></a>แหล่งข้อมูล

**ISV ต้องการข้อมูลประจำตัวอื่นสำหรับแหล่งข้อมูลเดียวกัน**

แหล่งข้อมูลสามารถมีหนึ่งชุดข้อมูลประจำตัวสำหรับผู้ใช้หลักหนึ่งราย ถ้าคุณจำเป็นต้องใช้ข้อมูลประจำตัวอื่น ให้สร้างผู้ใช้หลักเพิ่มเติม จากนั้นกำหนดข้อมูลประจำตัวอื่นในบริบทผู้ใช้หลักแต่ละคน จากนั้นฝังโดยใช้โทเค็น Azure AD ของผู้ใช้นั้น

## <a name="content-rendering"></a>แสดงเนื้อหา

**การแสดงหรือการใช้เนื้อหาแบบฝังตัวล้มเหลวหรือหมดเวลา**

ตรวจสอบให้แน่ใจว่าโทเค็นฝังตัวไม่หมดอายุ ตรวจสอบให้แน่ใจว่าคุณกำลังตรวจสอบวันหมดอายุของโทเค็นแบบฝังตัวและรีเฟรชโทเค็น สำหรับข้อมูลเพิ่มเติม ดู[รีเฟรชโทเค็นโดยใช้ JavaScript SDK](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Refresh-token-using-JavaScript-SDK-example)

**รายงานหรือแดชบอร์ดไม่โหลด**

ถ้าผู้ใช้ไม่สามารถดูรายงานหรือแดชบอร์ดได้ ตรวจสอบให้แน่ใจว่ารายงานหรือแดชบอร์ดโหลดอย่างถูกต้องภายใน powerbi.com รายงานหรือแดชบอร์ดจะไม่ทำงานภายในแอปพลิเคชันของคุณหากไม่โหลดภายใน powerbi.com

**รายงานหรือแดชบอร์ดทำงานช้า**

เปิดไฟล์จาก Power BI Desktop หรือภายใน powerbi.com และตรวจสอบว่าประสิทธิภาพการทำงานยอมรับได้สำหรับการไม่รวมปัญหากับแอปพลิเคชันของคุณหรือ API ที่ฝัง

## <a name="onboarding-experience-tool-for-embedding"></a>ประสบการณ์การเตรียมความพร้อมสำหรับการฝัง

คุณสามารถเข้าถึง[เครื่องมือประสบการณ์การเตรียมความพร้อม](https://aka.ms/embedsetup) เพื่อดาวน์โหลดแอปพลิเคชันตัวอย่างได้อย่างรวดเร็ว จากนั้น คุณสามารถเปรียบเทียบแอปพลิเคชันของคุณกับตัวอย่าง

### <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

ตรวจสอบว่า คุณผ่านข้อกำหนดเบื้องต้นทั้งหมด ก่อนที่จะใช้เครื่องมือประสบการณ์การเตรียมความพร้อม คุณต้องมีบัญชี **Power BI Pro** และการสมัครใช้งาน **Microsoft Azure**

* ถ้าคุณยังไม่ได้ลงทะเบียนสำหรับ **Power BI Pro** [ลงทะเบียนทดลองใช้ฟรี](https://powerbi.microsoft.com/en-us/pricing/)ก่อนที่คุณจะเริ่ม
* ถ้าคุณยังไม่มีการสมัครใช้งาน Azure สร้าง[บัญชีฟรี](https://azure.microsoft.com/free/?WT.mc_id=A261C142F)ก่อนที่คุณจะเริ่ม
* คุณจำเป็นต้องตั้งค่า[ผู้เช่า Azure Active Directory](create-an-azure-active-directory-tenant.md) ของคุณเอง
* คุณต้องติดตั้ง [Visual Studio](https://www.visualstudio.com/) (เวอร์ชัน 2013 หรือใหม่กว่า)

### <a name="common-issues"></a>ปัญหาที่พบบ่อย

บางปัญหาที่พบบ่อยที่คุณอาจเจอเมื่อทำการทดลองด้วย เครื่องมือประสบการณ์การเตรียมความพร้อม คือ:

#### <a name="using-the-embed-for-your-customers-sample-application"></a>การใช้แอปพลิเคชันตัวอย่าง การฝังตัวสำหรับของลูกค้าคุณ

ถ้าคุณกำลังทำงานกับประสบการณ์**ฝังตัวสำหรับลูกค้าของคุณ** บันทึกและคลายการบีบอัดไฟล์ *PowerBI-Developer-Samples.zip* จากนั้น เปิดโฟลเดอร์ *PowerBI-Developer-Samples-master\App Owns Data* และเรียกใช้ไฟล์ *PowerBIEmbedded_AppOwnsData.sln*

เมื่อเลือก**ให้สิทธิ์** (ขั้นตอนการให้สิทธิ์) คุณได้รับข้อผิดพลาดต่อไปนี้:

    AADSTS70001: Application with identifier <client ID> was not found in the directory <directory ID>

ทางแก้คือ ปิดหน้าต่างที่ผุดขึ้น รอสักครู่ แล้วลองอีกครั้ง คุณอาจต้องทำซ้ำหลายครั้ง ระยะเวลาจากการเสร็จสิ้นกระบวนการลงทะเบียนแอปพลิเคชัน จนถึงเวลาที่พร้อมใช้งานสำหรับ API ภายนอก คือต้นเหตุของปัญหา

ข้อผิดพลาดต่อไปนี้ปรากฏขึ้นเมื่อเรียกใช้แอปตัวอย่าง:

    Password is empty. Please fill password of Power BI username in web.config.

ข้อผิดพลาดนี้เกิดขึ้นเนื่องจากค่ารหัสผ่านผู้ใช้ของคุณ ยังไม่ได้ใส่เข้าไปในแอปพลิเคชันตัวอย่าง เปิดแฟ้ม Web.config ในโซลูชัน และกรอกเขตข้อมูล pbiPassword ด้วยรหัสผ่านผู้ใช้ของคุณ

#### <a name="using-the-embed-for-your-organization-sample-application"></a>การใช้แอปพลิเคชันตัวอย่าง การฝังตัวสำหรับองค์กรของคุณ

ถ้าคุณกำลังทำงานกับประสบการณ์**ฝังตัวสำหรับองค์กรของคุณ** บันทึกและคลายการบีบอัดไฟล์ *PowerBI-Developer-Samples.zip* จากนั้น เปิดโฟลเดอร์ *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app* และเรียกใช้ไฟล์ *pbi-saas-embed-report.sln*

เมื่อคุณเรียกใช้แอปตัวอย่าง**ฝังตัวสำหรับองค์กรของคุณ** คุณได้รับข้อผิดพลาดต่อไปนี้:

    AADSTS50011: The reply URL specified in the request does not match the reply URLs configured for the application: <client ID>

ทั้งนี้เนื่องจาก URL เปลี่ยนเส้นทางที่ระบุสำหรับเว็บเซิร์ฟเวอร์แอปพลิเคชัน แตกต่างจาก URL ของตัวอย่าง ถ้าคุณต้องการลงทะเบียนแอปพลิเคชันตัวอย่าง ใช้ `http://localhost:13526/` เป็น URL เปลี่ยนเส้นทาง

ถ้าคุณต้องการแก้ไขแอปพลิเคชันที่ลงทะเบียนแล้ว ให้เรียนรู้วิธีการแก้ไข[แอปพลิเคชันที่ลงทะเบียน AAD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#updating-an-application) เพื่อที่แอปพลิเคชันจะสามารถให้การเข้าถึง API ของเว็บ

ถ้าคุณต้องการแก้ไขโปรไฟล์หรือข้อมูลผู้ใช้ Power BI ของคุณ เรียนรู้วิธีการแก้ไข[ข้อมูล Power BI](https://docs.microsoft.com/en-us/power-bi/service-basic-concepts) ของคุณ

สำหรับข้อมูลเพิ่มเติม โปรดดู [คำถามที่ถามบ่อยของ Power BI Embedded](embedded-faq.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)
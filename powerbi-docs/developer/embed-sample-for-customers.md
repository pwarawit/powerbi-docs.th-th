---
title: การวิเคราะห์ที่ฝังตัวที่ใช้ในการฝังเนื้อหา Power BI ลงในแอปพลิเคชันสำหรับลูกค้าของคุณ
description: เรียนรู้วิธีรวมหรือฝังรายงาน, แดชบอร์ด หรือไทล์ เข้าไปในแอปพลิเคชั่นโดยการใช้ Power BI APIs สำหรับการวิเคราะห์ที่ฝังตัวสำหรับลูกค้าของคุณ เรียนรู้วิธีการรวม Power BI เข้ากันกับแอปพลิเคชันของคุณโดยใช้ซอฟต์แวร์การวิเคราะห์แบบฝังตัว, เครื่องมือการวิเคราะห์แบบฝังตัวหรือเครื่องมือข่าวกรองธุรกิจแบบฝังตัว
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.topic: tutorial
ms.service: powerbi
ms.subservice: powerbi-developer
ms.custom: seodec18
ms.date: 12/10/2018
ms.openlocfilehash: c662fea5bb343d835cffec126ffe6eb071be2218
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54296650"
---
# <a name="tutorial-embed-a-power-bi-report-dashboard-or-tile-into-an-application-for-your-customers"></a>บทช่วยสอน: ฝังรายงาน Power BI แดชบอร์ด หรือไทล์ลงในแอปพลิเคชันสำหรับลูกค้าของคุณ

ด้วย **Power BI Embedded ใน Azure** คุณสามารถฝังรายงาน, แดชบอร์ด หรือไทล์ลงในการใช้แอปพลิเคชันโดยใช้แอปเป็นเจ้าของข้อมูลได้ **แอปเป็นเจ้าของข้อมูล** เกี่ยวกับแอปพลิเคชันที่ใช้ Power BI เป็นแพลตฟอร์มการวิเคราะห์แบบฝังตัว ในฐานะเป็น**นักพัฒนาของผู้จำหน่ายซอฟท์แวร์อิสระ (ISV)** คุณสามารถสร้างเนื้อหา Power BI ที่แสดงรายงาน, แดชบอร์ด หรือไทล์ในแอปพลิเคชันที่รวมงานทั้งหมดไว้ด้วยกันและที่โต้ตอบได้ โดยผู้ใช้ไม่ต้องมีสิทธิ์การใช้งาน Power BI บทช่วยสอนนี้สาธิตวิธีการรวมรายงานลงในแอปพลิเคชัน โดยใช้ Power BI SDK .NET กับ Power BI JavaScript API เมื่อใช้ **Power BI Embedded ใน Azure** สำหรับลูกค้าของคุณ

ในบทช่วยสอนนี้ คุณจะเรียนรู้วิธีการ:
> [!div class="checklist"]
> * ลงทะเบียนแอปพลิเคชันใน Azure
> * ฝังรายงาน Power BI ลงในแอปพลิเคชัน

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

เมื่อต้องการเริ่มต้นใช้งาน คุณต้องมีบัญชี **Power BI Pro** (บัญชีนี้เป็น**บัญชีหลัก**ของคุณ) และการสมัครใช้งาน **Microsoft Azure**

* ถ้าคุณยังไม่ได้ลงทะเบียนสำหรับ **Power BI Pro** [ลงทะเบียนทดลองใช้ฟรี](https://powerbi.microsoft.com/en-us/pricing/)ก่อนที่คุณจะเริ่ม
* ถ้าคุณยังไม่มีการสมัครใช้งาน Azure สร้าง[บัญชีฟรี](https://azure.microsoft.com/free/?WT.mc_id=A261C142F)ก่อนที่คุณจะเริ่ม
* คุณจำเป็นต้องตั้งค่า[ผู้เช่า Azure Active Directory](create-an-azure-active-directory-tenant.md) ของคุณเอง
* คุณต้องติดตั้ง [Visual Studio](https://www.visualstudio.com/) (เวอร์ชัน 2013 หรือใหม่กว่า)

## <a name="set-up-your-embedded-analytics-development-environment"></a>ตั้งค่าสภาพแวดล้อมการพัฒนาการวิเคราะห์แบบฝังตัวของคุณ

ก่อนที่คุณจะเริ่มฝังรายการ, แดชบอร์ด หรือไทล์ลงในแอปพลิเคชันของคุณ คุณจำเป็นต้องตรวจสอบให้แน่ใจว่าสภาพแวดล้อมเอื้ออำนวยต่อการฝังด้วย Power BI

คุณสามารถเข้าถึง [เครื่องมือตั้งค่าการฝังตัว](https://aka.ms/embedsetup/AppOwnsData) เพื่อให้คุณสามารถเริ่มต้นใช้งาน และดาวน์โหลดแอปพลิเคชันตัวอย่างที่ช่วยแนะนำคุณไปตามขั้นตอนการสร้างสภาพแวดล้อม และการฝังรายงานได้

แต่ถ้าคุณเลือกที่จะตั้งค่าสภาพแวดล้อมด้วยตนเอง คุณสามารถดำเนินต่อตามด้านล่าง

### <a name="register-an-application-in-azure-active-directory-azure-ad"></a>ลงทะเบียนแอปพลิเคชันใน Azure Active Directory (Azure AD)

คุณลงทะเบียนแอปพลิเคชันของคุณกับ Azure Active Directory เพื่ออนุญาตให้แอปพลิเคชันของคุณเข้าถึง Power BI REST API การลงทะเบียนแอปพลิเคชันจะทำให้คุณสร้างอัตลักษณ์แอปพลิเคชันของคุณและระบุสิทธิ์ไปยังทรัพยากร Power BI REST

1. ยอมรับ[เงื่อนไขของ Microsoft Power BI API](https://powerbi.microsoft.com/api-terms)

2. ลงชื่อเข้าใช้[พอร์ทัล Azure](https://portal.azure.com)

    ![พอร์ทัล Main ของ Azure](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

3. ในบานหน้าต่างนำทางซ้ายมือ เลือก**บริการทั้งหมด** จากนั้นเลือก**การลงทะเบียนแอป** แล้วเลือก **ลงทะเบียนแอปพลิเคชันใหม่**

    ![ค้นหาการลงทะเบียนแอป](media/embed-sample-for-customers/embed-sample-for-customers-003.png)</br>
    ![ลงทะเบียนแอปใหม่](media/embed-sample-for-customers/embed-sample-for-customers-004.png)

4. ทำตามพร้อมท์และสร้างแอปพลิเคชัน์ใหม่ สำหรับแอปเป็นเจ้าของข้อมูล คุณต้องใช้ **พื้นถิ่น** สำหรับประเภทแอปพลิเคชัน คุณยังต้องให้ **URI ที่เปลี่ยนเส้นทาง** ซึ่ง **Azure AD** ใช้เพื่อส่งกลับผลลัพธ์โทเค็น ใส่ค่าที่เฉพาะสำหรับแอปพลิเคชันของคุณ (ตัวอย่างเช่น: `http://localhost:13526/Redirect`)

    ![สร้างแอป](media/embed-sample-for-customers/embed-sample-for-customers-005.png)

### <a name="apply-permissions-to-your-application-within-azure-active-directory"></a>นำสิทธิ์ไปใช้กับแอปพลิเคชันของคุณภายใน Azure Active Directory

เปิดใช้งานสิทธิ์เพิ่มเติมสำหรับแอปพลิเคชันรวมไปถึงสิ่งที่มีในหน้าการลงทะเบียนแอป ลงชื่อเข้าใช้ด้วยบัญชี *หลัก* ที่คุณกำลังใช้เพื่อการฝัง บัญชีหลักจะต้องเป็นบัญชีผู้ดูแลทั่วไป

### <a name="use-the-azure-active-directory-portal"></a>ใช้พอร์ทัล Azure Active Directory

1. เรียกดู [การลงทะเบียนแอป](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade) ภายในพอร์ทัล Azure และเลือกแอปที่คุณกำลังใช้เพื่อการฝังตัว

    ![การเลือกแอป](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

2. เลือก**การตั้งค่า** จากนั้นภายใต้**การเข้าถึง API** เลือก**สิทธิ์ที่จำเป็น**

    ![สิทธิ์ที่จำเป็น](media/embed-sample-for-customers/embed-sample-for-customers-008.png)

3. เลือก **Azure Active Directory Windows** จากนั้นตรวจสอบว่าได้เลือก**การเข้าถึงไดเรกทอรีในฐานะผู้ใช้ที่เข้าสู่ระบบ** เลือก**บันทึก**

    ![สิทธิ์ของ Windows Azure AD](media/embed-sample-for-customers/embed-sample-for-customers-011.png)

4. เลือก**เพิ่ม**

    ![เพิ่มสิทธิ์](media/embed-sample-for-customers/embed-sample-for-customers-012.png)

5. เลือก**เลือก API**

    ![เพิ่มการเข้าถึง API](media/embed-sample-for-customers/embed-sample-for-customers-013.png)

6. เลือก**บริการของ Power BI** แล้วเลือก**เลือก**

    ![เลือกบริการของ PBI](media/embed-sample-for-customers/embed-sample-for-customers-014.png)

7. เลือกสิทธิ์ทั้งหมดใต้**สิทธิ์ที่ได้รับมอบ** เลือก**บันทึก**เมื่อทำเสร็จแล้ว

    ![เลือกสิทธิ์ที่ได้รับมอบสิทธิ์](media/embed-sample-for-customers/embed-sample-for-customers-015.png)

8. ภายใน**สิทธิ์ที่ต้องใช้**เลือก**ให้สิทธิ์**

    เมื่อดำเนินการ**การให้สิทธิ์** คุณจำเป็นต้องมี*บัญชีหลัก*เพื่อมิต้องให้ Azure AD พร้อมท์ให้คุณทำการยินยอม ถ้าบัญชีที่ดำเนินการนี้เป็นผู้ดูแลระบบส่วนกลาง คุณจะต้องมอบสิทธิ์ให้แก่ผู้ใช้ทั้งหมดภายในองค์กรของคุณสำหรับแอปพลิเคชันนี้ ถ้าบัญชีที่ดำเนินการนี้เป็น*บัญชีผู้ใช้หลัก* และไม่ใช่ผู้ดูแลระบบส่วนกลาง คุณจะให้สิทธิ์แก่*บัญชีหลัก*สำหรับแอปพลิเคชันนี้ได้เท่านั้น

    ![การให้สิทธิ์ภายในกล่องโต้ตอบสิทธิ์ที่ต้องใช้](media/embed-sample-for-customers/embed-sample-for-customers-016.png)

## <a name="set-up-your-power-bi-environment"></a>ตั้งค่าสภาพแวดล้อม Power BI ของคุณ

### <a name="create-an-app-workspace"></a>สร้างพื้นที่ทำงานสำหรับแอป

หากคุณกำลังฝังรายงาน, แดชบอร์ด หรือไทล์สำหรับลูกค้า คุณต้องวางเนื้อหาลงในพื้นที่ทำงานแอป บัญชี*หลัก*จะต้องเป็นผู้ดูแลระบบของพื้นที่ทำงานแอป

1. เริ่มต้นโดยการสร้างพื้นที่ทำงาน เลือก **พื้นที่ทำงาน** > **สร้างพื้นที่ทำงานแอป** ในการสร้างพื้นที่ทำงาน วางเนื้อหาที่แอปพลิเคชันของคุณต้องเข้าถึง

    ![สร้างพื้นที่ทำงาน](media/embed-sample-for-customers/embed-sample-for-customers-020.png)

2. ตั้งชื่อพื้นที่ทำงาน ถ้าชื่อ **ID พื้นที่ทำงาน**ที่ตรงกันไม่สามารถใช้ได้ แก้ไขให้ ID ใหม่มีค่าไม่ซ้ำกัน

    ![ตั้งชื่อพื้นที่ทำงาน](media/embed-sample-for-customers/embed-sample-for-customers-021.png)

3. คุณมีสองสามตัวเลือกที่จะตั้งค่า ถ้าคุณเลือก**สาธารณะ** ทุกคนในองค์กรคุณสามารถดูสิ่งที่อยู่ในพื้นที่ทำงานได้ หากคุณเลือก **ส่วนตัว** หมายถึงมีเพียงสมาชิกเท่าของพื้นที่ทำงานเท่านั้นที่สามารถเห็นเนื้อหาได้

    ![ส่วนตัว/สาธารณะ](media/embed-sample-for-customers/embed-sample-for-customers-022.png)

    คุณไม่สามารถเปลี่ยนการตั้งค่า สาธารณะ/ส่วนตัว ได้หลังจากคุณสร้างกลุ่มแล้ว

4. คุณยังสามารถเลือกว่าสมาชิกสามารถเข้าถึงแบบ**แก้ไข**ได้หรือ**ดูเท่านั้น**

    ![การเพิ่มสมาชิก](media/embed-sample-for-customers/embed-sample-for-customers-023.png)

5. ใส่ที่อยู่อีเมลของบุคคลที่คุณต้องการให้เข้าถึงพื้นที่ทำงาน และเลือก**เพิ่ม** คุณไม่สามารถเพิ่มนามแฝงของกลุ่ม เพิ่มได้แค่บุคคลอย่างเดียว

6. ตัดสินใจว่า แต่ละคนเป็นสมาชิกหรือผู้ดูแลระบบ ผู้ดูแลระบบสามารถแก้ไขพื้นที่ทำงาน รวมถึงการเพิ่มสมาชิกคนอื่น ๆ สมาชิกสามารถแก้ไขเนื้อหาในพื้นที่ทำงาน นอกจากว่าพวกเขามีสิทธิ์เข้าถึงแบบดูเท่านั้น ทั้งผู้ดูแลระบบและสมาชิกสามารถเผยแพร่แอป

    ในตอนนี้ คุณสามารถดูพื้นที่ทำงานใหม่แล้ว Power BI จะสร้างพื้นที่ทำงาน และเปิดพื้นที่ทำงานนั้น ซึ่งจะปรากฏขึ้นในรายการของพื้นที่ทำงานที่คุณเป็นสมาชิก เนื่องจากคุณเป็นผู้ดูแล คุณสามารถเลือกจุดไข่ปลา (...) เพื่อกลับมา และทำการเปลี่ยนแปลง เพิ่มสมาชิกใหม่ หรือเปลี่ยนแปลงสิทธิ์ของพวกเขาได้

    ![พื้นที่ทำงานใหม่](media/embed-sample-for-customers/embed-sample-for-customers-025.png)

### <a name="create-and-publish-your-reports"></a>สร้าง และเผยแพร่รายงานของคุณ

คุณสามารถสร้างรายงานและชุดข้อมูลของคุณโดยใช้ Power BI Desktop แล้วจึงเผยแพร่รายงานเหล่านั้นไปยังพื้นที่ทำงานของแอป ผู้ใช้ปลายทางที่เผยแพร่รายงาน จำเป็นต้องมีสิทธิ์การใช้งาน Power BI Pro เพื่อเผยแพร่ไปยังพื้นที่ทำงานของแอป

1. ดาวน์โหลดตัวอย่าง[การสาธิตบล็อก](https://github.com/Microsoft/powerbi-desktop-samples)จาก GitHub

    ![ตัวอย่างรายงาน](media/embed-sample-for-customers/embed-sample-for-customers-026-1.png)

2. เปิดรายงาน PBIX ตัวอย่างใน **Power BI Desktop**

   ![รายงาน PBI บนเดสก์ท็อป](media/embed-sample-for-customers/embed-sample-for-customers-027.png)

3. เผยแพร่ไปยัง**พื้นที่ทำงานแอป**

   ![เผยแพร่รายงานเดสก์ท็อป](media/embed-sample-for-customers/embed-sample-for-customers-028.png)

    ในตอนนี้ คุณสามารถดูรายงานในบริการของ Power BI แบบออนไลน์

   ![มุมมองรายงาน PBI เดสก์ท็อปพร้อมให้บริการ](media/embed-sample-for-customers/embed-sample-for-customers-029.png)

## <a name="embed-your-content-using-the-sample-application"></a>ฝังเนื้อหาของคุณโดยใช้แอปพลิเคชันตัวอย่าง

ทำตามขั้นตอนเหล่านี้เพื่อเริ่มการฝังเนื้อหาของคุณโดยใช้แอปพลิเคชันตัวอย่าง

1. ดาวน์โหลด[ตัวอย่างแอปเป็นเจ้าของข้อมูล](https://github.com/Microsoft/PowerBI-Developer-Samples)จาก GitHub เพื่อเริ่มต้น

    ![ตัวอย่างแอปพลิเคชัน แอปเป็นเจ้าของข้อมูล](media/embed-sample-for-customers/embed-sample-for-customers-026.png)

2. เปิดแฟ้ม Web.config ในแอปพลิเคชันตัวอย่าง คุณต้องป้อนทั้ง 5 ช่อง เพื่อเรียกใช้แอปพลิเคชันให้สำเร็จ **applicationId**, **workspaceId**, **reportId**, **pbiUsername** และ **pbiPassword**

    ![แฟ้ม Web.config](media/embed-sample-for-customers/embed-sample-for-customers-030.png)

    ป้อนข้อมูล **applicationId** ด้วย **ID แอปพลิเคชัน** จาก **Azure** แอปพลิเชันจะใช้ **applicationId** เพื่อระบุตัวเองไปยังผู้ใช้จากที่คุณกำลังขอสิทธิ์ สำหรับวิธีรับ **applicationId** ให้ทำตามขั้นตอนต่อไปนี้:

    ลงชื่อเข้าใช้[พอร์ทัล Azure](https://portal.azure.com)

    ![พอร์ทัล Main ของ Azure](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

    ในบานหน้าต่างนำทางซ้ายมือ เลือก **บริการทั้งหมด** และเลือก **การลงทะเบียนแอป**

    ![ค้นหาการลงทะเบียนแอป](media/embed-sample-for-customers/embed-sample-for-customers-003.png)

    เลือกแอปพลิเคชันที่ต้องการรับ **applicationId**

    ![การเลือกแอป](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

    คุณควรจะเห็น **ID แอปพลิเคชัน** ที่แสดงในรูปของ GUID ใช้ **ID แอปพลิเคชัน** นี้เป็น **applicationId** สำหรับแอปพลิเคชัน

    ![applicationId](media/embed-sample-for-customers/embed-sample-for-customers-007.png)

    ป้อนข้อมูล **workspaceId** ด้วย **พื้นที่ทำงานแอปพลิเคชัน GUID** จาก Power BI

    ![workspaceId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

    กรอกข้อมูล **reportId** ด้วย **GUID รายงาน**จาก Power BI

    ![reportId](media/embed-sample-for-customers/embed-sample-for-customers-032.png)

    * กรอกข้อมูล **pbiUsername** ด้วยบัญชีผู้ใช้หลัก Power BI
    * กรอกข้อมูล **pbiPassword** ด้วยรหัสผ่านสำหรับบัญชีผู้ใช้หลัก Power BI

3. เรียกใช้แอปพลิเคชัน

    ก่อนอื่น ให้เลือก**เรียกใช้**ใน **Visual Studio**

    ![เรียกใช้แอปพลิเคชัน](media/embed-sample-for-customers/embed-sample-for-customers-033.png)

    จากนั้นเลือก **Embed Report** ขึ้นอยู่กับเนื้อหาที่คุณเลือกที่จะทดสอบ - รายงาน, แดชบอร์ด หรือไทล์ - แล้วเลือกตัวเลือกนั้นในแอปพลิเคชัน

    ![เลือกเนื้อหา](media/embed-sample-for-customers/embed-sample-for-customers-034.png)

    ตอนนี้ คุณสามารถดูรายงานในแอปพลิเคชันตัวอย่างได้แล้ว

    ![ดูแอปพลิเคชัน](media/embed-sample-for-customers/embed-sample-for-customers-035.png)

## <a name="embed-your-content-within-your-application"></a>ฝังเนื้อหาของคุณภายในแอปพลิเคชันของคุณ

ถึงแม้ว่าขั้นตอนการฝังเนื้อหาของคุณสามารถทำได้ด้วย [Power BI REST APIs](https://docs.microsoft.com/rest/api/power-bi/)รหัสตัวอย่างที่อธิบายไว้ในบทความนี้ถูกสร้างด้วย **.NET SDK**

การฝังตัวสำหรับลูกค้าของคุณภายในแอปพลิเคชันคุณ จำเป็นต้องให้คุณรับ**โทเค็นการเข้าถึง**สำหรับบัญชีหลักของคุณจาก **Azure AD** เป็นเรื่องจำเป็นต้องได้รับ[โทเค็นการเข้าถึง Azure AD](get-azuread-access-token.md#access-token-for-non-power-bi-users-app-owns-data) สำหรับแอปพลิเคชัน Power BI ของคุณ**โดยใช้แอปเป็นเจ้าของข้อมูล** ก่อนที่คุณจะเรียกใช้ [Power BI REST APIs](https://docs.microsoft.com/rest/api/power-bi/).

ในการสร้าง Power BI Client ด้วย **โทเค็นการเข้าถึง** คุณต้องการสร้างวัตถุไคลเอ็นต์ Power BI ซึ่งช่วยให้คุณสามารถติดต่อกับ [Power BI REST APIs](https://docs.microsoft.com/rest/api/power-bi/) ได้ คุณสร้างวัตถุไคลเอ็นต์ Power BI ได้โดยการคลุม **AccessToken** ด้วยวัตถุ ***Microsoft.Rest.TokenCredentials***

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. it's used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to embed items.
}
```

### <a name="get-the-content-item-you-want-to-embed"></a>รับเนื้อหาที่คุณต้องการฝังตัว

คุณสามารถใช้วัตถุไคลเอ็นต์ Power BI เพื่อดึงตัวอ้างอิงไปยังเนื้อหาที่คุณต้องการฝังตัว

นี่คือตัวอย่างรหัสวิธีการดึงรายงานตัวแรกจากพื้นที่ทำงานที่ระบุไว้

*ตัวอย่างของการรับรายการเนื้อหาไม่ว่าจะเป็นรายงาน แดชบอร์ด หรือไทล์ที่คุณต้องการฝังจะมีให้ในไฟล์ Controllers\HomeController.cs ใน[ตัวอย่างแอปพลิเคชัน](#embed-your-content-within-a-sample-application)*

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You need to provide the workspaceId where the dashboard resides.
ODataResponseListReport reports = await client.Reports.GetReportsInGroupAsync(workspaceId);

// Get the first report in the group.
Report report = reports.Value.FirstOrDefault();
```

### <a name="create-the-embed-token"></a>สร้างโทเค็นแบบฝังตัว

สร้างโทเค็นแบบฝังตัวซึ่งสามารถใช้ได้จาก JavaScript API โทเค็นแบบฝังตัวจะเป็นแบบเฉพาะเจาะจงกับรายการที่คุณจะฝัง ซึ่งหมายความว่า ทุกครั้งที่คุณต้องการฝังเนื้อหาของ Power BI ชิ้นหนึ่ง คุณต้องสร้างโทเค็นการฝังใหม่ขึ้นมา สำหรับข้อมูลเพิ่มเติม รวมไปถึง **accessLevel** ที่จะใช้ ดู[GenerateToken API](https://msdn.microsoft.com/library/mt784614.aspx)

นี่คือตัวอย่างของการเพิ่มโทเค็นฝังตัวสำหรับรายงานให้กับแอปพลิเคชันของคุณ

*ตัวอย่างของการสร้างโทเค็นฝังตัวสำหรับรายงาน แดชบอร์ด หรือไทล์จะมีให้ในไฟล์ Controllers\HomeController.cs ใน[ตัวอย่างแอปพลิเคชัน](#embed-your-content-within-a-sample-application)*

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Reports.GenerateTokenInGroup(workspaceId, report.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = report.EmbedUrl,
    Id = report.Id
};
```

คลาสถูกสร้างให้สำหรับ **EmbedConfig** และ **TileEmbedConfig** ตัวอย่างมีให้ในไฟล์ **Models\EmbedConfig.cs** และไฟล์ **Models\TileEmbedConfig.cs**

### <a name="load-an-item-using-javascript"></a>โหลดเนื้อหาโดยใช้ JavaScript

คุณสามารถใช้ JavaScript เพื่อโหลดรายงานลงในองค์ประกอบ div บนเว็บเพจของคุณ

สำหรับตัวอย่างแบบเต็มของการใช้ JavaScript API คุณสามารถใช้[เครื่องมือ Playground](https://microsoft.github.io/PowerBI-JavaScript/demo) ได้ เครื่องมือ Playground คือวิธีที่รวดเร็วเพื่อลองเล่นกับตัวอย่าง Power BI Embedded ชนิดต่าง ๆ กัน คุณยังสามารถรับข้อมูลเพิ่มเติมเกี่ยวกับ JavaScript API โดยเข้าดูที่หน้า [Powerbi-javascript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) ได้

ตัวอย่างนี้ใช้รูปแบบ **EmbedConfig** และรูปแบบ **TileEmbedConfig** พร้อมกับมุมมองรายงาน

*ตัวอย่างของการเพิ่มมุมมองรายงาน แดชบอร์ด หรือไทล์มีให้ในไฟล์ Views\Home\EmbedReport.cshtml, Views\Home\EmbedDashboard.cshtml หรือ Views\Home\Embedtile.cshtml ใน[ตัวอย่างแอปพลิเคชัน](#embed-your-content-within-a-sample-application)*

```javascript
<script src="~/scripts/powerbi.js"></script>
<div id="reportContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read report Id from Model
    var embedReportId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedReportId,
        permissions: models.Permissions.All,
        settings: {
            filterPaneEnabled: true,
            navContentPaneEnabled: true
        }
    };

    // Get a reference to the embedded report HTML element
    var reportContainer = $('#reportContainer')[0];

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);
</script>
```

## <a name="move-to-production"></a>ย้ายไปยังการผลิต

เมื่อคุณเสร็จสิ้นการพัฒนาแอปพลิเคชันของคุณ ถัดไปคือการสนับสนุนพื้นที่ทำงานแอปด้วยความจุเฉพาะ ความจุเฉพาะ จำเป็นสำหรับการย้ายไปยังการผลิต

### <a name="create-a-dedicated-capacity"></a>สร้างความจุเฉพาะ

เมื่อสร้างความจุเฉพาะ คุณสามารถใช้ประโยชน์จากการมีทรัพยากรเฉพาะที่จัดสรรไว้สำหรับลูกค้าของคุณ คุณสามารถซื้อความจุเฉพาะภายใน[พอร์ทัล Microsoft Azure](https://portal.azure.com) ได้ สำหรับรายละเอียดเกี่ยวกับวิธีการสร้างความจุ Power BI Embedded โปรดดู[สร้างความจุ Power BI Embedded ในพอร์ทัล Azure](azure-pbie-create-capacity.md)

ใช้ตารางด้านล่างเพื่อกำหนดความจุ Power BI Embedded ที่เหมาะกับความต้องการของคุณที่สุด

| โหนดของความจุ | แกนทั้งหมด<br/>*(Backend + frontend)* | Backend Cores | Frontend Cores | การจำกัดการเชื่อมต่อ DirectQuery/live|
| --- | --- | --- | --- | --- | --- |
| A1 |1 v-core(s) |0.5 core(s), 3-GB RAM |0.5 cores |0 5 per second |
| A2 |2 v-core(s) |1 core(s), 5-GB RAM |1 cor(e) | 10 ต่อวินาที |
| A3 |4 v-core(s) |2 core(s), 10-GB RAM |2 core(s) | 15 ต่อวินาที |
| A4 |8 v-core(s) |4 core(s), 25-GB RAM |4 core(s) |30 ต่อวินาที |
| A5 |16 v-core(s) |8 core(s), 50-GB RAM |8 core(s) |60 ต่อวินาที |
| A6 |32 v-core(s) |16 core(s), 100-GB RAM |16 core(s) |120 ต่อวินาที |

**_ด้วย A SKU คุณไม่สามารถเข้าถึงเนื้อหา Power BI ที่มีสิทธิ์การใช้งาน Power BI ฟรี_**

โทเค็นฝังตัวที่มีสิทธิ์การใช้งาน PRO มีไว้สำหรับทดสอบการพัฒนา ดังนั้น บัญชีหลัก Power BI จึงสามารถสร้าง จำนวนโทเค็นฝังตัวได้อย่างจำกัด ความจุเฉพาะจำเป็นสำหรับการฝังตัวในสภาพแวดล้อมการผลิต ไม่มีข้อจำกัดในจำนวนโทเค็นแบบฝังตัวที่คุณสามารถสร้างด้วยความจุเฉพาะ ไปยัง[คุณลักษณะที่มี](https://docs.microsoft.com/rest/api/power-bi/availablefeatures/getavailablefeatures) เพื่อตรวจสอบค่าการใช้งาน ที่สามารถบอกได้ว่าปัจจุบันมีการใช้งานฝังตัวแล้วกี่เปอร์เซ็นต์ ปริมาณการใช้งานขึ้นอยู่กับบัญชีผู้ใช้หลัก

สำหรับรายละเอียดเพิ่มเติม ดูได้ที่ [เอกสารทางเทคนิคเรื่องการวางแผนความจุวิเคราะห์แบบฝัง](https://aka.ms/pbiewhitepaper)

### <a name="assign-an-app-workspace-to-a-dedicated-capacity"></a>กำหนดพื้นที่ทำงานของแอปให้กับความจุเฉพาะ

เมื่อคุณสร้างความจุเฉพาะแล้ว คุณสามารถกำหนดพื้นที่ทำงานแอปไปยังความจุเฉพาะนั้นได้ เมื่อต้องกำหนดความจุเฉพาะให้พื้นที่ทำงาน ให้ทำตามขั้นตอนเหล่านี้

1. ภายใน**บริการของ Power BI** ขยายพื้นที่ทำงาน และเลือกที่จุดไข่ปลาสำหรับพื้นที่ทำงานที่คุณกำลังใช้เพื่อฝังเนื้อหา แล้วเลือก**แก้ไขพื้นที่ทำงาน**

    ![แก้ไขพื้นที่ทำงาน](media/embed-sample-for-customers/embed-sample-for-customers-036.png)

2. ขยาย**ขั้นสูง** แล้วเปิดใช้งาน**ความจุเฉพาะ** จากนั้นเลือกความจุเฉพาะที่คุณสร้างขึ้น จากนั้นเลือก**บันทึก**

    ![กำหนดความจุเฉพาะ](media/embed-sample-for-customers/embed-sample-for-customers-024.png)

3. หลังจากเลือก **บันทึก** คุณควรจะเห็น **รูปข้าวหลามตัด** ถัดจากชื่อพื้นที่ทำงานแอพลิเคชัน

    ![เชื่อมโยงพื้นที่ทำงานของแอปไปยังความจุ](media/embed-sample-for-customers/embed-sample-for-customers-037.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีฝังเนื้อหา Power BI ในแอปพลิเคชันสำหรับลูกค้าของคุณ คุณยังสามารถทดลองฝังเนื้อหา Power BI สำหรับองค์กรของคุณ

> [!div class="nextstepaction"]
>[ฝังตัวสำหรับองค์กรของคุณ](embed-sample-for-your-organization.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](http://community.powerbi.com/)

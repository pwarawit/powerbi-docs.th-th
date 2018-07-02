---
title: ฝังเนื้อหา Power BI ลงในแอปพลิเคชันสำหรับลูกค้าของคุณ
description: เรียนรู้วิธีการรวมหรือฝัง แดชบอร์ด, ไทล์ หรือรายงาน ลงในเว็บแอปด้วย Power BI API สำหรับลูกค้าของคุณ
author: markingmyname
ms.author: maghan
ms.date: 05/25/2018
ms.topic: tutorial
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: ae683dfbeb7b3848575ab766c33b695eb823d497
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34721052"
---
# <a name="tutorial-embed-a-power-bi-report-dashboard-or-tile-into-an-application-for-your-customers"></a>บทช่วยสอน: ฝังรายงาน, แดชบอร์ด หรือไทล์ Power BI ลงในแอปพลิเคชันสำหรับลูกค้าของคุณ
ด้วย **Power BI Embedded ใน Azure** คุณสามารถฝังรายงาน, แดชบอร์ด หรือไทล์ลงในการใช้แอปพลิเคชันโดยใช้**แอปเป็นเจ้าของข้อมูล**ได้ **แอปเป็นเจ้าของข้อมูล** เกี่ยวกับแอปพลิเคชันที่ใช้ Power BI เป็นแพลตฟอร์มการวิเคราะห์แบบฝังตัว นี่คือสถานการณ์ทั่วไปของ**นักพัฒนา ISV** ในฐานะเป็น**นักพัฒนา ISV** คุณสามารถสร้างเนื้อหา Power BI ที่แสดงรายงาน, แดชบอร์ด หรือไทล์ในแอปพลิเคชันที่รวมทั้งหมดเข้าด้วยกัน และโต้ตอบได้ โดยไม่ต้องให้ผู้ใช้แอปพลิเคชันต้องมีสิทธิ์การใช้งาน Power BI หรือแม้แต่ รู้ว่ามี Power BI อยู่ภายใน บทช่วยสอนนี้สาธิตวิธีการรวมรายงานลงในแอปพลิเคชัน โดยใช้ **Power BI** SDK .NET พร้อมกับ **Power BI** JavaScript API เมื่อใช้ **Power BI Embedded ใน Azure** สำหรับลูกค้าของคุณโดยใช้**แอปเป็นเจ้าของข้อมูล**

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการ:
>[!div class="checklist"]
>* ลงทะเบียนแอปพลิเคชันใน Azure
>* ฝังรายงาน Power BI ลงในแอปพลิเคชัน

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
เพื่อเริ่มต้นใช้งาน คุณต้องการบัญชีผู้ใช้ **Power BI Pro** ซึ่งจะเป็น**บัญชีหลัก**ของคุณ และการสมัครใช้งาน **Microsoft Azure**

* ถ้าคุณยังไม่ได้ลงทะเบียนสำหรับ **Power BI Pro** [ลงทะเบียนทดลองใช้ฟรี](https://powerbi.microsoft.com/en-us/pricing/)ก่อนที่คุณจะเริ่ม
* ถ้าคุณยังไม่มีการสมัครใช้งาน Azure สร้าง[บัญชีฟรี](https://azure.microsoft.com/free/?WT.mc_id=A261C142F)ก่อนที่คุณจะเริ่ม
* คุณจำเป็นต้องตั้งค่า[ผู้เช่า Azure Active Directory](create-an-azure-active-directory-tenant.md) ของคุณเอง
* คุณต้องติดตั้ง [Visual Studio](https://www.visualstudio.com/) (เวอร์ชัน 2013 หรือใหม่กว่า)

## <a name="setup-your-embedded-analytics-development-environment"></a>ตั้งค่าสภาพแวดล้อมการพัฒนา การวิเคราะห์แบบฝังตัวของคุณ

ก่อนที่คุณจะเริ่มการฝังรายงาน, แดชบอร์ด หรือไทล์ ลงในแอปพลิเคชันของคุณ คุณจำเป็นต้องตรวจสอบให้แน่ใจว่า สภาพแวดล้อมของคุณถูกตั้งค่าเพื่ออนุญาตให้ทำการฝัง โดยถือเป็นส่วนหนึ่งของการตั้งค่า คุณจะต้องทำสิ่งต่อไปนี้

คุณสามารถเข้าถึง[เครื่องมือประสบการณ์การเตรียมความพร้อม](https://aka.ms/embedsetup/AppOwnsData) เพื่อเริ่มต้นใช้งานได้อย่างรวดเร็ว และดาวน์โหลดแอปพลิเคชันตัวอย่างที่ช่วยแนะนำคุณไปตามขั้นตอนการสร้างสภาพแวดล้อม และการฝังรายงานได้

แต่ถ้าคุณเลือกที่จะตั้งค่าสภาพแวดล้อมด้วยตนเอง คุณสามารถดำเนินต่อตามด้านล่าง
### <a name="register-an-application-in-azure-active-directory-azure-ad"></a>ลงทะเบียนแอปพลิเคชันใน Azure Active Directory (Azure AD)

คุณลงทะเบียนแอปพลิเคชันของคุณกับ Azure Active Directory เพื่ออนุญาตให้แอปพลิเคชันของคุณเข้าถึง Power BI REST API ซึ่งจะช่วยให้คุณสร้างข้อมูลประจำตัวสำหรับแอปพลิเคชันของคุณ และระบุสิทธิ์ไปยังแหล่งข้อมูล REST ของ Power BI ได้

1. ยอมรับ[เงื่อนไขของ Microsoft Power BI API](https://powerbi.microsoft.com/api-terms)

2. ลงชื่อเข้าใช้[พอร์ทัล Azure](https://portal.azure.com)
 
    ![พอร์ทัลหลัก Azure](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

3. ในบานหน้าต่างนำทางด้านซ้าย เลือก**บริการทั้งหมด** เลือก**การลงทะเบียนแอป** แล้วเลือก**ลงทะเบียนแอปพลิเคชันใหม่**
   
    ![ค้นหาการลงทะเบียนแอป](media/embed-sample-for-customers/embed-sample-for-customers-003.png)</br>
    ![ลงทะเบียนแอปใหม่](media/embed-sample-for-customers/embed-sample-for-customers-004.png)

4. ทำตามพร้อมท์และสร้างแอปพลิเคชัน์ใหม่ สำหรับแอปเป็นเจ้าของข้อมูล คุณจำเป็นต้องใช้ชนิดของแอปพลิเคชันแบบ**ดั้งเดิม** คุณยังต้องให้ **URI ที่เปลี่ยนเส้นทาง** ซึ่ง **Azure AD** ใช้เพื่อส่งกลับผลลัพธ์โทเค็น ใส่ค่าที่เฉพาะสำหรับแอปพลิเคชันของคุณ (ตัวอย่างเช่น: http://localhost:13526/redirect)

    ![สร้างแอป](media/embed-sample-for-customers/embed-sample-for-customers-005.png)

### <a name="apply-permissions-to-your-application-within-azure-active-directory"></a>นำสิทธิ์ไปใช้กับแอปพลิเคชันของคุณภายใน Azure Active Directory

คุณจะต้องเปิดใช้งานสิทธิ์เพิ่มเติมให้กับแอปพลิเคชันของคุณ นอกเหนือจากสิทธิ์ที่มีในหน้าลงทะเบียนแอปพลิเคชัน คุณจะต้องเข้าสู่ระบบ ด้วยบัญชี*หลัก*ที่ใช้สำหรับฝังตัว หรือบัญชีผู้ดูแลระบบส่วนกลาง

### <a name="use-the-azure-active-directory-portal"></a>ใช้พอร์ทัล Azure Active Directory

1. เรียกดู[การลงทะเบียนแอป](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade)ภายในพอร์ทัล Azure และเลือกแอปที่คุณกำลังใช้สำหรับการฝัง
   
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

7. เลือกสิทธิ์ทั้งหมดใต้**สิทธิ์ที่ได้รับมอบ** คุณจะต้องเลือกทีละหนึ่งเพื่อบันทึกส่วนที่เลือก เลือก**บันทึก**เมื่อทำเสร็จแล้ว
   
    ![เลือกสิทธิ์ที่ได้รับมอบสิทธิ์](media/embed-sample-for-customers/embed-sample-for-customers-015.png)

8. ภายใน**สิทธิ์ที่ต้องใช้**เลือก**ให้สิทธิ์**
   
    การดำเนินการ**การให้สิทธิ์**จำเป็นสำหรับ*บัญชีหลัก*เพื่อหลีกเลี่ยงการถูกพร้อมท์เพื่อการยินยอมโดย Azure AD ถ้าบัญชีผู้ใช้ดำเนินการกระทำนี้ คือ ผู้ดูแลระบบส่วนกลาง คุณจะต้องให้สิทธิ์กับผู้ใช้ทั้งหมดภายในองค์กรของคุณสำหรับแอปพลิเคชันนี้ ถ้าบัญชีผู้ใช้ดำเนินการกระทำนี้ คือ *บัญชีหลัก*และไม่ใช่ผู้ดูแลระบบส่วนกลาง คุณจะให้สิทธิ์แก่*บัญชีหลัก*สำหรับแอปพลิเคชันนี้เท่านั้น
   
    ![การให้สิทธิ์ภายในกล่องโต้ตอบสิทธิ์ที่ต้องใช้](media/embed-sample-for-customers/embed-sample-for-customers-016.png)

## <a name="setup-your-power-bi-environment"></a>ตั้งค่าสภาพแวดล้อม Power BI ของคุณ

### <a name="create-an-app-workspace"></a>สร้างพื้นที่ทำงานสำหรับแอปฯ

ถ้าคุณมีการฝังรายงาน, แดชบอร์ด หรือไทล์สำหรับลูกค้าของคุณ คุณจะต้องวางเนื้อหาของคุณภายในพื้นที่ทำงานแอป บัญชี*หลัก*จะต้องเป็นผู้ดูแลระบบของพื้นที่ทำงานแอป

1. เริ่มต้นโดยการสร้างพื้นที่ทำงาน เลือก **พื้นที่ทำงาน** > **สร้างพื้นที่ทำงานแอป** นี่จะเป็นตำแหน่งที่วางเนื้อหาที่แอปพลิเคชันของคุณจำเป็นต้องเข้าถึง

    ![สร้างพื้นที่ทำงาน](media/embed-sample-for-customers/embed-sample-for-customers-020.png)

2. ตั้งชื่อพื้นที่ทำงาน ถ้าชื่อ **ID พื้นที่ทำงาน**ที่ตรงกันไม่สามารถใช้ได้ แก้ไขให้ ID ใหม่มีค่าไม่ซ้ำกัน นี่จะเป็นชื่อของแอปด้วย

    ![ตั้งชื่อพื้นที่ทำงาน](media/embed-sample-for-customers/embed-sample-for-customers-021.png)

3. คุณมีสองสามตัวเลือกที่จะตั้งค่า ถ้าคุณเลือก**สาธารณะ** ทุกคนในองค์กรคุณสามารถดูสิ่งที่อยู่ในพื้นที่ทำงานได้ ในทางกลับกัน **ส่วนตัว** หมายถึง เฉพาะสมาชิกของพื้นที่ทำงานเท่านั้นที่สามารถดูเนื้อหา

    ![ส่วนตัว/สาธารณะ](media/embed-sample-for-customers/embed-sample-for-customers-022.png)

    คุณไม่สามารถเปลี่ยนการตั้งค่า สาธารณะ/ส่วนตัว ได้หลังจากคุณสร้างกลุ่มแล้ว

4. คุณยังสามารถเลือกว่าสมาชิกสามารถเข้าถึงแบบ**แก้ไข**ได้หรือ**ดูเท่านั้น**

    ![การเพิ่มสมาชิก](media/embed-sample-for-customers/embed-sample-for-customers-023.png)

5. ใส่ที่อยู่อีเมลของบุคคลที่คุณต้องการให้เข้าถึงพื้นที่ทำงาน และเลือก**เพิ่ม** คุณไม่สามารถเพิ่มนามแฝงของกลุ่ม เพิ่มได้แค่บุคคลอย่างเดียว

6. ตัดสินใจว่า แต่ละคนเป็นสมาชิกหรือผู้ดูแลระบบ ผู้ดูแลระบบสามารถแก้ไขพื้นที่ทำงาน รวมถึงการเพิ่มสมาชิกคนอื่น ๆ สมาชิกสามารถแก้ไขเนื้อหาในพื้นที่ทำงาน นอกจากว่าพวกเขามีสิทธิ์เข้าถึงแบบดูเท่านั้น ทั้งผู้ดูแลระบบและสมาชิกสามารถเผยแพร่แอป

ในตอนนี้ คุณสามารถดูพื้นที่ทำงานใหม่แล้ว Power BI จะสร้างพื้นที่ทำงาน และเปิดพื้นที่ทำงานนั้น ซึ่งจะปรากฏขึ้นในรายการของพื้นที่ทำงานที่คุณเป็นสมาชิก เนื่องจากคุณเป็นผู้ดูแล คุณสามารถเลือกจุดไข่ปลา (...) เพื่อกลับมา และทำการเปลี่ยนแปลง เพิ่มสมาชิกใหม่ หรือเปลี่ยนแปลงสิทธิ์ของพวกเขาได้

   ![พื้นที่ทำงานใหม่](media/embed-sample-for-customers/embed-sample-for-customers-025.png)

### <a name="create-and-publish-your-reports"></a>สร้าง และเผยแพร่รายงานของคุณ

คุณสามารถสร้างรายงานและชุดข้อมูลของคุณโดยใช้ Power BI Desktop แล้วจึงเผยแพร่รายงานเหล่านั้นไปยังพื้นที่ทำงานของแอป ผู้ใช้ปลายทางที่เผยแพร่รายงานจำเป็นต้องมีสิทธิ์การใช้งาน Power BI Pro เพื่อเผยแพร่ไปยังพื้นที่ทำงานของแอป

1. ดาวน์โหลดตัวอย่าง[การสาธิตบล็อก](https://github.com/Microsoft/powerbi-desktop-samples)จาก GitHub

    ![ตัวอย่างรายงาน](media/embed-sample-for-customers/embed-sample-for-customers-026-1.png)

2. เปิดรายงาน PBIX ตัวอย่างใน **Power BI Desktop**

   ![รายงาน PBI บนเดสก์ท็อป](media/embed-sample-for-customers/embed-sample-for-customers-027.png)

3. เผยแพร่ไปยัง**พื้นที่ทำงานแอป**

   ![รายงาน PBI บนเดสก์ท็อป](media/embed-sample-for-customers/embed-sample-for-customers-028.png)

    ในตอนนี้ คุณสามารถดูรายงานในบริการของ Power BI แบบออนไลน์

   ![รายงาน PBI บนเดสก์ท็อป](media/embed-sample-for-customers/embed-sample-for-customers-029.png)

## <a name="embed-your-content"></a>ฝังเนื้อหาของคุณ

การฝังตัวสำหรับลูกค้าของคุณภายในแอปพลิเคชันคุณ จำเป็นต้องให้คุณรับ**โทเค็นการเข้าถึง**สำหรับบัญชีหลักของคุณจาก **Azure AD** จำเป็นต้อง[รับโทเค็นการเข้าถึง Azure AD](get-azuread-access-token.md#access-token-for-non-power-bi-users-app-owns-data) สำหรับแอปพลิเคชัน Power BI ของคุณ โดยใช้แอปเป็นเจ้าของข้อมูล ก่อนที่คุณจะเรียกใช้ไปยัง Power BI API

ทำตามขั้นตอนเหล่านี้เพื่อเริ่มการฝังเนื้อหาของคุณโดยใช้แอปพลิเคชันตัวอย่าง

1. ดาวน์โหลด[ตัวอย่างแอปเป็นเจ้าของข้อมูล](https://github.com/Microsoft/PowerBI-Developer-Samples)จาก GitHub เพื่อเริ่มต้น

    ![ตัวอย่างแอปพลิเคชัน แอปเป็นเจ้าของข้อมูล](media/embed-sample-for-customers/embed-sample-for-customers-026.png)

2. เปิดแฟ้ม Web.config ในแอปพลิเคชันตัวอย่าง มีเขตข้อมูล 5 เขตที่คุณจะต้องใส่ เพื่อให้เรียกใช้แอปพลิเคชันได้สำเร็จ **clientID**, **groupId**, **reportId**, **pbiUsername** และ **pbiPassword**

      ![แฟ้ม Web.config](media/embed-sample-for-customers/embed-sample-for-customers-030.png)

    * กรอกข้อมูล **clientId** ด้วย **ID แอปพลิเคชัน**จาก **Azure** **clientId** ให้แอปพลิเคชันใช้ระบุตัวเองระหว่างการร้องขอสิทธิ์กับผู้ใช้ เพื่อรับ **clientId** ทำตามขั้นตอนเหล่านี้:

    1. ลงชื่อเข้าใช้[พอร์ทัล Azure](https://portal.azure.com)

        ![พอร์ทัลหลัก Azure](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

    2. ในบานหน้าต่างนำทางด้านซ้าย เลือก**บริการทั้งหมด** และเลือก**การลงทะเบียนแอป**

        ![ค้นหาการลงทะเบียนแอป](media/embed-sample-for-customers/embed-sample-for-customers-003.png)
    3. เลือกแอปพลิเคชันที่คุณต้องการรับ **clientId**

        ![การเลือกแอป](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

    4. คุณควรจะเห็น **ID แอปพลิเคชัน** ที่แสดงในรูปของ GUID ใช้ **ID แอปพลิเคชัน**นี้เป็นค่า **clientId** สำหรับแอปพลิเคชัน

        ![clientId](media/embed-sample-for-customers/embed-sample-for-customers-007.png)     

    * กรอกข้อมูล **groupId** ด้วย **GUID พื้นที่ทำงานของแอป**จาก Power BI

        ![groupId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

    * กรอกข้อมูล **reportId** ด้วย **GUID รายงาน**จาก Power BI

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

## <a name="move-to-production"></a>ย้ายไปยังการผลิต

หลังจากที่คุณพัฒนาแอปพลิเคชันของคุณเสร็จแล้ว ก็ถึงเวลาที่จะรองรับพื้นที่ทำงานของแอปคุณด้วยความจุเฉพาะ ความจุเฉพาะ จำเป็นสำหรับการย้ายไปยังการผลิต

### <a name="create-a-dedicated-capacity"></a>สร้างความจุเฉพาะ
โดยการสร้างความจุเฉพาะ คุณสามารถใช้ประโยชน์จากการมีทรัพยากรเฉพาะที่จัดสรรไว้สำหรับลูกค้าของคุณ สำหรับพื้นที่ทำงานที่ไม่ได้กำหนดความจุเฉพาะให้ พื้นที่ทำงานเหล่านี้จะอยู่ในความจุที่แชร์กัน คุณสามารถสร้างความจุเฉพาะโดยใช้โซลูชัน[ความจุเฉพาะ Power BI Embedded](https://docs.microsoft.com/azure/power-bi-embedded/create-capacity) ใน Azure ได้

>[!Note]
>โทเค็นฝังตัวที่มีสิทธิ์การใช้งาน PRO มีไว้สำหรับการพัฒนาและการทดสอบ จึงจำกัดจำนวนโทเค็นฝังตัวของบัญชีหลัก Power BI ที่สามารถสร้างขึ้นได้ คุณต้องซื้อความจุเฉพาะสำหรับการฝังตัวในสภาพแวดล้อมการผลิต ไม่มีข้อจำกัดในจำนวนโทเค็นแบบฝังตัวที่คุณสามารถสร้างด้วยความจุเฉพาะ ไปยัง[ดูคุณลักษณะที่มี](https://msdn.microsoft.com/library/mt846473.aspx) เพื่อตรวจสอบค่าการใช้งาน ที่สามารถบอกได้ว่าปัจจุบันมีการใช้งานฝังตัวแล้วกี่เปอร์เซ็นต์
>

### <a name="assign-app-workspace-to-dedicated-capacity"></a>กำหนดพื้นที่ทำงานของแอปให้กับความจุเฉพาะ

เมื่อมีการสร้างความจุเฉพาะแล้ว กำหนดพื้นที่ทำงานแอปไปยังความจุเฉพาะนั้น เพื่อทำให้เสร็จสมบูรณ์ ทำตามขั้นตอนเหล่านี้

1. ภายใน**บริการของ Power BI** ขยายพื้นที่ทำงาน และเลือกที่จุดไข่ปลาสำหรับพื้นที่ทำงานที่คุณจะฝังเนื้อหาของคุณ แล้วเลือก**แก้ไขพื้นที่ทำงาน**

    ![แก้ไขพื้นที่ทำงาน](media/embed-sample-for-customers/embed-sample-for-customers-036.png)

2. ขยาย**ขั้นสูง** แล้วเปิดใช้งาน**ความจุเฉพาะ** จากนั้นเลือกความจุเฉพาะที่คุณสร้างขึ้น จากนั้นเลือก**บันทึก**

    ![กำหนดความจุเฉพาะ](media/embed-sample-for-customers/embed-sample-for-customers-024.png)

สำหรับตัวอย่างแบบเต็มของการใช้ JavaScript API คุณสามารถใช้[เครื่องมือ Playground](https://microsoft.github.io/PowerBI-JavaScript/demo) ได้ นี่คือวิธีที่รวดเร็วเพื่อลองเล่นกับตัวอย่าง Power BI Embedded ชนิดต่าง ๆ กัน คุณยังสามารถรับข้อมูลเพิ่มเติมเกี่ยวกับ JavaScript API โดยไปที่หน้า [PowerBI-JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) ได้

สำหรับคำถามเพิ่มเติมเกี่ยวกับ Power BI Embedded โปรดไปที่หน้า[คำถามที่ถามบ่อย](embedded-faq.md)  ถ้าคุณกำลังมีปัญหากับ Power Bi Embedded ภายในแอปพลิเคชันของคุณ แล้วโปรดไปที่หน้า[การแก้ไขปัญหา](embedded-troubleshoot.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)
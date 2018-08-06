---
title: ฝังเนื้อหา Power BI ลงในแอปพลิเคชันสำหรับองค์กรของคุณ
description: เรียนรู้วิธีการรวมหรือฝัง รายงาน แดชบอร์ด หรือไทล์ ลงในเว็บแอปด้วย Power BI API สำหรับองค์กรของคุณ
author: markingmyname
ms.author: maghan
ms.date: 07/13/2018
ms.topic: tutorial
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 544429528ed51dd2928eb82632f512ff3f7d5afd
ms.sourcegitcommit: fecea174721d0eb4e1927c1116d2604a822e4090
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/31/2018
ms.locfileid: "39359742"
---
# <a name="tutorial-embed-a-power-bi-report-dashboard-or-tile-into-an-application-for-your-organization"></a>บทช่วยสอน: ฝังรายงาน แดชบอร์ด หรือไทล์ Power BI ลงในแอปพลิเคชันสำหรับองค์กรของคุณ
บทช่วยสอนนี้จะสาธิตวิธีการรวมรายงานลงในแอปพลิเคชันโดยใช้ **Power BI .NET SDK** พร้อมกับ **Power BI JavaScript API** เมื่อทำการฝัง **Power BI** ลงในแอปพลิเคชันสำหรับองค์กรของคุณ ด้วย **Power BI** คุณสามารถฝังรายงาน แดชบอร์ด หรือไทล์ ลงในแอปพลิเคชันโดยใช้ **ผู้ใช้ที่เป็นเจ้าของข้อมูล** **ผู้ใช้ที่เป็นเจ้าของข้อมูล** ช่วยให้แอปพลิเคชันของคุณขยายบริการ Power BI

![ดูแอปพลิเคชัน](media/embed-sample-for-your-organization/embed-sample-for-your-organization-035.png)

ในบทช่วยสอนนี้ คุณจะเรียนรู้วิธีการ:
>[!div class="checklist"]
>* ลงทะเบียนแอปพลิเคชันใน Azure
>* ฝังรายงาน Power BI ลงในแอปพลิเคชัน

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
คุณต้องมีบัญชี **Power BI Pro** และการสมัครใช้งาน **Microsoft Azure** เพื่อเริ่มต้นใช้งาน

* ถ้าคุณยังไม่ได้ลงทะเบียนสำหรับ **Power BI Pro** [ลงทะเบียนทดลองใช้ฟรี](https://powerbi.microsoft.com/en-us/pricing/)ก่อนที่คุณจะเริ่ม
* ถ้าคุณยังไม่มีการสมัครใช้งาน Azure สร้าง[บัญชีฟรี](https://azure.microsoft.com/free/?WT.mc_id=A261C142F)ก่อนที่คุณจะเริ่ม
* คุณจำเป็นต้องตั้งค่า[ผู้เช่า Azure Active Directory](create-an-azure-active-directory-tenant.md) ของคุณเอง
* คุณต้องติดตั้ง [Visual Studio](https://www.visualstudio.com/) (เวอร์ชัน 2013 หรือใหม่กว่า)

## <a name="setup-your-embedded-analytics-development-environment"></a>ตั้งค่าสภาพแวดล้อมการพัฒนา การวิเคราะห์แบบฝังตัวของคุณ

ก่อนที่คุณจะเริ่มการฝังรายงาน, แดชบอร์ด หรือไทล์ ลงในแอปพลิเคชันของคุณ คุณจำเป็นต้องตรวจสอบให้แน่ใจว่า สภาพแวดล้อมของคุณถูกตั้งค่าเพื่ออนุญาตให้ทำการฝัง โดยถือเป็นส่วนหนึ่งของการตั้งค่า คุณจะต้องทำสิ่งต่อไปนี้

คุณสามารถเข้าถึง[เครื่องมือประสบการณ์การเตรียมความพร้อม](https://aka.ms/embedsetup/UserOwnsData) เพื่อเริ่มต้นใช้งาน และดาวน์โหลดแอปพลิเคชันตัวอย่างที่ช่วยแนะนำคุณไปตามขั้นตอนการสร้างสภาพแวดล้อม และการฝังรายงานได้

แต่ถ้าคุณเลือกที่จะตั้งค่าสภาพแวดล้อมด้วยตนเอง คุณสามารถดำเนินต่อตามด้านล่าง
### <a name="register-an-application-in-azure-active-directory-azure-ad"></a>ลงทะเบียนแอปพลิเคชันใน Azure Active Directory (Azure AD)

คุณลงทะเบียนแอปพลิเคชันของคุณกับ Azure Active Directory เพื่ออนุญาตให้แอปพลิเคชันของคุณเข้าถึง Power BI REST API ซึ่งจะช่วยให้คุณสร้างข้อมูลประจำตัวสำหรับแอปพลิเคชันของคุณ และระบุสิทธิ์ไปยังแหล่งข้อมูล REST ของ Power BI ได้

1. ยอมรับ[เงื่อนไขของ Microsoft Power BI API](https://powerbi.microsoft.com/api-terms)

2. ลงชื่อเข้าใช้[พอร์ทัล Azure](https://portal.azure.com)

    ![พอร์ทัลหลัก Azure](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

3. ในบานหน้าต่างนำทางด้านซ้าย เลือก**บริการทั้งหมด** เลือก**การลงทะเบียนแอป** แล้วเลือก**ลงทะเบียนแอปพลิเคชันใหม่**

    ![ค้นหาการลงทะเบียนแอป](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)</br>
    ![ลงทะเบียนแอปใหม่](media/embed-sample-for-your-organization/embed-sample-for-your-organization-004.png)

4. ทำตามพร้อมท์และสร้างแอปพลิเคชัน์ใหม่ สำหรับ **ผู้ใช้ที่เป็นเจ้าของข้อมูล** คุณจำเป็นต้องใช้ **Web app/API** สำหรับประเภทแอปพลิเคชัน คุณยังจำเป็นต้องให้ **URI ลงชื่อเข้าใช้** ซึ่ง **Azure AD** ใช้เพื่อส่งผลลัพธ์โทเค็นกลับคืน ป้อนค่าที่ระบุไปยังแอปพลิเคชันของคุณ ( เช่น http://localhost:13526/)

    ![สร้างแอป](media/embed-sample-for-your-organization/embed-sample-for-your-organization-005.png)

### <a name="apply-permissions-to-your-application-within-azure-active-directory"></a>นำสิทธิ์ไปใช้กับแอปพลิเคชันของคุณภายใน Azure Active Directory

คุณจะต้องเปิดใช้งานสิทธิ์เพิ่มเติมให้กับแอปพลิเคชันของคุณ นอกเหนือจากสิทธิ์ที่มีในหน้าลงทะเบียนแอปพลิเคชัน คุณจำเป็นต้องเข้าสู่ระบบด้วยบัญชี *ผู้ดูแลระบบส่วนกลาง* เพื่อเปิดใช้งานสิทธิ์

### <a name="use-the-azure-active-directory-portal"></a>ใช้พอร์ทัล Azure Active Directory

1. เรียกดู[การลงทะเบียนแอป](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade)ภายในพอร์ทัล Azure และเลือกแอปที่คุณกำลังใช้สำหรับการฝัง

    ![การเลือกแอป](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

2. เลือก**การตั้งค่า** จากนั้นภายใต้**การเข้าถึง API** เลือก**สิทธิ์ที่จำเป็น**

    ![สิทธิ์ที่จำเป็น](media/embed-sample-for-your-organization/embed-sample-for-your-organization-008.png)

3. เลือก **Azure Active Directory Windows** จากนั้นตรวจสอบว่าได้เลือก**การเข้าถึงไดเรกทอรีในฐานะผู้ใช้ที่เข้าสู่ระบบ** เลือก**บันทึก**

    ![สิทธิ์ของ Windows Azure AD](media/embed-sample-for-your-organization/embed-sample-for-your-organization-011.png)

4. เลือก**เพิ่ม**

    ![เพิ่มสิทธิ์](media/embed-sample-for-your-organization/embed-sample-for-your-organization-012.png)

5. เลือก**เลือก API**

    ![เพิ่มการเข้าถึง API](media/embed-sample-for-your-organization/embed-sample-for-your-organization-013.png)

6. เลือก**บริการของ Power BI** แล้วเลือก**เลือก**

    ![เลือกบริการของ PBI](media/embed-sample-for-your-organization/embed-sample-for-your-organization-014.png)

7. เลือกสิทธิ์ทั้งหมดใต้**สิทธิ์ที่ได้รับมอบ** คุณจำเป็นต้องเลือกทีละสิทธิ์ เพื่อบันทึกการเลือก เลือก**บันทึก**เมื่อทำเสร็จแล้ว

    ![เลือกสิทธิ์ที่ได้รับมอบสิทธิ์](media/embed-sample-for-your-organization/embed-sample-for-your-organization-015.png)

## <a name="setup-your-power-bi-environment"></a>ตั้งค่าสภาพแวดล้อม Power BI ของคุณ

### <a name="create-an-app-workspace"></a>สร้างพื้นที่ทำงานสำหรับแอปฯ

ถ้าคุณมีการฝังรายงาน, แดชบอร์ด หรือไทล์สำหรับลูกค้าของคุณ คุณจะต้องวางเนื้อหาของคุณภายในพื้นที่ทำงานแอป

1. เริ่มต้นโดยการสร้างพื้นที่ทำงาน เลือก **พื้นที่ทำงาน** > **สร้างพื้นที่ทำงานแอป** นี่จะเป็นตำแหน่งที่วางเนื้อหาที่แอปพลิเคชันของคุณจะเข้าถึง

    ![สร้างพื้นที่ทำงาน](media/embed-sample-for-your-organization/embed-sample-for-your-organization-020.png)

2. ตั้งชื่อพื้นที่ทำงาน ถ้าชื่อ **ID พื้นที่ทำงาน**ที่ตรงกันไม่สามารถใช้ได้ แก้ไขให้ ID ใหม่มีค่าไม่ซ้ำกัน นี่จะเป็นชื่อของแอปด้วย

    ![ตั้งชื่อพื้นที่ทำงาน](media/embed-sample-for-your-organization/embed-sample-for-your-organization-021.png)

3. คุณมีสองสามตัวเลือกที่จะตั้งค่า ถ้าคุณเลือก**สาธารณะ** ทุกคนในองค์กรคุณสามารถดูสิ่งที่อยู่ในพื้นที่ทำงานได้ ในทางกลับกัน **ส่วนตัว** หมายถึง เฉพาะสมาชิกของพื้นที่ทำงานเท่านั้นที่สามารถดูเนื้อหา

    ![ส่วนตัว/สาธารณะ](media/embed-sample-for-your-organization/embed-sample-for-your-organization-022.png)

    คุณไม่สามารถเปลี่ยนการตั้งค่า สาธารณะ/ส่วนตัว ได้หลังจากคุณสร้างกลุ่มแล้ว

4. คุณยังสามารถเลือกว่าสมาชิกสามารถเข้าถึงแบบ**แก้ไข**ได้หรือ**ดูเท่านั้น**

    ![การเพิ่มสมาชิก](media/embed-sample-for-your-organization/embed-sample-for-your-organization-023.png)

5. ใส่ที่อยู่อีเมลของบุคคลที่คุณต้องการให้เข้าถึงพื้นที่ทำงาน และเลือก**เพิ่ม** คุณไม่สามารถเพิ่มนามแฝงของกลุ่ม เพิ่มได้แค่บุคคลอย่างเดียว

6. ตัดสินใจว่า แต่ละคนเป็นสมาชิกหรือผู้ดูแลระบบ ผู้ดูแลระบบสามารถแก้ไขพื้นที่ทำงาน รวมถึงการเพิ่มสมาชิกคนอื่น ๆ สมาชิกสามารถแก้ไขเนื้อหาในพื้นที่ทำงาน นอกจากว่าพวกเขามีสิทธิ์เข้าถึงแบบดูเท่านั้น ทั้งผู้ดูแลระบบและสมาชิกสามารถเผยแพร่แอป

    ในตอนนี้ คุณสามารถดูพื้นที่ทำงานใหม่แล้ว Power BI จะสร้างพื้นที่ทำงาน และเปิดพื้นที่ทำงานนั้น ซึ่งจะปรากฏขึ้นในรายการของพื้นที่ทำงานที่คุณเป็นสมาชิก เนื่องจากคุณเป็นผู้ดูแล คุณสามารถเลือกจุดไข่ปลา (...) เพื่อกลับมา และทำการเปลี่ยนแปลง เพิ่มสมาชิกใหม่ หรือเปลี่ยนแปลงสิทธิ์ของพวกเขาได้

    ![สร้างพื้นที่ทำงาน](media/embed-sample-for-your-organization/embed-sample-for-your-organization-025.png)

### <a name="create-and-publish-your-reports"></a>สร้าง และเผยแพร่รายงานของคุณ

คุณสามารถสร้างรายงานและชุดข้อมูลของคุณโดยใช้ Power BI Desktop แล้วจึงเผยแพร่รายงานเหล่านั้นไปยังพื้นที่ทำงานของแอป ผู้ใช้ปลายทางที่เผยแพร่รายงาน จำเป็นต้องมีสิทธิ์การใช้งาน Power BI Pro เพื่อเผยแพร่ไปยังพื้นที่ทำงานของแอป

1. ดาวน์โหลดตัวอย่าง[การสาธิตบล็อก](https://github.com/Microsoft/powerbi-desktop-samples)จาก GitHub

    ![ตัวอย่างรายงาน](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026-1.png)

2. เปิดรายงาน PBIX ตัวอย่างใน **Power BI Desktop**

   ![รายงาน PBI บนเดสก์ท็อป](media/embed-sample-for-your-organization/embed-sample-for-your-organization-027.png)

3. เผยแพร่ไปยัง**พื้นที่ทำงานแอป**

   ![รายงาน PBI บนเดสก์ท็อป](media/embed-sample-for-your-organization/embed-sample-for-your-organization-028.png)

    ในตอนนี้ คุณสามารถดูรายงานในบริการของ Power BI แบบออนไลน์

   ![รายงาน PBI บนเดสก์ท็อป](media/embed-sample-for-your-organization/embed-sample-for-your-organization-029.png)

## <a name="embed-your-content-using-the-sample-application"></a>ฝังเนื้อหาของคุณโดยใช้แอปพลิเคชันตัวอย่าง

ทำตามขั้นตอนเหล่านี้เพื่อเริ่มการฝังเนื้อหาของคุณโดยใช้แอปพลิเคชันตัวอย่าง

1. ดาวน์โหลด [ตัวอย่างผู้ใช้ที่เป็นเจ้าของข้อมูล](https://github.com/Microsoft/PowerBI-Developer-Samples) จาก GitHub เพื่อเริ่มต้นใช้งาน  มีแอปพลิเคชัน 3 แอปที่แตกต่างกัน แอปที่หนึ่งคือ [รายงาน](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app) แอปที่สองคือ [แดชบอร์ด](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) และแอปที่สามคือ [ไทล์](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app)  บทความนี้อ้างอิงถึงแอปพลิเคชัน **รายงาน** ขณะที่เรากล่าวถึงขั้นตอนด้านล่าง

    ![ตัวอย่างแอปพลิเคชันของผู้ใช้ที่เป็นเจ้าของข้อมูล](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026.png)

2. เปิดไฟล์ Cloud.config ในแอปพลิเคชันตัวอย่าง มีไม่กี่เขตข้อมูลที่คุณจะต้องใส่เพื่อเรียกใช้แอปพลิเคชันให้สำเร็จ **ClientID** และ **ClientSecret**

    ![ไฟล์ Cloud Config](media/embed-sample-for-your-organization/embed-sample-for-your-organization-030.png)

    กรอกข้อมูล **ClientID** ด้วย **ID แอปพลิเคชัน** จาก **Azure** **ClientID** ให้แอปพลิเคชันใช้ระบุตัวเองสำหรับผู้ใช้ที่คุณร้องขอสิทธิ์

    หากต้องการรับ **ClientID** ให้ทำตามขั้นตอนเหล่านี้:

    ลงชื่อเข้าใช้[พอร์ทัล Azure](https://portal.azure.com)

    ![พอร์ทัลหลัก Azure](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

    ในบานหน้าต่างนำทางด้านซ้าย เลือก**บริการทั้งหมด** และเลือก**การลงทะเบียนแอป**

    ![ค้นหาการลงทะเบียนแอป](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)

    เลือกแอปพลิเคชันที่จำเป็นเพื่อใช้ **ClientID**

    ![การเลือกแอป](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

    คุณควรจะเห็น **ID แอปพลิเคชัน** ที่แสดงในรูปของ GUID ใช้ **ID แอปพลิเคชัน** นี้เป็น **ClientID** สำหรับแอปพลิเคชัน

    ![ClientID](media/embed-sample-for-your-organization/embed-sample-for-your-organization-007.png)

    กรอกข้อมูล **ClientSecret** จากส่วน **คีย์** ของส่วน **การลงทะเบียนแอป** ของคุณใน **Azure**

    หากต้องการรับ **ClientSecret** ให้ทำตามขั้นตอนเหล่านี้:

    ลงชื่อเข้าใช้[พอร์ทัล Azure](https://portal.azure.com)

    ![พอร์ทัลหลัก Azure](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

    ในบานหน้าต่างนำทางด้านซ้าย เลือก**บริการทั้งหมด** และเลือก**การลงทะเบียนแอป**

    ![ค้นหาการลงทะเบียนแอป](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)

    เลือกแอปพลิเคชันที่จำเป็นเพื่อใช้ **ClientSecret**

    ![การเลือกแอป](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

    เลือก **การตั้งค่า**

    ![การตั้งค่า](media/embed-sample-for-your-organization/embed-sample-for-your-organization-038.png)

    เลือก **คีย์**

    ![คีย์](media/embed-sample-for-your-organization/embed-sample-for-your-organization-039.png)

    กรอก **คำอธิบาย** ด้วยชื่อและเลือก **ระยะเวลา** แล้วเลือก **บันทึก** เพื่อรับ **ค่า** สำหรับแอปพลิเคชันของคุณ เมื่อคุณปิด Blade ของ **คีย์** หลังจากบันทึก **ค่าคีย์** เขตข้อมูลของค่าจะแสดงเป็น **_ซ่อน_** เท่านั้น และตอนนี้ คุณจะไม่สามารถเรียกใช้ **ค่าคีย์** ได้ หากคุณสูญเสีย **ค่าคีย์** คุณจะต้องสร้างค่าใหม่ภายใน **พอร์ทัล Azure**

    ![คีย์](media/embed-sample-for-your-organization/embed-sample-for-your-organization-031.png)

     กรอกข้อมูล **groupId** ด้วย **GUID พื้นที่ทำงานของแอป**จาก Power BI

    ![groupId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

    กรอกข้อมูล **reportId** ด้วย **GUID รายงาน**จาก Power BI

    ![reportId](media/embed-sample-for-customers/embed-sample-for-customers-032.png)

3. เรียกใช้แอปพลิเคชัน

    ก่อนอื่น ให้เลือก**เรียกใช้**ใน **Visual Studio**

    ![เรียกใช้แอปพลิเคชัน](media/embed-sample-for-your-organization/embed-sample-for-your-organization-033.png)

    แล้ว เลือก **รับรายงาน**

    ![เลือกเนื้อหา](media/embed-sample-for-your-organization/embed-sample-for-your-organization-034.png)

    ตอนนี้ คุณสามารถดูรายงานในแอปพลิเคชันตัวอย่างได้แล้ว

    ![ดูแอปพลิเคชัน](media/embed-sample-for-your-organization/embed-sample-for-your-organization-035.png)

## <a name="embed-your-content-within-your-application"></a>ฝังเนื้อหาของคุณภายในแอปพลิเคชันของคุณ
ถึงแม้ว่าขั้นตอนการฝังเนื้อหาของคุณสามารถทำได้ด้วย [Power BI REST APIs](https://docs.microsoft.com/rest/api/power-bi/)รหัสตัวอย่างที่อธิบายไว้ในบทความนี้ถูกสร้างด้วย **.NET SDK**

เมื่อต้องรวมในรายงานลงในเว็บแอป คุณต้องใช้ **Power BI REST API** REST API หรือ **Power BI C# SDK** และ **โทเค็นการเข้าถึง** การอนุญาต Azure Active Directory (AD) เพื่อรับรายงาน จากนั้น ให้คุณโหลดรายงานโดยใช้ **โทเค็นการเข้าถึง** เดียวกัน **Power BI Rest API** ให้การเข้าถึงทางการเขียนโปรแกรมสำหรับทรัพยากร **Power BI** เฉพาะ สำหรับข้อมูลเพิ่มเติม ดู [Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/) และ [Power BI JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)

### <a name="get-an-access-token-from-azure-ad"></a>รับโทเค็นการเข้าถึงจาก Azure AD
ภายในแอปพลิเคชันของคุณ คุณจะต้องรับ **โทเค็นการเข้าถึง** จาก Azure AD ก่อนที่คุณสามารถเรียกใช้ Power BI REST API ได้ สำหรับข้อมูลเพิ่มเติม ให้ดู[การรับรองตัวตนผู้ใช้และรับโทเค็นการเข้า Azure AD สำหรับแอป Power BI ของคุณ](get-azuread-access-token.md)

### <a name="get-a-report"></a>รับรายงาน
เมื่อต้องการรับรายงาน **Power BI** คุณต้องใช้การดำเนินการ [รับรายงาน](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) ที่รับรายการของ **รายงาน Power BI** จากรายชื่อของรายงาน คุณสามารถรับรหัสรายงานได้

### <a name="get-reports-using-an-access-token"></a>รับรายงานโดยใช้โทเค็นการเข้าถึง
[Get Reports](https://docs.microsoft.com/rest/api/power-bi/reports/getreports)operation จะส่งคืนค่ารายการของรายงาน จากรายการของรายงาน คุณสามารถรับรายงานชิ้นหนึ่ง

เพื่อเรียกใช้ REST API คุณต้องใส่ส่วนหัว *Authorization* ในรูปแบบ *Bearer {โทเค็นการเข้าถึง}*

#### <a name="get-reports-with-the-rest-api"></a>รับรายงาน ด้วย REST API

นี่คือตัวอย่างรหัสของวิธีการเรียกใช้รายงานที่มี **REST API**

*ตัวอย่างของการรับรายการเนื้อหาที่คุณต้องการฝัง (รายงาน แดชบอร์ด หรือไทล์) จะมีให้ในไฟล์ใน **_Default.aspx.cs_** ใน [แอปพลิเคชันตัวอย่าง](#embed-your-content-using-the-sample-application)*

```csharp
using Newtonsoft.Json;

//Get a Report. In this sample, you get the first Report.
protected void GetReport(int index)
{
    //Configure Reports request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}/Reports",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get Reports response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIReports Reports = JsonConvert.DeserializeObject<PBIReports>(reader.ReadToEnd());

            //Sample assumes at least one Report.
            //You could write an app that lists all Reports
            if (Reports.value.Length > 0)
            {
                var report = Reports.value[index];

                txtEmbedUrl.Text = report.embedUrl;
                txtReportId.Text = report.id;
                txtReportName.Text = report.name;
            }
        }
    }
}

//Power BI Reports used to deserialize the Get Reports response.
public class PBIReports
{
    public PBIReport[] value { get; set; }
}
public class PBIReport
{
    public string id { get; set; }
    public string name { get; set; }
    public string webUrl { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-reports-using-the-net-sdk"></a>รับรายงานโดยใช้.NET SDK
คุณสามารถใช้ .NET SDK เพื่อเรียกดูรายการของรายงานแทนที่จะเรียก REST API โดยตรง นี่คือตัวอย่างรหัสของวิธีแสดงรายการของรายงาน

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It is used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

### <a name="load-a-report-using-javascript"></a>โหลดรายงานโดยใช้ JavaScript
คุณสามารถใช้ JavaScript เพื่อโหลดรายงานลงในองค์ประกอบ div บนเว็บเพจของคุณ

นี่คือตัวอย่างรหัสวิธีการเรียกใช้รายงานจากพื้นที่ทำงานที่ระบุไว้

*ตัวอย่างของการโหลดรายการเนื้อหาไม่ว่าจะเป็นรายงาน แดชบอร์ด หรือไทล์ที่คุณต้องการฝังจะมีให้ในไฟล์ **_Default.aspx_** ใน [แอปพลิเคชันตัวอย่าง](#embed-your-content-using-the-sample-application)*

```javascript
<!-- Embed Report-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a report</div>

            <div>Enter an embed url for a report from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedReportAction" value="Embed Report" />
        </div>

        <div id="reportContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```javascript
window.onload = function () {
    // client side click to embed a selected report.
    var el = document.getElementById("bEmbedReportAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedReporte, false);
    } else {
        el.attachEvent('onclick', updateEmbedReport);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded report if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedReport();
    }
};

// update embed report
function updateEmbedReport() {

    // check if the embed url was selected
    var embedUrl = document.getElementById('tb_EmbedURL').value;
    if (embedUrl === "")
        return;

    // get the access token.
    accessToken = document.getElementById('MainContent_accessTokenTextbox').value;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the report.
    var reportContainer = document.getElementById('reportContainer');

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);

    // report.on will add an event handler which prints to Log window.
    report.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    }
  );
}
```

## <a name="using-a-power-bi-premium-dedicated-capacity"></a>ใช้ความจุเฉพาะของ Power BI Premium

หลังจากที่คุณพัฒนาแอปพลิเคชันของคุณเสร็จแล้ว ก็ถึงเวลาที่จะรองรับพื้นที่ทำงานของแอปคุณด้วยความจุเฉพาะ

### <a name="create-a-dedicated-capacity"></a>สร้างความจุเฉพาะ
โดยการสร้างความจุเฉพาะ คุณสามารถใช้ประโยชน์จากการมีทรัพยากรเฉพาะสำหรับเนื้อหาในพื้นที่ทำงานแอปของคุณ คุณสามารถสร้างความจุเฉพาะโดยใช้ [Power BI Premium](../service-premium.md) ได้

ตารางต่อไปนี้แสดงรายการ Power BI Premium SKU แบบพร้อมใช้งานซึ่งพร้อมใช้งานภายใน [Office 365](../service-admin-premium-purchase.md)

| โหนดของความจุ | วี-คอร์รวม<br/>*(Backend + frontend)* | Backend v-cores | Frontend v-cores | การจำกัดการเชื่อมต่อ DirectQuery/live | หน้าสูงสุดที่แสดงในชั่วโมงที่เรียกใช้มากที่สุด |
| --- | --- | --- | --- | --- | --- |
| EM1 |1 v-cores |.5 v-cores, 10GB RAM |.5 วี-คอร์ |3.75 ต่อวินาที |150-300 |
| EM2 |2 v-cores |1 v-cores, 10GB RAM |1 v-cores |7.5 ต่อวินาที |301-600 |
| EM3 |4 v-cores |2 วี-คอร์ 10GB RAM |2 v-cores |15 ต่อวินาที |601-1,200 |
| P1 |8 v-cores |4 วี-คอร์ 25GB RAM |4 v-cores |30 ต่อวินาที |1,201-2,400 |
| P2 |16 v-cores |8 วี-คอร์ 50GB RAM |8 v-cores |60 ต่อวินาที |2,401-4,800 |
| P3 |32 v-cores |16 วี-คอร์ 100GB RAM |16 v-cores |120 ต่อวินาที |4,801-9600 |
| P4 |64 v-cores |32 v-cores, 200 GB RAM |32 v-cores |240 ต่อวินาที |9601-19200
| P5 |128 v-cores |64 v-cores, 400 GB RAM |64 v-cores |480 ต่อวินาที |19201-38400

*ด้วย **_EM SKUS_** **คุณสามารถ**เข้าถึงเนื้อหาด้วยใบอนุญาต Power BI ฟรีเมื่อพยายามเข้าถึงที่ฝังอยู่ใน**_แอป MS Office_** แต่**คุณไม่สามารถเข้าถึง**เนื้อหาด้วยใบอนุญาต Power BI ฟรี เมื่อใช้ **_Powerbi.com_** หรือใช้ **_Power BI mobile_**.*

*ด้วย **_P SKUs_** **คุณสามารถ**เข้าถึงเนื้อหาด้วยใบอนุญาต Power BI ฟรีเมื่อพยายามเข้าถึงที่ฝังอยู่ใน**_แอป MS Office_** แต่**คุณไม่สามารถเข้าถึง_เนื้อหาด้วยใบอนุญาต Power BI ฟรี เมื่อใช้_** Powerbi.com**_หรือใช้_** Power BI mobile*

### <a name="assign-an-app-workspace-to-a-dedicated-capacity"></a>กำหนดพื้นที่ทำงานของแอปให้กับความจุเฉพาะ

เมื่อคุณสร้างความจุเฉพาะแล้ว คุณสามารถกำหนดพื้นที่ทำงานแอปไปยังความจุเฉพาะนั้นได้ เพื่อทำให้เสร็จสมบูรณ์ ทำตามขั้นตอนเหล่านี้

1. ภายใน**บริการของ Power BI** ขยายพื้นที่ทำงาน และเลือกที่จุดไข่ปลาสำหรับพื้นที่ทำงานที่คุณกำลังใช้เพื่อฝังเนื้อหา แล้วเลือก**แก้ไขพื้นที่ทำงาน**

    ![แก้ไขพื้นที่ทำงาน](media/embed-sample-for-your-organization/embed-sample-for-your-organization-036.png)

2. ขยาย**ขั้นสูง** แล้วเปิดใช้งาน**ความจุเฉพาะ** จากนั้นเลือกความจุเฉพาะที่คุณสร้างขึ้น จากนั้นเลือก**บันทึก**

    ![กำหนดความจุเฉพาะ](media/embed-sample-for-your-organization/embed-sample-for-your-organization-024.png)

3. หลังจากที่คุณเลือก **บันทึก** คุณควรเห็น **ข้าวหลามตัด** ถัดจากชื่อพื้นที่ทำงานแอป

    ![เชื่อมโยงพื้นที่ทำงานของแอปไปยังความจุ](media/embed-sample-for-your-organization/embed-sample-for-your-organization-037.png)

## <a name="admin-settings"></a>การตั้งค่าผู้ดูแลระบบ

ผู้ดูแลระบบส่วนกลางหรือผู้ดูแลระบบบริการ Power BI สามารถเปิดใช้งานความสามารถในการใช้ REST API โดยเปืดหรือปิดสำหรับผู้เช่า ผู้ดูแลระบบ Power BI สามารถตั้งการตั้งค่านี้สำหรับทั้งองค์กรหรือกลุ่มความปลอดภัยแต่ละกลุ่มก็ได้ มีการเปิดใช้งานสำหรับทั้งองค์กรตามค่าเริ่มต้น คุณสามารถทำสิ่งนี้ได้ผ่าน [พอร์ทัลผู้ดูแลระบบของ Power BI](../service-admin-portal.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป
ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีฝังเนื้อหา Power BI ในแอปพลิเคชันโดยใช้ **บัญชีองค์กร Power BI** ของคุณ ในตอนนี้คุณสามารถลองการฝังเนื้อหา Power BI ลงในแอปพลิเคชันโดยใช้แอปได้  คุณยังสามารถลองการฝังเนื้อหา Power BI สำหรับลูกค้าของคุณ

> [!div class="nextstepaction"]
> [ฝังตัวจากแอป](embed-from-apps.md)

> [!div class="nextstepaction"]
>[ฝังสำหรับลูกค้าของคุณ](embed-sample-for-customers.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)

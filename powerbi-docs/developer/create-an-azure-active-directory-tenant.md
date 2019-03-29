---
title: สร้างผู้เช่า Azure Active Directory เพื่อใช้กับ Power BI
description: เรียนรู้วิธีการสร้างผู้เช่า Azure Active Directory (Azure AD) ใหม่เพื่อใช้งานกับแอปพลิเคชันแบบกำหนดเองของคุณโดยใช้ Power BI REST API
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 11/30/2017
ms.openlocfilehash: ec03ba86fdbf57a9898b127aae9b76990837b5ba
ms.sourcegitcommit: 9f31cd41bd92e398717da5a69a074273e8c6f8a6
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/26/2019
ms.locfileid: "58473855"
---
# <a name="create-an-azure-active-directory-tenant-to-use-with-power-bi"></a>สร้างผู้เช่า Azure Active Directory เพื่อใช้กับ Power BI

เรียนรู้วิธีการสร้างผู้เช่า Azure Active Directory (Azure AD) ใหม่เพื่อใช้งานกับแอปพลิเคชันแบบกำหนดเองของคุณโดยใช้ Power BI REST API

ผู้เช่า คือ ตัวแทนขององค์กรภายใน Azure Active Directory ซึ่งเป็นอินสแตนซ์เฉพาะของบริการ Azure AD ที่องค์กรได้รับและเป็นเจ้าของเมื่อลงทะเบียนสมัครใช้บริการระบบคลาวด์ของ Microsoft เช่น Azure, Microsoft Intune หรือ Office 365 ผู้เช่า Azure AD แต่ละรายจะแตกต่างกันและแยกต่างหากจากผู้เช่า Azure AD อื่น ๆ

เมื่อมีผู้เช่า Azure AD คุณสามารถกำหนดแอปพลิเคชันและกำหนดสิทธิ์เพื่อให้แอปพลิเคชันของคุณสามารถใช้ Power BI REST API ได้

องค์กรของคุณอาจมีผู้เช่า Azure AD ที่คุณสามารถใช้สำหรับแอปพลิเคชันของคุณอยู่แล้ว คุณสามารถใช้ผู้เช่านั้นสำหรับความต้องการแอปพลิเคชันของคุณ หรือคุณสามารถสร้างผู้เช่าใหม่สำหรับแอปพลิเคชันของคุณโดยเฉพาะได้ บทความนี้กล่าวถึ่งวิธีการสร้างผู้เช่าใหม่

## <a name="create-an-azure-active-directory-tenant"></a>สร้างผู้เช่า Azure Active Directory

เพื่อรวม Power BI ลงในแอปพลิเคชันแบบกำหนดเองของคุณ คุณจำเป็นต้องกำหนดแอปพลิเคชันภายใน Azure AD ในการทำเช่นนั้น คุณต้องมีไดเรกทอรีภายใน Azure AD นี่คือผู้เช่าของคุณ ถ้าองค์กรของคุณยังไม่มีผู้เช่า เนื่องจากพวกเขาไม่ได้ใช้ Power BI หรือ Office 365 [คุณจะต้องสร้างขึ้นมาหนึ่งราย](https://docs.microsoft.com/azure/active-directory/develop/active-directory-howto-tenant) นอกจากนี้ คุณยังอาจต้องสร้างขึ้นมาหนึ่งรายถ้าไม่ต้องการให้แอปพลิเคชันของคุณผสมปะปนกับผู้เช่าในองค์กรของคุณ ซึ่งทำให้คุณสามารถเก็บสิ่งต่าง ๆ แยกออกมาต่างหากได้

หรือคุณอาจเพียงแค่ต้องการสร้างผู้เช่าเพื่อทำการทดสอบ

เมื่อต้องสร้างผู้เช่า Azure AD ใหม่ ให้ทำสิ่งต่อไปนี้

1. เรียกดู [พอร์ทัล Azure](https://portal.azure.com)และลงชื่อเข้าใช้ด้วยบัญชีผู้ใช้ที่มีการสมัครใช้งาน Azure

2. เลือก **ไอคอนเครื่องหมายบวก (+)**  และค้นหา *Azure Active Directory*

    ![ไอคอนบวก (+)](media/create-an-azure-active-directory-tenant/new-directory.png)

3. เลือก **Azure Active Directory** ในผลลัพธ์การค้นหา

    ![ค้นหา AAD](media/create-an-azure-active-directory-tenant/new-directory2.png)

4. เลือก **สร้าง**

5. ใส่ **ชื่อสำหรับองค์กร** พร้อมด้วย**ชื่อโดเมนเริ่มต้น** แล้วเลือก **สร้าง** การดำเนินการนี้จะสร้างไดเรกทอรีของคุณ

    ![องค์กรและโดเมน](media/create-an-azure-active-directory-tenant/organization-and-domain.png)

   > [!NOTE]
   > โดเมนเริ่มต้นของคุณจะเป็นส่วนหนึ่งของ onmicrosoft.com คุณสามารถเพิ่มชื่อโดเมนอื่น ๆ ได้ในภายหลัง ไดเรกทอรีของผู้เช่าอาจมีได้หลายโดเมนที่กำหนดไว้

6. หลังจากการสร้างไดเรกทอรีของคุณเสร็จสมบูรณ์ เลือกกล่องข้อมูลเพื่อจัดการไดเรกทอรีใหม่ของคุณ

ไดเรกทอรีของคุณจะถูกสร้างขึ้นในขณะนี้ ต่อไป เราจะต้องการเพิ่มผู้ใช้ให้กับผู้เช่า

## <a name="create-some-users-in-your-azure-active-directory-tenant"></a>สร้างผู้ใช้บางรายในผู้เช่า Azure Active Directory ของคุณ

ในตอนนี้่เรามีไดเรกทอรีแล้ว มาสร้างผู้ใช้อย่างน้อยสองรายกัน ซึ่งรายหนึ่งจะเป็นผู้ดูแลระบบส่วนกลางสำหรับผู้เช่าและอีกรายหนึ่งจะเป็นผู้ใช้ต้นแบบสำหรับฝังของเรา สิ่งนี้จะคล้ายกับบัญชีบริการ

1. ภายในพอร์ทัล Azure ตรวจสอบให้แน่ใจว่า เรากำลังอยู่บน Azure Active Directory ที่ปรากฎขึ้นทางด้านข้าง

    ![](media/create-an-azure-active-directory-tenant/aad-flyout.png)

    ถ้าไม่เป็นเช่นนั้น เลือกไอคอน Azure Active Directory จากแถบบริการทางด้านซ้าย

    ![](media/create-an-azure-active-directory-tenant/aad-service.png)
2. ภายใต้ **จัดการ** เลือก **ผู้ใช้และกลุ่ม**

    ![](media/create-an-azure-active-directory-tenant/users-and-groups.png)
3. เลือก **ผู้ใช้ทั้งหมด** แล้วเลือก **+ ผู้ใช้ใหม่**
4. ใส่ชื่อและชื่อผู้ใช้สำหรับผู้ใช้รายนี้ ซึ่งจะเป็นผู้ดูแลระบบส่วนกลางสำหรับผู้เช่าของคุณ นอกจากนี้ คุณจะต้องการเปลี่ยน **บทบาทไดเรกทอรี**ให้เป็น*ผู้ดูแลระบบส่วนกลาง* คุณยังสามารถแสดงรหัสผ่านชั่วคราวได้ เมื่อคุณทำเสร็จแล้ว เลือก **ถัดไป**

    ![](media/create-an-azure-active-directory-tenant/global-admin.png)

5. คุณจะต้องทำสิ่งเดียวกันนี้้อีกครั้งสำหรับผู้ใช้ทั่วไปในผู้เช่าของคุณ ซึ่งยังสามารถใช้สำหรับบัญชีสำหรับฝังต้นแบบของคุณด้วย ในเวลานี้ สำหรับ**บทบาทไดเรกทอรี** เราจะปล่อยให้เป็น *ผู้ใช้* ตรวจสอบให้แน่ใจว่าได้จดรหัสผ่านแล้ว แล้วเลือก **สร้าง**

    ![](media/create-an-azure-active-directory-tenant/pbiembed-user.png)
6. ลงทะเบียนสมัครใช้สำหรับ Power BI ด้วยบัญชีผู้ใช้ที่คุณสร้างในขั้นตอนที่ 5 คุณสามารถทำเช่นนั้นได้โดยไปที่ [powerbi.com](https://powerbi.microsoft.com/get-started/) และเลือก **ลองฟรี** ภายใต้ *Power BI - การทำงานร่วมกันและการแชร์บนระบบคลาวด์*

    ![](media/create-an-azure-active-directory-tenant/try-powerbi-free.png)

    เมื่อคุณลงทะเบียนสมัครใช้ คุณจะถูกพร้อมท์ให้ลองใช้ Power BI Pro ฟรี 60 วัน คุณสามารถเลือกอย่างนั้นเพื่อเป็นผู้ใช้แบบ Pro ได้ ในตอนนี้ คุณยังสามารถเริ่มต้นพัฒนาโซลูชันแบบฝังได้ถ้าเป็นสิ่งที่คุณกำลังค้นหา

   > [!NOTE]
   > ตรวจสอบให้แน่ใจว่า คุณลงทะเบียนสมัครใช้ด้วยอีเมลแอดเดรสที่คุณให้บัญชีผู้ใช้

## <a name="next-steps"></a>ขั้นตอนถัดไป

หลังจากที่มีผู้เช่า Azure AD แล้ว คุณสามารถใช้ผู้เช่านี้เพื่อทดสอบรายการภายใน Power BI และ/หรือคุณสามารถดำเนินต่อไปเพื่อฝังแดชบอร์ดและรายงาน Power BI ในแอปพลิเคชันของคุณ สำหรับข้อมูลเกี่ยวกับวิธีฝังรายการ ดู [วิธีฝังแดชบอร์ด รายงานและไทล์ Power BI ของคุณ](embedding-content.md)

[ไดเรกทอรี Azure AD คืออะไร](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)  
[วิธีการรับผู้เช่า Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-howto-tenant)  

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)

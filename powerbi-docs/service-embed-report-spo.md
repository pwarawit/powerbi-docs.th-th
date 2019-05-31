---
title: ฝังด้วยส่วนเว็บรายงานใน SharePoint Online
description: ด้วยส่วยรายงานเว็บ Power BI ใหม่ สำหรับ SharePoint Online คุณสามารถฝังรายงาน Power BI แบบโต้ตอบได้อย่างง่ายดายในหน้า SharePoint Online
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 05/16/2019
ms.openlocfilehash: c8789d47ed1b67f9fd6808865514120457a29dfe
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051266"
---
# <a name="embed-with-report-web-part-in-sharepoint-online"></a>ฝังด้วยส่วนเว็บรายงานใน SharePoint Online

ด้วยส่วยรายงานเว็บ Power BI ใหม่ สำหรับ SharePoint Online คุณสามารถฝังรายงาน Power BI แบบโต้ตอบได้อย่างง่ายดายในหน้า SharePoint Online

เมื่อใช้ใหม่**ฝังใน SharePoint Online**ตัวเลือก รายงานที่ฝังตัวมีเต็มรูปแบบความปลอดภัย ดังนั้นคุณสามารถสร้างพอร์ทัลภายในที่ปลอดภัย

## <a name="requirements"></a>ข้อกำหนด

สำหรับ**ฝังใน SharePoint Online**รายงานเพื่อทำงาน จำเป็นต้องต่อไปนี้:

* สิทธิ์การใช้งาน Power BI Pro หรือ[Power BI Premium ความจุ (EM หรือ P SKU)](service-premium-what-is.md)ด้วยสิทธิ์การใช้งาน Power BI
* Power BI web part สำหรับ SharePoint Online จำเป็นต้องใช้[หน้าที่ทันสมัย](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b)

## <a name="embed-your-report"></a>ฝังรายงานของคุณ
เมื่อต้องฝังรายงานของคุณลงใน SharePoint Online คุณจำเป็นต้องรับ URL ของรายงาน และใช้กับ SharePoint Online ของ Power BI web part ใหม่

### <a name="get-a-report-url"></a>รับ URL รายงาน

1. ภายใน Power BI ดูรายงาน

2. เลือกคำ**แฟ้ม**เมนูดรอปดาวน์ แล้ว เลือก**ฝังใน SharePoint Online**

    ![เมนูไฟล์](media/service-embed-report-spo/powerbi-file-menu.png)

3. คัดลอก URL ของรายงานจากกล่องโต้ตอบ

    ![ลิงก์ที่ฝังไว้](media/service-embed-report-spo/powerbi-embed-link-sharepoint.png)

### <a name="add-the-power-bi-report-to-a-sharepoint-online-page"></a>เพิ่มรายงาน Power BI ลงในหน้า SharePoint Online

1. เปิดหน้าเป้าหมายใน SharePoint Online และเลือก**แก้ไข**

    ![หน้าแก้ไข SP](media/service-embed-report-spo/powerbi-sharepoint-edit-page.png)

    หรือ ใน Sharepoint Online เลือก **+ ใหม่**เพื่อสร้างหน้าไซต์ที่ทันสมัยใหม่

    ![หน้าใหม่ SP](media/service-embed-report-spo/powerbi-sharepoint-new-page.png)

2. เลือกคำ **+** ดรอปดาวน์แล้ว เลือกการ**Power BI**

    ![web part ใหม่ของ SP](media/service-embed-report-spo/powerbi-sharepoint-new-web-part.png)

3. เลือก**เพิ่มรายงาน**

    ![รายงานใหม่ของ SP](media/service-embed-report-spo/powerbi-sharepoint-new-report.png)  

4. วาง URL ของรายงานก่อนหน้านี้คัดลอกไปยัง**ลิงก์รายงาน Power BI**บานหน้าต่าง รายงานโหลดโดยอัตโนมัติ

    ![คุณสมบัติ web part ใหม่ของ SP](media/service-embed-report-spo/powerbi-sharepoint-new-web-part-properties.png)

5. เลือก**เผยแพร่**เพื่อทำการเปลี่ยนแปลงการมองเห็นให้ผู้ใช้ SharePoint Online ของคุณ

    ![รายงาน SP โหลดแล้ว](media/service-embed-report-spo/powerbi-sharepoint-report-loaded.png)

## <a name="grant-access-to-reports"></a>อนุญาตการเข้าถึงรายงาน

ฝังรายงานใน SharePoint Online ไม่โดยอัตโนมัติให้ผู้ใช้สิทธิ์ในการดูรายงาน - คุณจำเป็นต้องตั้งค่ามุมมองสิทธิ์ใน Power BI

> [!IMPORTANT]
> ให้ตรวจสอบให้แน่ใจว่าว่าใครสามารถดูรายงานภายใน Power BI service และอนุญาตให้เข้าถึงสิ่งที่ไม่ได้อยู่ในรายการ

มีสองวิธีในการเข้าถึงรายงานใน Power BI วิธีแรก ถ้าคุณกำลังใช้กลุ่ม Office 365 เพื่อสร้างไซต์ทีม SharePoint Online คือ รายการผู้ใช้เป็นสมาชิกของการ**พื้นที่ทำงานแอปภายในบริการ Power BI**และ**หน้า SharePoint** สำหรับข้อมูลเพิ่มเติม ดูวิธีการ[จัดการพื้นที่ทำงานแอป](service-manage-app-workspace-in-power-bi-and-office-365.md)

วิธีสองคือการ ฝังรายงานภายในแอป และแชร์โดยตรงกับผู้ใช้:  

1. ผู้เขียน (จำเป็นต้องเป็นผู้ใช้ Pro) สร้างรายงานในพื้นที่ทำงานแอป การแชร์กับ**ผู้ใช้ฟรีของ Power BI**พื้นที่ทำงานแอปจำเป็นต้องตั้งค่าเป็นการ**พื้นที่ทำงาน Premium**

2. ผู้เขียนเผยแพร่แอป และติดตั้งได้ ผู้เขียนจำเป็นต้องทำให้แน่ใจว่าได้ติดตั้งแอปสามารถเข้าถึง URL ของรายงานที่ถูกใช้เพื่อฝังใน SharePoint Online

3. ในขั้นนี้ ผู้ใช้ทั้งหมดจำเป็นต้องติดตั้งแอปเช่นเดียวกัน คุณยังสามารถใช้**ติดตั้งแอปโดยอัตโนมัติ**คุณลักษณะ ซึ่งคุณสามารถเปิดใช้งานในการ[พอร์ทัลผู้ดูแลระบบ Power BI](service-admin-portal.md)เพื่อให้แอติดตั้งล่วงหน้าสำหรับผู้ใช้ปลายทางได้

   ![ติดตั้งแอปโดยอัตโนมัติ](media/service-embed-report-spo/install-app-automatically.png)

4. ผู้เขียนเปิดแอปและไปยังรายงาน

5. ผู้เขียนคัดลอก URL ของรายงานแบบฝังตัวจากรายงานติดตั้งแอป **อย่าใช้ URL ของรายงานต้นฉบับจากพื้นที่ทำงานแอป**

6. สร้างไซต์ทีมใหม่ใน SharePoint Online

7. เพิ่ม URL ของรายงานก่อนหน้านี้คัดลอกไปยัง web part Power BI

8. เพิ่มผู้ใช้ปลายทางและ/หรือกลุ่มทั้งหมดที่จะใช้ข้อมูลบนหน้า SharePoint Online และในแอป Power BI ที่คุณสร้างขึ้น

    > [!NOTE]
    > **ผู้ใช้หรือกลุ่มจำเป็นต้องเข้าถึงทั้งหน้า SharePoint Online และรายงานในแอป Power BI เพื่อดูรายงานบนหน้า SharePoint**

ในตอนนี้ ผู้ใช้ปลายทางสามารถไปยังไซต์ทีมใน SharePoint Online และดูรายงานบนหน้าได้แล้ว

## <a name="multi-factor-authentication"></a>การรับรองตัวตนแบบหลายปัจจัย

ถ้าสภาพแวดล้อม Power BI ของคุณทำให้คุณต้องลงชื่อเข้าใช้ด้วยการใช้การรับรองความถูกต้องแบบหลายปัจจัย คุณอาจถูกขอให้ลงชื่อเข้าใช้ด้วยอุปกรณ์ความปลอดภัยเพื่อยืนยันข้อมูลประจำตัวของคุณ ซึ่งเกิดขึ้นถ้าคุณไม่ได้ไม่ลงชื่อเข้าใช้ SharePoint Online โดยใช้การรับรองความถูกต้องแบบหลายปัจจัย แต่อุปกรณ์ความปลอดภัยเพื่อตรวจสอบบัญชีผู้ใช้จำเป็นต้องมีสภาพแวดล้อม Power BI ของคุณ

> [!NOTE]
> 2.0 Azure Active Directory ไม่สนับสนุนการรับรองความถูกต้องแบบหลายปัจจัย - ผู้ใช้จะเห็นข้อผิดพลาด ถ้าผู้ใช้ลงชื่อเข้าใช้ SharePoint Online อีกครั้งโดยใช้อุปกรณ์ความปลอดภัยของพวกเขา พวกเขาอาจสามารถดูรายงานได้

## <a name="web-part-settings"></a>ตั้งค่า web part

ด้านล่างคือการตั้งค่าที่คุณสามารถปรับเปลี่ยนสำหรับ Power BI web part สำหรับ SharePoint Online

![คุณสมบัติ web part ใหม่ของ SP](media/service-embed-report-spo/powerbi-sharepoint-web-part-properties.png)

| คุณสมบัติ | คำอธิบาย |
| --- | --- |
| ชื่อหน้า |ตั้งค่าหน้าเริ่มต้นของ web part เลือกค่าจากรายการแบบดรอปดาวน์ ถ้าไม่มีการแสดงหน้า รายงานของคุณมีหน้าหนึ่ง หรือ URL ที่คุณวางมีชื่อหน้า ลบส่วนของรายงานจาก URL เมื่อต้องเลือกหน้าใดหน้าหนึ่ง |
| แสดง |ปรับปรุงวิธีรายงานพอดีกับหน้า SharePoint Online |
| แสดงบานหน้าต่างนำทาง |แสดงหรือซ่อนบานหน้าหน้าต่างนำทาง |
| แสดงบานหน้าต่างตัวกรอง |แสดงหรือซ่อนบานหน้าต่างตัวกรอง |

## <a name="reports-that-do-not-load"></a>รายงานที่โหลดไม่ได้

ถ้ารายงานของคุณไม่โหลดภายใน web part Power BI คุณอาจเห็นข้อความต่อไปนี้:

![เนื้อหานี้ไม่พร้อมใช้งานข้อความ](media/service-embed-report-spo/powerbi-sharepoint-report-not-found.png)

มีเหตุผลโดยทั่วไปสำหรับข้อความนี้สองตัว

1. คุณไม่มีสิทธิ์เข้าถึงรายงาน
2. รายงานถูกลบ

ติดต่อเจ้าของหน้า SharePoint Online เพื่อช่วยแก้ไขปัญหา

## <a name="licensing"></a>สิทธิ์การใช้งาน

การที่ผู้ใช้ดูรายงานใน SharePoint ต้องมี**ใบอนุญาตใช้งาน Power BI Pro** หรือไม่เช่นนั้นเนื้อหาต้องอยู่ในพื้นที่ทำงานที่อยู่ใน **[ความจุพรีเมียมของ Power BI (EM หรือ P SKU)](service-admin-premium-purchase.md)**

## <a name="known-issues-and-limitations"></a>ปัญหาและขีดจำกัดที่ทราบแล้ว

* ข้อผิดพลาด: "เกิดข้อผิดพลาด โปรดลองออกจากระบบ และย้อนกลับมา แล้วเข้ามาเยี่ยมชมหน้านี้อีกครั้ง ID สหสัมพันธ์: ไม่ได้กำหนด http สถานะการตอบสนอง: 400 รหัสผิดพลาดของเซิร์ฟเวอร์ 10001 ข้อความ: รีเฟรชโทเค็นหายไป
  
  ถ้าคุณได้รับข้อผิดพลาดนี้ โปรดทำตามขั้นตอนการแก้ปัญหาขั้นตอนใดขั้นตอนหนึ่งด้านล่าง
  
  1. ลงชื่อออกจาก SharePoint และลงชื่อกลับเข้าใช้ ตรวจสอบให้แน่ใจว่าปิดหน้าต่างเบราว์เซอร์ทั้งหมดก่อนที่ลงชื่อกลับเข้าใช้

  2. ถ้าบัญชีผู้ใช้ของคุณจำเป็นต้องรับรองความถูกต้องแบบหลายปัจจัย (MFA), แล้วลงชื่อเข้าใช้ SharePoint โดยใช้อุปกรณ์ MFA (แอปโทรศัพท์ สมาร์ทการ์ด และอื่น ๆ)
  
  3. บัญชีผู้ใช้ Azure B2B Guest ไม่ได้รับการสนับสนุน ผู้ใช้เห็นโลโก้ Power BI ที่แสดงส่วนที่กำลังโหลด แต่ไม่ได้แสดงรายงาน

* Power BI ไม่รองรับภาษาเดียวกับที่ SharePoint Online รองรับ ผลที่ได้คือคุณอาจไม่เห็นการแปลที่เหมาะสมภายในรายงานแบบฝังตัว

* คุณอาจพบปัญหาถ้าใช้ Internet Explorer 10 คุณสามารถค้นหาที่[เบราว์เซอร์ที่รองรับ Power BI](consumer/end-user-browsers.md)และสำหรับ[Office 365](https://products.office.com/office-system-requirements#Browsers-section)ได้

* Web part Power BI จะไม่พร้อมใช้งานสำหรับ [ระบบคลาวด์แห่งชาติ](https://powerbi.microsoft.com/clouds/)

* SharePoint Server แบบคลาสสิกไม่ได้รับการสนับสนุนด้วย web part นี้

* [ตัวกรอง URL](service-url-filters.md) จะไม่ได้รับการสนับสนุนด้วย SPO web part

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [อนุญาตหรือป้องกันไม่ให้สร้างไซต์แบบสมัยใหม่โดยผู้ใช้ปลายทาง](https://support.office.com/article/Allow-or-prevent-creation-of-modern-site-pages-by-end-users-c41d9cc8-c5c0-46b4-8b87-ea66abc6e63b)  
* [สร้างและกระจายแอปฯใน Power BI](service-create-distribute-apps.md)  
* [แชร์แดชบอร์ดกับเพื่อนร่วมงานและคนอื่นๆ](service-share-dashboards.md)  
* [Power BI Premium คืออะไร?](service-premium-what-is.md)
* [ฝังรายงานในพอร์ทัลความปลอดภัยหรือเว็บไซต์](service-embed-secure.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](http://community.powerbi.com/)
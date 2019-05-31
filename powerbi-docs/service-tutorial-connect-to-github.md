---
title: 'บทช่วยสอน: เชื่อมต่อกับ repo GitHub ด้วย Power BI'
description: ในบทช่วยสอนนี้ คุณจะเชื่อมต่อกับข้อมูลจริงในบริการ GitHub ด้วย Power BI และ Power BI จะสร้างแดชบอร์ดและรายงานโดยอัตโนมัติ
author: maggiesMSFT
manager: kfile
ms.reviewer: SarinaJoan
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 04/19/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 3aeb1fc16ae200399125a2366a8993d45aad34c4
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578628"
---
# <a name="tutorial-connect-to-a-github-repo-with-power-bi"></a>บทช่วยสอน: เชื่อมต่อกับ repo GitHub ด้วย Power BI
ในบทช่วยสอนนี้ คุณจะเชื่อมต่อกับข้อมูลจริงในบริการ GitHub ด้วย Power BI และ Power BI จะสร้างแดชบอร์ดและรายงานโดยอัตโนมัติ คุณเชื่อมต่อกับเก็บสาธารณะเนื้อหา Power BI (หรือที่เรียกว่าการ*repo*) และดูคำตอบของคำถามเช่น: มีบุคคลกี่คนให้การสนับสนุนเนื้อหาสาธารณะของ Power BI ใครให้การสนับสนุนมากที่สุด วันใดในสัปดาห์ที่มีการสนับสนุนมากที่สุด และคำถามอื่น ๆ 

![รายงาน GitHub ใน Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-punch-card.png)

ในบทช่วยสอนนี้ คุณจะทำขั้นตอนต่อไปนี้ให้เสร็จสมบูรณ์:

> [!div class="checklist"]
> * ลงทะเบียนบัญชี GitHub ถ้าคุณยังไม่มีบัญชี 
> * ลงชื่อเข้าใช้บัญชี Power BI ของคุณ หรือลงทะเบียน ถ้าคุณยังไม่มีบัญชี
> * เปิดบริการ Power BI
> * ค้นหาแอป GitHub
> * ใส่ข้อมูลสำหรับ Repo GitHub สาธารณะของ Power BI
> * ดูแดชบอร์ดและรายงานด้วยข้อมูล GitHub
> * เพิ่มพื้นที่ทรัพยากรโดยการลบแอป

ถ้าคุณไม่ได้ลงทะเบียน Power BI ให้[ลงทะเบียนรุ่นทดลองใช้ฟรี](https://app.powerbi.com/signupredirect?pbi_source=web)ก่อนที่คุณจะเริ่มต้นใช้งาน

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

เมื่อต้องการเรียนรู้บทช่วยสอนนี้ให้เสร็จสมบูรณ์ คุณต้องมีบัญชี GitHub ถ้าคุณยังไม่มีบัญชี 

- ลงทะเบียนสำหรับการ[บัญชี GitHub](https://docs.microsoft.com/contribute/get-started-setup-github)


## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. ลงชื่อเข้าใช้บริการ Power BI (https://app.powerbi.com) 
2. ในบานหน้าต่างนำทางด้านซ้าย ให้เลือก **แอป** แล้วเลือก **รับแอป**
   
   ![รับแอปใน Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial.png) 

3. เลือก**แอ**ชนิด**GitHub**ในกล่องค้นหา > **รับทันที**
   
   ![รับ GitHub ใน Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-app-source.png) 

4. ใน**ติดตั้งแอป Power BI นี้ใช่ไหม**เลือก**ติดตั้ง**
5. ใน**แอปของคุณใหม่พร้อม**เลือก**ไปยังแอ**
6. ใน**เริ่มต้นใช้งานแอปของคุณใหม่**เลือก**เชื่อมต่อข้อมูล**

    ![เริ่มต้นใช้งานแอปใหม่ของคุณ](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

7. ป้อนชื่อที่เก็บและเจ้าของที่เก็บ Repo URL สำหรับ Repo นี้คือ https://github.com/MicrosoftDocs/powerbi-docs ดังนั้น **เจ้าของที่เก็บ**จะเป็น **MicrosoftDocs** และ**ที่เก็บ**จะเป็น **powerbi-docs** 
   
    ![ชื่อ Repo GitHub ใน Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect.png)

5. ป้อนข้อมูลประจำตัว GitHub ที่คุณสร้างขึ้น Power BI อาจข้ามขั้นตอนนี้ ถ้าคุรลงชื่อเข้าใช้ GitHub ในเบราว์เซอร์ของคุณ 

6. สำหรับ**วิธีการรับรองความถูกต้อง**เก็บ**oAuth2**เลือก\> **ลงชื่อเข้าใช้**

7. ทำตามหน้าจอการรับรองความถูกต้อง GitHub มอบสิทธิ์ Power BI ให้กับข้อมูล GitHub
   
   ในตอนนี้ Power BI สามารถเชื่อมต่อกับ GitHub และเชื่อมต่อกับข้อมูล  ข้อมูลจะถูกรีเฟรชวันละหนึ่งครั้ง

8. หลังจาก Power BI นำเข้าข้อมูล คุณเห็นเนื้อหาของพื้นที่ทำงาน GitHub ของคุณใหม่ 
9. เลือกลูกศรถัดจากชื่อพื้นที่ทำงานในแถบนำทางด้านซ้าย คุณเห็นพื้นที่ทำงานประกอบด้วยแดชบอร์ดและรายงาน 

    ![ในบานหน้าต่างนำทางด้านซ้าย](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav-expanded.png)

10. เลือกจุดไข่ปลา (...) ถัดจากชื่อแดชบอร์ด > **เปลี่ยนชื่อ** > ชนิด**แดชบอร์ด GitHub**
 
    ![ไทล์ GitHub ใน Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav.png) 

8. เลือกไอคอนนำทางส่วนกลางเพื่อลดการนำทางด้านซ้าย เพื่อให้มีพื้นที่ว่างเพิ่มเติม

    ![ไอคอนการนำทางส่วนกลาง](media/service-tutorial-connect-to-github/power-bi-global-navigation-icon.png)

10. เลือกแดชบอร์ด GitHub ของคุณ
    
    แดชบอร์ด GitHub ประกอบด้วยข้อมูลสด ดังนั้นค่าคุณเห็นอาจแตกต่างกัน

    ![แดชบอร์ด GitHub ใน Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-new-dashboard.png)

    

## <a name="ask-a-question"></a>ถามคำถาม

1. วางเคอร์เซอร์ของคุณ**ถามคำถามเกี่ยวกับข้อมูลของคุณ** Power BI ข้อเสนอ**คำถามเพื่อให้คุณเริ่มต้น** 

1. เลือก**จำนวนผู้ใช้มี**
 
    ![จำนวนผู้ใช้มี](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-qna-how-many-users.png)

13. ในระหว่าง**กี่**และ**ผู้ใช้จะมี**ชนิด**ดึงการร้องขอต่อ** 

     Power BI สร้างแผนภูมิแท่งแสดงจำนวนการร้องขอการดึงข้อมูลสำหรับแต่ละบุคคล

    ![จำนวนคำขอดึงข้อมูลต่อผู้ใช้มี](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-qna-how-many-prs.png)


13. เลือกหมุดเพื่อปักหมุดไปยังแดชบอร์ด แล้ว**ออกจากถามตอบ**

## <a name="view-the-github-report"></a>ดูรายงาน GitHub 

1. ในแดชบอร์ด GitHub เลือกแผนภูมิคอลัมน์**ดึงคำขอตามเดือน**เพื่อเปิดรายงานที่เกี่ยวข้อง

    ![คำขอดึงข้อมูลตามเดือนแผนภูมิคอลัมน์](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-column-chart.png)

2. เลือกชื่อผู้ใช้ในการ**คำขอดึงข้อมูลทั้งหมดตามผู้ใช้**แผนภูมิ ในตัวอย่างนี้ เราเห็นส่วนใหญ่ของชั่วโมงของพวกเขาได้ในเดือนกุมภาพันธ์

    ![การเน้นรายงาน GitHub ใน Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-cross-filter-total-prs.png)

3. เลือกแท็บ **บัตรเจาะรู** เพื่อดูหน้าถัดไปในรายงาน 
 
    ![บัตรเจาะรูของรายงาน GitHub ใน Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-tues-3pm.png)

    สวัสดิการวันอังคารเวลา 3 pm คือ เวลาทั่วไปมากที่สุดและวันของสัปดาห์สำหรับ*ยอมรับ*เมื่อผู้ใช้เช็คอินงานของพวกเขา

## <a name="clean-up-resources"></a>เพิ่มพื้นที่ทรัพยากร

ในตอนนี้ คุณสำเร็จบทช่วยสอนแล้ว คุณสามารถลบแอป GitHub ได้ 

1. ในแถบนำทางด้านซ้าย ให้เลือก **แอป**
2. วางเมาส์เหนือไทล์ GitHub และเลือกถังขยะ **ลบ**

    ![ลบแอป GitHub](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-delete.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป

ในบทช่วยสอนนี้ คุณได้เชื่อมต่อกับ Repo สาธารณะของ GitHub และข้อมูลที่ได้รับ ซึ่ง Power BI ได้จัดรูปแบบในแดชบอร์ดและรายงาน คุณได้ตอบคำถามบางอย่างเกี่ยวกับข้อมูลโดยการสำรวจแดชบอร์ดและรายงาน ในตอนนี้ คุณสามารถเรียนรู้เพิ่มเติมเกี่ยวกับการเชื่อมต่อกับบริการอื่นๆ เช่น Salesforce, Microsoft Dynamics และ Google Analytics 
 
> [!div class="nextstepaction"]
> [เชื่อมต่อกับบริการออนไลน์ที่คุณใช้](service-connect-to-services.md)



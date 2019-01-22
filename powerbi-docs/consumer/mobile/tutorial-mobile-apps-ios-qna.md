---
title: 'บทช่วยสอน: ถามคำถามกับ Q&A นักวิเคราะห์เสมือนในแอป iOS'
description: ในบทช่วยสอนนี้ ถามคำถามเกี่ยวกับข้อมูลตัวอย่างในคำพูดของคุณเอง กับนักวิเคราะห์เสมือนของถามตอบ ในแอปมือถือ Power BI บนอุปกรณ์ iOS ของคุณ
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: tutorial
ms.date: 11/16/2018
ms.author: mshenhav
ms.openlocfilehash: 74949d2b71dbdca46bbda9623a962616a72af45e
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54282943"
---
# <a name="tutorial-ask-questions-about-your-data-with-the-qa-virtual-analyst-in-the-power-bi-ios-apps"></a>บทช่วยสอน: ถามเกี่ยวกับข้อมูลของคุณกับ Q&A นักวิเคราะห์เสมือนในแอป Power BI iOS

วิธีง่ายที่สุดในการเรียนรู้เกี่ยวกับข้อมูลของคุณ คือ การถามคำถามเกี่ยวกับข้อมูลของคุณโดยใช้ถ้อยคำของคุณเอง ในบทความนี้ คุณจะถามคำถาม และดูข้อมูลเชิงลึกที่แนะนำเกี่ยวกับข้อมูลตัวอย่าง กับนักวิเคราะห์เสมือนของถามตอบ ในแอปมือถือ Microsoft Power BI บน iPad, iPhone และ iPod Touch ของคุณ 

นำไปใช้กับ:

| ![iPhone](./media/tutorial-mobile-apps-ios-qna/iphone-logo-50-px.png) | ![iPad](./media/tutorial-mobile-apps-ios-qna/ipad-logo-50-px.png) |
|:--- |:--- |
| iPhone |iPad |

นักวิเคราะห์เสมือนของถามตอบ เป็นประสบการณ์การสนทนาข่าวกรองธุรกิจ ที่เข้าถึงข้อมูลการถามตอบเบื้องต้นในบริการของ Power BI [(https://powerbi.com)](https://powerbi.com) ซึ่งแนะนำข้อมูลเชิงลึก และคุณสามารถพิมพ์ หรือพูดคำถามของคุณเอง

![นักวิเคราะห์เสมือนของถามตอบสำหรับยอดขายสูงสุด](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-intro.png)

ในบทช่วยสอนนี้ คุณจะได้:

> [!div class="checklist"]
> * ติดตั้งแอป Power BI บนมือถือสำหรับ iOS
> * ดาวน์โหลดรายงานและแดชบอร์ดตัวอย่าง Power BI
> * ดูข้อมูลเชิงลึกที่แนะนำโดยแอปสำหรับอุปกรณ์เคลื่อนที่

ถ้าคุณไม่ได้ลงทะเบียน Power BI ให้[ลงทะเบียนรุ่นทดลองใช้ฟรี](https://app.powerbi.com/signupredirect?pbi_source=web)ก่อนที่คุณจะเริ่มต้นใช้งาน

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

### <a name="install-the-power-bi-for-ios-app"></a>ติดตั้งแอป Power BI สำหรับ iOS
[ดาวน์โหลดแอป iOS](http://go.microsoft.com/fwlink/?LinkId=522062 "ดาวน์โหลดแอป iPhone") จาก Apple App Store ไปยัง iPad, iPhone หรือ iPod Touch ของคุณ

เวอร์ชันเหล่านี้สนับสนุนแอป Power BI สำหรับ iOS:
- iPad ที่มี iOS 10 หรือใหม่กว่า
- iPhone 5 และสูงกว่า ที่มี iOS 10 หรือใหม่กว่า 
- iPod Touch ที่มี iOS 10 หรือใหม่กว่า

### <a name="download-the-opportunity-analysis-sample"></a>ดาวน์โหลดตัวอย่างการวิเคราะห์โอกาสทางการขาย
ขั้นตอนแรกในบทช่วยสอน คือ ดาวน์โหลดตัวอย่างการวิเคราะห์โอกาสทางการขายในบริการของ Power BI

1. เปิดบริการของ Power BI ในเบราว์เซอร์ของคุณ (app.powerbi.com) และลงชื่อเข้าใช้

1. เลือกที่ไอคอนนำทางส่วนกลาง เพื่อเปิดการนำทางด้านซ้าย

    ![ไอคอนนำทางส่วนกลาง](./media/tutorial-mobile-apps-ios-qna/power-bi-android-quickstart-global-nav-icon.png)

2. ในบานหน้าต่างนำทางด้านซ้าย เลือก **พื้นที่ทำงาน** > **พื้นที่ทำงานของฉัน**

    ![พื้นที่ทำงานของฉัน](./media/tutorial-mobile-apps-ios-qna/power-bi-android-quickstart-my-workspace.png)

3. ที่มุมล่างซ้าย เลือก**รับข้อมูล**
   
    ![รับข้อมูล](./media/tutorial-mobile-apps-ios-qna/power-bi-get-data.png)

3. บนหน้า รับข้อมูล เลือกไอคอน**ตัวอย่าง**
   
   ![ไอคอนตัวอย่าง](./media/tutorial-mobile-apps-ios-qna/power-bi-samples-icon.png)

4. เลือก **ตัวอย่างการวิเคราะห์โอกาสทางการขาย**
 
    ![ตัวอย่างการวิเคราะห์โอกาสทางการขาย](./media/tutorial-mobile-apps-ios-qna/power-bi-oa.png)
 
8. เลือก **เชื่อมต่อ**  
  
   ![ตัวอย่างการวิเคราะห์โอกาสทางการขาย - เชื่อมต่อ](./media/tutorial-mobile-apps-ios-qna/opportunity-connect.png)
   
5. Power BI นำเข้าตัวอย่าง เพิ่มแดชบอร์ดใหม่, รายงาน และชุดข้อมูลลงในพื้นที่ทำงานของฉัน
   
   ![แดชบอร์ดตัวอย่างการวิเคราะห์โอกาสทางการขาย](./media/tutorial-mobile-apps-ios-qna/power-bi-service-opportunity-sample.png)

คุณพร้อมที่จะดูตัวอย่างบนอุปกรณ์ iOS ของคุณแล้ว

## <a name="try-featured-insights"></a>ลองใช้ข้อมูลเชิงลึกที่แนะนำ
1. บน iPhone หรือ iPad ของคุณ เปิดแอป Power BI แล้วลงชื่อเข้าใช้ด้วยข้อมูลประจำตัวของบัญชีผู้ใช้ Power BI ของคุณ ซึ่งเป็นบัญชีเดียวกันกับที่คุณใช้ในบริการของ Power BI ในเบราว์เซอร์

1.  แตะที่ปุ่มนำทางส่วนกลาง ![ปุ่มนำทางส่วนกลาง](./media/tutorial-mobile-apps-ios-qna/power-bi-iphone-global-nav-button.png) > **พื้นที่ทำงาน** > **พื้นที่ทำงานของฉัน** และเปิดแดชบอร์ดตัวอย่างการวิเคราะห์โอกาสทางการขาย

2. แตะไอคอนนักวิเคราะห์เสมือนของถามตอบ ![ไอคอนนักวิเคราะห์เสมือนของถามตอบ](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-q-n-a-icon.png) จากเมนูการดำเนินการที่ด้านล่างของหน้า (ที่ด้านบนของหน้าใน iPad)

     ![แดชบอร์ดตัวอย่างการวิเคราะห์โอกาสทางการขาย](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-opportunity-analysis.png)

     นักวิเคราะห์เสมือนของถามตอบสำหรับ Power BI จะมีตัวอย่างคำแนะนำ เพื่อเริ่มต้นใช้งาน

     ![ปุ่มข้อมูลเชิงลึกที่แนะนำ](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-suggest-insights.png)
3. แตะ **ข้อมูลเชิงลึกที่แนะนำ**

     นักวิเคราะห์เสมือนของถามตอบจะแนะนำตัวอย่างข้อมูลเชิงลึกให้คุณทราบ
4. เลื่อนไปทางขวา แล้วแตะ**ข้อมูลเชิงลึก 2**

    ![ปุ่มข้อมูลเชิงลึก 2](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-suggest-insight-2.png)

     นักวิเคราะห์เสมือนของถามตอบจะแสดงข้อมูลเชิงลึก 2

    ![ข้อมูลเชิงลึก 2](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-show-insight-2.png)
5. แตะแผนภูมิเพื่อเปิดในโหมดโฟกัส

    ![แผนภูมิของข้อมูลเชิงลึก 2 ในโหมดโฟกัส](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-open-insight-2.png)
6. แตะลูกศรที่มุมซ้ายบน เพื่อกลับไปยังประสบการการใช้งานของนักวิเคราะห์เสมือนของถามตอบ

## <a name="clean-up-resources"></a>เพิ่มพื้นที่ทรัพยากร

เมื่อคุณจบบทช่วยสอนนี้แล้ว คุณสามารถลบแดชบอร์ด, รายงาน และชุดข้อมูลของตัวอย่างการวิเคราะห์โอกาสทางการขายได้

1. เปิดบริการของ Power BI (app.powerbi.com) และลงชื่อเข้าใช้

2. ในบานหน้าต่างนำทางด้านซ้าย เลือก **พื้นที่ทำงาน** > **พื้นที่ทำงานของฉัน**

3. บนแท็บ**แดชบอร์ด** เลือกที่ไอคอนถังขยะ **ลบ** ถัดจากแดชบอร์ดการวิเคราะห์โอกาสทางการขาย

    ![ลบแดชบอร์ดตัวอย่าง](./media/tutorial-mobile-apps-ios-qna/power-bi-service-delete-opportunity-sample.png)

4. เลือกแท็บ**รายงาน** และทำสิ่งเดียวกันสำหรับรายงานการวิเคราะห์โอกาสทางการขาย

5. เลือกแท็บ**ชุดข้อมูล** และทำสิ่งเดียวกันสำหรับชุดข้อมูลการวิเคราะห์โอกาสทางการขาย


## <a name="next-steps"></a>ขั้นตอนถัดไป

คุณได้ลอง นักวิเคราะห์เสมือนของถามตอบ ในแอปมือถือ Power BI สำหรับ iOS แล้ว เรียนรู้เพิ่มเติมเกี่ยวกับ ถามตอบในบริการของ Power BI
> [!div class="nextstepaction"]
> [การถามตอบในบริการ Power BI](../end-user-q-and-a.md)


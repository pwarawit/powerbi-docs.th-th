---
title: เชื่อมต่อกับ MailChimp ด้วย Power BI
description: MailChimp สำหรับ Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 8599c22246183d28d13eb80f05250baa8dc27f5d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "64579073"
---
# <a name="connect-to-mailchimp-with-power-bi"></a>เชื่อมต่อกับ MailChimp ด้วย Power BI
บทความนี้แนะนำคุณเกี่ยวกับการดึงข้อมูลของคุณจากบัญชี MailChimp ของคุณด้วยแอเทมเพลต Power BI แอปเทมเพลสร้างพื้นที่ทำงานกับแดชบอร์ด ชุดของรายงาน และชุดข้อมูลเพื่อให้คุณสามารถสำรวจข้อมูล MailChimp ของคุณ ดึงการวิเคราะห์เพื่อสร้าง[แดชบอร์ด MailChimp](https://powerbi.microsoft.com/integrations/mailchimp)และระบุแนวโน้มภายในของการส่งเสริมการขาย รายงาน และผู้สมัครใช้งานแต่ละรายการของคุณได้อย่างรวดเร็ว การรีเฟรชข้อมูลรายวัน แน่ใจว่า คุณกำลังตรวจสอบข้อมูลอยู่เสมอ

หลังจากที่คุณติดตั้งแอปเทมเพล คุณสามารถเปลี่ยนแดชบอร์ดและรายงาน จากนั้น คุณสามารถแจกจ่ายเป็นแอปให้เพื่อนร่วมงานในองค์กรของคุณ

เชื่อมต่อไปยัง[MailChimp เทมเพลแอ](https://app.powerbi.com/getdata/services/mailchimp)สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ

[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

3. เลือก**MailChimp** \> **รับทันที**
4. ใน**ติดตั้งแอป Power BI นี้ใช่ไหม**เลือก**ติดตั้ง**
4. ในการ**แอ**บานหน้าต่าง เลือกแบบ**MailChimp**ไทล์

    ![ไทล์ของแอป power BI MailChimp](media/service-connect-to-mailchimp/power-bi-connect-mailchimp.png)

6. ใน**เริ่มต้นใช้งานแอปของคุณใหม่**เลือก**เชื่อมต่อข้อมูล**

    ![เริ่มต้นใช้งานแอปใหม่ของคุณ](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

1. สำหรับวิธีการรับรองความถูกต้อง ให้เลือก **oAuth2** \> **ลงชื่อเข้าใช้**
   
    เมื่อถูกถาม ให้ใส่ข้อมูลประจำตัว MailChimp ของคุณและทำตามกระบวนการรับรองตัวตน
   
    ในครั้งแรกที่คุณเชื่อมต่อ Power BI จะปรากฏข้อความให้คุณอนุญาตให้เข้าถึงแบบอ่านอย่างเดียวสำหรับบัญชีของคุณ เลือก**อนุญาต**เพื่อเริ่มกระบวนการนำเข้า อาจใช้เวลาสักครู่ ขึ้นอยู่กับปริมาณของข้อมูลในบัญชีของคุณ
   
    ![Power BI Connector สำหรับ MailChimp](media/service-connect-to-mailchimp/allow.png)

5. หลังจาก Power BI นำเข้าข้อมูล แดชบอร์ด MailChimp เปิดขึ้น
   
    ![แดชบอร์ด BI MailChimp power](media/service-connect-to-mailchimp/power-bi-mailchimp-dashboard.png)

## <a name="modify-and-distribute-your-app"></a>ปรับเปลี่ยน และแจกจ่ายแอปของคุณ

คุณได้ติดตั้งแอปเทมเพล MailChimp ซึ่งหมายความว่า คุณจะสร้างพื้นที่ทำงานแอ MailChimp ในพื้นที่ทำงาน คุณสามารถเปลี่ยนรายงานและแดชบอร์ด และแจกจ่ายเป็นแอ*แอ*ให้เพื่อนร่วมงานในองค์กรของคุณได้ 

1. เมื่อต้องดูเนื้อหาทั้งหมดของ MailChimp พื้นที่ทำงานใหม่ ในแถบนำทางด้านซ้าย เลือก**พื้นที่ทำงาน** > **MailChimp** 

    ![MailChimp พื้นที่ทำงานในบานหน้าต่างนำทางด้านซ้าย](media/service-connect-to-mailchimp/power-bi-mailchimp-left-nav.png)

    มุมมองนี้คือ รายการเนื้อหาสำหรับพื้นที่ทำงาน ในมุมขวาบน คุณเห็น**อัปเดตแอปฯ** เมื่อคุณพร้อมที่จะแจกจ่ายแอปของคุณให้เพื่อนร่วมงานของคุณ ที่อยู่ที่คุณจะเริ่มต้น

    ![รายการเนื้อหา MailChimp](media/service-connect-to-mailchimp/power-bi-mailchimp-content-list.png)

2. เลือก**รายงาน**และ**ชุดข้อมูล**เพื่อดูองค์ประกอบอื่น ๆ ในพื้นที่ทำงาน 

    อ่านเกี่ยวกับ[แจกจ่ายแอ](service-create-distribute-apps.md)ให้เพื่อนร่วมงานของคุณ

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [สร้างพื้นที่ทำงานใหม่ใน Power BI](service-create-the-new-workspaces.md)
* [ติดตั้งและใช้แอปฯใน Power BI](consumer/end-user-apps.md)
* [แอป Power BI สำหรับบริการภายนอก](service-connect-to-services.md)
* มีคำถามหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


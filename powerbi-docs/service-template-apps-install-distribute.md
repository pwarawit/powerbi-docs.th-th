---
title: แจกจ่ายแอปแม่แบบในองค์กรของคุณ - Power BI (ตัวอย่าง)
description: เรียนรู้เกี่ยวกับการติดตั้ง กำหนดเอง และการแจกจ่ายแอปแม่แบบในองค์กรของคุณใน Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 04/19/2019
ms.author: maggies
ms.openlocfilehash: 2b7b2630e665fca9013920718ff58dd973f01392
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578564"
---
# <a name="install-and-distribute-template-apps-in-your-organization---power-bi-preview"></a>แจกจ่ายแอปแม่แบบในองค์กรของคุณ - Power BI (ตัวอย่าง)

คุณจะเป็นนักวิเคราะห์ Power BI หรือไม่ ถ้าดังนั้น บทความนี้อธิบายวิธีการติดตั้ง*เทมเพลแอ*เพื่อเชื่อมต่อกับบริการคุณใช้เพื่อเรียกใช้ธุรกิจของคุณ เช่น Salesforce, Microsoft Dynamics และ Google Analytics จำนวนมาก คุณสามารถปรับเปลี่ยนแดชบอร์ดและรายงานตามความต้องการขององค์กรของคุณ และกระจายให้เพื่อนร่วมงานของคุณเป็นแอ*แอ*ได้ 

![Power BI ได้ติดตั้งแล้ว](media/service-template-apps-install-distribute/power-bi-get-apps.png)

ถ้าคุณสนใจในการสร้างแอปแม่แบบเพื่อกระจายด้วยตนเอง ดู[สร้างแอปแม่แบบใน Power BI](service-template-apps-create.md) Power BI คู่ค้าสามารถสร้างแอป Power BI ด้วยเพียงเล็กน้อย หรือไม่มีการเข้ารหัส และปรับใช้กับลูกค้า Power BI 

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น  

นี่คือข้อกำหนดสำหรับการติดตั้ง กำหนดเอง และการแจกจ่ายแอปแม่แบบ: 

- [ใบอนุญาต Power BI pro](service-self-service-signup-for-power-bi.md)
- ความชำนาญกับ[แนวคิดพื้นฐานของ Power BI ](service-basic-concepts.md)
- ลิงก์ติดตั้งที่ถูกต้องจากผู้สร้างแอปแม่แบบหรือ AppSource 
- สิทธิ์ในการติดตั้งแอปแม่แบบ 

## <a name="install-a-template-app"></a>สร้างแอปแม่แบบ

คุณอาจได้รับลิงก์ไปยังแอปแม่แบบ ไม่เช่นนั้น คุณสามารถค้นหา AppSource สำหรับแอปแม่แบบที่คุณสนใจได้ ใช้วิธีใด หลังจากที่คุณติดตั้ง คุณสามารถปรับเปลี่ยน และแจกจ่ายให้กับองค์กรของคุณเองได้

### <a name="search-appsource-from-a-browser"></a>ค้นหา AppSource จากเบราว์เซอร์

ในเบราว์เซอร์ เลือกลิงก์นี้เพื่อเปิด AppSource ให้ถูกกรองไปยังแอป Power BI:

- https://appsource.microsoft.com/marketplace/apps?product=power-bi

### <a name="search-appsource-from-the-power-bi-service"></a>ค้นหา AppSource จากบริการ Power BI

1. ในบานหน้าต่างนำทางด้านซ้ายของบริการ Power BI เลือก**แอป** > **รับแอป**

    ![รับแอป](media/service-template-apps-install-distribute/power-bi-get-apps-arrow.png)

2. ใน AppSource เลือก**แอป**

    ![ค้นหาใน AppSource](media/service-template-apps-install-distribute/power-bi-appsource.png)

3. เรียกดูหรือค้นหาแอป จากนั้นเลือก**รับทันที**

2. ในกล่องโต้ตอบ ให้เลือก **ติดตั้ง**

    ถ้าคุณมีสิทธิ์การเข้าใช้งาน Power BI Pro แอปจะถูกติดตั้งพร้อมกับพื้นที่ทำงานของแอปที่เกี่ยวข้อง คุณกำหนดค่าแอปในพื้นที่ทำงานเกี่ยวข้อง

    เมื่อการติดตั้งสำเร็จ คุณจะเห็นการแจ้งเตือนว่า แอปใหม่ของคุณพร้อมแล้ว 

3. เลือก**ไปยังแอป**
4. ใน**เริ่มต้นใช้งานแอปใหม่ของคุณ**เลือกหนึ่งในสามตัวเลือก:

    ![เริ่มต้นด้วยแอปของคุณ](media/service-template-apps-create/power-bi-template-app-get-started.png)

    - **สำรวจแอป**: สำรวจข้อมูลพื้นฐานตัวอย่าง เริ่มที่นี่เพื่อสัมผัสรูปลักษณ์ของแอป 
    - **เชื่อมต่อข้อมูล**: เปลี่ยนแหล่งข้อมูลจากข้อมูลตัวอย่างไปเป็นแหล่งข้อมูลของคุณเอง คุณสามารถกำหนดชุดข้อมูลพารามิเตอร์และแหล่งข้อมูลประจำตัวใหม่ได้ ดู[ข้อจำกัดที่ทราบแล้ว](service-template-apps-tips.md#known-limitations)ในบทความเคล็ดลับของแอปแม่แบบ 
    - **ไปยังพื้นที่ทำงาน**(ตัวเลือกที่ทันสมัยที่สุด): คุณสามารถอนุญาตให้มีการเปลี่ยนแปลงใดๆ ก็ได้โดยตัวสร้างแอป

    หรือข้ามกล่องโต้ตอบนี้ และเข้าถึงพื้นที่ทำงานที่เกี่ยวข้องโดยตรงผ่านทาง**พื้นที่ทำงาน**ในบานหน้าต่างนำทางด้านซ้าย   
 
5. ก่อนที่คุณแชร์กับเพื่อนร่วมงานของคุณ คุณจะต้องเชื่อมต่อกับข้อมูลของคุณเองก่อน คุณอาจต้องการปรับเปลี่ยนรายงานหรือแดชบอร์ดเพื่อทำให้ทำงานสำหรับองค์กรของคุณ คุณยังสามารถเพิ่มรายงานหรือแดชบอร์ดอื่นๆ ในตอนนี้

## <a name="update-and-distribute-the-app"></a>ปรับปรุงและแจกจ่ายแอป

หลังจากที่คุณได้ปรับปรุงแอปสำหรับองค์กรของคุณแล้ว คุณก็พร้อมที่จะเผยแพร่ได้ ขั้นตอนจะเหมือนกับการเผยแพร่แอปอื่นๆ 

1. เมื่อคุณเสร็จสิ้นการกำหนดเอง ในมุมมองรายการพื้นที่ทำงานเลือก**อัปเดตแอป**ในมุมขวาบน  

    ![เริ่มการติดตั้งแอป](media/service-template-apps-install-distribute/power-bi-start-install-app.png)

2. ใน**รายละเอียด** คุณสามารถปรับเปลี่ยนคำอธิบายและสีพื้นหลังได้

   ![ตั้งค่าคำอธิบายและสีของแอป](media/service-template-apps-install-distribute/power-bi-install-app-details.png)

3. ใน**เนื้อหา**คุณสามารถเลือกเพจเริ่มต้น อาจเป็นแดชบอร์ดหรือรายงานก็ได้

   ![ตั้งค่าหน้าเริ่มต้นของแอป](media/service-template-apps-install-distribute/power-bi-install-app-content.png)

4. ใน**เข้าถึง** คุณให้การเข้าถึงโดยการเลือกผู้ใช้งานหรือบุคคลในองค์กรของคุณทั้งหมดอย่างใดอย่างหนึ่ง  

   ![ตั้งค่าการเข้าถึงแอป](media/service-template-apps-install-distribute/power-bi-install-access.png)

5. เลือก**อัปเดตแอป** 

6. หลังจากเผยแพร่เรียบร้อยแล้ว คุณสามารถคัดลอกลิงก์และแชร์กับใครก็ได้ตามคุณต้องการให้เข้าถึง ถ้าคุณได้แชร์แอปกับผู้อื่นแล้ว ผู้อื่นจะแอปบนแท็บ**องค์กรของฉัน**ใน AppSource

## <a name="next-steps"></a>ขั้นตอนถัดไป 

[สร้างพื้นที่ทำงานกับเพื่อนร่วมงานของคุณใน Power BI](service-create-workspaces.md)





￼ 

 

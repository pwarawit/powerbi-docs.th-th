---
title: เชื่อมต่อกับ Smartsheet ด้วย Power BI
description: Smartsheet สำหรับ Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 841201aa87139b9630d6fc076d57109fb2b09804
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578930"
---
# <a name="connect-to-smartsheet-with-power-bi"></a>เชื่อมต่อกับ Smartsheet ด้วย Power BI
บทความนี้แนะนำคุณเกี่ยวกับการดึงข้อมูลของคุณจากบัญชี Smartsheet ของคุณด้วยแอเทมเพลต Power BI Smartsheet มีแพลตฟอร์มอย่างง่าย สำหรับการทำงานร่วมกันและการแชร์ไฟล์ แอปเทมเพล Smartsheet สำหรับ Power BI มีแดชบอร์ด รายงาน และชุดข้อมูลที่แสดงภาพรวมของบัญชี Smartsheet ของคุณ คุณยังสามารถใช้[Power BI Desktop](desktop-connect-to-data.md)เพื่อเชื่อมต่อโดยตรงกับแต่ละแผ่นงานในบัญชีของคุณได้ 

หลังจากที่คุณติดตั้งแอปเทมเพล คุณสามารถเปลี่ยนแดชบอร์ดและรายงาน จากนั้น คุณสามารถแจกจ่ายเป็นแอปให้เพื่อนร่วมงานในองค์กรของคุณ

เชื่อมต่อไปยัง[Smartsheet เทมเพลแอ](https://app.powerbi.com/groups/me/getdata/services/smartsheet)สำหรับ Power BI

>[!NOTE]
>มีบัญชีผู้ดูแลระบบ Smartsheet เป็นสิ่งจำเป็นสำหรับการเชื่อมต่อ และโหลดแอเทมเพลต Power BI เนื่องจากมีการเข้าถึงเพิ่มเติม

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ

[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

3. เลือก**Smartsheet** \> **รับทันที**
4. ใน**ติดตั้งแอป Power BI นี้ใช่ไหม**เลือก**ติดตั้ง**
4. ในการ**แอ**บานหน้าต่าง เลือกแบบ**Smartsheet**ไทล์

    ![ไทล์ของแอป power BI Smartsheet](media/service-connect-to-smartsheet/power-bi-smartsheet-tile.png)

6. ใน**เริ่มต้นใช้งานแอปของคุณใหม่**เลือก**เชื่อมต่อข้อมูล**

    ![เริ่มต้นใช้งานแอปใหม่ของคุณ](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

4. สำหรับวิธีการรับรองความถูกต้อง เลือก **oAuth2 \> ลงชื่อเข้าใช้**
   
   เมื่อได้รับพร้อมท์ ใส่ข้อมูลประจำตัวของ Smartsheet และทำตามกระบวนการรับรองความถูกต้อง
   
   ![ข้อมูลประจำตัวของ Smartsheet](media/service-connect-to-smartsheet/creds.png)
   
   ![ลงชื่อเข้าใช้ของ Smartsheet](media/service-connect-to-smartsheet/creds2.png)

5. หลังจาก Power BI นำเข้าข้อมูล แดชบอร์ด Smartsheet เปิดขึ้น
   
   ![แดชบอร์ด Smartsheet](media/service-connect-to-smartsheet/power-bi-smartsheet-dashboard.png)

## <a name="modify-and-distribute-your-app"></a>ปรับเปลี่ยน และแจกจ่ายแอปของคุณ

คุณได้ติดตั้งแอปเทมเพล Smartsheet ซึ่งหมายความว่า คุณจะสร้างพื้นที่ทำงานแอ Smartsheet ในพื้นที่ทำงาน คุณสามารถเปลี่ยนรายงานและแดชบอร์ด และแจกจ่ายเป็นแอ*แอ*ให้เพื่อนร่วมงานในองค์กรของคุณได้ 

1. เมื่อต้องดูเนื้อหาทั้งหมดของ Smartsheet พื้นที่ทำงานใหม่ ในแถบนำทางด้านซ้าย เลือก**พื้นที่ทำงาน** > **Smartsheet** 

    ![พื้นที่ทำงาน Smartsheet ในบานหน้าต่างนำทางด้านซ้าย](media/service-connect-to-smartsheet/power-bi-smartsheet-workspace.png)

    มุมมองนี้คือ รายการเนื้อหาสำหรับพื้นที่ทำงาน ในมุมขวาบน คุณเห็น**อัปเดตแอปฯ** เมื่อคุณพร้อมที่จะแจกจ่ายแอปของคุณให้เพื่อนร่วมงานของคุณ ที่อยู่ที่คุณจะเริ่มต้น 

    ![รายการเนื้อหา Smartsheet](media/service-connect-to-smartsheet/power-bi-smartsheet-workspace-content.png)

2. เลือก**รายงาน**และ**ชุดข้อมูล**เพื่อดูองค์ประกอบอื่น ๆ ในพื้นที่ทำงาน

    อ่านเกี่ยวกับ[แจกจ่ายแอ](service-create-distribute-apps.md)ให้เพื่อนร่วมงานของคุณ

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
Smartsheet แอเทมเพลสำหรับ Power BI มีภาพรวมของบัญชีของคุณ Smartsheet เช่นจำนวนของพื้นที่ทำงาน รายงาน และแผ่นงานที่คุณมี เมื่อพวกเขากำลังปรับเปลี่ยนและอื่น ๆ ผู้ใช้ผู้ดูแลระบบยังดูข้อมูลเกี่ยวกับผู้ใช้ในระบบของพวกเขา เช่นผู้สร้างแผ่นงานที่ด้านบน  

เพื่อเชื่อมต่อโดยตรงไปยังแต่ละแผ่นงานในบัญชีของคุณ คุณสามารถใช้ตัวเชื่อมต่อ Smartsheet ใน [Power BI Desktop](desktop-connect-to-data.md) ได้  

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [สร้างพื้นที่ทำงานใหม่ใน Power BI](service-create-the-new-workspaces.md)
* [ติดตั้งและใช้แอปฯใน Power BI](consumer/end-user-apps.md)
* [เชื่อมต่อกับแอป Power BI สำหรับบริการภายนอก](service-connect-to-services.md)
* มีคำถามหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)
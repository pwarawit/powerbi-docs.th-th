---
title: การรวม Power BI ด้วย Microsoft Flow
description: เรียนรู้วิธีสร้างโฟลวที่์ถูกทริกเกอร์ ด้วยการแจ้งเตือนข้อมูล Power BI
author: mgblythe
manager: kfile
ms.reviewer: ''
featuredvideoid: YhmNstC39Mw
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/01/2018
ms.author: mblythe
LocalizationGroup: Get started
ms.openlocfilehash: c02ce0a92e258055edf906cf17730fec56bcb450
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "61147150"
---
# <a name="microsoft-flow-and-power-bi"></a>Microsoft Flow และ Power BI

[Microsoft Flow](https://flow.microsoft.com/documentation/getting-started)คือ SaaS ที่นำเสนอสำหรับการทำงานอัตโนมัติสำหรับเวิร์กโฟลว์ในแอปพลิเคชันที่หลากหลายและบริการ SaaS ที่ผู้ใช้ทางธุรกิจใช้อยู่ ด้วยโฟลว์ คุณสามารถทำงานโดยอัตโนมัติ โดยการรวมแอปโปรดของคุณและบริการที่ (รวมถึง Power BI) เพื่อรับการแจ้งเตือน การซิงโครไนซ์ไฟล์ การเก็บรวบรวมข้อมูล และอื่น ๆ การทำงานซ้ำ ๆ กลายเป็นเรื่องง่าย ด้วยเวิร์คโฟลว์อัตโนมัติ

[เริ่มต้นใช้งานโฟลว์ตอนนี้เลย](https://flow.microsoft.com/documentation/getting-started)

ดู Sirui สร้างโฟลว์ที่ส่งอีเมลที่มีลายละเอียดให้เพื่อนร่วมงาน เมื่อการแจ้งเตือนของ Power BI ถูกทริกเกอร์ แล้ว ทำตามคำแนะนำทีละขั้นตอนด้านล่างวิดีโอเพื่อลองทำด้วยตนเอง

<iframe width="560" height="315" src="https://www.youtube.com/embed/YhmNstC39Mw" frameborder="0" allowfullscreen></iframe>

## <a name="create-a-flow-that-is-triggered-by-a-power-bi-data-alert"></a>สร้างโฟลว์ที่ทริกเกอร์ โดยข้อมูลการแจ้งเตือนของ Power BI

### <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
บทเรียนนี้จะแสดงวิธีการสร้างโฟลว์ที่แตกต่างกันสองโฟลว์ หนึ่งโฟลว์จากเทมเพลตและอีกหนึ่งทำมาจากเริ่มต้น เพื่อทำตาม[สร้างการแจ้งเตือนข้อมูลใน Power BI](service-set-data-alerts.md)สร้างบัญชีผู้ใช้ฟรีของ Slack และ[ลงชื่อเข้าใช้ Microsoft Flow](https://flow.microsoft.com/#home-signup) (ซึ่งใช้ฟรี)

## <a name="create-a-flow-that-uses-power-bi---from-a-template"></a>สร้างโฟลว์ที่ใช้ Power BI จากเทมเพลต
ในงานนี้ เราจะใช้เทมเพลตเพื่อสร้างโฟลว์อย่างง่ายที่จะถูกทริกเกอร์ โดยการแจ้งเตือนข้อมูล Power BI (notification)

1. ลงชื่อเข้าใช้ Microsoft Flow (flow.microsoft.com)
2. ให้เลือก**โฟลว์ของฉัน**
   
   ![แถบเมนโฟลว์](media/service-flow-integration/power-bi-my-flows.png)
3. ให้เลือก**สร้างจากเทมเพลต**
   
    ![แถบเมนูโฟลว์ของฉัน](media/service-flow-integration/power-bi-template.png)
4. ใช้กล่องค้นหาเพื่อค้นหาเทมเพล Power BI และให้เลือก**ส่งอีเมลถึงผู้ชมใดๆ เมื่อการแจ้งเตือนข้อมูล Power BI ถูกทริกเกอร์ > ดำเนินการต่อ**
   
    ![ผลลัพธ์การค้นหา](media/service-flow-integration/power-bi-flow-alert.png)


### <a name="build-the-flow"></a>สร้างโฟลว์
เทมเพลตนี้มีหนึ่งทริกเกอร์ (ข้อมูลแจ้งเตือน Power BI สำหรับเหรียญรโอลิมปิกใหม่ของไอร์แลนด์) และการดำเนินการหนึ่งอย่าง (ส่งอีเมล) เมื่อคุณเลือกเขตข้อมูล โฟลว์จะแสดงเนื้อหาแบบไดนามิกที่คุณสามารถรวม  ในตัวอย่างนี้ เราจะรวมค่าไทล์และ URL ไทล์ในเนื้อหาข้อความ

![เทมเพลตของ flow](media/service-flow-integration/power-bi-template1.png)

1. จากเมนูดรอปดาวน์ทริกเกอร์ ให้เลือกการแจ้งเตือนข้อมูล Power BI ให้เลือก**เหรียญรางวัลใหม่สำหรับไอร์แลนด์** เมื่อต้องการเรียนรู้วิธีการสร้างการแจ้งเตือน ให้ดู[การแจ้งเตือนข้อมูลใน Power BI](service-set-data-alerts.md)
   
   ![ดรอปดาวน์การแจ้งเตือน](media/service-flow-integration/power-bi-trigger-flow.png)
2. ใส่ที่อยู่อีเมลที่ถูกต้องอย่างน้อยหนึ่งอีเมล์ จากนั้นให้เลือก**แก้ไข** (แสดงด้านล่าง) หรือ**เพิ่มเนื้อหาแบบไดนามิก** 
   
   ![ส่งเป็นหน้าจออีเมล](media/service-flow-integration/power-bi-flow-email.png)

3. ขั้นตอนสร้างชื่อเรื่องและข้อความสำหรับคุณ ซึ่งคุณสามารถเก็บหรือปรับเปลี่ยนได้ ค่าทั้งหมดที่คุณตั้งค่าเมื่อคุณได้สร้างการแจ้งเตือนใน Power BI มันจะพร้อมใช้งาน เพียงแค่วางเคอร์เซอร์ของคุณ และเลือกจากพื้นที่การเน้นสีเทา 

   ![ส่งเป็นหน้าจออีเมล](media/service-flow-integration/power-bi-flow-email-default.png)

1.  ตัวอย่างเช่น ถ้าคุณสร้างชื่อเรื่องการแจ้งเตือนใน Power BI เรื่อง**เราชนะเหรียญรางวัลอื่น**คุณสามาจะรถเลือก**ชื่อเรื่องการแจ้งเตือน**เพื่อเพิ่มข้อความนั้นลงในเช่องชื่อเรื่องอีเมลของคุณได้

    ![สร้างข้อความของอีเมล](media/service-flow-integration/power-bi-flow-message.png)

    และคุณสามารถใช้เนื้อความอีเมลเริ่มต้น หรือสร้างด้วยตนเองได้ ตัวอย่างข้างต้นประกอบด้วยการปรับเปลี่ยนข้อความเพียงไม่กี่จุด

1. เมื่อคุณทำเสร็จแล้ว ให้เลือก**สร้างโฟลว์**หรือ**บันทึกโฟลว์**  ขั้นตอนถูกสร้างขึ้นและถูกประเมิน  ขั้นตอนช่วยให้คุณทราบถ้าพบข้อผิดพลาด
2. ถ้าพบข้อผิดพลาด ให้เลือก**แก้ไขโฟลว์**เมื่อต้องการแก้ไขปัญหาเหล่านั้น ถ้าไม่ ให้เลือก**เสร็จแล้ว**เพื่อเรียกใช้โฟลว์ใหม่
   
   ![ข้อความแสดงความสำเร็จ](media/service-flow-integration/power-bi-flow-running.png)
5. เมื่อการแจ้งเตือนข้อมูลถูกทริกเกอร์ อีเมลที่จะถูกส่งไปยังที่อยู่คุณระบุ  
   
   ![อีเมลที่แจ้งเตือน](media/service-flow-integration/power-bi-flow-email2.png)

## <a name="create-a-flow-that-uses-power-bi---from-scratch-blank"></a>สร้างโฟลว์ที่ใช้ Power BI แบบตั้งแต่เริ่มต้น (ว่าง)
ในงานนี้ เราจะสร้างโฟลว์ง่ายๆ ตั้งแต่เริ่มต้น ซึ่งจะถูกทริกเกอร์โดยการแจ้งเตือนข้อมูล Power BI (notification)

1. ลงชื่อเข้าใช้ Microsoft Flow
2. ให้เลือก**โฟลว์ของฉัน** > **สร้างจากเอกสารเปล่า**
   
   ![แถบเมนูด้านบนของโฟลว์](media/service-flow-integration/power-bi-my-flows.png)
3. ใช้กล่องค้นหาเพื่อค้นหาทริกเกอร์ Power BI และเลือก**Power BI เมื่อการแจ้งเตือนข้อมูลถูกทริกเกอร์**

### <a name="build-your-flow"></a>สร้างโฟลว์ของคุณ
1. จากรายการแบบดร๊อปดาวน์ ให้เลือกชื่อของการแจ้งเตือนของคุณ  เมื่อต้องการเรียนรู้วิธีการสร้างการแจ้งเตือน ให้ดู[การแจ้งเตือนข้อมูลใน Power BI](service-set-data-alerts.md)
   
    ![เลือกชื่อของการแจ้งเตือน](media/service-flow-integration/power-bi-totalstores2.png)
2. เลือก**ขั้นตอนใหม่** > **เพิ่มแอคชัน**
   
   ![เพิ่มขั้นตอนใหม่](media/service-flow-integration/power-bi-new-step.png)
3. ให้ค้นหา**Outlook**และให้เลือก**สร้างเหตุการณ์**
   
   ![สร้างโฟลว์](media/service-flow-integration/power-bi-create-event.png)
4. กรอกเขตข้อมูลในช่องเหตุการณ์ เมื่อคุณเลือกเขตข้อมูล โฟลว์จะแสดงเนื้อหาแบบไดนามิกที่คุณสามารถรวม
   
   ![ดำเนินต่อเพื่อสร้างโฟลว์](media/service-flow-integration/power-bi-flow-event.png)
5. ให้เลือก **สร้างโฟลว์**เมื่อทำเสร็จแล้ว  โฟลว์จะบันทึกและประเมิน ถ้าไม่ มีข้อผิดพลาด ให้เลือก**เสร็จสิ้น**เพื่อเรียกใช้โฟลว์นี้  ขั้นตอนใหม่ถูกเพิ่มลงในหน้า**โฟลว์ของฉัน**
   
   ![ทำให้โฟลว์เสร็จสมบูรณ์](media/service-flow-integration/power-bi-flow-running.png)
6. เมื่อโฟลว์ถูกทริกเกอร์ โดยการแจ้งเตือนข้อมูล Power BI คุณจะได้รับการแจ้งเตือนเหตุการณ์บน Outlook ที่คล้ายกัน
   
    ![โฟลว์ทริกเกอร์การแจ้งเตือนใน Outlook](media/service-flow-integration/power-bi-flow-notice.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [เริ่มต้นใช้งาน Microsoft Flow](https://flow.microsoft.com/documentation/getting-started/)
* [ตั้งค่าการแจ้งเตือนข้อมูลใน Power BI service](service-set-data-alerts.md)
* [ตั้งค่าการแจ้งเตือนข้อมูลบน iPhone ของคุณ](consumer/mobile/mobile-set-data-alerts-in-the-mobile-apps.md)
* [ตั้งค่าการแจ้งเตือนข้อมูลในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่สำหรับ Windows 10](consumer/mobile/mobile-set-data-alerts-in-the-mobile-apps.md)
* มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


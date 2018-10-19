---
title: Microsoft Power BI Premium คืออะไร?
description: Power BI Premium คือความสามารถเฉพาะสำหรับองค์กรหรือทีมของคุณ ซึ่งให้ประสิทธิภาพการทำงานเพิ่มขึ้นและปริมาณข้อมูลขนาดใหญ่ขึ้น โดยที่คุณไม่จำเป็นต้องซื้อสิทธิ์การใช้งานต่อผู้ใช้
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 09/11/2018
LocalizationGroup: Premium
ms.openlocfilehash: 0723ddb57131fed499d4ac86666b3cd6d8bcbd2d
ms.sourcegitcommit: 833cf1252807721fb1b3000487bd032bfd6c8c98
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/04/2018
ms.locfileid: "48271819"
---
# <a name="what-is-microsoft-power-bi-premium"></a>Microsoft Power BI Premium คืออะไร?

Microsoft Power BI Premium ให้บริการด้านทรัพยากรที่อุทิศแด่การดำเนินงานบริการ Power BI สำหรับองค์กรหรือทีมของคุณ ซึ่งทำให้ประสิทธิภาพการทำงานเพิ่มขึ้น และทำให้ใช้ปริมาณข้อมูลขนาดใหญ่ได้ นอกจากนี้ Premium ยังเปิดเนื้อหาแจกจ่ายอย่างแพร่หลายโดยที่คุณไม่ต้องซื้อสิทธิ์การใช้งาน Pro ต่อผู้ใช้สำหรับผู้ชม

คุณสามารถใช้ประโยชน์จาก Power BI Premium ได้โดยการกำหนดพื้นที่ทำงานให้กับ*ความจุพรีเมียม* ความจุพรีเมียมเป็นทรัพยากรเฉพาะสำหรับองค์กรของคุณ พื้นที่ทำงานที่ไม่ได้กำหนดให้มีความจุพรีเมียมอยู่ใน*ความจุที่ใช้ร่วมกัน* ด้วยความจุที่ใช้ร่วมกัน ปริมาณงานของคุณจะทำงานบนแหล่งทรัพยากรการคำนวณที่ลูกค้าคนอื่น ๆ ใช้ร่วมกัน 

ในส่วนของความจุที่ใช้ร่วมกัน Power BI จำกัดผู้ใช้รายบุคคลมากขึ้นเพื่อความมั่นใจด้านคุณภาพของประสบการณ์สำหรับผู้ใช้ทุกคน โดยค่าเริ่มต้น พื้นที่ทำงานของคุณจะอยู่ในความจุที่ใช้ร่วมกัน ซึ่งรวมถึง *พื้นที่ทำงานของฉัน*แบบส่วนตัวของคุณและแอปพื้นที่ทำงาน

[!INCLUDE [powerbi-premium-illustration](./includes/powerbi-premium-illustration.md)]

<iframe width="560" height="315" src="https://www.youtube.com/embed/lNQDkN0GXzU?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="capacity-tiers"></a>ระดับความจุ

นี่คือสรุปความแตกต่างระหว่างความจุที่ใช้ร่วมกันและความจุพรีเมียม

|  | ความจุที่ใช้ร่วมกัน | ความจุ Power BI Premium |
| --- | --- | --- |
| **อัตราฟื้นฟู** |8/วัน |48/วัน |
| **แยกกับฮาร์ดแวร์เฉพาะ** |![](media/service-premium/not-available.png "ไม่พร้อมใช้งาน") |![](media/service-premium/available.png "พร้อมใช้งาน") |
| **แจก Enterprise Distribution ให้** ***ผู้ใช้ทั้งหมด*** | | |
| แอปและการแชร์ |![](media/service-premium/not-available.png "ไม่พร้อมใช้งาน") |![](media/service-premium/available.png "พร้อมใช้งาน")<sup>1</sup> |
| API และตัวควบคุมแบบฝังตัว |![](media/service-premium/not-available.png "ไม่พร้อมใช้งาน") |![](media/service-premium/available.png "พร้อมใช้งาน")<sup>2</sup> |
| **เผยแพร่รายงาน Power BI ในสถานที่** |![](media/service-premium/not-available.png "ไม่พร้อมใช้งาน") |![](media/service-premium/available.png "พร้อมใช้งาน") |

*<sup>1</sup> สำหรับข้อมูลเพิ่มเติม โปรดดู [คุณลักษณะตามประเภทสิทธิ์การใช้งาน](service-features-license-type.md)*  
*<sup>2</sup>การปรับปรุงในอนาคตที่มาพร้อมกับ Power BI Premium*

หากต้องการเริ่มใช้ความจุ Power BI Premium ให้กำหนดพื้นที่ทำงานไปยังความจุ เมื่อความจุพรีเมียมมารองรับพื้นที่ทำงาน คุณจะได้รับ:

* **กำหนดการรีเฟรช**: สำหรับความจุที่ใช้ร่วมกัน กำหนดการรีเฟรชสำหรับชุดข้อมูลแบบจำลองนำเข้าถูกจำกัดไว้ที่แปดครั้งต่อวัน สำหรับชุดข้อมูลในพื้นที่ทำงานแบบพรีเมียม คุณสามารถจัดกำหนดการรีเฟรชสูงสุด 48 ครั้งต่อวัน การรีเฟรชแคช DirectQuery ก็ยังคงถูกจำกัดที่แปดครั้งต่อวันสำหรับความจุพรีเมียม

* **แยกกับฮาร์ดแวร์เฉพาะ**: ในความจุที่ใช้ร่วมกัน ความต้องการทรัพยากรของปริมาณงานสามารถส่งผลกระทบต่อสมรรถภาพของรายงานและแดชบอร์ดของคุณ ในทางกลับกัน ความจุพรีเมียมมีความเสถียรและมีสมรรถภาพมากกว่าสำหรับปริมาณงานของคุณ โดยการแยกออกจากปริมาณงานที่ไม่เกี่ยวข้อง

หากแอปได้รับการสนุบสนุนด้วยความจุพรีเมียม (กล่าวคือ แอปเผยแพร่จากพื้นที่ทำงานแอปที่ปัจจุบันถูกกำหนดให้เป็นพรีเมียม) ผู้ใช้ทุกคนในองค์กรของคุณไม่ว่าจะถูกกำหนดสิทธิ์ใช้งานใดจะสามารถใช้แอปที่เผยแพร่แล้วนั้นได้

หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับการกำหนดพื้นที่ทำงานให้มีความจุพรีเมียม โปรดดู [จัดการ Power BI Premium](service-admin-premium-manage.md)

<a name="premiumskus"/>

### <a name="premium-capacity-nodes"></a>โหนดความจุแบบพรีเมียม

Power BI Premium ความจุ v-core ที่แตกต่างกัน สำหรับข้อมูลเพิ่มเติมเกี่ยวกับข้อเสนอ SKU ที่ระบุและค่าใช้จ่าย ดูที่[การกำหนดราคา Power BI](https://powerbi.microsoft.com/pricing/) [ตัวคำนวนค่าใช้จ่าย](https://powerbi.microsoft.com/calculator/)พร้อมใช้งาน สำหรับข้อมูลเกี่ยวกับการวางแผนความจุวิเคราะห์แบบฝังตัว ให้ดู[อกสารทางเทคนิคเรื่องการวางแผนการใช้ Power BI สำหรับองค์กร](https://aka.ms/pbienterprisedeploy)

* โหนด P สามารถใช้สำหรับการปรับใช้แบบฝังตัว หรือบริการ

* โหนด EM สามารถใช้สำหรับการปรับใช้แบบฝังตัวเท่านั้น โหนด EM ไม่สามารถเข้าถึงความสามารถพรีเมียม เช่น การแชร์แอปให้ผู้ใช้ที่ไม่มีสิทธิ์การใช้งาน Power BI Pro

>[!NOTE]
>ลิงก์ในตารางนี้จะทำงานได้อย่างถูกต้องสำหรับผู้ใช้ที่เป็นผู้ดูแลทั่วไปของ Office 365 ผู้อื่นได้รับข้อผิดพลาด 404

| โหนดของความจุ | วี-คอร์รวม<br/>*(Backend + frontend)* | วี-คอร์ Backend | วี-คอร์ Frontend | การจำกัดการเชื่อมต่อ DirectQuery/live | หน้าสูงสุดที่แสดงในชั่วโมงที่เรียกใช้มากที่สุด | ความพร้อมใช้งาน |
| --- | --- | --- | --- | --- | --- | --- |
| [EM1 (แบบรายเดือน)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |1 v-core |0.5 v-cores 2.5-GB RAM |0.5 v-cores |3.75 ต่อวินาที |150-300 |พร้อมใช้งาน |
| [EM2 (แบบรายเดือน)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |2 v-cores |1 v-core, 5-GB RAM |1 v-core |7.5 ต่อวินาที |301-600 |พร้อมใช้งาน |
| [EM3 (แบบรายเดือน)](https://portal.office.com/SubscriptionDetails?OfferId=4004702D-749C-4F74-BF47-3048F1833780&adminportal=1) |4 v-cores |2 v-cores, 10-GB RAM |2 v-cores | |601-1,200 |พร้อมใช้งาน |
| [P1](https://portal.office.com/SubscriptionDetails?OfferId=b3ec5615-cc11-48de-967d-8d79f7cb0af1&adminportal=1) |8 v-cores |4 v-cores, 25-GB RAM |4 v-cores |30 ต่อวินาที |1,201-2,400 |พร้อมใช้งาน ([รายเดือน](https://portal.office.com/SubscriptionDetails?OfferId=E4C8EDD3-74A1-4D42-A738-C647972FBE81&adminportal=1)พร้อมใช้งานเช่นกัน) |
| [P2](https://portal.office.com/SubscriptionDetails?OfferId=062F2AA7-B4BC-4B0E-980F-2072102D8605&adminportal=1) |16 v-cores |8 v-cores, 50-GB RAM |8 v-cores |60 ต่อวินาที |2,401-4,800 |พร้อมใช้งาน |
| [P3](https://portal.office.com/SubscriptionDetails?OfferId=40c7d673-375c-42a1-84ca-f993a524fed0&adminportal=1) |32 v-cores |16 v-cores, 100-GB RAM |16 v-cores |120 ต่อวินาที |4,801-9600 |พร้อมใช้งาน |

* วี-คอร์ Frontend รับผิดชอบบริการเว็บ แดชบอร์ด และการจัดการเอกสารรายงาน การจัดการสิทธิ์การเข้าถึง การจัดกำหนดการ API การอัปโหลดและการดาวน์โหลด และโดยทั่วไปนั้นเพื่อทุกอย่างที่เกี่ยวกับประสบการณ์การใช้งานของผู้ใช้

* วี-คอร์ Backend รับผิดชอบงานที่ยาก เช่น การประมวลผลคิวรี การจัดการแคช การเรียกใช้ R Server การรีเฟรชข้อมูล การประมวลผลภาษาธรรมชาติ ตัวดึงข้อมูลแบบเรียลไทม์ และการแสดงผลฝั่งเซิร์ฟเวอร์ในรูปแบบรายงานและรูป ด้วยการใช้วี-คอร์ Backend หน่วยความจำจะถูกสงวนไว้เช่นกัน การมีหน่วยความจำที่เพียงพอกลายเป็นสิ่งสำคัญ โดยเฉพาะอย่างยิ่งเมื่อทำงานกับตัวแบบข้อมูลขนาดใหญ่หรือตัวเลขขนาดใหญ่ของชุดข้อมูลที่ใช้งานอยู่

## <a name="power-bi-report-server"></a>เซิร์ฟเวอร์รายงาน Power BI
Power BI Premium ยังรวมถึงความสามารถในการดำเนินเซิร์ฟเวอร์รายงาน Power BI ภายในองค์กรของคุณ หากต้องการเรียนรู้เพิ่มเติม โปรดดู[เริ่มต้นใช้งานเซิร์ฟเวอร์รายงาน Power BI](report-server/get-started.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI Premium คำถามที่พบบ่อย](service-premium-faq.md)  
[บันทึกย่อประจำรุ่นของ Power BI Premium](service-premium-release-notes.md)  
[วิธีการซื้อ Power BI Premium](service-admin-premium-purchase.md)  
[การจัดการ Power BI Premium](service-admin-premium-manage.md)  
[เอกสารทางเทคนิคเรื่อง Microsoft Power BI Premium](https://aka.ms/pbipremiumwhitepaper)  
[เอกสารทางเทคนิคเรื่องการวางแผนการใช้ Power BI สำหรับองค์กร](https://aka.ms/pbienterprisedeploy)  
[จัดการPower BI ในองค์กรของคุณ](service-admin-administering-power-bi-in-your-organization.md)  

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)

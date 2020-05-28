---
title: การแก้ไขปัญหาไปป์ไลน์การปรับใช้
description: แก้ปัญหาไปป์ไลน์การปรับใช้ใน Power BI
author: KesemSharabi
ms.author: kesharab
ms.topic: overview
ms.service: powerbi
ms.subservice: powerbi-service
ms.date: 05/06/2020
ms.openlocfilehash: fda846a19b5c6081c59f08f2bf9f94eddbc9852c
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83148551"
---
# <a name="deployment-pipelines-troubleshooting-preview"></a>การแก้ไขปัญหาไปป์ไลน์การปรับใช้ (ตัวอย่าง)

ใช้บทความนี้เพื่อแก้ไขปัญหาในไปป์ไลน์การปรับใช้

## <a name="general"></a>ทั่วไป

### <a name="whats-deployment-pipelines-in-power-bi"></a>ไปป์ไลน์การปรับใช้ใน Power BI คืออะไร

เมื่อต้องการทำความเข้าใจเกี่ยวกับการปรับใช้ไปป์ไลน์ใน Power BI โปรดดู [ภาพรวมของไปป์ไลน์การปรับใช้](deployment-pipelines-overview.md)

### <a name="how-do-i-get-started-with-deployment-pipelines"></a>ฉันจะเริ่มต้นอย่างไรกับไปป์ไลน์การปรับใช้

เริ่มต้นไปป์ไลน์การปรับใช้โดยใช้ [คำแนะนำเริ่มต้น](deployment-pipelines-get-started.md)

### <a name="why-cant-i-see-the-deployment-pipelines-button"></a>เหตุใดฉันจึงไม่เห็นปุ่มไปป์ไลน์การปรับใช้

ถ้าไม่เป็นไปตามเงื่อนไขต่อไปนี้คุณจะไม่สามารถดูปุ่มไปป์ไลน์การปรับใช้ได้

* คุณเป็นผู้ใช้ Power BI [Pro](../admin/service-admin-purchasing-power-bi-pro.md)

* คุณเป็นสมาชิกขององค์กรที่มีความจุแบบพรีเมียม

* สามารถกำหนดพื้นที่ทำงานให้กับไปป์ไลน์เดียวเท่านั้น

* คุณเป็นผู้ดูแลระบบของพื้นที่ทำงานใหม่

## <a name="licensing"></a>สิทธิ์การใช้งาน

### <a name="what-licenses-are-needed-to-work-with-deployment-pipelines"></a>สิทธิ์การใช้งานใดที่จำเป็นในการดำเนินการไปป์ไลน์การปรับใช้

หากต้องการใช้ไปป์ไลน์การปรับใช้ คุณจะต้องเป็น [ผู้ใช้ Pro](../admin/service-admin-purchasing-power-bi-pro.md) กับ [ความจุแบบพรีเมียม](../admin/service-premium-what-is.md) สำหรับข้อมูลเพิ่มเติม ดู [การเข้าถึงไปป์ไลน์การปรับใช้](deployment-pipelines-get-started.md#accessing-deployment-pipelines)

### <a name="what-type-of-capacity-can-i-assign-to-a-workspace-in-a-pipeline"></a>ฉันสามารถกำหนดความจุชนิดใดให้กับพื้นที่ทำงานในไปป์ไลน์ได้

พื้นที่ทำงานทั้งหมดในขั้นตอนการปรับใช้จะต้องอยู่ภายในความจุเฉพาะสำหรับไปป์ไลน์เพื่อให้สามารถใช้ได้ อย่างไรก็ตามคุณสามารถใช้ความจุที่แตกต่างกันสำหรับพื้นที่ทำงานที่แตกต่างกันในไปป์ไลน์ คุณยังสามารถใช้ชนิดความจุที่แตกต่างกันสำหรับพื้นที่ทำงานที่แตกต่างกันในไปป์ไลน์เดียวกันได้

สำหรับการพัฒนาและการทดสอบ คุณสามารถใช้ความจุ A หรือ EM ควบคู่ไปกับบัญชี Pro Power BI สำหรับผู้ใช้แต่ละราย

สำหรับพื้นที่ทำงานการผลิต คุณต้องมีความจุ P ถ้าคุณเป็น ISV แจกจ่ายเนื้อหาผ่านแอปพลิเคชันแบบฝังตัวคุณยังสามารถใช้ความจุ A หรือ EM สำหรับการผลิตได้

## <a name="technical"></a>ทางเทคนิค

### <a name="why-cant-i-see-all-my-workspaces-when-i-try-to-assign-a-workspace-to-a-pipeline"></a>เหตุใดฉันจึงไม่สามารถดูพื้นที่ทำงานของฉันทั้งหมดได้เมื่อฉันพยายามกำหนดพื้นที่ทำงานให้กับไปป์ไลน์

เมื่อต้องการกำหนดพื้นที่ทำงานให้กับไปป์ไลน์ต้องเป็นไปตามเงื่อนไขต่อไปนี้:

* พื้นที่ทำงานเป็น [ประสบการณ์พื้นที่ทำงานใหม่](../collaborate-share/service-create-the-new-workspaces.md)

* คุณเป็นผู้ดูแลระบบของพื้นที่ทำงาน

* พื้นที่ทำงานไม่ได้ถูกกำหนดให้กับไปป์ไลน์อื่น

* พื้นที่ทำงานอยู่บน [ความจุแบบพรีเมียม](../admin/service-premium-what-is.md)

พื้นที่ทำงานที่ไม่เป็นไปตามเงื่อนไขเหล่านี้จะไม่แสดงในรายการของพื้นที่ทำงานที่คุณสามารถเลือกได้

### <a name="how-can-i-assign-workspaces-to-all-the-stages-in-a-pipeline"></a>ฉันสามารถกำหนดพื้นที่ทำงานให้กับขั้นตอนทั้งหมดในไปป์ไลน์ได้อย่างไร

คุณสามารถกำหนดพื้นที่ทำงานได้หนึ่งรายการต่อไปป์ไลน์ เมื่อพื้นที่ทำงานถูกกำหนดให้กับไปป์ไลน์คุณสามารถปรับใช้กับขั้นตอนไปป์ไลน์ถัดไปได้ ในระหว่างการปรับใช้ครั้งแรก พื้นที่ทำงานใหม่จะถูกสร้างขึ้นด้วยสำเนาของรายการในขั้นตอนต้นทาง ความสัมพันธ์ของรายการที่คัดลอกจะถูกเก็บไว้ สำหรับข้อมูลเพิ่มเติม ดูวิธีการ [กำหนดพื้นที่ทำงานให้กับไปป์ไลน์การปรับใช้](deployment-pipelines-get-started.md#step-2---assign-a-workspace-to-a-deployment-pipeline)

### <a name="why-did-my-first-deployment-fail"></a>เหตุใดการปรับใช้ครั้งแรกของฉันจึงล้มเหลว

การปรับใช้ครั้งแรกของคุณอาจล้มเหลวเนื่องจากมีเหตุผลหลายประการ บางสาเหตุเหล่านี้จะแสดงอยู่ในตารางด้านล่าง

|ข้อผิดพลาด  |การดำเนินการ  |
|---------|---------|
|คุณไม่มี [สิทธิ์ความจุแบบพรีเมียม](deployment-pipelines-process.md#creating-a-premium-capacity-workspace)     |เมื่อต้องการรับสิทธิ์ความจุแบบพรีเมียม คุณสามารถขอให้ผู้ดูแลความจุเพิ่มพื้นที่ทำงานของคุณไปยังความจุ หรือขอสิทธิ์ในการกำหนดสำหรับความจุ หลังจากที่พื้นที่ทำงานอยู่ในความจุให้ปรับใช้ใหม่        |
|คุณไม่มีสิทธิ์ในพื้นที่ทำงาน     |หากต้องการปรับใช้คุณจะต้องเป็นสมาชิกพื้นที่ทำงาน ขอให้ผู้ดูแลระบบพื้นที่ทำงานของคุณมอบสิทธิ์ที่เหมาะสมให้แก่คุณ         |
|ผู้ดูแลระบบ Power BI ของคุณได้ปิดใช้งานการสร้างพื้นที่ทำงาน     |ติดต่อผู้ดูแลระบบ Power BI ของคุณเพื่อขอรับการสนับสนุน         |
|พื้นที่ทำงานของคุณไม่เป็น [ประสบการณ์พื้นที่ทำงานใหม่](../collaborate-share/service-create-the-new-workspaces.md)     |สร้างเนื้อหาของคุณในประสบการณ์พื้นที่ทำงานใหม่ ถ้าคุณมีเนื้อหาในพื้นที่ทำงานคลาสสิกคุณสามารถ [อัปเกรด](../collaborate-share/service-upgrade-workspaces.md) ไปยังประสบการณ์พื้นที่ทำงานใหม่         |
|การใช้งาน [การปรับใช้แบบเลือก](deployment-pipelines-get-started.md#selective-deployment) ของคุณและไม่ได้เลือกชุดข้อมูลของเนื้อหาของคุณ     |ทำรายการใดรายการหนึ่งต่อไปนี้: </br></br>ยกเลิกการเลือกเนื้อหาที่เชื่อมโยงกับชุดข้อมูลของคุณ เนื้อหาที่ไม่ได้เลือกของคุณ (เช่นรายงานหรือแดชบอร์ด) จะไม่ถูกคัดลอกไปยังขั้นตอนต่อไป </br></br>เลือกชุดข้อมูลที่เชื่อมโยงกับเนื้อหาที่เลือก ชุดข้อมูลของคุณจะถูกคัดลอกไปยังขั้นตอนถัดไป         |

### <a name="im-getting-a-warning-that-i-have-unsupported-artifacts-in-my-workspace-when-im-trying-to-deploy-how-can-i-know-which-artifacts-are-not-supported"></a>ฉันได้รับคำเตือนว่าฉันมี 'วัตถุที่ไม่ได้รับการรองรับ' ในพื้นที่ทำงานของฉันเมื่อฉันพยายามปรับใช้ ฉันจะทราบได้อย่างไรว่าวัตถุใดที่ไม่ได้รับการรองรับ

สำหรับรายการที่ครอบคลุมของรายการและวัตถุที่ไม่ได้รับการรองรับในไปป์ไลน์การปรับใช้ดูส่วนต่อไปนี้:

* [รายการที่ไม่รองรับ](deployment-pipelines-process.md#unsupported-items)

* [คุณสมบัติรายการที่ไม่ได้คัดลอก](deployment-pipelines-process.md#item-properties-that-are-not-copied)

### <a name="why-did-my-deployment-fail-due-to-broken-rules"></a>ทำไมการปรับใช้ของฉันล้มเหลวเนื่องจากกฎที่เสียหาย

ถ้าคุณมีปัญหาในการกำหนดค่ากฎของชุดข้อมูลให้เยี่ยมชม [กฎชุดข้อมูล](deployment-pipelines-get-started.md#step-4---create-dataset-rules)และตรวจสอบให้แน่ใจว่าคุณได้ทำตาม [ข้อจำกัดของกฎชุดข้อมูล](deployment-pipelines-get-started.md#dataset-rule-limitations)

ถ้าการปรับใช้ของคุณได้รับการดำเนินการสำเร็จก่อนหน้านี้และไม่สามารถทำงานกับกฎที่เสียหายแบบฉับพลันได้ อาจเกิดจากชุดข้อมูลถูกเผยแพร่ใหม่ การเปลี่ยนแปลงต่อไปนี้ไปยังชุดข้อมูลต้นทางให้ผลลัพธ์ในการปรับใช้ล้มเหลว:

**กฎพารามิเตอร์**

* พารามิเตอร์ที่ถูกเอาออก

* ชื่อพารามิเตอร์ที่มีการเปลี่ยนแปลง

**กฎของแหล่งข้อมูล**

กฎชุดข้อมูลของคุณมีค่าที่ขาดหายไป ซึ่งอาจเกิดขึ้นหากมีการเปลี่ยนแปลงชุดข้อมูลของคุณ

![กฎที่เสียหาย](media/deployment-pipelines-troubleshooting/broken-rule.png)

เมื่อการปรับใช้ที่สำเร็จก่อนหน้านี้ล้มเหลวเนื่องจากลิงก์ที่เสียหาย คำเตือนจะปรากฏขึ้น คุณสามารถคลิก **กำหนดค่ากฎ** เพื่อนำทางไปยังบานหน้าต่างการตั้งค่าการปรับใช้ที่มีการทำเครื่องหมายชุดข้อมูลที่ล้มเหลว เมื่อคุณคลิกที่ชุดข้อมูล กฎที่เสียหายจะถูกทำเครื่องหมาย

เมื่อต้องการปรับใช้สำเร็จ ให้แก้ไขหรือลบกฎที่เสียหายและปรับใช้ใหม่

### <a name="how-can-i-change-the-data-source-in-the-pipeline-stages"></a>ฉันจะเปลี่ยนแหล่งข้อมูลในขั้นตอนไปป์ไลน์ได้อย่างไร

คุณไม่สามารถเปลี่ยนการเชื่อมต่อแหล่งข้อมูลในบริการของ Power BI

ถ้าคุณต้องการเปลี่ยนแหล่งข้อมูลในขั้นตอนการทดสอบหรือการผลิตคุณสามารถใช้ [กฎชุดข้อมูล](deployment-pipelines-get-started.md#step-4---create-dataset-rules) หรือ [Api](https://docs.microsoft.com/rest/api/power-bi/datasets/updateparametersingroup) กฎชุดข้อมูลจะมีผลหลังจากการปรับใช้ครั้งถัดไปเท่านั้น

### <a name="i-fixed-a-bug-in-production-but-now-i-cant-click-the-deploy-to-previous-stage-button-why-is-it-greyed-out"></a>ฉันแก้ไขบักในการผลิตแต่ตอนนี้ฉันไม่สามารถคลิกที่ปุ่ม 'ปรับใช้กับขั้นตอนก่อนหน้า' ได้ เหตุใดจึงเป็นสีเทา

คุณสามารถปรับใช้งานย้อนกลับไปยังขั้นตอนที่ว่างเปล่าได้เท่านั้น ถ้าคุณมีเนื้อหาในขั้นตอนการทดสอบคุณจะไม่สามารถปรับใช้งานย้อนหลังจากการผลิตได้

หลังจากสร้างไปป์ไลน์ให้ใช้ขั้นตอนการพัฒนาเพื่อพัฒนาเนื้อหาของคุณและขั้นตอนการทดสอบเพื่อตรวจทานและทดสอบ คุณสามารถแก้ไขบักในขั้นตอนเหล่านี้และจากนั้นปรับใช้สภาพแวดล้อมแบบคงที่ไปยังขั้นตอนการผลิต

>[!NOTE]
>การปรับใช้ย้อนหลังรองรับเฉพาะ [การปรับใช้เต็มรูปแบบ](deployment-pipelines-get-started.md#deploying-all-content) เท่านั้น ไม่รองรับ [การปรับใช้ที่เลือก](deployment-pipelines-get-started.md#selective-deployment)

### <a name="does-deployment-pipelines-support-multi-geo"></a>ไปป์ไลน์การปรับใช้รองรับหลายพรมแดนหรือไม่?

รองรับหลายพรมแดน ซึ่งอาจใช้เวลานานในการปรับใช้เนื้อหาระหว่างขั้นตอนในพรมแดนแตกต่างกัน

## <a name="permissions"></a>การอนุญาต

### <a name="what-is-the-deployment-pipelines-permissions-model"></a>แบบจำลองสิทธิ์ของไปป์ไลน์การปรับใช้คืออะไร

แบบจำลองสิทธิ์ของไปป์ไลน์การปรับใช้ได้รับการอธิบายไว้ในส่วน [สิทธิ์](deployment-pipelines-process.md#permissions)

### <a name="who-can-deploy-content-between-stages"></a>ใครสามารถปรับใช้เนื้อหาระหว่างขั้นตอนได้

สามารถปรับใช้เนื้อหาไปยังขั้นตอนที่ว่างเปล่าหรือไปยังขั้นตอนที่มีเนื้อหาได้ เนื้อหาต้องอยู่ใน [ความจุแบบพรีเมียม](../admin/service-premium-what-is.md)

* **การปรับใช้งานไปยังขั้นตอนที่ว่างเปล่า** - [ผู้ใช้ Pro](../admin/service-admin-purchasing-power-bi-pro.md) ใดก็ตามที่เป็นสมาชิกหรือผู้ดูแลระบบในพื้นที่ทำงานต้นทาง

* **ปรับใช้กับขั้นตอนที่มีเนื้อหา** - [ผู้ใช้ Pro](../admin/service-admin-purchasing-power-bi-pro.md) ใดก็ตามที่เป็นสมาชิกหรือผู้ดูแลระบบของทั้งสองพื้นที่ทำงานในขั้นตอนปรับใช้แหล่งที่มาและเป้าหมาย

* **การแทนที่ชุดข้อมูล** - การปรับใช้แทนที่แต่ละชุดข้อมูลที่รวมอยู่ในขั้นตอนเป้าหมายแม้ว่าจะไม่มีการเปลี่ยนแปลงชุดข้อมูล ผู้ใช้ต้องเป็นเจ้าของชุดข้อมูลในขั้นตอนเป้าหมายทั้งหมดที่ระบุในการปรับใช้

### <a name="which-permissions-do-i-need-to-configure-dataset-rules"></a>ฉันจำเป็นต้องใช้สิทธิ์ใดในการกำหนดค่ากฎชุดข้อมูล

ในการกำหนดค่ากฎชุดข้อมูลในไปป์ไลน์การปรับใช้คุณต้องเป็นเจ้าของชุดข้อมูล

### <a name="why-cant-i-see-workspaces-in-the-pipeline"></a>เหตุใดฉันจึงไม่เห็นพื้นที่ทำงานในไปป์ไลน์

สิทธิ์ของไปป์ไลน์และพื้นที่ทำงานได้รับการจัดการแยกกัน คุณอาจมีสิทธิ์ในการใช้งานไปป์ไลน์ แต่ไม่สามารถใช้สิทธิ์ในพื้นที่ทำงานได้ สำหรับข้อมูลเพิ่มเติมให้ตรวจทานส่วน [สิทธิ์](deployment-pipelines-process.md#permissions)

## <a name="next-steps"></a>ขั้นตอนถัดไป

>[!div class="nextstepaction"]
>[บทนำสู่ไปป์ไลน์การปรับใช้](deployment-pipelines-overview.md)

>[!div class="nextstepaction"]
>[เริ่มต้นกับไปป์ไลน์การปรับใช้](deployment-pipelines-get-started.md)

>[!div class="nextstepaction"]
>[ทำความเข้าใจกระบวนการไปป์ไลน์การปรับใช้](deployment-pipelines-process.md)

>[!div class="nextstepaction"]
>[แนวทางปฏิบัติที่ดีที่สุดสำหรับไปป์ไลน์การปรับใช้](deployment-pipelines-best-practices.md)
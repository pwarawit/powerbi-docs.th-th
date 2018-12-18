---
title: 'บริการจากบุคคลที่สาม: ตัวเชื่อมต่อ Google Analytics'
description: 'บริการจากบุคคลที่สาม: ตัวเชื่อมต่อ Google Analytics สำหรับ Power BI Desktop'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b7451f156503d88baf4bdf3f3ae2cb99c04a94c1
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/07/2018
ms.locfileid: "53025614"
---
# <a name="google-analytics-connector-for-power-bi-desktop"></a>ตัวเชื่อมต่อ Google Analytics สำหรับ Power BI Desktop
> [!NOTE]
> ชุดเนื้อหา Google Analytics และตัวเชื่อมต่อใน Power BI Desktop พึ่งพา Google Analytics Core Reporting API ด้วยเหตุนี้ คุณลักษณะและความพร้อมใช้งาน อาจแตกต่างกันไปตามเวลา

คุณสามารถเชื่อมต่อกับข้อมูล Google Analytics โดยใช้ตัวเชื่อมต่อ **Google Analytics** ได้ เพื่อเชื่อมต่อ ทำตามขั้นตอนต่อไปนี้:

1. ใน **Power BI Desktop** เลือก**รับข้อมูล**จากการแท็บ ribbon **หน้าแรก**
2. ในหน้าต่าง**รับข้อมูล** เลือก**บริการออนไลน์**จากประเภทในบานหน้าต่างด้านซ้าย
3. เลือก **Google Analytics** จากตัวเลือกในบานหน้าต่างด้านขวา
4. ที่ด้านล่างของหน้าต่าง เลือก**เชื่อมต่อ**  
   ![](media/service-google-analytics-connector/tps_googleanalytics_1.png)

คุณได้รับพร้อมท์กล่องโต้ตอบที่อธิบายว่า ตัวเชื่อมต่อเป็นบริการจากบุคคลที่สาม และเตือนเกี่ยวกับคุณลักษณะและความพร้อมใช้งาน ที่อาจเปลี่ยนไปตามช่วงเวลา และคำอธิบายอื่น ๆ  
![](media/service-google-analytics-connector/tps_googleanalytics_2.png)

เมื่อคุณเลือก**ดำเนินการต่อ** คุณจะได้รับพร้อมท์ให้ลงชื่อเข้าใช้ Google Analytics  
![](media/service-google-analytics-connector/tps_googleanalytics_3.png)

เมื่อคุณใส่ข้อมูลประจำตัวของคุณ คุณได้รับพร้อมท์ว่า Power BI ต้องสามารถเข้าถึงแบบออฟไลน์ นี่คือวิธีที่คุณใช้ **Power BI Desktop** เพื่อเข้าถึงข้อมูล Google Analytics ของคุณ  

เมื่อคุณยอมรับ **Power BI Desktop** แสดงให้เห็นว่าคุณลงชื่อเข้าใช้แล้ว  
![](media/service-google-analytics-connector/tps_googleanalytics_5.png)

เลือก**เชื่อมต่อ** และข้อมูล Google Analytics ของคุณ จะถูกเชื่อมต่อกับ **Power BI Desktop** และโหลดข้อมูล  
![](media/service-google-analytics-connector/tps_googleanalytics_6.png)

## <a name="changes-to-the-api"></a>การเปลี่ยนแปลงของ API
แม้ว่าเราพยายามเผยแพร่อัปเดตที่สอดคล้องกับการเปลี่ยนแปลงใด ๆ API อาจเปลี่ยนแปลงในลักษณะที่ส่งผลกระทบต่อผลลัพธ์ของคิวรีที่เราสร้างขึ้น ในบางกรณี บางแบบสอบถามอาจไม่สนับสนุนอีกต่อไป เนื่องจากการต้องพึ่งพาจากบุคคลที่สามนี้ เราไม่สามารถรับประกันผลลัพธ์ของคิวรีคุณเมื่อใช้ตัวเชื่อมต่อนี้

รายละเอียดเพิ่มเติมเกี่ยวกับ การเปลี่ยนแปลง Google Analytics API สามารถอ่านใน[บันทึกการเปลี่ยนแปลง](https://developers.google.com/analytics/devguides/changelog)ของพวกเขาได้


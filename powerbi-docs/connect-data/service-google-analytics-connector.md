---
title: 'บริการจากบุคคลที่สาม: ตัวเชื่อมต่อ Google Analytics'
description: 'บริการจากบุคคลที่สาม: ตัวเชื่อมต่อ Google Analytics สำหรับ Power BI Desktop'
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: ec290ce53155f24a9213a4849ecb82abd6cfc592
ms.sourcegitcommit: e8ed3d120699911b0f2e508dc20bd6a9b5f00580
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/11/2020
ms.locfileid: "86263654"
---
# <a name="use-the-google-analytics-connector-for-power-bi-desktop"></a>ใช้ตัวเชื่อมต่อ Google Analytics สำหรับ Power BI Desktop
> [!NOTE]
> ชุดเนื้อหา Google Analytics และตัวเชื่อมต่อใน Power BI Desktop พึ่งพา Google Analytics Core Reporting API ด้วยเหตุนี้ คุณลักษณะและความพร้อมใช้งาน อาจแตกต่างกันไปตามเวลา

คุณสามารถเชื่อมต่อกับข้อมูล Google Analytics โดยใช้ตัวเชื่อมต่อ **Google Analytics** ได้ เพื่อเชื่อมต่อ ทำตามขั้นตอนต่อไปนี้:

1. ใน **Power BI Desktop** เลือก**รับข้อมูล**จากการแท็บ ribbon **หน้าแรก**
2. ในหน้าต่าง**รับข้อมูล** เลือก**บริการออนไลน์**จากประเภทในบานหน้าต่างด้านซ้าย
3. เลือก **Google Analytics** จากตัวเลือกในบานหน้าต่างด้านขวา
4. ที่ด้านล่างของหน้าต่าง เลือก**เชื่อมต่อ**  
   ![หน้าจอของแท็บหน้าแรก ที่แสดงแถบเครื่องมือริบบอนรับข้อมูลพร้อมด้วย Google Analytics ที่เลือกไว้และปุ่มเชื่อมต่อ](media/service-google-analytics-connector/tps_googleanalytics_1.png)

คุณได้รับพร้อมท์กล่องโต้ตอบที่อธิบายว่า ตัวเชื่อมต่อเป็นบริการจากบุคคลที่สาม และเตือนเกี่ยวกับคุณลักษณะและความพร้อมใช้งาน ที่อาจเปลี่ยนไปตามช่วงเวลา และคำอธิบายอื่น ๆ  
![ภาพหน้าจอของกล่องโต้ตอบการเชื่อมต่อ ที่แสดงคำเตือนว่าตัวเชื่อมต่อทำงานโดยใช้บริการของบุคคลที่สาม](media/service-google-analytics-connector/tps_googleanalytics_2.png)

เมื่อคุณเลือก**ดำเนินการต่อ** คุณจะได้รับพร้อมท์ให้ลงชื่อเข้าใช้ Google Analytics  
![ภาพหน้าจอของข้อความแจ้งเตือน Google Analytics ที่แสดงว่าคุณจำเป็นต้องลงชื่อเข้าใช้เพื่อเชื่อมต่อ](media/service-google-analytics-connector/tps_googleanalytics_3.png)

เมื่อคุณใส่ข้อมูลประจำตัวของคุณ คุณได้รับพร้อมท์ว่า Power BI ต้องสามารถเข้าถึงแบบออฟไลน์ นี่คือวิธีที่คุณใช้ **Power BI Desktop** เพื่อเข้าถึงข้อมูล Google Analytics ของคุณ  

เมื่อคุณยอมรับ **Power BI Desktop** แสดงให้เห็นว่าคุณลงชื่อเข้าใช้แล้ว  
![ภาพหน้าจอของข้อความแจ้งเตือน Google Analytics ที่แสดงว่าคุณลงชื่อเข้าใช้](media/service-google-analytics-connector/tps_googleanalytics_5.png)

เลือก**เชื่อมต่อ** และข้อมูล Google Analytics ของคุณ จะถูกเชื่อมต่อกับ **Power BI Desktop** และโหลดข้อมูล  
![ภาพหน้าจอของกล่องโต้ตอบโหลด ที่แสดงว่ามีการเชื่อมต่อและโหลดข้อมูล Google Analytics](media/service-google-analytics-connector/tps_googleanalytics_6.png)

## <a name="changes-to-the-api"></a>การเปลี่ยนแปลงของ API
แม้ว่าเราพยายามเผยแพร่อัปเดตที่สอดคล้องกับการเปลี่ยนแปลงใด ๆ API อาจเปลี่ยนแปลงในลักษณะที่ส่งผลกระทบต่อผลลัพธ์ของคิวรีที่เราสร้างขึ้น ในบางกรณี บางแบบสอบถามอาจไม่สนับสนุนอีกต่อไป เนื่องจากการต้องพึ่งพาจากบุคคลที่สามนี้ เราไม่สามารถรับประกันผลลัพธ์ของคิวรีคุณเมื่อใช้ตัวเชื่อมต่อนี้

รายละเอียดเพิ่มเติมเกี่ยวกับ การเปลี่ยนแปลง Google Analytics API สามารถอ่านใน[บันทึกการเปลี่ยนแปลง](https://developers.google.com/analytics/devguides/changelog)ของพวกเขาได้


---
title: เปลี่ยนวิธีการที่การแสดงผลด้วยภาพโต้ตอบในรายงาน
description: จัดทำเอกสารประกอบสำหรับวิธีการตั้งค่าการโต้ตอบแบบภาพในรายงานบริการ Microsoft Power BI และรายงาน Power BI Desktop
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
featuredvideoid: N_xYsCbyHPw
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 02/28/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 7e2ef4a1ec49335a49e7f934a7606b2fe64f755c
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/09/2018
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>การโต้ตอบแบบการแสดงภาพในรายงาน Power BI
ถ้าคุณมีสิทธิ์ในการแก้ไขรายงาน คุณสามารถใช้**โต้ตอบแบบภาพ**เพื่อเปลี่ยนวิธีแสดงภาพบนหน้ารายงานมีผลกระทบต่อกันได้ 

ตามค่าเริ่มต้น สามารถใช้การแสดงภาพบนหน้ารายงานเพื่อกรองแบบไขว้และไฮไลท์ข้ามไปยังแสดงภาพอื่น ๆ ในหน้าดังกล่าว
ตัวอย่างเช่น เลือกหนึ่งสถานะในการแสดงภาพของแผนที่เน้นแผนภูมิคอลัมน์และตัวกรองแผนภูมิเส้นเพื่อให้แสดงเฉพาะข้อมูลที่นำไปใช้กับหนึ่งสถานะดังกล่าว
ดู[เกี่ยวกับการกรองและการเน้น](power-bi-reports-filters-and-highlighting.md) และหากคุณมีการแสดงภาพที่สนับสนุน[การเข้าถึงรายละเอียด](power-bi-visualization-drill-down.md)ตามค่าเริ่มต้น การเข้าถึงรายละเอียดข้อมูลแสดงภาพหนึ่งไม่มีผลกระทบต่อการแสดงภาพอื่น ๆ บนหน้ารายงานดังกล่าว แต่ลักษณะการทำงานที่เป็นค่าเริ่มต้นทั้งสองนี้สามารถแทนที่ได้ และโต้ตอบมีการตั้งค่าในแบบต่อหนึ่งการแสดงภาพ

บทความนี้แสดงวิธีใช้**การโต้ตอบภาพ**ในบริการ Power BI [มุมมองการแก้ไข](service-interact-with-a-report-in-editing-view.md)และใน Power BI Desktop ถ้ามีการแชร์รายงานกับคุณ คุณจะไม่สามารถเปลี่ยนการตั้งค่าการโต้ตอบแบบภาพได้

> [!NOTE]
> คำศัพท์*ตัวกรองไขว้*และ*ไฮไลท์ข้าม*จะนำมาใช้เพื่อแยกความแตกต่างลักษณะการทำงานที่อธิบายไว้ที่นี่สำหรับสิ่งที่เกิดขึ้นเมื่อคุณใช้การพื้นที่**ตัวกรอง**เพื่อกรองและเน้นการแสดงภาพ  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. เลือกการแสดงภาพเพื่อเปิดใช้งาน  
2. แสดงตัวเลือก**การโต้ตอบแบบภาพ**
    - ในบริการ Power BI เลือกรายการแบบเลื่อนลงจากแถบเมนูรายงาน

       ![การโต้ตอบแบบภาพแบบเลื่อนลง](media/service-reports-visual-interactions/power-bi-visual-interaction.png)

    - ที่เดสก์ท็อป เลือก**รูปแบบ > การโต้ตอบ**

        ![จากนั้นเลือก รูปแบบ และเลือก การโต้ตอบ](media/service-reports-visual-interactions/pbi-visual-interaction-desktop.png)

3. เมื่อต้องการเปิดใช้งานตัวควบคุมการแสดงภาพโต้ตอบ เลือก**แก้ไขการโต้ตอบ** Power BI เพิ่มไอคอนตัวกรองข้าม และไฮไลท์ข้ามไปยังการแสดงภาพอื่น ๆ ทั้งหมดบนหน้ารายงาน
   
    ![รายงานที่มีการโต้ตอบแบบภาพที่เปิดใช้งานอยู่](media/service-reports-visual-interactions/power-bi-icons-on.png)
3. กำหนดว่ารายการใดควรมีผลกระทบต่อผู้อื่นสำหรับการแสดงภาพที่เลือก  และมีอีกหนึ่งทางเลือกคือ ทำซ้ำสำหรับแสดงภาพอื่น ๆ ทั้งหมดบนหน้ารายงาน
   
   * หากควรมีการใช้ตัวกรองข้ามสำหรับการแสดงภาพ ให้เลือกไอคอน**ตัวกรอง**![ไอคอนตัวกรอง](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png)
   * หากควรมีการใช้ไฮไลท์ข้ามสำหรับการแสดงภาพ ให้เลือกไอคอน**ไฮไลท์**![ไอคอนไฮไลท์](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png)
   * หากไม่ต้องการให้มีผลกระทบ เลือกไอคอน**ไม่มีผลกระทบ**![ไอคอนไม่มีผลกระทบ](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png)

4. เมื่อต้องการเปิดใช้งานตัวควบคุมการเข้าถึงรายละเอียด เลือก**ตัวกรองการเข้าถึงรายละเอียดสำหรับภาพอื่น ๆ**  ในตอนนี้เมื่อคุณเจาะลึกลงรายละเอียด (และเจาะขึ้นมา) ในการแสดงภาพ การแสดงภาพอื่น ๆ บนหน้ารายงานจะเปลี่ยนเพื่อแสดงเลือกการเจาะลงรายละเอียดปัจจุบันของคุณ 

   ![วิดีโอเกี่ยวกับการเปิดใช้งานตัวควบคุมการเข้าถึงรายละเอียด](media/service-reports-visual-interactions/drill2.gif)

### <a name="next-steps"></a>ขั้นตอนถัดไป
[วิธีการใช้ตัวกรองรายงาน](power-bi-how-to-report-filter.md)

[ตัวกรองและการทำไฮไลท์ในรายงาน](power-bi-reports-filters-and-highlighting.md)

[Power BI - แนวคิดพื้นฐาน](service-basic-concepts.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


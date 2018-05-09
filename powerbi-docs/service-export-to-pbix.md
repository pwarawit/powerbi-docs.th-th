---
title: วิธีการส่งออกรายงานจากบริการ Power BI ไปยังเดสก์ท็อป (ตัวอย่าง)
description: ดาวน์โหลดรายงานจากบริการ Power BI ไปยังไฟล์ Power BI Desktop
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 0cda094f3104b32f9bad31bf5030e235eb7ce83d
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/09/2018
---
# <a name="export-a-report-from-power-bi-service-to-desktop-preview"></a>ส่งออกรายงานจากบริการ Power BI ไปยังเดสก์ท็อป (ตัวอย่าง)
ใน Power BI Desktop คุณสามารถส่งออก (นอกจากนี้ยังเรียกว่า*ดาวน์โหลด*) รายงานไปยังบริการ Power BI โดยการบันทึกรายงาน และเลือก**เผยแพร่**ได้ คุณสามารถส่งออกในทิศทางอื่นเช่น และดาวน์โหลดรายงานจากบริการ Power BI ลงในเดสก์ท็อปได้ นามสกุลสำหรับไฟล์ที่ถูกส่งออกในทิศทางใดก็ตามคือ *.pbix*

มีข้อจำกัดและข้อควรพิจารณาสองสามข้อ ซึ่งจะมีการกล่าวถึงในบทความนี้ในภายหลัง

![รายการแบบเลื่อนลงของไฟล์](media/service-export-to-pbix/power-bi-file-export.png)

## <a name="download-the-report-as-a-pbix"></a>ดาวน์โหลดรายงานเป็นแบบ .pbix
การดาวน์โหลดไฟล์ .pbix ให้ทำตามขั้นตอนเหล่านี้:

1. ใน**บริการ Power BI** เปิดรายงานที่คุณต้องการดาวน์โหลดใน[มุมมองการแก้ไข](service-reading-view-and-editing-view.md)
2. จากแถบเมนู เลือก**ไฟล์ > ดาวน์โหลดรายงาน**
   
   > [!NOTE]
   > ต้องมีการ[สร้างรายงานขึ้นแล้วโดยใช้ Power BI Desktop](guided-learning/publishingandsharing.yml#step-2) หลังวันที่ 23 พฤศจิกายน 2016 และอัปเดตมาตั้งแต่ตอนนั้นเพื่อที่จะสามารถดาวน์โหลดรายงานได้ ถ้ายังไม่มีการสร้างและอัปเดตดังกล่าว ตัวเลือกเมนูในเมนู*ดาวน์โหลดรายงาน*ในบริการ Power BI จะเป็นสีเทา
   > 
   > 
3. ขณะกำลังสร้างไฟล์ .pbix แบนเนอร์สถานะจะแสดงความคืบหน้า เมื่อไฟล์พร้อม คุณจะถูกขอให้เปิดหรือบันทึกไฟล์ .pbix ชื่อของไฟล์ตรงกับชื่อเรื่องของรายงาน
   
    ![เปิด บันทึก หรือยกเลิก](media/service-export-to-pbix/power-bi-save-pbix.png)
   
    ตอนนี้คุณมีตัวเลือกในการเปิดไฟล์ .pbix ในบริการ Power BI (app.powerbi.com) หรือใน Power BI Desktop     
4. เมื่อต้องการเปิดรายงานในเดสก์ท็อปทันที เลือก**เปิด** เมื่อต้องการบันทึกไฟล์ไปยังตำแหน่งเฉพาะ เลือก**บันทึก > บันทึกเป็น** ถ้าคุณยังไม่มี ให้[ติดตั้ง Power BI Desktop](desktop-get-the-desktop.md)
   
    เมื่อคุณเปิดรายงานในเดสก์ท็อป คุณอาจเห็นข้อความเตือนให้คุณทราบว่า บางคุณลักษณะที่พร้อมใช้งานในรายงานการบริการ Power BI อาจไม่พร้อมใช้งานในเดสก์ท็อป
   
    ![กล่องโต้ตอบคำเตือน](media/service-export-to-pbix/power-bi-export-to-pbix_2.png)

5. ตัวแก้ไขรายงานในเดสก์ท็อปมีลักษณะเหมือนตัวแก้ไขรายงานในบริการ Power BI  
   
    ![ตัวแก้ไขรายงานบนเดสก์ท็อป](media/service-export-to-pbix/power-bi-desktop.png)

## <a name="considerations-and-troubleshooting"></a>ข้อควรพิจารณาและการแก้ไขปัญหา
มีข้อควรพิจารณาและขีดจำกัดที่สำคัญสองสามข้อที่เชื่อมโยงกับการดาวน์โหลด (ส่งออก) เป็น *.pbix* ไฟล์จากบริการ Power BI

* เมื่อต้องดาวน์โหลดไฟล์ คุณต้องสามารถเข้าถึงเพื่อแก้ไขรายงานได้
* ต้องมีการสร้างรายงานขึ้นโดยใช้**Power BI Desktop**และ*เผยแพร่*ไปยัง**บริการ Power BI** หรือต้องมีการ*อัปโหลด* .pbix ไปยังบริการดังกล่าว
* ต้องมีการเผยแพร่หรืออัปเดตรายงานหลังจากวันที่ 23 พฤศจิกายน 2016 รายงานที่เผยแพร่ก่อนวันที่ดังกล่าวจะไม่สามารถดาวน์โหลดได้
* คุณลักษณะนี้จะไม่สามารถใช้งานได้กับรายงานที่สร้างขึ้นใน**บริการ Power BI** รวมถึงชุดเนื้อหาด้วย
* คุณควรใช้เวอร์ชันล่าสุดของ **Power BI Desktop** เสมอเมื่อเปิดไฟล์ที่ดาวน์โหลดแล้ว ไฟล์ *.pbix* ที่ดาวน์โหลดแล้วอาจไม่สามารถเปิดได้ในเวอร์ชันที่ไม่ใช่เวอร์ชั่นปัจจุบันของ**Power BI Desktop**
* หากผู้ดูแลระบบของคุณปิดใช้งานความสามารถในการส่งออกข้อมูล คุณลักษณะนี้จะไม่ปรากฏใน**บริการ Power BI**

## <a name="next-steps"></a>ขั้นตอนถัดไป
ดูวิดีโอความยาวหนึ่งนาที**Guy in a Cube**สำหรับคุณลักษณะนี้:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ymWqU5jiUl0" frameborder="0" allowfullscreen></iframe>

นอกจากนี้ ต่อไปนี้คือบทความเพิ่มเติมที่สามารถช่วยให้คุณเรียนรู้วิธีการใช้**บริการ Power BI**:

* [รายงานใน Power BI](service-reports.md)
* [Power BI - แนวคิดพื้นฐาน](service-basic-concepts.md)

เมื่อคุณได้ติดตั้ง **Power BI Desktop** เนื้อหาต่อไปนี้สามารถช่วยให้คุณเริ่มต้นและใช้งานได้อย่างรวดเร็ว:

* [เริ่มต้นใช้งาน Power BI Desktop](desktop-getting-started.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)   


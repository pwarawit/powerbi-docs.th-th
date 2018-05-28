---
title: การแสดงภาพการ์ด (หรือที่เรียกกันว่า ไทล์จำนวนมาก)
description: สร้างการแสดงภาพการ์ดใน Power BI
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
ms.date: 12/24/2017
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: f38f3bb19be268cba4745c88aa98d09c080c773e
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
---
# <a name="card-visualizations"></a>การแสดงภาพการ์ด
บางครั้งตัวเลขเพียงตัวเดียวก็เป็นสิ่งสำคัญที่สุดที่คุณต้องการติดตามในแดชบอร์ด Power BI หรือรายงานของคุณ เช่น ยอดขายรวม ส่วนแบ่งตลาดแบบปีต่อปี ตลาดแชร์ปีปี หรือโอกาสทั้งหมด แสดงภาพชนิดนี้จะเรียกว่า*การ์ด* เช่นเดียวกับการแสดงภาพดั้งเดิมของ Power BI แทบจะทุกชนิด คุณสามารถสร้างการ์ดขึ้นได้ โดยใช้ตัวแก้ไขรายงาน หรือการถามตอบ

![การแสดงภาพการ์ด](media/power-bi-visualization-card/pbi_opptuntiescard.png)

## <a name="create-a-card-using-the-report-editor"></a>สร้างการ์ดโดยใช้ตัวแก้ไขรายงาน
คำแนะนำเหล่านี้จะใช้ตัวอย่างการวิเคราะห์การค้าปลีก ถ้าต้องการทำตามคำแนะนำดังกล่าว ให้[ดาวน์โหลดตัวอย่าง](sample-datasets.md)สำหรับบริการของ Power BI (app.powerbi.com) หรือ Power BI Desktop   

1. เริ่มต้นจาก[หน้ารายงานว่าง](power-bi-report-add-page.md) แล้วเลือก**ร้านค้า** \> เขตข้อมูล**เปิดจำนวนร้านค้า** ถ้าคุณกำลังใช้บริการของ Power BI ให้ตรวจสอบให้แน่ใจว่าคุณได้เปิดรายงานใน[มุมมองการแก้ไข](service-interact-with-a-report-in-editing-view.md)แล้ว

    Power BI จะสร้างแผนภูมิคอลัมน์ที่มีตัวเลขเพียงตัวเลขเดียว

   ![](media/power-bi-visualization-card/pbi_rptnumbertilechart.png)
2. ในบานหน้าต่างการแสดงภาพ ให้เลือกไอคอนการ์ด

   ![](media/power-bi-visualization-card/pbi_changechartcard.png)
6. โฮเวอร์เหนือการ์ด แล้วเลือกไอคอนหมุด![](media/power-bi-visualization-card/pbi_pintile.png)ที่จะเพิ่มการแสดงภาพไปยังแดชบอร์ด

   ![](media/power-bi-visualization-card/power-bi-pin-icon.png)
7. ปักหมุดไทล์ลงในแดชบอร์ดที่มีอยู่ หรือแดชบอร์ดใหม่

   * แดชบอร์ดที่มีอยู่: เลือกชื่อของแดชบอร์ดจากรายการแบบหล่นลง
   * แดชบอร์ดใหม่: พิมพ์ชื่อของแดชบอร์ดใหม่
8. เลือก**หมุด**

   ข้อความการดำเนินการสำเร็จ (ใกล้กับมุมบนขวา) ช่วยให้คุณทราบว่าได้เพิ่มการแสดงภาพเป็นไทล์ ลงในแดชบอร์ดของคุณแล้ว

   ![](media/power-bi-visualization-card/power-bi-pin-success-message.png)
9. เลือก**ไปยังแดชบอร์ด** ในส่วนนี้ คุณสามารถ[แก้ไขและย้าย](service-dashboard-edit-tile.md)การแสดงภาพที่ปักหมุดไว้ได้


## <a name="create-a-card-from-the-qa-question-box"></a>สร้างการ์ดจากกล่องคำถามการถามตอบ
กล่องคำถามการถามตอบเป็นวิธีที่ง่ายที่สุดในการสร้างการ์ด กล่องคำถามการถามตอบจะพร้อมใช้งานในบริการของ Power BI (app.powerbi.com) จากแดชบอร์ดหรือรายงาน ขั้นตอนด้านล่างนี้จะอธิบายถึงวิธีการสร้างการ์ดจากแดชบอร์ดบริการของ Power BI ถ้าคุณต้องการสร้างการ์ดโดยใช้การถามตอบใน Power BI Desktop [ให้ทำตามคำแนะนำเหล่านี้](https://powerbi.microsoft.com/en-us/blog/power-bi-desktop-december-feature-summary/#QandA)เกี่ยวกับการแสดงตัวอย่างการถามตอบสำหรับรายงานของ Desktop

1. สร้าง[แดชบอร์ด](service-dashboards.md)แล้ว[รับข้อมูล](service-get-data.md) ตัวอย่างนี้จะใช้[ตัวอย่างการวิเคราะห์โอกาส](sample-opportunity-analysis.md)

1. ที่ด้านบนในแดชบอร์ดของคุณ ให้เริ่มพิมพ์สิ่งที่คุณต้องการทราบเกี่ยวกับข้อมูลของคุณในกล่องคำถาม 

   ![](media/power-bi-visualization-card/power-bi-q-and-a-box.png)

>**เคล็ดลับ**: ในส่วนรายงานของบริการของ Power BI ใน[มุมมองการแก้ไข](service-reading-view-and-editing-view.md) ให้เลือก**ถามคำถาม**จากแถบเมนูด้านบน ในส่วนรายงานของ Power BI Desktop ให้หาพื้นที่ว่างบางตำแหน่งในรายงาน แล้วดับเบิลคลิกเพื่อเปิดกล่องคำถาม

3. ตัวอย่างเช่น พิมพ์ "จำนวนโอกาส" ในกล่องคำถาม

   ![](media/power-bi-visualization-card/power-bi-q-and-a.png)

   กล่องคำถามจะคอยช่วยเหลือคุณ โดยจะมีคำแนะนำรวมทั้งการกล่าวซ้ำ และสุดท้ายก็จะแสดงจำนวนรวม  
4. เลือกไอคอนหมุด![](media/power-bi-visualization-card/pbi_pintile.png)ในมุมขวาบที่จะเพิ่มการ์ดไปยังแดชบอร์ด

   ![](media/power-bi-visualization-card/power-bi-pin.png)
5. ปักหมุดการ์ดเป็นไทล์ลงในแดชบอร์ดที่มีอยู่ หรือแดชบอร์ดใหม่

   * แดชบอร์ดที่มีอยู่: เลือกชื่อของแดชบอร์ดจากรายการแบบหล่นลง ตัวเลือกของคุณจะถูกจำกัดให้ใช้งานเฉพาะกับแดชบอร์ดดังกล่าวภายในพื้นที่ทำงานปัจจุบัน
   * แดชบอร์ดใหม่: พิมพ์ชื่อของแดชบอร์ดใหม่ แล้วจะได้รับการเพิ่มไปยังพื้นที่ทำงานปัจจุบันของคุณ
6. เลือก**หมุด**

   ข้อความการดำเนินการสำเร็จ (ใกล้กับมุมบนขวา) ช่วยให้คุณทราบว่าได้เพิ่มการแสดงภาพเป็นไทล์ ลงในแดชบอร์ดของคุณแล้ว  

   ![](media/power-bi-visualization-card/power-bi-success.png)
7. เลือก**ไปยังแดชบอร์ด** เมื่อต้องการดูไทล์ใหม่ ในส่วนนั้น คุณก็สามารถ[เปลี่ยนชื่อ ปรับขนาด เพิ่มการเชื่อมโยงหลายมิติ และจัดตำแหน่งไทล์ใหม่ และอื่นๆ](service-dashboard-edit-tile.md) ในแดชบอร์ดของคุณได้

   ![](media/power-bi-visualization-card/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>ข้อควรพิจารณาและการแก้ไขปัญหา
- ถ้าคุณไม่สามารถเห็นกล่องคำถามทั้งหมด โปรดติดต่อผู้ดูแลระบบหรือผู้ดูแลผู้เช่าของคุณ    
- ถ้าคุณกำลังใช้ Desktop และการดับเบิลคลิกพื้นที่ว่างในรายงานไม่สามารถเปิดการถามตอบได้ คุณก็อาจจะต้องเปิดใช้งานการถามตอบดังกล่าว  เลือก**ไฟล์ > ตัวเลือกและการตั้งค่า > ตัวเลือก > คุณลักษณะการแสดงตัวอย่าง > การถามตอบ**และรีสตาร์ต Desktop


## <a name="next-steps"></a>ขั้นตอนถัดไป
[ไทล์แดชบอร์ดใน Power BI](service-dashboard-tiles.md)

[แดชบอร์ดใน Power BI](service-dashboards.md)

[Power BI - แนวคิดพื้นฐาน](service-basic-concepts.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)

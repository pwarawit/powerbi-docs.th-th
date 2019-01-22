---
title: กล่องข้อความและรูปร่างในรายงาน Power BI
description: เอกสารประกอบเกี่ยวกับการเพิ่มและสร้างกล่องข้อความ และรูปร่างในรายงานโดยใช้ Microsoft Power BI service
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: _3q6VEBhGew
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 03/22/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 937e15f5cd56f7c720afa945598f9fc1641468f7
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54295546"
---
# <a name="static-content-in-power-bi-reports"></a>เนื้อหาคงที่ในรายงาน Power BI
สามารถเพิ่มกล่องข้อความและรูปร่าง ลงในรายงานโดยใช้บริการ Power BI service และ Power BI Desktop ในทั้งสองกรณี คุณต้องแก้ไขสิทธิ์สำหรับรายงาน ถ้ารายงานมีการแชร์ให้กับคุณในบริการของ Power BI คุณจะไม่ได้สิทธิ์การแก้ไข 

Watch Will ใช้ Power BI Desktop เพื่อ[เพิ่มรูปภาพแบบคงที่ไปยังรายงาน](guided-learning/visualizations.yml?tutorial-step=11)แล้ว ทำตามขั้นตอนด้านล่างเพื่อลองใช้ Power BI service แทน
> 
> <iframe width="560" height="315" src="https://www.youtube.com/embed/_3q6VEBhGew" frameborder="0" allowfullscreen></iframe>
> 

## <a name="add-a-text-box-to-a-report"></a>เพิ่มกล่องข้อความไปยังรายงาน
1. เปิดรายงานในมุมมองการแก้ไข

2. วางเคอร์เซอร์ของคุณในพื้นที่ว่างบนพื้นที่รายงาน และให้เลือก**กล่องข้อความ**
   
   ![](media/power-bi-reports-add-text-and-shapes/pbi_textbox.png)
2. พิมพ์ข้อความของคุณลงในกล่องข้อความ รวมทั้ง รูปแบบฟอนต์ สี และการจัดแนวข้อความ 
   
   ![](media/power-bi-reports-add-text-and-shapes/pbi_textbox2new.png)
3. การจัดตำแหน่งกล่องข้อความ ให้เลือกพื้นที่สีเทาที่ด้านบนแล้วลาก และเมื่อต้องการปรับขนาดกล่องข้อความ เลือกแล้วลากจุดเค้าร่าง 
   
   ![](media/power-bi-reports-add-text-and-shapes/textboxsmaller.gif)

4. ด้วยกล่องข้อความที่เลือก เพิ่มการจัดรูปแบบเพิ่มเติมในบานหน้าต่างการแสดงภาพ ในตัวอย่างนี้ เราได้จัดรูปแบบพื้นหลังและเส้นขอบ คุณยังสามารถสร้างเป็นขนาดที่แน่นอนและตำแหน่งของกล่องข้อความ  

   ![](media/power-bi-reports-add-text-and-shapes/power-bi-borders.png)

5. เพื่อปิดกล่องข้อความ เลือกพื้นที่ว่างบนพื้นที่รายงาน 

5. เลือกไอคอนหมุด![](media/power-bi-reports-add-text-and-shapes/pbi_pintile.png)เพื่อปักหมุดกล่องข้อความไปยังแดชบอร์ด 

## <a name="add-a-shape-to-a-report"></a>เพิ่มรูปร่างไปยังรายงาน
1. วางเคอร์เซอร์ของคุณที่ใดก็ได้บนพื้นที่รายงาน แล้วเลือก**รูปร่าง**
   
   ![](media/power-bi-reports-add-text-and-shapes/power-bi-shapes.png)
2. จากดร๊อปดาวน์ เลือกรูปร่างเพื่อเพิ่มในพื้นที่รายงานของคุณ ลองเพิ่มลูกศรเพื่อดึงดูดความสนใจไปแผนภูมิฟองแปรปรวนของยอดขายสูงสุด 
   
   ในบานหน้าต่าง**จัดรูปแบบรูปร่าง** ให้ปรับแต่งรูปร่างของคุณ ในตัวอย่างนี้ เราได้สร้างเป็นลูกศรสีแดงมีขอบสีแดงเข้ม ถูกหมุน 90 องศา
   
   ![](media/power-bi-reports-add-text-and-shapes/power-bi-arrrow.png)
3. เพื่อจัดตำแหน่งรูปร่าง ให้เลือกพื้นที่สีเทาที่ด้านบนและลาก และเมื่อต้องการปรับขนาดกล่องข้อความ เลือกและลากจุดเค้าร่างใดๆก็ได้ เหมือนในหนังสือ คุณยังสามารถสร้างเป็นขนาดที่แน่นอนและตำแหน่งของกล่องข้อความ

> **หมายเหตุ**: รูปร่างที่ไม่สามารถปักหมุดที่ยังแดชบอร์ดได้ ยกเว้นเป็นหนึ่งภาพเมื่อคุณ[ปักหมุดหน้าสด](service-dashboard-pin-live-tile-from-report.md) 
> 
> 

### <a name="next-steps"></a>ขั้นตอนถัดไป
[เพิ่มไฮเปอร์ลิงก์ให้กล่องข้อความ](service-add-hyperlink-to-text-box.md)

[Power BI แนวคิดพื้นฐาน](consumer/end-user-basic-concepts.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)

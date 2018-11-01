---
title: วิชวล KPI
description: สร้างวิชวล KPI ใน Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: xmja6EpqaO0
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: tutorial
ms.date: 09/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: aec8bc2d7faa8d3c4b9c7b4eb69ed9a930cfbcd1
ms.sourcegitcommit: ce8332a71d4d205a1f005b703da4a390d79c98b6
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/27/2018
ms.locfileid: "47417245"
---
# <a name="kpi-visuals"></a>วิชวล KPI
ดัชนีประสิทธิภาพหลัก (KPI) เป็นภาพสัญลักษณ์ที่แสดงปริมาณความก้าวหน้าของงานที่ทำเพื่อมุ่งไปยังเป้าหมายที่วัดผลได้ สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ KPI ดู [Microsoft Developer Network](https://msdn.microsoft.com/library/hh272050)

ถ้าคุณไม่ได้ลงทะเบียน Power BI ให้[ลงทะเบียนรุ่นทดลองใช้ฟรี](https://app.powerbi.com/signupredirect?pbi_source=web)ก่อนที่คุณจะเริ่มต้นใช้งาน

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
* [Power BI Desktop - ฟรี!](https://powerbi.microsoft.com/en-us/get-started/)
* [ไฟล์ PBIX ตัวอย่างการวิเคราะห์การขายปลีก](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)

## <a name="when-to-use-a-kpi"></a>เมื่อต้องการใช้ KPI
KPI เป็นตัวเลือกที่ดีที่สุด:

* เมื่อต้องวัดความคืบหน้า (ฉันอยู่ข้างหน้าหรือข้างหลังสิ่งใด)
* เมื่อวัดระยะห่างจากเป้าหมาย (ฉันอยู่ห่างจากเป้าหมายหรือห่างจากจุดเริ่มเท่าใด)   

## <a name="kpi-requirements"></a>ข้อกำหนดของ KPI
ดัชนีประสิทธิภาพหลัก (KPI) อิงกับการวัดเฉพาะและถูกออกแบบมาเพื่อช่วยให้คุณประเมินค่าและสถานะปัจจุบันเมื่อเทียบกับเป้าหมายที่กำหนด ดังนั้น ภาพ KPI จำเป็นต้องมีการวัด*พื้นฐาน*ที่ประเมินเป็นค่าและการวัดหรือค่า*เป้าหมาย* และ*ค่าเกณฑ์*หรือ*จุดหมาย*.

ในปัจจุบัน ชุดข้อมูล KPI จำเป็นต้องประกอบด้วยค่าเป้าหมายสำหรับ KPI ถ้าชุดข้อมูลของคุณไม่ประกอบด้วยค่าเป้าหมาย คุณสามารถสร้างค่าเป้าหมายโดยการเพิ่มแผ่นงาน Excel ที่แสดงค่าเป้าหมาย ให้กับรูปแบบข้อมูลหรือไฟล์ PBIX ของคุณ


## <a name="how-to-create-a-kpi"></a>วิธีการสร้าง KPI
เมื่อต้องการทำตามขั้นตอน เปิด[ไฟล์ .PBIX วิเคราะห์การค้าปลีก](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)ใน Power BI Desktop เราจะสร้าง KPI ที่วัดความคืบหน้าที่เราได้ทำเพื่อบรรลุเป้าหมายยอดขาย

หรือดู วิธีที่คุณสามารถสร้างภาพการวัดตัวเดียว: ตัวประเมิน บัตร และ KPI

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. เปิดรายงานในมุมมองรายงาน และ[เลือกแท็บสีเหลืองเพื่อเพิ่มหน้าใหม่](../power-bi-report-add-page.md)    
2. จากบานหน้าต่างเขตข้อมูล ให้เลือก**ยอดขาย > หน่วยรวมปีนี้**  ซึ่งจะเป็นตัวดัชนี
3. เพิ่ม**เวลา > เดือนการเงิน**  เพื่อแสดงแนวโน้ม
4. สิ่งสำคัญ: เรียงลำดับแผนภูมิตาม**เดือนงบประมาณ** เมื่อคุณแปลงการแสดงภาพเป็น KPI จึงไม่มีตัวเลือกการเรียงลำดับ

    ![](media/power-bi-visualization-kpi/power-bi-chart.png)
5. แปลงภาพเป็น KPI โดยเลือกไอคอน KPI จากบานหน้าต่างการแสดงภาพ
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi-template.png)
6. เพิ่มเป้าหมาย เพิ่มยอดขายของปีล่าสุดเป็นเป้าหมาย ลาก**หน่วยรวมปีที่แล้ว**ไปยังเขตข้อมูล**เป้าหมาย**
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi-done.png)
7. อีกทางหนึ่งคือ จัดรูปแบบ KPI โดยเลือกไอคอน ลูกกลิ้งทาสี เพื่อเปิดบานหน้าต่างการจัดรูปแบบ
   
   * **ตัวดัชนี** - ควบคุมหน่วยแสดงผลของตัวดัชนีและตำแหน่งทศนิยม
   * **แกนแนวโน้ม** - เมื่อตั้งค่าเป็น**เปิด** แกนแนวโน้มจะถูกแสดงเป็นพื้นหลังของภาพ KPI  
   * **เป้าหมาย** - เมื่อตั้งค่าเป็น**เปิด** ภาพจะแสดงเป้าหมายและระยะห่างจากเป้าหมายเป็นเปอร์เซ็นต์
   * **รหัสสี > ทิศทาง** - บาง KPI จะถูกถือว่า*ดีขึ้น*เมื่อมีค่าสูงขึ้นและบาง KPI จะถูกถือว่า*ดีขึ้น*เมื่อมีค่าต่ำลง ตัวอย่างเช่น กำไรเทียบกับเวลารอ โดยทั่วไปแล้ว กำไรที่สูงขึ้นจะดีกว่าเมื่อเทียบกับค่าสูงขึ้นของเวลารอ เลือก**สูงขึ้นดีกว่า**และเลือกเปลี่ยนการตั้งค่าสีได้


KPI จะพร้อมใช้งาน ในบริการของ Power BI และบนอุปกรณ์เคลื่อนที่ของคุณ เพื่อช่วยให้คุณเชื่อมต่อกับธุรกิจสำคัญของคุณเสมอ

## <a name="considerations-and-troubleshooting"></a>ข้อควรพิจารณาและการแก้ไขปัญหา
* ถ้า KPI ของคุณไม่มีลักษณะคล้ายกับด้านบน อาจเป็นเพราะคุณจำเป็นต้องเรียงลำดับตามเดือนทางบัญชี เนื่องจาก KPI ไม่มีตัวเลือกการเรียงลำดับ คุณจะต้องเรียงลำดับตามเดือนทางบัญชี*ก่อน*คุณแปลงภาพของคุณเป็น KPI

## <a name="next-steps"></a>ขั้นตอนถัดไป

[แผนที่พื้นฐานใน Power BI](power-bi-map-tips-and-tricks.md)

[ชนิดการแสดงภาพใน Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
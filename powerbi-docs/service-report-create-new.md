---
title: 'สอนสร้างรายงานใหม่จากชุดข้อมูล '
description: สร้างรายงาน Power BI ใหม่จากชุดข้อมูล
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: monitoring
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 7da16deb3e5919d509a5cbbb7fd845914c8c4ea4
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/09/2018
---
# <a name="create-a-new-power-bi-report-by-importing-a-dataset"></a>สร้างรายงาน Power BI ใหม่จากชุดข้อมูลนำเข้า
คุณได้อ่าน[รายงานใน Power BI](service-reports.md)และตอนนี้ คุณต้องการสร้างรายงานของคุณเอง มีวิธีในสร้างรายงานหลายวิธี และในบทความนี้เราจะเริ่มต้น โดยการสร้างรายงานพื้นฐานมากจากชุดข้อมูล Excel เมื่อคุณทำความเข้าใจพื้นฐานของการสร้างรายงาน การ**ขั้นตอนถัดไป**ที่ด้านล่างจะพาคุณไปยังหัวข้อการรายงานขั้นสูงเพิ่มเติม  

> **เคล็ดลับ**: เมื่อต้องการสร้างรายงาน โดยการคัดลอกรายงานที่มีอยู่ ดู[คัดลอกรายงาน](power-bi-report-copy.md)
> 
### <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
- Power BI บริการ (สำหรับการสร้างรายงานโดยใช้ Power BI Desktop ดู[มุมมองรายงานบนเดสก์ท็อป](desktop-report-view.md)   
- ตัวอย่างการวิเคราะห์การค้าปลีก

## <a name="import-the-dataset"></a>นำเข้าชุดข้อมูล
วิธีการสร้างรายงานนี้เริ่มต้น ด้วยชุดข้อมูลและพื้นที่ว่างเปล่ารายงานว่างเปล่า เมื่อต้องติดตาม[ดาวน์โหลดชุดข้อมูล Excel ตัวอย่างการวิเคราะห์ร้านค้าปลีก](http://go.microsoft.com/fwlink/?LinkId=529778)และบันทึกไปยัง OneDrive for Business (ที่ต้องการ) หรือภายในเครื่อง

1. เราจะสร้างรายงานในพื้นที่ทำงานบริการ Power BI ดังนั้นให้เลือกพื้นที่ทำงานมีอยู่ หรือสร้างขึ้นใหม่
   
   ![รายการพื้นที่ทำงานแอป](media/service-report-create-new/power-bi-workspaces2.png)
2. จากด้านล่างของ navpane ซ้าย เลือก**รับข้อมูล**
   
   ![รับข้อมูล](media/service-report-create-new/power-bi-get-data3.png)
3. เลือก**แฟ้ม**และนำทางไปยังตำแหน่งที่คุณบันทึกตัวอย่างการวิเคราะห์ร้านค้าปลีก
   
    ![เลือกไฟล์](media/service-report-create-new/power-bi-select-files.png)
4. สำหรับการดำเนินการนี้ เลือก**นำเข้า**
   
   ![เลือกนำเข้า](media/service-report-create-new/power-bi-import.png)
5. หลังจากที่ชุดข้อมูลจะถูกนำเข้า เลือก**ชุดข้อมูลมุมมอง**
   
   ![ดูชุดข้อมูล](media/service-report-create-new/power-bi-view-dataset.png)
6. ดูชุดข้อมูลที่เปิดตัวแก้ไขรายงานจริงขึ้น  คุณจะเห็นรายงานเครื่องมือการแก้ไขและพื้นที่ว่างเปล่า
   
   ![ตัวแก้ไขรายงาน](media/service-report-create-new/power-bi-blank-report.png)

> **เคล็ดลับ**: ถ้าคุณไม่คุ้นเคยกับรายงานพื้นที่แก้ไข หรือต้องการการทบทวน[ชมการแนะนำของตัวแก้ไขรายงาน](service-the-report-editor-take-a-tour.md)ก่อนดำเนินการต่อ
> 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>เพิ่มการวัดรัศมีลงในรายงาน
หลังจากที่ชุดข้อมูลของเราจะถูกนำเข้า มาเริ่มต้นการตอบคำถามบางอย่าง  เราหัวหน้าฝ่ายตลาดเจ้าหน้าที่ (CMO) ต้องการทราบเกี่ยวกับวิธีปิดเราที่การประชุมเป้าหมายการขายของปีนี้ การวัดจะเป็น[ตัวเลือกการแสดงภาพที่ดี](power-bi-report-visualizations.md)สำหรับการแสดงข้อมูลชนิดนี้

1. ในบานหน้าต่างเขตข้อมูล เลือก**ยอดขาย** > **ค่ายอดขายของปี** > **นี้**
   
    ![แผนภูมิคอลัมน์ในตัวแก้ไขรายงาน](media/service-report-create-new/power-bi-report-step1.png)
2. แปลงภาพเป็นการวัด โดยการเลือกเทมเพลวัด![ไอคอนตัววัด](media/service-report-create-new/powerbi-gauge-icon.png)จาก**แสดงภาพ**บานหน้าต่าง
   
    ![ภาพแผนที่ในตัวแก้ไขรายงาน](media/service-report-create-new/power-bi-report-step2.png)
3. ลาก**ยอดขาย** > **เป้าหมายยอดขาย** > **ของปีนี้**เพื่อ**ค่าเป้าหมาย**กัน ดูเหมือนว่าเรากำลังใกล้เคียงกับเป้าหมายของเรามาก
   
    ![ตัววัดแบบภาพ ด้วยเป้าหมายเป็นค่าเป้าหมาย](media/service-report-create-new/power-bi-report-step3.png)
4. ในตอนนี้เป็นเวลาที่เหมาะสม[บันทึกรายงานของคุณ](service-report-save.md)
   
   ![เมนูไฟล์](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>เพิ่มชาร์ตพื้นที่และ slicer ในรายงาน
CMO ของเรามีคำถามบางอย่างเพิ่มเติมให้แก่เรา เธอต้องการทราบข้อมูลการขายปีนีเมื่อ้เปรียบเทียบกับปีที่แล้ว และเธอต้องการดูโดยการค้นหาด้วยเขตอำเภอ

1. ก่อนอื่น มาสร้างพื้นที่ว่างในพื้นที่รายงานก่อน เลือกตัววัด และย้ายไปมุมบนขวา จากนั้น จับ และลากมุมหนึ่ง และทำให้เล็กลง
2. ยกเลิกเลือกตัววัด ในบานหน้าต่างเขตข้อมูล เลือก**ยอดขาย** > **ค่ายอดขายของปีนี้** > **นี้**เลือก**ขาย** >  **ยอดขายของปีที่แล้ว**
   
    ![ตัวแก้ไขรายงาน ด้วยตัววัดและแผนภูมิแท่ง](media/service-report-create-new/power-bi-report-step4.png)
3. แปลงภาพเป็นการวัด โดยการเลือกเทมเพลวัด![ไอคอนตัววัด](media/service-report-create-new/power-bi-areachart-icon.png)จาก**แสดงภาพ**บานหน้าต่าง
4. เลือก**เวลา** > **รอบระยะเวลา**เพื่อเพิ่มไปยัง**แกน**กัน
   
    ![ตัวแก้ไขรายงาน ด้วยแผนภูมิพื้นที่ที่ใช้งานอยู่](media/service-report-create-new/power-bi-report-step5.png)
5. เมื่อต้องการเรียงลำดับการแสดงภาพ โดยรอบระยะเวลา เลือกจุดไข่ปลา แล้วเลือก**เรียงลำดับตามระยะเวลา**
6. ตอนนี้มาเพิ่มตัวแบ่งส่วนข้อมูล เลือกพื้นที่ว่างบนพื้นที่รายงาน และเลือกตัวแบ่งส่วนข้อมูล ![ไอคอนตัวแบ่งส่วนข้อมูล](media/service-report-create-new/power-bi-slicer-icon.png)    แม่แบบ เพิ่มตัวแบ่งส่วนข้อมูลที่ว่างเปล่าเมื่อต้องการพื้นที่ของเรา
   
    ![พื้นที่รายงาน](media/service-report-create-new/power-bi-report-step6.png)    
7. จากบานหน้าต่างเขตข้อมูล เลือก**เขต** > **เขต** ย้าย และปรับขนาดตัวแบ่งส่วนข้อมูล
   
    ![ตัวแก้ไขรายงาน เพิ่มเขต](media/service-report-create-new/power-bi-report-step7.png)  
8. ใช้ตัวแบ่งส่วนข้อมูลเพื่อค้นหารูปแบบและข้อมูลเชิงลึก โดยเขต
   
   ![วิดีโอของการใช้ตัวแบ่งส่วนข้อมูล](media/service-report-create-new/power-bi-slicer-video2.gif)  

สำรวจข้อมูลของคุณ และเพิ่มการแสดงภาพต่อไป เมื่อคุณค้นหาข้อมูลเชิงลึกที่น่าสนใจโดยเฉพาะอย่างยิ่ง[ปักหมุดเหล่านั้นไปยังแดชบอร์ด](service-dashboard-pin-tile-from-report.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [เพิ่มหน้าใหม่ลงในรายงาน](power-bi-report-add-page.md)  
* เรียนรู้วิธีการ[ปักหมุดภาพไปยังแดชบอร์ด](service-dashboard-pin-tile-from-report.md)   
* มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)

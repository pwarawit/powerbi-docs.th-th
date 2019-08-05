---
title: สร้างรายงานจากชุดข้อมูล
description: สร้างรายงาน Power BI จากชุดข้อมูล
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: f2d9046c907b78ce2c1bb2754007c34199877a08
ms.sourcegitcommit: f05ba39a0e46cb9cb43454772fbc5397089d58b4
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/26/2019
ms.locfileid: "68523078"
---
# <a name="create-a-report-in-the-power-bi-service-by-importing-a-dataset"></a>สร้างรายงานในบริการของ Power BI โดยการนำเข้าชุดข้อมูล
คุณได้อ่าน[รายงานใน Power BI](consumer/end-user-reports.md)และตอนนี้ คุณต้องการสร้างรายงานของคุณเอง มีหลายวิธีในการสร้างรายงาน ในบทความนี้เราจะเริ่มต้นด้วยการสร้างรายงานพื้นฐานในบริการของ Power BI จากชุดข้อมูล Excel เมื่อคุณทำความเข้าใจพื้นฐานของการสร้างรายงาน ตรวจดู[ขั้นตอนถัดไป](#next-steps)ที่ด้านล่างสำหรับหัวข้อการรายงานขั้นสูงเพิ่มเติม  

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
- [ลงทะเบียนสำหรับบริการของ Power BI](service-self-service-signup-for-power-bi.md) สำหรับการสร้างรายงานโดยใช้ Power BI Desktop ให้ดู [มุมมองรายงานบนเดสก์ท็อป](desktop-report-view.md) 
- [ดาวน์โหลดชุดข้อมูล Excel ตัวอย่างการวิเคราะห์ร้านค้าปลีก](http://go.microsoft.com/fwlink/?LinkId=529778)และบันทึกไปยัง OneDrive for Business หรือภายในเครื่อง

## <a name="import-the-dataset"></a>นำเข้าชุดข้อมูล
วิธีการสร้างรายงานนี้เริ่มต้น ด้วยชุดข้อมูลและพื้นที่ว่างเปล่ารายงานว่างเปล่า คุณสามารถทำตามชุดข้อมูล Excel ตัวอย่างของการวิเคราะห์ร้านค้าปลีก

1. เราจะสร้างรายงานในพื้นที่ทำงานบริการของ Power BI ดังนั้นให้เลือกพื้นที่ทำงานมีอยู่หรือสร้างขึ้นใหม่
   
   ![รายการพื้นที่ทำงานแอป](media/service-report-create-new/power-bi-workspaces2.png)
2. จากด้านล่างของบานหน้าต่างพื้นที่นำทางด้านซ้าย เลือก **รับข้อมูล**
   
   ![รับข้อมูล](media/service-report-create-new/power-bi-get-data3.png)
3. เลือก**แฟ้ม**และนำทางไปยังตำแหน่งที่คุณบันทึกตัวอย่างการวิเคราะห์ร้านค้าปลีก
   
    ![เลือกไฟล์](media/service-report-create-new/power-bi-select-files.png)
4. สำหรับการดำเนินการนี้ เลือก**นำเข้า**
   
   ![เลือกนำเข้า](media/service-report-create-new/power-bi-import.png)
5. หลังจากที่ชุดข้อมูลจะถูกนำเข้า เลือก**ชุดข้อมูลมุมมอง**
   
   ![ดูชุดข้อมูล](media/service-report-create-new/power-bi-view-dataset.png)
6. ดูชุดข้อมูลที่เปิดตัวแก้ไขรายงานจริงขึ้น  คุณจะเห็นรายงานเครื่องมือการแก้ไขและพื้นที่ว่างเปล่า
   
   ![ตัวแก้ไขรายงาน](media/service-report-create-new/power-bi-blank-report.png)

> [!TIP]
> ถ้าคุณไม่คุ้นเคยกับรายงานพื้นที่แก้ไข หรือต้องการการทบทวน [ชมการแนะนำของตัวแก้ไขรายงาน](service-the-report-editor-take-a-tour.md)ก่อนดำเนินการต่อ 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>เพิ่มการวัดรัศมีลงในรายงาน
หลังจากที่ชุดข้อมูลของเราจะถูกนำเข้า มาเริ่มต้นการตอบคำถามบางอย่าง  เราหัวหน้าฝ่ายตลาดเจ้าหน้าที่ (CMO) ต้องการทราบเกี่ยวกับวิธีปิดเราที่การประชุมเป้าหมายการขายของปีนี้ การวัดจะเป็น[ตัวเลือกการแสดงภาพที่ดี](visuals/power-bi-report-visualizations.md)สำหรับการแสดงข้อมูลชนิดนี้

1. ในบานหน้าต่างเขตข้อมูล เลือก**ยอดขาย** > **ค่ายอดขายของปี** > **นี้**
   
    ![แผนภูมิคอลัมน์ในตัวแก้ไขรายงาน](media/service-report-create-new/power-bi-report-step1.png)
2. แปลงภาพเป็นการวัด โดยการเลือกเทมเพลวัด![ไอคอนตัววัด](media/service-report-create-new/powerbi-gauge-icon.png)จาก**หน้าต่าง**แสดงภาพ
   
    ![ภาพแผนที่ในตัวแก้ไขรายงาน](media/service-report-create-new/power-bi-report-step2.png)
3. ลาก**ยอดขาย** > **เป้าหมายยอดขาย** > **ของปีนี้**เพื่อ**ค่าเป้าหมาย**กัน ดูเหมือนว่าเรากำลังใกล้เคียงกับเป้าหมายของเรามาก
   
    ![ตัววัดแบบภาพ ด้วยเป้าหมายเป็นค่าเป้าหมาย](media/service-report-create-new/power-bi-report-step3.png)
4. ในตอนนี้เป็นเวลาที่เหมาะสมที่จะบันทึกรายงานของคุณ
   
   ![เมนูไฟล์](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>เพิ่มชาร์ตพื้นที่และ slicer ในรายงาน
CMO ของเรามีคำถามบางอย่างเพิ่มเติมให้แก่เรา พวกเขาต้องการทราบวิธีการเปรียบเทียบยอดขายของปีนี้กับปีที่แล้ว และพวกเขาต้องการดูผลลัพธ์ตามเขต

1. ก่อนอื่น มาสร้างพื้นที่ว่างในพื้นที่รายงานก่อน เลือกตัววัด และย้ายไปมุมบนขวา จากนั้น จับ และลากมุมหนึ่ง และทำให้เล็กลง
2. ยกเลิกเลือกตัววัด ในบานหน้าต่างเขตข้อมูล เลือก**ยอดขาย** > **ค่ายอดขายของปีนี้** > **นี้**เลือก**ขาย** >  **ยอดขายของปีที่แล้ว**
   
    ![ตัวแก้ไขรายงาน ด้วยตัววัดและแผนภูมิแท่ง](media/service-report-create-new/power-bi-report-step4.png)
3. แปลงภาพเป็นแผนภูมิพื้นที่โดยเลือกเทมเพลตแผนภูมิพื้นที่![
ไอคอนแผนภูมิ](media/service-report-create-new/power-bi-areachart-icon.png)จาก**หน้าต่าง**แสดงภาพ
4. เลือก**เวลา** > **รอบระยะเวลา**เพื่อเพิ่มไปยัง**แกน**กัน
   
    ![ตัวแก้ไขรายงาน ด้วยแผนภูมิพื้นที่ที่ใช้งานอยู่](media/service-report-create-new/power-bi-report-step5.png)
5. เมื่อต้องการเรียงลำดับการแสดงภาพ โดยรอบระยะเวลา เลือกจุดไข่ปลา แล้วเลือก**เรียงลำดับตามระยะเวลา**
6. ตอนนี้มาเพิ่มตัวแบ่งส่วนข้อมูล เลือกพื้นที่ว่างบนพื้นที่รายงาน และเลือกตัวแบ่งส่วนข้อมูล ![ไอคอนตัวแบ่งส่วนข้อมูล](media/service-report-create-new/power-bi-slicer-icon.png) แม่แบบ ตอนนี้เรามีตัวแบ่งส่วนข้อมูลที่ว่างเปล่าบนพื้นที่ทำงานของเรา
   
    ![พื้นที่รายงาน](media/service-report-create-new/power-bi-report-step6.png)    
7. จากบานหน้าต่างเขตข้อมูล เลือก**เขต** > **เขต** ย้าย และปรับขนาดตัวแบ่งส่วนข้อมูล
   
    ![ตัวแก้ไขรายงาน เพิ่มเขต](media/service-report-create-new/power-bi-report-step7.png)  
8. ใช้ตัวแบ่งส่วนข้อมูลเพื่อค้นหารูปแบบและข้อมูลเชิงลึก โดยเขต
   
   ![วิดีโอของการใช้ตัวแบ่งส่วนข้อมูล](media/service-report-create-new/power-bi-slicer-video2.gif)  

สำรวจข้อมูลของคุณ และเพิ่มการแสดงภาพต่อไป เมื่อคุณค้นหาข้อมูลเชิงลึกที่น่าสนใจโดยเฉพาะอย่างยิ่ง[ปักหมุดเหล่านั้นไปยังแดชบอร์ด](service-dashboard-pin-tile-from-report.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป

* เรียนรู้วิธีการ[ปักหมุดภาพไปยังแดชบอร์ด](service-dashboard-pin-tile-from-report.md)   
* มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


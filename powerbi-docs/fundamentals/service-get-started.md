---
title: เริ่มต้นใช้งานกับบริการ Power BI
description: เริ่มต้นใช้งานบริการออนไลน์ Power BI (app.powerbi.com)
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: tutorial
ms.date: 09/05/2019
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: 67bb913f582b372d2c9ffcbe72a59aeade143fac
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83358771"
---
# <a name="tutorial-get-started-with-the-power-bi-service"></a>บทช่วยสอน: เริ่มต้นใช้งานกับบริการ Power BI
บทช่วยสอนนี้เป็นการแนะนำคุณสมบัติการทำงานบางรายการของ*บริการของ Power BI* ในบทช่วยสอนนี้ คุณจะได้เชื่อมต่อกับข้อมูล สร้างรายงานและแดชบอร์ด และถามคำถามต่าง ๆ เกี่ยวกับข้อมูลของคุณ คุณสามารถทำสิ่งต่าง ๆ ได้มากมายด้วยบริการของ Power BI บทช่วยสอนนี้เป็นเพียงการทำงานเบื้องต้นสำหรับคุณเท่านั้น เพื่อทำความเข้าใจว่าบริการ Power BI นั้นเหมาะสมกับข้อเสนอ Power BI อื่นๆ อย่างไร เราขอแนะนำให้คุณอ่านเรื่อง [Power BI คืออะไร](power-bi-overview.md)

![หน้าหลักบริการของ Power BI](media/service-get-started/power-bi-service-get-started-home.png)

ในบทช่วยสอนนี้ คุณจะทำขั้นตอนต่อไปนี้ให้เสร็จสมบูรณ์:

> [!div class="checklist"]
> * ลงชื่อเข้าใช้บัญชีออนไลน์ Power BI ของคุณ หรือลงทะเบียน ถ้าคุณยังไม่มีบัญชี
> * เปิดบริการของ Power BI
> * รับข้อมูลบางอย่าง และเปิดในมุมมองรายงาน
> * ใช้ข้อมูลนั้นเพื่อสร้างการแสดงภาพ และบันทึกเป็นรายงาน
> * สร้างแดชบอร์ด โดยปักหมุดไทล์จากรายงาน
> * เพิ่มการแสดงภาพอื่น ๆ ที่แดชบอร์ดของคุณโดยใช้เครื่องมือการถามตอบตามภาษาธรรมชาติ
> * ปรับขนาด จัดเรียงใหม่ และโต้ตอบกับไทล์บนแดชบอร์ด
> * ล้างข้อมูล โดยการลบชุดข้อมูล รายงาน และแดชบอร์ด

> [!TIP]
> ต้องการหลักสูตรฝึกอบรมด้วยตนเองแบบฟรีแทนหรือไม่ [ลงทะเบียนในหลักสูตรการวิเคราะห์และแสดงข้อมูลบน EdX ของเรา](https://aka.ms/edxpbi)

## <a name="sign-up-for-the-power-bi-service"></a>ลงชื่อออกจากบริการ Power BI
ถ้าคุณยังไม่มีบัญชี Power BI [ให้ลงทะเบียน Power BI Pro แบบทดลองใช้ฟรี](https://app.powerbi.com/signupredirect?pbi_source=web) ก่อนที่คุณจะเริ่มต้น

หลังจากที่คุณมีบัญชี ให้ใส่ *app.powerbi.com* ในเบราว์เซอร์ของคุณเพื่อเปิดบริการของ Power BI 

## <a name="step-1-get-data"></a>ขั้นตอนที่ 1: รับข้อมูล

เมื่อคุณต้องการสร้างรายงาน Power BI บ่อยครั้งที่คุณมักจะเริ่มต้นใน Power BI Desktop แต่ครั้งนี้ เราจะเริ่มต้นจากการสร้างรายงานในบริการ Power BI

ในบทช่วยสอนนี้ เราจะได้รับข้อมูลจากไฟล์ CSV คุณต้องการทำตามหรือไม่ [ดาวน์โหลดไฟล์ CSV ตัวอย่างทางการเงิน](https://go.microsoft.com/fwlink/?LinkID=521962)

1. [ลงชื่อเข้าใช้ Power BI](https://www.powerbi.com/) ไม่มีบัญชีใช่หรือ ไม่ต้องกังวล คุณสามารถลงทะเบียนเพื่อทดลองใช้ฟรี
2. Power BI เปิดในเบราว์เซอร์ของคุณ เลือก**รับข้อมูล** ที่ด้านล่างของบานหน้าต่างนำทาง

    หน้า**รับข้อมูล**จะเปิดขึ้น   

3. ภายใต้ส่วน**สร้างเนื้อหาใหม่** ให้เลือก**ไฟล์** 
   
   ![รับไฟล์](media/service-get-started/gs1.png)
4.  เลือก**ไฟล์ภายในเครื่อง**
   
    ![รับข้อมูล > หน้าจอไฟล์](media/service-get-started/power-bi-service-get-data-local-file.png)

5. เรียกดูไฟล์บนคอมพิวเตอร์ของคุณ และเลือก**เปิด**

5. สำหรับบทช่วยสอนนี้ เราเลือก**นำเข้า**เพื่อเพิ่มไฟล์ Excel เป็นชุดข้อมูลที่เราสามารถใช้เพื่อสร้างรายงานและแดชบอร์ด ถ้าคุณเลือก**อัปโหลด** เวิร์กบุ๊ก Excel ทั้งหมดถูกอัปโหลดไปยัง Power BI ซึ่งคุณสามารถเปิด และแก้ไขใน Excel online
   
   ![เลือกนำเข้า](media/service-get-started/power-bi-import.png)
6. เมื่อชุดข้อมูลของคุณพร้อมแล้ว ให้เลือก**ชุดข้อมูล** จากนั้นจึงเลือก**สร้างรายงาน**ถัดจากชุดข้อมูล**ตัวอย่างการเงิน**เพื่อเปิดตัวแก้ไขรายงาน 

    ![รายการชุดข้อมูล](media/service-get-started/power-bi-service-datasets.png)

    พื้นที่ทำงานสำหรับรายงานว่างเปล่า เราจะเห็นหน้าต่าง**ตัวกรอง** **การแสดงภาพ** และ**เขตข้อมูล**ทางด้านขวา

    ![พื้นที่รายงานเปล่า](media/service-get-started/power-bi-service-blank-report.png)

7. โปรดสังเกตว่ามีตัวเลือกสำหรับ**มุมมองการอ่าน**บนหน้าต่างนำทางด้านบน เนื่องจากคุณมีตัวเลือกนี้ นั่นหมายความว่าคุณกำลังอยู่ในมุมมองการแก้ไข วิธียอดเยี่ยมในการทำความคุ้นเคยกับตัวแก้ไขรายงานคือ[การแนะนำระบบ](../create-reports/service-the-report-editor-take-a-tour.md)

    ![ตัวเลือกมุมมองการอ่าน](media/service-get-started/power-bi-service-reading-view.png)

    ขณะอยู่ในมุมมองการแก้ไข คุณสามารถสร้างและปรับเปลี่ยนรายงานของคุณได ้เนื่องจากคุณเป็น*เจ้าของ*รายงาน นั่นคือคุณคือ*ผู้สร้าง* เมื่อคุณแชร์รายงานของคุณกับเพื่อนร่วมงาน พวกเขาเท่านั้นจะสามารถโต้ตอบกับรายงานในมุมมองการอ่าน เพื่อนร่วมงานของคุณเป็น*ผู้บริโภค* เรียนรู้เพิ่มเติมเกี่ยวกับ[มุมมองการอ่าน และมุมมองการแก้ไข](../consumer/end-user-reading-view.md)


## <a name="step-2-create-a-chart-in-a-report"></a>ขั้นตอนที่ 2: สร้างแผนภูมิในรายงาน
หลังจากที่คุณเชื่อมต่อกับข้อมูลแล้ว เริ่มต้นสำรวจ  เมื่อคุณพบสิ่งที่น่าสนใจ คุณสามารถสร้างแดชบอร์ดเพื่อตรวจสอบ และดูการเปลี่ยนแปลงเมื่อเวลาผ่านไปได้ มาดูว่าทำงานอย่างไร
    
1. ในตัวแก้ไขรายงาน เราจะเริ่มต้นในบานหน้าต่าง**เขตข้อมูล**ทางด้านขวาของหน้าเพื่อสร้างรูปภาพ เลือกกล่องกาเครื่องหมาย**ยอดขายรวม**และ**วันที่**
   
   ![รายการเขตข้อมูล](media/service-get-started/power-bi-service-fields-pane-selected.png)

    Power BI วิเคราะห์ข้อมูลและสร้างรูปภาพ ถ้าคุณเลือก**วันที่**ก่อน คุณจะเห็นตาราง ถ้าคุณเลือก**ยอดขายรวม**ก่อน คุณจะเห็นแผนภูมิคอลัมน์ 

2. สลับไปยังวิธีการแสดงข้อมูลของคุณแบบอื่น มาดูข้อมูลนี้เป็นแผนภูมิเส้น เลือกไอคอนแผนภูมิเส้นจากบานหน้าต่าง **การแสดงภาพ**
   
   ![ตัวแก้ไขรายงานที่มีแผนภูมิเส้นที่เลือก](media/service-get-started/power-bi-service-select-line-chart.png)

3. แผนภูมินี้น่าสนใจ ดังนั้นให้*ปักหมุด*ที่แดชบอร์ด วางเมาส์เหนือการแสดงภาพแล้วเลือกไอคอนปักหมุด เมื่อคุณปักหมุดการแสดงภาพนี้ ภาพจะถูกเก็บไว้ในแดชบอร์ดของคุณและจะอัปเดตอยู่เสมอเพื่อให้คุณสามารถติดตามค่าล่าสุดได้อย่างรวดเร็ว
   
   ![ปักหมุดไอคอน](media/service-get-started/power-bi-service-pin-visual.png)

4. เนื่องจากเป็นรายงานใหม่ คุณจะได้รับแจ้งให้บันทึกก่อนที่คุณสามารถปักหมุดการแสดงภาพไปยังแดชบอร์ดได้ ตั้งชื่อรายงานของคุณ (ตัวอย่างเช่น *ยอดขายตามช่วงเวลา*) แล้วเลือก**บันทึก** 

5. เลือก**แดชบอร์ดใหม่** และตั้งชื่อเป็น*ตัวอย่างการเงินสำหรับบทช่วยสอน* 
   
   ![ตั้งชื่อรายงาน](media/service-get-started/power-bi-pin.png)
   
6. เลือก**หมุด**
   
    ข้อความว่าสำเร็จแล้ว (ใกล้กับมุมบนขวา) ช่วยให้คุณทราบว่าได้เพิ่มการแสดงภาพเป็นไทล์ลงในแดชบอร์ดของคุณแล้ว
   
    ![ได้ปักหมุดกล่องโต้ตอบแดชบอร์ด](media/service-get-started/power-bi-pin-success.png)

7. ให้เลือก**ไปยังแดชบอร์ด**เพื่อดูแดชบอร์ดใหม่ที่มีแผนภูมิเส้นที่คุณปักหมุดตามไทล์ 
   
   ![แดชบอร์ดที่มีการแสดงภาพถูกปักหมุด](media/service-get-started/power-bi-service-dashboard-tile.png)
   
8. เลือกไทล์ใหม่บนแดชบอร์ดของคุณพื่อกลับไปยังรายงาน Power BI นำคุณกลับสู่รายงานในมุมมองการอ่าน 

1. เมื่อต้องการสลับกลับไปยังมุมมองการแก้ไข ให้เลือก**ตัวเลือกเพิ่มเติม** (...) จากหน้าต่างนำทางด้านบน > **แก้ไข** เมื่อกลับไปที่มุมมองการแก้ไข คุณสามารถทำการสำรวจและปักหมุดไทล์ได้ต่อไป

    ![เลือกแก้ไขเพื่อทำการแก้ไขรายงาน](media/service-get-started/power-bi-service-edit-report.png)

## <a name="step-3-explore-with-qa"></a>ขั้นตอนที่ 3: สำรวจด้วยการถามตอบ

หากต้องการสำรวจข้อมูลอย่างรวดเร็ว ลองถามคำถามในกล่องการถามตอบ การถามตอบสร้างการสอบถามด้วยภาษาธรรมชาติเกี่ยวกับข้อมูลของคุณ ในแดชบอร์ด กล่องการถามตอบอยู่ที่ด้านบนสุด (**ถามคำถามเกี่ยวกับข้อมูลของคุณ**) ในรายงาน กล่องนี้อยู่ที่หน้าต่างนำทางด้านบนสุด (**ถามคำถาม**)

1. ถ้าต้องการกลับไปยังแดชบอร์ด ให้เลือก**พื้นที่ทำงานของฉัน**ในแถบ **Power BI** สีดำ

    ![กลับไปยังพื้นที่ทำงานของฉัน](media/service-get-started/power-bi-service-go-my-workspace.png)

1. บนแท็บ**แดชบอร์ด** ให้เลือกแดชบอร์ดของคุณ

    ![เลือกแดชบอร์ดของคุณ](media/service-get-started/power-bi-service-dashboard-tab.png)

1. เลือก**ถามคำถามเกี่ยวกับข้อมูลของคุณ** การถามตอบนำเสนอคำแนะนำจำนวนมากโดยอัตโนมัติ

    ![พื้นที่ Q&A](media/service-get-started/power-bi-service-new-qanda.png)

    > [!NOTE]
    > หากคุณไม่เห็นคำแนะนำ ให้เปิดใช้งาน**ประสบการณ์การถามตอบใหม่**

2. คำแนะนำบางอย่างจะเปลี่ยนกลับเป็นค่าเดียว ตัวอย่างเช่น เลือก**ยอดขาย**สูงสุด

    การถามตอบจะค้นหาคำตอบและแสดงในรูปแบบของการแสดงภาพ*การ์ด*

    ![การ์ดยอดขายสูงสุด](media/service-get-started/power-bi-service-qanda-maximum-sale.png)

3. เลือกไอคอนหมุด ![ปักหมุดไอคอน](media/service-get-started/pbi_pinicon.png) หากต้องการแสดงการแสดงภาพเกี่ยวกับตัวอย่างการเงินสำหรับแดชบอร์ดบทช่วยสอน

1. เลื่อนลงใน**คำถามเพื่อให้คุณเริ่มต้นระบุ**รายการและเลือก**เฟืองโดยเฉลี่ยสำหรับแต่ละเดือน** 

    ![เฟืองโดยเฉลี่ยสำหรับแต่ละเดือน](media/service-get-started/power-bi-service-qanda-average-cog.png)

1. ปักหมุดแผนภูมิแท่งที่แดชบอร์ด**ตัวอย่างการเงินสำหรับบทช่วยสอน**ด้วย

1. วางเคอร์เซอร์ด้านหลัง*ตามเดือน*ในกล่องการถามตอบ และพิมพ์*เป็นเส้น* เลือก**เส้น (ประเภทการแสดงภาพ)** 

    ![แผนภูมิเป็นการแสดงภาพเป็นเส้น](media/service-get-started/power-bi-service-qanda-as-line.png)

4. เลือก**ออกจากการถามตอบ**เพื่อกลับไปยังแดชบอร์ดของคุณ ซึ่งคุณจะเห็นไทล์ใหม่ที่คุณสร้างไว้ 

   ![แดชบอร์ดที่มีแผนภูมิที่ปักหมุดไว้](media/service-get-started/power-bi-service-dashboard-qna.png)

   แม้ว่าคุณจะเปลี่ยนแผนภูมิเป็นแผนภูมิเส้นแล้ว แต่คุณก็ยังมองเห็นได้ เนื่องจากไทล์ยังเป็นแผนภูมิแท่งตามรูปแบบที่คุณปักหมุดไว้ 

## <a name="step-4-reposition-tiles"></a>ขั้นตอนที่ 4: การจัดตำแหน่งไทล์ใหม่

แดชบอร์ดกว้าง เราสามารถจัดเรียงไทล์ใหม่เพื่อทำให้การใช้งานพื้นที่แดชบอร์ดดียิ่งขึ้นได้

1. ลากมุมขวาล่างของไทล์แผนภูมิเส้น*ยอดขายรวม*ขึ้นไปด้านบน จนกว่าจะมีความสูงเท่ากับไทล์ยอดขาย จากนั้นจึงปล่อย

    ![ปรับขนาดไทล์](media/service-get-started/power-bi-service-resize-tile.png)

    ในตอนนี้ ทั้งสองไทล์จึงมีความสูงเท่ากัน

    ![ปรับขนาดไทล์แล้ว](media/service-get-started/power-bi-service-resized-tile.png)

1. ลากไทล์แผนภูมิแท่ง*ค่าเฉลี่ย COGS* จนกว่าจะอยู่ที่ด้านล่างแผนภูมิเส้น*ยอดขายรวม*พอดี

    การจัดตำแหน่งช่วยให้ดูดีขึ้น

    ![จัดเรียงแดชบอร์ดใหม่แล้ว](media/service-get-started/power-bi-service-rearranged-dashboard.png)

## <a name="step-5-interact-with-tiles"></a>ขั้นตอนที่ 5: โต้ตอบกับไทล์

ส่วนนี้คือหนึ่งในการโต้ตอบครั้งสุดท้ายที่จะต้องสังเกต ก่อนที่คุณจะเริ่มสร้างแดชบอร์ดและรายงานของคุณเอง การเลือกไทล์ที่แตกต่างกันให้ผลลัพธ์ที่แตกต่างกัน 

1. ขั้นตอนแรก ให้เลือกไทล์แผนภูมิเส้น*ยอดขายรวม*ที่คุณปักหมุดจากรายงาน 

    Power BI เปิดรายงานในมุมมองการอ่าน 

2. เลือกปุ่มย้อนกลับของเบราว์เซอร์ 

1. ตอนนี้ให้เลือกไทล์แผนภูมิแท่ง*ค่าเฉลี่ยของ COGS* ที่คุณสร้างขึ้นในการถามตอบ 

    Power BI ไม่เปิดรายงาน แต่การถามตอบจะเปิดรายงานแทน เนื่องจากคุณสร้างแผนภูมินี้ที่นั่น


## <a name="clean-up-resources"></a>ล้างแหล่งข้อมูล
ในตอนนี้ คุณสำเร็จบทช่วยสอนแล้ว คุณสามารถลบชุดข้อมูล รายงานและแดชบอร์ดได้ 

1. ในบานหน้าต่างนำทางตรวจสอบให้แน่ใจว่าคุณอยู่ใน **พื้นที่ทำงานของฉัน**
2. เลือกแท็บ**ชุดข้อมูล**และค้นหาชุดข้อมูลที่คุณนำเข้าสำหรับบทช่วยสอนนี้  
3. เลือก **ตัวเลือกเพิ่มเติม** (...) > **ลบ**

    ![ลบชุดข้อมูล](media/service-get-started/power-bi-service-delete-dataset.png)

    เมื่อคุณลบชุดข้อมูล คุณจะเห็นคำเตือนว่า**รายงานทั้งหมดและแดชบอร์ดที่มีข้อมูลจากชุดข้อมูลจะถูกลบออกไป**

4. เลือก**ลบ**

## <a name="next-steps"></a>ขั้นตอนถัดไป

ทำให้แดชบอร์ดของคุณดียิ่งขึ้นด้วยการเพิ่มไทล์การแสดงภาพเพิ่มเติม และ[การเปลี่ยนชื่อ การเปลี่ยนขนาด การสร้างลิงก์ และการจัดตำแหน่งใหม่](../create-reports/service-dashboard-edit-tile.md)
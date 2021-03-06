---
title: 'บทช่วยสอน: เริ่มต้นการสร้างในบริการ Power BI'
description: เริ่มต้นใช้งานบริการออนไลน์ Power BI (app.powerbi.com)
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: tutorial
ms.date: 07/08/2020
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: 7b9f69607d2fef823ba67d5af035e1e2064a9a72
ms.sourcegitcommit: c18130ea61e67ba111be870ddb971c6413a4b632
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/09/2020
ms.locfileid: "86162401"
---
# <a name="tutorial-get-started-creating-in-the-power-bi-service"></a>บทช่วยสอน: เริ่มต้นการสร้างในบริการ Power BI
บทช่วยสอนนี้เป็นการแนะนำคุณสมบัติการทำงานบางรายการของ*บริการของ Power BI* ในบทช่วยสอนนี้ คุณจะได้เชื่อมต่อกับข้อมูล สร้างรายงานและแดชบอร์ด และถามคำถามต่าง ๆ เกี่ยวกับข้อมูลของคุณ คุณสามารถทำสิ่งต่าง ๆ ได้มากมายด้วยบริการของ Power BI บทช่วยสอนนี้เป็นเพียงการทำงานเบื้องต้นสำหรับคุณเท่านั้น เพื่อทำความเข้าใจว่าบริการ Power BI นั้นเหมาะสมกับข้อเสนอ Power BI อื่นๆ อย่างไร เราขอแนะนำให้คุณอ่านเรื่อง [Power BI คืออะไร](power-bi-overview.md)

คุณเป็น*ผู้อ่าน*รายงานมากกว่าผู้สร้างหรือไม่ [การเดินทางสำรวจบริการ Power BI](../consumer/end-user-experience.md) เป็นจุดเริ่มต้นที่ดีสำหรับคุณ

:::image type="content" source="media/service-get-started/power-bi-service-rearranged-dashboard.png" alt-text="ภาพหน้าจอของแดชบอร์ดตัวอย่างด้านการเงิน":::

ในบทช่วยสอนนี้ คุณจะทำขั้นตอนต่อไปนี้ให้เสร็จสมบูรณ์:

> [!div class="checklist"]
> * ลงชื่อเข้าใช้บัญชีออนไลน์ Power BI ของคุณ หรือลงทะเบียน ถ้าคุณยังไม่มีบัญชี
> * เปิดบริการของ Power BI
> * รับข้อมูลบางอย่าง และเปิดในมุมมองรายงาน
> * ใช้ข้อมูลนั้นเพื่อสร้างการแสดงภาพ และบันทึกเป็นรายงาน
> * สร้างแดชบอร์ด โดยปักหมุดไทล์จากรายงาน
> * เพิ่มการแสดงภาพอื่น ๆ ที่แดชบอร์ดของคุณโดยใช้เครื่องมือการถามตอบตามภาษาธรรมชาติ
> * ปรับขนาด จัดเรียงใหม่ และแก้ไขรายละเอียดสำหรับไทล์บนแดชบอร์ด
> * ล้างข้อมูล โดยการลบชุดข้อมูล รายงาน และแดชบอร์ด

## <a name="sign-up-for-the-power-bi-service"></a>ลงชื่อออกจากบริการ Power BI
คุณต้องมีสิทธิ์การใช้งาน Power BI Pro เพื่อสร้างเนื้อหาใน Power BI ถ้าคุณยังไม่มีบัญชี Power BI [ให้ลงทะเบียน Power BI Pro แบบทดลองใช้ฟรี](https://app.powerbi.com/signupredirect?pbi_source=web) ก่อนที่คุณจะเริ่มต้น

## <a name="step-1-get-data"></a>ขั้นตอนที่ 1: รับข้อมูล

เมื่อคุณต้องการสร้างรายงาน Power BI บ่อยครั้งที่คุณมักจะเริ่มต้นใน Power BI Desktop Power BI Desktop ให้ประสิทธิภาพมากขึ้น คุณสามารถแปลง จัดรูปร่าง และสร้างแบบจำลองข้อมูลก่อนที่จะเริ่มออกแบบรายงาน แต่ครั้งนี้ เราจะเริ่มต้นจากการสร้างรายงานในบริการ Power BI

ในบทช่วยสอนนี้ เราได้รับข้อมูลจากไฟล์ Microsoft Excel แบบง่าย คุณต้องการทำตามหรือไม่ [ดาวน์โหลดไฟล์ตัวอย่างทางการเงิน](https://go.microsoft.com/fwlink/?LinkID=521962)

1. ในการเริ่มต้น ให้เปิดบริการ Power BI (app.powerbi.com) ในเบราว์เซอร์ของคุณ 

    ไม่มีบัญชีใช่หรือ ไม่ต้องกังวล คุณสามารถ[ลงทะเบียนเพื่อรับสิทธิ์ทดลองใช้ Power BI Pro ฟรี](https://app.powerbi.com/signupredirect?pbi_source=web)

1. ให้เลือก **พื้นที่ทำงานของฉัน** ในบานหน้าต่างการนำทาง

1. ใน **พื้นที่ทำงานของฉัน** ให้เลือก **ใหม่** > **อัปโหลดไฟล์**

    หน้า**รับข้อมูล**จะเปิดขึ้น   

3. ภายใต้ส่วน **สร้างเนื้อหาใหม่** ตรวจสอบให้แน่ใจว่ามีการเลือก **ไฟล์** จากนั้นเลือกตำแหน่งที่คุณบันทึกไฟล์ Excel
   
    :::image type="content" source="media/service-get-started/power-bi-service-get-data-local-file.png" alt-text="ภาพหน้าจอของสร้างเนื้อหาใหม่ > ไฟล์":::

5. เรียกดูไฟล์บนคอมพิวเตอร์ของคุณ และเลือก**เปิด**

5. สำหรับบทช่วยสอนนี้ เราเลือก**นำเข้า**เพื่อเพิ่มไฟล์ Excel เป็นชุดข้อมูลที่เราสามารถใช้เพื่อสร้างรายงานและแดชบอร์ด ถ้าคุณเลือก**อัปโหลด** เวิร์กบุ๊ก Excel ทั้งหมดถูกอัปโหลดไปยัง Power BI ซึ่งคุณสามารถเปิด และแก้ไขใน Excel Online
   
   :::image type="content" source="media/service-get-started/power-bi-import.png" alt-text="ภาพหน้าจอของการเลือกนำเข้า":::
6. เมื่อชุดข้อมูลของคุณพร้อมแล้ว ให้เลือก **ตัวเลือกเพิ่มเติม (...)** ถัดจากชุดข้อมูลตัวอย่างทางการเงินของคุณ จากนั้นเลือก **สร้างรายงาน**
1. เปิดตัวแก้ไขรายงาน 

    :::image type="content" source="media/service-get-started/power-bi-service-datasets.png" alt-text="ภาพหน้าจอของเนื้อหาทั้งหมด > สร้างรายงาน":::

    พื้นที่ทำงานสำหรับรายงานว่างเปล่า เราจะเห็นหน้าต่าง**ตัวกรอง** **การแสดงภาพ** และ**เขตข้อมูล**ทางด้านขวา

    :::image type="content" source="media/service-get-started/power-bi-service-blank-report.png" alt-text="ภาพหน้าจอของผืนผ้าใบรายงานเปล่า":::

    > [!TIP]
    > เลือกปุ่มการนำทางส่วนกลางที่มุมซ้ายบนเพื่อยุบบานหน้าต่างนำทาง วิธีที่ผืนผ้าใบของคุณมีพื้นที่มากขึ้น
    >
    >:::image type="content" source="media/service-get-started/power-bi-global-nav-button.png" alt-text="ปุ่มการนำทางส่วนกลาง":::
    >

7. ขณะนี้คุณอยู่ในมุมมองการแก้ไข สังเกตเห็นตัวเลือก **มุมมองการอ่าน** ในแถบเมนู 

    :::image type="content" source="media/service-get-started/power-bi-service-reading-view.png" alt-text="ภาพหน้าจอของตัวเลือกมุมมองการอ่าน":::

    ขณะอยู่ในมุมมองการแก้ไข คุณสามารถแก้ไขรายงานได ้เนื่องจากคุณเป็น*เจ้าของ* และ *ผู้สร้าง* รายงาน เมื่อคุณแชร์รายงานของคุณกับเพื่อนร่วมงาน บ่อยครั้งที่พวกเขาเท่านั้นจะสามารถโต้ตอบกับรายงานในมุมมองการอ่าน พวกเขาเป็น *ผู้บริโภค* รายงานใน **พื้นที่ทำงานของฉัน** 

## <a name="step-2-create-a-chart-in-a-report"></a>ขั้นตอนที่ 2: สร้างแผนภูมิในรายงาน
หลังจากที่คุณเชื่อมต่อกับข้อมูลแล้ว เริ่มต้นสำรวจ เมื่อคุณพบสิ่งที่น่าสนใจ คุณสามารถบันทึกลงในผืนผ้าใบรายงาน จากนั้นคุณสามารถปักหมุดมันไว้ที่แดชบอร์ดเพื่อตรวจสอบและดูว่าจะเปลี่ยนแปลงอย่างไรเมื่อเวลาผ่านไป แต่สิ่งแรกที่ต้องทำ
    
1. ในตัวแก้ไขรายงาน ให้เริ่มต้นในบานหน้าต่าง**เขตข้อมูล**ทางด้านขวาของหน้าเพื่อสร้างรูปภาพ เลือกเขตข้อมูล **ยอดขายรวม** เขตข้อมูล **วันที่**
   
   :::image type="content" source="media/service-get-started/power-bi-service-fields-pane-selected.png" alt-text="ภาพหน้าจอของรายการเขตข้อมูล":::

    Power BI วิเคราะห์ข้อมูลและสร้างการแสดงข้อมูลด้วยภาพแผนภูมิคอลัมน์ 

    > [!NOTE]
    > ถ้าคุณเลือกเขตข้อมูล **วันที่** แทนที่ **ยอดขายรวม** มาก่อนแล้ว คุณจะเห็นตาราง ไม่ต้องกังวล! เรากำลังจะเปลี่ยนการแสดงข้อมูลด้วยภาพในขั้นตอนถัดไป

    เขตข้อมูลบางอันมีสัญลักษณ์ซิกมาถัดจากเขตข้อมูลดังกล่าว เพราะ Power BI ตรวจพบว่าเขตข้อมูลประกอบด้วยค่าตัวเลข

    :::image type="content" source="media/service-get-started/power-bi-sigma-fields.png" alt-text="เขตข้อมูลที่มีสัญลักษณ์ซิกมา":::

2. สลับไปยังวิธีการแสดงข้อมูลของคุณแบบอื่นกันเถอะ แผนภูมิเส้นเป็นวิชวลที่ดีสำหรับการแสดงค่าเมื่อเวลาผ่านไป เลือกไอคอน **แผนภูมิเส้น** จากบานหน้าต่าง **การแสดงข้อมูลด้วยภาพ**
   
   :::image type="content" source="media/service-get-started/power-bi-service-select-line-chart.png" alt-text="ภาพหน้าจอของตัวแก้ไขรายงานที่มีแผนภูมิเส้นที่เลือก":::

3. แผนภูมินี้น่าสนใจ ดังนั้นให้*ปักหมุด*ที่แดชบอร์ด วางเมาส์เหนือการแสดงภาพแล้วเลือกไอคอนปักหมุด
   
   :::image type="content" source="media/service-get-started/power-bi-service-pin-visual.png" alt-text="ภาพหน้าจอของไอคอนหมุด":::

4. เนื่องจากเป็นรายงานใหม่ คุณจะได้รับแจ้งให้บันทึกก่อนที่คุณสามารถปักหมุดการแสดงภาพไปยังแดชบอร์ดได้ ตั้งชื่อรายงานของคุณ (ตัวอย่างเช่น *รายงานตัวอย่างทางการเงิน*) จากนั้น **บันทึก** 

    ในตอนนี้คุณกำลังดูรายงานในมุมมองการอ่าน 

6. เลือกไอคอน **หมุด** อีกครั้ง
 
5. เลือก **แดชบอร์ดใหม่** และตั้งชื่อเป็น *แดชบอร์ดตัวอย่างด้านการเงิน* เป็นต้น 
   
   :::image type="content" source="media/service-get-started/power-bi-pin.png" alt-text="ภาพหน้าจอของชื่อแดชบอร์ด":::
  
    ข้อความว่าสำเร็จแล้ว (ใกล้กับมุมบนขวา) ช่วยให้คุณทราบว่าได้เพิ่มการแสดงภาพเป็นไทล์ลงในแดชบอร์ดของคุณแล้ว
   
    :::image type="content" source="media/service-get-started/power-bi-pin-success.png" alt-text="ภาพหน้าจอของกล่องโต้ตอบที่ปักหมุดไว้ที่แดชบอร์ด":::

    ตอนนี้คุณได้ตรึงการแสดงข้อมูลด้วยภาพนี้แล้ว ซึ่งถูกจัดเก็บไว้ในแดชบอร์ดของคุณ ข้อมูลจะยังคงเป็นปัจจุบันอยู่เสมอเพื่อให้คุณสามารถติดตามค่าล่าสุดได้อย่างรวดเร็ว อย่างไรก็ตาม ถ้าคุณเปลี่ยนประเภทการแสดงข้อมูลด้วยภาพในรายงาน การแสดงข้อมูลด้วยภาพบนแดชบอร์ดจะไม่เปลี่ยนแปลง

7. ให้เลือก**ไปยังแดชบอร์ด**เพื่อดูแดชบอร์ดใหม่ที่มีแผนภูมิเส้นที่คุณปักหมุดตามไทล์ 
   
   :::image type="content" source="media/service-get-started/power-bi-service-dashboard-tile.png" alt-text="แดชบอร์ดที่มีการแสดงข้อมูลด้วยภาพถูกปักหมุดอยู่":::
   
8. เลือกไทล์ใหม่บนแดชบอร์ดของคุณ Power BI นำคุณกลับสู่รายงานในมุมมองการอ่าน

1. เมื่อต้องการสลับกลับไปยังมุมมองการแก้ไข ให้เลือก **ตัวเลือกเพิ่มเติม** (...) ในแถบเมนู > **แก้ไข**

    :::image type="content" source="media/service-get-started/power-bi-service-edit-report.png" alt-text="ภาพหน้าจอของเลือกแก้ไขเพื่อทำการแก้ไขรายงาน":::

    เมื่อกลับไปที่มุมมองการแก้ไข คุณสามารถทำการสำรวจและปักหมุดไทล์ได้ต่อไป

## <a name="step-3-explore-with-qa"></a>ขั้นตอนที่ 3: สำรวจด้วยการถามตอบ

หากต้องการสำรวจข้อมูลอย่างรวดเร็ว ลองถามคำถามในกล่องการถามตอบ Q&A ช่วยให้คุณสามารถถามคิวรีได้ด้วยภาษาธรรมชาติเกี่ยวกับข้อมูลของคุณ ในแดชบอร์ด กล่อง Q&A อยู่ที่ด้านบนสุด (**ถามคำถามเกี่ยวกับข้อมูลของคุณ**) ภายใต้แถบเมนู ในรายงาน กล่องนี้อยู่ที่แถบเมนูด้านบนสุด (**ถามคำถาม**)

1. ถ้าต้องการกลับไปยังแดชบอร์ด ให้เลือก **พื้นที่ทำงานของฉัน** ในแถบส่วนหัว **Power BI** สีดำ

    :::image type="content" source="media/service-get-started/power-bi-service-go-my-workspace.png" alt-text="ภาพหน้าจอของกลับไปยังพื้นที่ทำงานของฉัน":::

1. ใน **พื้นที่ทำงานของฉัน** ให้เลือกแดชบอร์ดของคุณ

    :::image type="content" source="media/service-get-started/power-bi-service-dashboard-tab.png" alt-text="ภาพหน้าจอของเลือกแดชบอร์ดของคุณ":::

1. เลือก**ถามคำถามเกี่ยวกับข้อมูลของคุณ** การถามตอบนำเสนอคำแนะนำจำนวนมากโดยอัตโนมัติ 

    :::image type="content" source="media/service-get-started/power-bi-service-new-qanda.png" alt-text="ภาพหน้าจอของผืนผ้าใบ Q&A":::

    > [!NOTE]
    > หากคุณไม่เห็นคำแนะนำ ให้เปิดใช้งาน**ประสบการณ์การถามตอบใหม่**

    :::image type="content" source="media/service-get-started/power-bi-new-qna-experience.png" alt-text="ภาพหน้าจอของของการเปิดประสบการณ์ Q&A ใหม่":::

1. คำแนะนำบางอย่างจะเปลี่ยนกลับเป็นค่าเดียว ตัวอย่างเช่น เลือก **ฟันเฟืองเฉลี่ยเป็นเท่าไร**

    การถามตอบจะค้นหาคำตอบและแสดงในรูปแบบของการแสดงภาพ*การ์ด*

3. เลือก **ปักหมุดวิชวล** และปักหมุดการแสดงข้อมูลด้วยภาพนี้ไปยังแดชบอร์ดตัวอย่างทางการเงิน

    :::image type="content" source="media/service-get-started/power-bi-qna-pin-tile.png" alt-text="ภาพหน้าจอการปักหมุดวิชวล":::

1. กลับไปที่ Q&A และเลือก **แสดงคำแนะนำทั้งหมด**
1. เลือก **กำไรทั้งหมดตามประเทศ** 

    :::image type="content" source="media/service-get-started/power-bi-qna-total-profit-country.png" alt-text="ภาพหน้าจอของกำไรทั้งหมดตามประเทศ":::

1. ปักหมุดแผนผังไปยังแดชบอร์ดตัวอย่างทางการเงินด้วย

1. บนแดชบอร์ด ให้เลือกแผนที่คุณเพิ่งปักหมุด ดูว่าจะเปิด Q&A อีกครั้งได้อย่างไร 
1. วางเคอร์เซอร์ด้านหลัง *ตามประเทศ* ในกล่องการถามตอบ และพิมพ์*เป็นแท่ง* Power BI สร้างแผนภูมิแท่งพร้อมผลลัพธ์

    :::image type="content" source="media/service-get-started/power-bi-qna-profit-country-bar.png" alt-text="ภาพหน้าจอของการแสดงข้อมูลด้วยภาพแผนภูมิแท่ง":::

1. ปักหมุดแผนภูมิแท่งไปยังแดชบอร์ดตัวอย่างทางการเงินด้วย

4. เลือก**ออกจากการถามตอบ**เพื่อกลับไปยังแดชบอร์ดของคุณ ซึ่งคุณจะเห็นไทล์ใหม่ที่คุณสร้างไว้ 

   :::image type="content" source="media/service-get-started/power-bi-service-dashboard-qna.png" alt-text="ภาพหน้าจอของแดชบอร์ดที่มีวิชวล Q&A ปักหมุดอยู่":::

   แม้ว่าคุณจะเปลี่ยนแผนที่เป็นแผนภูมิแท่งใน Q&A แล้ว แต่ไทล์นั้นยังคงอยู่ในแผนที่เพราะเป็นแผนที่เมื่อคุณปักหมุด 

## <a name="step-4-reposition-tiles"></a>ขั้นตอนที่ 4: การจัดตำแหน่งไทล์ใหม่

เราสามารถจัดเรียงไทล์ใหม่เพื่อทำให้การใช้งานพื้นที่แดชบอร์ดดียิ่งขึ้นได้

1. ลากมุมขวาล่างของไทล์แผนภูมิเส้น*ยอดขายรวม*ขึ้นไปด้านบน จนกว่าจะมีความสูงเท่ากับไทล์ยอดขาย จากนั้นจึงปล่อย

    :::image type="content" source="media/service-get-started/power-bi-service-resize-tile.png" alt-text="ภาพหน้าจอของการปรับขนาดไทล์":::

    ในตอนนี้ ทั้งสองไทล์จึงมีความสูงเท่ากัน

1. เลือก **ตัวเลือกเพิ่มเติม (...)** สำหรับค่าเฉลี่ยของไทล์ COGS > **แก้ไขรายละเอียด** 

    :::image type="content" source="media/service-get-started/power-bi-tile-edit-details.png" alt-text="ภาพหน้าจอของเมนูตัวเลือกเพิ่มเติมสำหรับไทล์":::

1. ในกล่อง **ชื่อ** ให้พิมพ์ *ต้นทุนเฉลี่ยของสินค้าที่ขาย* > **ใช้**

    :::image type="content" source="media/service-get-started/power-bi-tile-details-dialog.png" alt-text="ภาพหน้าจอของกล่องโต้ตอบแก้ไขรายละเอียด":::

1. จัดเรียงวิชวลอื่น ๆ ให้พอดีเข้าด้วยกัน

    การจัดตำแหน่งช่วยให้ดูดีขึ้น

    :::image type="content" source="media/service-get-started/power-bi-service-rearranged-dashboard.png" alt-text="ภาพหน้าจอของแดชบอร์ดที่ถูกจัดเรียง":::


## <a name="clean-up-resources"></a>ล้างแหล่งข้อมูล
ในตอนนี้ คุณสำเร็จบทช่วยสอนแล้ว คุณสามารถลบชุดข้อมูล รายงานและแดชบอร์ดได้ 

1. เลือก **พื้นที่ทำงานของฉัน** ในแถบส่วนหัว **Power BI** สีดำ
2. เลือก **ตัวเลือกเพิ่มเติม (...)** ถัดจากชุดข้อมูลตัวอย่างทางการเงิน > **ลบ**

    :::image type="content" source="media/service-get-started/power-bi-service-delete-dataset.png" alt-text="ภาพหน้าจอของการลบชุดข้อมูล":::

    คุณจะเห็นคำเตือนว่า**รายงานทั้งหมดและแดชบอร์ดที่มีข้อมูลจากชุดข้อมูลจะถูกลบออกไป**

4. เลือก**ลบ**

## <a name="next-steps"></a>ขั้นตอนถัดไป

สำรวจคอลเลกชันของเนื้อหา Microsoft Learn เหล่านี้สำหรับ Power BI:

- [เรียนรู้เกี่ยวกับ Power BI](https://docs.microsoft.com/users/microsoftpowerplatform-5978/collections/r52to235xrjxk)
- [กลายเป็นนักวิเคราะห์ข้อมูล Power BI](https://docs.microsoft.com/users/microsoftpowerplatform-5978/collections/djwu3eywpk4nm)

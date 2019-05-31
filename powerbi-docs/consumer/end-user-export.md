---
title: ส่งออกข้อมูลจาก Power BI visual
description: ส่งออกข้อมูลจากวิชวลรายงานและแดชบอร์ดวิชวล และดูใน Excel
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: jtlLGRKBvXY
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 4/9/2019
ms.author: mihart
LocalizationGroup: Consumers
ms.openlocfilehash: d4384db8e05a69b138e76377e7c7b845867fa881
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "61063856"
---
# <a name="export-data-from-visual"></a>ส่งออกข้อมูลจากภาพ
ถ้าคุณต้องการดูข้อมูลที่ถูกใช้เพื่อสร้างวิชวล[คุณสามารถแสดงข้อมูลใน Power BI](end-user-show-data.md)หรือส่งออกข้อมูลนั้นไปยัง Excel ได้ ตัวเลือกในการส่งออกข้อมูลจำเป็นต้องมีชนิดหรือสิทธิ์การใช้งานบางอย่าง และแก้ไขสิทธิ์ไปยังเนื้อหา ถ้าคุณไม่สามารถส่งออก ตรวจสอบกับผู้ดูแลระบบ Power BI ของคุณ 

## <a name="from-a-visual-on-a-power-bi-dashboard"></a>จากภาพบนแดชบอร์ด Power BI

1. เริ่มต้นบนแดชบอร์ด Power BI ต่อไปนี้เรากำลังใช้แดชบอร์ดจาก***ตัวอย่างด้านการตลาด และขาย***แอ คุณสามารถ[ดาวน์โหลดแอปนี้จาก AppSource.com](https://appsource.microsoft.com/en-us/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample-preview?flightCodes=e2b06c7a-a438-4d99-9eb6-4324ce87f282)ได้

    ![](media/end-user-export/power-bi-dashboard.png)

2. โฮเวอร์เหนือวิชวลเพื่อแสดงจุดไข่ปลา (...) แล้วคลิกเพื่อแสดงเมนูการดำเนินการ

    ![](media/end-user-export/power-bi-dashboard-export-visual.png)

3. เลือก**ส่งออกไปยัง Excel**

4. เกิดอะไรขึ้นถัดจากขึ้นอยู่กับเบราว์เซอร์ที่คุณกำลังใช้ คุณอาจได้รับพร้อมท์ให้บันทึกไฟล์หรือคุณอาจเห็นลิงก์ไปยังไฟล์ส่งออกที่ด้านล่างของเบราว์เซอร์ได้ 

    ![](media/end-user-export/power-bi-export-browser.png)

5. เปิดไฟล์ใน Excel  

    ![](media/end-user-export/power-bi-excel.png)


## <a name="from-a-visual-in-a-report"></a>จากวิชวลในรายงาน
คุณสามารถส่งออกข้อมูลจากวิชวลในรายงานเป็นไฟล์.csv หรือ.xlsx (Excel) รูปแบบได้ 

1. บนแดชบอร์ด เลือกไทล์เพื่อเปิดรายงานพื้นฐาน  ในตัวอย่างนี้ เรากำลังเลือกวิชวลเดิมเป็นด้านบน*หน่วยรวม YTD %ความแปรปรวน* 

    ![](media/end-user-export/power-bi-export-report.png)

    เนื่องจากไทล์นี้ถูกสร้างขึ้นจากการ*ยอดขายและตัวอย่างทางการตลาด*รายงาน ที่รายงานที่เปิด และ ซึ่งเปิดไปยังหน้าที่ประกอบด้วยภาพไทล์ที่เลือก 

2. เลือกไทล์ในรายงาน แจ้งให้ทราบเกี่ยวกับการ**ตัวกรอง**บานหน้าต่างทางด้านขวา ภาพนี้มีตัวกรอง เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับตัวกรอง ดู[ใช้ตัวกรองในรายงาน](end-user-report-filter.md)

    ![](media/end-user-export/power-bi-export-filters.png)


3. เลือกจุดไข่ปลาที่มุมขวาบนของการแสดงภาพ เลือก**ส่งออกข้อมูล**

    ![](media/end-user-export/power-bi-export-report2.png)

4. คุณจะเห็นตัวเลือกการส่งออกข้อมูล Summarized หรือ Underlying ข้อมูล ถ้าคุณกำลังใช้*ยอดขายและตัวอย่างทางการตลาด*แอป**ข้อมูลเบื้องต้น**จะถูกปิดใช้งาน แต่คุณอาจพบรายงานที่มีการเปิดใช้งานทั้งสองตัวเลือก นี่คือคำอธิบายของความแตกต่าง

    **ข้อมูลสรุป**: เลือกตัวเลือกนี้ถ้าคุณต้องการส่งออกข้อมูลสำหรับสิ่งที่คุณเห็นในภาพ  ส่งออกชนิดนี้แสดงเฉพาะข้อมูลที่ถูกใช้เพื่อสร้างภาพ ถ้าวิชวลมีตัวกรอง แล้วข้อมูลคุณส่งออกจะยังสามารถกรอง ตัวอย่าง สำหรับภาพนี้ การส่งออกจะรวมเฉพาะข้อมูลสำหรับ 2014 และภูมิภาคส่วนกลาง และ 4 ของผู้ผลิตเฉพาะข้อมูล: VanArsdel, Natura, Aliqui และ Prirum
  

    **ข้อมูลเบื้องต้น**: เลือกตัวเลือกนี้ถ้าคุณต้องการส่งออกข้อมูลสำหรับสิ่งที่คุณเห็นในวิชวล**plus**ข้อมูลเพิ่มเติมจากชุดข้อมูลพื้นฐาน  ซึ่งอาจรวมถึงข้อมูลที่มีอยู่ในชุดข้อมูล แต่ไม่ได้ใช้ในวิชวล 

    ![](media/end-user-export/power-bi-export-report3.png)

5. เกิดอะไรขึ้นถัดจากขึ้นอยู่กับเบราว์เซอร์ที่คุณกำลังใช้ คุณอาจได้รับพร้อมท์ให้บันทึกไฟล์หรือคุณอาจเห็นลิงก์ไปยังไฟล์ส่งออกที่ด้านล่างของเบราว์เซอร์ได้ 

    ![](media/end-user-export/power-bi-export-edge.png)


7. เปิดไฟล์ใน Excel เปรียบเทียบจำนวนข้อมูลที่ส่งออกไปยังข้อมูลเราส่งออกจากภาพเดียวกันบนแดชบอร์ด ความแตกต่างคือการ ส่งออกนี้มี**ข้อมูลเบื้องต้น** 

    ![](media/end-user-export/power-bi-underlying.png)


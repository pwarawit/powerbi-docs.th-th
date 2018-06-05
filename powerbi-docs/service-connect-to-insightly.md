---
title: เชื่อมต่อกับ Insightly ด้วย Power BI
description: Insightly สำหรับ Power BI
services: powerbi
documentationcenter: ''
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: a49260a90647178e0737e728804b00c004b21376
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815328"
---
# <a name="connect-to-insightly-with-power-bi"></a>เชื่อมต่อกับ Insightly ด้วย Power BI
แสดงข้อมูลเป็นภาพและแชร์ข้อมูล Insightly CRM ของคุณใน Power BI ด้วยชุดเนื้อหา Insightly เชื่อมต่อกับ Power BI โดยใช้คีย์ Insightly API ของคุณเพื่อดูและสร้างรายงานและแดชบอร์ดจากข้อมูล CRM ของคุณ ด้วย Power BI คุณสามารถวิเคราะห์ข้อมูลของคุณในรูปแบบใหม่ สร้างแผนภูมิและกราฟอันทรงพลัง และแสดงรายชื่อผู้ติดต่อ ลูกค้าเป้าหมาย และองค์กรต่าง ๆ บนแผนที่ได้

เชื่อมต่อไปยัง[ชุดเนื้อหา Insightly](https://app.powerbi.com/getdata/services/insightly)สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือก**รับข้อมูล**ที่ด้านล่างของแผงนำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-insightly/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-insightly/services.png)
3. เลือก**Insightly** \> **รับ**
   
   ![](media/service-connect-to-insightly/insightly.png)
4. เลือก**คีย์**เป็นประเภทการรับรองความถูกต้อง และใส่คีย์ Insight API ของคุณ จากนั้นเลือก**ลงชื่อเข้าใช้** ดูรายละเอียดที่[การค้นหานี้](#FindingParams)ที่ด้านล่าง
   
   ![](media/service-connect-to-insightly/creds.png)
5. หลังจากอนุมัติ กระบวนการนำเข้าจะเริ่มโดยอัตโนมัติ เมื่อเสร็จสิ้น แดชบอร์ดใหม่ รายงาน และแบบจำลองจะปรากฏในบานหน้าต่างนำทาง เลือกแดชบอร์ดเพื่อดูข้อมูลที่นำเข้าของคุณ
   
     ![](media/service-connect-to-insightly/dashboard.png)

**ฉันต้องทำอะไรต่อ?**

* ลอง[ถามคำถามในกล่องถามตอบ](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานพื้นฐาน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
ชุดเนื้อหานี้ประกอบด้วยตารางต่อไปนี้ ที่มีเขตข้อมูลจากบันทึกที่สอดคล้องกัน:

| ตาราง |  |  |  |
| --- | --- | --- | --- |
| ที่ติดต่อ |โอกาสทางการขาย |ขั้นตอนไปป์ไลน์ |วันที่งานเสร็จสมบูรณ์ |
| เขตข้อมูลแบบกำหนดเอง |วันปิดโอกาสทางการขาย |วันที่โครงการเสร็จสมบูรณ์ |งาน |
| เหตุการณ์ |วันคาดการณ์โอกาสทางการขาย |โครงการ |ทีม/สมาชิก |
| ลูกค้าเป้าหมาย |องค์กร |แท็ก |ผู้ใช้ |

นอกจากนี้ ตารางและรายงานจำนวนมากยังรวมถึงเขตข้อมูลจากการคำนวณที่ไม่ซ้ำกัน เช่น:  

* ตารางที่มีวันที่ปิดการคาดการณ์โอกาส "แบบรวมกลุ่ม" วันที่ปิดโอกาสการขายจริง วันที่เสร็จสิ้นโครงการ และวันที่งานเสร็จสิ้นสำหรับการวิเคราะห์แยกตามเดือน ไตรมาส หรือปี  
* เขตข้อมูลค่าถ่วงน้ำหนักสำหรับโอกาสทางการขาย (ค่าโอกาส * ความน่าเป็นในการชนะการขาย)  
* เขตข้อมูลระยะเวลาเฉลี่ยและระยะเวลารวมสำหรับงาน ยึดเริ่มต้นวันที่เริ่มต้นและและวันที่งานเสร็จสมบูรณ์  
* รายงานที่มีเขตข้อมูลที่คำนวณสำหรับอัตราโอกาสชนะ (จำนวนการชนะ/จำนวนโอกาสทางการขายรวม) และค่าอัตราชนะ (ค่าของการชนะ/ค่าของโอกาสทางการขายรวม)  

## <a name="system-requirements"></a>ข้อกำหนดของระบบ
จำเป็นต้องมีบัญชีผู้ใช้ Insightly พร้อมการเข้าถึง Insightly API ความสามารถในการมองเห็นสิทธิ์การใช้งานจะยึดตามคีย์ API ที่ใช้ในการสร้างการเชื่อมต่อกับ Power BI คุณจะสามารถมองเห็นบันทึก Insightly ได้ในรายงานและแดชบอร์ด Power BI ที่คุณแชร์กับผู้อื่น

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>การค้นหาพารามิเตอร์
**คีย์ API**

เมื่อต้องการคัดลอกคีย์ API ของคุณจาก Insightly เลือกตั้งค่าผู้ใช้จากเมนูโปรไฟล์ Insightly แล้วเลื่อนลง สตริงนี้ของอักขระจะถูกใช้เพื่อเชื่อมต่อข้อมูลของคุณไปยัง Power BI

![](media/service-connect-to-insightly/findapi.png)

## <a name="troubleshooting"></a>การแก้ไขปัญหา
ระบบนำเข้าข้อมูลของคุณผ่านทาง Insightly API ซึ่งรวมถึงขีดจำกัดประจำวันโดยยึดตามระดับแผนการสมัครใช้งาน Insightly ของคุณ ขีดจำกัดจะแสดงอยู่ในส่วนขีดจำกัดอัตรา/การควบคุมคำขอของเอกสาร API ของเรา: https://api.insight.ly/v2.2/Help#!/Overview/Introduction#ratelimit

รายงานที่ให้ไว้ใช้เขตข้อมูลค่าเริ่มต้นจาก Insightly และอาจไม่รวมค่าที่กำหนดเองของคุณ แก้ไขรายงานเพื่อดูเขตข้อมูลที่พร้อมใช้งานทั้งหมด

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งานใน Power BI](service-get-started.md)

[รับข้อมูลใน Power BI](service-get-data.md)


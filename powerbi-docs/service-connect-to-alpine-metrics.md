---
title: เชื่อมต่อกับ Alpine Metrics Sales Predictions ด้วย Power BI
description: Alpine Metrics Sales Predictions สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 7456a030dd5047642c4de9c7a289fed96fe390f1
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/29/2018
ms.locfileid: "37135984"
---
# <a name="connect-to-alpine-metrics-sales-predictions-with-power-bi"></a>เชื่อมต่อกับ Alpine Metrics Sales Predictions ด้วย Power BI
Alpine Metrics ช่วยให้กระบวนการคาดการณ์การขายในคลาวด์มีประสิทธิภาพสูงสุด และพร้อมใช้งานสำหรับการจัดการขายทั้งขนาดใหญ่และขนาดเล็ก ชุดเนื้อหาคาดการณ์ยอดขาย Alpine Metrics สำหรับ Power BI มีเมตริก เช่นยอดขายที่เป็นไปได้และความเสี่ยงที่คาดการณ์ ช่วยให้คุณได้ข้อมูลเชิงลึกสำหรับอนาคตธุรกิจของคุณ 

เชื่อมต่อไปยัง[ชุดเนื้อหาการคาดการณ์ยอดขายอัลไพน์ เมทริกซ์](https://app.powerbi.com/getdata/services/alpine-metrics)สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกรับข้อมูลที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ  
   
    ![](media/service-connect-to-alpine-metrics/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**  
   
    ![](media/service-connect-to-alpine-metrics/services.png)
3. เลือก**คาดการณ์ยอดขาย AlpineMetrics**แล้วเลือก**รับ**  
   
    ![](media/service-connect-to-alpine-metrics/alpine.png)
4. เลือก**OAuth 2**แล้วเลือก**ลงชื่อเข้าใช้** เมื่อได้รับข้อความปรากฏ ให้ใส่ข้อมูลประจำตัว AlpineMetrics ของคุณ
   
    ![](media/service-connect-to-alpine-metrics/creds.png)
   
    ![](media/service-connect-to-alpine-metrics/creds2.png)
5. เมื่อเชื่อมต่อแล้ว แดชบอร์ด รายงาน และชุดข้อมูลจะโหลดโดยอัตโนมัติสามารถ เมื่อเสร็จสมบูรณแล้ว์ ไทล์จะอัปเดตด้วยข้อมูลจากบัญชีของคุณ
   
    ![](media/service-connect-to-alpine-metrics/dashboard.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานด้านใน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
ชุดเนื้อหานี้ประกอบด้วยข้อมูลจากตารางต่อไปนี้:  

    - บัญชี    
    - พื้นที่ธุรกิจ    
    - ประเทศ    
    - อุตสาหกรรม    
    - โอกาสทางการขาย  
    - บุคคล  
    - การคาดการณ์    
    - ประวัติการคาดการณ์    
    - ผลิตภัณฑ์  
    - ภูมิภาค    

## <a name="system-requirements"></a>ความต้องการของระบบ
จำเป็นต้องมีบัญชี Alpine Metrics ที่มีสิทธิ์การใช้งานตารางข้างต้นเพื่อเริ่มสร้างตัวอย่างชุดเนื้อหานี้

## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI คืออะไร](power-bi-overview.md)

[Power BI แนวคิดพื้นฐาน](service-basic-concepts.md)


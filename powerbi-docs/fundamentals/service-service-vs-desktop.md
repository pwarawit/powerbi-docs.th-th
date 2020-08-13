---
title: การเปรียบเทียบ Power BI Desktop และบริการ Power BI
description: Power BI Desktop เป็นการวิเคราะห์ข้อมูลและเครื่องมือสร้างรายงานที่สมบูรณ์ บริการ Power BI เป็นบริการออนไลน์บนคลาวด์สำหรับการแก้ไขรายงานและความร่วมมือกับทีมและองค์กร
author: maggiesMSFT
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/07/2020
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 4118e5c009a8d7372d5cb58d1e1b9d033a70494e
ms.sourcegitcommit: 154946ece829360cc0ff3be13276cd7a129f3388
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/07/2020
ms.locfileid: "87988718"
---
# <a name="comparing-power-bi-desktop-and-the-power-bi-service"></a>การเปรียบเทียบ Power BI Desktop และบริการ Power BI

ในแผนภาพเวนน์ที่เปรียบเทียบ Power BI Desktop และบริการ Power BI พื้นที่ตรงกลางจะแสดงให้เห็นว่าทั้งสองทับซ้อนกันอย่างไร งานบางอย่างที่คุณสามารถทำได้ทั้งใน Power BI Desktop หรือบริการ ทั้งสองด้านของแผนภาพเวนน์แสดงคุณสมบัติที่เป็นเอกลักษณ์ของแอปพลิเคชันและบริการ  

![แผนภาพเวนน์ แสดงความสัมพันธ์ระหว่าง Power BI Desktop และบริการ Power BI](media/service-service-vs-desktop/power-bi-venn-desktop-service.png)

**Power BI Desktop** คือเครื่องมือวิเคราะห์ข้อมูลและสร้างรายงานที่สมบูรณ์ ซึ่งคุณติดตั้งได้ฟรีบนเครื่องคอมพิวเตอร์ของคุณ ซึ่งรวมถึง Query Editor ที่คุณสามารถเชื่อมต่อกับแหล่งข้อมูลที่แตกต่างกันมากมายและรวมเข้าด้วยกัน (มักเรียกว่าการสร้างแบบจำลอง) ลงในแบบจำลองข้อมูล จากนั้นคุณออกแบบรายงานที่ยึดตามแบบจำลองข้อมูลนั้น [แนวทางการเริ่มใช้งาน Power BI Desktop](desktop-getting-started.md) ผ่านกระบวนการต่างๆ

**บริการของ PowerBI** เป็นบริการบนคลาวด์ ซึ่งสนับสนุนการแก้ไขรายงานและความร่วมมือกับทีมและองค์กร คุณสามารถเชื่อมต่อกับแหล่งข้อมูลในบริการ Power BI ได้เช่นกัน แต่การสร้างแบบจำลองจะถูกจำกัดไว้

นักออกแบบรายงาน Power BI ส่วนใหญ่ที่ทำงานในโครงการข่าวกรองธุรกิจจะใช้ **Power BI Desktop** เพื่อสร้างรายงาน Power BI จากนั้นใช้ **บริการ Power BI** เพื่อทำงานร่วมกันและแจกจ่ายรายงาน

บริการ Power BI ยังโฮสต์ *รายงานที่มีการแบ่งหน้า* ในพื้นที่ทำงานที่ได้รับการสนับสนุนโดยความจุของ Power BI Premium คุณสร้างรายงานแบบแบ่งหน้าด้วย Power BI Report Builder ดู [เปรียบเทียบรายงาน Power BI และรายงานที่แบ่งหน้า](../paginated-reports/paginated-reports-report-builder-power-bi.md#compare-power-bi-reports-and-paginated-reports) ในบทความ "รายงานที่มีการแบ่งหน้าใน Power BI Premium คืออะไร" สำหรับข้อมูลเพิ่มเติม

## <a name="editing-power-bi-reports"></a>การแก้ไขรายงาน Power BI

ทั้งในแอปพลิเคชันและบริการ คุณสร้างและแก้ไข *รายงาน* ของ Power BI รายงานสามารถมีตั้งแต่หนึ่งหน้าขึ้นไปได้ พร้อมด้วยวิชวลและชุดของวิชวล เพิ่มบุ๊กมาร์ก ปุ่ม ตัวกรอง และการเจาะลึกข้อมูลเพื่อปรับปรุงการนำทางในรายงานของคุณ

![ภาพหน้าจอของ Power BI Desktop และบริการ Power BI พร้อมส่วนที่มีลำดับเลข](media/service-service-vs-desktop/power-bi-editing-desktop-service.png)

เครื่องมือแก้ไขรายงานใน Power BI Desktop และในบริการมีความคล้ายคลึงกัน โดยมีการสร้างขึ้นจากสามส่วน:  

1. บานหน้าต่างนำทางด้านบนแตกต่างกันใน Power BI Desktop และบริการ    
2. พื้นที่รายงาน     
3. **ช่องข้อมูล** **การแสดงภาพ**และพื้นที่**ตัวกรอง**

วิดีโอนี้แสดงเครื่องมือแก้ไขรายงานใน Power BI Desktop 

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

## <a name="working-in-the-power-bi-service"></a>การทำงานในบริการของ Power BI

### <a name="collaborating"></a>การทำงานร่วมกัน

หลังจากที่คุณสร้างรายงาน คุณสามารถบันทึกลง *พื้นที่ทำงาน* ใน **บริการ Power BI** ซึ่งคุณและเพื่อนร่วมงานของคุณทำงานร่วมกันได้ คุณสร้าง *แดชบอร์ด* ด้านบนของรายงานเหล่านั้น จากนั้น คุณแชร์แดชบอร์ดและรายงานเหล่านั้นกับผู้ใช้รายงานภายในและภายนอกองค์กรของคุณ ผู้ใช้รายงานของคุณดูรายงานเหล่านั้นในบริการ Power BI ใน *มุมมองการอ่าน* ไม่ใช่มุมมองการแก้ไข พวกเขาไม่มีการเข้าถึงคุณลักษณะทั้งหมดที่พร้อมใช้งานสำหรับผู้สร้างรายงาน  คุณยังสามารถแชร์ชุดข้อมูลของคุณและให้ผู้อื่นสร้างรายงานของพวกเขาเองได้ อ่านเพิ่มเติมเกี่ยวกับ [การทำงานร่วมกันในบริการ Power BI](../collaborate-share/service-new-workspaces.md)

### <a name="self-service-data-prep-with-dataflows"></a>การเตรียมข้อมูลด้วยตัวเองโดยใช้กระแสข้อมูล

กระแสข้อมูลช่วยให้องค์กรรวมข้อมูลจากแหล่งที่แตกต่างกันอย่างสิ้นเชิง และเตรียมข้อมูลนั้นเพื่อทำแบบจำลอง นักวิเคราะห์สามารถสร้างกระแสข้อมูลได้ง่ายๆ ด้วยการใช้เครื่องมือแบบบริการตนเองที่คุ้นเคยกันดี นักวิเคราะห์ใช้กระแสข้อมูลเพื่อนำเข้า แปลง ผสานรวม และเติมแต่งข้อมูลขนาดใหญ่โดยการกำหนดการเชื่อมต่อของแหล่งข้อมูล, ตรรกะ ETL, กำหนดการรีเฟรช และอื่นๆ อ่านเพิ่มเติมเกี่ยวกับ [การเตรียมข้อมูลด้วยตัวเองโดยใช้กระแสข้อมูล](../transform-model/service-dataflows-overview.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป

[Power BI Desktop คืออะไร](desktop-what-is-desktop.md)

[สร้างรายงาน](../create-reports/service-report-create-new.md)นี้ในบริการของ Power BI

[แนวคิดพื้นฐานสำหรับนักออกแบบรายงาน](service-basic-concepts.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)

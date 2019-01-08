---
title: เชื่อมต่อกับ Smartsheet ด้วย Power BI
description: Smartsheet สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 55d61e89b1fb01de472d967a312b25340d482951
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008478"
---
# <a name="connect-to-smartsheet-with-power-bi"></a>เชื่อมต่อกับ Smartsheet ด้วย Power BI
Smartsheet มีแพลตฟอร์มอย่างง่าย สำหรับการทำงานร่วมกันและการแชร์ไฟล์ ชุดเนื้อหา Smartsheet สำหรับ Power BI มีแดชบอร์ด รายงาน และชุดข้อมูลที่แสดงภาพรวมของบัญชี Smartsheet ของคุณ คุณยังสามารถใช้ [Power BI Desktop](desktop-connect-to-data.md) เพื่อเชื่อมต่อโดยตรงไปยังแต่ละแผ่นงานในบัญชีของคุณได้ 

เชื่อมต่อไปยัง[ชุดเนื้อหา Smartsheet](https://app.powerbi.com/groups/me/getdata/services/smartsheet) สำหรับ Power BI

>[!NOTE]
>บัญชีผู้ดูแลระบบ Smartsheet เป็นบัญชีที่แนะนำสำหรับการเชื่อมต่อ และโหลดชุดเนื้อหา Power BI เนื่องจากมีการเข้าถึงเพิ่มเติม

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-smartsheet/pbi_getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-smartsheet/pbi_getservices.png) 
3. เลือก **Smartsheet \> รับ**
   
   ![](media/service-connect-to-smartsheet/smartsheet.png)
4. สำหรับวิธีการรับรองความถูกต้อง เลือก **oAuth2 \> ลงชื่อเข้าใช้**
   
   เมื่อได้รับพร้อมท์ ใส่ข้อมูลประจำตัวของ Smartsheet และทำตามกระบวนการรับรองความถูกต้อง
   
   ![](media/service-connect-to-smartsheet/creds.png)
   
   ![](media/service-connect-to-smartsheet/creds2.png)
5. หลังจากที่ Power BI นำเข้าข้อมูลแล้ว คุณจะเห็นแดชบอร์ด รายงาน และชุดข้อมูลใหม่ ในบานหน้าต่างนำทางด้านซ้ายมือ รายการใหม่จะถูกทำเครื่องหมาย ด้วยเครื่องหมายดอกจันสีเหลือง \* เลือกรายการ Smartsheet
   
   ![](media/service-connect-to-smartsheet/dashboard.png)

**ฉันต้องทำอะไรต่อ?**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
ชุดเนื้อหา Smartsheet สำหรับ Power BI มีภาพรวมของบัญชี Smartsheet ของคุณ เช่น จำนวนของพื้นที่ทำงาน รายงาน และแผ่นงานที่คุณมี เมื่อใดที่ถูกแก้ไข ฯลฯ ผู้ใช้ที่เป็นผู้ดูแลระบบ จะเห็นข้อมูลเกี่ยวกับผู้ใช้ในระบบของพวกเขา เช่น ผู้ที่สร้างแผ่นงานอันดับต้น ๆ  

เพื่อเชื่อมต่อโดยตรงไปยังแต่ละแผ่นงานในบัญชีของคุณ คุณสามารถใช้ตัวเชื่อมต่อ Smartsheet ใน [Power BI Desktop](desktop-connect-to-data.md) ได้  

## <a name="next-steps"></a>ขั้นตอนถัดไป:

[Power BI คืออะไร](power-bi-overview.md)

[รับข้อมูลสำหรับ Power BI](service-get-data.md)
---
title: เชื่อมต่อกับ Smartsheet ด้วย Power BI
description: Smartsheet สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: b30e9934c6a1779538aeb5fe82db59e018fdb880
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34249470"
---
# <a name="connect-to-smartsheet-with-power-bi"></a>เชื่อมต่อกับ Smartsheet ด้วย Power BI
Smartsheet มีแพลตฟอร์มอย่างง่าย สำหรับการทำงานร่วมกันและการแชร์ไฟล์ ชุดเนื้อหา Smartsheet สำหรับ Power BI มีแดชบอร์ด รายงาน และชุดข้อมูลที่แสดงภาพรวมของบัญชี Smartsheet ของคุณ คุณยังสามารถใช้ [Power BI Desktop](desktop-connect-to-data.md) เพื่อเชื่อมต่อโดยตรงไปยังแต่ละแผ่นงานในบัญชีของคุณได้ 

เชื่อมต่อไปยัง[ชุดเนื้อหา Smartsheet](https://app.powerbi.com/groups/me/getdata/services/smartsheet) สำหรับ Power BI

>[!NOTE]
>บัญชีผู้ดูแลระบบ Smartsheet เป็นบัญชีที่แนะนำสำหรับการเชื่อมต่อ และโหลดชุดเนื้อหา Power BI เนื่องจากมีการเข้าถึงเพิ่มเติม

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือก**รับข้อมูล**ที่ด้านล่างของบานหน้าต่างนำทางด้านซ้าย
   
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

* ลอง[ถามคำถามในกล่องถามตอบ](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานพื้นฐาน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
ชุดเนื้อหา Smartsheet สำหรับ Power BI มีภาพรวมของบัญชี Smartsheet ของคุณ เช่น จำนวนของพื้นที่ทำงาน รายงาน และแผ่นงานที่คุณมี เมื่อใดที่ถูกแก้ไข ฯลฯ ผู้ใช้ที่เป็นผู้ดูแลระบบ จะเห็นข้อมูลเกี่ยวกับผู้ใช้ในระบบของพวกเขา เช่น ผู้ที่สร้างแผ่นงานอันดับต้น ๆ  

เพื่อเชื่อมต่อโดยตรงไปยังแต่ละแผ่นงานในบัญชีของคุณ คุณสามารถใช้ตัวเชื่อมต่อ Smartsheet ใน [Power BI Desktop](desktop-connect-to-data.md) ได้  

## <a name="next-steps"></a>ขั้นตอนถัดไป:

[เริ่มต้นใช้งานด้วย Power BI](service-get-started.md)

[รับข้อมูลสำหรับ Power BI](service-get-data.md)
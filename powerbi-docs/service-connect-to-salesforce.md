---
title: เชื่อมต่อกับ Salesforce ด้วย Power BI
description: Salesforce สำหรับ Power BI
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
ms.openlocfilehash: 8089c796441fd4200b146da6330dd5c208bf8b30
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815678"
---
# <a name="connect-to-salesforce-with-power-bi"></a>เชื่อมต่อกับ Salesforce ด้วย Power BI
ด้วย Power BI คุณสามารถเชื่อมต่อกับบัญชี Salesforce.com ของคุณได้อย่างง่ายดาย สร้างการเชื่อมต่อนี้เพื่อดึงข้อมูลของคุณและมีแดชบอร์ด และรายงานที่เกี่ยวข้องที่ยึดตามข้อมูลของคุณโดยอัตโนมัติ

เชื่อมต่อกับ[ชุดเนื้อหา Salesforce](https://app.powerbi.com/getdata/services/salesforce)สำหรับ Power BI หรืออ่านเพิ่มเติมเกี่ยวกับการ[รวม Salesforce](https://powerbi.microsoft.com/integrations/salesforce)ด้วย Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-salesforce/pbi_getdata.png) 
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-salesforce/pbi_getservices.png) 
3. คลิก**Salesforce**และเลือก**รับ**  
   
   ![](media/service-connect-to-salesforce/salesforce.png)
4. เลือก**ลงชื่อเข้าใช้**เพื่อเริ่มต้นขั้นตอนการเข้าสู่ระบบ
   
    ![](media/service-connect-to-salesforce/dialog.png)
5. เมื่อมีข้อความถาม ให้ใส่ข้อมูลประจำตัวของ Salesforce คลิก**อนุญาต**เพื่อให้ Power BI สามารถเข้าถึงข้อมูล Salesforce พื้นฐานและข้อมูลของคุณ
   
   ![](media/service-connect-to-salesforce/sf_authorize.png)
6. กำหนดค่าสิ่งที่คุณต้องการนำเข้าลงใน Power BI โดยใช้ตัวเลือกรายการแบบดร๊อปดาวน์
   
   * **แดชบอร์ด**
     
     เลือกแดชบอร์ดที่กำหนดไว้ล่วงหน้าโดยยึดตาม persona (เช่น**ผู้จัดการฝ่ายขาย**) แดชบอร์ดเหล่านี้นำชุดข้อมูลมาตรฐานเฉพาะจาก Salesforce และจะไม่รวมเขตข้อมูลแบบกำหนดเอง
     
     ![](media/service-connect-to-salesforce/pbi_salesforcechooserole.png)
   * **รายงาน**
     
     เลือกอย่างน้อยหนึ่งรายงานแบบกำหนดเองจากบัญชี Salesforce ของคุณ รายงานเหล่านี้จะตรงกับมุมมองของคุณใน Salesforce และสามารถรวมข้อมูลจากเขตข้อมูลแบบกำหนดเองหรือวัตถุ
     
     ![](media/service-connect-to-salesforce/pbi_salesforcereports.png)
     
     ถ้าคุณไม่เห็นรายงานใดๆ ให้เพิ่มหรือสร้าบัญชี Salesforce ของคุณ แล้วลองเชื่อมต่ออีกครั้ง
7. คลิก **เชื่อมต่อ** เพื่อเริ่มกระบวนการนำเข้า ในระหว่างการนำเข้า คุณเห็นการแจ้งเตือนที่แสดงว่าการนำเข้ากำลังดำเนินการอยู่ เมื่อการนำเข้าเสร็จสมบูรณ์ คุณจะเห็นแดชบอร์ด รายงาน และชุดข้อมูลสำหรับข้อมูล Salesforce ของที่คุณแสดงอยู่ในบานหน้าต่างนำทางทางด้านซ้าย
   
   ![](media/service-connect-to-salesforce/pbi_getdatasalesforcedash.png)

คุณสามารถปรับเปลี่ยนแดชบอร์ดนี้เพื่อแสดงข้อมูลของคุณด้วยวิธีใดก็ตามที่คุณต้องการ คุณสามารถถามคำถาม Q&A หรือคลิกที่ไทล์เพื่อ[เปิดรายงานด้านใน](service-dashboard-tiles.md)และ[เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานด้านใน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="system-requirements"></a>ความต้องการของระบบ
* เชื่อมต่อกับบัญชีผลิตภัณฑ์ Salesforce ที่สามารถเข้าถึง API ที่เปิดใช้งาน
* สิทธิ์ที่มอบให้กับแอป Power BI ในระหว่างการเข้าสู่ระบบ
* บัญชีมีการเรียกใช้ API เพียงพอที่สามารถใช้งานดึงและรีเฟรชข้อมูล
* โทเค็นรับรองตัวตนที่จำเป็นกับการรีเฟรช ให้ทำให้แน่ใจว่า คุณมีชุดข้อมูล 5 ชุดหรือน้อยกว่า ชุดข้อมูล Salesforce ที่ถูกนำเข้า ด้วยที่ Salesforce มีขีดจำกัดของโทเค็นการรับรองความถูกต้อง 5 ตัวสำหรับแอปพลิเคชัน

## <a name="troubleshooting"></a>การแก้ไขปัญหา
ถ้าคุณพบข้อผิดพลาดใดๆ โปรดตรวจสอบความต้องการด้านบน โปรดทราบว่าความสามารถในการเข้าสู่ระบบแบบโดเมนแบบกำหนดเองหรือแบบ sandbox ยังไม่รองรับในขณะนี้

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งาน Power BI](service-get-started.md)

[รับข้อมูล](service-get-data.md)


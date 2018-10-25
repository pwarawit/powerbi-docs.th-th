---
title: เชื่อมต่อกับ SparkPost ด้วย Power BI
description: SparkPost สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 5db91d037ae32f43fe703bdc7e589a1ec5a295ca
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/21/2018
ms.locfileid: "46547625"
---
# <a name="connect-to-sparkpost-with-power-bi"></a>เชื่อมต่อกับ SparkPost ด้วย Power BI
ชุดเนื้อหา Power BI สำหรับ SparkPost ให้คุณสามารถดึงชุดข้อมูลที่มีค่าจากบัญชี SparkPost ของคุณ ลงมาในแดชบอร์ดข้อมูลเชิงลึก ในแดชบอร์ดเดียว ด้วยชุดเนื้อหา SparkPost คุณสามารถแสดงภาพสถิติอีเมลโดยรวม รวมถึงโดเมน แคมเปญ และการมีส่วนร่วม แบ่งตาม ISP

เชื่อมต่อไปยัง[ชุดเนื้อหา SparkPost สำหรับ Power BI](https://app.powerbi.com/getdata/services/spark-post)

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-sparkpost/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-sparkpost/services.png)
3. เลือกชุดเนื้อหา **SparkPost** และคลิก**รับ** 
   
   ![](media/service-connect-to-sparkpost/sparkpost.png)
4. เมื่อได้รับพร้อมท์ ระบุคีย์ SparkPost API ของคุณ และเลือกลงชื่อเข้าใช้ ดูรายละเอียดที่ [การค้นหาพารามิเตอร์นี้](#FindingParams) ที่ด้านล่าง
   
   ![](media/service-connect-to-sparkpost/creds.png)
5. ข้อมูลของคุณจะเริ่มโหลด ซึ่งอาจใช้เวลาสักระยะ ขึ้นอยู่กับขนาดของบัญชีคุณ หลังจากที่ Power BI นำเข้าข้อมูลแล้ว คุณจะเห็นแดชบอร์ด รายงาน และชุดข้อมูลเริ่มต้นในบานหน้าต่างนำทางด้านซ้าย พร้อมด้วยข้อมูลสถิติของอีเมลในรอบ 90 วันที่ผ่านมา รายการใหม่จะถูกทำเครื่องหมายด้วย เครื่องหมายดอกจันสีเหลือง \*
   
   ![](media/service-connect-to-sparkpost/dashboard.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
ชุดเนื้อหา SparkPost สำหรับ Power BI รวบรวมข้อมูล เช่น จำนวนคลิกที่ไม่ซ้ำกัน อัตราการยอมรับ อัตราแจ้งการตีกลับ อัตราการล่าช้า อัตราการปฏิเสธ และอีกมากมาย

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>การค้นหาพารามิเตอร์
ชุดเนื้อหาใช้คีย์ API เพื่อเชื่อมต่อกับบัญชี SparkPost ของคุณไปยัง Power BI คุณสามารถค้นหาคีย์ API ของคุณ ในบัญชีคุณได้ที่ บัญชี \> API & SMTP (ดูรายละเอียดเพิ่มเติม[ที่นี่](https://support.sparkpost.com/customer/portal/articles/1933377-create-api-keys)) เราแนะนำให้ใช้คีย์ API ที่มีสิทธิ์สำหรับ `Message Events: Read-only ` และ `Metrics: Read-only`

![](media/service-connect-to-sparkpost/sparkpost1.png)


---
title: เชื่อมต่อกับ SQL Sentry ด้วย Power BI
description: SQL Sentry สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 1fc8decc70ade009a7c4236686cfe9cf72adb54d
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008936"
---
# <a name="connect-to-sql-sentry-with-power-bi"></a>เชื่อมต่อกับ SQL Sentry ด้วย Power BI
วิเคราะห์ข้อมูลประสิทธิภาพการทำงานของคุณที่รวบรวมโดย SQL Sentry ทำได้ง่ายขึ้นด้วย Power BI Power BI เรียกคืนข้อมูลของคุณ จากนั้นสร้างแดชบอร์ดค่าเริ่มต้นและรายงานที่เกี่ยวข้องที่ยึดตามข้อมูลนั้น

เชื่อมต่อไปยัง[ชุดเนื้อหา SQL Sentry สำหรับ Power BI](https://app.powerbi.com/groups/me/getdata/services/sql-sentry)

>[!NOTE]
>การเข้าถึงบัญชี SQL Sentry ที่คุณใช้สำหรับการเชื่อมต่อกับ http://cloud.sqlsentry.com และ ID ฐานข้อมูลที่คุณจะติดตาม จำเป็นสำหรับการเชื่อมต่อ  คำแนะนำสำหรับตำแหน่งที่จะค้นหา ID ของฐานข้อมูล มีอยู่ที่ด้านล่าง

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-sql-sentry/pbi_getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-sql-sentry/pbi_getservices.png) 
3. เลือก**SQL Sentry \>รับ**
   
   ![](media/service-connect-to-sql-sentry/sqlsentry.png)
4. ให้**ID ฐานข้อมูล**ของฐานข้อมูลที่คุณต้องการตรวจสอบใน Power BI ดูรายละเอียดเพิ่มเติมที่[การค้นหานี้](#FindingParams)ที่ด้านล่าง
   
   ![](media/service-connect-to-sql-sentry/img2400.png)
5. สำหรับวิธีการรับรองความถูกต้อง ให้เลือก **oAuth2\> ลงชื่อเข้าใช้**
   
   เมื่อได้รับข้อความปรากฏขึ้น ให้ใส่ข้อมูลประจำตัวของ cloud.sqlsentry.com และทำตามกระบวนการรับรองความถูกต้องสำหรับ SQL Sentry
   
   ![](media/service-connect-to-sql-sentry/img6400.png)
   
   ในครั้งแรกที่คุณเชื่อมต่อ Power BI จะปรากฏข้อความให้คุณอนุญาตให้เข้าถึงแบบอ่านอย่างเดียวสำหรับบัญชีของคุณ เลือก อนุญาต เพื่อเริ่มกระบวนการนำเข้า  กระบวนการนำเข้าอาจใช้เวลาสักครู่ โดยขึ้นอยู่กับปริมาณของข้อมูลในบัญชีของคุณ
   
   ![](media/service-connect-to-sql-sentry/img7400.png)
6. หลังจาก Power BI นำเข้าข้อมูล คุณจะเห็นแดชบอร์ด รายงาน และชุดข้อมูลใหม่ในแผงนำทางด้านซ้าย รายการใหม่จะถูกทำเครื่องหมายด้วย เครื่องหมายดอกจันสีเหลือง\*:
   
   ![](media/service-connect-to-sql-sentry/img8200.png)
7. เลือกแดชบอร์ด SQL Sentry
   
   นี่คือแดชบอร์ดตามเริ่มต้นที่ Power BI สร้างขึ้นเพื่อแสดงข้อมูลของคุณ คุณสามารถปรับเปลี่ยนแดชบอร์ดนี้เพื่อแสดงข้อมูลของคุณด้วยวิธีใดก็ตามที่คุณต้องการ
   
   ![](media/service-connect-to-sql-sentry/img9dashboard800.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
ข้อมูลต่อไปนี้จะพร้อมใช้งานจาก SQL Sentry ใน Power BI:

| ชื่อตาราง | คำอธิบาย |
| --- | --- |
| การเชื่อมต่อ |ตารางนี้แสดงข้อมูลเกี่ยวกับการเชื่อมต่อ SQL Sentry ที่กำหนดเองของคุณ |
| วันที่<br /> |ตารางนี้ประกอบด้วยวันที่จากวันนี้ย้อนกลับไปยังวันที่แรกสุดที่มีการรวบรวมและเก็บรักษาข้อมูลประสิทธิภาพการทำงาน |
| ช่วงเวลาเครื่องไม่ทำงาน<br /> |ตารางนี้ประกอบด้วยข้อมูลที่เกี่ยวข้องกับช่วงหยุดทำงานและช่วงพร้อมใช้งานสำหรับแต่ละเซิร์ฟเวอร์ที่ถูกตรวจติดตามในสภาพแวดล้อมของคุณ |
| การใช้หน่วยความจำ<br /> |ตารางนี้ประกอบด้วยข้อมูลเกี่ยวกับปริมาณหน่วยความจำพร้อมใช้งานหรือฟรีในแต่ละเซิร์ฟเวอร์ของคุณ<br /> |
| เซิร์ฟเวอร์<br /> |ตารางนี้ประกอบด้วยบันทึกสำหรับแต่ละเซิร์ฟเวอร์ในสภาพแวดล้อมของคุณ |
| สถานภาพเซิร์ฟเวอร์<br /> |ตารางนี้ประกอบด้วยข้อมูลสำหรับเหตุการณ์ทั้งหมดที่สร้างขึ้นโดยเงื่อนไขแบบกำหนดเองในสภาพแวดล้อมของคุณ รวมถึงความร้ายแรงและจำนวนด้วย |

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>การค้นหาพารามิเตอร์
**ID ฐานข้อมูล**สามารถพบได้โดยการเข้าสู่ระบบ<https://cloud.sqlsentry.com>ในหน้าต่างเว็บเบราว์เซอร์ใหม่  **ID ฐานข้อมูล**จะแสดงอยู่บนเพจภาพรวมหลัก:

    ![](media/service-connect-to-sql-sentry/database2.png)

**ID ฐานข้อมูล**จะแสดงขึ้นบนหน้าจอรายละเอียดฐานข้อมูล:

    ![](media/service-connect-to-sql-sentry/database.png)


## <a name="troubleshooting"></a>การแก้ไขปัญหา
ถ้าระบบไม่แสดงข้อมูลจากบางแอปฯของคุณใน Power BI ตรวจสอบให้แน่ใจว่า คุณกำลังใช้ ID ฐานข้อมูลที่ถูกต้องและที่คุณมีสิทธิ์ในการดูข้อมูล 

ถ้าคุณไม่ได้เป็นเจ้าของฐานข้อมูล SQL Sentry ที่มีการซิงโครไนซ์อยู่ <https://cloud.sqlsentry.com>โปรดติดต่อผู้ดูแลระบบของคุณเพื่อให้แน่ใจว่าคุณมีสิทธิ์ในการดูข้อมูลที่รวบรวมไว้

## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI คืออะไร](power-bi-overview.md)

[รับข้อมูลสำหรับ Power BI](service-get-data.md)


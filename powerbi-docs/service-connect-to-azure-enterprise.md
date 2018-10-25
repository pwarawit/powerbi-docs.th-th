---
title: เชื่อมต่อกับ Microsoft Azure Enterprise ด้วย Power BI
description: Microsoft Azure Enterprise สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 93e1534af258a11a7af0f95b179653a1d8e54307
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/21/2018
ms.locfileid: "46544658"
---
# <a name="connect-to-microsoft-azure-enterprise-with-power-bi"></a>เชื่อมต่อกับ Microsoft Azure Enterprise ด้วย Power BI
สำรวจและตรวจติดตามข้อมูล Microsoft Azure Enterprise ของคุณใน Power BI ด้วยชุดเนื้อหา Power BI ข้อมูลจะรีเฟรชโดยอัตโนมัติหนึ่งครั้งต่อวัน

เชื่อมต่อไปยัง[ชุดเนื้อหา Microsoft Azure Enterprise](https://app.powerbi.com/getdata/services/azure-enterprise)สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
    ![](media/service-connect-to-azure-enterprise/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-azure-enterprise/services.png)
3. เลือก**Microsoft Azure Enterprise** \> **รับ**
   
   ![](media/service-connect-to-azure-enterprise/mazureenterprise.png)
4. ระบุ URL ของสภาพแวดล้อม Azure จำนวนเดือนของข้อมูลที่คุณต้องการนำเข้าและจำนวนการลงทะเบียน Azure Enterprise ของคุณ URL สำหรับสภาพแวดล้อม Azure ของคุณจะเป็น `https://ea.azure.com`หรือ`https://ea.windowsazure.cn` ดูรายละเอียด [ค้นหาพารามิเตอร์เหล่านี้](#FindingParams) ที่ด้านล่าง
   
    ![](media/service-connect-to-azure-enterprise/params.png)
5. ใส่คีย์การเข้าถึงเพื่อเชื่อมต่อ สามารถพบคีย์สำหรับการลงทะเบียนของคุณ ได้ในพอร์ทัล Azure EA ของคุณ
   
    ![](media/service-connect-to-azure-enterprise/creds.png)
6. กระบวนการนำเข้าจะเริ่มโดยอัตโนมัติ เมื่อเสร็จสิ้น แดชบอร์ดใหม่ รายงาน และแบบจำลองจะปรากฏในบานหน้าต่างนำทาง เลือกแดชบอร์ดเพื่อดูข้อมูลที่นำเข้าของคุณ
   
   ![](media/service-connect-to-azure-enterprise/dashboard.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
ชุดเนื้อหา Azure Enterprise รวมข้อมูลรายงานรายเดือนสำหรับช่วงของเดือนที่คุณระบุในระหว่างขั้นตอนการเชื่อมต่อ ช่วงวันที่จะเป็นหน้าต่างเคลื่อนที่ได้ ดังนั้นวันที่รวมอยู่จะถูกอัปเดตเมื่อรีเฟรชชุดข้อมูล

## <a name="system-requirements"></a>ข้อกำหนดของระบบ
ชุดเนื้อหานี้จำเป็นต้องเข้าถึงคุณลักษณะ Enterprise ภายในพอร์ทัล Azure

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>การค้นหาพารามิเตอร์
การรายงาน Power BI มีสำหรับ EA Direct, คู่ค้า และลูกค้าทางอ้อม ผู้ที่สามารถดูข้อมูลการเรียกเก็บเงินได้ โปรดอ่านข้อมูลด้านล่างนี้สำหรับรายละเอียดการค้นหาแต่ละค่าที่คาดหมายสำหรับขั้นตอนการเชื่อมต่อ

**URL ของสภาพแวดล้อม Azure**

* โดยทั่วไปแล้วค่านี้คือ https://ea.azure.com อย่างไรก็ตามคุณสามารถตรวจสอบ URL ได้เมื่อคุณลงชื่อเข้าใช้เพื่อยืนยัน
  
    ![](media/service-connect-to-azure-enterprise/params3.png)

**จำนวนเดือน**

* ควรเป็นตัวเลขระหว่าง 1-36 แทนจำนวนเดือนของข้อมูล (นับจากวันนี้) ที่คุณต้องการนำเข้า

**หมายเลขการลงทะเบียน**

* คือหมายเลขการลงทะเบียน Azure Enterprise ของคุณ ซึ่งจะพบได้บนหน้าจอหลักของ [พอร์ทัล Azure Enterprise](https://ea.azure.com/) ภายใต้ "รายละเอียดการลงทะเบียน"
  
    ![](media/service-connect-to-azure-enterprise/params2.png)

**คีย์การเข้าถึง**

* สามารถพบคีย์ของคุณในพอร์ทัล Azure Enterprise ภายใต้ "ดาวน์โหลดการใช้งาน" > "คีย์การเข้าถึง API"
  
    ![](media/service-connect-to-azure-enterprise/creds2.png)

**ความช่วยเหลือเพิ่มเติม**

* สำหรับความช่วยเหลือเพิ่มเติมในการตั้งค่า Azure Enterprise Power BI Pack เข้าสู่ระบบพอร์ทัล Enterprise Azure เพื่อดูไฟล์ช่วยเหลือ API (API Help File) ภายใต้ "ความช่วยเหลือ" และคำแนะนำเพิ่มเติมภายใต้ รายงาน -> ดาวน์โหลดการใช้งาน -> คีย์การเข้าถึง API

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งานใน Power BI](service-get-started.md)

[รับข้อมูลใน Power BI](service-get-data.md)


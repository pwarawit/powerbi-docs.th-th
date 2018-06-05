---
title: เชื่อมต่อกับ Microsoft Azure Enterprise ด้วย Power BI
description: Microsoft Azure Enterprise สำหรับ Power BI
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
ms.openlocfilehash: 60bcad86af5fcaa09d6b2fb16b581ec7c37264ae
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
ms.locfileid: "30815263"
---
# <a name="connect-to-microsoft-azure-enterprise-with-power-bi"></a>เชื่อมต่อกับ Microsoft Azure Enterprise ด้วย Power BI
สำรวจและตรวจติดตามข้อมูล Microsoft Azure Enterprise ของคุณใน Power BI ด้วยชุดเนื้อหา Power BI ข้อมูลจะรีเฟรชโดยอัตโนมัติหนึ่งครั้งต่อวัน

เชื่อมต่อไปยัง[ชุดเนื้อหา Microsoft Azure Enterprise](https://app.powerbi.com/getdata/services/azure-enterprise)สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือก**รับข้อมูล**ที่ด้านล่างของแผงนำทางด้านซ้ายมือ
   
    ![](media/service-connect-to-azure-enterprise/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-azure-enterprise/services.png)
3. เลือก**Microsoft Azure Enterprise** \> **รับ**
   
   ![](media/service-connect-to-azure-enterprise/mazureenterprise.png)
4. ระบุ URL ของสภาพแวดล้อม Azure จำนวนเดือนของข้อมูลที่คุณต้องการนำเข้าและจำนวนการลงทะเบียน Azure Enterprise ของคุณ URL สำหรับสภาพแวดล้อม Azure ของคุณจะเป็น `https://ea.azure.com`หรือ`https://ea.windowsazure.cn` ดูรายละเอียด [ค้นหาพารามิเตอร์เหล่านี้](#FindingParams) ที่ด้านล่าง
   
    ![](media/service-connect-to-azure-enterprise/params.png)
5. ใส่คีย์การเข้าถึงการเชื่อมต่อ คุณสามารถพบคีย์สำหรับการลงทะเบียนของคุณได้ในพอร์ทัล Azure EA ของคุณ
   
    ![](media/service-connect-to-azure-enterprise/creds.png)
6. กระบวนการนำเข้าจะเริ่มโดยอัตโนมัติ เมื่อเสร็จสิ้น แดชบอร์ดใหม่ รายงาน และแบบจำลองจะปรากฏในบานหน้าต่างนำทาง เลือกแดชบอร์ดเพื่อดูข้อมูลที่นำเข้าของคุณ
   
   ![](media/service-connect-to-azure-enterprise/dashboard.png)

**ฉันต้องทำอะไรต่อ?**

* ลอง[ถามคำถามในกล่องถามตอบ](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานพื้นฐาน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
ชุดเนื้อหา Azure Enterprise รวมข้อมูลรายงานรายเดือนสำหรับช่วงของเดือนที่คุณระบุในระหว่างขั้นตอนการเชื่อมต่อ ช่วงวันที่จะเป็นหน้าต่างเคลื่อนที่ได้ ดังนั้นวันที่รวมอยู่จะถูกอัปเดตเมื่อรีเฟรชชุดข้อมูล

## <a name="system-requirements"></a>ข้อกำหนดของระบบ
ชุดเนื้อหานี้จำเป็นต้องมีการเข้าถึงคุณลักษณะ Enterprise ภายในพอร์ทัล Azure

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>การค้นหาพารามิเตอร์
การรายงาน Power BI จะพร้อมใช้งานสำหรับ EA Direct คู่ค้าและลูกค้าทางอ้อม ซึ่งเป็นผู้ที่สามารถดูข้อมูลการเรียกเก็บเงินได้ โปรดอ่านข้อมูลด้านล่างนี้สำหรับรายละเอียดการค้นหาแต่ละค่าที่คาดหมายสำหรับขั้นตอนการเชื่อมต่อ

**URL ของสภาพแวดล้อม Azure**

* โดยทั่วไปแล้ว ค่านี้คือ https://ea.azure.com อย่างไรก็ ตามคุณสามารถตรวจสอบ URL ได้เมื่อคุณลงชื่อเข้าใช้เพื่อยืนยัน
  
    ![](media/service-connect-to-azure-enterprise/params3.png)

**จำนวนเดือน**

* ส่วนนี้ควรเป็นตัวเลขระหว่าง 1 - 36 ที่แสดงถึงจำนวนเดือนของข้อมูล (จากวันนี้) ที่คุณต้องการนำเข้า

**หมายเลขการลงทะเบียน**

* ส่วนนี้คือตัวเลขการลงทะเบียน Azure Enterprise ของคุณ ซึ่งจะพบได้บนหน้าจอหลักของ [พอร์ทัล Azure Enterprise](https://ea.azure.com/) ใต้ "รายละเอียดการลงทะเบียน"
  
    ![](media/service-connect-to-azure-enterprise/params2.png)

**คีย์การเข้าถึง**

* สามารถพบคีย์ของคุณในพอร์ทัล Azure Enterprise ใต้ "ดาวน์โหลดการใช้งาน" > "API Access Key"
  
    ![](media/service-connect-to-azure-enterprise/creds2.png)

**วิธีใช้เพิ่มเติม**

* สำหรับความช่วยเหลือเพิ่มเติมในการตั้งค่า Azure Enterprise Power BI Pack เข้าสู่ระบบพอร์ทัล Enterprise Azure เพื่อดูไฟล์ช่วยเหลือ API (API Help File) ใต้ "ความช่วยเหลือ" และคำแนะนำเพิ่มเติมใต้รายงาน -> ดาวน์โหลดการใช้งาน -> คีย์การเข้าถึง API

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งานใน Power BI](service-get-started.md)

[รับข้อมูลใน Power BI](service-get-data.md)


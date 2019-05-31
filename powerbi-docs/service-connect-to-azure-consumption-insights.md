---
title: เชื่อมต่อกับข้อมูลรายจ่ายเชิงลึกของ Microsoft Azure ด้วย Power BI
description: ข้อมูลรายจ่ายเชิงลึกของ Microsoft Azure สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/20/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 089f8c31a0b1eb11f6871268f2f848949be95d9b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222127"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>เชื่อมต่อกับข้อมูลรายจ่ายเชิงลึกของ Microsoft Azure ด้วย Power BI
สำรวจ และตรวจสอบข้อมูลรายจ่าย Microsoft Azure ใน Power BI ด้วยชุดเนื้อหา Power BI ข้อมูลถูกรีเฟรชวันละครั้งโดยอัตโนมัติ

เชื่อมต่อไปยัง[ชุดเนื้อหาข้อมูลรายจ่ายเชิงลึกของ Azure Microsoft](https://app.powerbi.com/getdata/services/azureconsumption) สำหรับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
    ![](media/service-connect-to-azure-consumption-insights/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-azure-consumption-insights/services.png)
3. เลือก**Microsoft Azure Consumption Insights** \> **รับทันที** 
   
   ![](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. ใส่จำนวนเดือนของข้อมูลที่คุณต้องการนำเข้า และหมายเลขการลงทะเบียน Azure Enterprise ของคุณ ดูรายละเอียดที่ [การค้นหาพารามิเตอร์เหล่านี้](#FindingParams) ด้านล่าง
   
    ![](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. ใส่คีย์การเข้าถึงเพื่อเชื่อมต่อ คุณสามารถค้นหาคีย์ของคุณลงทะเบียนในพอร์ทัล Azure EA 
   
    ![](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. กระบวนการนำเข้าเริ่มต้นโดยอัตโนมัติ เมื่อเสร็จสมบูรณ์ แดชบอร์ดใหม่ รายงาน และแบบจำลองปรากฏในบานหน้าต่างนำทาง เลือกแดชบอร์ดเพื่อดูข้อมูลที่นำเข้าของคุณ
   
   ![](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* ในขณะที่ชุดข้อมูลของคุณถูกกำหนดให้รีเฟรชรายวัน คุณสามารถเปลี่ยนแปลงกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการใช้**รีเฟรชเดี๋ยวนี้**

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
ชุดเนื้อหา Microsoft Azure Consumption Insights มีข้อมูลสำหรับช่วงเดือนที่คุณใส่เมื่อเชื่อมต่อรายงานรายเดือน ช่วงเป็นหน้าต่างเคลื่อนที่ ดังนั้นวันที่รวมอยู่จะถูกอัปเดเมื่อรีเฟรชชุดข้อมูล

## <a name="system-requirements"></a>ข้อกำหนดของระบบ
ชุดเนื้อหานี้จำเป็นต้องเข้าถึงคุณลักษณะ Enterprise ภายในพอร์ทัล Azure 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>การค้นหาพารามิเตอร์
รายงาน power BI จะพร้อมใช้งานสำหรับ EA Direct คู่ค้า และ ลูกค้าทางอ้อมที่สามารถดูข้อมูลการเรียกเก็บเงิน ต้องการอ่านด้านล่างสำหรับรายละเอียดเกี่ยวกับการค้นหาค่าแต่ละขั้นตอนการเชื่อมต่อ

**จำนวนเดือน**

* จำนวนเดือน (1-36) ของข้อมูลจากวันนี้ที่คุณต้องการนำเข้า

**หมายเลขการลงทะเบียน**

* Azure Enterprise ลงทะเบียนหมายเลขของคุณ ซึ่งคุณสามารถค้นหาที่[Azure Enterprise Portal](https://ea.azure.com/)หน้าจอหลักภายใต้**รายละเอียดการลงทะเบียน**
  
    ![](media/service-connect-to-azure-consumption-insights/params2.png)

**คีย์การเข้าถึง**

* คุณสามารถค้นหาคีย์การเข้าถึงในพอร์ทัล Azure Enterprise ภายใต้**ดาวน์โหลดการใช้งาน** > **แป้นการเข้าถึง API**ได้
  
    ![](media/service-connect-to-azure-consumption-insights/creds2.png)

**ความช่วยเหลือเพิ่มเติม**

* สำหรับความช่วยเหลือเพิ่มเติมการตั้งค่าชุด Azure Enterprise Power BI ลงชื่อเข้าใช้ Azure Enterprise Portal และดูไฟล์การช่วยเหลือ API ภายใต้**ช่วย** คุณยังสามารถค้นหาคำแนะนำเพิ่มเติมภายใต้**รายงาน** -> **ดาวน์โหลดการใช้งาน** -> **แป้นการเข้าถึง API**ได้

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งานใน Power BI](service-get-started.md)

[รับข้อมูลใน Power BI](service-get-data.md)


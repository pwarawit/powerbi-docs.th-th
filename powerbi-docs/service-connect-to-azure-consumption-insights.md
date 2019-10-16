---
title: เชื่อมต่อกับข้อมูลรายจ่ายเชิงลึกของ Microsoft Azure ด้วย Power BI
description: ข้อมูลรายจ่ายเชิงลึกของ Microsoft Azure สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggies
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 09/25/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: e51f936e44e8c8ee3442aedfb2389675774c0a47
ms.sourcegitcommit: 5e277dae93832d10033defb2a9e85ecaa8ffb8ec
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/07/2019
ms.locfileid: "72020441"
---
# <a name="connect-to-microsoft-azure-consumption-insights-with-power-bi"></a>เชื่อมต่อกับข้อมูลรายจ่ายเชิงลึกของ Microsoft Azure ด้วย Power BI
สำรวจและตรวจสอบปริมาณการใช้ข้อมูลของ Microsoft Azure ในบริการของ Power BI ที่มีชุดเนื้อหาของ Power BI ข้อมูลจะถูกรีเฟรชโดยอัตโนมัติวันละหนึ่งครั้ง

เชื่อมต่อไปยัง[ชุดเนื้อหาข้อมูลเชิงลึกในปริมาณการใช้ของ Microsoft Azure](https://app.powerbi.com/getdata/services/azureconsumption) สำหรับบริการของ Power BI

> [!NOTE]
> สำหรับการตั้งค่าแบบกำหนดเองเพิ่มเติม ลองใช้[ตัวเชื่อมต่อข้อมูลเชิงลึกในปริมาณการใช้ของ Azure](desktop-connect-azure-consumption-insights.md) ใน Power BI Desktop

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. ในบริการของ Power BI ให้เลือก**รับข้อมูล**ซึ่งอยู่ด้านล่างของบานหน้าต่างนำทางด้านซ้าย
   
    ![รับข้อมูล](media/service-connect-to-azure-consumption-insights/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![รับบริการ](media/service-connect-to-azure-consumption-insights/services.png)
3. เลือก**ข้อมูลเชิงลึกในปริมาณการใช้ของ Microsoft Azure** \> **รับตอนนี้** 
   
   ![รับทันที](media/service-connect-to-azure-consumption-insights/mazureconsumption.png)
4. ใส่จำนวนเดือนของข้อมูลที่คุณต้องการนำเข้า และหมายเลขการลงทะเบียน Azure Enterprise ของคุณ ดูรายละเอียดที่ [การค้นหาพารามิเตอร์เหล่านี้](#FindingParams) ด้านล่าง
   
    ![เชื่อมต่อกับ Microsoft Azure Consumption Insights](media/service-connect-to-azure-consumption-insights/azureconsumptionparams.png)
5. ใส่คีย์การเข้าถึงเพื่อเชื่อมต่อ คุณสามารถค้นหาคีย์การลงทะเบียนของคุณได้ในพอร์ทัล Azure EA 
   
    ![ข้อมูลเชิงลึกในปริมาณการใช้ของ Microsoft Azure: คีย์](media/service-connect-to-azure-consumption-insights/msazureconsumptioncreds.png)
6. กระบวนการนำเข้าเริ่มต้นโดยอัตโนมัติ เมื่อเสร็จสิ้นแล้ว แดชบอร์ด รายงาน และแบบจำลองใหม่จะปรากฏในบานหน้าต่างนำทาง เลือกแดชบอร์ดเพื่อดูข้อมูลที่นำเข้าของคุณ
   
   ![แดชบอร์ดข้อมูลเชิงลึกในปริมาณการใช้ของ Microsoft Azure](media/service-connect-to-azure-consumption-insights/msazureconsumptiondashboard.png)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](consumer/end-user-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถปรับเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้ **รีเฟรชตอนนี้**

## <a name="whats-included"></a>มีอะไรรวมอยู่บ้าง
ชุดเนื้อหาข้อมูลเชิงลึกในปริมาณการใช้ของ Microsoft Azure จะประกอบด้วยข้อมูลการรายงานประจำเดือนสำหรับช่วงเดือนที่คุณระบุเมื่อเชื่อมต่อ ช่วงจะเป็นหน้าต่างเคลื่อนที่ ดังนั้นวันที่ที่รวมอยู่จะได้รับการอัปเดตเมื่อมีการรีเฟรชชุดข้อมูล

## <a name="system-requirements"></a>ข้อกำหนดของระบบ
ชุดเนื้อหานี้จำเป็นต้องเข้าถึงคุณลักษณะขององค์กรภายในพอร์ทัล Azure 

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>การค้นหาพารามิเตอร์
การรายงาน Power BI มีสำหรับ EA Direct, คู่ค้า และลูกค้าทางอ้อม ผู้ที่สามารถดูข้อมูลการเรียกเก็บเงินได้ อ่านรายละเอียดด้านล่าง เพื่อค้นหาค่าแต่ละค่าที่ต้องใช้ในตอนเชื่อมต่อ

**จำนวนเดือน**

* จำนวนเดือน (1-36) ของข้อมูลจากวันนี้ที่คุณต้องการนำเข้า

**หมายเลขการลงทะเบียน**

* หมายเลขการลงทะเบียน Azure Enterprise ของคุณ ซึ่งจะพบได้ที่หน้าจอหลักของ[พอร์ทัล Azure Enterprise](https://ea.azure.com/) ภายใต้ **รายละเอียดการลงทะเบียน**
  
    ![จำนวนการลงทะเบียน](media/service-connect-to-azure-consumption-insights/params2.png)

**คีย์การเข้าถึง**

* สามารถค้นหาคีย์การเข้าถึงของคุณในพอร์ทัล Azure Enterprise ภายใต้**ดาวน์โหลดการใช้งาน** > **คีย์การเข้าถึง API**
  
    ![คีย์การเข้าถึง](media/service-connect-to-azure-consumption-insights/creds2.png)

**ความช่วยเหลือเพิ่มเติม**

* สำหรับความช่วยเหลือเพิ่มเติมในการตั้งค่าชุด Azure Enterprise Power BI ให้ลงชื่อเข้าใช้ในพอร์ทัล Azure Enterprise และดูไฟล์วิธีใช้ API ภายใต้**ความช่วยเหลือ** นอกจากนี้ คุณยังสามารถค้นหาคำแนะนำเพิ่มเติมภายใต้**รายงาน** -> **ดาวน์โหลดการใช้งาน** -> **คีย์การเข้าถึง API**
* สำหรับการตั้งค่าแบบกำหนดเองเพิ่มเติม ลองใช้[ตัวเชื่อมต่อข้อมูลเชิงลึกในปริมาณการใช้ของ Azure](desktop-connect-azure-consumption-insights.md) ใน Power BI Desktop

## <a name="next-steps"></a>ขั้นตอนถัดไป

[ตัวเชื่อมต่อข้อมูลเชิงลึกในปริมาณการใช้ของ Azure](desktop-connect-azure-consumption-insights.md) ใน Power BI Desktop

[รับข้อมูลใน Power BI](service-get-data.md)


---
title: ข้อมูลสดของ SQL Server Analysis Services ใน Power BI
description: ข้อมูลสดของ SQL Server Analysis Services ใน Power BI สิ่งนี้สามารถทำได้ผ่านแหล่งข้อมูล ที่ถูกกำหนดค่าสำหรับเกตเวย์เอ็นเตอร์ไพรส์
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
author: Minewiskan
ms.author: owend
ms.reviewer: ''
ms.custom: ''
ms.date: 08/10/2017
LocalizationGroup: Data from databases
ms.openlocfilehash: 3bbe3763ecf17fe80d1b3859f18e105e566e14ee
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83281541"
---
# <a name="sql-server-analysis-services-live-data-in-power-bi"></a>ข้อมูลสดของ SQL Server Analysis Services ใน Power BI

ใน Power BI มีสองวิธีที่คุณสามารถเชื่อมต่อสดกับเซิร์ฟเวอร์ SQL Server Analysis Services ใน**รับข้อมูล** คุณสามารถเชื่อมต่อกับเซิร์ฟเวอร์ SQL Server Analysis Services หรือคุณสามารถเชื่อมต่อกับ[ไฟล์ Power BI Desktop](service-desktop-files.md) หรือ[สมุดงาน Excel](service-excel-workbook-files.md) ที่เชื่อมต่อกับเซิร์ฟเวอร์ Analysis Services อยู่แล้ว แนวทางปฏิบัติที่ดีที่สุด Microsoft ขอแนะนำให้ใช้ Power BI Desktop เนื่องจากความสมบูรณ์ของชุดเครื่องมือตัวและความสามารถในการรักษาสำเนาสำรองของไฟล์ Power BI Desktop ภายในเครื่อง

>[!IMPORTANT]
> * เพื่อเชื่อมต่อสดไปยังเซิร์ฟเวอร์ Analysis Services เกตเวย์ข้อมูลภายในองค์กร ต้องถูกติดตั้งและกำหนดค่าโดยผู้ดูแลระบบ สำหรับข้อมูลเพิ่มเติม ดู[เกตเวย์ข้อมูลภายในองค์กร](service-gateway-onprem.md)
> * เมื่อคุณใช้เกตเวย์ ข้อมูลของคุณยังคงอยู่ภายในองค์กร  รายงานที่คุณสร้างขึ้นจากข้อมูลนั้น จะถูกบันทึกในบริการของ Power BI 
> * [ถามตอบ คิวรีด้วยภาษาธรรมชาติ](../create-reports/service-q-and-a-direct-query.md) ยังเป็นคุณลักษณะตัวอย่าง สำหรับการเชื่อมต่อ Analysis Services แบบสด

## <a name="to-connect-to-a-model-from-get-data"></a>เชื่อมต่อกับรูปแบบข้อมูลจาก รับข้อมูล

1. ใน**พื้นที่ทำงานของฉัน** เลือก**รับข้อมูล** คุณยังสามารถเปลี่ยนไปยังพื้นที่ทำงานกลุ่ม ถ้ามี

   ![เชื่อมต่อเพื่อรับปุ่มข้อมูล](media/sql-server-analysis-services-tabular-data/connecttoas_getdatabutton.png)

2. เลือก**ฐานข้อมูลและอื่นๆ อีกมากมาย**

   ![เชื่อมต่อเพื่อรับข้อมูล 1](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_1.png)

3. เลือก **SQL Server Analysis Services** > **เชื่อมต่อ**

   ![เชื่อมต่อเพื่อรับข้อมูล 2](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_2.png)

4. เลือกเซิร์ฟเวอร์ ถ้าคุณไม่เห็นเซิร์ฟเวอร์ใดเลยในนี้ แสดงว่ายังไม่ได้กำหนดเกตเวย์และแหล่งข้อมูล หรือบัญชีของคุณไม่ได้อยู่ในรายการในแท็บ**ผู้ใช้**ของแหล่งข้อมูลในเกตเวย์ ตรวจสอบกับผู้ดูแลของคุณ

5. เลือกรูปแบบที่คุณต้องการเชื่อมต่อ ซึ่งอาจเป็นแบบตาราง หรือแบบหลายมิติ

หลังจากคุณเชื่อมต่อกับรูปแบบแล้ว จะปรากฏในไซต์ Power BI ของคุณใน**พื้นที่ทำงาน/ชุดข้อมูลของฉัน** ถ้าคุณสลับไปยังพื้นที่ทำงานกลุ่ม ชุดข้อมูลจะปรากฏขึ้นภายในกลุ่ม

![เชื่อมต่อกับชุดข้อมูล](media/sql-server-analysis-services-tabular-data/connecttoas_dataset_5.png)

## <a name="dashboard-tiles"></a>ไทล์แดชบอร์ด

ถ้าคุณปักหมุดวิชวลจากรายงานไปยังแดชบอร์ด ไทล์ที่ปักหมุดไว้จะรีเฟรชทุก 10 นาทีโดยอัตโนมัติ ถ้ามีการอัปเดตข้อมูลในเซิร์ฟเวอร์ Analysis Services ภายในองค์กรของคุณ ไทล์จะได้รับการปรับปรุงอัตโนมัติหลังผ่านไป 10 นาที

## <a name="common-issues"></a>ปัญหาที่พบบ่อย

* ข้อผิดพลาด ไม่สามารถโหลดเค้าร่างแบบจำลอง - ข้อผิดพลาดนี้เกิดขึ้นเมื่อผู้ใช้เชื่อมต่อกับ SSAS ไม่ได้รับอนุญาตให้เข้าถึงฐานข้อมูล SSAS, คิวบ์ และแบบจำลอง

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [เกตเวย์ข้อมูลภายในองค์กร](service-gateway-onprem.md)  
* [จัดการแหล่งข้อมูล Analysis Services](service-gateway-enterprise-manage-ssas.md)  
* [การแก้ไขปัญหา เกตเวย์ข้อมูลในองค์กร](service-gateway-onprem-tshoot.md)  

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)
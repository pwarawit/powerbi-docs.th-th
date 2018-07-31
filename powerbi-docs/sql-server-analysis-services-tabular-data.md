---
title: ข้อมูลสดของ SQL Server Analysis Services ใน Power BI
description: ข้อมูลสดของ SQL Server Analysis Services ใน Power BI สิ่งนี้สามารถทำได้ผ่านแหล่งข้อมูล ที่ถูกกำหนดค่าสำหรับเกตเวย์เอ็นเตอร์ไพรส์
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: maghan
LocalizationGroup: Data from databases
ms.openlocfilehash: 86dabdb84dd4ca949930c25213f554060135f10a
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/26/2018
ms.locfileid: "34722965"
---
# <a name="sql-server-analysis-services-live-data-in-power-bi"></a>ข้อมูลสดของ SQL Server Analysis Services ใน Power BI
ใน Power BI มีสองวิธีที่คุณสามารถเชื่อมต่อสดกับเซิร์ฟเวอร์ SQL Server Analysis Services ใน**รับข้อมูล** คุณสามารถเชื่อมต่อกับเซิร์ฟเวอร์ SQL Server Analysis Services หรือคุณสามารถเชื่อมต่อกับ[ไฟล์ Power BI Desktop](service-desktop-files.md) หรือ[สมุดงาน Excel](service-excel-workbook-files.md) ที่เชื่อมต่อกับเซิร์ฟเวอร์ Analysis Services อยู่แล้ว แนวทางปฏิบัติที่ดีที่สุด Microsoft ขอแนะนำให้ใช้ Power BI Desktop เนื่องจากความสมบูรณ์ของชุดเครื่องมือตัวและความสามารถในการรักษาสำเนาสำรองของไฟล์ Power BI Desktop ภายในเครื่อง

 >[!IMPORTANT]
 >* เพื่อเชื่อมต่อสดไปยังเซิร์ฟเวอร์ Analysis Services เกตเวย์ข้อมูลภายในองค์กร ต้องถูกติดตั้งและกำหนดค่าโดยผู้ดูแลระบบ สำหรับข้อมูลเพิ่มเติม ดู[เกตเวย์ข้อมูลภายในองค์กร](service-gateway-onprem.md)
 >* เมื่อคุณใช้เกตเวย์ ข้อมูลของคุณยังคงอยู่ภายในองค์กร  รายงานที่คุณสร้างขึ้นจากข้อมูลนั้น จะถูกบันทึกในบริการของ Power BI 
 >* [ถามตอบ คิวรีด้วยภาษาธรรมชาติ](service-q-and-a-direct-query.md) ยังเป็นคุณลักษณะตัวอย่าง สำหรับการเชื่อมต่อ Analysis Services แบบสด

## <a name="to-connect-to-a-model-from-get-data"></a>เชื่อมต่อกับรูปแบบข้อมูลจาก รับข้อมูล
1. ใน**พื้นที่ทำงานของฉัน** เลือก**รับข้อมูล** คุณยังสามารถเปลี่ยนไปยังพื้นที่ทำงานกลุ่ม ถ้ามี
   
   ![](media/sql-server-analysis-services-tabular-data/connecttoas_getdatabutton.png)
2. เลือก**ฐานข้อมูลและอื่นๆ อีกมากมาย**
   
   ![](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_1.png)
3. เลือก **SQL Server Analysis Services** > **เชื่อมต่อ** 
   
   ![](media/sql-server-analysis-services-tabular-data/connecttoas_getdata_2.png)
4. เลือกเซิร์ฟเวอร์ ถ้าคุณไม่เห็นเซิร์ฟเวอร์ใดเลยในนี้ แสดงว่ายังไม่ได้กำหนดเกตเวย์และแหล่งข้อมูล หรือบัญชีของคุณไม่ได้อยู่ในรายการในแท็บ**ผู้ใช้**ของแหล่งข้อมูลในเกตเวย์ ตรวจสอบกับผู้ดูแลของคุณ
5. เลือกรูปแบบที่คุณต้องการเชื่อมต่อ ซึ่งอาจเป็นแบบตาราง หรือแบบหลายมิติ

หลังจากคุณเชื่อมต่อกับรูปแบบแล้ว จะปรากฏในไซต์ Power BI ของคุณใน**พื้นที่ทำงาน/ชุดข้อมูลของฉัน** ถ้าคุณสลับไปยังพื้นที่ทำงานกลุ่ม ชุดข้อมูลจะปรากฏขึ้นภายในกลุ่ม

![](media/sql-server-analysis-services-tabular-data/connecttoas_dataset_5.png)

## <a name="dashboard-tiles"></a>ไทล์แดชบอร์ด
ถ้าคุณปักหมุดวิชวลจากรายงานไปยังแดชบอร์ด ไทล์ที่ปักหมุดไว้จะรีเฟรชทุก 10 นาทีโดยอัตโนมัติ ถ้ามีการอัปเดตข้อมูลในเซิร์ฟเวอร์ Analysis Services ภายในองค์กรของคุณ ไทล์จะได้รับการปรับปรุงอัตโนมัติหลังผ่านไป 10 นาที

## <a name="common-issues"></a>ปัญหาที่พบบ่อย

* ข้อผิดพลาด ไม่สามารถโหลดเค้าร่างแบบจำลอง - ข้อผิดพลาดนี้เกิดขึ้นเมื่อผู้ใช้เชื่อมต่อกับ SSAS ไม่ได้รับอนุญาตให้เข้าถึงฐานข้อมูล SSAS, คิวบ์ และแบบจำลอง

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เกตเวย์ข้อมูลภายในองค์กร](service-gateway-onprem.md)  
[จัดการแหล่งข้อมูล Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[การแก้ไขปัญหาเกตเวย์ข้อมูลภายในองค์กร](service-gateway-onprem-tshoot.md)  
มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)
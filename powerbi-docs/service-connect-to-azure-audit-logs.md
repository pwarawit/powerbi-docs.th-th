---
title: เชื่อมต่อกับ Azure Audit Logs ด้วย Power BI
description: บันทึกการตรวจสอบ Azure สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/06/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 903f2a345ba4d87cb217ececa459a3cca14d72fa
ms.sourcegitcommit: e8d924ca25e060f2e1bc753e8e762b88066a0344
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/29/2018
ms.locfileid: "37134650"
---
# <a name="connect-to-azure-audit-logs-with-power-bi"></a>เชื่อมต่อกับ Azure Audit Logs ด้วย Power BI
ด้วยชุดเนื้อหาของบันทึกการตรวจสอบ Azure คุณสามารถวิเคราะห์และแสดงผลข้อมูลที่จัดเก็บไว้ในบันทึกการตรวจสอบได้ Power BI ดึงข้อมูลของคุณ สร้างแดชบอร์ดที่ใช้งานทันที และสร้างรายงานที่ยึดตามข้อมูลนั้น

เชื่อมต่อไปยัง[ชุดเนื้อหา Azure Audit Logs](https://app.powerbi.com/getdata/services/azure-audit-logs)หรืออ่านเพิ่มเติมเกี่ยวกับการ[รวม Azure Audit Logs](https://powerbi.microsoft.com/integrations/azure-audit-logs)กับ Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ  
   
    ![](media/service-connect-to-azure-audit-logs/getdata.png)
2. ในกล่อง**บริการ** เลือก**รับ**  
   
    ![](media/service-connect-to-azure-audit-logs/services.png) 
3. เลือก**Azure Audit Logs** > **รับ**  
   
   ![](media/service-connect-to-azure-audit-logs/azureauditlogs.png)
4. เมื่อได้รับข้อความปรากฏ ให้ใส่ **ID การสมัครใช้งาน Azure** ของคุณ ดูรายละเอียดในการค้นหา[ID การสมัครใช้งาน](#FindingParams)ของคุณที่ด้านล่าง   
   
    ![](media/service-connect-to-azure-audit-logs/parameters.png)
5. สำหรับ **วิธีการรับรองความถูกต้อง** ให้เลือก **oAuth2** \> **ลงชื่อเข้าใช้**
   
    ![](media/service-connect-to-azure-audit-logs/creds.png)
6. ใส่ข้อมูลประจำตัวของบัญชีผู้ใช้เพื่อเสร็จสิ้นกระบวนการลงชื่อเข้าใช้
   
    ![](media/service-connect-to-azure-audit-logs/login.png)
7. Power BI จะดึงข้อมูลบันทึกการตรวจสอบ Azure ของคุณและสร้างแดชบอร์ดและรายงานแบบพร้อมใช้งานขึ้น 
   
    ![](media/service-connect-to-azure-audit-logs/dashboard.png)

**ฉันต้องทำอะไรต่อ?**

* ลอง[ถามคำถามในกล่อง Q&A](power-bi-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานด้านใน
* ถึงแม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรซรายวัน คุณสามารถเปลี่ยนแปลงกำหนดเวลารีเฟรช หรือลองรีเฟรชตามความต้องการ โดยใช้**รีเฟรชทันที**

## <a name="system-requirements"></a>ข้อกำหนดของระบบ
ชุดเนื้อหาในบันทึกการตรวจสอบ Azure จำเป็นต้องมีการเข้าถึงบันทึกการตรวจสอบในพอร์ทัล Azure รายละเอียดเพิ่มเติม[ที่นี่](https://azure.microsoft.com/documentation/articles/insights-debugging-with-events/)

<a name="FindingParams"></a>

## <a name="finding-parameters"></a>การค้นหาพารามิเตอร์
มีสองวิธีที่ง่ายในการค้นหา ID การสมัครใช้งานของคุณ

1. จาก https://portal.azure.com -&gt;เรียกดู -&gt; การสมัคร -&gt; รหัสการสมัครใช้งาน
2. จาก https://manage.windowsazure.com -&gt;การตั้งค่า -&gt; รหัสการสมัครใช้งาน

ID การสมัครใช้งานของคุณจะเป็นชุดของตัวเลขและตัวอักษร คล้ายกับตัวอย่างในขั้นตอนที่\#4 ข้างต้น 

## <a name="troubleshooting"></a>การแก้ไขปัญหา
ถ้าคุณเห็นข้อผิดพลาดข้อมูลประจำตัวหรือมีข้อผิดพลาดในการพยายามรีเฟรชเนื่องจากข้อมูลประจำตัวไม่ถูกต้อง โปรดลองลบตัวอย่างทั้งหมดของชุดเนื้อหาบันทึกการตรวจสอบ Azure และเชื่อมต่ออีกครั้ง

## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI คืออะไร](power-bi-overview.md)  
[Power BI แนวคิดพื้นฐาน](service-basic-concepts.md)  


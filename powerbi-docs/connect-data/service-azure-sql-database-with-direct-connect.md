---
title: Azure SQL Database พร้อม DirectQuery
description: Azure SQL Database พร้อม DirectQuery
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.custom: ''
ms.date: 04/28/2020
LocalizationGroup: Data from databases
ms.openlocfilehash: aa1ae57d928633ce61ab66a8e0e905118c3a7877
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83302172"
---
# <a name="azure-sql-database-with-directquery"></a>Azure SQL Database พร้อม DirectQuery

เรียนรู้วิธีการเชื่อมต่อโดยตรงไปยังฐานข้อมูล SQL Azure และสร้างรายงานที่ใช้ข้อมูลสด คุณสามารถเก็บข้อมูลของคุณที่แหล่งข้อมูลได้ แต่ไม่ใช่ใน Power BI

ด้วย DirectQuery แบบสอบถามจะถูกส่งกลับไปยังฐานข้อมูล SQL Azure ของคุณตามที่คุณสำรวจข้อมูลในมุมมองรายงาน ประสบการณ์การใช้งานนี้แนะนำสำหรับผู้ใช้ที่คุ้นเคยกับฐานข้อมูลและเอนทิตีที่ผู้ใช้งานดังกล่าวเชื่อมต่อด้วย

**หมายเหตุ:**

* ระบุชื่อเซิร์ฟเวอร์ที่มีคุณสมบัติครบถ้วนเมื่อเชื่อมต่อ (ดูด้านล่างสำหรับรายละเอียดเพิ่มเติม)
* ตรวจสอบให้แน่ใจว่ามีการกำหนดค่ากฎไฟร์วอลล์สำหรับฐานข้อมูลเพื่อ "[อนุญาตการเข้าถึงบริการ Azure](https://docs.microsoft.com/azure/sql-database/sql-database-networkaccess-overview#allow-azure-services)"
* ทุกการดำเนินการ เช่น การเลือกคอลัมน์หรือการเพิ่มตัวกรอง จะส่งการสอบถามย้อนกลับไปยังฐานข้อมูล
* ไทล์จะรีเฟรชทุกชั่วโมง (รีเฟรชไม่จำเป็นต้องมีการจัดกำหนดการ) คุณสามารถปรับความถี่การรีเฟรชในส่วนการตั้งค่าขั้นสูงเมื่อทำการเชื่อมต่อ
* การถามตอบไม่พร้อมใช้งานสำหรับชุดข้อมูล DirectQuery
* การเปลี่ยนแปลงเค้าร่างจะไม่ถูกเลือกโดยอัตโนมัติ

ข้อจำกัดและบันทึกย่อเหล่านี้อาจเปลี่ยนแปลงขณะที่เราปรับปรุงประสบการณ์การใช้งานขึ้นเรื่อย ๆ ขั้นตอนในการเชื่อมต่อจะมีรายละเอียดดังด้านล่าง

> [!Important]
> เรากำลังปรับปรุงการเชื่อมต่อของเรากับฐานข้อมูล SQL ของ Azure  ใช้ Power BI Desktop เชื่อมต่อกับแหล่งฐานข้อมูล SQL ของ Azure  เมื่อคุณได้สร้างรูปแบบข้อมูลและรายงานของคุณแล้ว คุณสามารถเผยแพร่สิ่งดังกล่าวไปยังบริการ Power BI  ตัวเชื่อมต่อโดยตรงกับฐานข้อมูล SQL ของ Azure ในบริการ Power BI ในขณะนี้ไม่ได้รับการสนับสนุน

## <a name="power-bi-desktop-and-directquery"></a>ใช้ DirectQuery ใน Power BI Desktop

เมื่อต้องการเชื่อมต่อกับฐานข้อมูล SQL Azure ที่ใช้ DirectQuery คุณจะต้องใช้ Power BI Desktop แนวทางนี้เพิ่มความยืดหยุ่นและขีดความสามารถให้มากขึ้น รายงานที่สร้างขึ้นโดยใช้ Power BI Desktop จะสามารถเผยแพร่ไปยังบริการ Power BI ได้ คุณสามารถเรียนรู้เพิ่มเติมเกี่ยวกับวิธีการเชื่อมต่อ[ฐานข้อมูล SQL Azure ที่ใช้ DirectQuery](desktop-use-directquery.md)ภายใน Power BI Desktop ได้

## <a name="find-parameter-values"></a>ค้นหาค่าพารามิเตอร์ต่างๆ

คุณสามารถค้นหาชื่อเซิร์ฟเวอร์และชื่อฐานข้อมูลแบบเต็มได้ในพอร์ทัล Azure

![การอัปเดตพอร์ทัล Azure ใหม่](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![การอัปเดตพอร์ทัล Azure](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

[!INCLUDE [direct-query-sso](../includes/direct-query-sso.md)]

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [ใช้ DirectQuery ใน Power BI Desktop](desktop-use-directquery.md)  
* [Power BI คืออะไร](../fundamentals/power-bi-overview.md)  
* [รับข้อมูลสำหรับ Power BI](service-get-data.md)  

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)

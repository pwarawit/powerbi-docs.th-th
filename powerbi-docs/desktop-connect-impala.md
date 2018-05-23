---
title: เชื่อมต่อกับฐานข้อมูล Impala ใน Power BI Desktop
description: เชื่อมต่อและใช้ฐานข้อมูล Impala ใน Power BI Desktop ได้อย่างง่ายดาย
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 04/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: bef087b485573ba9a629887bfb05d875c88c8b4c
ms.sourcegitcommit: 3f2f254f6e8d18137bae879ddea0784e56b66895
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/26/2018
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>เชื่อมต่อกับฐานข้อมูล Impala ใน Power BI Desktop
ใน Power BI Desktop คุณสามารถเชื่อมต่อกับฐานข้อมูล **Impala** และใช้ข้อมูลเบื้องต้นเช่นเดียวกับแหล่งข้อมูลอื่นใน Power BI Desktop ได้

## <a name="connect-to-an-impala-database"></a>เชื่อมต่อกับฐานข้อมูล Impala
ในการเชื่อมต่อกับฐานข้อมูล **Impala** เลือก**รับข้อมูล**จาก Ribbon **หน้าแรก** ใน Power BI Desktop เลือก**ฐานข้อมูล**จากประเภททางด้านซ้าย จากนั้นคุณจะเห็น **Impala**

![](media/desktop-connect-impala/connect_impala_2.png)

ในหน้าต่าง **Impala** ที่ปรากฏขึ้น ให้พิมพ์หรือวางชื่อเซิร์ฟเวอร์ Impala ลงในกล่องแล้วเลือก**ตกลง** โปรดทราบว่าคุณสามารถเลือก**นำเข้า**ข้อมูลได้โดยตรงใน Power BI หรือจะใช้ **DirectQuery** ก็ได้ เรียนรู้เพิ่มเติมเกี่ยวกับ[การใช้ DirectQuery](desktop-use-directquery.md)

![](media/desktop-connect-impala/connect_impala_3a.png)

เมื่อข้อความปรากฏขึ้น ให้ใส่ชื่อผู้ใช้และรหัสผ่านของคุณ หรือเชื่อมต่อแบบไม่ระบุชื่อ อย่างใดอย่างหนึ่งที่ระบบสนับสนุน

![](media/desktop-connect-impala/connect_impala_4.png)

> [!NOTE]
> เมื่อคุณใส่ชื่อผู้ใช้และรหัสผ่านสำหรับเซิร์ฟเวอร์ **Impala** ที่เฉพาะเจาะจงแล้ว Power BI Desktop จะใช้ข้อมูลประจำตัวเดียวกันนั้นเพื่อพยายามเชื่อมต่ออีกครั้ง คุณสามารถปรับเปลี่ยนข้อมูลประจำตัวเหล่านั้นได้โดยไปที่ **ไฟล์ > ตัวเลือกและการตั้งค่า > การตั้งค่าแหล่งข้อมูล**
> 
> 

เมื่อเชื่อมต่อเสร็จเรียบร้อยแล้ว หน้าต่าง**ตัวนำทาง**จะปรากฏขึ้น และแสดงข้อมูลที่พร้อมใช้งานบนเซิร์ฟเวอร์ ซึ่งคุณสามารถเลือกองค์ประกอบหนึ่งรายการหรือหลายรายการเพื่อนำเข้าและใช้ใน**Power BI Desktop** ได้

![](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด
มีบางข้อจำกัดและข้อควรพิจารณาที่ควรระลึกถึงสำหรับตัวเชื่อมต่อ**Impala**:

* แผนในอนาคตจะรวมถึงการเปิดใช้งานการรีเฟรชการสนับสนุนโดยใช้**Power BI Gateway**

## <a name="next-steps"></a>ขั้นตอนถัดไป
มีข้อมูลหลากหลายประเภทที่คุณสามารถเชื่อมต่อโดยใช้ Power BI Desktop สำหรับข้อมูลเพิ่มเติมเกี่ยวกับแหล่งข้อมูล โปรดดูทรัพยากรต่อไปนี้:

* [เริ่มต้นใช้งาน Power BI Desktop](desktop-getting-started.md)
* [แหล่งข้อมูลใน Power BI Desktop](desktop-data-sources.md)
* [จัดรูปร่างและรวมข้อมูลด้วย Power BI Desktop](desktop-shape-and-combine-data.md)
* [เชื่อมต่อกับสมุดงาน Excel ใน Power BI Desktop](desktop-connect-excel.md)   
* [ใส่ข้อมูลลงใน Power BI Desktop โดยตรง](desktop-enter-data-directly-into-desktop.md)   


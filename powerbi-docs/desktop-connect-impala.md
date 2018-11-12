---
title: เชื่อมต่อกับฐานข้อมูล Impala ใน Power BI Desktop
description: เชื่อมต่อและใช้ฐานข้อมูล Impala ใน Power BI Desktop ได้อย่างง่ายดาย
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1b512a3e6ef3ead8d93e1b554fbab3aaed8a2a5a
ms.sourcegitcommit: b343e44dbafc0b718c564402593d4b6e3a8ce97c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/06/2018
ms.locfileid: "51027402"
---
# <a name="connect-to-an-impala-database-in-power-bi-desktop"></a>เชื่อมต่อกับฐานข้อมูล Impala ใน Power BI Desktop
ใน Power BI Desktop คุณสามารถเชื่อมต่อกับฐานข้อมูล **Impala** และใช้ข้อมูลเบื้องต้นเช่นเดียวกับแหล่งข้อมูลอื่นใน Power BI Desktop ได้

## <a name="connect-to-an-impala-database"></a>เชื่อมต่อกับฐานข้อมูล Impala
หากต้องการเชื่อมต่อกับฐานข้อมูล **Impala** ให้ปฏิบัติตามขั้นตอนต่อไปนี้: 

1. เลือก **รับข้อมูล** จาก ribbon **หน้าแรก** ใน Power BI Desktop 

2. เลือก **ฐานข้อมูล** จากหมวดหมู่ทางด้านซ้าย คุณจะเห็น **Impala**

    ![รับข้อมูล](media/desktop-connect-impala/connect_impala_2.png)

3. ในหน้าต่าง **Impala** ที่ปรากฏขึ้น ให้พิมพ์หรือวางชื่อเซิร์ฟเวอร์ Impala ลงในกล่อง จากนั้นเลือก **ตกลง** คุณสามารถเลือก **นำเข้า** ข้อมูลได้โดยตรงลงใน
 Power BI หรือจะใช้ **DirectQuery** ก็ได้ เรียนรู้เพิ่มเติมเกี่ยวกับ [การใช้ DirectQuery](desktop-use-directquery.md)

    ![หน้าต่าง Impala](media/desktop-connect-impala/connect_impala_3a.png)

4. เมื่อได้รับพร้อมท์ ใส่ข้อมูลประจำตัวของคุณ หรือเชื่อมต่อแบบไม่ระบุชื่อ ตัวเชื่อมต่อ Impala รองรับการรับรองความถูกต้องแบบไม่ระบุชื่อ, แบบพื้นฐาน (ชื่อผู้ใช้ + รหัสผ่าน) และแบบ Windows

    ![ตัวเชื่อมต่อ Impala](media/desktop-connect-impala/connect_impala_4.png)

    > [!NOTE]
    > หลังจากคุณใส่ชื่อผู้ใช้และรหัสผ่านสำหรับเซิร์ฟเวอร์ **Impala** ที่เฉพาะเจาะจงแล้ว Power BI Desktop จะใช้ข้อมูลประจำตัวเดียวกันนั้นเพื่อพยายามเชื่อมต่อในลำดับถัดมา คุณสามารถปรับเปลี่ยนข้อมูลประจำตัวเหล่านั้นได้โดยไปที่ **ไฟล์ > ตัวเลือกและการตั้งค่า > การตั้งค่าแหล่งข้อมูล**


5. หลังจากที่คุณเชื่อมต่อ หน้าต่าง **ตัวนำทาง** จะปรากฏขึ้น และแสดงข้อมูลที่พร้อมใช้งานบนเซิร์ฟเวอร์ เลือกองค์ประกอบจากข้อมูลนี้เพื่อนำเข้าและใช้ใน **Power BI Desktop**

    ![หน้าต่างตัวนำทาง](media/desktop-connect-impala/connect_impala_5.png)

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด
มีบางข้อจำกัดและข้อควรพิจารณาที่ควรระลึกถึงสำหรับตัวเชื่อมต่อ**Impala**:

* เกตเวย์ข้อมูลภายในองค์กรรองรับตัวเชื่อมต่อ Impala โดยใช้กลไกการรับรองความถูกต้องที่รองรับสามแบบ

## <a name="next-steps"></a>ขั้นตอนถัดไป
มีแหล่งข้อมูลต่าง ๆ มากมายที่คุณสามารถเชื่อมต่อโดยการใช้ Power BI Desktop สำหรับข้อมูลเพิ่มเติมเกี่ยวกับแหล่งข้อมูล โปรดดูทรัพยากรต่อไปนี้:

* [Power BI Desktop คืออะไร](desktop-what-is-desktop.md)
* [แหล่งข้อมูลใน Power BI Desktop](desktop-data-sources.md)
* [จัดรูปร่างและรวมข้อมูลด้วย Power BI Desktop](desktop-shape-and-combine-data.md)
* [เชื่อมต่อกับเวิร์กบุ๊ก Excel ใน Power BI Desktop](desktop-connect-excel.md)   
* [ป้อนข้อมูลลงใน Power BI Desktop โดยตรง](desktop-enter-data-directly-into-desktop.md)   


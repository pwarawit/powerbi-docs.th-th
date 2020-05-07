---
title: ปิดใช้งานการรีเฟรชพื้นหลังของ Power Query
description: คำแนะนำเมื่อปิดใช้งานการรีเฟรชพื้นหลังของ Power Query
author: peter-myers
manager: asaxton
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/26/2019
ms.author: v-pemyer
ms.openlocfilehash: 59cb62a9186da03a265fc3a8711d7275c3772af3
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "75623072"
---
# <a name="disable-power-query-background-refresh"></a>ปิดใช้งานการรีเฟรชพื้นหลังของ Power Query

บทความนี้มุ่งเป้าหมายไปที่เรื่อง ตัวสร้างแบบจำลองข้อมูลนำเข้าที่ทำงานกับ Power BI Desktop

ตามค่าเริ่มต้นเมื่อ Power Query นำเข้าข้อมูลจะยังเก็บแถวของข้อมูลตัวอย่างถึง 1000 แถวสำหรับแต่ละคิวรี ข้อมูลตัวอย่างจะช่วยแสดงตัวอย่างด่วนของข้อมูลต้นฉบับ และผลลัพธ์การแปลงสำหรับแต่ละขั้นตอนของแบบสอบถามของคุณ ซึ่งจะถูกเก็บแยกบนแผ่นดิสก์หรือไฟล์ภายในของ Power BI Desktop

อย่างไรก็ตามเมื่อไฟล์ Power BI Desktop ของคุณมีแบบสอบถามจำนวนมาก การดึงและจัดเก็บข้อมูลการแสดงตัวอย่างสามารถขยายเวลาที่ใช้เพื่อทำการรีเฟรชให้เสร็จสมบูรณ์

## <a name="recommendation"></a>คำแนะนำ

คุณจะได้รับการรีเฟรชได้รวดเร็วยิ่งขึ้นโดยการตั้งค่าไฟล์ Power BI Desktop เพื่ออัปเด การแสดงตัวอย่างของแคช_ในพื้นหลัง_ ใน Power BI Desktop คุณเปิดใช้งานโดยการเลือก _ไฟล์ > ตัวเลือกและการตั้งค่า > ตัวเลือก_จากนั้นเลือกหน้า_โหลดข้อมูล_ คุณสามารถเปิดตัวเลือก**การอนุญาตให้ดาวน์โหลดภาพแสดงตัวอย่างข้อมูลในพื้นหลัง** โปรดทราบว่าตัวเลือกนี้สามารถกำหนดสำหรับไฟล์ปัจจุบันได้

![ตัวเลือกข้อมูลพื้นหลังของ Power BI Desktop](media/power-query-background-refresh/power-query-options-background-data.png)

การเปิดใช้งานการรีเฟรชพื้นหลังสามารถทำให้ข้อมูลแสดงตัวอย่างหมดอายุแล้ว ถ้าเกิดขึ้น ตัวแก้ไข Power Query จะแจ้งให้คุณทราบด้วยคำเตือนต่อไปนี้:

![ตัวแก้ไข Power Query จะแจ้งเกี่ยวกับข้อมูลตัวอย่างเดิม](media/power-query-background-refresh/power-query-preview-data-old.png)

สามารถอัปเดตแคชตัวอย่างได้ คุณสามารถอัปเดตสำหรับคิวรีเดียว หรือคิวรีทั้งหมดโดยใช้คำสั่ง **รีเฟรชตัวอย่าง** คุณจะพบที่ริบบิ้น **หน้าหลัก** ของหน้าต่างตัวแก้ไข Power Query

![ตัวแก้ไข Power Query สั่งให้รีเฟรชข้อมูลตัวอย่าง](media/power-query-background-refresh/power-query-refresh-preview-data.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป

สำหรับข้อมูลเพิ่มเติมที่เกี่ยวข้องกับบทความนี้ โปรดดูทรัพยากรต่อไปนี้:

- [เอกสาร Power Query](/power-query/)
- มีคำถามหรือไม่? [ลองถามชุมชน Power BI](https://community.powerbi.com/)

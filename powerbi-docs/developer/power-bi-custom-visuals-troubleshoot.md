---
title: การแก้ปัญหาวิธีพัฒนา Power BI ส่วนการแสดงผล Power BI
description: บทความนี้อธิบายถึงปัญหาทั่วไปที่คุณอาจพบเมื่อพัฒนาหรือสร้าง Power BI แบบกำหนดเอง
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: troubleshooting
ms.subservice: powerbi-custom-visuals
ms.date: 11/06/2018
ms.openlocfilehash: e28df5035e057d485a8122853f6ae88327e3045f
ms.sourcegitcommit: 01de0b01f66f28ca45b8d309d7864f261d6c9a85
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/16/2019
ms.locfileid: "74127765"
---
# <a name="troubleshoot-power-bi-power-bi-visuals"></a>แก้ไขปัญหา Power BI ส่วนการแสดงผล Power BI

## <a name="debug"></a>ข้อบกพร่อง

**ไม่พบคำสั่ง Pbiviz (หรือข้อผิดพลาดที่คล้ายกัน)**

เมื่อคุณเรียกใช้ `pbiviz` ในบรรทัดคำสั่งของเทอร์มินัล คุณควรเห็นหน้าจอความช่วยเหลือ ถ้าไม่มี แสดงว่าคำสั่งนั้นไม่ได้ถูกติดตั้งอย่างถูกต้อง ตรวจสอบให้แน่ใจว่า คุณติดตั้ง NodeJS เวอร์ชันขั้นต่ำ 4.0

**ไม่พบวิชวลดีบักในแท็บการแสดงภาพ**

ดีบักวิชวล มีลักษณะเหมือนไอคอนรูปพร้อมท์ภายในแท็บ**แสดงภาพ**

![การเลือกวิชวล](media/power-bi-custom-visuals-troubleshoot/powerbi-developer-visual-selection.png)

ถ้าคุณไม่เห็นไอคอนนั้น ตรวจสอบให้แน่ใจว่าคุณได้เปิดใช้งานภายในการตั้งค่า Power BI

> [!NOTE]
> ดีบักวิชวล ในขณะใช้งานได้เฉพาะ ในบริการของ Power BI และยังไม่รองรับโดย Power BI Desktop หรือแอปสำหรับอุปกรณ์เคลื่อนที่ วิชวลที่แพคเกจแล้วจะยังคงทำงานได้ทุก ๆ ที่

**ไม่สามารถติดต่อเซิร์ฟเวอร์วิชวล**

เรียกใช้เซิร์ฟเวอร์วิชวลด้วยคำสั่ง `pbiviz start` ในบรรทัดคำสั่งของเทอร์มินัล จากรากของโครงการวิชวลของคุณ ถ้าเซิร์ฟเวอร์ไม่ทำงาน เป็นไปได้ว่าไม่ได้ติดตั้งใบรับรอง SSL ของคุณอย่างถูกต้อง

สามารถติดต่อทีมให้บริการส่วนการแสดงผล Power BI ได้: *pbicvsupport@microsoft.com*  เพื่อสอบถามข้อสงสัย แสดงความเห็นหรือแจ้งประเด็นใด ๆ ที่คุณมี

## <a name="next-steps"></a>ขั้นตอนถัดไป

สำหรับข้อมูลเพิ่มเติม โปรดเยี่ยมชม[คำถามที่ถามบ่อยเกี่ยวกับ Power BI ส่วนการแสดงผล Power BI](power-bi-custom-visuals-faq.md#organizational-visuals)
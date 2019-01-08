---
title: การแก้ปัญหาวิธีพัฒนาวิชวลแบบกำหนดเองของ Power BI
description: บทความนี้อธิบายถึงปัญหาทั่วไปที่คุณอาจพบเมื่อพัฒนาหรือสร้าง Power BI แบบกำหนดเอง
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 11/06/2018
ms.openlocfilehash: 264794346a046ceb85c67f77d2fe6d80556d342d
ms.sourcegitcommit: 88ae40a25ea54ef7153885dd04ef57d12522d4e1
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/04/2019
ms.locfileid: "54056006"
---
# <a name="troubleshoot-power-bi-custom-visuals"></a>แก้ปัญหาการแสดงภาพ Power BI แบบกำหนดเอง

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

อย่าลังเลที่จะติดต่อทีมดูแลวิชวลแบบกำหนดเอง: *pbicvsupport@microsoft.com* กับคำถาม ความคิดเห็น หรือปัญหาที่คุณมี

## <a name="next-steps"></a>ขั้นตอนถัดไป

สำหรับข้อมูลเพิ่มเติม โปรดเยี่ยมชม[คำถามที่ถามบ่อยเกี่ยวกับวิชวลแบบกำหนดเองของ Power BI](power-bi-custom-visuals-faq.md#organizational-custom-visuals)

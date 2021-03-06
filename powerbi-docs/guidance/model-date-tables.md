---
title: สร้างตารางวันที่ใน Power BI Desktop
description: เทคนิคและคำแนะนำสำหรับการสร้างตารางวันที่ใน Power BI Desktop
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2020
ms.author: v-pemyer
ms.openlocfilehash: ad85ad56db907ca19af7dc14681eb34f8c2b9abc
ms.sourcegitcommit: 46a340937d9f01c6daba86a4ab178743858722ec
ms.contentlocale: th-TH
ms.lasthandoff: 06/26/2020
ms.locfileid: "85398341"
---
# <a name="create-date-tables-in-power-bi-desktop"></a>สร้างตารางวันที่ใน Power BI Desktop

บทความนี้มุ่งเป้าหมายไปที่เรื่อง ตัวสร้างแบบจำลองข้อมูลนำเข้าที่ทำงานกับ Power BI Desktop มีการอธิบายแนวทางปฏิบัติในการออกแบบที่ดีสำหรับการสร้างตารางวันที่ในรูปแบบข้อมูลของคุณ

เมื่อต้องการทำงานกับนิพจน์การวิเคราะห์ข้อมูล (DAX) [ฟังก์ชันตัวแสดงเวลา](/dax/time-intelligence-functions-dax)มีข้อกำหนดของแบบจำลองล่วงหน้า: คุณต้องมีอย่างน้อยหนึ่ง _ตารางวันที่_ ในแบบจำลองของคุณ ตารางวันที่เป็นตารางที่ตรงกับความต้องการต่อไปนี้:

> [!div class="checklist"]
> - การดำเนินการนี้จะต้องมีคอลัมน์ชนิดข้อมูล **วันที่** (หรือ **วันที่/เวลา**) ซึ่งเป็นที่รู้จักกันในชื่อ _คอลัมน์วันที่_
> - คอลัมน์วันที่ต้องมีค่าไม่ซ้ำกัน
> - คอลัมน์วันที่ต้องไม่มีช่องว่าง
> - คอลัมน์วันที่ต้องไม่มีวันที่หายไป
> - คอลัมน์วันที่ต้องครอบคลุมปีเต็ม ปีไม่จำเป็นต้องเป็นปีปฏิทิน (มกราคม - ธันวาคม)
> - ตารางวันที่ต้องได้รับ [การทำเครื่องหมายเป็นตารางวันที่](../transform-model/desktop-date-tables.md#setting-your-own-date-table)

คุณสามารถใช้เทคนิคหลายอย่างในการเพิ่มตารางวันที่ไปยังแบบจำลองของคุณ:

- ตัวเลือกวันที่/เวลาอัตโนมัติ
- Power Query เพื่อเชื่อมต่อกับตารางมิติวันที่
- Power Query เพื่อสร้างตารางวันที่
- DAX เพื่อสร้างตารางวันที่
- DAX เพื่อโคลนตารางวันที่ที่มีอยู่

> [!TIP]
> ตารางวันที่อาจเป็นคุณลักษณะที่สอดคล้องกันมากที่สุดที่คุณจะเพิ่มลงในแบบจำลองของคุณ มีอะไรเพิ่มเติม ภายในองค์กรที่ตารางวันที่ควรได้รับการกำหนดอย่างสม่ำเสมอ ดังนั้นเทคนิคที่คุณตัดสินใจที่จะใช้ เราขอแนะนำให้คุณสร้าง [เทมเพลต Power BI Desktop](../create-reports/desktop-templates.md) ที่มีตารางวันที่กำหนดค่าแบบเต็ม แชร์เทมเพลตกับผู้สร้างโมเดลทั้งหมดในองค์กรของคุณ ดังนั้นเมื่อใดก็ตามที่มีคนพัฒนาโมเดลใหม่พวกเขาสามารถเริ่มต้นด้วยตารางวันที่ที่กำหนดอย่างสม่ำเสมอ

## <a name="use-auto-datetime"></a>ใช้วันที่/เวลาอัตโนมัติ

ตัวเลือก [วันที่/เวลาแบบอัตโนมัต](../transform-model/desktop-auto-date-time.md) ให้ความสะดวกรวดเร็วและสามารถปรับแต่งตัวแสดงเวลาได้ง่าย ผู้เขียนรายงานสามารถใช้งานตัวปรับแต่งการแสดงเวลาได้ง่ายเมื่อมีการกรอง การจัดกลุ่มและการเจาะลึกลงไปตามช่วงเวลาของปฏิทิน

เราขอแนะนำให้คุณเก็บตัวเลือกวันที่/ เวลาอัตโนมัติที่เปิดใช้งานเฉพาะเมื่อคุณใช้งานช่วงเวลาของปฏิทินและเมื่อคุณมีข้อกำหนดแบบจำลองที่เรียบง่ายในความสัมพันธ์กับเวลา การใช้ตัวเลือกนี้ยังสามารถทำได้อย่างสะดวกสบายเมื่อสร้างแบบจำลองเฉพาะกิจ การดำเนินการสำรวจข้อมูลหรือการสร้างโพรไฟล์ อย่างไรก็ตามวิธีการนี้ไม่รองรับการออกแบบตารางวันที่เดียวที่สามารถเผยแพร่ตัวกรองไปยังหลายตารางได้ สำหรับข้อมูลเพิ่มเติมดู [คำแนะนำวันที่/เวลาอัตโนมัติใน Power BI Desktop](auto-date-time.md)

## <a name="connect-with-power-query"></a>เชื่อมต่อกับ Power Query

เมื่อแหล่งข้อมูลของคุณมีตารางวันที่แล้วเราขอแนะนำให้คุณใช้เป็นแหล่งข้อมูลของตารางวันที่แบบจำลองของคุณ โดยทั่วไปแล้วจะเป็นกรณีที่คุณกำลังเชื่อมต่อไปยังคลังข้อมูล เนื่องจากจะมีตารางมิติวันที่ ด้วยวิธีนี้แบบจำลองของคุณใช้เป็นแหล่งข้อมูลของความจริงเดียวสำหรับเวลาในองค์กรของคุณ

ถ้าคุณกำลังพัฒนาแบบจำลอง DirectQuery และแหล่งข้อมูลของคุณไม่มีตารางวันที่ เราขอแนะนำให้คุณเพิ่มตารางวันที่ไปยังแหล่งข้อมูล ซึ่งควรเป็นไปตามข้อกำหนดในการสร้างแบบจำลองทั้งหมดของตารางวันที่ จากนั้นคุณสามารถใช้ Power Query เพื่อเชื่อมต่อกับตารางวันที่ ด้วยวิธีนี้การคำนวณแบบจำลองของคุณสามารถใช้ประโยชน์จากความสามารถในตัวแสดงเวลา DAX ได้

## <a name="generate-with-power-query"></a>สร้างด้วย Power Query

คุณสามารถสร้างตารางวันที่โดยใช้ Power Query ต่อไปนี้คือสองรายการบล็อกที่แสดงวิธีการ:

- [การสร้างมิติวันที่ด้วยสคริปต์ Power Query](https://www.mattmasson.com/2014/02/creating-a-date-dimension-with-a-power-query-script/) โดย Matt Masson
- [สร้างตารางมิติวันที่ใน Power Query](https://blog.crossjoin.co.uk/2013/11/19/generating-a-date-dimension-table-in-power-query/) โดย Chris Webb

> [!TIP]
> ถ้าคุณไม่มีคลังข้อมูลหรือข้อกำหนดอื่นๆ ที่สอดคล้องกันสำหรับเวลาในองค์กรของคุณ ให้พิจารณาใช้ Power Query เพื่อเผยแพร่[กระแสข้อมูล](../transform-model/service-dataflows-overview.md) จากนั้นให้ผู้สร้างแบบจำลองข้อมูลทั้งหมดเชื่อมต่อกับกระแสข้อมูล เพื่อเพิ่มตารางวันที่ลงในแบบจำลองของพวกเขา กระแสข้อมูล จะกลายเป็นแหล่งเดียวของความจริงสำหรับเวลาในองค์กรของคุณ

ถ้าคุณต้องการสร้างตารางวันที่ให้ลองทำด้วย DAX คุณอาจพบว่ามันง่ายขึ้น มีอะไรเพิ่มเติมซึ่งมีแนวโน้มที่จะสะดวกมากขึ้น เนื่องจาก DAX มีความสามารถในการสร้างและการจัดการตารางวันที่ได้อย่างง่ายดาย

## <a name="generate-with-dax"></a>สร้างด้วย DAX

คุณสามารถสร้างตารางวันที่ในแบบจำลองของคุณโดยการสร้างตารางที่มีการคำนวณโดยใช้ [ปฏิทิน](/dax/calendar-function-dax) หรือ [CALENDARAUTO](/dax/calendarauto-function-dax)ฟังก์ชัน DAX แต่ละฟังก์ชันจะส่งกลับตารางแบบคอลัมน์เดียวของวันที่ จากนั้นคุณสามารถขยายตารางที่มีการคำนวณด้วยคอลัมน์จากการคำนวณเพื่อรองรับการกรองช่วงวันที่และข้อกำหนดของการจัดกลุ่ม

- ใช้ฟังก์ชัน **ปฏิทิน** เมื่อคุณต้องการกำหนดช่วงวันที่ คุณส่งผ่านสองค่า: วันที่เริ่มต้นและวันสิ้นสุด ค่าเหล่านี้สามารถถูกกำหนดโดยฟังก์ชัน DAX อื่นๆเช่น `MIN(Sales[OrderDate])` หรือ `MAX(Sales[OrderDate])`
- ใช้ฟังก์ชัน **CALENDARAUTO** เมื่อคุณต้องการให้ช่วงวันที่ครอบคลุมวันที่ทั้งหมดที่จัดเก็บไว้ในแบบจำลองโดยอัตโนมัติ คุณสามารถส่งผ่านพารามิเตอร์ตัวเลือกเดียวที่เป็นเดือนสิ้นสุดของปี (ถ้าปีของคุณเป็นปีปฏิทินซึ่งลงท้ายด้วยเดือนธันวาคมคุณไม่จำเป็นต้องส่งค่า) มันเป็นฟังก์ชั่นที่มีประโยชน์เพราะช่วยให้มั่นใจได้ว่าจะส่งคืนวันที่เต็มปีซึ่งเป็นข้อกำหนดสำหรับตารางวันที่ที่ทำเครื่องหมายไว้ ยิ่งไปกว่านั้นคุณไม่จำเป็นต้องจัดการการขยายตารางไปยังปีในอนาคต: เมื่อการรีเฟรชข้อมูลเสร็จสมบูรณ์จะทริกเกอร์การคำนวณใหม่ของตาราง การคำนวณใหม่จะขยายช่วงวันที่ของตารางโดยอัตโนมัติเมื่อวันที่สำหรับปีใหม่ถูกโหลดลงในแบบจำลอง

## <a name="clone-with-dax"></a>ลอกแบบด้วย DAX

เมื่อโมเดลของคุณมีตารางวันที่และคุณต้องการมีตารางวันที่เพิ่มเติมคุณสามารถโคลนตารางวันที่ที่มีอยู่ได้อย่างง่ายดาย ซึ่งเป็นกรณีเมื่อวันที่เป็น [มิติการเล่นบทบาท](star-schema.md#role-playing-dimensions) คุณสามารถลอกแบบตารางได้โดยการสร้างตารางที่มีการคำนวณ นิพจน์ตารางที่ได้รับการคำนวณเป็นเพียงชื่อของตารางวันที่ที่มีอยู่

## <a name="next-steps"></a>ขั้นตอนถัดไป

สำหรับข้อมูลเพิ่มเติมที่เกี่ยวข้องกับบทความนี้ โปรดดูทรัพยากรต่อไปนี้:

- [วันที่/เวลาอัตโนมัติใน Power BI Desktop](../transform-model/desktop-auto-date-time.md)
- [คำแนะนำวันที่/เวลาอัตโนมัติใน Power BI Desktop](auto-date-time.md)
- [ตั้งค่า และใช้งานตารางวันที่ใน Power BI Desktop](../transform-model/desktop-date-tables.md)
- [การเตรียมข้อมูลด้วยตนเองใน Power BI](../transform-model/service-dataflows-overview.md)
- [ฟังก์ชัน CALENDAR (DAX)](/dax/calendar-function-dax)
- [ฟังก์ชัน CALENDARAUTO (DAX)](/dax/calendarauto-function-dax)
- มีคำถามหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
- มีข้อเสนอแนะไหม [สนับสนุนแนวคิดในการปรับปรุง Power BI](https://ideas.powerbi.com/)

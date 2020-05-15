---
title: รับข้อมูลจากไฟล์ Comma Separated Value (.CSV) (ใช้จุลภาคเป็นตัวคั่น)
description: เรียนรู้วิธีการรับข้อมูลจากไฟล์ CSV ลงใน Power BI
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: a33c8a45f4f32efb0a47df82b8af23d42c281ae9
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83300355"
---
# <a name="get-data-from-comma-separated-value-csv-files"></a>รับข้อมูลจากไฟล์ Comma Separated Value (.CSV) (ใช้จุลภาคเป็นตัวคั่น)
![](media/service-comma-separated-value-files/csv_icon.png)

ไฟล์ค่าที่ใช้จุลภาคเป็นตัวคั่นเป็นที่รู้จักกันในรูปแบบ .CSV ซึ่งเป็นไฟล์ข้อความอย่างง่ายที่มีแถวของข้อมูล โดยที่แต่ละค่าจะถูกคั่นด้วยเครื่องหมายจุลภาค ชนิดของไฟล์เหล่านี้อาจประกอบด้วยข้อมูลจำนวนมากภายในขนาดไฟล์ค่อนข้างเล็ก ทำให้ไฟล์เหล่านี้เป็นแหล่งข้อมูลที่เหมาะสมที่สุดสำหรับ Power BI คุณสามารถดาวน์โหลดตัวอย่างไฟล์ .CSV [ที่นี่](https://go.microsoft.com/fwlink/?LinkID=619356)

ถ้าคุณมu .CSV ถึงเวลาไปที่ไซต์ Power BI ของคุณในฐานเป็นชุดข้อมูล ซึ่งคุณสามารถเริ่มการสำรวจข้อมูล สร้างแดชบอร์ดบางรายการ และแชร์ข้อมูลเชิงลึกของคุณกับผู้อื่นได้

>[!TIP]
>องค์กรจำนวนมากส่งออกผลลัพธ์ .CSV ด้วยข้อมูลที่อัปเดตแต่ละวัน เมื่อต้องการตรวจสอบว่าชุดข้อมูลของคุณใน Power BI ยังคงรวมอยู่กับไฟล์ที่อัปเดตแล้วหรือไม่นั้น ตรวจสอบให้แน่ใจว่าไฟล์ถูกบันทึกไปยัง OneDrive ด้วยชื่อเดียวกัน

## <a name="where-your-file-is-saved-makes-a-difference"></a>ตำแหน่งที่คุณบันทึกไฟล์สร้างความแตกต่างได้
**ภายในเครื่อง** - ถ้าคุณบันทึกไฟล์ .CSV ลงในไดรฟ์ภายในเครื่องคอมพิวเตอร์ของคุณหรือในตำแหน่งอื่นในองค์กรของคุณ จาก Power BI คุณสามารถ*นำเข้า*ไฟล์ของคุณไปยัง Power BI ได้ ไฟล์ของคุณจะยังคงอยู่บนไดรฟ์ในเครื่อง ดังนั้นจึงไม่มีการนำเข้าใน Power BI จริง ๆ สิ่งที่เกิดขึ้นจริง ๆ คือมีการสร้างชุดข้อมูลใหม่ใน Power BI และข้อมูลจากไฟล์ .CSV จะโหลดลงในชุดข้อมูลดังกล่าว

**OneDrive - ธุรกิจ**– ถ้าคุณมี OneDrive for Business และคุณลงชื่อเข้าใช้ด้วยบัญชีเดียวกันกับที่คุณลงชื่อเข้าใช้ Power BI ปัจจุบัน นี่คือวิธีที่มีประสิทธิภาพที่สุดในการเก็บไฟล์ .CSV และชุดข้อมูล รายงาน และแดชบอร์ดใน Power BI ของคุณให้รวมกัน เนื่องจากทั้ง Power BI และ OneDrive อยู่ในระบบคลาวด์ Power BI จะ*เชื่อมต่อ*ไปยังไฟล์ของคุณบน OneDrive ประมาณทุกชั่วโมง ถ้าพบการเปลี่ยนแปลงใด ๆ ก็ตาม Power BI จะอัปเดต ชุดข้อมูล รายงาน และแดชบอร์โดยอัตโนมัติ

**OneDrive - ส่วนบุคคล** – ถ้าคุณบันทึกไฟล์ของคุณไปยังบัญชี OneDrive ของคุณเอง คุณจะยังได้รับประโยชน์หลายอย่างแบบเดียวกับที่คุณได้จาก OneDrive for Business ความแตกต่างที่สำคัญที่สุด คือเมื่อคุณเชื่อมต่อกับไฟล์ของคุณ (โดยใช้ รับข้อมูล > ไฟล์ > OneDrive – ส่วนบุคคล) คุณจำเป็นต้องลงชื่อเข้าใช้ OneDrive ของคุณด้วยบัญชี Microsoft ของคุณ ซึ่งโดยปกติแล้วจะแตกต่างจากที่คุณใช้ลงชื่อเข้าใช้ Power BI เมื่อลงชื่อเข้าใช้ด้วย OneDrive ของคุณด้วยบัญชี Microsoft ตรวจสอบให้แน่ใจว่าได้เลือกตัวเลือก คงการลงชื่อเข้าใช้ของฉันไว้เสมอ ด้วยวิธีนี้ Power BI จะสามารถเชื่อมต่อกับไฟล์ของคุณประมาณทุกชั่วโมง และทำให้คุณแน่ใจว่า ชุดข้อมูลของคุณใน Power BI มีข้อมูลที่ตรงกัน

**SharePoint - ของไซต์ของทีม** การบันทึกไฟล์ Power BI Desktop ของคุณไปยัง SharePoint ไซต์ของทีมจะเหมือนกับการบันทึกไปยัง OneDrive for Business มาก ความแตกต่างที่สำคัญที่สุดคือ วิธีที่คุณเชื่อมต่อไปยังไฟล์จาก Power BI คุณสามารถระบุ URL หรือเชื่อมต่อไปยังโฟลเดอร์รากฐานได้

## <a name="import-or-connect-to-a-csv-file"></a>นำเข้าหรือเชื่อมต่อกับไฟล์ .CSV
>[!IMPORTANT]
>ขนาดไฟล์สูงสุดที่คุณสามารถนำเข้าใน Power BI ได้คือ 1 กิกะไบต์

1. ใน Power BI ในพื้นที่ตัวนำทาง คลิก**รับข้อมูล**
   
   ![](media/service-comma-separated-value-files/csv_get_data_button.png)
2. ใน**ไฟล์** คลิก**รับ**
   
   ![](media/service-comma-separated-value-files/csv_files_get.png)
3. ค้นหาไฟล์ของคุณ
   
   ![](media/service-comma-separated-value-files/csv_find_your_file.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป
**สำรวจข้อมูลของคุณ** เมื่อคุณได้รับข้อมูลจากไฟล์ของคุณลงใน Power BI แล้ว นั่นก็ถึงเวลาการสำรวจ เพียงคลิกขวาที่ชุดข้อมูลใหม่ จากนั้นคลิก**สำรวจ**

**กำหนดการรีเฟรช** ถ้าไฟล์ของคุณบันทึกลงในไดรฟ์ภายในเครื่อง คุณสามารถตั้งค่ารีเฟรชตามกำหนดการได้ เพื่อให้ชุดข้อมูลและรายงานใน Power BI ของคุณเป็นเวอร์ชันล่าสุดเสมอ เมื่อต้องการเรียนรู้เพิ่มเติม ดู[รีเฟรชข้อมูลใน Power BI](refresh-data.md) ถ้าไฟล์ของคุณถูกบันทึกไปยัง OneDrive, Power BI จะรวมข้อมูลกับ OneDrive ประมาณทุกชั่วโมงโดยอัตโนมัติ

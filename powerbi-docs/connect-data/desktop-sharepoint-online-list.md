---
title: สร้างรายงานบนรายการ SharePoint
description: บทช่วยสอนนี้แสดงวิธีการแปลงข้อมูลในรายการ SharePoint ของคุณลงในรายงาน Power BI
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 01/10/2020
ms.author: davidi
LocalizationGroup: Visualizations
ms.openlocfilehash: 74dbd1207a39f44f761c5068af41db1f40acabe3
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85222672"
---
# <a name="create-a-report-on-a-sharepoint-list"></a>สร้างรายงานบนรายการ SharePoint

ทีมและองค์กรจำนวนมากใช้รายการใน SharePoint Online เพื่อจัดเก็บข้อมูลเนื่องจากง่ายต่อการตั้งค่าและทำให้ผู้ใช้สามารถอัปเดตได้อย่างง่ายดาย  บางครั้งการใช้แผนภูมิเป็นแนวทางที่ง่ายกว่ามากสำหรับผู้ใช้เพื่อทำความเข้าใจข้อมูลอย่างรวดเร็วแทนที่จะดูตัวรายการเอง ในบทช่วยสอนนี้ เราจะแสดงวิธีการแปลงข้อมูลในรายการ SharePoint ของคุณลงในรายงาน Power BI

ดูวิดีโอบทช่วยสอนห้านาทีนี้ หรือเลื่อนลงเพื่อดูคำแนะนำทีละขั้นตอน

<iframe width="400" height="450" src="https://www.youtube.com/embed/OZO3x2NF8Ak" frameborder="0" allowfullscreen></iframe>

## <a name="part-1-connect-to-your-sharepoint-list"></a>ส่วนที่ 1: เชื่อมต่อไปยังรายการ SharePoint ของคุณ

1. หากคุณยังไม่มี ให้ดาวน์โหลดและติดตั้ง [Power BI Desktop](https://powerbi.microsoft.com/desktop/)
2. เปิด Power BI Desktop และในแท็บหน้าแรกของริบบอน ให้เลือก **รับข้อมูล** > **เพิ่มเติม**
3. เลือก**บริการออนไลน์** จากนั้นเลือก **รายการ SharePoint Online**  

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-getdata.png" alt="get data" width="350"/>

4. เลือก **เชื่อมต่อ**
4. ค้นหาที่อยู่ (หรือที่เรียกว่า URL) ของเว็บไซต์ SharePoint Online ที่มีรายการของคุณ  จากหน้าเพจหนึ่งใน SharePoint Online โดยทั่วไปคุณสามารถรับที่อยู่ของไซต์ได้จากการเลือก **หน้าหลัก** ในบานหน้าต่างนำทาง หรือไอคอนสำหรับไซต์ที่ด้านบน จากนั้นคัดลอกที่อยู่จากแถบที่อยู่ของเว็บเบราว์เซอร์

   ดูวิดีโอของขั้นตอนนี้:
   <iframe width="400" height="300" src="https://www.youtube.com/embed/OZO3x2NF8Ak?start=48&end=90" frameborder="0" allowfullscreen></iframe>

5. ใน Power BI Desktop ให้วางที่อยู่ลงในเขตข้อมูล **URL ของไซต์** ในกล่องโต้ตอบ open (เปิด)

6. คุณอาจหรืออาจไม่เห็นหน้าจอการเข้าถึง SharePoint เหมือนรูปภาพต่อไปนี้  หากคุณไม่เห็น ให้ข้ามไปยังขั้นตอนที่ 10  หากคุณเห็น ให้เลือก **บัญชี Microsoft** ทางด้านซ้ายของหน้า

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-auth1.png" alt="choose Microsoft account" width="500"/>

7. เลือก **ลงชื่อเข้าใช้** และป้อนชื่อผู้ใช้และรหัสผ่านที่คุณใช้ในการลงชื่อเข้าใช้ Microsoft 365

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-auth2.png" alt="sign in" width="500"/>

8. เมื่อคุณเสร็จสิ้นการลงชื่อเข้าใช้ ให้เลือก **เชื่อมต่อ**

9. ที่ด้านซ้ายของตัวนำทาง ให้เลือกกล่องกาเครื่องหมายข้างรายการ SharePoint ที่คุณต้องการเชื่อมต่อ

    <img src="media/desktop-sharepoint-online-list/desktop-sharepoint-online-list-select-list.png" alt="get data" width="450"/>

10. เลือก **โหลด**  Power BI โหลดข้อมูลรายการของคุณลงในรายงานใหม่

## <a name="part-2-create-a-report"></a>ส่วนที่ 2: สร้างรายงาน

1. ทางด้านซ้าย ให้เลือกไอคอน **ข้อมูล** เพื่อดูว่ามีการโหลดข้อมูลรายการ SharePoint ของคุณแล้ว

2. ตรวจสอบให้แน่ใจว่าคอลัมน์รายการที่มีตัวเลขแสดงไอคอน Sum หรือ Sigma ใน **บานหน้าต่างเขตข้อมูล** ทางด้านขวา  หากไม่มีสิ่งใด ให้เลือกส่วนหัวของคอลัมน์ในมุมมองตาราง จากนั้นเลือกแท็บ **การสร้างแบบจำลอง** จากนั้นเปลี่ยน **ชนิดข้อมูล** เป็น **จำนวนทศนิยม** หรือ **จำนวนเต็ม** ทั้งนี้ขึ้นอยู่กับข้อมูลของคุณ  ถ้าได้รับพร้อมท์ให้ยืนยันการเปลี่ยนแปลงของคุณ ให้เลือก **ใช่**  ถ้าตัวเลขของคุณเป็นรูปแบบพิเศษ เช่น สกุลเงิน คุณยังสามารถเลือกได้จากการตั้งค่า **รูปแบบ**

   ดูวิดีโอของขั้นตอนนี้:
   <iframe width="400" height="300" src="https://www.youtube.com/embed/OZO3x2NF8Ak?start=147&end=204" frameborder="0" allowfullscreen></iframe>

3. ทางด้านซ้าย ให้เลือกไอคอน **รายงาน**
4. เลือกคอลัมน์ที่คุณต้องการแสดงภาพโดยการเลือกกล่องกาเครื่องหมายด้านข้างบานหน้าต่าง **เขตข้อมูล** ทางด้านขวา

   ดูวิดีโอของขั้นตอนนี้:
   <iframe width="400" height="300" src="https://www.youtube.com/embed/OZO3x2NF8Ak?start=215&end=252" frameborder="0" allowfullscreen></iframe>

5. เปลี่ยนชนิดของวิชวล ถ้าคุณต้องการ
6. คุณสามารถสร้างการแสดงผลข้อมูลด้วยภาพหลายรายการในรายงานเดียวกันได้โดยการกดโดยยกเลิกการเลือกวิชวลที่มีอยู่ แล้วเลือกกล่องกาเครื่องหมายสำหรับคอลัมน์อื่นในบานหน้าต่าง **เขตข้อมูล**
7. เลือก **บันทึก** เพื่อบันทึกรายงานของคุณ

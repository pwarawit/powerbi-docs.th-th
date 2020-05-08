---
title: เผยแพร่จาก Power BI Desktop
description: เผยแพร่จาก Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 3a67c36b2594696e1c576693cc5808eb0227c1c7
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "76709604"
---
# <a name="publish-datasets-and-reports-from-power-bi-desktop"></a>เผยแพร่ชุดข้อมูลและรายงานจาก Power BI Desktop
เมื่อคุณเผยแพร่เป็นไฟล์ Power BI Desktop ไปยังบริการ Power BI แสดงว่าคุณได้เผยแพร่ข้อมูลในแบบจำลองดังกล่าวไปยังพื้นที่ทำงาน Power BI ของคุณ ข้อมูลเดียวกันนี้จะเป็นจริงสำหรับรายงานใด ๆ ที่คุณสร้างไว้ในมุมมอง**รายงาน** คุณจะเห็นชุดข้อมูลใหม่ที่มีชื่อเดียวกัน และรายงานต่างๆในตัวนำทางของพื้นที่ทำงานของคุณ

การเผยแพร่จาก Power BI Desktop จะให้ผลลัพธ์เดียวกันกับการใช้ **Get Data** ใน Power BI เพื่อเชื่อมต่อและอัปโหลดไฟล์ Power BI Desktop

> [!NOTE]
> การเปลี่ยนแปลงใดๆที่คุณทำกับรายงานใน Power BI จะไม่ถูกบันทึกกลับไปยังไฟล์ Power BI Desktop ต้นฉบับ ซึ่งรวมถึงเวลาที่คุณเเพิ่ม ลบ หรือเปลี่ยนแปลงการแสดงภาพต่าง ๆ ในรายงาน
> 
> 

## <a name="to-publish-a-power-bi-desktop-dataset-and-reports"></a>เมื่อต้องการเผยแพร่ชุดข้อมูลและรายงาน Power BI Desktop
1. ใน Power BI Desktop เลือก **ไฟล์** \> **เผยแพร่** \> **เผยแพร่ไปยัง Power BI** หรือเลือก **เผยแพร่** บน Ribbon  

   ![ปุ่มเผยแพร่](media/desktop-upload-desktop-files/pbid_publish_publishbutton.png)

2. ลงชื่อเข้าใช้ไปยัง Power BI
3. เลือกปลายทาง

   ![เลือกปลายทางของการเผยแพร่](media/desktop-upload-desktop-files/pbid_publish_select_destination.png)

เมื่อการเผยแพร่เสร็จสมบูรณ์ คุณจะได้รับลิงก์ไปยังรายงานของคุณ เลือกลิงก์เพื่อเปิดรายงานในไซต์ Power BI ของคุณ

![กล่องโต้ตอบเผยแพร่สำเร็จ](media/desktop-upload-desktop-files/pbid_publish_success.png)

## <a name="republish-or-replace-a-dataset-published-from-power-bi-desktop"></a>เผยแพร่อีกครั้งหรือแทนที่ชุดข้อมูลที่เผยแพร่จาก Power BI Desktop
ชุดข้อมูลและรายงานใดๆ ที่คุณสร้างขึ้นใน Power BI Desktop ให้อัปโหลดไปยังไซค์ Power BI ของคุณเมื่อเผยแพร่ไฟล์ Power BI Desktop เมื่อคุณเผยแพร่ไฟล์ Power BI Desktop ของคุณอีกครั้ง ชุดข้อมูลในไซต์ Power BI ของคุณจะถูกแทนที่ด้วยชุดข้อมูลที่อัปเดตแล้วจากไฟล์ Power BI Desktop

กระบวนการนี้ค่อนข้างจะตรงไปตรงมา แต่จะมีรายการ 2-3 รายการที่คุณควรทราบ:

* ถ้าคุณมีชุดข้อมูลสองรายการ หรือมากกว่าใน Power BI โดยใช้ชื่อเดียวกันกับไฟล์ Power BI Desktop การเผยแพร่อาจล้มเหลวได้ ตรวจสอบให้แน่ใจว่า คุณมีชุดข้อมูลเดียวเท่านั้นใน Power BI ที่มีชื่อเดียวกัน นอกจากนี้คุณยังสามารถเปลี่ยนชื่อไฟล์และเผยแพร่ โดยสร้างชุดข้อมูลใหม่ชื่อเดียวกันกับไฟล์
* ถ้าคุณเปลี่ยนชื่อหรือลบคอลัมน์หรือหน่วยวัด การแสดงภาพใดๆที่คุณมีใน Power BI ที่มีเขตข้อมูลนั้นอาจจะไม่สามารถใช้งาน 
* Power BI ละเว้นการเปลี่ยนแปลงการจัดรูปแบบบางอย่างของคอลัมน์ที่มีอยู่ ตัวอย่างเช่น หากคุณเปลี่ยนรูปแบบของคอลัมน์จาก 0.25% เป็น 25%
* สมมติว่าคุณมีกำหนดการรีเฟรชที่มีการกำหนดค่าสำหรับชุดข้อมูลที่มีอยู่ของคุณใน Power BI เมื่อคุณเพิ่มแหล่งข้อมูลใหม่ลงในไฟล์ของคุณแล้วเผยแพร่อีกครั้ง คุณจะต้องลงชื่อเข้าใช้ก่อน่การรีเฟรชตามกำหนดการครั้งถัดไป
* เมื่อคุณเผยแพร่ชุดข้อมูลที่เผยแพร่จาก Power BI Desktop ใหม่ และมีการกำหนดตารางเวลาการรีเฟรช การรีเฟรชชุดข้อมูลจะเริ่มต้นทันทีที่คุณเผยแพร่อีกครั้ง 


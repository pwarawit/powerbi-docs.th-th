---
title: เผยแพร่จาก Power BI Desktop
description: เผยแพร่จาก Power BI Desktop
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
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 1ac80fb4f355ba9199554ceb043cf7e8ff79ce54
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
ms.locfileid: "30974576"
---
# <a name="publish-from-power-bi-desktop"></a>เผยแพร่จาก Power BI Desktop
เมื่อคุณเผยแพร่เป็นไฟล์**Power BI Desktop**ไปยัง**Power BI service** ข้อมูลอยู่ในรูปแบบและใด ๆ ที่คุณสร้างขึ้นในมุมมอง**รายงาน**ซึ่งเผยแพร่ไปยังพื้นที่ทำงาน Power BI ของคุณ คุณจะเห็นชุดข้อมูลใหม่ที่มีชื่อเดียวกัน และรายงานต่างๆในตัวนำทางของพื้นที่ทำงานของคุณ

โดยการเผยแพร่จาก**Power BI Desktop**มีผลเช่นเดียวกับการใช้การ**รับข้อมูล**ใน Power BI เพื่อเชื่อมต่อ และอัปโหลดไฟล์**Power BI Desktop**

> [!NOTE]
> การเปลี่ยนแปลงใดๆ ที่คุณทำในลงในรายงาน Power BI ตัวอย่างเช่น เพิ่ม ลบ หรือเปลี่ยนแปลงการจัดรูปแบบข้อมูลในรายงาน จะไม่ถูกบันทึกลงในไฟล์ต้นฉบับ**Power BI Desktop**
> 
> 

## <a name="to-publish-a-power-bi-desktop-dataset-and-reports"></a>เมื่อต้องการเผยแพร่ชุดข้อมูลและรายงาน Power BI Desktop
1. ใน Power BI Desktop \> **ไฟล์** \>**เผยแพร่** \> **เผยแพร่ไปยัง Power BI** หรือคลิกเผยแพร่**บนริบ**บอน  
   ![](media/desktop-upload-desktop-files/pbid_publish_publishbutton.png)
2. ลงชื่อเข้าใช้ไปยัง Power BI

เมื่อเสร็จสิ้น คุณจะได้รับลิงก์เพื่อเปิดรายงานของคุณในเว็บไซต์ Power BI ของคุณ  
    ![](media/desktop-upload-desktop-files/pbid_publish_success.png)

## <a name="re-publish-or-replace-a-dataset-published-from-power-bi-desktop"></a>เผยแพร่อีกครั้งหรือแทนที่ชุดข้อมูลที่เผยแพร่จาก Power BI Desktop
เมื่อคุณเผยแพร่ไฟล์**Power BI Desktop** ชุดข้อมูลและรายงานใด ๆ ที่คุณสร้างขึ้นใน**Power BI Desktop**ถูกอัปโหลดไปยังเไซต์ Power BI ของคุณ เมื่อคุณเผยแพร่แฟ้ม**Power BI Desktop**ของคุณอีกครั้ง ชุดข้อมูลในไซต์ Power BI ของคุณจะถูกแทนที่ด้วยชุดข้อมูลที่ถูกอัปเดจากไฟล์**Power BI Desktop**

สิ่งนี้ค่อนข้างตรงไปตรงมา แต่ก็มีบางสิ่งที่คุณควรทราบ

* ถ้าคุณมีชุดข้อมูลสองรายการ หรือมากกว่าใน Power BI โดยใช้ชื่อเดียวกันกับไฟล์**Power BI Desktop** การเผยแพร่อาจล้มเหลวได้ ตรวจสอบให้แน่ใจว่า คุณมีชุดข้อมูลเดียวเท่านั้นใน Power BI ที่มีชื่อเดียวกัน นอกจากนี้คุณยังสามารถเปลี่ยนชื่อไฟล์และเผยแพร่ โดยสร้างชุดข้อมูลใหม่ชื่อเดียวกันกับไฟล์
* ถ้าคุณเปลี่ยนชื่อหรือลบคอลัมน์หรือหน่วยวัด การแสดงภาพใดๆที่คุณมีใน Power BI ที่มีเขตข้อมูลนั้นอาจจะไม่สามารถใช้งาน 
* Power BI ละเว้นการเปลี่ยนแปลงการจัดรูปแบบบางอย่างของคอลัมน์ที่มีอยู่ ตัวอย่างเช่น ถ้าคุณเปลี่ยนรูปแบบของคอลัมน์จาก 0.25 เป็น 25%
* ถ้าคุณมีการกำหนดเวลาการรีเฟรชสำหรับชุดข้อมูลของคุณใน Power BI และคุณได้เพิ่มแหล่งข้อมูลใหม่ลงในไฟล์ของคุณ แล้วเผยแพร่อีกครั้ง คุณจะต้องลงชื่อเข้าใช้*จัดการแหล่งข้อมูล*ก่อนที่จะมีการรีเฟรชตามกำหนดเวลาครั้งถัดไป


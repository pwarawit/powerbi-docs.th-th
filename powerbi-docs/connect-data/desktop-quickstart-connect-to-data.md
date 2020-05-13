---
title: เริ่มต้นใช้งานด่วน เชื่อมต่อกับข้อมูลใน Power BI Desktop
description: วิธีการเชื่อมต่อกับแหล่งข้อมูลที่พร้อมใช้งานใน Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: quickstart
ms.date: 01/10/2020
ms.author: davidi
LocalizationGroup: quickstart
ms.openlocfilehash: d689258b4e4da5349d57b41f72d4266eb759029b
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83348608"
---
# <a name="quickstart-connect-to-data-in-power-bi-desktop"></a>เริ่มต้นใช้งานด่วน: เชื่อมต่อกับข้อมูลใน Power BI Desktop

ในเริ่มต้นใช้งานด่วนนี้ คุณเชื่อมต่อกับข้อมูลโดยใช้ Power BI Desktop ซึ่งเป็นขั้นตอนแรกในการสร้างรูปแบบข้อมูล และสร้างรายงาน

![Power BI Desktop](media/desktop-what-is-desktop/what-is-desktop_01.png)

ถ้าคุณไม่ได้ลงทะเบียน Power BI ให้[ลงทะเบียนรุ่นทดลองใช้ฟรี](https://app.powerbi.com/signupredirect?pbi_source=web)ก่อนที่คุณจะเริ่มต้นใช้งาน

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

เพื่อทำตามขั้นตอนในบทความนี้ คุณจำเป็นต้องมีทรัพยากรต่อไปนี้:

* ดาวน์โหลด และติดตั้ง Power BI Desktop ซึ่งเป็นโปรแกรมประยุกต์ฟรีที่ทำงานบนคอมพิวเตอร์ของคุณ คุณสามารถ[ดาวน์โหลด Power BI Desktop](https://powerbi.microsoft.com/desktop) ได้โดยตรง หรือคุณสามารถดาวน์โหลดได้จาก [Microsoft Store](https://aka.ms/pbidesktopstore) ได้
* [ดาวน์โหลดเวิร์กบุ๊ก Excel ตัวอย่างนี้](https://go.microsoft.com/fwlink/?LinkID=521962) และสร้างโฟลเดอร์ที่ชื่อว่า *C:\PBID-qs* ซึ่งคุณสามารถเก็บไฟล์ Excel ขั้นตอนต่อ ๆ ไปในเริ่มต้นใช้งานด่วนนี้ ถือว่า นั่นคือตำแหน่งที่ตั้งไฟล์สำหรับเวิร์กบุ๊ก Excel ที่ดาวน์โหลด
* สำหรับตัวเชื่อมต่อข้อมูลจำนวนมากใน Power BI Desktop จำเป็นต้องใช้ Internet Explorer 10 (หรือใหม่กว่า) สำหรับการรับรองความถูกต้อง

## <a name="launch-power-bi-desktop"></a>เปิดใช้ Power BI Desktop

เมื่อคุณติดตั้ง Power BI Desktop แล้ว เปิดใช้แอปพลิเคชันเพื่อให้ทำงานบนคอมพิวเตอร์ของคุณ คุณจะเห็นบทช่วยสอน Power BI ทำตามบทช่วยสอนหรือปิดกล่องโต้ตอบเพื่อเริ่มต้นด้วยพื้นที่ทำงานว่างเปล่า พื้นที่ทำงานคือพื้นที่ที่คุณสามารถสร้างวิชวลและรายงานต่าง ๆ จากข้อมูลของคุณได้

![Power BI Desktop พร้อมพื้นที่ทำงานว่างเปล่า](media/desktop-quickstart-connect-to-data/qs-connect-data_01.png)

## <a name="connect-to-data"></a>เชื่อมต่อกับข้อมูล

ด้วย Power BI Desktop คุณสามารถเชื่อมต่อกับข้อมูลประเภทต่าง ๆ มากมาย แหล่งข้อมูลเหล่านี้ หมายรวมถึงแหล่งข้อมูลพื้นฐาน เช่น ไฟล์ Microsoft Excel คุณสามารถเชื่อมต่อกับบริการออนไลน์ที่ประกอบด้วยข้อมูลทุกประเภท เช่น Salesforce, Microsoft Dynamics, Azure Blob Storage และอื่น ๆ อีกมากมาย

เพื่อเชื่อมต่อกับข้อมูล ไปที่ ribbon **หน้าแรก** และเลือก**รับข้อมูล**

![รับข้อมูลบน ribbon หน้าหลัก](media/desktop-quickstart-connect-to-data/qs-connect-data_02.png)

หน้าต่าง **รับข้อมูล** จะปรากฏขึ้น คุณสามารถเลือกได้จากแหล่งข้อมูลหลายประเภทมามกมายที่ Power BI Desktop สามารถเชื่อมต่อด้วยได้ ในเริ่มต้นใช้งานด่วนนี้ ให้ใชเวิร์กบุ๊ก Excel ที่คุณดาวน์โหลดใน [ข้อกำหนดเบื้องต้น](#prerequisites)

![รับข้อมูลจากแหล่งข้อมูลทั้งหมด](media/desktop-quickstart-connect-to-data/qs-connect-data_03.png)

เนื่องจากแหล่งข้อมูลนี้เป็นไฟล์ Excel ให้เลือก **Excel** จากหน้าต่าง **รับข้อมูล** จากนั้น เลือกปุ่ม **เชื่อมต่อ**

Power BI จะแจ้งให้คุณระบุตำแหน่งที่ตั้งของไฟล์ Excel ที่ต้องการเชื่อมต่อ ไฟล์ที่ดาวน์โหลดจะเรียกว่า *ตัวอย่างทางการเงิน* เลือกไฟล์ดังกล่าว จากนั้น เลือก **เปิด**

![รับข้อมูลในตัวอย่างทางการเงิน](media/desktop-quickstart-connect-to-data/qs-connect-data_04.png)

จากนั้น Power BI Desktop จะโหลดเวิร์กบุ๊กและอ่านเนื้อหาของตนเอง และแสดงข้อมูลที่มีอยู่ในไฟล์โดยใช้หน้าต่าง **ตัวนำทาง** ในหน้าต่างดังกล่าว คุณสามารถเลือกข้อมูลที่คุณต้องการโหลดไปยัง Power BI Desktop เลือกตารางดังกล่าวโดยกาที่กล่องกาเครื่องหมายข้างแต่ละตารางที่คุณต้องการนำเข้า นำเข้าตารางที่พร้อมใช้งานทั้งคู่

![เลือกข้อมูลในหน้าต่างตัวนำทาง](media/desktop-quickstart-connect-to-data/qs-connect-data_05.png)

เมื่อคุณเลือกเสร็จแล้ว เลือก**โหลด**เพื่อนำเข้าข้อมูลลงใน Power BI Desktop

## <a name="view-data-in-the-fields-pane"></a>ดูข้อมูลในบานหน้าต่างเขตข้อมูล

เมื่อคุณโหลดตารางเสร็จ บานหน้าต่าง**เขตข้อมูล**จะแสดงข้อมูลให้คุณ คุณสามารถขยายแต่ละตารางโดยเลือกที่ลูกศรข้างชื่อ ในรูปต่อไปนี้ ตาราง *financials* ถูกขยาย แสดงแต่ละเขตข้อมูลของตารางนั้น

![รับข้อมูล](media/desktop-quickstart-connect-to-data/qs-connect-data_06.png)

เท่านี้ก็เรียบร้อย! คุณได้เชื่อมต่อกับข้อมูลใน Power BI Desktop โหลดข้อมูลนั้น และตอนนี้ คุณเห็นเขตข้อมูลทั้งหมดที่มีในตารางเหล่านั้น

## <a name="next-steps"></a>ขั้นตอนถัดไป

คุณสามารถทำอะไรได้มากมายด้วย Power BI Desktop เมื่อคุณเชื่อมต่อกับข้อมูลแล้ว เช่น การสร้างวิชวลและรายงาน ลองดูที่ทรัพยากรต่อไปนี้เพื่อช่วยคุณเริ่มต้น:

* [เริ่มต้นใช้งาน Power BI Desktop](../fundamentals/desktop-getting-started.md)

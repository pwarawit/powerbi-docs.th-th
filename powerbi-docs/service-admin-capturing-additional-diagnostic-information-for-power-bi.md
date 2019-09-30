---
title: การจับข้อมูลการวินิจฉัยเพิ่มเติม
description: คำแนะนำนี้ ให้สองทางเลือกในการรวบรวมข้อมูลเพิ่มเติมเพื่อการวินิจฉัยจาก เว็บไคลเอ็นต์ Power BI
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 710fb4cdcf9efb051434966d47c2eaced17ac9ba
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100229"
---
# <a name="capture-additional-diagnostic-information-for-power-bi"></a>จับข้อมูลการวินิจฉัยเพิ่มเติมสำหรับ Power BI

บทความนี้ ให้ข้อมูลที่ได้ในการรวบรวมเพิ่มเติมเพื่อการวินิจฉัยจาก เว็บไคลเอ็นต์ Power BI

1. เรียกดู [Power BI](https://app.powerbi.com) ด้วย Microsoft Edge หรือ Internet Explorer

1. กด **F12**เพื่อเปิดเครื่องมือสำหรับนักพัฒนา Microsoft Edge

   ![สกรีนช็อตของแท็บองค์ประกอบเครื่องมือสำหรับนักพัฒนา Microsoft Edge](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)

1. เลือกแท็บ **เครือข่าย** จะแสดงรายการข้อมูลเครือข่ายที่ดักจับได้แล้ว

   ![สกรีนช็อตของแท็บเครือข่ายเครื่องมือสำหรับนักพัฒนา Microsoft Edge](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)

    คุณสามารถ

    * เรียกดูภายในหน้าต่าง และจำลองปัญหาใดก็ได้ที่คุณกำลังเจออยู่

    * ซ่อนและแสดงหน้าต่าง เครื่องมือสำหรับนักพัฒนา ตลอดเวลาระหว่างเซสชัน โดยการกด F12

1. เมื่อต้องหยุดการการสร้างโปรไฟล์เซสซันคุณสามารถเลือกสี่เหลี่ยมสีแดงบนแท็บ**เครือข่าย** ในบริเวณของเครื่องมือสำหรับนักพัฒนา

   ![สกรีนช็อตของแท็บเครือข่ายของเครื่องมือสำหรับนักพัฒนา Microsoft Edge ที่มีการโทรออกจากปุ่มหยุด](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)

1. เลือกไอคอนดิสก์เพื่อส่งออกข้อมูลเป็นไฟล์ที่เก็บถาวรของ HTTP (ฮาร์)

   ![สกรีนช็อตของแท็บเครือข่ายของเครื่องมือสำหรับนักพัฒนา Microsoft Edge ที่มีการโทรออกจากไอคอนแผ่นดิสก์](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)

1. ใส่ชื่อไฟล์ และบันทึกไฟล์ HAR

    ไฟล์ HAR จะประกอบด้วยข้อมูลทั้งหมดเกี่ยวกับคำขอเครือข่าย ระหว่างหน้าต่างเบราว์เซอร์และ Power BI ซึ่งรวมไปถึง:

    * ID กิจกรรมสำหรับการร้องขอแต่ละรายการ

    * ประทับเวลาที่แม่นยำสำหรับการร้องขอแต่ละรายการ

    * ข้อมูลข้อผิดพลาดใดๆที่ส่งกลับไปยังไคลเอ็นต์

    แฟ้มการติดตามที่ได้ ยังประกอบด้วยข้อมูลที่ใช้เพื่อแสดงภาพบนหน้าจอ

1. คุณสามารถส่งไฟล์ HAR ให้ฝ่ายสนับสนุนสำหรับตรวจสอบ

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](http://community.powerbi.com/)

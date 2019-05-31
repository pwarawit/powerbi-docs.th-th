---
title: เก็บรวบรวมข้อมูลการวินิจฉัยเพิ่มเติม
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
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100229"
---
# <a name="capture-additional-diagnostic-information-for-power-bi"></a>เก็บรวบรวมข้อมูลการวินิจฉัยเพิ่มเติมสำหรับ Power BI

บทความนี้มีคำแนะนำสำหรับการรวบรวมข้อมูลการวินิจฉัยเพิ่มเติมด้วยตนเองจากไคลเอ็นต์เว็บ Power BI

1. เรียกดู[Power BI](https://app.powerbi.com)ด้วย Microsoft Edge หรือ Internet Explorer

1. กด**F12**เพื่อเปิดเครื่องมือนักพัฒนา Microsoft Edge

   ![สกรีนช็อตของ Microsoft Edge แท็บนักพัฒนาเครื่องมือองค์ประกอบ](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)

1. เลือกแท็บ **เครือข่าย** จะแสดงรายการข้อมูลเครือข่ายที่ดักจับได้แล้ว

   ![สกรีนช็อตของ Microsoft Edge แท็บนักพัฒนาเครื่องมือเครือข่าย](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)

    คุณสามารถ

    * เรียกดูภายในหน้าต่าง และจำลองปัญหาใดก็ได้คุณอาจมาถึง

    * ซ่อน และแสดงนักพัฒนาหน้าต่างเครื่องมือตลอดเวลาระหว่างเซสชัน โดยการกด F12

1. เมื่อต้องหยุดการสร้างโพรไฟล์เซสชัน คุณสามารถเลือกสี่เหลี่ยมสีแดงบนการ**เครือข่าย**แท็บนักพัฒนาของเครื่องมือพื้นที่ได้

   ![สกรีนช็อตของ Microsoft Edge แท็บนักพัฒนาเครื่องมือเครือข่าย ด้วยการโทรออกจากปุ่มหยุด](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)

1. เลือกไอคอนแผ่นดิสก์เพื่อส่งออกข้อมูลเป็นไฟล์เก็บถาวร HTTP (HAR)

   ![สกรีนช็อตของ Microsoft Edge แท็บนักพัฒนาเครื่องมือเครือข่าย ด้วยคำบรรยายภาพของไอคอนแผ่นดิสก์](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)

1. ใส่ชื่อไฟล์ และบันทึกไฟล์ HAR

    ไฟล์ HAR จะประกอบด้วยข้อมูลทั้งหมดเกี่ยวกับคำขอเครือข่ายระหว่างหน้าต่างเบราว์เซอร์และ Power BI รวมถึง:

    * รหัสกิจกรรมของแต่ละคำขอ

    * การประทับเวลาที่แม่นยำสำหรับแต่ละคำขอ

    * ข้อมูลข้อผิดพลาดใด ๆ ที่ส่งกลับไปยังไคลเอนต์

    แฟ้มการติดตามที่ได้ ยังประกอบด้วยข้อมูลที่ใช้เพื่อแสดงภาพบนหน้าจอ

1. คุณสามารถส่งไฟล์ HAR ให้ฝ่ายสนับสนุนสำหรับตรวจสอบ

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](http://community.powerbi.com/)

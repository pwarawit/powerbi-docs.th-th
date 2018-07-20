---
title: การจับข้อมูลการวินิจฉัยเพิ่มเติม
description: การจับข้อมูลการวินิจฉัยเพิ่มเติม
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 76860e740d43a1907692a7cd4fed1a6df68c93d4
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34239233"
---
# <a name="capturing-additional-diagnostic-information"></a>การจับข้อมูลการวินิจฉัยเพิ่มเติม
## <a name="capturing-additional-diagnostic-information-for-power-bi"></a>การจับข้อมูลการวินิจฉัยเพิ่มเติมสำหรับ Power BI
คำแนะนำนี้ ให้สองทางเลือกในการรวบรวมข้อมูลเพิ่มเติมเพื่อการวินิจฉัยจาก เว็บไคลเอ็นต์ Power BI  มีเพียงทางเลือกหนึ่งเท่านั้นที่จะต้องทำตาม

## <a name="network-capture---edge--internet-explorer"></a>ดักจับข้อมูลเครือข่าย - Edge และ Internet Explorer
1. เรียกดู [Power BI](https://app.powerbi.com) ด้วย Edge หรือ Internet Explorer
2. เปิดเครื่องมือนักพัฒนา Edge โดยการกด F12
3. จะแสดงหน้าต่างเครื่องมือสำหรับนักพัฒนา: 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-developer-tools.png)
4. สลับไปยังแท็บเครือข่าย จะแสดงรายการข้อมูลเครือข่ายที่ดักจับได้แล้ว 
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab.png)
5. คุณสามารถเรียกดูภายในหน้าต่าง และจำลองปัญหาใดก็ได้ที่คุณกำลังเจออยู่ คุณสามารถซ่อนและแสดงหน้าต่าง เครื่องมือสำหรับนักพัฒนา ตลอดเวลาระหว่างเซสชัน โดยการกด F12
6. เมื่อต้องหยุดการดักจับข้อมูล คุณสามารถเลือกสี่เหลี่ยมสีแดงบนแท็บเครือข่าย ในบริเวณของเครื่องมือสำหรับนักพัฒนา
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-stop.png)
7. เลือกบนไอคอนรูปแผ่นดิสก์เพื่อ**ส่งออกเป็น HAR**
   
   ![](media/service-admin-capturing-additional-diagnostic-information-for-power-bi/edge-network-tab-save.png)
8. ใส่ชื่อไฟล์ และบันทึกไฟล์ HAR
   
    ไฟล์ HAR จะประกอบด้วยข้อมูลทั้งหมดเกี่ยวกับคำขอเครือข่าย ระหว่างหน้าต่างเบราว์เซอร์และ Power BI  ซึ่งจะรวมถึง รหัสกิจกรรมของแต่ละคำขอ ประทับเวลาที่แม่นยำของคำขอ และข้อมูลข้อผิดพลาดใด ๆ ที่ส่งกลับไปยังไคลเอนต์  แฟ้มการติดตามที่ได้ ยังประกอบด้วยข้อมูลที่ใช้เพื่อแสดงภาพบนหน้าจอ
9. คุณสามารถส่งไฟล์ HAR ให้ฝ่ายสนับสนุนสำหรับตรวจสอบ

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](http://community.powerbi.com/)


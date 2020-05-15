---
title: สร้างคิวอาร์โค้ดให้แก่รายงานที่ใช้ในแอปสำหรับอุปกรณ์เคลื่อนที่ของ Power BI
description: คิวอาร์โค้ดใน Power BI สามารถเชื่อมต่อทุกอย่างในโลกแห่งความจริง เข้ากับข้อมูลที่เกี่ยวข้องกับ BI ในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ได้โดยตรง โดยที่ไม่จำเป็นต้องใช้การค้นหา
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/07/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 0d7d0e9e1845eb7e075b8ad1ea3254c82c1d616d
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83314730"
---
# <a name="create-a-qr-code-for-a-tile-in-power-bi-to-use-in-the-mobile-apps"></a>สร้างคิวอาร์โค้ด ให้แก่รายงานที่ใช้ในแอปสำหรับอุปกรณ์เคลื่อนที่ของ Power BI
คิวอาร์โค้ดใน Power BI สามารถเชื่อมต่อทุกอย่างในโลกแห่งความจริง เข้ากับข้อมูลที่เกี่ยวข้องกับ BI่ได้โดยตรง &#151; โดยที่ไม่จำเป็นต้องใช้การค้นหา

คุณสามารถสร้างคิวอาร์โค้ด ในบริการ Power BI สำหรับไทล์ในแดชบอร์ดใด ๆ แม้ว่าในแดชบอร์ดของคุณไม่สามารถแก้ไข จากนั้น คุณใส่คิวอาร์โค้ดในตำแหน่งหลัก ตัวอย่างเช่น คุณสามารถวางลงในอีเมล หรือพิมพ์ออกมาและวางในตำแหน่งที่เจาะจง 

เพื่อนร่วมงานที่คุณแชร์รายงานด้วยจะสามารถสแกนคิวอาร์โค้ดเพื่อเข้าถึงรายงาน ได้จาก[อุปกรณ์เคลื่อนที่ของพวกเขา](../consumer/mobile/mobile-apps-qr-code.md) พวกเขาสามารถใช้ที่สแกนคิวอาร์โค้ดที่อยู่ในแอป Power BI หรือที่สแกนคิวอาร์โค้ดอื่น ๆ ที่ติดตั้งบนอุปกรณ์ของพวกเขา


## <a name="create-a-qr-code-for-a-tile"></a>สร้างคิวอาร์โค้ดสำหรับไทล์
1. เปิดแดชบอร์ดในบริการ Power BI
2. เลือก **ตัวเลือกเพิ่มเติม** (...) ที่มุมขวาบนของไทล์ แล้วเลือก**โหมดโฟกัส** ![](media/service-create-qr-code-for-tile/fullscreen-icon.jpg)
3. เลือก **ตัวเลือกเพิ่มเติม** (...) ที่มุมขวาบน แล้วเลือก**สร้างคิวอาร์โค้ด** 
   
    ![](media/service-create-qr-code-for-tile/power-bi-create-qr-code-tile.png)
4. กล่องโต้ตอบที่มีคิวอาร์โค้ดจะปรากฏขึ้น 
   
    ![](media/service-create-qr-code-for-tile/pbi_qrcode_opportunity_count.png)
5. จากที่นี่ คุณสามารถสแกนคิวอาร์โค้ด หรือดาวน์โหลด และบันทึกเพื่อให้คุณสามารถ: 
   
   * เพิ่มคิวอาร์โค้ดลงในอีเมลหรือเอกสารอื่น ๆ หรือ 
   * พิมพคิวอาร์โค้ดและวางในตำแหน่งที่เจาะจง 

## <a name="print-the-qr-code"></a>พิมพ์คิวอาร์โค้ด
Power BI สร้างคิวอาร์โค้ด เป็นไฟล์ JPG พร้อมที่จะพิมพ์ 

1. เลือก**ดาวน์โหลด**แล้ว เปิดไฟล์ JPG บนคอมพิวเตอร์ที่เชื่อมต่อกับเครื่องพิมพ์  
   
   > [!TIP]
   > ไฟล์ JPG จะมีชื่อเหมือนกันเป็นไทล์ ตัวอย่างเช่น “การนับจำนวนโอกาส - ตามเดือน ขั้นการขาย.jpg”
   > 
   > 
2. พิมพ์ไฟล์ที่ขนาด 100 เปอร์เซ็นต์ หรือ “ขนาดตามจริง”  
3. ตัดคิวอาร์โค้ดโดยรอบตามของของแผ่นงาน และใช้กาวติดไว้ตรงบริเวณที่เกี่ยวข้องกับรายงานนั้น ๆ 

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [เชื่อมต่อกับข้อมูล Power BI จากโลกแห่งความจริง](../consumer/mobile/mobile-apps-data-in-real-world-context.md)ด้วยแอปโทรศัพท์เคลื่อนที่
* [สแกนคิวอาร์โค้ดของ Power BI จากอุปกรณ์เคลื่อนที่ของคุณ](../consumer/mobile/mobile-apps-qr-code.md)
* [สร้างคิวอาร์โค้ดสำหรับรายงาน](service-create-qr-code-for-report.md)
* มีคำถามหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
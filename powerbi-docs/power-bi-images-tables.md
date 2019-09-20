---
title: แสดงรูปภาพต่าง ๆ ในตารางหรือเมทริกซ์ในรายงาน
description: ใน Power BI Desktop ให้คุณสร้างคอลัมน์ที่มีไฮเปอร์ลิงก์ไปยังรูปภาพ จากนั้นจึงเพิ่มไฮเปอร์ลิงก์ดังกล่าวไปยังตารางรายงาน เมทริกซ์ ตัวแบ่งส่วนข้อมูล หรือการ์ดแบบหลายแถวเพื่อแสดงรูปภาพใน Power BI Desktop หรือบริการของ Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/11/2019
ms.author: maggies
LocalizationGroup: Visualizations
ms.openlocfilehash: 2ebbc277f2a269ebaf2d1bdb99f1aa800576b466
ms.sourcegitcommit: ba085b248c54e8fb1fd8eb2bb23a814e3fdd7ff6
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2019
ms.locfileid: "70936504"
---
# <a name="display-images-in-a-table-matrix-or-slicer-in-a-report"></a>แสดงรูปภาพต่าง ๆ ในตาราง เมทริกซ์ หรือตัวแบ่งส่วนข้อมูลในรายงาน

วิธีที่ดีในการเพิ่มประสิทธิภาพให้กับรายงานของคุณคือการเพิ่มรูปภาพในรายงาน รูปภาพแบบคงที่บนหน้ารายงานนั้นเหมาะสำหรับวัตถุประสงค์บางอย่าง แต่บางครั้งคุณก็ต้องใช้รูปภาพที่เกี่ยวข้องกับข้อมูลในรายงานของคุณ ในหัวข้อนี้จะสอนวิธีการแสดงรูปภาพต่าง ๆ ในตาราง เมทริกซ์ ตัวแบ่งส่วนข้อมูล หรือการ์ดแบบหลายแถว 

![รูปภาพ URL ในตาราง](media/power-bi-images-tables/power-bi-url-images-table.png)

## <a name="add-images-to-your-report"></a>เพิ่มรูปภาพลงในรายงานของคุณ

1. สร้างคอลัมน์ที่มี Url ของรูปภาพ ดูข้อกำหนดต่าง ๆ ได้ที่[ข้อควรพิจารณา](#considerations)ในบทความนี้

1. เลือกคอลัมน์นั้น บนริบบอน**การวางรูปแบบ**สำหรับ**หมวดหมู่ข้อมูล** ให้เลือก**URL ของรูปภาพ**

    ![ตั้งค่าหมวดหมู่ข้อมูลเป็น URL ของรูปภาพ](media/power-bi-images-tables/power-bi-set-url-image.png)

1. เพิ่มคอลัมน์ไปที่ตาราง เมทริกซ์ ตัวแบ่งส่วนข้อมูล หรือการ์ดแบบหลายแถว

    ![ตัวแบ่งส่วนข้อมูลที่มีรูปภาพ](media/power-bi-images-tables/power-bi-url-images-slicer.png)

## <a name="considerations"></a>ข้อควรพิจารณา

- รูปภาพต้องอยู่ในรูปแบบไฟล์เหล่านี้:  .bmp, .jpg, .jpeg, .gif, .png หรือ .svg
- URL ต้องสามารถเข้าถึงได้โดยไม่ระบุตัวตน และไม่อยู่ในเว็บไซต์ที่จำเป็นต้องลงชื่อเข้าใช้ เช่น SharePoint อย่างไรก็ตาม หากมีการโฮสต์รูปภาพบน SharePoint หรือ OneDrive คุณอาจได้รับรหัสฝังตัวซึ่งจะนำทางไปยังรูปภาพดังกล่าวโดยตรง 


## <a name="next-steps"></a>ขั้นตอนถัดไป

[เพิ่มรูปร่างแบบคงที่ กล่องข้อความ และรูปภาพในรายงาน](https://docs.microsoft.com/power-bi/guided-learning/visualizations?tutorial-step=11)

[แนวคิดพื้นฐานสำหรับนักออกแบบในบริการ Power BI](service-basic-concepts.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


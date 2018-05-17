---
title: การเรียกใช้สคริปต์ R ใน Power BI Desktop
description: การเรียกใช้สคริปต์ R ใน Power BI Desktop
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
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 34e756a661ec580e2c0eea8fc53378566eccf305
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/12/2018
---
# <a name="run-r-scripts-in-power-bi-desktop"></a>เรียกใช้สคริปต์ R ใน Power BI Desktop
คุณสามารถเรียกใช้สคริปต์ R โดยตรงใน**Power BI Desktop** และนำเข้าชุดข้อมูลผลลัพธ์ลงในรูปแบบข้อมูล Power BI Desktop ได้

## <a name="install-r"></a>ติดตั้ง R
เพื่อเรียกใช้สคริปต์ R ใน Power BI Desktop คุณจำเป็นต้องติดตั้ง **R** บนเครื่องคอมพิวเตอร์ของคุณ คุณสามารถดาวน์โหลด และติดตั้ง **R** ฟรีจากหลายแหล่ง รวมไปถึง[หน้าดาวน์โหลด Revolution Open](https://mran.revolutionanalytics.com/download/) และ[ที่เก็บ CRAN](https://cran.r-project.org/bin/windows/base/) ได้ รุ่นปัจจุบันของการเขียนสคริปต์ R ใน Power BI Desktop สนับสนุนตัวอักษร Unicode ตลอดจนช่องว่าง (ตัวอักษรว่างเปล่า) ในเส้นทางการติดตั้ง

## <a name="run-r-scripts"></a>เรียกใช้สคริปต์ R
ด้วยเพียงไม่กี่ขั้นตอนใน Power BI Desktop คุณสามารถเรียกใช้สคริปต์ R และสร้างรูปแบบข้อมูล จากนั้นคุณสามารถสร้างรายงาน และแชร์บนบริการ Power BI ต่อไปได้ สคริปต์ R ใน Power BI Desktop ตอนนี้สนับสนุนรูปแบบตัวเลขที่มีจุดทศนิยม (.) และเครื่องหมายจุลภาค (,)

### <a name="prepare-an-r-script"></a>เตรียมสคริปต์ R
เพื่อเรียกใช้สคริปต์ R ใน Power BI Desktop สร้างสคริปต์ R ของคุณในสภาพแวดล้อมการพัฒนา และการตรวจสอบให้แน่ใจว่าการเรียกใช้สำเร็จ

เพื่อเรียกใช้สคริปต์ใน Power BI Desktop ตรวจสอบให้แน่ใจว่าสคริปต์ทำงานสำเร็จในพื้นที่ทำงานที่สร้างขึ้นใหม่และยังไม่ได้เปลี่ยนแปลงอะไร ซึ่งหมายความว่า ทุกแพคเกจและสคริปต์ที่ขึ้นต่อกัน ต้องโหลดและทำงานได้ คุณสามารถใช้ *source()* เพื่อเรียกใช้สคริปต์ที่ขึ้นต่อกันได้

เมื่อเตรียมและเรียกใช้สคริปต์ R ใน Power BI Desktop จะมีข้อจำกัดบางอย่าง:

* เฉพาะข้อมูลเฟรมเท่านั้นที่ถูกนำเข้า ดังนั้นให้แน่ใจว่าข้อมูลที่คุณต้องการนำเข้าไปยัง Power BI อยู่ในรูปเฟรมข้อมูล
* คอลัมน์ที่มีชนิดเป็นจำนวนเชิงซ้อนและเวกเตอร์จะไม่ถูกนำเข้า และจะถูกแทนที่ด้วยค่าผิดพลาดในตารางที่สร้างใหม่
* ค่าที่มีเป็น N/A จะถูกแปลงเป็นค่า NULL ใน Power BI Desktop
* สคริปต์ R ใด ๆ ที่ทำงานนานกว่า 30 นาทีจะหมดเวลา
* การเรียกแบบโต้ตอบในสคริปต์ R เช่นรอให้ผู้ใช้ป้อนข้อมูล จะหยุดการทำงานการของสคริปต์
* เมื่อตั้งค่าไดเรกทอรีการทำงานภายในสคริปต์ R คุณ*ต้อง*กำหนดเส้นทางแบบเต็มไปยังไดเรกทอรีการทำงาน แทนที่จะเป็นเส้นทางสัมพัทธ์

### <a name="run-your-r-script-and-import-data"></a>เรียกใช้สคริปต์ R ของคุณ และนำเข้าข้อมูล
1. ใน Power BI Desktop ตัวเชื่อมต่อข้อมูลสคริปต์ R จะอยู่ใน**รับข้อมูล** เมื่อต้องการเรียกใช้สคริปต์ R ของคุณ เลือก**รับข้อมูล &gt; เพิ่มเติม...**  แล้วเลือก**อื่น ๆ&gt; สคริปต์ R** ดังที่แสดงในรูปต่อไปนี้:
   
   ![](media/desktop-r-scripts/r-scripts-1.png)
2. ถ้าติดตั้ง R ไว้บนเครื่องคอมพิวเตอร์ของคุณ เวอร์ชันที่ติดตั้งล่าสุดจะถูกเลือกเป็นโปรแกรม R ของคุณ เพียงแค่คัดลอกสคริปต์ของคุณลงในหน้าต่างสคริปต์ แล้วเลือก**ตกลง**
   
   ![](media/desktop-r-scripts/r-scripts-2.png)
3. ถ้าไม่ได้ติดตั้ง R, ไม่รู้จัก หรือถ้ามีการติดตั้งหลายชุดบนเครื่องคอมพิวเตอร์ของคุณ ขยาย**การตั้งค่าการติดตั้ง R** เพื่อแสดงตัวเลือกการติดตั้ง หรือเลือกการติดตั้งที่คุณต้องการรันสคริปต์ R
   
   ![](media/desktop-r-scripts/r-scripts-3.png)
   
   ถ้า R ติดตั้งแล้วแต่ไม่รู้จัก คุณสามารถระบุให้ชัดเจนในกล่องข้อความที่ให้มาเมื่อคุณขยาย**การตั้งค่าการติดตั้ง R** ได้ ในรูปภาพด้านบน เส้นทาง *C:\Program Files\R\R-3.2.0* ถูกระบุไว้อย่างชัดเจนในกล่องข้อความ
   
   ค่าการติดตั้ง R จะเก็บไว้ส่วนกลาง ที่ส่วนการเขียน R สคริปต์ ของกล่องโต้ตอบตัวเลือก เพื่อระบุการตั้งค่าการติดตั้ง R เลือก**ไฟล์ > ตัวเลือกและการตั้งค่า** แล้วเลือก**ตัวเลือก > การเขียน R สคริปต์** ถ้ามีการติดตั้ง R หลายชุด จะมีเมนูดรอปดาวน์ให้คุณเลือกการติดตั้งที่จะใช้งาน
   
   ![](media/desktop-r-scripts/r-scripts-4.png)
4. เลือก**ตกลง**เพื่อเรียกใช้สคริปต์ R เมื่อสคริปต์ทำงานเสร็จเรียบร้อย คุณสามารถเลือกเฟรมข้อมูลผลลัพธ์ เพื่อเพิ่มไปยังรูปแบบ Power BI

### <a name="refresh"></a>รีเฟรช
คุณสามารถรีเฟรชสคริปต์ R ใน Power BI Desktop เมื่อคุณรีเฟรชสคริปต์ R, Power BI Desktop เรียกใช้สคริปต์ R อีกครั้งในสภาพแวดล้อมของ Power BI Desktop

## <a name="next-steps"></a>ขั้นตอนถัดไป
ดูข้อมูลเพิ่มเติมเกี่ยวกับ R ใน Power BI

* [สร้างวิชวล R ใน Power BI Desktop](desktop-r-visuals.md)
* [ใช้ R IDE ภายนอกกับ Power BI](desktop-r-ide.md)

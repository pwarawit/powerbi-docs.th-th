---
title: การเรียกใช้สคริปต์ Python ใน Power BI Desktop
description: การเรียกใช้สคริปต์ Python ใน Power BI Desktop
author: otarb
manager: rajatt
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 06/18/2018
ms.author: otarb
LocalizationGroup: Connect to data
ms.openlocfilehash: c7214d67cba58cdcd2e63b194e6c648e614943af
ms.sourcegitcommit: 698b788720282b67d3e22ae5de572b54056f1b6c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/17/2018
ms.locfileid: "45975023"
---
# <a name="run-python-scripts-in-power-bi-desktop"></a>เรียกใช้สคริปต์ Python ใน Power BI Desktop
คุณสามารถเรียกใช้สคริปต์ Python โดยตรงใน **Power BI Desktop** และนำเข้าชุดข้อมูลผลลัพธ์ลงในรูปแบบข้อมูล Power BI Desktop ได้

## <a name="install-python"></a>ติดตั้ง Python
เพื่อเรียกใช้สคริปต์ Python ใน Power BI Desktop คุณจำเป็นต้องติดตั้ง **Python** บนเครื่องคอมพิวเตอร์ของคุณ คุณสามารถดาวน์โหลดและติดตั้ง **Python** ได้ฟรีจากตำแหน่งที่ตั้งต่าง ๆ ซึ่งรวมถึง[หน้าดาวน์โหลด Official Python](https://www.python.org/) และ [Anaconda](https://anaconda.org/anaconda/python/) รุ่นปัจจุบันของการเขียนสคริปต์ Python ในPower BI Desktopสนับสนุนอักขระ Unicode ตลอดจนช่องว่าง (อักขระว่าง) ในเส้นทางการติดตั้ง

## <a name="run-python-scripts"></a>เรียกใช้สคริปต์ Python
ด้วยเพียงไม่กี่ขั้นตอนใน Power BI Desktop คุณสามารถเรียกใช้สคริปต์ Python และสร้างรูปแบบข้อมูล จากนั้นคุณสามารถสร้างรายงาน และแชร์บนบริการ Power BI ต่อไปได้

### <a name="prepare-a-python-script"></a>เตรียมสคริปต์ Python
เพื่อเรียกใช้สคริปต์ Python ใน Power BI Desktop สร้างสคริปต์ Python ของคุณในสภาพแวดล้อมการพัฒนา และการตรวจสอบให้แน่ใจว่าการเรียกใช้สำเร็จ

เพื่อเรียกใช้สคริปต์ใน Power BI Desktop ตรวจสอบให้แน่ใจว่าสคริปต์ทำงานสำเร็จในพื้นที่ทำงานที่สร้างขึ้นใหม่และยังไม่ได้เปลี่ยนแปลงอะไร ซึ่งหมายความว่า ทุกแพคเกจและสคริปต์ที่ขึ้นต่อกัน ต้องโหลดและทำงานได้

เมื่อเตรียมและเรียกใช้สคริปต์ Python ใน Power BI Desktop จะมีข้อจำกัดบางอย่าง:

* นำเข้าเฉพาะเฟรมข้อมูล Pandas เท่านั้นที่ ดังนั้นให้แน่ใจว่าข้อมูลที่คุณต้องการนำเข้าไปยัง Power BI อยู่ในรูปเฟรมข้อมูล
* สคริปต์ Python ใด ๆ ที่ทำงานนานกว่า 30 นาทีจะหมดเวลา
* การเรียกแบบโต้ตอบในสคริปต์ Python เช่น รอให้ผู้ใช้ป้อนข้อมูล จะหยุดการทำงานการของสคริปต์
* เมื่อตั้งค่าไดเรกทอรีการทำงานภายในสคริปต์ Python คุณ*ต้อง*กำหนดเส้นทางแบบเต็มไปยังไดเรกทอรีการทำงาน แทนที่จะเป็นเส้นทางสัมพัทธ์
* ในขณะนี้ไม่รองรับตารางที่ซ้อนกัน (ตารางของตาราง) 

### <a name="run-your-python-script-and-import-data"></a>เรียกใช้สคริปต์ Python ของคุณ และนำเข้าข้อมูล
1. ใน Power BI Desktop ตัวเชื่อมต่อข้อมูลสคริปต์ Python จะอยู่ใน**รับข้อมูล** เมื่อต้องการเรียกใช้สคริปต์ Python ของคุณ เลือก**รับข้อมูล &gt; เพิ่มเติม...** แล้วเลือก**อื่น ๆ&gt; สคริปต์ Python** ดังที่แสดงในรูปต่อไปนี้:
   
   ![](media/desktop-python-scripts/python-scripts-1.png)
2. ถ้าติดตั้ง Python ไว้บนเครื่องคอมพิวเตอร์ของคุณ เวอร์ชันที่ติดตั้งล่าสุดจะถูกเลือกเป็นโปรแกรม Python ของคุณ เพียงแค่คัดลอกสคริปต์ของคุณลงในหน้าต่างสคริปต์ แล้วเลือก**ตกลง**
   
   ![](media/desktop-python-scripts/python-scripts-2.png)
3. ถ้าไม่มีการติดตั้ง Python หรือไม่มีการระบุ หรือถ้ามีการติดตั้งหลายชุดบนเครื่องคอมพิวเตอร์ของคุณ คำเตือนจะปรากฏขึ้น
   
   ![](media/desktop-python-scripts/python-scripts-3.png)
   
   การตั้งค่าการการติดตั้ง Python จะเก็บไว้ส่วนกลางในส่วนการเขียนสคริปต์ Python  ของกล่องโต้ตอบตัวเลือก เพื่อระบุการตั้งค่าการติดตั้ง Python เลือก**ไฟล์ > ตัวเลือกและการตั้งค่า** แล้วเลือก **ตัวเลือก > การเขียนสคริปต์ Python** ถ้ามีการติดตั้ง Python หลายชุด จะมีเมนูดรอปดาวน์ให้คุณเลือกการติดตั้งที่จะใช้งาน นอกจากนี้คุณสามารถเลือก **อื่น ๆ** และกำหนดเส้นทางแบบกำหนดเองได้
   
   ![](media/desktop-python-scripts/python-scripts-4.png)
4. เลือก **ตกลง** เพื่อเรียกใช้สคริปต์ Python เมื่อสคริปต์ทำงานเสร็จเรียบร้อย คุณสามารถเลือกเฟรมข้อมูลผลลัพธ์ เพื่อเพิ่มไปยังรูปแบบ Power BI

### <a name="refresh"></a>รีเฟรช
คุณสามารถรีเฟรชสคริปต์ Python ใน Power BI Desktop เมื่อคุณรีเฟรชสคริปต์ Python แล้ว Power BI Desktop จะเรียกใช้สคริปต์ Python อีกครั้งในสภาพแวดล้อมของ Power BI Desktop

## <a name="next-steps"></a>ขั้นตอนถัดไป
ดูข้อมูลเพิ่มเติมเกี่ยวกับ Python ใน Power BI ต่อไปนี้

* [สร้างวิชวล Python ใน Power BI Desktop](desktop-python-visuals.md)
* [ใช้ Python IDE ภายนอกกับ Power BI](desktop-python-ide.md)
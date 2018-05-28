---
title: 'ข้อผิดพลาด: เราไม่พบข้อมูลใด ๆ ในสมุดงาน Excel ของคุณ'
description: 'ข้อผิดพลาด: เราไม่พบข้อมูลใด ๆ ในสมุดงาน Excel ของคุณ'
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
LocalizationGroup: Troubleshooting
ms.openlocfilehash: a58af88d23c04c0afd2fa71cab7824b657451b33
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
---
# <a name="error-we-couldnt-find-any-data-in-your-excel-workbook"></a>ข้อผิดพลาด: เราไม่พบข้อมูลใด ๆ ในสมุดงาน Excel ของคุณ

>[!NOTE]
>บทความนี้นำไปใช้กับ Excel 2007 และเวอร์ชันที่ใหม่กว่า

เมื่อคุณนำเข้าสมุดงาน Excel ไปใน Power BI คุณอาจเห็นข้อผิดพลาดต่อไปนี้:

*ข้อผิดพลาด: เราไม่พบข้อมูลใด ๆ ในสมุดงาน Excel ของคุณ ข้อมูลของคุณอาจไม่ถูกจัดรูปแบบอย่างถูกต้อง คุณจำเป็นต้องแก้ไขสมุดงานของคุณใน Excel จากนั้นนำเข้าอีกครั้ง*

![](media/service-admin-troubleshoot-excel-workbook-data/pbi_wecouldntfindanydata.png)

## <a name="quick-solution"></a>แก้ไขปัญหาอย่างรวดเร็ว
1. แก้ไขมุดงานใน Excel
2. เลือกช่วงของเซลล์ที่มีข้อมูลของคุณ แถวแรกควรประกอบด้วยส่วนหัวของคอลัมน์ (ชื่อคอลัมน์)
3. กด**Ctrl + T**เพื่อสร้างตาราง
4. บันทึกสมุดงานของคุณ
5. กลับไปยัง Power BI และนำเข้าสมุดงานของคุณอีกครั้ง หรือถ้าคุณกำลังทำงานใน Excel 2016 และคุณได้บันทึกสมุดงานของคุณไปยัง OneDrive for Business ใน Excel ให้คลิกไฟล์ > เผยแพร่

## <a name="details"></a>รายละเอียด
### <a name="cause"></a>สาเหตุ
ใน Excel คุณสามารถสร้า**ตาราง**นอกช่วงของเซลล์ได้ ซึ่งทำให้ง่ายขึ้นเมื่อต้องการเรียงลำดับ กรอง และจัดรูปแบบข้อมูล

เมื่อคุณนำเข้าสมุดงาน Excel, Power BI จะค้นหาตารางเหล่านี้และนำเข้าในชุดข้อมูลหนึ่ง ถ้าไม่พบตารางใด คุณจะเห็นข้อความข้อผิดพลาดนี้

### <a name="solution"></a>วิธีแก้
1. เปิดสมุดงานของคุณใน Excel 
    >[!NOTE]
    >รูปภาพต่อไปนี้เป็นภาพของ Excel 2013 ถ้าคุณกำลังใช้เวอร์ชันอื่น องค์ประกอบต่าง ๆ อาจแตกต่างกันเล็กน้อย แต่ขั้นตอนต่าง ๆ จะเหมือนกัน
    
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht1.png)
2. เลือกช่วงของเซลล์ที่มีข้อมูลของคุณ แถวแรกควรประกอบด้วยส่วนหัวของคอลัมน์ (ชื่อคอลัมน์)
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht2.png)
3. ใน Ribbon บนแถบ**แทรก** คลิก**ตาราง** (หรือโดยการใช้ทางลัด กด**Ctrl + T**)
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht3.png)
4. คุณจะเห็นกล่องโต้ตอบต่อไปนี้ ตรวจสอบให้แน่ใจว่าได้เลือก**ตารางของฉันมีส่วนหัว** และเลือก**ตกลง**:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlcreatetbl.png)
5. ในตอนนี้ ข้อมูลของคุณถูกจัดรูปแบบเป็นตาราง:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xltbl.png)
6. บันทึกสมุดงานของคุณ
7. กลับไปยัง Power BI เลือกรับข้อมูลที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_getdata.png)
8. ในกล่อง**ไฟล์** เลือก**รับ**
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_getfiles.png)
9. นำเข้าสมุดงาน Excel ของคุณอีกครั้ง ขณะนี้ การนำเข้าควรพบตารางและดำเนินการสำเร็จ
   
    ถ้าการนำเข้ายังคงล้มเหลว แจ้งให้เราทราบโดยการคลิก ** ชุมชน ** ในเมนูช่วยเหลือ:
   
    ![](media/service-admin-troubleshoot-excel-workbook-data/pbi_questionmenucommunity.png)

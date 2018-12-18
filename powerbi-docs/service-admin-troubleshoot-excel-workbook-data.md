---
title: 'ข้อผิดพลาด: เราไม่พบข้อมูลใด ๆ ในสมุดงาน Excel ของคุณ'
description: 'ข้อผิดพลาด: เราไม่พบข้อมูลใด ๆ ในสมุดงาน Excel ของคุณ'
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: ea5312178d33986ebc3f4b9e8610012c87d54216
ms.sourcegitcommit: 72c9d9ec26e17e94fccb9c5a24301028cebcdeb5
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/07/2018
ms.locfileid: "53026042"
---
# <a name="error-we-couldnt-find-any-data-in-your-excel-workbook"></a>ข้อผิดพลาด: เราไม่พบข้อมูลใด ๆ ในสมุดงาน Excel ของคุณ

>[!NOTE]
>บทความนี้นำไปใช้กับ Excel 2007 และเวอร์ชันที่ใหม่กว่า

เมื่อคุณนำเข้าสมุดงาน Excel ไปใน Power BI คุณอาจเห็นข้อผิดพลาดต่อไปนี้:

*ข้อผิดพลาด: เราไม่พบข้อมูลใด ๆ ในสมุดงาน Excel ของคุณ ข้อมูลของคุณอาจไม่ถูกจัดรูปแบบอย่างถูกต้อง คุณจำเป็นต้องแก้ไขสมุดงานของคุณใน Excel จากนั้นนำเข้าอีกครั้ง*

![ไม่พบข้อมูลในสมุดงาน](media/service-admin-troubleshoot-excel-workbook-data/pbi_wecouldntfindanydata.png)

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
    
    ![เปิดเวิร์กบุ๊ก](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht1.png)
2. เลือกช่วงของเซลล์ที่มีข้อมูลของคุณ แถวแรกควรประกอบด้วยส่วนหัวของคอลัมน์ (ชื่อคอลัมน์)
   
    ![เลือกช่วงของเซลล์](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht2.png)
3. ใน Ribbon บนแถบ**แทรก** คลิก**ตาราง** (หรือโดยการใช้ทางลัด กด**Ctrl + T**)
   
    ![ใส่ตาราง](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlwksht3.png)
4. คุณจะเห็นกล่องโต้ตอบต่อไปนี้ ตรวจสอบให้แน่ใจว่าได้เลือก**ตารางของฉันมีส่วนหัว** และเลือก**ตกลง**:
   
    ![สร้างตาราง](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xlcreatetbl.png)
5. ในตอนนี้ ข้อมูลของคุณถูกจัดรูปแบบเป็นตาราง:
   
    ![ข้อมูลที่จัดรูปแบบเป็นตาราง](media/service-admin-troubleshoot-excel-workbook-data/pbi_trb_xltbl.png)
6. บันทึกสมุดงานของคุณ
7. กลับไปยัง Power BI เลือกรับข้อมูลที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
    ![รับข้อมูล](media/service-admin-troubleshoot-excel-workbook-data/pbi_getdata.png)
8. ในกล่อง**ไฟล์** เลือก**รับ**
   
    ![รับไฟล์](media/service-admin-troubleshoot-excel-workbook-data/pbi_getfiles.png)
9. นำเข้าสมุดงาน Excel ของคุณอีกครั้ง ขณะนี้ การนำเข้าควรพบตารางและดำเนินการสำเร็จ
   
    ถ้าการนำเข้ายังคงล้มเหลว แจ้งให้เราทราบโดยการคลิก ** ชุมชน ** ในเมนูช่วยเหลือ:
   
    ![ลิงก์ไปยังกลุ่มชุมชน](media/service-admin-troubleshoot-excel-workbook-data/pbi_questionmenucommunity.png)

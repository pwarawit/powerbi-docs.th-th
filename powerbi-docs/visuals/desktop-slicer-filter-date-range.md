---
title: ใช้ตัวแบ่งส่วนข้อมูลหรือตัวกรองวันที่แบบสัมพัทธ์ใน Power BI Desktop
description: เรียนรู้วิธีการใช้ตัวแบ่งส่วนข้อมูลหรือตัวกรองเพื่อจำกัดช่วงวันที่ที่สัมพันธ์ใน Power BI Desktop
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 692d752756590945eb17e2f512929f7303727e94
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/22/2018
ms.locfileid: "46564819"
---
# <a name="use-a-relative-date-slicer-and-filter-in-power-bi-desktop"></a>ใช้ตัวแบ่งส่วนข้อมูลและตัวกรองวันที่แบบสัมพัทธ์ใน Power BI Desktop
ด้วย**ตัวแบ่งส่วนข้อมูลวันที่ที่สัมพันธ์**หรือ**ตัวกรองวันที่ี่ที่สัมพันธ์** คุณสามารถใช้ตัวกรองที่ยึดตามเวลากับคอลัมน์วันที่ใดก็ตามในแบบจำลองข้อมูลของคุณได้ ตัวอย่างเช่น คุณสามารถใช้**ตัวแบ่งส่วนข้อมูลวันที่ที่เกี่ยวข้อง**เพื่อแสดงข้อมูลยอดขายเฉพาะที่เกิดขึ้นภายใน 30 วันที่ผ่านมา (หรือ เดือน, เดือนตามปฏิทิน ฯลฯ) ได้ และเมื่อคุณรีเฟรชข้อมูล ช่วงเวลาสัมพัทธ์จะถูกปรับให้ใช้วันที่ที่เหมาะสมโดยอัตโนมัติ

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_01.png)

## <a name="using-the-relative-date-range-slicer"></a>การใช้ตัวแบ่งส่วนข้อมูลช่วงวันที่ที่สัมพันธ์
คุณสามารถใช้ตัวแบ่งส่วนข้อมูลวันที่ที่สัมพันธ์ได้เช่นเดียวกับตัวแบ่งส่วนข้อมูลอื่น ๆ เพียงแค่สร้างวิชวล**ตัวแบ่งส่วนข้อมูล**สำหรับรายงานของคุณ จากนั้นเลือกค่าวันที่สำหรับค่า**เขตข้อมูล** ในรูปต่อไปนี้ จะมีการเลือกช่องข้อมูล*OrderDate*

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_02.png)

เลือกกะรัตที่มุมบนขวาของ**ตัวแบ่งส่วนข้อมูลวันที่ที่สัมพันธ์**และเมนูจะปรากฏขึ้น

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_03.png)

ตัวแบ่งส่วนข้อมูลวันที่ที่สัมพันธ์ เลือก*สัมพันธ์*

จากนั้นคุณสามารถเลือกการตั้งค่าดังกล่าวได้ สำหรับรายการดรอปดาวน์แรกใน*ตัวแบ่งส่วนข้อมูลวันที่ที่เกี่ยวข้อง* คุณมีตัวเลือกต่อไปนี้:

* สุดท้าย
* ถัดไป
* นี้

ตัวเลือกเหล่านี้จะแสดงในรูปต่อไปนี้

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_04.png)

การตั้งค่า (ตรงกลาง) ถัดไปใน*ตัวแบ่งส่วนข้อมูลวันที่ที่เกี่ยวข้อง* ให้คุณสามารถพิมพ์ตัวเลขเพื่อกำหนดช่วงวันที่สัมพัทธ์ได้

การตั้งค่าที่สาม ให้คุณเลือกหน่วยวัดวันที่ คุณมีตัวเลือกต่อไปนี้:

* วัน
* สัปดาห์
* สัปดาห์ (ปฏิทิน)
* เดือน
* เดือน (ปฏิทิน)
* ปี
* ปี (ปฏิทิน)

ตัวเลือกเหล่านี้จะแสดงในรูปต่อไปนี้

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_05.png)

ถ้าคุณเลือก*เดือน*จากรายการ และป้อน 2 ในการตั้งค่าตรงกลาง สิ่งต่อไปนี้จะเกิดขึ้น: ถ้าวันนี้คือวันที่ 20 กรกฎาคม ข้อมูลที่รวมอยู่ในวิชวลที่จำกัดโดยตัวแบ่งส่วนข้อมูล จะแสดงข้อมูลของสองเดือนก่อนหน้านี้ เริ่มตั้งแต่วันที่ 20 พฤษภาคมจนถึงวันที่ 20 กรกฎาคม (วันที่ของวันนี้)

ในการเปรียบเทียบ ถ้าคุณเลือก*เดือน (ปฏิทิน)* ภาพที่จำกัดจะแสดงข้อมูลจากวันที่ 1 พฤษภาคมถึงวันที่ 30 มิถุนายน (สองเดือนเต็มตามเดือนในปฏิทิน)

## <a name="using-the-relative-date-range-filter"></a>การใช้ตัวกรองข้อมูลช่วงวันที่ที่สัมพันธ์
คุณยังสามารถสร้างตัวกรองช่วงวันที่สัมพัทธ์สำหรับหน้ารายงานของคุณ หรือทั้งรายงานของคุณได้ ใการทำเช่นนั้น เพียงแค่ลากเขตข้อมูลวันที่ไปยังพื้นที่**ตัวกรองระดับหน้า**หรือ**ตัวกรองระดับรายงาน**ในพื้นที่**เขตข้อมูล** ดังที่แสดงในรูปต่อไปนี้

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_06.png)

เมื่ออยู่ที่นั่นแล้ว คุณสามารถปรับเปลี่ยนช่วงวันที่สัมพัทธ์ในแบบเดียวกับวิธีการกำหนด**ตัวแบ่งส่วนข้อมูลวันที่ที่เกี่ยวข้อง**เอง เลือก**กรองข้อมูลวันที่ที่สัมพันธ์** จากดรอปดาวน์**ชนิดตัวกรอง**

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_07.png)

เมื่อเลือก**กรองข้อมูลวันที่ที่สัมพันธ์**แล้ว คุณจะเห็นสามส่วนสำหรับการปรับเปลี่ยน ซึ่งรวมถึงกล่องตัวเลขตรงกลาง เช่นเดียวกับตัวแบ่งส่วนข้อมูล

![](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter_08.png)

และนั่นคือทั้งหมด สำหรับการใช้ข้อจำกัดวันที่ที่สัมพัทธ์ในรายงานของคุณ

## <a name="limitations-and-considerations"></a>ข้อจำกัดและข้อควรพิจารณา
ในขณะนี้ ข้อจำกัดและข้อควรพิจารณาดังต่อไปนี้นำไปใช้กับ**ตัวแบ่งส่วนข้อมูลช่วงวันที่ที่สัมพันธ์**และตัวกรอง

* ข้อมูลแบบจำลองใน**Power BI**จะไม่รวมข้อมูลโซนเวลา แบบจำลองสามารถจัดเก็บเวลาต่าง ๆ ได้ แต่จะไม่มีการระบุโซนเวลาที่แบบจำลองดังกล่าวอยู่
* ตัวแบ่งส่วนข้อมูลและตัวกรองจะยึดตามเวลาใน UTC เสมอ ดังนั้น ถ้าคุณกำหนดค่าตัวกรองในรายงานและส่งไปยังเพื่อนร่วมงานในโซนเวลาอื่น คุณและเพื่อนร่วมงานจะเห็นข้อมูลเดียวกัน แต่ถ้าคุณไม่ได้อยู่ในโซนเวลา UTC คุณอาจเห็นข้อมูลที่เวลาผิดจากที่คุณคาดหมาย
* ข้อมูลที่รวบรวมไว้ในโซนเวลาท้องถิ่นสามารถแปลงเป็น UTC ได้โดยใช้**ตัวแก้ไขการสอบถาม (คิวรี่)**

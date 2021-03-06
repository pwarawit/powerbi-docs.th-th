---
title: ใช้ตัวแบ่งส่วนข้อมูลหรือตัวกรองวันที่แบบสัมพัทธ์ใน Power BI
description: เรียนรู้วิธีการใช้ตัวแบ่งส่วนข้อมูลหรือตัวกรองเพื่อจำกัดช่วงวันที่ที่สัมพันธ์ใน Power BI
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/05/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 5d50f6dc1f1671ae8eb6695d9d39443367dfc20e
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85233451"
---
# <a name="creating-a-relative-date-slicer-and-filter-in-power-bi"></a>การสร้างตัวแบ่งส่วนและตัวกรองวันที่แบบสัมพัทธ์ใน Power BI

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]

ด้วย**ตัวแบ่งส่วนข้อมูลวันที่ที่สัมพันธ์**หรือ**ตัวกรองวันที่ี่ที่สัมพันธ์** คุณสามารถใช้ตัวกรองที่ยึดตามเวลากับคอลัมน์วันที่ใดก็ตามในแบบจำลองข้อมูลของคุณได้ ตัวอย่างเช่น คุณสามารถใช้**ตัวแบ่งส่วนข้อมูลวันที่ที่เกี่ยวข้อง**เพื่อแสดงข้อมูลยอดขายเฉพาะที่เกิดขึ้นภายใน 30 วันที่ผ่านมา (หรือ เดือน, เดือนตามปฏิทิน ฯลฯ) ได้ เมื่อคุณรีเฟรชข้อมูล ช่วงเวลาสัมพัทธ์จะถูกปรับให้ใช้วันที่ที่เหมาะสมโดยอัตโนมัติ

![ภาพหน้าจอของรายงานที่มีลูกศรชี้ไปยังตัวแบ่งส่วนวันที่แบบสัมพันธ์กัน](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-01.png)

หากต้องการแชร์รายงานของคุณกับผู้ร่วมงาน Power BI คุณจะต้องมีสิทธิ์การใช้งาน Power BI Pro แต่ละรายการ หรือรายงานจะถูกบันทึกในความจุแบบพรีเมียม

## <a name="create-the-relative-date-range-slicer"></a>ใช้ตัวแบ่งส่วนช่วงวันที่แบบสัมพัทธ์

คุณสามารถใช้ตัวแบ่งส่วนข้อมูลวันที่ที่สัมพันธ์ได้เช่นเดียวกับตัวแบ่งส่วนข้อมูลอื่น ๆ สร้างวิชวล**ตัวแบ่งส่วนข้อมูล**สำหรับรายงานของคุณ จากนั้นเลือกค่าวันที่สำหรับค่า**เขตข้อมูล** ในรูปต่อไปนี้ เราได้เลือกเขตข้อมูล *OrderDate*

![สกรีนช็อตของบานหน้าต่างการแสดงภาพที่มีลูกศรชี้ไปที่ไอคอนวิชวลตัวแบ่งส่วนข้อมูลและเขตข้อมูลด้วย](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-02.png)

เลือกตัวแบ่งส่วนข้อมูลบนพื้นที่ทำงานของคุณ และกะรัตที่มุมบนด้านขวาของวิชวลตัวแบ่งส่วนข้อมูล หากวิชวลนี้มีข้อมูลวันที่ เมนูจะแสดงตัวเลือกสำหรับ **สัมพัทธ์**

![สกรีนช็อตของวิชวลตัวแบ่งส่วนข้อมูลที่มีการเรียกออกไปรอบ ๆ กะรัตและลูกศรชี้ไปที่สัมพัทธ์](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-03.png)

ตัวแบ่งส่วนข้อมูลวันที่ที่สัมพันธ์ เลือก*สัมพันธ์*

จากนั้นคุณสามารถเลือกการตั้งค่าดังกล่าวได้

สำหรับการตั้งค่าครั้งแรกใน*ตัวแบ่งส่วนข้อมูลวันที่ที่สัมพัทธ์* คุณมีตัวเลือกต่อไปนี้:

![สกรีนช็อตของตัวเลือกการกำหนดค่าที่สัมพัทธ์กับการตั้งค่าครั้งแรกที่เรียกออก](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-04.png)

* สุดท้าย

* ถัดไป

* นี้

การตั้งค่าครั้งที่สอง (ตรงกลาง) ใน*ตัวแบ่งส่วนข้อมูลวันที่ที่สัมพัทธ์* ให้คุณสามารถระบุตัวเลขเพื่อกำหนดช่วงวันที่สัมพัทธ์ได้

![สกรีนช็อตของตัวเลือกการกำหนดค่าที่สัมพัทธ์กับการตั้งค่าครั้งที่สองที่เรียกออก](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-04a.png)

การตั้งค่าที่สาม ให้คุณเลือกหน่วยวัดวันที่ คุณมีตัวเลือกต่อไปนี้:

![สกรีนช็อตของตัวเลือกการกำหนดค่าที่สัมพัทธ์กับการตั้งค่าครั้งที่สามที่เรียกออก](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-05.png)

* วัน

* สัปดาห์

* สัปดาห์ (ปฏิทิน)

* เดือน

* เดือน (ปฏิทิน)

* ปี

* ปี (ปฏิทิน)

หากคุณเลือก**เดือน**จากรายการ และป้อนตัวเลข *2* ในการตั้งค่าตรงกลาง นี่คือสิ่งที่จะเกิดขึ้น:

* ถ้าวันนี้คือวันที่ 20 กรกฎาคม

* ข้อมูลที่รวมอยู่ในวิชวลที่จำกัดโดยตัวแบ่งส่วนข้อมูลจะแสดงข้อมูลสองเดือนก่อนหน้านี้

* เริ่มจากวันที่ 21 พฤษภาคมและไปจนถึงวันที่ 20 กรกฎาคม (วันที่ของวันนี้)

ในการเปรียบเทียบ ถ้าคุณเลือก*เดือน (ปฏิทิน)* วิชวลที่จำกัดจะแสดงข้อมูลจากวันที่ 1 พฤษภาคมถึงวันที่ 30 มิถุนายน (สองเดือนเต็มตามเดือนในปฏิทิน)

## <a name="create-the-relative-date-range-filter"></a>สร้างตัวกรองข้อมูลช่วงวันที่แบบสัมพัทธ์

คุณยังสามารถสร้างตัวกรองช่วงวันที่สัมพัทธ์สำหรับหน้ารายงานของคุณ หรือทั้งรายงานของคุณได้ ในการทำเช่นนั้น ให้่ลากเขตข้อมูลวันที่ไปยังแหล่งข้อมูล **ตัวกรองระดับหน้า**หรือแหล่งข้อมูล **ตัวกรองระดับรายงาน**ในบานหน้าต่าง**เขตข้อมูล**:

![สกรีนช็อตของเขตข้อมูล OrderDate ที่ถูกลากไปยังแหล่งข้อมูลตัวกรองระดับหน้า](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-06.png)

เมื่อมี คุณสามารถเปลี่ยนช่วงวันที่ที่สัมพัทธ์ ซึ่งคล้ายกับวิธีการที่คุณสามารถกำหนด **ตัวแบ่งส่วนข้อมูลวันที่ที่สัมพันธ์** เอง เลือก**กรองข้อมูลวันที่ที่สัมพันธ์** จากดรอปดาวน์**ชนิดตัวกรอง**

![สกรีนช็อตที่แสดงรายการดรอปดาวน์ของชนิดตัวกรองและตัวชี้เมาส์บนการกรองข้อมูลวันที่ที่สัมพัทธ์](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-07.png)

เมื่อคุณเลือก**การกรองข้อมูลวันที่ที่สัมพัทธ์**แล้ว คุณจะเห็นสามส่วนที่จะเปลี่ยน ซึ่งรวมถึงกล่องตัวเลขตรงกลาง เช่นเดียวกับตัวแบ่งส่วนข้อมูล

![สกรีนช็อตของตัวกรองระดับรายงานมีลูกศรชี้ไปที่แสดงรายการเมื่อมีตัวเลือกค่า](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-08.png)

## <a name="limitations-and-considerations"></a>ข้อจำกัดและข้อควรพิจารณา

ในขณะนี้ ข้อจำกัดและข้อควรพิจารณาดังต่อไปนี้นำไปใช้กับ**ตัวแบ่งส่วนข้อมูลช่วงวันที่ที่สัมพันธ์**และตัวกรอง

* แบบจำลองข้อมูลใน**Power BI**จะไม่รวมข้อมูลโซนเวลา แบบจำลองสามารถจัดเก็บเวลาต่าง ๆ ได้ แต่จะไม่มีการระบุโซนเวลาที่แบบจำลองดังกล่าวอยู่

* ตัวแบ่งส่วนข้อมูลและตัวกรองจะยึดตามเวลาใน UTC หากคุณตั้งค่าตัวกรองในรายงาน และส่งไปยังเพื่อนร่วมงานในโซนเวลาอื่น คุณทั้งสองคนจะเห็นข้อมูลเดียวกัน หากคุณไม่ได้อยู่ในโซนเวลามาตรฐานสากล คุณและเพื่อนร่วมงานของคุณต้องคำนึงถึงการเผื่อเวลาทจะเกิดขึ้นกับคุณ

* คุณสามารถแปลงข้อมูลที่รวบรวมไว้ในโซนเวลาท้องถิ่นเป็น UTC ได้โดยใช้**ตัวแก้ไขการสอบถาม**

## <a name="next-steps"></a>ขั้นตอนถัดไป

- [ใช้ตัวแบ่งส่วนและตัวกรองวันที่แบบสัมพัทธ์ใน Power BI](desktop-slicer-filter-date-range.md)
- [ตัวแบ่งส่วนข้อมูลใน Power BI](power-bi-visualization-slicers.md)

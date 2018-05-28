---
title: ใช้พารามิเตอร์ What if (เกิดอะไรขึ้นถ้า) เพื่อแสดงภาพตัวแปรใน Power BI Desktop
description: สร้างตัวแปร What if ของคุณเองเพื่อสร้างภาพและแสดงตัวแปรใน Power BI
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
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 5222b6ba99c9e61d1070f66115b90aa29099fd8d
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
---
# <a name="create-and-use-a-what-if-parameter-to-visualize-variables-in-power-bi-desktop"></a>สร้างและใช้พารามิเตอร์ What if (ถ้า) เพื่อแสดงภาพตัวแปรใน Power BI Desktop
เริ่มต้นเมื่อสิงหาคม 2017 สำหรับ**Power BI Desktop** ที่คุณจะสามารถสร้างตัวแปร **What if (เกิดอะไรขึ้นถ้า)** สำหรับรายงานของคุณ โต้ตอบกับตัวแปรในฐานะเป็นตัวแบ่งส่วนข้อมูล จากนั้นแสดงข้อมูลเป็นภาพและกำหนดปริมาณค่าที่สำคัญต่าง ๆ ในรายงานของคุณ

![](media/desktop-what-if/what-if_01.png)

พารามิเตอร์**What if**จะพบในแท็บ**การสร้างแบบจำลอง**ใน**Power BI Desktop** เมื่อคุณทำขั้นตอนนั้น กล่องโต้ตอบจะปรากฏขึ้น ซึ่งคุณสามารถกำหนดค่าพารามิเตอร์ได้

## <a name="creating-a-what-if-parameter"></a>การสร้างพารามิเตอร์ What if
เมื่อต้องสร้างพารามิเตอร์**What if (เกิดอะไรขึ้นถ้า)** เลือกปุ่ม**What if**จากแท็บ**การสร้างแบบจำลอง**ใน**Power BI Desktop** ในรูปต่อไปนี้ เราได้สร้างพารามิเตอร์ที่เรียกว่า*เปอร์เซ็นต์ส่วนลด*และตั้งค่าชนิดข้อมูลเป็น*เลขทศนิยม* ค่า*ต่ำสุด*เป็นศูนย์ ค่า*สูงสุด*คือ 0.50 (ห้าสิบเปอร์เซ็นต์) นอกจากนี้ เรายังได้ตั้งค่า*ส่วนเพิ่ม*เป็น 0.05 หรือห้าเปอร์เซ็นต์ นั่นคือจำนวนที่พารามิเตอร์จะปรับเปลี่ยนเมื่อมีการโต้ตอบในรายงาน

![](media/desktop-what-if/what-if_02.png)

> [!NOTE]
> สำหรับตัวเลขทศนิยม ตรวจสอบให้แน่ใจว่าคุณเติมข้างหน้าด้วยศูนย์ เป็น 0.50 แทนที่จะเป็น .50 ในกล่องนั้น มิฉะนั้น ระบบจะไม่ตรวจสอบตัวเลขดังกล่าวและจะไม่สามารถเลือกปุ่ม**ตกลง**ได้
> 
> 

เพื่อความสะดวกของคุณ กล่อง**เพิ่มตัวแบ่งส่วนข้อมูลไปยังหน้านี้**จะวางตัวแบ่งส่วนข้อมูลและพารามิเตอร์**What if (เกิดอะไรขึ้นถ้า)** ลงบนหน้ารายงานปัจจุบันโดยอัตโนมัติ

![](media/desktop-what-if/what-if_03.png)

นอกจากการสร้างพารามิเตอร์แล้ว การสร้างพารามิเตอร์**What if (เกิดอะไรขึ้นถ้า)** จะสร้างหน่วยวัดด้วย ซึ่งคุณสามารถใช้เพื่อแสดงค่าปัจจุบันของ พารามิเตอร์**What if**ได้

![](media/desktop-what-if/what-if_04.png)

การทราบว่าเมื่อคุณสร้างพารามิเตอร์What if**ขึ้น ทั้งพารามิเตอร์และหน่วยวัดจะกลายเป็นส่วนหนึ่งของแบบจำลองของคุณนั้นเป็นสิ่งสำคัญและเป็นประโยชน์ ซึ่งจะพร้อมใช้งานตลอดทั้งรายงาน และสามารถใช้ได้บนหน้ารายงานอื่น ๆ ด้วย และเนื่องจากเป็นส่วนหนึ่งของแบบจำลอง คุณสามารถลบตัวแบ่งส่วนข้อมูลจากหน้ารายงานได้ และถ้าคุณต้องการย้อนกลับ เพียงแค่จับที่พารามิเตอร์ **What if** จากรายการ**เขตข้อมูล**และลากไปที่พื้นที่รายงาน (จากนั้นเปลี่ยนภาพเป็นตัวแบ่งส่วนข้อมูล) เพื่อให้พารามิเตอร์**What if**กลับมายังรายงานของคุณอย่างง่ายดาย

## <a name="using-a-what-if-parameter"></a>ใช้พารามิเตอร์ What If
เรามาสร้างตัวอย่างง่าย ๆ ของการใช้พารามิเตอร์**What if**กัน เราได้สร้างพารามิเตอร์**What if**ในส่วนก่อนหน้านี้ ขณะนี้เราจะนำมาใช้โดยการสร้างหน่วยวัดใหม่ที่ใช้แถบเลื่อนในการปรับค่า ในการทำขั้นตอนนี้ เราจะสร้างหนึ่งหน่วยวัดใหม่

![](media/desktop-what-if/what-if_05.png)

หน่วยวัดใหม่ดังกล่าวจะเป็นยอดขายรวมที่มีการนำอัตราส่วนลดมาใช้ คุณสามารถสร้างหน่วยวัดที่มีความซับซ้อนและน่าสนใจได้ แน่นอนว่านั่นช่วยให้ผู้ใช้รายงานของคุณสร้างภาพตัวแปรของพารามิิเตอร์**What if**ของคุณได้ ตัวอย่างเช่น คุณสามารถสร้างรายงานที่ทำให้ผู้ขายเห็นค่าตอบแทนของตนถ้าสามารถขายได้ตรงตามเป้าหมายหรือเปอร์เซ็นต์ยอดขายที่ตั้งไว้ หรือดูผลกระทบต่อการขายที่เพิ่มขึ้นเมื่อส่วนลดเพิ่มมากขึ้น

เมื่อเราพิมพ์สูตรหน่วยวัดลงในแถบสูตร และตั้งชื่อเป็น**ยอดขายหลังจากส่วนลด** เราเห็นผลลัพธ์ดังนี้:

![](media/desktop-what-if/what-if_06.png)

จากนั้นเราสร้างภาพคอลัมน์หนึ่งขึ้นด้วย*OrderDate*บนแกน โดยที่ทั้ง*SalesAmount*และหน่วยวัดที่เพิ่งสร้างขึ้นนั่นคือ *ยอดขายหลังจากส่วนลด* จะเป็นค่าบนแกน

![](media/desktop-what-if/what-if_07.png)

จากนั้น เมื่อเราเลื่อนแถบเลื่อน เราจะเห็นว่าคอลัมน์*ยอดขายหลังจากส่วนลด*แสดงปริมาณยอดขายหลังหักส่วนลด

![](media/desktop-what-if/what-if_08.png)

และมีแค่นั้น คุณสามารถใช้พารามิเตอร์**What if**ได้ในทุกสถานการณ์ เพื่อให้ผู้ใช้รายงานสามารถโต้ตอบในสถานการณ์สมมติที่หลากหลายที่คุณสร้างในรายงานของคุณได้

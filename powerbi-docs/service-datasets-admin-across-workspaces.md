---
title: ควบคุมการใช้ชุดข้อมูลทั้งพื้นที่ทำงาน (ดูตัวอย่าง) - Power BI
description: เรียนรู้วิธีการจำกัดการไหลของข้อมูลในผู้เช่า Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/31/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 363bf9b107722b3993ed7ac43138c73da03f410a
ms.sourcegitcommit: 7c426a5209d4fdd1360fc3d0442d57991be1984d
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/03/2019
ms.locfileid: "66461798"
---
# <a name="control-the-use-of-datasets-across-workspaces-preview"></a>ควบคุมการใช้ชุดข้อมูลทั้งพื้นที่ทำงาน (ดูตัวอย่าง)

การใช้ชุดข้อมูลทั้งพื้นที่ทำงานเป็นวิธีมีประสิทธิภาพเพื่อส่งเสริมวัฒนธรรมการเก็บข้อมูลและการพัฒนาข้อมูลให้เป็นระบบภายในองค์กร ถ้าคุณเป็นผู้ดูแลระบบ Power BI ในบางครั้งคุณต้องการจำกัดการไหลของข้อมูลภายในผู้เช่า Power BI ด้วยการตั้งค่าผู้เช่า **ใช้ชุดข้อมูลทั้งพื้นที่ทำงาน** คุณสามารถจำกัดการใช้ชุดข้อมูลซ้ำ ไม่ว่าจะทั้งหมดหรือบางส่วนต่อกลุ่มความปลอดภัยได้

![การตั้งค่าพื้นที่ทำงานของผู้ดูแลระบบ Power BI](media/service-datasets-admin-across-workspaces/power-bi-admin-workspace-settings.png)

หากคุณปิดการตั้งค่านี้ จะมีผลกระทบต่อผู้สร้างรายงาน:

- ปุ่มคัดลอกรายงานทั้งพื้นที่ทำงานไม่พร้อมใช้งาน 
- ในรายงานที่ยึดตามชุดข้อมูลที่ใช้ร่วมกัน ปุ่ม**แก้ไขรายงาน**ไม่พร้อมใช้งาน
- ในบริการของ Power BI ประสบการณ์การค้นหาจะแสดงเฉพาะชุดข้อมูลในพื้นที่ทำงานปัจจุบันเท่านั้น
- ใน Power BI Desktop ประสบการณ์การค้นหาจะแสดงเฉพาะชุดข้อมูลจากพื้นที่ทำงานที่คุณเป็นสมาชิกเท่านั้น
- ใน Power BI Desktop ถ้าผู้ใช้เปิดไฟล์.pbix ด้วยการเชื่อมต่อสดไปยังชุดข้อมูลที่อยู่นอกพื้นที่ทำงานใด ๆ ที่ผู้ใช้เป็นสมาชิกของ พวกเขาจะเห็นข้อความแสดงข้อผิดพลาด ซึ่งขอให้พวกเขาเชื่อมต่อกับชุดข้อมูลอื่น

## <a name="provide-a-link-for-the-certification-process"></a>มีลิงก์สำหรับกระบวนการออกใบรับรอง

ในฐานะผู้ดูแลระบบผู้เช่า คุณสามารถใส่ URL สำหรับลิงก์**การเรียนรู้เพิ่มเติม** บนหน้าการตั้งค่า**การรับรอง**ได้  ลิงก์นี้สามารถไปที่เอกสารประกอบเกี่ยวกับกระบวนการออกใบรับรองของคุณ ถ้าคุณไม่มีปลายทางสำหรับลิงก์**การเรียนรู้เพิ่มเติม** ตามค่าเริ่มต้นจะลิงก์ไปยังบทความ[ใบรับรองชุดข้อมูล](service-datasets-certify.md)

![เรียนรู้เพิ่มเติมเกี่ยวกับใบรับรองชุดข้อมูล](media/service-datasets-certify-promote/power-bi-dataset-learn-more-certification.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป

- [ใช้ชุดข้อมูลทั้งพื้นที่ทำงาน (ดูตัวอย่าง)](service-datasets-across-workspaces.md)
- มีคำถามหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)

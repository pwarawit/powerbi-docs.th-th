---
title: แชร์โดยตรงจากบริการของ Power BI ไปยัง Teams
description: คุณสามารถแชร์แดชบอร์ดและรายงาน Power BI จากบริการของ Power BI ไปยัง Microsoft Teams ได้โดยตรง
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
LocalizationGroup: Share your work
ms.date: 07/22/2020
ms.openlocfilehash: 6305a41188c4416b62d5432823bb30946e5e524d
ms.sourcegitcommit: 65025ab7ae57e338bdbd94be795886e5affd45b4
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/28/2020
ms.locfileid: "87254087"
---
# <a name="share-directly-to-teams-from-the-power-bi-service"></a>แชร์โดยตรงจากบริการของ Power BI ไปยัง Teams

คุณสามารถแชร์แดชบอร์ด รายงาน และวิชวล Power BI จากบริการของ Power BI ไปยัง Microsoft Teams ได้โดยตรง ใช้คุณลักษณะ**แชร์ไปยัง Teams** เพื่อเริ่มการสนทนาอย่างรวดเร็วเมื่อคุณดูรายงานและแดชบอร์ดในบริการของ Power BI

ดู[การทำงานร่วมกันใน Microsoft Teams ด้วย Power BI](service-collaborate-microsoft-teams.md) สำหรับพื้นหลังเกี่ยวกับวิธีที่ระบบ Power Bi และ Teams ทำงานร่วมกัน รวมถึงข้อกำหนดต่าง ๆ ที่คุณต้องปฏิบัติตามด้วย

## <a name="share-power-bi-content-to-teams"></a>แชร์เนื้อหา Power BI ไปยัง Teams

ทำตามขั้นตอนเหล่านี้เพื่อแชร์ลิงก์ที่เชื่อมโยงกับรายงาน แดชบอร์ด และวิชวลในบริการของ Power BI ไปยังช่องทางการสื่อสารและการสนทนาของ Microsoft Teams

1. เลือกหนึ่งในตัวเลือกเหล่านี้:

   * **แชร์ไปยัง Teams** ในแถบการดำเนินการของแดชบอร์ดหรือรายงาน:

       ![ภาพหน้าจอของปุ่มแชร์ไปยัง Teams ในแถบการดำเนินการ](media/service-share-report-teams/service-teams-share-to-teams-action-bar-button.png)
    
   * **แชร์ไปยัง Teams** ในเมนูบริบทสำหรับวิชวลเดียว:
    
      ![ภาพหน้าจอของปุ่มแชร์ไปยัง Teams ในเมนูบริบทวิชวล](media/service-share-report-teams/service-teams-share-to-teams-visual-context-menu.png)

1. ในกล่องโต้ตอบ**แชร์กับ Microsoft Teams** ให้เลือกช่องหรือบุคคลที่คุณต้องการส่งลิงก์ไปให้ เพิ่มข้อความถ้าคุณต้องการ คุณอาจถูกขอให้ลงชื่อเข้าใช้ Microsoft Teams ก่อน

    ![ภาพหน้าจอของแชร์ไปยังกล่องโต้ตอบ Microsoft Teams ด้วยข้อมูลและข้อความ](media/service-share-report-teams/service-teams-share-to-teams-dialog.png)

1. เลือก**แชร์** เพื่อส่งลิงก์
    
1. ลิงก์จะถูกเพิ่มไปยังการสนทนาที่มีอยู่หรือเริ่มการสนทนาใหม่

    ![ภาพหน้าจอของการสนทนาของ Microsoft Teams ที่มีลิงก์ไปยังรายการ Power BI](media/service-share-report-teams/service-teams-share-to-teams-deep-link.png)

1. เลือกลิงก์เพื่อเปิดรายการในบริการ Power BI

1. ถ้าคุณใช้เมนูบริบทสำหรับภาพที่ระบุ ภาพจะถูกไฮไลท์เมื่อรายงานเปิดขึ้น

    ![ภาพหน้าจอของรายงาน Power BI ที่เปิดด้วยวิชวลเฉพาะที่มีการไฮไลต์ไว้](media/service-share-report-teams/service-teams-share-to-teams-spotlight-visual.png)


## <a name="known-issues-and-limitations"></a>ปัญหาและขีดจำกัดที่ทราบแล้ว

- ผู้ใช้ที่ไม่มีสิทธิ์การใช้งาน Power BI หรือสิทธิ์ในการเข้าถึงรายงานจะเห็นข้อความ "เนื้อหาไม่พร้อมใช้งาน"
- ปุ่ม**แชร์ไปยัง Teams** อาจไม่ทำงานถ้าเบราว์เซอร์ของคุณใช้การตั้งค่าความเป็นส่วนตัวที่เข้มงวด ใช้ **ยังพบปัญหาอยู่ใช่หรือไม่? ลองเปิดในตัวเลือกหน้าต่างใหม่** ถ้ากล่องโต้ตอบไม่เปิดอย่างถูกต้อง
- **แชร์ไปยัง Teams** ไม่มีการแสดงตัวอย่างลิงก์
- การแสดงตัวอย่างลิงก์และการ**แชร์ไปยัง Teams** ไม่อนุญาตให้ผู้ใช้สามารถดูรายการได้ สิทธิ์ต้องได้รับการจัดการแยกต่างหาก
- ปุ่ม**แชร์ไปยัง Teams** ไม่พร้อมใช้งานในเมนูบริบทวิชวล เมื่อผู้สร้างรายงานตั้งค่า**ตัวเลือกเพิ่มเติม**เป็น**ปิด**สำหรับวิชวล
- ดูปัญหาอื่น ๆ ที่หัวข้อ[ปัญหาที่ทราบแล้วและข้อจำกัดต่าง ๆ](service-collaborate-microsoft-teams.md#known-issues-and-limitations) ในบทความ “ทำงานร่วมกันใน Microsoft Teams"

## <a name="next-steps"></a>ขั้นตอนถัดไป

- [ทำงานร่วมกันใน Microsoft Teams ด้วย Power BI](service-collaborate-microsoft-teams.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)

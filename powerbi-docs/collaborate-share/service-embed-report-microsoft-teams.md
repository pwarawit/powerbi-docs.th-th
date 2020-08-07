---
title: ฝังรายงาน Power BI ใน Microsoft Teams
description: คุณสามารถฝังรายงาน Power BI แบบโต้ตอบในช่องทางการสื่อสารและการสนทนาของ Microsoft Teams ได้อย่างง่ายดาย .
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 07/31/2020
ms.openlocfilehash: 53126fe044f65740b9dac072422f749312b960da
ms.sourcegitcommit: d9d67ee47954379c2df8db8d0dc8302de4c9f1e5
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/31/2020
ms.locfileid: "87478026"
---
# <a name="embed-power-bi-content-in-microsoft-teams"></a>ฝังเนื้อหา Power BI ใน Microsoft Teams

คุณสามารถฝังรายงาน Power BI แบบโต้ตอบในช่องทางการสื่อสารและการสนทนาของ Microsoft Teams ได้อย่างง่ายดาย 

## <a name="requirements"></a>ข้อกำหนด

หากต้องการใช้แท็บ **Power BI** ใน Microsoft Teams ให้ตรวจสอบองค์ประกอบต่าง ๆ เหล่านี้:

- Microsoft Teams มีแท็บ **Power BI**
- หากต้องการเพิ่มรายงานใน Microsoft Teams ด้วยแท็บ **Power BI** อย่างน้อยคุณต้องมีบทบาทผู้ชมในพื้นที่ทำงานที่โฮสต์รายงาน ดู[บทบาทในพื้นที่ทำงานใหม่](service-new-workspaces.md#roles-in-the-new-workspaces)สำหรับข้อมูลเกี่ยวกับบทบาทที่แตกต่างกัน
- หากต้องการดูรายงานในแท็บ **Power BI** ใน Microsoft Teams ผู้ใช้ต้องมีสิทธิ์ในการดูรายงาน
- ผู้ใช้จะต้องเป็นผู้ใช้  Microsoft Teams ที่มีสิทธิ์เข้าถึงช่องและการสนทนา

ดู[การทำงานร่วมกันใน Microsoft Teams ด้วย Power BI](service-embed-report-microsoft-teams.md) สำหรับเบื้องหลังเกี่ยวกับวิธีที่ระบบ Power Bi และ Teams ทำงานร่วมกัน รวมถึงข้อกำหนดต่าง ๆ ด้วย

## <a name="embed-a-report-in-teams"></a>ฝังรายงานใน Teams

ทำตามขั้นตอนเหล่านี้เพื่อฝังรายงานของคุณลงในแชนเนลหรือแชทของ Microsoft Teams

1. เปิดแชนเนลหรือแชทใน Microsoft Teams และเลือกไอคอน **+**

    ![ภาพหน้าจอของเพิ่มแท็บไปยังช่องทางการสื่อสารหรือการสนทนา](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-add.png)

1. เลือกแท็บ **Power BI**

    ![ภาพหน้าจอของรายการแท็บ Microsoft Teams ที่แสดง Power BI](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab.png)

1. ใช้ตัวเลือกที่ให้มาเพื่อเลือกรายงานจากพื้นที่ทำงานหรือแอป Power BI

    ![ภาพหน้าจอของแท็บ Power B I สำหรับการตั้งค่า Microsoft Teams](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab-settings.png)

1. ชื่อแท็บจะอัปเดตโดยอัตโนมัติเพื่อให้ตรงกับชื่อของชื่อรายงาน แต่คุณสามารถเปลี่ยนได้

1. เลือก**บันทึก**

### <a name="reports-you-can-embed-on-the-power-bi-tab"></a>รายงานที่คุณสามารถฝังบนแท็บ Power BI ได้

คุณสามารถฝังรายงานประเภทต่อไปนี้ได้บนแท็บ **Power BI**:

- รายงานแบบโต้ตอบและรายงานที่มีการแบ่งหน้า
- รายงานใน**พื้นที่ทำงานของฉัน** ประสบการณ์พื้นที่ทำงานใหม่ และพื้นที่ทำงานแบบคลาสสิก
- รายงานในแอป Power BI

## <a name="start-a-conversation"></a>เริ่มการสนทนา

เมื่อคุณเพิ่มแท็บรายงาน Power BI ไปยัง Microsoft Teams  Teams จะสร้างแท็บการสนทนาสำหรับรายงานโดยอัตโนมัติ

- เลือกไอคอน**แสดงแท็บการสนทนา**ในมุมบนขวา

    ![ภาพหน้าจอของไอคอนแสดงแท็บการสนทนา](media/service-embed-report-microsoft-teams/power-bi-teams-conversation-icon.png)

    ข้อคิดเห็นแรกคือการเชื่อมโยงไปยังรายงาน ทุกคนในช่องของ Microsoft Teams สามารถดูและพูดคุยเกี่ยวกับรายงานในการสนทนาได้

    ![ภาพหน้าจอของแท็บการสนทนา](media/service-embed-report-microsoft-teams/power-bi-teams-conversation-tab.png)

## <a name="known-issues-and-limitations"></a>ปัญหาและขีดจำกัดที่ทราบแล้ว

- คุณไม่สามารถฝังแดชบอร์ด Power BI ลงในแท็บ **Power BI** สำหรับ Microsoft Teams ได้
- ไม่รองรับ[ตัวกรอง URL](service-url-filters.md) ที่มีแท็บ **Power BI** สำหรับ Microsoft Teams
- ในระบบคลาวด์ภายในประเทศ แท็บ **Power BI** ใหม่ไม่พร้อมใช้งาน รุ่นที่เก่ากว่าอาจพร้อมใช้งานที่ไม่รองรับพื้นที่ทำงานใหม่ พื้นที่ทำงานที่เคยทำ หรือรายงานในแอป Power BI
- หลังจากที่คุณบันทึกแท็บแล้ว คุณไม่สามารถเปลี่ยนชื่อแท็บผ่านการตั้งค่าแท็บได้ ใช้ตัวเลือก**เปลี่ยนชื่อ**เพื่อดำเนินการเปลี่ยนชื่อ
- ดูปัญหาอื่น ๆ ที่หัวข้อ[ปัญหาที่ทราบแล้วและข้อจำกัดต่าง ๆ](service-collaborate-microsoft-teams.md#known-issues-and-limitations) ในบทความ “ทำงานร่วมกันใน Microsoft Teams"

## <a name="next-steps"></a>ขั้นตอนถัดไป

- [ทำงานร่วมกันใน Microsoft Teams ด้วย Power BI](service-collaborate-microsoft-teams.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)

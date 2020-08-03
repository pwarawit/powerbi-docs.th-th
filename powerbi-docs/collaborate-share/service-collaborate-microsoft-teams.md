---
title: ทำงานร่วมกันใน Microsoft Teams ด้วย Power BI
description: คุณสามารถแชร์และทำงานร่วมกันในส่วนของเนื้อหา Power Bi แบบโต้ตอบในช่องทางการสื่อสารและการสนทนาของ Microsoft Teams ได้อย่างง่ายดาย
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 07/22/2020
ms.openlocfilehash: 17a0879dac416a98d214ed11861947cb2c311487
ms.sourcegitcommit: 65025ab7ae57e338bdbd94be795886e5affd45b4
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/28/2020
ms.locfileid: "87254219"
---
# <a name="collaborate-in-microsoft-teams-with-power-bi"></a>ทำงานร่วมกันใน Microsoft Teams ด้วย Power BI

คุณมีตัวเลือกหลายรูปแบบในการแชร์และการทำงานร่วมกันในส่วนของเนื้อหา Power Bi แบบโต้ตอบในช่องทางการสื่อสารและการสนทนาของ Microsoft Teams 

- ด้วยแท็บ**Power BI**สำหรับ Microsoft Teams คุณสามารถ[ฝังรายงานแบบโต้ตอบในช่องทางการสื่อสารและการสนทนาของ Microsoft Teams ได้](service-embed-report-microsoft-teams.md) แท็บ **Power BI** ช่วยให้เพื่อนร่วมงานของคุณสามารถค้นหาข้อมูลของทีมและหารือเกี่ยวกับข้อมูลภายในช่องทางการสื่อสารสำหรับทีมของคุณ 
- สร้าง[ตัวอย่างลิงก์](service-teams-link-preview.md) เมื่อคุณวางลิงก์ที่เชื่อมโยงไปยังรายงานของคุณ แดชบอร์ด และแอปต่าง ๆ ลงในกล่องข้อความ Microsoft Teams ตัวอย่างลิงก์แสดงข้อมูลเกี่ยวกับลิงก์ 
- ใช้[แชร์ไปยัง Teams](service-share-report-teams.md) เมื่อคุณดูรายงานและแดชบอร์ดในบริการของ Power BI เพื่อเริ่มการสนทนาใน Teams อย่างรวดเร็ว
 
:::image type="content" source="media/service-collaborate-microsoft-teams/power-bi-embed-teams-report.png" alt-text="ภาพหน้าจอของรายงาน Power B I ที่ฝังในช่องทาง Teams":::

## <a name="requirements"></a>ข้อกำหนด

สำหรับ Power BI ที่จะทำงานใน Microsoft Teams ให้ตรวจสอบองค์ประกอบต่าง ๆ เหล่านี้:

- ผู้ใช้ของคุณสิทธิ์การใช้งาน Power BI Pro หรือรายงานที่มีอยู่ในความจุ [Power BI Premium (EM หรือ P SKU)](../admin/service-premium-what-is.md) พร้อมสิทธิ์การใช้งาน Power BI
- ผู้ใช้ลงชื่อเข้าใช้ในบริการของ Power BI เพื่อเปิดใช้สิทธิ์การใช้งาน Power BI ของตนเองแล้ว
- ผู้ใช้จะต้องปฏิบัติตามข้อกำหนดในการใช้งานแท็บ **Power BI** ใน Microsoft Teams

หากต้องการใช้แท็บ **Power BI** ใน Microsoft Teams ให้ตรวจสอบองค์ประกอบต่าง ๆ เหล่านี้:

- Microsoft Teams มีแท็บ **Power BI**
- หากต้องการเพิ่มรายงานใน Microsoft Teams ด้วยแท็บ **Power BI** อย่างน้อยคุณต้องมีบทบาทผู้ชมในพื้นที่ทำงานที่โฮสต์รายงาน ดู[บทบาทในพื้นที่ทำงานใหม่](service-new-workspaces.md#roles-in-the-new-workspaces)สำหรับข้อมูลเกี่ยวกับบทบาทที่แตกต่างกัน
- หากต้องการดูรายงานในแท็บ **Power BI** ใน Microsoft Teams ผู้ใช้ต้องมีสิทธิ์ในการดูรายงาน
- ผู้ใช้จะต้องเป็นผู้ใช้  Microsoft Teams ที่มีสิทธิ์เข้าถึงช่องและการสนทนา

หากต้องการใช้ฟังก์ชัน**แชร์ไปยัง Teams** ใน Power BI ให้ตรวจสอบการตั้งค่านี้:

- ผู้ดูแลระบบ Power BI ยังไม่ได้ปิดใช้งาน **แชร์ไปยัง Teams** ในการตั้งค่าผู้เช่าในพอร์ทัลผู้ดูแลระบบ Power BI การตั้งค่านี้อนุญาตให้องค์กรซ่อนปุ่ม**แชร์ไปยัง Teams** ได้ ดูรายละเอียดที่บทความ[พอร์ทัลผู้ดูแลระบบ Power BI](../admin/service-admin-portal.md#share-to-teams-tenant-setting)

## <a name="grant-access-to-reports"></a>อนุญาตการเข้าถึงรายงาน

การฝังรายงานใน Microsoft Teams หรือการส่งลิงก์ไปยังรายการไม่ได้ให้สิทธิ์แก่ผู้ใช้ในการดูรายงานโดยอัตโนมัติ คุณจำเป็นต้อง[อนุญาตให้ผู้ใช้สามารถดูรายงานใน Power BI](service-share-dashboards.md) ได้ คุณสามารถใช้ Microsoft 365 Group สำหรับทีมของคุณเพื่อทำให้ง่ายขึ้น

> [!IMPORTANT]
> ให้ตรวจสอบให้แน่ใจว่าว่าใครสามารถดูรายงานภายใน Power BI service และอนุญาตให้เข้าถึงสิ่งที่ไม่ได้อยู่ในรายการ

วิธีหนึ่งในการตรวจสอบให้แน่ใจว่าทุกคนในทีมมีสิทธิ์เข้าถึงรายงานคือการวางรายงานในพื้นที่ทำงานเดียวและให้การเข้าถึง Microsoft 365 Group กับทีมของคุณ

## <a name="known-issues-and-limitations"></a>ปัญหาและขีดจำกัดที่ทราบแล้ว

- Power BI ไม่รองรับภาษาที่แปลเป็นภาษาท้องถิ่นเช่นเดียวกับที่ Microsoft Teams รองรับ ผลที่ได้คือคุณอาจไม่เห็นการแปลที่เหมาะสมภายในรายงานแบบฝังตัว
- คุณไม่สามารถฝังแดชบอร์ด Power BI ในแท็บ **Power BI** สำหรับ Microsoft Teams ได้
- ผู้ใช้ที่ไม่มีสิทธิ์การใช้งาน Power BI หรือสิทธิ์ในการเข้าถึงรายงานจะเห็นข้อความ "เนื้อหาไม่พร้อมใช้งาน"
- คุณอาจพบปัญหาถ้าคุณใช้ Internet Explorer 10 <!--You can look at the [browsers support for Power BI](../consumer/end-user-browsers.md) and for [Microsoft 365](https://products.office.com/office-system-requirements#Browsers-section). -->
- ไม่รองรับ[ตัวกรอง URL](service-url-filters.md) ที่มีแท็บ **Power BI** สำหรับ Microsoft Teams
- ในระบบคลาวด์ภายในประเทศ แท็บ **Power BI** ใหม่ไม่พร้อมใช้งาน รุ่นที่เก่ากว่าอาจพร้อมใช้งานที่ไม่รองรับพื้นที่ทำงานใหม่ พื้นที่ทำงานที่เคยทำ หรือรายงานในแอป Power BI
- หลังจากที่คุณบันทึกแท็บแล้ว คุณจะไม่สามารถเปลี่ยนชื่อแท็บผ่านการตั้งค่าแท็บได้ ใช้ตัวเลือก**เปลี่ยนชื่อ**เพื่อดำเนินการเปลี่ยนชื่อ
- การลงชื่อเข้าระบบครั้งเดียวไม่ได้รับการรองรับสำหรับบริการการแสดงตัวอย่างลิงก์
- การแสดงตัวอย่างลิงก์ไม่ทำงานในแชทการประชุมหรือแชนเนลส่วนตัว

## <a name="next-steps"></a>ขั้นตอนถัดไป

- [ฝังเนื้อหา Power BI ใน Microsoft Teams](service-embed-report-microsoft-teams.md)
- [รับตัวอย่างลิงก์ Power BI ใน Microsoft Teams](service-teams-link-preview.md)
- [แชร์โดยตรงจากบริการของ Power BI ไปยัง Teams](service-share-report-teams.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)

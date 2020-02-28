---
title: ฝังรายงานด้วยแท็บ Power BI สำหรับ Microsoft Teams
description: ด้วยแท็บ Power BI สำหรับ Microsoft Teams คุณสามารถฝังรายงานแบบโต้ตอบในแชนเนลและแชทได้อย่างง่ายดาย
author: LukaszPawlowski-MS
ms.author: lukaszp
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 01/31/2020
ms.openlocfilehash: fb4846a777dda4787e1ed0be7de869367a616ea5
ms.sourcegitcommit: b22a9a43f61ed7fc0ced1924eec71b2534ac63f3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/21/2020
ms.locfileid: "77530498"
---
# <a name="embed-report-with-the-power-bi-tab-for-microsoft-teams"></a>ฝังรายงานด้วยแท็บ Power BI สำหรับ Microsoft Teams

ด้วยแท็บ Power BI ที่อัปเดตใหม่สำหรับ Microsoft Teams คุณสามารถฝังรายงานแบบโต้ตอบในแชนเนลและแชทของ Microsoft Teams ได้อย่างง่ายดาย

ใช้แท็บ Power BI สำหรับ Microsoft Teams เพื่อช่วยเพื่อนร่วมงานของคุณค้นหาข้อมูลที่ทีมของคุณใช้และเพื่อพูดคุยเกี่ยวกับข้อมูลภายในแชนเนลของทีมคุณ

## <a name="requirements"></a>ข้อกำหนด

เพื่อให้ **แท็บ Power BI สำหรับ Microsoft Teams** ทำงาน จำเป็นต้องมีรายการต่อไปนี้:

- สิทธิการใช้งาน Power BI Pro หรือรายงานที่มีอยู่ในความจุ [Power BI Premium (EM หรือ P SKU)](service-premium-what-is.md) พร้อมสิทธิการใช้งาน Power BI
- แท็บ Power BI สำหรับ Microsoft Teams
- ผู้ใช้ต้องลงชื่อเข้าใช้ในบริการของ Power BI เพื่อเปิดใช้สิทธิการใช้งาน Power BI ของพวกเขาสำหรับการใช้รายงาน
- ผู้ใช้ต้องมีสิทธิ์ในการดูรายงาน

## <a name="embed-your-report"></a>ฝังรายงานของคุณ
เมื่อต้องฝังรายงานของคุณลงในแชนเนลหรือแชทของ Microsoft Teams ให้เพิ่มตามที่อธิบายไว้ด้านล่าง

1. เปิดแชนเนลหรือแชทที่ต้องการใน Microsoft Teams และเลือกไอคอน **+**

    ![เพิ่มแท็บไปยังแชนเนลหรือแชท](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-add.png)

2. เลือกแท็บ Power BI

    ![รายการแท็บของ Microsoft Teams ที่แสดง Power BI](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab.png)

3. ใช้ตัวเลือกที่ให้มาเพื่อเลือกรายงานจากพื้นที่ทำงาน ที่แชร์กับฉัน หรือแอป Power BI

    ![แท็บ Power BI สำหรับการตั้งค่า Microsoft Teams](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab-settings.png)

4. ชื่อแท็บจะได้รับการอัปเดตโดยอัตโนมัติเพื่อให้ตรงกับชื่อของชื่อรายงาน แต่คุณสามารถเปลี่ยนแปลงค่าได้ 

5. กด **บันทึก**

## <a name="supported-reports"></a>รายงานที่ได้รับการสนับสนุน

แท็บเปิดใช้งานการฝังรายงานต่อไปนี้:

- รายงานแบบโต้ตอบและรายงานที่มีการแบ่งหน้า
- รายงานในพื้นที่ทำงานของฉัน ประสบการณ์พื้นที่ทำงานใหม่ และพื้นที่ทำงานแบบคลาสสิก
- รายงานในแอป Power BI


## <a name="grant-access-to-reports"></a>อนุญาตการเข้าถึงรายงาน

การฝังรายงานใน Microsoft Teams ไม่ให้สิทธิผู้ใช้ในการดูรายงานโดยอัตโนมัติ คุณต้อง [อนุญาตให้ผู้ใช้ดูรายงานใน Power BI](service-share-dashboards.md) คุณสามารถใช้กลุ่ม Office 365 สำหรับทีมของคุณเพื่อทำให้ง่ายขึ้น 

> [!IMPORTANT]
> ให้ตรวจสอบให้แน่ใจว่าว่าใครสามารถดูรายงานภายใน Power BI service และอนุญาตให้เข้าถึงสิ่งที่ไม่ได้อยู่ในรายการ

วิธีหนึ่งในการตรวจสอบให้แน่ใจว่าทุกคนในทีมของคุณมีสิทธิ์เข้าถึงรายงานที่คุณฝังคือการวางพวกเขาเหล่านั้นไว้ในพื้นที่ทำงานแบบเดี่ยวใน Power BI และให้ Office 365 Group แก่ทีมของคุณเข้าถึงพื้นที่ทำงาน

## <a name="known-issues-and-limitations"></a>ปัญหาและขีดจำกัดที่ทราบแล้ว

- Power BI ไม่รองรับภาษาที่แปลเป็นภาษาท้องถิ่นเช่นเดียวกับที่ Microsoft Teams รองรับ ผลที่ได้คือคุณอาจไม่เห็นการแปลที่เหมาะสมภายในรายงานแบบฝังตัว
- คุณไม่สามารถฝังแดชบอร์ด Power BI ในแท็บ Power BI สำหรับ Microsoft Teams ได้
- ผู้ใช้ที่ไม่มีสิทธิการใช้งาน Power BI หรือสิทธิการใช้งานในรายงานจะเห็นข้อความ "เนื้อหาไม่พร้อมใช้งาน"
- คุณอาจพบปัญหาถ้าใช้ Internet Explorer 10 <!--You can look at the [browsers support for Power BI](consumer/end-user-browsers.md) and for [Office 365](https://products.office.com/office-system-requirements#Browsers-section). -->
- ไม่สนับสนุน[ตัวกรอง URL](service-url-filters.md) กับแท็บ Power BI สำหรับ Microsoft Teams
- ในบริการคลาวด์แห่งชาติที่แท็บ Power BI ใหม่ไม่พร้อมใช้งาน อาจมีเวอร์ชันเก่ากว่าที่ไม่รองรับพื้นที่ทำงานใหม่ ประสบการณ์พื้นที่ทำงานใหม่ หรือรายงานในแอป Power BI 
- เมื่อมีการบันทึกแท็บแล้ว คุณจะไม่สามารถเปลี่ยนแปลงชื่อแท็บผ่านการตั้งค่าแท็บได้ ใช้ตัวเลือกเปลี่ยนชื่อเพื่อดำเนินการเปลี่ยนชื่อ

## <a name="next-steps"></a>ขั้นตอนถัดไป
- [แชร์แดชบอร์ดกับเพื่อนร่วมงานและคนอื่นๆ](service-share-dashboards.md)  
- [สร้างและกระจายแอปฯใน Power BI](service-create-distribute-apps.md)  
- [Power BI Premium คืออะไร?](service-premium-what-is.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)

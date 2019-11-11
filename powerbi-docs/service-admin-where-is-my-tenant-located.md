---
title: ผู้เช่า Power BI ของฉันอยู่ที่ไหน
description: เรียนรู้ตำแหน่งที่ผู้เช่า Power BI ของคุณอยู่และวิธีเลือกตำแหน่งที่ตั้ง เป็นเรื่องสำคัญที่ต้องเรียนรู้เพราะอาจส่งผลกระทบต่อการโต้ตอบที่คุณมีกับบริการ
author: mgblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 3f12e6f0b54f85ebd626b2bd35bf1a03d513c17a
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/09/2019
ms.locfileid: "73873325"
---
# <a name="where-is-my-power-bi-tenant-located"></a>ผู้เช่า Power BI ของฉันอยู่ที่ไหน?

<iframe width="560" height="315" src="https://www.youtube.com/embed/0fOxaHJPvdM?showinfo=0" frameborder="0" allowfullscreen></iframe>

เรียนรู้ตำแหน่งที่ผู้เช่า Power BI ของคุณอยู่และวิธีเลือกตำแหน่งที่ตั้ง การเรียนรู้ตำแหน่งที่ตั้งถือเป็นสิ่งสำคัญเนื่องจากสามารถส่งผลกระทบต่อการโต้ตอบที่คุณมีกับบริการได้

## <a name="how-to-determine-where-your-power-bi-tenant-is-located"></a>วิธีการตรวจสอบตำแหน่งที่ผู้เช่า Power BI ของคุณอยู่

หากต้องการค้นหาภูมิภาคที่ผู้เช่าของคุณอยู่ ให้ปฏิบัติตามขั้นตอนเหล่านี้

1. ในบริการของ Power BI ที่เมนูด้านบน เลือกความช่วยเหลือ ( **?** ) จากนั้นเลือก **เกี่ยวกับ Power BI**

1. ค้นหาค่าที่อยู่ถัดจาก **ข้อมูลของคุณถูกเก็บไว้ใน** ค่านั้นคือภูมิภาคที่ผู้เช่าของคุณอยู่ ค่านี้ยังมีภูมิภาคที่ข้อมูลของคุณถูกเก็บไว้ เว้นแต่ว่าคุณกำลังใช้ความจุเฉพาะในภูมิภาคอื่นสำหรับพื้นที่ทำงานของคุณด้วย

    ![ขอบเขตข้อมูล](media/service-admin-where-is-my-tenant-located/power-bi-data-region.png)

## <a name="how-the-data-region-is-selected"></a>วิธีเลือกขอบเขตข้อมูล

ขอบเขตข้อมูลจะยึดตามประเทศที่คุณเลือกเมื่อคุณสร้างผู้เช่า การเลือกนำไปใช้เพื่อลงทะเบียนใน Office 365 และ Power BI เนื่องจากข้อมูลนี้ถูกใช้ร่วมกัน หากเป็นผู้เช่าใหม่ ให้เลือกประเทศที่เหมาะสมจากรายการเมื่อคุณลงทะเบียน

![การเลือกประเทศ](media/service-admin-where-is-my-tenant-located/sign-up-country-selection.png)

Power BI จะเลือกขอบเขตข้อมูลที่ใกล้เคียงการเลือกของคุณมากที่สุด ซึ่งจะกำหนดตำแหน่งที่เก็บข้อมูลสำหรับผู้เช่าของคุณ

> [!IMPORTANT]
> คุณไม่สามารถเปลี่ยนการเลือกหลังจากที่สร้างผู้เช่า

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)


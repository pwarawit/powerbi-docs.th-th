---
title: ผู้เช่า Power BI ของฉันอยู่ที่ไหน
description: เรียนรู้ตำแหน่งที่ผู้เช่า Power BI ของคุณอยู่และวิธีเลือกตำแหน่งที่ตั้ง เป็นเรื่องสำคัญที่ต้องทำความเข้าใจเนื่องจากอาจส่งผลกระทบต่อการโต้ตอบที่คุณมีกับบริการ
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/31/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: e71844110eb3452cbcb3b224bbca9db57475367e
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54282183"
---
# <a name="where-is-my-power-bi-tenant-located"></a>ผู้เช่า Power BI ของฉันอยู่ที่ไหน

<iframe width="560" height="315" src="https://www.youtube.com/embed/0fOxaHJPvdM?showinfo=0" frameborder="0" allowfullscreen></iframe>

เรียนรู้ตำแหน่งที่ผู้เช่า Power BI ของคุณอยู่และวิธีเลือกตำแหน่งที่ตั้ง การทำความเข้าใจตำแหน่งที่ตั้งถือเป็นสิ่งสำคัญเนื่องจากสามารถส่งผลต่อการโต้ตอบที่คุณมีกับบริการได้

## <a name="how-to-determine-where-your-power-bi-tenant-is-located"></a>วิธีการตรวจสอบตำแหน่งที่ผู้เช่า Power BI ของคุณอยู่

หากต้องการค้นหาภูมิภาคที่ผู้เช่าของคุณอยู่ ให้ปฏิบัติตามขั้นตอนเหล่านี้

1. ในบริการของ Power BI ที่เมนูด้านบน เลือกความช่วยเหลือ (**?**) จากนั้นเลือก **เกี่ยวกับ Power BI**

1. ค้นหาค่าที่อยู่ถัดจาก **ข้อมูลของคุณถูกเก็บไว้ใน** นี่คือภูมิภาคที่ผู้เช่าของคุณอยู่

    ![ขอบเขตข้อมูล](media/service-admin-where-is-my-tenant-located/power-bi-data-region.png)

## <a name="how-the-data-region-is-selected"></a>วิธีเลือกขอบเขตข้อมูล

ขอบเขตข้อมูลจะยึดตามประเทศที่คุณเลือกเมื่อคุณสร้างผู้เช่า ข้อมูลนี้นำไปใช้เพื่อลงทะเบียน Office 365 นอกเหนือจาก Power BI เนื่องจากข้อมูลนี้ถูกใช้ร่วมกัน หากเป็นผู้เช่าใหม่ ให้เลือกประเทศที่เหมาะสมจากรายการเมื่อคุณลงทะเบียน

![การเลือกประเทศ](media/service-admin-where-is-my-tenant-located/sign-up-country-selection.png)

Power BI จะเลือกขอบเขตข้อมูลที่ใกล้เคียงการเลือกนี้มากที่สุด ซึ่งจะกำหนดตำแหน่งที่เก็บข้อมูลสำหรับผู้เช่าของคุณ

> [!IMPORTANT]
> คุณไม่สามารถเปลี่ยนการเลือกนี้หลังจากที่สร้างผู้เช่า

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


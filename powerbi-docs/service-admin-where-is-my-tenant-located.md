---
title: ผู้เช่า Power BI ของฉันอยู่ที่ไหน
description: เรียนรู้ตำแหน่งที่ผู้เช่า Power BI ของคุณอยู่และวิธีเลือกตำแหน่งที่ตั้ง เป็นเรื่องสำคัญที่ต้องทำความเข้าใจเนื่องจากอาจส่งผลกระทบต่อการโต้ตอบที่คุณมีกับบริการ
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 08/10/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: c0c6de63292d3087aaa78dd97b73f868ef9d804e
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34293662"
---
# <a name="where-is-my-power-bi-tenant-located"></a>ผู้เช่า Power BI ของฉันอยู่ที่ไหน
<iframe width="560" height="315" src="https://www.youtube.com/embed/0fOxaHJPvdM?showinfo=0" frameborder="0" allowfullscreen></iframe>

เรียนรู้ตำแหน่งที่ผู้เช่า Power BI ของคุณอยู่และวิธีเลือกตำแหน่งที่ตั้ง เป็นเรื่องสำคัญที่ต้องทำความเข้าใจเนื่องจากอาจส่งผลกระทบต่อการโต้ตอบที่คุณมีกับบริการ

## <a name="how-to-determine-where-your-power-bi-tenant-is-located"></a>วิธีการตรวจสอบตำแหน่งที่ผู้เช่า Power BI ของคุณอยู่
ในการค้นหาภูมิภาคที่ผู้เช่าของคุณอยู่นั้น คุณสามารถทำสิ่งต่อไปนี้

1. เลือก **?** ภายในบริการ Power BI
2. เลือก **เกี่ยวกับ Power BI**
3. ค้นหาค่าที่อยู่ถัดจาก **ข้อมูลของคุณถูกเก็บไว้ใน** นี่คือภูมิภาคที่คุณอยู่

![](media/service-admin-where-is-my-tenant-located/power-bi-data-region.png)

## <a name="how-the-data-region-is-selected"></a>วิธีเลือกขอบเขตข้อมูล
ขอบเขตข้อมูลจะยึดตามประเทศที่เลือกไว้ตั้งแต่สร้างผู้เช่าเป็นครั้งแรก ข้อมูลนี้นำไปใช้เพื่อลงชื่อสมัครใช้ Office 365 ได้นอกเหนือไปจาก Power BI แล้ว เนื่องจากข้อมูลนี้ถูกใช้ร่วมกัน ถ้านี่คือผู้เช่าใหม่ เมื่อคุณลงชื่อสมัครใช้ ก็จะเห็นรายการดรอปดาวน์ประเทศ

![](media/service-admin-where-is-my-tenant-located/sign-up-country-selection.png)

การเลือกนี้คือการเลือกว่าจะจัดเก็บข้อมูลของคุณไว้ที่ตำแหน่งที่ตั้งในไดรฟ์ใด Power BI จะเลือกขอบเขตข้อมูลที่ใกล้เคียงกับสิ่งที่เลือกนี้มากที่สุด

> [!WARNING]
> การเลือกนี้ไม่สามารถเปลี่ยนแปลงได้!
> 
> 

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


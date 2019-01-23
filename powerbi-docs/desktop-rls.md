---
title: ทำความเข้าใจเกี่ยวกับการรักษาความปลอดภัยระดับแถว (RLS) ด้วย Power BI Desktop
description: วิธีการกำหนดค่าความปลอดภัยระดับแถวสำหรับชุดข้อมูลที่นำเข้า และ DirectQuery ภายใน Power BI Desktop
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/03/2018
LocalizationGroup: Create reports
ms.openlocfilehash: a5f594f241fb4964775055a022b2f7c943dd05a1
ms.sourcegitcommit: 2c49a7cee9c77f46830ddfa59fdedbf30186d389
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/23/2019
ms.locfileid: "54488787"
---
# <a name="row-level-security-rls-with-power-bi-desktop"></a>รักษาความปลอดภัยระดับแถว (RLS) ด้วย Power BI Desktop

รักษาความปลอดภัยระดับแถว (RLS) ด้วย Power BI Desktop จำกัดการเข้าถึงข้อมูลสำหรับผู้ใช้ที่กำหนด ตัวกรองจะจำกัดข้อมูลในระดับแถว คุณสามารถกำหนดตัวกรองภายในบทบาท

ในตอนนี้คุณสามารถกำหนดค่า RLS สำหรับรูปแบบข้อมูลที่นำเข้าลงใน Power BI ด้วย Power BI Desktop ได้ คุณยังสามารถกำหนดค่า RLS บนชุดข้อมูลที่กำลังใช้ DirectQuery เช่น SQL Server ได้อีกด้วย ก่อนหน้านี้ คุณสามารถใช้ได้เฉพาะ RLS ภายในแบบจำลองภายในองค์กรของ Analysis Services ภายนอก Power BI เท่านั้น ในส่วนการเชื่อมต่อสดของ Analysis Services คุณสามารถกำหนดค่ารักษาความปลอดภัยระดับแถวบนแบบจำลองภายในองค์กรได้ ตัวเลือกความปลอดภัยจะไม่แสดงสำหรับชุดข้อมูลที่เชื่อมต่อสด

> [!IMPORTANT]
> ถ้าคุณกำหนดบทบาทและกฎ ภายในบริการของ Power BI คุณจะต้องสร้างบทบาทเหล่านั้นภายใน Power BI Desktop และเผยแพร่รายงานนั้นไปยังบริการ

เรียนรู้เพิ่มเติมเกี่ยวกับตัวเลือกสำหรับ [RLS ภายในบริการของ Power BI](service-admin-rls.md)

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>ขั้นตอนถัดไป

[รักษาความปลอดภัยระดับแถว (RLS) ด้วยบริการของ Power BI](service-admin-rls.md)  

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)
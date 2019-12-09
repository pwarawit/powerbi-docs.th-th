---
title: ทำความเข้าใจเกี่ยวกับการรักษาความปลอดภัยระดับแถว (RLS) ด้วย Power BI Desktop
description: วิธีการกำหนดค่าความปลอดภัยระดับแถวสำหรับชุดข้อมูลที่นำเข้า และ DirectQuery ภายใน Power BI Desktop
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.custom: ''
ms.date: 12/05/2019
LocalizationGroup: Create reports
ms.openlocfilehash: abbd8f34f42bdcfdca6e65df58c78bf394f00d91
ms.sourcegitcommit: 9a265d8117cc202f5f700286b5ff42a631aacdb4
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/06/2019
ms.locfileid: "74882781"
---
# <a name="row-level-security-rls-with-power-bi-desktop"></a>รักษาความปลอดภัยระดับแถว (RLS) ด้วย Power BI Desktop

คุณสามารถใช้การรักษาความปลอดภัยระดับแถว (RLS) ด้วย Power BI Desktop เพื่อจำกัดการเข้าถึงข้อมูลสำหรับให้ผู้ใช้ได้ ตัวกรองจะจำกัดข้อมูลในระดับแถว คุณสามารถกำหนดตัวกรองภายในบทบาท

ในตอนนี้คุณสามารถกำหนดค่า RLS สำหรับรูปแบบข้อมูลที่นำเข้าลงใน Power BI ด้วย Power BI Desktop ได้ คุณยังสามารถกำหนดค่า RLS บนชุดข้อมูลที่กำลังใช้ [DirectQuery](desktop-use-directquery.md) เช่น SQL Server ได้อีกด้วย ก่อนหน้านี้ คุณสามารถใช้ได้เฉพาะ RLS ภายในแบบจำลองภายในองค์กรของ Analysis Services ภายนอก Power BI เท่านั้น ในส่วนการเชื่อมต่อสดของ Analysis Services คุณสามารถกำหนดค่ารักษาความปลอดภัยระดับแถวบนแบบจำลองภายในองค์กรได้ ตัวเลือกความปลอดภัยจะไม่แสดงสำหรับชุดข้อมูลที่เชื่อมต่อสด

> [!IMPORTANT]
> ถ้าคุณกำหนดบทบาทและกฎ ภายในบริการของ Power BI คุณจะต้องสร้างบทบาทเหล่านั้นภายใน Power BI Desktop และเผยแพร่รายงานนั้นไปยังบริการ

เรียนรู้เพิ่มเติมเกี่ยวกับตัวเลือกสำหรับ [RLS ภายในบริการของ Power BI](service-admin-rls.md)

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>ขั้นตอนถัดไป

[รักษาความปลอดภัยระดับแถว (RLS) ด้วยบริการของ Power BI](service-admin-rls.md)  

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
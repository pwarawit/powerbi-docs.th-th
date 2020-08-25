---
title: ใช้คีย์ที่ลูกค้าจัดการใน Power BI
description: ศึกษาวิธีการใช้คีย์ที่ลูกค้าจัดการใน Power BI
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.date: 08/12/2020
LocalizationGroup: Premium
ms.openlocfilehash: 8d13cc7a24486fada7f8d428ba52abeaa49d2518
ms.sourcegitcommit: b60063c49ac39f8b28c448908ecbb44b54326335
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/12/2020
ms.locfileid: "88160951"
---
# <a name="use-customer-managed-keys-in-power-bi"></a>ใช้คีย์ที่ลูกค้าจัดการใน Power BI

Power BI เข้ารหัสข้อมูลที่พักอยู่และในระหว่างการดำเนินการ ตามค่าเริ่มต้น Power BI ใช้คีย์ที่จัดการโดย Microsoft เพื่อเข้ารหัสลับข้อมูลของคุณ องค์กรสามารถเลือกใช้คีย์ของตนเองเพื่อเข้ารหัสเนื้อหาของผู้ใช้ในทั้งหมดใน Power BI จากภาพรายงานเพื่อนำเข้าชุดข้อมูลในความจุแบบพรีเมียมได้ 

## <a name="why-use-customer-managed-keys"></a>เหตุใดจึงต้องใช้คีย์ที่ลูกค้าจัดการ
ด้วยการใช้คีย์ที่ลูกค้าจัดการของ Power BI (CMK) องค์กะรสามารถตอบสนองความต้องการด้านการปฏิบัติตามข้อกำหนดสำหรับการเข้ารหัสข้อมูลที่อยู่กับผู้บริการคลาวด์ของตน (ซึ่งในกรณีนี้คือ Microsoft) CMK ช่วยให้องค์กรสามารถเข้ารหัสเนื้อหาของผู้ใช้ Power BI ของตนได้ด้วยคีย์ที่องค์กรกำหนดขึ้นและบริหารจัดการ การเลิกใช้คีย์ที่ลูกค้าจัดการจะทำให้ทุกคนไม่สามารถอ่านเนื้อหาของผู้ใช้ภายใน Power BI ได้ภายในเวลาหนึ่งชั่วโมงรวมถึง Microsoft ด้วย เมื่อเทียบกับข้อเสนอ BYOK วิธีการ CMK ยังครอบคลุมถึงเนื้อหาของผู้ใช้นอกความจุแบบพรีเมียมของ Power BI ด้วย ทั้งยังมีนโยบายการแคชที่เข้มข้นกว่า และตามค่าเริ่มต้น ระบบจะเปิดใช้งาน BYOK ในทุก ๆ ความจุ 
 
## <a name="how-to-use-customer-managed-keys"></a>วิธีการใช้คีย์ที่ลูกค้าจัดการ
หากต้องการใช้คีย์ที่ลูกค้าจัดการ องค์กรของคุณต้องมีคุณสมบัติด้านขนาดผ่านเกณฑ์ที่กำหนด ผู้ดูแลระบบส่วนกลางขององค์กรของคุณต้องส่งคำขอการสนับสนุนไปยัง Microsoft หรือติดต่อผู้จัดการบัญชี Microsoft ขององค์กรของคุณเพื่อเรียนรู้เพิ่มเติมเกี่ยวกับขั้นตอนการใช้งาน  


## <a name="next-steps"></a>ขั้นตอนถัดไป

สามารถดูข้อมูลต่าง ๆ ที่มีประโยชน์ต่อการใช้คีย์ที่ลูกค้าเป็นผู้จัดการได้ที่ลิงค์ต่าง ๆ ดังต่อไปนี้:

* [นำคีย์การเข้ารหัสลับของคุณเองมาใช้กับ Power BI](service-encryption-byok.md)
* [กำหนดค่าการสนับสนุน Multi-Geo สำหรับ Power BI Premium](service-admin-premium-multi-geo.md)
* [วิธีการทำงานของความจุ](service-premium-what-is.md#how-capacities-function)
* [การรีเฟรชแบบเพิ่มหน่วย](service-premium-incremental-refresh.md)

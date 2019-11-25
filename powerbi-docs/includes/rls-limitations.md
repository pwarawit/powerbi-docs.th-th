---
author: mgblythe
ms.service: powerbi
ms.topic: include
ms.date: 09/13/2019
ms.author: mblythe
ms.openlocfilehash: c658e683e86a899d45728220dee3706a0d617f0f
ms.sourcegitcommit: c395fe83d63641e0fbd7c98e51bbab224805bbcc
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/21/2019
ms.locfileid: "74284169"
---
## <a name="limitations"></a>ข้อจำกัด

ต่อไปนี้คือรายการของข้อจำกัดปัจจุบันสำหรับความปลอดภัยระดับแถวบนแบบจำลองคลาวด์

* ถ้าก่อนหน้านี้คุณได้กำหนดบทบาทและกฎในบริการ Power BI แล้ว คุณต้องสร้างขึ้นใหม่ใน Power BI Desktop

* คุณสามารถกำหนด RLS บนชุดข้อมูลที่สร้างขึ้นด้วย Power BI Desktop เท่านั้น ถ้าคุณต้องการเปิดใช้งาน RLS สำหรับชุดข้อมูลที่สร้างขึ้นโดยใช้ Excel คุณจะต้องแปลงไฟล์ของคุณให้เป็นไฟล์ Power BI Desktop (PBIX) ก่อน [เรียนรู้เพิ่มเติม](../desktop-import-excel-workbooks.md)

* ETL และการเชื่อมต่อ DirectQuery เท่านั้นที่ได้รับการสนับสนุน Live connection ไปถึง Analysis Services ได้รับการจัดการในแบบจำลองแบบภายในองค์กร

## <a name="known-issues"></a>ปัญหาที่ทราบแล้ว

มีปัญหาที่ทราบอยู่แล้วซึ่งคุณจะได้รับข้อความแสดงข้อผิดพลาดหากคุณพยายามเผยแพร่รายงานที่เผยแพร่ก่อนหน้านี้จาก Power BI Desktop ต่อไปนี้คือสถานการณ์สมมติ

1. แอนนามีชุดข้อมูลที่เผยแพร่ไปยังบริการ Power BI และมีการกำหนดค่า RLS แล้ว

1. เมื่อแอนนาทำการปรับปรุงรายงานใน Power BI Desktop และเผยแพร่อีกครั้ง

1. Anna ได้รับข้อผิดพลาด

**แก้ไขปัญหาชั่วคราว:** เผยแพร่ไฟล์ Power BI Desktop จากบริการ Power BI อีกครั้งจนกว่าปัญหานี้ได้รับการแก้ไข คุณสามารถทำได้โดยการเลือก **รับข้อมูล** > **ไฟล์**

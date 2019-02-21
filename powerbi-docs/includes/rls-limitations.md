---
author: mgblythe
ms.service: powerbi
ms.topic: include
ms.date: 02/15/2019
ms.author: mblythe
ms.openlocfilehash: 44ef0aa9d436f3a8a02f9a6b831847d5c996558a
ms.sourcegitcommit: 91ac6185f7026ddbaa925dc54057bb742b4fa411
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/16/2019
ms.locfileid: "56333845"
---
## <a name="limitations"></a>ข้อจำกัด

ต่อไปนี้คือรายการของข้อจำกัดปัจจุบันสำหรับความปลอดภัยระดับแถวบนแบบจำลองคลาวด์

* ถ้าก่อนหน้านี้คุณได้กำหนดบทบาทและกฎในบริการ Power BI แล้ว คุณต้องสร้างขึ้นใหม่ใน Power BI Desktop

* คุณสามารถกำหนด RLS บนชุดข้อมูลที่สร้างขึ้นด้วย Power BI Desktop เท่านั้น ถ้าคุณต้องการเปิดใช้งาน RLS สำหรับชุดข้อมูลที่สร้างขึ้นโดยใช้ Excel คุณจะต้องแปลงไฟล์ของคุณให้เป็นไฟล์ Power BI Desktop (PBIX) ก่อน [เรียนรู้เพิ่มเติม](../desktop-import-excel-workbooks.md)

* ETL และการเชื่อมต่อ DirectQuery เท่านั้นที่ได้รับการสนับสนุน Live connection ไปถึง Analysis Services ได้รับการจัดการในแบบจำลองแบบภายในองค์กร

* ถามตอบและ Cortana ไม่ได้รับการสนับสนุนกับ RLS ในขณะนี้

## <a name="known-issues"></a>ปัญหาที่ทราบแล้ว

มีปัญหาที่ทราบอยู่แล้วซึ่งคุณจะได้รับข้อความแสดงข้อผิดพลาดหากคุณพยายามเผยแพร่รายงานที่เผยแพร่ก่อนหน้านี้จาก Power BI Desktop ต่อไปนี้คือสถานการณ์สมมติ

1. แอนนามีชุดข้อมูลที่เผยแพร่ไปยังบริการ Power BI และมีการกำหนดค่า RLS แล้ว

1. เมื่อแอนนาทำการปรับปรุงรายงานใน Power BI Desktop และเผยแพร่อีกครั้ง

1. Anna ได้รับข้อผิดพลาด

**แก้ไขปัญหาชั่วคราว:** เผยแพร่ไฟล์ Power BI Desktop จากบริการ Power BI อีกครั้งจนกว่าปัญหานี้ได้รับการแก้ไข คุณสามารถทำได้โดยการเลือก **รับข้อมูล** > **ไฟล์**

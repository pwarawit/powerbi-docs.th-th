---
author: davidiseminger
ms.service: powerbi
ms.topic: include
ms.date: 01/31/2020
ms.author: davidi
ms.openlocfilehash: b67025de5e2a70876a31fd42e22c9572403288fa
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "77464420"
---
## <a name="limitations"></a>ข้อจำกัด

ข้อจำกัดปัจจุบันสำหรับการรักษาความปลอดภัยระดับแถวบนโมเดลระบบคลาวด์ มีดังต่อไปนี้:

* ถ้าก่อนหน้านี้คุณได้กำหนดบทบาทและกฎในบริการ Power BI แล้ว คุณต้องสร้างขึ้นใหม่ใน Power BI Desktop

* คุณสามารถกำหนด RLS บนชุดข้อมูลที่สร้างขึ้นด้วย Power BI Desktop เท่านั้น ถ้าคุณต้องการเปิดใช้งาน RLS สำหรับชุดข้อมูลที่สร้างขึ้นโดยใช้ Excel คุณจะต้องแปลงไฟล์ของคุณให้เป็นไฟล์ Power BI Desktop (PBIX) ก่อน [เรียนรู้เพิ่มเติม](../desktop-import-excel-workbooks.md)

* สนับสนุนเฉพาะการนำเข้าและการเชื่อมต่อ DirectQuery เท่านั้น Live connection ไปถึง Analysis Services ได้รับการจัดการในแบบจำลองแบบภายในองค์กร

## <a name="known-issues"></a>ปัญหาที่ทราบแล้ว

มีปัญหาที่รู้จัก ที่คุณจะได้รับข้อความแสดงข้อผิดพลาด หากคุณพยายามเผยแพร่รายงานที่เผยแพร่แล้วก่อนหน้านี้จาก Power BI Desktop ต่อไปนี้คือสถานการณ์สมมติ:

1. แอนนามีชุดข้อมูลที่เผยแพร่ไปยังบริการ Power BI และมีการกำหนดค่า RLS แล้ว

1. เมื่อแอนนาทำการปรับปรุงรายงานใน Power BI Desktop และเผยแพร่อีกครั้ง

1. Anna ได้รับข้อผิดพลาด

**วิธีแก้ปัญหา:** เผยแพร่ไฟล์ Power BI Desktop จากบริการ Power BI อีกครั้งจนกว่าปัญหานี้ได้รับการแก้ไข คุณสามารถทำได้โดยการเลือก **รับข้อมูล** > **ไฟล์**

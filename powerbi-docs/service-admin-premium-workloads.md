---
title: วิธีการกำหนดค่าปริมาณงานใน Power BI Premium
description: เรียนรู้วิธีการกำหนดค่าปริมาณงานในกำลังการผลิตของ Power BI Premium
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/26/2019
LocalizationGroup: Premium
ms.openlocfilehash: 5b9bec67fef672d219b11bf3b3750959e72410b6
ms.sourcegitcommit: 364ffa1178cdfb0a20acffc0fd79922ebc892d72
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/02/2019
ms.locfileid: "57226077"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>กำหนดค่าปริมาณงานในกำลังการผลิตแบบ Premium

บทความนี้อธิบายเกี่ยวกับการเปิดใช้งาน และกำหนดปริมาณงานสำหรับกำลังการผลิตแบบ Power BI Premium ตามค่าเริ่มต้น กำลังการผลิตที่สนับสนุนเฉพาะปริมาณงานที่เชื่อมโยงกับการเรียกใช้คิวรี Power BI ปริมาณงานคิวรีจะเหมาะสมและจำกัดตามทรัพยากรที่ขึ้นอยู่กับกำลังการผลิตของ SKU Premium ของคุณ กำลังการผลิตของ premium ยังรองรับปริมาณงานเพิ่มเติมที่สามารถใช้ capacity resources ได้ด้วย

## <a name="configure-workloads"></a>กำหนดค่าปริมาณงาน

คุณสามารถเปิดใช้งาน และกำหนดค่าปริมาณงานเพิ่มเติมสำหรับ[Dataflows](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium)และ[แบ่งรายงาน](paginated-reports-save-to-power-bi-service.md)ได้ เริ่มต้นค่าหน่วยความจำสำหรับปริมาณงานเหล่านี้จะยึดโหนดความจุพร้อมใช้งานสำหรับ SKU ของคุณ ตั้งค่าหน่วยความจำสูงสุดไม่สะสม หน่วยความจำสูงสุดค่าสูงสุดที่ระบุเป็นการจัดสรรแบบไดนามิกสำหรับ dataflows แต่สาธิตจัดไว้สำหรับรายงานแบบแบ่งหน้า 

### <a name="to-configure-workloads-in-the-power-bi-admin-portal"></a>เปิดใช้ปริมาณงานในพอร์ทัลผู้ดูแลระบบของ Power BI

1. ใน**ตั้งค่ากำลังการผลิต** > **กำลังการผลิตแบบ PREMIUM**เลือกความจุ

1. ขยาย**ปริมาณงาน**ที่ใต้ **ตัวเลือกเพิ่มเติม**

1. เปิดใช้งานปริมาณงานอย่างน้อยหนึ่งตัว และตั้งค่าสำหรับ **ความจำสูงสุด**   

    
    ![เปิดใช้งานปริมาณงาน](media/service-admin-premium-workloads/admin-portal-workloads.png)

1. คลิก**ใช้**

> [!NOTE]
> ถ้ามีการใช้ปริมาณงานของรายงานแบบแบ่งหน้า ระลึกไว้ว่ารายงานแบบแบ่งหน้าช่วยให้คุณสามารถเรียกใช้โค้ดของคุณเองได้เมื่อทำการสร้างรายงาน (เช่น การเปลี่ยนสีข้อความจำนวนมากตามเนื้อหา) Power BI Premium เรียกใช้รายงานแบบแบ่งหน้ามีช่องว่างที่มีอยู่ภายในกำลังการผลิต เรากำหนดหน่วยความจำสูงสุดที่คุณระบุไว้ในช่องว่างนี้ ไม่ว่าจะใช้ปริมาณงานอยู่หรือไม่ ถ้าคุณใช้รายงาน Power BI หรือกระแสข้อมูลในความจุเดียวกัน ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าหน่วยความจำให้ต่ำพอสำหรับรายงานแบบแบ่งหน้า โดยจะไม่ส่งผลกระทบในเชิงลบกับปริมาณงานอื่นๆ ในบางกรณีที่หาได้ยาก ปริมาณงานของรายงานแบบแบ่งหน้าอาจไม่พร้อมใช้งาน ในกรณีเช่นนี้ ปริมาณงานจะแสดงสถานะข้อผิดพลาดในพอร์ทัลผู้ดูแลระบบ และผู้ใช้จะเห็นการหมดเวลาในการสร้างรายงาน เพื่อเป็นการลดปัญหานี้ ให้คุณปิดใช้งานปริมาณงานแล้วเปิดใช้งานอีกครั้ง


### <a name="rest-api"></a>REST API

ปริมาณงานคุณสามารถเปิดใช้งาน และกำหนดความจุ โดยใช้[Capacitie](https://docs.microsoft.com/rest/api/power-bi/capacities)REST APIs


## <a name="next-steps"></a>ขั้นตอนถัดไป

[การจัดการ Power BI Premium capacity resource และการปรับให้เหมาะสม](service-premium-understand-how-it-works.md)   
[เตรียมข้อมูลด้วยตนเองใน Power BI ด้วย Dataflows](service-dataflows-overview.md)   
[รายงานแบบแบ่งหน้าใน Power BI Premium คืออะไร](paginated-reports-report-builder-power-bi.md)   

มีคำถามเพิ่มเติมหรือไม่? [ถามชุมชน Power BI](http://community.powerbi.com/)
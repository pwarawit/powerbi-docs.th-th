---
title: ใช้ DirectQuery ด้วยกระแสข้อมูลใน Power BI (ตัวอย่าง)
description: ใช้ DirectQuery ด้วยกระแสข้อมูลใน Power BI
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/19/2020
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 9de8c9611b24eaa627b3ddf044f13d36d7b9a3d4
ms.sourcegitcommit: 250242fd6346b60b0eda7a314944363c0bacaca8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/20/2020
ms.locfileid: "83694584"
---
# <a name="use-directquery-with-dataflows-in-power-bi-preview"></a>ใช้ DirectQuery ด้วยกระแสข้อมูลใน Power BI (ตัวอย่าง)

คุณสามารถใช้ DirectQuery เพื่อเชื่อมต่อโดยตรงไปยังกระแสข้อมูล และเชื่อมต่อโดยตรงกับกระแสข้อมูลของคุณโดยไม่ต้องนำเข้าข้อมูล 

การใช้ DirectQuery กับกระแสข้อมูลช่วยให้สามารถปรับปรุงขั้นตอนต่อไปนี้ในกระบวนการ Power BI และกระแสข้อมูลของคุณได้เช่น:

* **หลีกเลี่ยงการกำหนดตารางเวลาการรีเฟรชแยกต่างหาก**-DirectQuery เชื่อมต่อโดยตรงกับกระแสข้อมูลโดยไม่จำเป็นต้องสร้างชุดข้อมูล เช่นเดียวกับการใช้ DirectQuery ด้วยกระแสข้อมูลของคุณหมายความว่าคุณไม่จำเป็นต้องกำหนดตารางเวลาการรีเฟรชแยกต่างหากสำหรับกระแสข้อมูลและชุดข้อมูล เพื่อให้แน่ใจว่าข้อมูลของคุณจะถูกซิงโครไนซ์

* **การกรองข้อมูล**- DirectQuery มีประโยชน์สำหรับการทำงานบนมุมมองที่กรองแล้วของข้อมูลภายในกระแสข้อมูล ถ้าคุณต้องการกรองข้อมูลและทำงานกับชุดย่อยของข้อมูลที่มีขนาดเล็กลงในกระแสข้อมูลของคุณ คุณสามารถใช้ DirectQuery (และโปรแกรมคำนวณ) เพื่อกรองข้อมูลของกระแสข้อมูล และทำงานกับชุดย่อยที่กรองแล้วที่คุณต้องการ


## <a name="using-directquery-for-dataflows"></a>การใช้ DirectQuery สำหรับกระแสข้อมูล

การใช้ DirectQuery ด้วยกระแสข้อมูลคือคุณลักษณะตัวอย่างที่พร้อมใช้งานเริ่มตั้งแต่ Power BI Desktop รุ่นเดือนพฤษภาคม 2020 

นอกจากนี้ ยังมีข้อกำหนดเบื้องต้นสำหรับการใช้ DirectQuery กับกระแสข้อมูล:

* กระแสข้อมูลของคุณต้องอยู่ภายในพื้นที่ทำงานที่เปิดใช้ Power BI Premium
* ต้องเปิดใช้งาน**โปรแกรมคำนวณ** สำหรับข้อมูลเพิ่มเติมเกี่ยวกับโปรแกรมการคำนวณ ให้ดู [โปรแกรมการคำนวณขั้นสูง ](service-dataflows-enhanced-compute-engine.md)

## <a name="enable-directquery-for-dataflows"></a>เปิดใช้งาน DirectQuery สำหรับกระแสข้อมูล

เพื่อให้แน่ใจว่ากระแสข้อมูลของคุณพร้อมใช้งานสำหรับการเข้าถึง DirectQuery โปรแกรมการคำนวณขั้นสูงจะต้องอยู่ในสถานะที่ปรับให้เหมาะสมแล้ว เมื่อต้องการเปิดใช้งาน DirectQuery สำหรับกระแสข้อมูล ให้ตั้งค่าตัวเลือก **การตั้งค่าโปรแกรมการคำนวณขั้นสูง**ใหม่เป็น **ปรับให้เหมาะสมแล้ว** รูปภาพต่อไปนี้แสดงการตั้งค่าที่เลือกอย่างถูกต้อง

![เปิดใช้งานโปรแกรมการคำนวณขั้นสูงสำหรับกระแสข้อมูล](media/service-dataflows-directquery/dataflows-directquery-01.png)

เมื่อคุณใช้การตั้งค่าดังกล่าว ให้รีเฟรชกระแสข้อมูลเพื่อทำให้การปรับให้เหมาะสมมีผล 


## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด

มีข้อจำกัดที่เป็นที่รู้กันสองสามประการในเรื่องของ DirectQuery และกระแสข้อมูล ซึ่งจะอธิบายไว้ในรายการต่อไปนี้

* DirectQuery สำหรับกระแสข้อมูลไม่ทำงานกับการเปิดใช้งาน**คุณลักษณะการแสดงตัวอย่างเมตาดาต้าขั้นสูง** คาดว่าจะมีการยกเลิกคุณลักษณะนี้ใน Power BI Desktop รายเดือนที่กำลังจะมาถึง
* ในระหว่างช่วงเวลาการแสดงตัวอย่างของคุณลักษณะนี้ ลูกค้าบางรายอาจพบปัญหาเกี่ยวกับการหมดเวลา หรือประสิทธิภาพการทำงานเมื่อใช้ DirectQuery กับกระแสข้อมูล ปัญหาดังกล่าวจะได้รับการแก้ไขในระหว่างช่วงเวลาการแสดงตัวอย่างนี้


## <a name="next-steps"></a>ขั้นตอนถัดไป

บทความต่อไปนี้มีประโยชน์ในการศึกษาข้อมูลเพิ่มเติมและสถานการณ์ต่างๆ เมื่อใช้กระแสข้อมูล:

* [การเตรียมข้อมูลด้วยตัวเองโดยใช้กระแสข้อมูล](service-dataflows-overview.md)
* [การใช้เอนทิตีที่คำนวณใน Power BI Premium](service-dataflows-computed-entities-premium.md)
* [การใช้กระแสข้อมูลกับแหล่งข้อมูลภายในองค์กร](service-dataflows-on-premises-gateways.md)
* [แหล่งข้อมูลของนักพัฒนาสำหรับกระแสข้อมูล Power BI](service-dataflows-developer-resources.md)
* [ การรวมกระแสข้อมูลและ Azure Data Lake (ตัวอย่าง)](service-dataflows-azure-data-lake-integration.md)

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ Common Data Model สามารถดูได้ในบทความภาพรวม:
* [Common Data Model - ภาพรวม](https://docs.microsoft.com/powerapps/common-data-model/overview)
* [เรียนรู้เพิ่มเติมเกี่ยวกับเค้าร่าง Common Data Model และเอนทิตีบน GitHub](https://github.com/Microsoft/CDM)

บทความ Power BI Desktop ที่เกี่ยวข้อง:

* [เชื่อมต่อชุดข้อมูลในบริการของ Power BI จาก Power BI Desktop](../connect-data/desktop-report-lifecycle-datasets.md)
* [ภาพรวมคิวรีใน Power BI Desktop](desktop-query-overview.md)

บทความบริการของ Power BI ที่เกี่ยวข้อง:
* [การกำหนดค่าการรีเฟรชตามกำหนดการ](../connect-data/refresh-scheduled-refresh.md)

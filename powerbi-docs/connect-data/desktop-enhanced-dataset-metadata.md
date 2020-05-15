---
title: การใช้เมตาดาต้าชุดข้อมูลที่ปรับปรุงใน Power BI Desktop (ตัวอย่าง)
description: บทความนี้อธิบายวิธีการใช้เมตาดาต้าชุดข้อมูลที่ปรับปรุงประสิทธิภาพแล้วใน Power BI
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 03/31/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 87b4be55b1b811f63dbb7fe271bc3c3fa4af2755
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83347435"
---
# <a name="using-enhanced-dataset-metadata-preview"></a>การใช้เมตาดาต้าชุดข้อมูลที่ปรับปรุงประสิทธิภาพแล้ว (ตัวอย่าง)

เมื่อ Power BI Desktop สร้างรายงาน จะมีการสร้างเมตาดาต้าชุดข้อมูลในไฟล์ PBIX และ PBIT ที่เกี่ยวข้องกันด้วย ก่อนหน้านี้ มีการจัดเก็บเมตาดาต้าในรูปแบบที่เฉพาะเจาะจงไปยัง Power BI Desktop ใช้นิพจน์ M และแหล่งข้อมูลที่เข้ารหัส 64 และสมมติฐานที่ทำเกี่ยวกับวิธีการจัดเก็บเมตาดาต้า

ด้วยการเผยแพร่คุณลักษณะ**เมตาดาต้าชุดข้อมูลที่ปรับปรุงประสิทธิภาพแล้ว** ข้อจำกัดมากมายเหล่านี้จึงถูกกำจัดออกไป ด้วยการเปิดใช้งานคุณลักษณะ**เมตาดาต้าชุดข้อมูลที่ปรับปรุงประสิทธิภาพแล้ว** เมตาดาต้าที่สร้างโดย Power BI Desktop จะใช้รูปแบบที่คล้ายคลึงกับรูปแบบที่ใช้สำหรับแบบจำลองตาราง Analysis Services โดยยึดตาม[แบบจำลองออบเจ็กต์ตาราง](https://docs.microsoft.com/bi-reference/tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo)


คุณลักษณะ**เมตาดาต้าชุดข้อมูลที่ปรับปรุงประสิทธิภาพแล้ว**เป็นข้อมูลเชิงกลยุทธ์และพื้นฐาน เนื่องจากฟังก์ชัน Power BI ในอนาคตจะสร้างขึ้นตามเมตาดาต้าของฟังก์ชันดังกล่าว ความสามารถเพิ่มเติมบางอย่างที่จะได้รับประโยชน์จากเมตาดาต้าชุดข้อมูลที่ปรับปรุงประสิทธิภาพแล้วรวมถึง [อ่าน/เขียน XMLA](https://docs.microsoft.com/power-platform-release-plan/2019wave2/business-intelligence/xmla-readwrite) สำหรับการจัดการของชุดข้อมูล Power BI และการย้ายปริมาณงาน Analysis Services ไปยัง Power BI เพื่อให้ได้ประโยชน์จากคุณลักษณะที่พัฒนาขึ้นใหม่



## <a name="enable-enhanced-dataset-metadata"></a>เปิดใช้งานเมตาดาต้าชุดข้อมูลที่ปรับปรุงประสิทธิภาพแล้ว

คุณลักษณะ **เมตาดาต้าชุดข้อมูลที่ปรับปรุงประสิทธิภาพแล้ว** ขณะนี้อยู่ในตัวอย่าง เมื่อต้องการเปิดใช้งานเมตาดาต้าชุดข้อมูลที่ปรับปรุงประสิทธิภาพแล้ว ใน Power BI Desktop ให้เลือกตัวเลือก **ไฟล์> ตัวเลือกและการตั้งค่า> ตัวเลือก> คุณลักษณะตัวอย่าง** จากนั้นเลือกกล่องกาเครื่องหมาย **จัดเก็บชุดข้อมูลโดยใช้รูปแบบเมตาดาต้าที่ปรับปรุงประสิทธิภาพแล้ว** ดังที่แสดงในรูปต่อไปนี้ 

![เปิดใช้งานคุณลักษณะตัวอย่าง](media/desktop-enhanced-dataset-metadata/enhanced-dataset-metadata-01.png)

คุณจะได้รับพร้อมท์แจ้งให้รีสตาร์ท Power BI Desktop

![พร้อมท์แจ้งให้รีสตาร์ท](media/desktop-enhanced-dataset-metadata/enhanced-dataset-metadata-02.png)

เมื่อเปิดใช้งานคุณลักษณะตัวอย่าง Power BI Desktop พยายามอัปเกรดไฟล์ PBIX และ PBIT ที่ใช้รูปแบบเมตาดาต้าก่อนหน้า 

> [!IMPORTANT]
> การเปิดใช้งานคุณลักษณะ **เมตาดาต้าชุดข้อมูลที่ปรับปรุงประสิทธิภาพแล้ว** ส่งผลในการอัปเกรดที่ย้อนกลับไม่ได้ในรายงาน รายงาน Power BI ใดๆ ที่โหลดหรือสร้างขึ้นด้วย Power BI Desktop เมื่อมีการเปิดใช้งาน **เมตาดาต้าชุดข้อมูลที่ปรับปรุงประสิทธิภาพแล้ว** รายงานนั้นจะถูกแปลงกลับไปเป็นเมตาดาต้าชุดข้อมูลที่ปรับปรุงประสิทธิภาพแล้ว

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด

ในเวอร์ชันตัวอย่าง ข้อจำกัดต่อไปนี้จะนำไปใช้เมื่อเปิดใช้งานคุณลักษณะตัวอย่าง

### <a name="unsupported-features-and-connectors"></a>คุณลักษณะและตัวเชื่อมต่อที่ไม่รองรับ
เมื่อเปิดไฟล์ PBIX หรือ PBIT ที่มีอยู่ซึ่งยังไม่ได้รับการอัปเกรด การอัปเกรดจะล้มเหลวถ้าชุดข้อมูลประกอบด้วยคุณลักษณะหรือตัวเชื่อมต่อเหล่านี้ ถ้าเกิดความล้มเหลวดังกล่าว ไม่ควรส่งผลกระทบต่อประสบการณ์ของผู้ใช้ทันทีและ Power BI Desktop ยังคงใช้รูปแบบเมตาดาต้าก่อนหน้านี้

* สคริปต์ Python
* ตัวเชื่อมต่อแบบกำหนดเอง
* Azure DevOps Server
* BI Connector
* Denodo
* Dremio
* Exasol
* Indexima
* IRIS
* Jethro ODBC
* Kyligence Enterprise
* Mark Logic ODBC
* Qubole Presto
* Team Desk
* นิพจน์ M ที่มีการผสมอักขระบางอย่าง เช่น “\\n” ในชื่อคอลัมน์
* เมื่อใช้ชุดข้อมูลที่มีการเปิดใช้งานคุณลักษณะ **เมตาดาต้าชุดข้อมูลที่ปรับปรุงประสิทธิภาพแล้ว** คุณไม่สามารถตั้งค่าแหล่งข้อมูล Single Sign On (SSO) ในบริการ Power BI

นอกจากนี้ ไฟล์ PBIX และ PBIT ที่ได้รับการอัปเกรดเรียบร้อยแล้วเพื่อใช้ **เมตาดาต้าชุดข้อมูลที่ปรับปรุงประสิทธิภาพแล้ว** *ไม่สามารถ* ใช้คุณลักษณะหรือตัวเชื่อมต่อข้างต้นในเวอร์ชันปัจจุบันได้

### <a name="lineage-view"></a>มุมมองสายข้อมูล
ชุดข้อมูลที่ใช้รูปแบบเมตาดาต้าใหม่ในขณะนี้ไม่แสดงลิงก์ไปยังกระแสข้อมูลในมุมมองสายข้อมูลในบริการของ Power BI

## <a name="next-steps"></a>ขั้นตอนถัดไป

คุณสามารถทำการเรียงลำดับของของต่างๆ ด้วย Power BI Desktop สำหรับข้อมูลเพิ่มเติมเกี่ยวกับขีดความสามารถ กรุณาดูแหล่งทรัพยากรต่อไปนี้:

* [Power BI Desktop คืออะไร](../fundamentals/desktop-what-is-desktop.md)
* [มีอะไรใหม่ใน Power BI Desktop บ้าง](../fundamentals/desktop-latest-update.md)
* [ภาพรวมคำถามด้วย Power BI Desktop](../transform-model/desktop-query-overview.md)
* [ชนิดข้อมูลใน Power BI Desktop](desktop-data-types.md)
* [จัดรูปร่างและรวมข้อมูลด้วย Power BI Desktop](desktop-shape-and-combine-data.md)
* [งานแบบสอบถามทั่วไปใน Power BI Desktop](../transform-model/desktop-common-query-tasks.md)
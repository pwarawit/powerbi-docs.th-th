---
title: เปิดใช้งานป้ายชื่อระดับความลับใน Power BI
description: เรียนรู้วิธีการเปิดใช้งานป้ายชื่อระดับความลับใน Power BI
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-eim
ms.topic: how-to
ms.date: 07/06/2020
ms.author: painbar
LocalizationGroup: Data from files
ms.openlocfilehash: 0fe1b7b1b8175511838005b7b63ca7543bbf939a
ms.sourcegitcommit: 181679a50c9d7f7faebcca3a3fc55461f594d9e7
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/07/2020
ms.locfileid: "86034347"
---
# <a name="enable-sensitivity-labels-in-power-bi"></a>เปิดใช้งานป้ายชื่อระดับความลับใน Power BI

เพื่อให้มีการใช้ [ป้ายชื่อระดับความลับของ Microsoft Information Protection](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) ใน Power BI ป้ายชื่อดังกล่าวจะต้องเปิดใช้งานบนผู้เช่า บทความนี้แสดงให้เห็นว่าผู้ดูแลระบบผู้เช่า Power BI จะดำเนินการเช่นนั้นได้อย่างไร สำหรับภาพรวมเกี่ยวกับป้ายชื่อระดับความลับใน Power BI โปรดดู [ป้ายชื่อระดับความลับใน Power BI](service-security-sensitivity-label-overview.md) สำหรับข้อมูลเกี่ยวกับการใช้ป้ายชื่อระดับความลับใน Power BI โปรดดู [การใช้ป้ายชื่อระดับความลับ](./service-security-apply-data-sensitivity-labels.md) 

เมื่อเปิดใช้งานป้ายชื่อระดับความลับ:

* ผู้ใช้และกลุ่มความปลอดภัยที่ระบุในองค์กรสามารถจัดประเภทและ [นำป้ายชื่อระดับความลับ](./service-security-apply-data-sensitivity-labels.md) ไปใช้ในรายงาน Power BI แดชบอร์ด ชุดข้อมูล และกระแสข้อมูล
* สมาชิกทั้งหมดขององค์กรสามารถดูป้ายชื่อเหล่านั้นได้

การเปิดใช้งานป้ายชื่อระดับความลับจำเป็นต้องมีสิทธิ์การใช้งาน Azure Information Protection โปรดดู [การให้สิทธิการใช้งาน](service-security-sensitivity-label-overview.md#licensing) สำหรับรายละเอียดเพิ่มเติม

## <a name="enable-sensitivity-labels"></a>เปิดใช้งานป้ายชื่อระดับความลับ

ไปที่ **พอร์ทัลผู้ดูแลระบบ Power BI**  ให้เปิดบานหน้าต่าง **การตั้งค่าผู้เช่า** และค้นหาส่วน **การป้องกันข้อมูล**

![ค้นหาส่วน Information Protection](media/service-security-enable-data-sensitivity-labels/enable-data-sensitivity-labels-01.png)

ในส่วน **Information Protection** ให้ดำเนินการขั้นตอนต่อไปนี้:
1. เปิด **อนุญาตให้ผู้ใช้นำป้ายชื่อระดับความลับไปใช้สำหรับเนื้อหา Power BI**
1. เปิดใช้งานตัวสลับ
1. กำหนดบุคคลที่สามารถใช้และเปลี่ยนแปลงป้ายชื่อระดับความลับในแอสเซท Power BI ได้ ตามค่าเริ่มต้น ทุกคนในองค์กรของคุณจะสามารถใช้ป้ายชื่อระดับความลับได้ อย่างไรก็ตาม คุณสามารถเลือกที่จะเปิดใช้งานการตั้งค่าป้ายชื่อระดับความลับเฉพาะสำหรับผู้ใช้หรือกลุ่มความปลอดภัยที่เฉพาะเจาะจงได้ เมื่อเลือกทั้งองค์กรหรือกลุ่มความปลอดภัยที่เฉพาะเจาะจง คุณสามารถยกเว้นชุดย่อยของผู้ใช้หรือกลุ่มความปลอดภัยที่เฉพาะเจาะจงได้
   
   * เมื่อมีการเปิดใช้งานป้ายชื่อระดับความลับสำหรับทั้งองค์กร โดยทั่วไปจะมีการยกเว้นกลุ่มความปลอดภัย
   * เมื่อมีการเปิดใช้งานป้ายชื่อระดับความลับเฉพาะสำหรับผู้ใช้หรือกลุ่มความปลอดภัยที่เฉพาะเจาะจง โดยทั่วไปจะมีการยกเว้นผู้ใช้ที่เฉพาะเจาะจง  
    วิธีการนี้จะทำให้สามารถป้องกันไม่ให้ผู้ใช้บางรายนำป้ายชื่อระดับความลับใน Power BI ไปใช้งาน ถึงแม้ว่าพวกเขาจะเป็นสมาชิกของกลุ่มที่มีสิทธิ์ในการทำเช่นนั้นก็ตาม

1. กด **นำไปใช้**

![เปิดใช้งานป้ายชื่อระดับความลับ](media/service-security-enable-data-sensitivity-labels/enable-data-sensitivity-labels-02.png)

> [!IMPORTANT]
> เฉพาะผู้ใช้ Power BI Pro เท่านั้นที่มีสิทธิ์ *สร้าง* และ *แก้ไข* ในแอสเซท และผู้ที่เป็นส่วนหนึ่งของกลุ่มความปลอดภัยที่เกี่ยวข้องที่ตั้งค่าในส่วนนี้จะสามารถตั้งค่าและแก้ไขป้ายชื่อระดับความลับได้ ผู้ใช้ที่ไม่ได้เป็นส่วนหนึ่งของกลุ่มนี้จะไม่สามารถตั้งค่า หรือแก้ไขป้ายชื่อได้  

## <a name="troubleshooting"></a>การแก้ไขปัญหา

Power BI ใช้ป้ายชื่อระดับความลับ Microsoft Information Protection ดังนั้นถ้าคุณพบข้อผิดพลาดเมื่อพยายามเปิดใช้งานป้ายชื่อระดับความลับ อาจเป็นเพราะหนึ่งในสาเหตุต่อไปนี้:

* คุณไม่มี[สิทธิ์การใช้งาน](service-security-sensitivity-label-overview.md#licensing) Azure Information Protection
* ไม่มีการโยกย้ายป้ายชื่อระดับความลับไปยังเวอร์ชัน Microsoft Information Protection ที่สนับสนุนโดย Power BI เรียนรู้เพิ่มเติมเกี่ยวกับ [การโยกย้ายป้ายชื่อระดับความลับ](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)
* ไม่ได้มีการกำหนดป้ายชื่อระดับความลับ Microsoft Information Protection ในองค์กร โปรดทราบว่าเพื่อให้สามารถใช้งานได้ ป้ายชื่อจะต้องเป็นส่วนหนึ่งของนโยบายที่เผยแพร่แล้ว จึงจะสามารถใช้ได้ [เรียนรู้เพิ่มเติมเกี่ยวกับป้ายชื่อระดับความลับ](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels) หรือเยี่ยมชม [ศูนย์ความปลอดภัยและการปฏิบัติตามข้อกำหนดของ Microsoft](https://sip.protection.office.com/sensitivity?flight=EnableMIPLabels) เพื่ออ่านข้อมูลเกี่ยวกับวิธีการกำหนดป้ายชื่อและเผยแพร่นโยบายสำหรับองค์กรของคุณ

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด

ดู [ป้ายชื่อระดับความลับใน Power BI](service-security-sensitivity-label-overview.md#limitations) สำหรับรายการขีดจำกัดของป้ายชื่อระดับความลับใน Power BI

## <a name="next-steps"></a>ขั้นตอนถัดไป

บทความนี้อธิบายวิธีการเปิดใช้งานป้ายชื่อระดับความลับใน Power BI บทความต่อไปนี้แสดงรายละเอียดเพิ่มเติมเกี่ยวกับการป้องกันข้อมูลใน Power BI 

* [ภาพรวมของป้ายชื่อระดับความลับใน Power BI](service-security-sensitivity-label-overview.md)
* [วิธีการใช้ป้ายชื่อระดับความลับใน Power BI](../collaborate-share/service-security-apply-data-sensitivity-labels.md)
* [ใช้ตัวควบคุม Microsoft Cloud App Security ใน Power BI](service-security-using-microsoft-cloud-app-security-controls.md)
* [รายงานเมตริกการป้องกัน](service-security-data-protection-metrics-report.md)
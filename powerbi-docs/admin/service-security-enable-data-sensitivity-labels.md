---
title: เปิดใช้งานป้ายชื่อระดับความลับใน Power BI
description: เรียนรู้วิธีการเปิดใช้งานป้ายชื่อระดับความลับใน Power BI
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-eim
ms.topic: how-to
ms.date: 08/10/2020
ms.author: painbar
LocalizationGroup: Data from files
ms.openlocfilehash: ebc4601f3575e84c248aef9204537a7d93c428ac
ms.sourcegitcommit: 9e39232cbc28d8b39dfec5496db7ece9837b5e53
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/10/2020
ms.locfileid: "88049195"
---
# <a name="enable-sensitivity-labels-in-power-bi"></a>เปิดใช้งานป้ายชื่อระดับความลับใน Power BI

เพื่อให้มีการใช้ [ป้ายชื่อระดับความลับของ Microsoft Information Protection](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) ใน Power BI ป้ายชื่อดังกล่าวจะต้องเปิดใช้งานบนผู้เช่า บทความนี้แสดงให้เห็นว่าผู้ดูแลระบบผู้เช่า Power BI จะดำเนินการเช่นนั้นได้อย่างไร สำหรับภาพรวมเกี่ยวกับป้ายชื่อระดับความลับใน Power BI โปรดดู [ป้ายชื่อระดับความลับใน Power BI](service-security-sensitivity-label-overview.md) สำหรับข้อมูลเกี่ยวกับการใช้ป้ายชื่อระดับความลับใน Power BI โปรดดู [การใช้ป้ายชื่อระดับความลับ](./service-security-apply-data-sensitivity-labels.md) 

เมื่อเปิดใช้งานป้ายชื่อระดับความลับ:

* ผู้ใช้และกลุ่มความปลอดภัยที่ระบุในองค์กรสามารถจัดประเภทและ [นำป้ายชื่อระดับความลับ](./service-security-apply-data-sensitivity-labels.md) ไปใช้ในรายงาน Power BI แดชบอร์ด ชุดข้อมูล และกระแสข้อมูล
* สมาชิกทั้งหมดขององค์กรสามารถดูป้ายชื่อเหล่านั้นได้

การเปิดใช้งานป้ายชื่อระดับความลับจำเป็นต้องมีสิทธิ์การใช้งาน Azure Information Protection ดู [ใบอนุญาตใช้งานและข้อกำหนด](#licensing-and-requirements) สำหรับรายละเอียด

## <a name="licensing-and-requirements"></a>การอนุญาตใช้งานและสิ่งที่ต้องการ

* จำเป็นต้องมีใบอนุญาตใช้งานความคุ้มครองข้อมูล Azure Premium P1 หรือ Premium P2 เพื่อใช้หรือดูป้ายระดับความลับของความคุ้มครองข้อมูลของ Microsoft ใน Power BI ความคุ้มครองข้อมูลของ Azure สามารถซื้อได้ทั้งแบบสแตนด์อโลนหรือผ่านชุดการออกใบอนุญาตใช้งานของ Microsoft ดู [การกำหนดราคา Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection/) สำหรับรายละเอียด

* ในการใช้ป้ายกำกับกับเนื้อหา Power BI ผู้ใช้ต้องมีใบอนุญาตใช้งาน Power BI Pro นอกเหนือจากสิทธิ์การใช้งานความคุ้มครองข้อมูลของ Azure ที่กล่าวถึงข้างต้น

* แอป Office มี [ข้อกำหนดสิทธิ์การใช้งานสำหรับการดูและใช้ป้ายชื่อระดับความลับ]( https://docs.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels#subscription-and-licensing-requirements-for-sensitivity-labels ) ของตัวเอง

* ก่อนเปิดใช้งานป้ายชื่อระดับความลับสำหรับผู้เช่าของคุณ ให้ตรวจสอบให้แน่ใจว่าได้กำหนดและเผยแพร่ให้สำหรับผู้ใช้และกลุ่มที่เกี่ยวข้องแล้ว ดู [สร้างและกำหนดค่าป้ายชื่อระดับความลับและนโยบาย](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels?view=o365-worldwide) สำหรับรายละเอียด

>[!NOTE]
> หากองค์กรของคุณใช้ป้ายชื่อระดับความลับของความคุ้มครองข้อมูลของ Azure จำเป็นต้องโยกย้ายไปยังแพลตฟอร์มความคุ้มครองข้อมูลการติดป้ายชื่อแบบรวมของ Microsoft เพื่อให้ใช้ใน Power BI ได้ [เรียนรู้เพิ่มเติมเกี่ยวกับการย้ายป้ายชื่อระดับความลับ](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels)

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

* คุณไม่มี[สิทธิ์การใช้งาน](#licensing-and-requirements) Azure Information Protection
* ป้ายชื่อระดับความลับยังไม่ได้รับการ [ย้ายข้อมูล](#enable-sensitivity-labels) ไปยังเวอร์ชันความคุ้มครองข้อมูลของ Microsoft ที่รองรับโดย Power BI
* ไม่มีป้ายชื่อระดับความลับความคุ้มครองข้อมูลของ Microsoft ถูก [กำหนดไว้ในองค์กร](#enable-sensitivity-labels)

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด

ดู [ป้ายชื่อระดับความลับใน Power BI](service-security-sensitivity-label-overview.md#limitations) สำหรับรายการขีดจำกัดของป้ายชื่อระดับความลับใน Power BI

## <a name="next-steps"></a>ขั้นตอนถัดไป

บทความนี้อธิบายวิธีการเปิดใช้งานป้ายชื่อระดับความลับใน Power BI บทความต่อไปนี้แสดงรายละเอียดเพิ่มเติมเกี่ยวกับการป้องกันข้อมูลใน Power BI 

* [ภาพรวมของป้ายชื่อระดับความลับใน Power BI](service-security-sensitivity-label-overview.md)
* [วิธีการใช้ป้ายชื่อระดับความลับใน Power BI](../collaborate-share/service-security-apply-data-sensitivity-labels.md)
* [ใช้ตัวควบคุม Microsoft Cloud App Security ใน Power BI](service-security-using-microsoft-cloud-app-security-controls.md)
* [รายงานเมตริกการป้องกัน](service-security-data-protection-metrics-report.md)
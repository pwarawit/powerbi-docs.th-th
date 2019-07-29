---
title: การแจ้งเตือนการหยุดชะงักของบริการ
description: เรียนรู้เกี่ยวกับวิธีการรับการแจ้งเตือนทางอีเมลเมื่อบริการของ Power BI หยุดทำงานหรือลดประสิทธิภาพ
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 07/19/2019
ms.author: mblythe
ms.openlocfilehash: 0bb78e29cc3e9b9792d5916050179703281aa01a
ms.sourcegitcommit: 850e7883e21190151684e32f4d957beecd08e959
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/20/2019
ms.locfileid: "68366760"
---
# <a name="service-interruption-notifications"></a>การแจ้งเตือนการหยุดชะงักของบริการ

สิ่งสำคัญคือต้องมีข้อมูลเชิงลึกเกี่ยวกับความพร้อมใช้งานของแอปพลิเคชันทางธุรกิจที่สำคัญสำหรับภารกิจของคุณ Power BI มีการแจ้งเตือนเหตุการณ์เพื่อให้คุณสามารถเลือกรับอีเมลได้ถ้ามีการหยุดทำงานหรือการลดประสิทธิภาพของบริการ ในขณะที่ข้อตกลงระดับบริการของ Power BI (SLA) อยู่ที่ 99.9% ทำให้เกิดเหตุการณ์เหล่านี้ไม่บ่อย แต่เราต้องการให้แน่ใจว่าคุณได้รับแจ้งให้ทราบ หน้าจอต่อไปนี้แสดงชนิดของอีเมลที่คุณจะได้รับถ้าคุณเปิดใช้งานการแจ้งเตือน:

![รีเฟรชอีเมลแจ้งเตือน](media/service-interruption-notifications/refresh-notification-email.png)

ในตอนนี้ เราจะส่งอีเมลสำหรับ_สถานการณ์ความน่าเชื่อถือ_ดังต่อไปนี้:

- เปิดความน่าเชื่อถือของรายงาน
- ความน่าเชื่อถือของการรีเฟรชแบบจำลอง
- ความน่าเชื่อถือของการรีเฟรชคิวรี

หลังจากที่มีการแก้ไขปัญหาแล้ว คุณจะได้รับอีเมลการติดตามผล

> [!NOTE]
> ปัจจุบัน คุณลักษณะนี้พร้อมใช้งานสำหรับความจุเฉพาะใน Power BI Premium เท่านั้น ซึ่งไม่พร้อมใช้งานสำหรับความจุที่ใช้ร่วมกัน

## <a name="enable-notifications"></a>เปิดใช้งานการแจ้งเตือน

ผู้ดูแลระบบผู้เช่า Power BI จะเปิดใช้งานการแจ้งเตือนในพอร์ทัลผู้ดูแลระบบ:

1. ระบุหรือสร้างกลุ่มความปลอดภัยที่เปิดใช้งานอีเมลซึ่งควรได้รับการแจ้งเตือน

1. ในพอร์ทัลผู้ดูแลระบบ ให้เลือก**การตั้งค่าผู้เช่า** ภายใต้**วิธีใช้และการตั้งค่าการสนับสนุน** ขยาย**รับการแจ้งเตือนทางอีเมลสำหรับบริการขัดข้องหรือเหตุการณ์**

1. เปิดใช้งานการแจ้งเตือน ให้ใส่กลุ่มความปลอดภัยและเลือก **นำไปใช้**

    ![เปิดใช้งานการแจ้งเตือนบริการ](media/service-interruption-notifications/enable-notifications.png)

> [!NOTE]
> Power BI ส่งการแจ้งเตือนจากบัญชีno-reply-powerbi@microsoft.com ตรวจสอบให้แน่ใจว่าบัญชีนี้ได้รับอนุญาตเพื่อมิให้การแจ้งเตือนถูกส่งไปยังสแปมหรือโฟลเดอร์ขยะ

## <a name="next-steps"></a>ขั้นตอนถัดไป

[ตัวเลือกการสนับสนุน Power BI Pro และ Power BI Premium](service-support-options.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)
---
title: ข้อมูลขาออกของ Power BI และ Azure
description: ทำความเข้าใจเกี่ยวกับค่าใช้จ่ายในการเข้าถึง Azure และ Power BI ตามสถานที่ตั้งของผู้เช่าและ Power BI Premium
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/18/2018
ms.author: davidi
LocalizationGroup: Data from databases
ms.openlocfilehash: 0150e4e62fffd116b144880ab4aecc81de0b2c49
ms.sourcegitcommit: 1a79e48ac820c28c5d0fd05399f49ed22fc74ed7
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/19/2018
ms.locfileid: "49435583"
---
# <a name="power-bi-and-azure-egress"></a>ข้อมูลขาออกของ Power BI และ Azure

เมื่อใช้ Power BI กับแหล่งข้อมูล Azure คุณสามารถหลีกเลี่ยงค่าใช้จ่ายในการเข้าถึง Azure ได้โดยตรวจสอบให้แน่ใจว่าผู้เช่า Power BI ของคุณอยู่ในพื้นที่เดียวกันกับแหล่งข้อมูล Azure ของคุณ

เมื่อผู้เช่า Power BI ของคุณใช้งานในพื้นที่ Azure เดียวกับที่คุณใช้แหล่งข้อมูลของคุณ คุณจะไม่ต้องเสียค่าใช้จ่ายในการเข้าถึงสำหรับการรีเฟรชตามกำหนดเวลาและการโต้ตอบระหว่าง DirectQuery 

## <a name="determining-where-your-power-bi-tenant-is-located"></a>ตรวจสอบตำแหน่งที่ผู้เช่า Power BI ของคุณอยู่

เมื่อต้องการค้นหาว่าผู้เช่า Power BI ของคุณอยู่ที่ใด ดูบทความ [ผู้เช่า Power BI ของฉันอยู่ที่ไหน](service-admin-where-is-my-tenant-located.md)

สำหรับลูกค้า Power BI Premium Multi-Geo หากผู้เช่า Power BI ของคุณไม่อยู่ในตำแหน่งที่เหมาะสมสำหรับแหล่งข้อมูลบางส่วนที่ใช้ Azure คุณสามารถปรับใช้ Power BI Premium Multi-Geo ในพื้นที่ Azure ที่ต้องการและได้รับประโยชน์จากการที่ผู้เช่า Power BI และแหล่งข้อมูล Azure อยู่ในภูมิภาค Azure เดียวกัน

## <a name="next-steps"></a>ขั้นตอนถัดไป

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ Power BI Premium หรือ Multi-Geo โปรดดูที่แหล่งข้อมูลต่อไปนี้:

* [Microsoft Power BI Premium คืออะไร?](service-premium.md)
* [วิธีการซื้อ Power BI Premium](service-admin-premium-purchase.md)
* [การสนับสนุน Multi-Geo สำหรับ Power BI Premium (ตัวอย่าง)](service-admin-premium-multi-geo.md)
* [ผู้เช่า Power BI ของฉันอยู่ที่ไหน?](service-admin-where-is-my-tenant-located.md)
* [Power BI Premium คำถามที่พบบ่อย](service-premium-faq.md)



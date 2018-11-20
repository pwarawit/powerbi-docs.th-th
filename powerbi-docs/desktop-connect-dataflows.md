---
title: เชื่อมต่อกับข้อมูลที่สร้างขึ้นโดยกระแสข้อมูล Power BI ใน Power BI Desktop (เบต้า)
description: เชื่อมต่อและใช้กระแสข้อมูลใน Power BI Desktop ได้อย่างง่ายดาย
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 11/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: f87db1f715118f346e3b8069897e92fd157f881c
ms.sourcegitcommit: b23fdcc0ceff5acd2e4d52b15b310068236cf8c7
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265943"
---
# <a name="connect-to-data-created-by-power-bi-dataflows-in-power-bi-desktop-beta"></a>เชื่อมต่อกับข้อมูลที่สร้างขึ้นโดยกระแสข้อมูล Power BI ใน Power BI Desktop (เบต้า)
ใน **Power BI Desktop** คุณสามารถเชื่อมต่อกับ **กระแสข้อมูล Power BI** เช่นเดียวกับแหล่งข้อมูลอื่นใน Power BI Desktop ได้

![เชื่อมต่อกับกระแสข้อมูล](media/desktop-connect-dataflows/connect-dataflows_01.png)

ตัวเชื่อมต่อ**กระแสข้อมูล Power BI (เบต้า)** จะให้คุณได้เชื่อมต่อกับเอนทิตีที่สร้างโดยกระแสข้อมูลในบริการของ Power BI 

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด

ในการใช้**ตัวเชื่อมต่อกระแสข้อมูล Power BI** เวอร์ชันเบต้า คุณต้องใช้ **Power BI Desktop** เวอร์ชันล่าสุด คุณสามารถ[ดาวน์โหลด Power BI Desktop](desktop-get-the-desktop.md) ได้ทุกเมื่อ และติดตั้งบนคอมพิวเตอร์ของคุณ เพื่อให้แน่ใจว่าคุณมีรุ่นล่าสุด  

> [!NOTE]
> ตัวเชื่อมต่อกระแสข้อมูล Power BI เวอร์ชันก่อนหน้ากำหนดให้คุณดาวน์โหลดไฟล์ .MEZ และวางไว้ในโฟลเดอร์ **Power BI Desktop**เวอร์ชันปัจจุบันมีตัวเชื่อมต่อกระแสข้อมูล Power BI เพื่อไม่ต้องใช้ไฟล์นั้นอีกต่อไปและไม่ให้เกิดปัญหากับตัวเชื่อมต่อเวอร์ชันที่รวมมาด้วย หาคุณวางไฟล์ .MEZ ไว้ในโฟลเดอร์ด้วยตัวเอง คุณ*ต้อง*ลบไฟล์ .MEZ ที่ดาวน์โหลดมาออกจากโฟลเดอร์ **เอกสาร > Power BI Desktop > ตัวเชื่อมต่อแบบกำหนดเอง** 

## <a name="desktop-performance"></a>ประสิทธิภาพการทำงานของ Desktop
**Power BI Desktop** ทำงานภายในเครื่องบนคอมพิวเตอร์ที่มีติดตั้งโปรแกรมเอาไว้ ประสิทธิภาพการรวบรวมของกระแสข้อมูลถูกกำหนดโดยปัจจัยหลายอย่าง ซึ่งปัจจัยเหล่านั้นประกอบไปด้วย ขนาดของข้อมูล, CPU และ RAM ของคอมพิวเตอร์, แบนด์วิดท์เครือข่าย, ระยะห่างจากศูนย์ข้อมูล และปัจจัยอื่นๆ

คุณสามารถปรับปรุงประสิทธิภาพการรวบรวมข้อมูลสำหรับกระแสข้อมูลได้ ตัวอย่างเช่น ถ้าขนาดของข้อมูลที่รวบรวมนั้นใหญ่เกินกว่าที่ **Power BI Desktop** จะจัดการได้ในคอมพิวเตอร์ คุณอาจใช้เอนทิตีที่เชื่อมโยงและเอนทิตีที่คำนวณในกระแสข้อมูลเพื่อรวมข้อมูลนั้น (ภายในกระแสข้อมูล) แล้วเลือกดึงเอาเฉพาะข้อมูลที่รวมและเตรียมไว้ก่อนแล้ว เมื่อทำเช่นนั้น การประมวลผลข้อมูลขนาดใหญ่จะดำเนินการออนไลน์ในกระแสข้อมูล แทนที่จะดำเนินการภายในอินสแตนซ์ที่ทำงานอยู่ของ **Power BI Desktop** วิธีนั้นจะทำให้ Power BI Desktop รวบรวมข้อมูลได้ในขนาดที่เล็กลง และรักษาการใช้งานที่มีกระแสข้อมูลให้ตอบสนองรวดเร็ว


## <a name="next-steps"></a>ขั้นตอนถัดไป
มีสิ่งน่าสนใจหลายอย่างที่คุณสามารถทำได้โดยใช้กระแสข้อมูล Power BI สำหรับข้อมูลเพิ่มเติม โปรดดูทรัพยากรต่อไปนี้:

* [การเตรียมข้อมูลด้วยตัวเองโดยใช้กระแสข้อมูล](service-dataflows-overview.md)
* [การสร้างและใช้กระแสข้อมูลใน Power BI](service-dataflows-create-use.md)
* [การใช้เอนทิตีที่คำนวณใน Power BI Premium (ตัวอย่าง)](service-dataflows-computed-entities-premium.md)
* [การใช้กระแสข้อมูลพร้อมแหล่งข้อมูลในองค์กร (ตัวอย่าง)](service-dataflows-on-premises-gateways.md)
* [แหล่งข้อมูลของนักพัฒนาสำหรับกระแสข้อมูล Power BI (ตัวอย่าง)](service-dataflows-developer-resources.md)

ยังมีบทความเกี่ยวกับ**Power BI Desktop** ที่อาจเป็นประโยชน์กับคุณ:

* [แหล่งข้อมูลใน Power BI Desktop](desktop-data-sources.md)
* [จัดรูปร่างและรวมข้อมูลด้วย Power BI Desktop](desktop-shape-and-combine-data.md)
* [ป้อนข้อมูลลงใน Power BI Desktop โดยตรง](desktop-enter-data-directly-into-desktop.md)   


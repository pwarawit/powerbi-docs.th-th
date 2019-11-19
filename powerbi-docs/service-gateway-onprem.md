---
title: เกตเวย์ข้อมูลภายในองค์กร
description: บทความนี้คือภาพรวมของเกตเวย์ข้อมูลภายในองค์กรสำหรับ Power BI คุณสามารถใช้เกตเวย์นี้เพื่อทำงานกับแหล่งข้อมูล DirectQuery คุณยังสามารถใช้เกตเวย์นี้เพื่อรีเฟรชชุดข้อมูลบนระบบคลาวด์กับข้อมูลภายในองค์กร
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Gateways
ms.date: 07/15/2019
ms.openlocfilehash: 8ca43232cdc5781900dd7cf8b9f72c510dab2e37
ms.sourcegitcommit: 2b7beec5237a597bab2da8eb6ffe69122a5d2ed9
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442806"
---
# <a name="what-is-an-on-premises-data-gateway"></a>เกตเวย์ข้อมูลในองค์กรคืออะไร?

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

เกตเวย์ข้อมูลภายในองค์กรทำหน้าที่เป็นสะพาน โดยให้บริการการถ่ายโอนข้อมูลที่รวดเร็วและปลอดภัยระหว่างข้อมูลภายในองค์กร (ข้อมูลที่ไม่ได้อยู่ในระบบคลาวด์) และบริการคลาวด์ของ Microsoft อีกหลายบริการ บริการคลาวด์เหล่านี้ประกอบรวมด้วย Power BI, PowerApps, Microsoft Flow, Azure Analysis Services และ Azure Logic Apps โดยการใช้เกตเวย์ องค์กรสามารถเก็บฐานข้อมูลและแหล่งข้อมูลอื่น ๆ บนเครือข่ายภายในองค์กรของตนได้ และยังใช้ข้อมูลภายในองค์กรในบริการคลาวด์ได้อย่างปลอดภัย

## <a name="how-the-gateway-works"></a>วิธีการทำงานของเกตเวย์

![ภาพรวมของเกตเวย์](media/service-gateway-onprem/on-premises-data-gateway.png)

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับวิธีการทำงานของเกตเวย์ ดูที่ [สถาปัตยกรรมของเกตเวย์ข้อมูลภายในองค์กร](/data-integration/gateway/service-gateway-onprem-indepth)

## <a name="types-of-gateways"></a>ชนิดของเกตเวย์

มีเกตเวย์สองชนิดที่แตกต่างกันสำหรับสถานการณ์ที่แตกต่างกัน:

* **เกตเวย์ข้อมูลภายในองค์กร** ช่วยให้ผู้ใช้หลายคนสามารถเชื่อมต่อกับหลายแหล่งข้อมูลภายในองค์กรได้ คุณสามารถใช้เกตเวย์ข้อมูลภายในองค์กรที่มีบริการที่สนับสนุนทั้งหมดได้ด้วยการติดตั้งเกตเวย์ครั้งเดียว เกตเวย์นี้เหมาะสมสำหรับสถานการณ์ที่ซับซ้อนสำหรับบุคคลหลายคนที่เข้าถึงแหล่งข้อมูลหลายแหล่ง

* **เกตเวย์ข้อมูลในองค์กร (โหมดส่วนบุคคล)** ช่วยให้ผู้ใช้หนึ่งรายสามารถเชื่อมต่อกับแหล่งข้อมูล และไม่สามารถแชร์ให้กับผู้อื่นได้ เกตเวย์ข้อมูลภายในองค์กร (โหมดส่วนบุคคล) จะสามารถใช้กับ Power BI เท่านั้น เกตเวย์นี้เหมาะที่สุดกับสถานการณ์ที่คุณเป็นเพียงบุคคลเดียวที่สร้างรายงาน และคุณไม่จำเป็นต้องใช้แหล่งข้อมูลใด ๆ ร่วมกันกับผู้อื่น

## <a name="use-a-gateway"></a>ใช้เกตเวย์

มีสี่ขั้นตอนหลักสำหรับการใช้เกตเวย์

1. [ดาวน์โหลดและติดตั้งเกตเวย์](/data-integration/gateway/service-gateway-install)บนคอมพิวเตอร์เฉพาะที่
1. [กำหนดค่า](/data-integration/gateway/service-gateway-app)เกตเวย์ที่ยึดตามไฟร์วอลล์ของคุณและข้อกำหนดของเครือข่ายอื่นๆ
1. [เพิ่มผู้ดูแลระบบเกตเวย์](/data-integration/gateway/service-gateway-manage) ซึ่งสามารถจัดการและดูแลข้อกำหนดของเครือข่ายอื่น ๆ ได้ด้วย
1. [ใช้เกตเวย์](service-gateway-sql-tutorial.md) เพื่อรีเฟรชแหล่งข้อมูลภายในองค์กร
1. [แก้ไขปัญหา](service-gateway-onprem-tshoot.md)เกตเวย์ในกรณีของข้อผิดพลาด

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [ติดตั้งเกตเวย์ข้อมูลภายในองค์กร](/data-integration/gateway/service-gateway-install)

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)

---
title: Power BI และ ExpressRoute
description: Power BI และ ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: c7d12bf6a1a2a02c988f8351a1844be1080ad2b8
ms.sourcegitcommit: a97c0c34f888e44abf4c9aa657ec9463a32be06f
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/17/2019
ms.locfileid: "71074795"
---
# <a name="power-bi-and-expressroute"></a>Power BI และ ExpressRoute

**ExpressRoute**เป็นบริการของ Azure ที่ช่วยให้คุณสร้างการเชื่อมต่อแบบส่วนตัวระหว่างศูนย์ข้อมูล Azure (ที่ Power BI อยู่) และโครงสร้างพื้นฐานภายในองค์กรของคุณ หรือสร้างการเชื่อมต่อแบบส่วนตัวระหว่างศูนย์ข้อมูล Azure และสภาพแวดล้อมโคโลเคชั่นของคุณ

ด้วย**Power BI**และ**ExpressRoute** คุณสามารถสร้างการเชื่อมต่อเครือข่ายส่วนตัวจากองค์กรของคุณไปยัง Power BI ได้ (หรือใช้สิ่งอำนวยความสะดวกโคโลเคชั่นของ ISP) เบี่ยงอินเทอร์เน็ตเพื่อเพิ่มความปลอดภัยกับข้อมูล Power BI และการเชื่อมต่อที่อ่อนไหว

สำหรับข้อมูลเพิ่มเติม ให้ดู [ภาพรวมของ ExpressRoute](/azure/expressroute/expressroute-introduction) Power BI สอดคล้องกับ ExpressRoute โดยมีข้อยกเว้นบางอย่างที่ Power BI จะรับหรือส่งข้อมูลผ่านอินเทอร์เน็ตสาธารณะ สำหรับรายการของ URL ที่ Power BI ใช้ ให้ดูที่[Power BI URL](power-bi-whitelist-urls.md)

![ไดอะแกรม ExpressRoute](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)
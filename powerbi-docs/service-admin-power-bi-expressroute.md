---
title: Power BI และ ExpressRoute
description: Power BI และ ExpressRoute
author: mgblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 59ddddcf1b02f07b850294fa314b7508f7f9fcdc
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/09/2019
ms.locfileid: "73856945"
---
# <a name="power-bi-and-expressroute"></a>Power BI และ ExpressRoute

**ExpressRoute**เป็นบริการของ Azure ที่ช่วยให้คุณสร้างการเชื่อมต่อแบบส่วนตัวระหว่างศูนย์ข้อมูล Azure (ที่ Power BI อยู่) และโครงสร้างพื้นฐานภายในองค์กรของคุณ หรือสร้างการเชื่อมต่อแบบส่วนตัวระหว่างศูนย์ข้อมูล Azure และสภาพแวดล้อมโคโลเคชั่นของคุณ

ด้วย**Power BI**และ**ExpressRoute** คุณสามารถสร้างการเชื่อมต่อเครือข่ายส่วนตัวจากองค์กรของคุณไปยัง Power BI ได้ (หรือใช้สิ่งอำนวยความสะดวกโคโลเคชั่นของ ISP) เบี่ยงอินเทอร์เน็ตเพื่อเพิ่มความปลอดภัยกับข้อมูล Power BI และการเชื่อมต่อที่อ่อนไหว

สำหรับข้อมูลเพิ่มเติม ให้ดู [ภาพรวมของ ExpressRoute](/azure/expressroute/expressroute-introduction) Power BI สอดคล้องกับ ExpressRoute โดยมีข้อยกเว้นบางอย่างที่ Power BI จะรับหรือส่งข้อมูลผ่านอินเทอร์เน็ตสาธารณะ สำหรับรายการของ URL ที่ Power BI ใช้ ให้ดูที่[Power BI URL](power-bi-whitelist-urls.md)

![ไดอะแกรม ExpressRoute](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)
---
title: Azure และ Power BI
description: Azure และ Power BI
author: davidiseminger
ms.author: davidi
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/08/2019
LocalizationGroup: Data from databases
ms.openlocfilehash: 9d48054e4b41c097d51522ad7596b750bd067e6d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "65513331"
---
# <a name="azure-and-power-bi"></a>Azure และ Power BI

ด้วยบริการ**Azure** และ**Power BI** คุณสามารถเปิดใช้การประมวลผลข้อมูลของคุณลงในการวิเคราะห์และรายงานที่ให้ข้อมูลเชิงลึกแบบเรียลไทม์ในธุรกิจของคุณได้ ไม่ว่าการประมวลข้อมูลจะอยู่ในคลาวด์หรือภายในองค์กร ตรงไปตรงมาหรือซับซ้อน มาจากแหล่งเดียวหรือปรับมาตราส่วนให้กว้างขึ้น จัดเก็บเอาไว้หรือเรียลไทม์ก็ตาม Azure และ Power BI มีภาวะเชื่อมต่อและการหาปริพันธ์ที่อยู่ภายใน เพื่อให้ความพยายามในระบบธุรกิจอัจฉริยะเป็นจริงขึ้นมาได้

![Azure](media/service-azure-and-power-bi/azure_1.png)

Power BI มีการเชื่อมต่อ Azure ที่พร้อมใช้งานที่หลากหลาย และโซลูชันข่าวกรองทางธุรกิจที่คุณสามารถสร้างได้ด้วยบริการเหล่านั้น จะมีความเป็นเอกลักษณ์เช่นเดียวกับธุรกิจของคุณ คุณสามารถเชื่อมต่อในปริมานน้อยได้ เช่น หนึ่งแหล่งข้อมูล Azure หรือจำนวนไม่กี่แหล่ง จาก นั้นจัดรูปร่างและปรับปรุงข้อมูลของคุณเพื่อสร้างรายงานแบบกำหนดเอง

## <a name="azure-sql-database-and-power-bi"></a>ฐานข้อมูล Azure SQL และ Power BI

คุณสามารถเริ่มต้นด้วยการเชื่อมต่อตรงไปยังฐานข้อมูล SQL Azure และสร้างรายงานเพื่อตรวจติดตามความคืบหน้าของธุรกิจของคุณได้ การใช้[Power BI Desktop](desktop-getting-started.md) คุณสามารถสร้างรายงานที่ระบุแนวโน้มและตัวบ่งชี้ประสิทธิภาพที่สำคัญที่ขับเคลื่อนธุรกิจของคุณให้มุ่งไปข้างหน้า

![SQL ไปยัง PBI](media/service-azure-and-power-bi/azure_2_sqltopbi.png)

มีข้อมูลเพิ่มเติมจำนวนมากที่ให้คุณเรียนรู้เกี่ยวกับ[ฐานข้อมูล Azure SQL](http://azure.microsoft.com/services/sql-database/) ได้

## <a name="transform-shape-and-merge-your-cloud-data"></a>แปลง ปรับรูปร่าง และผสานข้อมูลในระบบคลาวด์ของคุณ

คุณมีข้อมูลที่ซับซ้อนกว่าและมีทุกประเภทของแหล่งที่มาของข้อมูลหรือไม่? ไม่มีปัญหา ด้วย **Power BI Desktop** และบริการของ Azure คุณสามารถเชื่อมต่อได้ง่าย ๆ โดยการแตะกล่องโต้ตอบ**รับข้อมูล** ภายในแบบสอบถามเดียวกัน คุณสามารถเชื่อมต่อ**ฐานข้อมูล SQL Azure**ของคุณ แหล่งข้อมูล**Azure HDInsight**ของคุณ และ**การเก็บข้อมูล Azure Blob** ของคุณได้ (หรือ**ตารางเก็บข้อมูล Azure**) จากนั้นเลือกเฉพาะชุดย่อยภายในแต่ละรายการที่คุณต้องการและปรับปรุงเอกสารจากตรงนั้น

คุณสามารถสร้างรายงานอื่นสำหรับผู้ชมกลุ่มอื่นโดยใช้การเชื่อมต่อข้อมูลเดียวกันและแม้แต่การสอบถามเดียวกันได้เช่นกัน เพียงแค่สร้างหน้ารายงานใหม่ ปรับปรุงการแสดงภาพของคุณสำหรับแต่ละผู้ชม และดูการติดตามความก้าวหน้าธุรกิจของคุณ

![Multiple ไปยัง PBI](media/service-azure-and-power-bi/azure_3_multipletopbi.png)

สำหรับข้อมูลเพิ่มเติม โปรดดูที่แหล่งทรัพยากรต่อไปนี้:

* [ฐานข้อมูล Azure SQL](http://azure.microsoft.com/services/sql-database/)
* [Azure HDInsight (HDFS)](http://azure.microsoft.com/services/hdinsight/)
* [พื้นที่จัดเก็บ Azure](http://azure.microsoft.com/services/storage/) (พื้นที่จัดเก็บ Blob และพื้นที่จัดเก็บตาราง)

## <a name="get-complex-and-ahead-using-azure-services-and-power-bi"></a>รับรายงานที่ซับซ้อน (และทำล่วงหน้า) โดยใช้ Azure Services และ Power BI

คุณสามารถขยายได้มากเท่าที่คุณต้องการสำหรับ Azure และ Power BI ควบคุมการประมวลผลข้อมูลหลายแหล่ง ใช้ระบบแบบเรียลไทม์ขนาดใหญ่ ใช้[Stream Analytics](http://azure.microsoft.com/services/stream-analytics/)และ[Event Hubs](http://azure.microsoft.com/services/event-hubs/)และรวมบริการ SaaS ต่าง ๆ ของคุณเข้ากับรายงานข่าวกรองทางธุรกิจที่ให้ข้อมูลทางธุรกิจที่ล้ำสมัยกับคุณ

![Azure เชิงซ้อน](media/service-azure-and-power-bi/azure_4_complex.png)

## <a name="context-insights-with-power-bi-embedded-analytics"></a>ข้อมูลเชิงลึกในบริบทพร้อมการวิเคราะห์ Power BI Embedded

ฝังการแสดงภาพเชิงโต้ตอบอันน่าทึ่งในแอปพลิเคชัน เว็บไซต์ พอร์ทัล และอื่นๆ เพื่อใช้ประโยชน์จากข้อมูลธุรกิจของคุณ ด้วย [Power BI Embedded เป็นแหล่งทรัพยากรใน Azure](https://azure.microsoft.com/services/power-bi-embedded/) คุณจะสามารถฝังรายงานเชิงโต้ตอบและแดชบอร์ดได้อย่างง่ายดาย ดังนั้นผู้ใช้ของคุณจะเพลิดเพลินไปกับการใช้งานข้ามอุปกรณ์ที่สม่ำเสมอและมีความแม่นยำสูง  Power BI ที่ใช้กับการฝังการวิเคราะห์นั้นมีไว้เพื่อช่วยในการเดินทางจากข้อมูล -> ความรู้ -> ข้อมูลเชิงลึก -> การดำเนินการ  ยิ่งไปกว่านั้น คุณสามารถขยายค่าของ Power BI และ Azure ได้โดยการฝังการวิเคราะห์ใน [แอปพลิเคชันและพอร์ทัลภายในขององค์](https://powerbi.microsoft.com/developers/embedded-analytics/organization/)

มีข้อมูลจำนวนมากเกี่ยวกับ Power BI API ใน[พอร์ทัลนักพัฒนา Power BI](http://dev.powerbi.com)

สำหรับข้อมูลเพิ่มเติม โปรดดูที่ [นักพัฒนาใช้ Power BI ทำอะไรได้บ้าง](developer/what-can-you-do.md)

## <a name="embed-your-power-bi-data-within-your-app"></a>ฝังข้อมูล Power BI ของคุณไว้ภายในแอป

ฝังการแสดงภาพเชิงโต้ตอบอันน่าทึ่งในแอปพลิเคชัน เว็บไซต์ พอร์ทัล และอื่นๆ เพื่อแสดงข้อมูลธุรกิจของคุณในบริบท ด้วยการใช้ [Power BI Embedded ใน Azure](https://azure.microsoft.com/services/power-bi-embedded/) คุณสามารถฝังรายงานเชิงโต้ตอบและแดชบอร์ดได้อย่างง่ายดาย เพื่อให้ผู้ใช้ของคุณเพลิดเพลินไปกับการใช้งานข้ามอุปกรณ์ที่สม่ำเสมอและมีความแม่นยำสูง

## <a name="what-could-you-do-with-azure-and-power-bi"></a>คุณสามารถทำอะไรได้บ้างกับ Azure และ Power BI?

มีหลากหลายสถานการณ์มากทีี่เราสามารถใช้งาน **Azure**ร่วมกับ**Power BI**ได้ ความเป็นไปได้และโอกาสต่าง ๆ จะมีความเป็นเอกลักษณ์เฉกเช่นธุรกิจของคุณ สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ**บริการ Azure** สามารถดูได้ที่[เพจภาพรวม](https://docs.microsoft.com/azure/machine-learning/team-data-science-process/plan-your-environment)ซึ่งอธิบายเกี่ยวกับ**สถานการณ์สมมติการวิเคราะห์ข้อมูลโดยใช้ Azure** และเรียนรู้วิธีการเปลี่ยนแปลงแหล่งข้อมูลเป็นข่าวกรองที่ขับเคลื่อนธุรกิจของคุณให้ก้าวไปข้างหน้า
---
title: การกำหนดคำแนะนำเครื่องมือเองใน Power BI Desktop
description: สร้างเครื่องมือคำแนะนำแบบกำหนดเองสำหรับภาพโดยใช้การลากและวาง
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: f44f74934bbac345bef165492e83f6ce783b5513
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/24/2018
---
# <a name="customizing-tooltips-in-power-bi-desktop"></a>การกำหนดคำแนะนำเครื่องมือเองใน Power BI Desktop
คำแนะนำเครื่องมือเป็นวิธีที่เหมาะสมในการให้ข้อมูลตามบริบทและรายละเอียดไปยังจุดข้อมูลบนภาพได้มากกว่า รูปต่อไปนี้แสดงคำแนะนำเครื่องมือที่นำไปใช้กับแผนภูมิใน Power BI Desktop

![](media/desktop-custom-tooltips/custom-tooltips_1.png)

เมื่อมีการสร้างภาพ คำแนะนำเครื่องมือเริ่มต้นจะแสดงค่าและประเภทของจุดข้อมูล มีหลายตัวอย่างที่ความสามารถในการกำหนดข้อมูลคำแนะนำเครื่องมือจะเป็นประโยชน์ได้ และจะให้บริบทและข้อมูลเพิ่มเติมสำหรับผู้ใช้ที่ดูภาพ คำแนะนำเครื่องมือแบบกำหนดเองช่วยให้คุณสามารถระบุจุดข้อมูลเพิ่มเติมที่แสดงเป็นส่วนหนึ่งของคำแนะนำดังกล่าว

## <a name="how-to-customize-tooltips"></a>วิธีการกำหนดคำแนะนำเครื่องมือด้วยตนเอง
เมื่อต้องสร้างคำแนะนำแบบกำหนดเอง ในแอ่ง**ช่องข้อมูล**ของพื้นที่**การแสดงภาพ** เพียงแค่ลากช่องข้อมูลลงในบักเก็ต**คำแนะนำเครื่องมือ**ที่แสดงในรูปต่อไปนี้ ในรูปต่อไปนี้ มีการช่องข้อมูลสี่ช่องลงในบักเก็ต**คำแนะนำเครื่องมือ**

![](media/desktop-custom-tooltips/custom-tooltips_2.png)

หลังจากที่เพิ่มคำแนะนำเครื่องมือเข้าไปยังช่องข้อมูลแล้ว ให้เลื่อนไปเหนือจุดข้อมูลบนการแสดงภาพที่แสดงค่าสำหรับช่องข้อมูลเหล่านั้นในคำแนะนำเครื่องมือ

![](media/desktop-custom-tooltips/custom-tooltips_3.png)

## <a name="customizing-tooltips-with-aggregation-or-quick-calcs"></a>กำหนดคำแนะนำเครื่องมือด้วยตนเองด้วยการรวมหรือ Quick Calcs (คำนวณด่วน)
คุณสามารถกำหนดคำแนะนำเครื่องมือเพิ่มเติมได้โดยการเลือกฟังก์ชันการรวมหรือ*คำนวณด่วน*โดยการเลือกลูกศรข้างช่องข้อมูลในบักเก็ต**คำแนะนำเครื่องมือ** และเลือกจากตัวเลือกที่ใช้งานได้

![](media/desktop-custom-tooltips/custom-tooltips_4.png)

มีหลายวิธีในการกำหนด**คำแนะนำเครื่องมือ**ด้วยตนเอง นั่นคืิอ โดยใช้ช่องข้อมูลใด ๆ ที่พร้อมใช้งานในชุดข้อมูลของคุณ การสื่อข้อมูลอย่างรวดเร็วและข้อมูลเชิงลึกกับผู้ใช้ที่ดูแดชบอร์ดหรือรายงานของคุณ


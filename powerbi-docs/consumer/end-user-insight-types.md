---
title: ชนิดของข้อมูลเชิงลึกด่วนที่ได้รับการสนับสนุนโดย Power BI
description: ข้อมูลเชิงลึกด่วน และดูข้อมูลเชิงลึก ด้วย Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 10/2/2019
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 507d49ba6cdb894667bf66f8f35c5c325b9ff25e
ms.sourcegitcommit: b7a9862b6da940ddebe61bc945a353f91cd0e4bd
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/04/2019
ms.locfileid: "71943926"
---
# <a name="types-of-insights-supported-by-power-bi"></a>ชนิดของข้อมูลเชิงลึกด่วนที่ได้รับการสนับสนุนโดย Power BI

บริการของ Power BI สามารถค้นหาข้อมูลเชิงลึกในแดชบอร์ดหรือรายงานของคุณได้โดยอัตโนมัติ

## <a name="how-does-insights-work"></a>ข้อมูลเชิงลึกทำงานอย่างไร
Power BI จะค้นหาชุดข้อมูลย่อยที่แตกต่างกันของคุณได้อย่างรวดเร็ว ในขณะที่ค้นหา Power BI จะใช้ชุดของอัลกอริทึมที่มีความซับซ้อนเพื่อค้นหาข้อมูลเชิงลึกที่น่าสนใจ Power BI สแกนของชุดข้อมูลที่เป็นไปได้มากในระยะเวลาที่กำหนด

คุณสามารถเรียกใช้ข้อมูลเชิงลึกกับชุดข้อมูลหรือแดชบอร์ดไทล์   

## <a name="what-types-of-insights-can-we-find"></a>เราสามารถพบข้อมูลเชิงลึกชนิดใด
ต่อไปนี้คือตัวอย่างของอัลกอริธึมที่เราใช้:

## <a name="category-outliers-topbottom"></a>ประเภทข้อมูลที่ผิดปกติ (บน/ล่าง)
ไฮไลต์กรณีที่ สำหรับหน่วยวัดในแบบจำลอง หนึ่ง หรือสองสมาชิกของมิติมีค่ามากขนาดใหญ่กว่าสมาชิกคนอื่น ๆ ของมิติ  

![ตัวอย่างข้อมูลที่ผิดปกติ](./media/end-user-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>เปลี่ยนจุดในชุดข้อมูลเวลา
ไฮไลต์เมื่อมีการเปลี่ยนแปลงที่สำคัญในแนวโน้มในชุดข้อมูลเวลา

![เปลี่ยนจุดในชุดข้อมูลเวลา](./media/end-user-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>สหสัมพันธ์
ตรวจพบกรณีที่หลายหน่วยวัดแสดงความสัมพันธ์ระหว่างแต่ละคนเมื่อลงจุดตามขนาดในชุดข้อมูล

![ตัวอย่างสหสัมพันธ์](./media/end-user-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>ผลต่างต่ำ
ตรวจพบกรณีที่จุดข้อมูลอยู่ไม่ห่างจากค่าเฉลี่ย

![ตัวอย่างผลต่างต่ำ](./media/end-user-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>ส่วนหลัก (ปัจจัยหลัก)
ค้นหากรณีที่ส่วนใหญ่ของค่าทั้งหมดสามารถเกิดจากการคูณเดียวเมื่อแบ่งย่อยตามขนาดอื่น  

![ตัวอย่างปัจจัยหลัก](./media/end-user-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>แนวโน้มโดยรวมในชุดข้อมูลเวลา
ตรวจพบแนวโน้มขึ้น หรือลงในชุดข้อมูลเวลา

![แนวโน้มโดยรวมในชุดข้อมูลเวลา](./media/end-user-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>กาลในชุดข้อมูลเวลา
ค้นหารูปแบบเป็นครั้งคราวในข้อมูลชุดข้อมูลเวลา เช่นกาลรายสัปดาห์ เดือน หรือรายปี

![ตัวอย่างกาล](./media/end-user-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>การแชร์แบบคงที่
ไฮไลต์กรณีมีความสัมพันธ์หลัก-รองระหว่างใช้ร่วมกันของค่ารองสัมพันธ์กับค่าโดยรวมของค่าหลักระหว่างตัวแปรอย่างต่อเนื่อง

![การแชร์แบบคงที่](./media/end-user-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>ข้อมูลชุดเวลาที่ผิดปกติ
สำหรับข้อมูลทั่วทั้งชุดข้อมูลเวลา ตรวจพบเมื่อมีการระบุวันที่หรือเวลา ด้วยค่าที่แตกต่างอย่างมากจากค่าวันที่/เวลาอื่น ๆ

![ข้อมูลชุดเวลาที่ผิดปกติ](./media/end-user-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[ข้อมูลเชิงลึกที่ power BI](end-user-insights.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


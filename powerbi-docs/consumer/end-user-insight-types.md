---
title: ชนิดของข้อมูลเชิงลึกด่วนที่ได้รับการสนับสนุนโดย Power BI
description: ข้อมูลเชิงลึกด่วน และดูข้อมูลเชิงลึก ด้วย Power BI
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: d3d6592d3cf2e0bc7239a6f725dbfc1334108823
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/22/2018
ms.locfileid: "46564865"
---
# <a name="types-of-insights-supported-by-power-bi"></a>ชนิดของข้อมูลเชิงลึกด่วนที่ได้รับการสนับสนุนโดย Power BI
## <a name="how-does-insights-work"></a>ข้อมูลเชิงลึกทำงานอย่างไร
Power BI จะค้นหาเซตย่อยของชุดข้อมูลของคุณในขณะที่มันกำลังใช้ชุดอัลกอริธึมที่ชาญฉลาดในการค้นพบแนวโน้มข้อมูลเชิงลึกที่น่าสนใจ Power BI สแกนของชุดข้อมูลที่เป็นไปได้มากในระยะเวลาที่กำหนด

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
ตรวจพบกรณีที่จุดข้อมูลไม่ใช่ far from ค่าเฉลี่ย

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

ถ้าคุณเป็นเจ้าของชุดข้อมูล[ปรับให้เหมาะสมสำหรับข้อมูลเชิงลึก](../service-insights-optimize.md)

คำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


---
title: ตัวอย่างวิชวล Power BI
description: บทความนี้แสดงตัวอย่างวิชวล Power BI ประกอบไปด้วยแบ่งส่วนข้อมูล แผนภูมิมากกว่า20ชนิด WebGL รวมถึง วิชวล R และสคริปต์
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 03/17/2019
ms.openlocfilehash: 5e2ad0fa43a186be76a58f1ab3bb4bf054a677a5
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83132319"
---
# <a name="samples-of-power-bi-visuals"></a>ตัวอย่างสำหรับวิชวล Power BI

คุณสามารถดาวน์โหลด ใช้ และปรับเปลี่ยนวิชวล Power BI เหล่านี้ได้จาก GitHub ตัวอย่างเหล่านี้แสดงวิธีการจัดการสถานการณ์ทั่วไปเมื่อพัฒนาด้วย Power BI

## <a name="slicers"></a>ตัวแบ่งส่วนข้อมูล

ตัวแบ่งส่วนข้อมูลจะจำกัดส่วนของข้อมูลที่แสดงอยู่ในการแสดงภาพอื่นๆ ในรายงาน ตัวแบ่งส่วนข้อมูลเป็นหนึ่งในหลายวิธีในการกรองข้อมูลใน Power BI

| <img src="media/samples/chiclet-slicer.png" width="200">  | <img src="media/samples/timeline-slicer.png" width="200"> | <img src="media/samples/sample-slicer.png" width="200">|
| ------------- | ------------- | -------------|
| [Chiclet Slicer](https://github.com/Microsoft/powerbi-visuals-chicletslicer/)  </br>แสดงรูปภาพหรือปุ่มข้อความที่ทำหน้าที่เป็นตัวกรองกราฟิกในพื้นที่บนวิชวลอื่น ๆ | [Timeline Slicer](https://github.com/Microsoft/powerbi-visuals-timeline/) </br>ตัวเลือกช่วงวันที่แบบกราฟิกที่กรองตามวันที่ | [ตัวอย่างตัวแบ่งส่วนข้อมูล](https://github.com/Microsoft/powerbi-visuals-sampleslicer/) </br>อธิบายการใช้ API การกรองขั้นสูง

## <a name="charts"></a>แผนภูมิ

รับแรงบันดาลใจจากแกลเลอรีของเรา ที่ประกอบด้วยแผนภูมิแท่ง แผนภูมิวงกลม  Word Cloud และอื่นๆ

| <img src="media/samples/aster-plot.png" width="200">  | <img src="media/samples/bullet-chart.png" width="200"> | <img src="media/samples/Chord.png" width="200">|
| ------------- | ------------- | -------------|
| [Aster Plot](https://github.com/Microsoft/powerbi-visuals-asterplot/)  </br>แนวทางใหม่สำหรับแผนภูมิโดนัทมาตรฐาน ที่ใช้ค่าที่สองเพื่อลบมุม | [แผนภูมิหัวข้อย่อย](https://github.com/Microsoft/powerbi-visuals-bulletchart/) </br>แผนภูมิแท่งซึ่งมีองค์ประกอบภาพพิเศษที่ให้บริบท อันเป็นประโยชน์สำหรับการติดตามเป้าหมาย | [Chord](https://github.com/Microsoft/powerbi-visuals-chord/) </br>วิธีการทางกราฟิกที่แสดงความสัมพันธ์ของข้อมูลในเมทริกซ์
| <img src="media/samples/dot-plot.png" width="200"> | <img src="media/samples/dual-kpi.png" width="200">| <img src="media/samples/enhanced-scatter.png" width="200"> 
| [การพล็อตด้วยจุด](https://github.com/Microsoft/powerbi-visuals-dotplot/) </br>แสดงการกระจายของความถี่ในรูปแบบที่ดูดี | [Dual KPI](https://github.com/Microsoft/powerbi-visuals-dualkpi/) </br>แสดงภาพหน่วยวัดสองรายการในช่วงเวลา แสดงแนวโน้มของรายการดังกล่าวบนเส้นเวลาร่วมกันได้อย่างมีประสิทธิภาพ | [Enhanced Scatter](https://github.com/Microsoft/powerbi-visuals-enhancedscatter/) </br>การปรับปรุงของแผนภูมิกระจายที่มีอยู่
| <img src="media/samples/forcegraph.png" width="200">| <img src="media/samples/gantt.png" width="200">| <img src="media/samples/table-heatmap.png" width="200">
| [Force Graph](https://github.com/Microsoft/powerbi-visuals-forcegraph/) </br>บังคับเค้าโครงไดอะแกรมด้วยเส้นโค้ง ซึ่งประโยชน์ในการแสดงการเชื่อมต่อระหว่างเอนทิตี | [Gantt](https://github.com/Microsoft/powerbi-visuals-gantt/) </br>แผนภูมิแท่งที่แสดงเส้นเวลาโครงการหรือกำหนดการพร้อมทรัพยากร | [Table Heatmap](https://github.com/Microsoft/powerbi-visuals-heatmap/) </br>เปรียบเทียบข้อมูลได้อย่างง่ายดายและคล่องตัวโดยใช้สีในตาราง
| <img src="media/samples/histogram-chart.png" width="200"> | <img src="media/samples/linedot-chart.png" width="200"> | <img src="media/samples/mekko-chart.png" width="200"> 
| [Histogram chart](https://github.com/Microsoft/powerbi-visuals-histogram/) </br>แสดงภาพการกระจายข้อมูลในช่วงเวลาต่อเนื่องหรือบางช่วงเวลา | [LineDot chart](https://github.com/Microsoft/powerbi-visuals-linedotchart/) </br>แผนภูมิเส้นแบบเคลื่อนไหวที่มีจุดเคลื่อนไหว ซึ่งจะดึงดูดให้ผู้ชมสนใจข้อมูล | [Mekko chart](https://github.com/Microsoft/powerbi-visuals-mekkochart/) </br>การผสมผสานของแผนภูมิคอลัมน์แบบเรียงซ้อน 100% และแผนภูมิแท่งแบบเรียงซ้อน 100% รวมอยู่ในมุมมองเดียว
| <img src="media/samples/multikpi.png" width="200"> | <img src="media/samples/powerkpi.png" width="200"> | <img src="media/samples/powerkpi-matrix.png" width="200"> 
| [หลาย KPI](https://github.com/microsoft/PowerBI-visuals-MultiKPI/) </br> การแสดงภาพหลาย KPI อันทรงพลังด้วย KPI หลักพร้อมกับกราฟ Sparklines ที่มีข้อมูลที่สนับสนุนหลายรายการ | [Power KPI](https://github.com/microsoft/PowerBI-visuals-PowerKPI/) </br>ตัวบ่งชี้ KPI อันทรงพลัง ด้วยแผนภูมิหลายเส้นและป้ายชื่อสำหรับวันที่  มูลค่า และความแปรปรวนปัจจุบัน | [Power KPI Matrix](https://github.com/microsoft/PowerBI-visuals-PowerKPIMatrix/) </br>ตรวจสอบดัชนีชี้วัดที่สมดุลและจำนวนเมตริกและ KPI ที่ไม่ จำกัด ในรายการขนาดกะทัดรัดและอ่านง่าย
| <img src="media/samples/pulse-chart.png" width="200">| <img src="media/samples/radar-chart.png" width="200"> | <img src="media/samples/sankey-chart.png" width="200"> 
| [Pulse chart](https://github.com/Microsoft/powerbi-visuals-pulsechart/) </br>แผนภูมิเส้นนี้มีซึ่งมีคำอธิบายประกอบของเหตุการณ์สำคัญ เหมาะสำหรับการบอกเล่าเรื่องราวด้วยข้อมูล| [Radar chart](https://github.com/Microsoft/powerbi-visuals-radarchart/) </br>นำเสนอหลายหน่วยวัดที่ลงจุดบนแกนบอกประเภท ซึ่งมีประโยชน์ในการเปรียบเทียบคุณลักษณะ | [Sankey Chart](https://github.com/Microsoft/powerbi-visuals-sankey/) </br>แผนภาพกระแสข้อมูลที่ความกว้างของชุดข้อมูลเป็นสัดส่วนกับปริมาณของกระแสข้อมูล
| <img src="media/samples/stream-graph.png" width="200"> | <img src="media/samples/sunburst.png" width="200">| <img src="media/samples/tornado.png" width="200">
| [Stream graph](https://github.com/Microsoft/powerbi-visuals-streamgraph/) </br>แผนภูมิพื้นที่แบบเรียงซ้อนที่มีการประมาณค่าในช่วงอย่างราบรื่น ซึ่งมักจะใช้ในการแสดงค่าในช่วงเวลาหนึ่ง | [Sunburst chart](https://github.com/Microsoft/powerbi-visuals-sunburst/) </br>แผนภูมิโดนัทหลายระดับสำหรับการแสดงภาพข้อมูลตามลำดับชั้น| [Tornado chart](https://github.com/Microsoft/powerbi-visuals-tornado/) </br>เปรียบเทียบความสำคัญเชิงสัมพัทธ์ของตัวแปรระหว่างสองกลุ่ม
 | <img src="media/samples/word-cloud.png" width="200">
 | [Word Cloud](https://github.com/Microsoft/powerbi-visuals-wordcloud/) </br>สร้างวิชวลสนุกสนานจากข้อความในข้อมูลของคุณที่ใช้บ่อย

## <a name="webgl"></a>WebGL

WebGL อนุญาตให้เนื้อหาเว็บใช้ API ที่ยึดตาม OpenGL ES 2.0 เพื่อทำการแสดงภาพแบบ 2 มิติ และ 3 มิติ ในพื้นที่ทำงาน HTML

| <img src="media/samples/globe-map.png" width="250">|
| ------------- |
| [Globe Map](https://github.com/Microsoft/powerbi-visuals-globemap/) </br>ลงจุดตำแหน่งที่ตั้งลงบนแผนที่ 3 มิติแบบโต้ตอบ

## <a name="r-visuals"></a>วิชวล R

ตัวอย่างเหล่านี้สาธิตวิธีการใช้งานการวิเคราะห์และการแสดงผลด้วยภาพของวิชวล R และสคริปต์ R

| <img src="media/samples/association-rules.png" width="200">| <img src="media/samples/clustering.png" width="200">| <img src="media/samples/clustering-with-outliers.png" width="200">|
|------------- |------------- |------------- |------------- |
| [กฎความสัมพันธ์](https://github.com/Microsoft/powerbi-visuals-assorules/) </br>แสดงความสัมพันธ์ระหว่างข้อมูลที่ดูไม่เกี่ยวข้องกันโดยการใช้คำสั่ง if-then | [การทำคลัสเตอร์](https://github.com/Microsoft/powerbi-visuals-clustering-kmeans/) </br>ค้นหากลุ่มที่คล้ายคลึงกันในข้อมูลของคุณโดยใช้อัลกอริทึม k-means | [การทำคลัสเตอร์กับค่าผิดปกติ](https://github.com/microsoft/PowerBI-visuals-dbscan/) </br>ค้นหากลุ่มที่คล้ายคลึงกันและค่าผิดปกติในข้อมูลของคุณ
| <img src="media/samples/correlation-plot.png" width="200"> | <img src="media/samples/decision-tree-chart.png" width="200"> | <img src="media/samples/forecasting-tbats.png" width="200"> 
| [การลงจุดค่าสหสัมพันธ์](https://github.com/Microsoft/powerbi-visuals-corrplot/) </br>เน้นตัวแปรที่สัมพันธ์กันมากที่สุดในตารางข้อมูล | [แผนผังต้นไม้การตัดสินใจ](https://github.com/Microsoft/powerbi-visuals-decision-tree/) </br>แผนผังรูปต้นไม้ที่เป็นแบบแผนสำหรับกำหนดความน่าจะเป็นทางสถิติโดยใช้การแบ่งพาร์ติชันแบบเรียกซ้ำ | [การคาดการณ์ TBATS](https://github.com/Microsoft/powerbi-visuals-forcasting-tbats/) </br>การพยากรณ์ชุดข้อมูลเวลาสำหรับชุดข้อมูลที่มีหลาย seasonality โดยใช้แบบจำลอง TBATS
| <img src="media/samples/forecasting-with-ARIMA.png" width="200"> | <img src="media/samples/funnel-plot.png" width="200"> | <img src="media/samples/outliers-detection.png" width="200"> 
| [การคาดการณ์ด้วย ARIMA](https://github.com/Microsoft/powerbi-visuals-forcastingarima/) </br>ทำนายค่าในอนาคตโดยยึดตามข้อมูลในอดีตโดยใช้ Autoregressive Integrated Moving Avg (ARIMA) | [กราฟกรวยคว่ำ](https://github.com/Microsoft/powerbi-visuals-funnel/) </br>ค้นหาค่าผิดปกติในข้อมูลของคุณโดยใช้กราฟกรวยคว่ำ | [การตรวจจับค่าผิดปกติ](https://github.com/Microsoft/powerbi-visuals-outliers-det/) </br>ค้นหาค่าผิดปกติในข้อมูลของคุณโดยใช้วิธีการและการพล็อตกราฟที่เหมาะสมที่สุด
| <img src="media/samples/spline-chart.png" width="200"> | <img src="media/samples/time-series-decomposition-chart.png" width="200"> | <img src="media/samples/time-series-forecasting-chart.png" width="200">
| [Spline chart](https://github.com/Microsoft/powerbi-visuals-spline/) </br>แสดงภาพและทำความเข้าใจข้อมูลรบกวน | [แผนภูมิ Time series decomposition](https://github.com/Microsoft/powerbi-visuals-timeseriesdecomposition/) </br>ทำความเข้าใจคอมโพเนนต์ของชุดข้อมูลเวลาด้วย "Seasonal and Trend decomposition โดยใช้ Loess" | [แผนภูมิ Time series forecasting](https://github.com/Microsoft/powerbi-visuals-forcasting-exp/) </br>ใช้วิธี exponential smoothing เพื่อคาดการณ์ค่าอนาคตตามค่าที่ได้รับก่อนหน้านี้

## <a name="next-steps"></a>ขั้นตอนถัดไป

หากต้องการลองสร้างวิชวล Power BI โปรดดูที่ [บทช่วยสอน : การพัฒนาวิชวล Power BI](custom-visual-develop-tutorial.md)

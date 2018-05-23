---
title: โต้ตอบกับแผนผังมี ArcGIS ที่ถูกแชร์กับคุณ
description: 'ใช้แผนผัง ArcGis ในมุมมองการอ่าน '
author: mihart
manager: kfile
ms.reviewer: ''
tags: power bi, service, desktop, mobile
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/28/2018
ms.author: mihart
ms.openlocfilehash: 2a5e654062c056308431b2a94f7e2da4e3d46d17
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/17/2018
---
# <a name="interacting-with-arcgis-maps-in-power-bi"></a>โต้ตอบกับ ArcGIS แมปใน Power BI
หัวข้อนี้ถูกเขียนจากมุมมองของจุดของบุคคล*ใช้*แผน ArcGIS ในบริการ Power BI เดสก์ท็อป หรืออุปกรณ์เคลื่อนที่ เมื่อผู้สร้างการแชร์การแมป ArcGIS กับคุณ มีหลายวิธีในการโต้ตอบกับแผนผังนั้น  เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับการสร้างแผนผังมี ArcGIS ดู[ArcGIS แมป โดยบทช่วยสอนทาง esri](power-bi-visualization-arcgis.md)

ชุดข้อมูลของ ArcGIS แผนที่ และ Power BI นำการแมปนอกเหนือจากงานนำเสนอของจุดบนแผนที่ไปยังระดับใหม่ทั้งหมด ตัวเลือกที่พร้อมใช้งานสำหรับแผนที่พื้นฐาน ชนิดตำแหน่งที่ตั้ง ธีม สไตล์สัญลักษณ์ และเลเยอร์อ้างอิงสร้างการแสดงภาพของแผนที่มีข้อมูลครบครัน gorgeous ชุดข้อมูลของเลเยอร์ข้อมูลอย่างเป็นทางการ (เช่นข้อมูล census) บนแผนที่ด้วยการวิเคราะห์เชิงพื้นที่บ่งบอกเพิ้อทำความเข้าใจของข้อมูลในการแสดงภาพของคุณ

> [!TIP]
> หมายถึง GIS สำหรับข้อมูลวิทยาศาสตร์ทางภูมิศาสตร์
> 

ตัวอย่างที่เราจะใช้เป็นแผนที่ ArcGIS เดียวกันที่สร้างขึ้นในการ[ArcGIS แมป โดยบทช่วยสอนทาง esri](power-bi-visualization-arcgis.md) ซึ่งมีลักษณะที่ขายของปีที่แล้วเรียงลำดับตามเมือง และใช้ basemap ถนน สัญลักษณ์ฟองเพื่อแสดงขนาด และชั้นที่อ้างอิงสำหรับรายได้ภายในบ้านโดยเฉลี่ย แผนที่ประกอบด้วยหมุด 3 และรัศมีไดรฟ์หนึ่งครั้ง (เป็นสีม่วง)

![](media/power-bi-visualizations-arcgis/power-bi-arcgis-esri-new.png)

> [!TIP]
> เยี่ยมชม[หน้าของทาง esri บน Power BI](https://www.esri.com/powerbi)เพื่อดูตัวอย่างมาก และอ่านคำบอกเล่าจาก จากนั้นดูแผนที่ esri [สำหรับหน้าเริ่มต้น ArcGIS Maps for Power BI](https://doc.arcgis.com/en/maps-for-powerbi/get-started/about-maps-for-power-bi.htm)
> 
> 

<br/>

## <a name="user-consent"></a>ความยินยอมของผู้ใช้
ในครั้งแรกที่เพื่อนร่วมงานที่ใช้ร่วมกันแผน ArcGIS กับคุณ Power BI จะแสดงพร้อมท์ใน ArcGIS Maps for Power BI จะมีให้ทาง Esri (www.esri.com) และการใช้ ArcGIS Maps for Power BI เป็นชื่อเรื่อง โดยข้อกำหนดและนโยบายความเป็นส่วนตัวของทาง Esri Power BI ผู้ขอเมื่อต้องใช้ ArcGIS Maps for Power BI ภาพจำเป็นต้องยอมรับกล่องโต้ตอบได้รับความยินยอม

## <a name="selection-tools"></a>เติมรายการที่เลือก
ArcGIS Maps for Power BI ให้ 3 โหมดตัวเลือก คุณสามารถเลือกสูงสุดของจุดข้อมูล 250 ในแต่ละครั้ง

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-tools2.png)

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-single2.png) เลือกแต่ละจุดข้อมูล

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-marquee2.png) วาดสี่เหลี่ยมผืนผ้าบนแผนที่ และเลือกจุดข้อมูลที่มีอยู่ ใช้ CTRL เพื่อเลือกพื้นที่สี่เหลี่ยมผืนผ้ามากกว่าหนึ่งรายการ

![](media/power-bi-visualizations-arcgis/power-bi-esri-selection-reference-layer2.png) อนุญาตให้ขอบเขตหรือรูปหลายเหลี่ยมภายในเลเยอร์อ้างอิงที่จะใช้เมื่อต้องเลือกจุดข้อมูลที่มีอยู่

<br/>

## <a name="interacting-with-an-arcgis-map"></a>โต้ตอบกับแผน ArcGIS
ฟีเจอร์พร้อมใช้งานคุณขึ้นอยู่กับว่าคุณเป็น*creator* (บุคคลที่ทำการแมป) หรือ*ผู้บริโภค*(บุคคลที่ใช้ร่วมกันแผน ArcGIS กับคุณ) ถ้าคุณโต้ตอบกับแผน ArcGIS ที่เป็นผู้บริโภค (หรือ[มุมมองการอ่าน](service-reading-view-and-editing-view.md)ต่อไปนี้เป็นการกระทำที่คุณใช้งาน

* เหมือนกับชนิดการแสดงภาพอื่น ๆ คุณสามารถ[ปักหมุดกับแดชบอร์ด](service-dashboard-pin-tile-from-report.md), [มุมมอง](service-reports-show-data.md)และ/หรือ[ส่งออกข้อมูลเบื้องต้น](power-bi-visualization-export-data.md)และดูแมปเป็น[โหมดโฟกัส](service-focus-mode.md)และ[เต็มหน้าจอ](service-fullscreen-mode.md)    
* ขยายการ**ตัวกรอง**บานหน้าต่างเพื่อสำรวจแมปโดยใช้ตัวกรอง เมื่อคุณปิดรายงาน ตัวกรองที่คุณใช้จะไม่ถูกบันทึก    
    ![](media/power-bi-visualizations-arcgis/power-bi-filter-newer.png)  
* ถ้าแผนที่คุณมีเลเยอร์อ้างอิง เลือกตำแหน่งที่ตั้งเมื่อต้องแสดงรายละเอียดในคำแนะนำ ต่อไปนี้เราได้เลือกเขตเอี่ยมศิริ และดูข้อมูลจากการอ้างอิงรายได้ภายในบ้านเฉลี่ยเลเยอร์ creator ที่เพิ่มลงในแผนผัง
  
    ![](media/power-bi-visualizations-arcgis/power-bi-reference-layer.png)  
  
    ในกรณีนี้ เรายังได้รับแผนภูมิ เลือกแท่งในแผนภูมิเพื่อเจาะลึกลงในข้อมูล ต่อไปนี้เราเห็นว่า ครอบครัว 79 ตัวซึ่งในเขตเอี่ยมศิริราย $200,000 ต่อ หรือมากกว่า
  
    ![](media/power-bi-visualizations-arcgis/power-bi-tooltip-chart.png)
  
    เลือกลูกศรเมื่อต้องแสดงแผนภูมิใด ๆ เพิ่มเติม
* โฮเวอร์เหนือสัญลักษณ์ตำแหน่งที่ตั้ง basemap เมื่อต้องแสดงรายละเอียดในคำแนะนำ     
  ![](media/power-bi-visualizations-arcgis/power-bi-arcgis-hover.png)
  
  > [!TIP]
  > คุณอาจต้องการย่อ/ขยายในเมื่อต้องเลือกตำแหน่งที่ตั้งที่เฉพาะเจาะจง  มิฉะนั้น ถ้ามีจะซ้อนทับตำแหน่งที่ตั้ง Power BI อาจนำเสนอคุณแนะนำเครื่องมือมากกว่า 1 ในแต่ละครั้ง เลือกลูกศรเพื่อย้ายไปมาระหว่างคำแนะนำเครื่องมือ
  > 
  > ![](media/power-bi-visualizations-arcgis/power-bi-3-screens.png)
  > 
  > 
* ถ้าผู้สร้างมีเพิ่มเลเยอร์โฟร์มีการแมป ArcGIS คุณจะเห็นข้อมูลเพิ่มเติมที่แสดงในมุมขวาบนของแมป  ตัวอย่างเช่น นี่ผู้สร้างแผนผังเพิ่ม “เด็กอายุไม่เกิน 14 ปี”
  
    ![](media/power-bi-visualizations-arcgis/power-bi-demographics.png)

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด
ArcGIS Maps for Power BI จะพร้อมใช้งานในบริการและแอปพลิเคชันต่อไปนี้:

<table>
<tr><th>บริการ/แอป</th><th>ความพร้อมใช้งาน</th></tr>
<tr>
<td>Power BI Desktop</td>
<td>ใช่</td>
</tr>
<tr>
<td>บริการ power BI (app.powerbi.com)</td>
<td>ใช่</td>
</tr>
<tr>
<td>แอป Power BI บนมือถือ</td>
<td>ใช่</td>
</tr>
<tr>
<td>เผยแพร่ไปยัง Power BI</td>
<td>ไม่ใช่</td>
</tr>
<tr>
<td>Power BI Embedded</td>
<td>ไม่ใช่</td>
</tr>
<tr>
<td>บริการ power BI ที่ฝังตัว (PowerBI.com)</td>
<td>ไม่ใช่</td>
</tr>
</table>

**วิธีทำ ArcGIS Maps for Power BI ทำงานร่วมกันอย่างไร**
ArcGIS Maps for Power BI จะได้มาจากทาง Esri (www.esri.com) การใช้ ArcGIS Maps for Power BI คือชื่อเรื่อง โดยของทาง Esri [เงื่อนไข](https://go.microsoft.com/fwlink/?LinkID=8263222)และ[นโยบายความเป็นส่วนตัว](https://go.microsoft.com/fwlink/?LinkID=826323) Power BI ผู้ขอเมื่อต้องใช้ ArcGIS Maps for Power BI ภาพจำเป็นต้องยอมรับกล่องโต้ตอบได้รับความยินยอม  ใช้ ArcGIS Maps for Power BI ของทาง Esri อาจมีของทาง Esri ข้อกำหนดและนโยบายความเป็นส่วนตัว ซึ่งยังได้เชื่อมโยงกับจากกล่องโต้ตอบได้รับความยินยอม แต่ละผู้ใช้ต้องยินยอมก่อนที่จะใช้ ArcGIS Maps for Power BI เป็นครั้งแรก เมื่อผู้ใช้ยอมรับความยินยอม ข้อมูลที่ผูกไว้กับภาพจะถูกส่งไปยังบริการของทาง Esri น้อยสำหรับการกำหนดพิกัดทางภูมิศาสตร์ ซึ่งหมายความว่า การแปลงข้อมูลตำแหน่งที่ตั้งลงในข้อมูลละติจูดและลองจิจูดที่สามารถแสดงได้ในแผนผังไว้ คุณควรถือว่า ข้อมูลใด ๆ ที่ผูกอยู่กับการแสดงภาพข้อมูลสามารถถูกส่งไปยังบริการของทาง Esri ทาง Esri มีบริการต่าง ๆ เช่นแผนที่พื้นฐาน การวิเคราะห์เชิงพื้นที่ กำหนดพิกัดทางภูมิศาสตร์ เป็นต้น ArcGIS Maps for Power BI ที่ภาพโต้ตอบกับบริการเหล่านี้โดยใช้การเชื่อมต่อ SSL ที่ได้รับการป้องกัน โดยใบรับรองที่ให้ไว้ และยังคงรักษา โดยทาง Esri สามารถรับข้อมูลเพิ่มเติมเกี่ยวกับ ArcGIS Maps for Power BI จากของทาง Esri [ArcGIS Maps for Power BI หน้าผลิตภัณฑ์](https://www.esri.com/powerbi)ได้

เมื่อผู้ใช้ลงชื่อค่าสำหรับเครื่องหมายบวกสมัครใช้งานนำเสนอ โดยทาง Esri ผ่าน ArcGIS Maps for Power BI พวกเขากำลังใส่ลงในข้อความสัมพันธ์โดยตรงกับทาง Esri Power BI ส่งข้อมูลส่วนบุคคลเกี่ยวกับผู้ใช้ไปยังทาง Esri ผู้ใช้ลงชื่อเข้าใช้ และเชื่อถือทาง Esri มีให้แอปพลิเคชัน AAD โดยใช้ข้อมูลประจำตัวของพวกเขาเอง AAD ด้วยการดำเนินการดังกล่าว ผู้ใช้ที่จะแชร์ข้อมูลส่วนบุคคลของพวกเขาโดยตรงกับทาง Esri เมื่อผู้ใช้เพิ่มเครื่องหมายบวกเนื้อหาเมื่อต้องการ ArcGIS Maps for Power BI visual นอกจากนี้ผู้ใช้ Power BI ต้องเป็นเครื่องหมายบวกสมัครใช้งานจากทาง Esri เพื่อดู หรือแก้ไขเนื้อหานั้น 

สำหรับการคำถามโดยละเอียดทางเทคนิคเกี่ยวกับวิธีการทำงานของ ArcGIS Maps for Power BI ของทาง Esri สื่อสารกับทาง Esri ผ่านไซต์ฝ่ายสนับสนุนของพวกเขา

**ไม่สามารถแสดงแผนที่ ArcGIS**    
ในบริการหรือแอปพลิเคชันที่ไม่พร้อมใช้งาน ArcGIS Maps for Power BI การแสดงภาพจะแสดงเป็นว่างภาพ มีโลโก้ Power BI

**ฉันไม่เห็นทั้งหมดที่อยู่ของฉันบนแผนที่**    
เมื่อกำหนดพิกัดทางภูมิศาสตร์ถนนที่อยู่ ที่อยู่ก่อน 1500 เท่านั้นคือภูมิศาสตร์ ชื่อกำหนดพิกัดทางภูมิศาสตร์หรือหลายประเทศไม่ได้อาจ มีขีดจำกัดอยู่ 1500

**มีค่าธรรมเนียมใด ๆ สำหรับการใช้ ArcGIS Maps for Power BI หรือไม่**

แผนผัง ArcGIS สำหรับ Power BI จะพร้อมใช้งานผู้ใช้ Power BI ทั้งหมดโดยไม่มีค่าใช้จ่ายเพิ่มเติม ซึ่งเป็นคอมโพเนนต์ที่ให้มาโดย**ทาง Esri**และการใช้งานจะขึ้นอยู่กับข้อกำหนดและนโยบายความเป็นส่วนตัวที่ให้มาโดย**ทาง Esri**ตามที่บันทึกไว้ก่อนหน้านี้ในบทความนี้

**ฉันได้รับข้อผิดพลาดเกี่ยวกับแคของฉันกำลังแบบเต็ม**

นี่คือข้อบกพร่องที่กำลังส่ง  ในระหว่างนี้ เลือกลิงก์ที่ปรากฏในข้อความข้อผิดพลาดสำหรับคำแนะนำในการล้างแคช Power BI ของคุณ

**ฉันสามารถดู ArcGIS maps ของฉันแบบออฟไลน์ได้หรือไม่**

ไม่ Power BI จำเป็นต้องเชื่อมต่อเครือข่ายเมื่อต้องแสดงแผนที่แบบ

## <a name="next-steps"></a>ขั้นตอนถัดไป
ขอความช่วยเหลือ: **ทาง Esri**แสดง[เอกสารที่ครอบคลุม](https://go.microsoft.com/fwlink/?LinkID=828772)ชุดคุณลักษณะของ**ArcGIS Maps for Power BI**

คุณสามารถถามคำถาม ค้นหาข้อมูลล่าสุด รายงานปัญหา และค้นหาคำตอบใน Power BI [เธรดชุมชนที่เกี่ยวข้องกับ**ArcGIS Maps for Power BI**](https://go.microsoft.com/fwlink/?LinkID=828771)ได้

ถ้าคุณมีคำแนะนำสำหรับการปรับปรุงประสิทธิภาพ โปรดส่งเพื่อ[รายการแนวคิดของ Power BI](https://ideas.powerbi.com)

[ใช้ ArcGIS Maps for Power BI หน้าผลิตภัณฑ์](https://www.esri.com/powerbi)


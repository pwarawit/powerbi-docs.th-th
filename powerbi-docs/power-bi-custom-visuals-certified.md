---
title: การแสดงภาพแบบกำหนดเองของ Power BI ที่ผ่านการรับรอง
description: ข้อกำหนดและกระบวนการที่จะส่งวิชวลแบบกำหนดเองเพื่อผ่านการรับรอง และรายการของวิชวลแบบกำหนดเองที่ผ่านการรับรองแล้ว
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 02/13/2018
ms.author: mihart
ms.openlocfilehash: 4676b31a117573d1d69b5947ec2380c4abf29405
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2018
ms.locfileid: "44726880"
---
# <a name="getting-a-custom-visual-certified"></a>การนำวิชวลแบบกำหนดเอง*เข้ารับการรับรอง*
## <a name="what-is-meant-by-certified"></a>*การรับรอง*หมายถึงอะไร
*วิชวลแบบกำหนดเองที่ผ่านการรับรองแล้ว* คือวิชวลที่โค้ดผ่านเงื่อนไขที่กำหนด และผ่านการทดสอบความปลอดภัยที่เข้มงวด  เมื่อวิชวลแบบกำหนดเองได้ผ่านการรับรองแล้ว สามารถ[ส่งออกวิชวลไปยัง PowerPoint](service-publish-to-powerpoint.md) และแสดงในอีเมลเมื่อผู้ใช้[สมัครสมาชิกไปยังหน้ารายงาน](service-report-subscribe.md)ได้ แน่นอน มันยังสามารถใช้งานได้เช่นเดียวกับ[วิชวลแบบกำหนดเองมาตรฐาน](power-bi-custom-visuals.md) และถูกเพิ่มเข้าไปในบริการของ Power BI และรายงานของ Power BI Desktop และสามารถดูได้ใน Power BI บนอุปกรณ์เคลื่อนที่ และที่ฝังตัวได้

คุณเป็นนักพัฒนาเว็บ และสนใจสร้างการแสดงภาพของคุณเอง และเพิ่มเข้าไปใน [Microsoft AppSource](https://appsource.microsoft.com) หรือไม่ ดู [เริ่มต้นใช้งานเครื่องมือสำหรับนักพัฒนา](service-custom-visuals-getting-started-with-developer-tools.md) เพื่อเรียนรู้วิธีการ


## <a name="certification-requirements"></a>ข้อบังคับสำหรับการรับรอง
* ต้องได้รับอนุมัติจาก Microsoft AppSource    
* วิชวลแบบกำหนดเอง ต้องเขียนด้วย API รุ่น 1.2 หรือสูงกว่า    
* เก็บรหัสในที่สามารถตรวจสอบได้ (เช่น โค้ดของวิชวล สามารถดึงผ่าน GitHub)    
* ใช้เฉพาะ OSS สาธารณะที่สามารถตรวจสอบได้เป็นส่วนประกอบ    
* ไม่เข้าถึงบริการหรือแหล่งข้อมูลภาพนอก    

> **เคล็ดลับ**: เราขอแนะนำให้ คุณใช้ EsLint กับชุดกฎความปลอดภัยเริ่มต้น เพื่อการตรวจสอบรหัสของคุณ ก่อนส่งมาให้เรา
> 
> 

## <a name="process-for-submitting-a-custom-visual-for-certification"></a>กระบวนการการส่งวิชวลแบบกำหนดเองเพื่อการรับรอง
เมื่อต้องการส่งวิชวลแบบกำหนดเองไปขอการรับรอง:

1. ส่งอีเมลไปยังฝ่ายสนับสนุน วิชวลแบบกำหนดเองของ Power BI (pbicvsupport@microsoft.com) ในอีเมล ให้ระบุข้อมูลต่อไปนี้:    

   * หัวข้อ: Visual Certification Request    
   * ลิงก์ไปยังที่เก็บ GitHub ที่ใช้เก็บโค้ด    
   * ยึดตามข้อกำหนดที่ให้ (ดูด้านบน)    
   * ผ่านการรีวิวโค้ดและความปลอดภัย    

2. ทีมงานวิชวลแบบกำหนดเองที่ Microsoft จะแจ้งให้คุณทราบเมื่อวิชวลแบบกำหนดเองของคุณได้รับการรับรอง และถูกเพิ่มลงในรายการวิชวลที่ผ่านการรับรองแล้ว (ตามด้านล่าง) หรือถูกปฏิเสธพร้อมกับรายงานปัญหาที่ต้องแก้ไข เป็นความรับผิดชอบของนักพัฒนา ที่ต้องเปิดช่องทางการติดต่อสื่อสารกับ Microsoft และปรับปรุงวิชวลที่ผ่านการรับรองแล้ว ถ้าจำเป็น

## <a name="removal-of-power-bi-certified-custom-visuals"></a>การถอดการรับรอง วิชวลแบบกำหนดเองของ Power BI
Microsoft ขอสงวนสิทธิ์ในการลบวิชวล จากรายการของวิชวลที่ผ่านการรับรองได้  

## <a name="list-of-custom-visuals-that-have-been-certified"></a>รายการวิชวลแบบกำหนดเองที่ผ่านการรับรองแล้ว

| ลิงก์ไปยัง AppSource | ลิงก์ไปยังวิดีโอ |
| --- | --- |
| [Aster Plot](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380759) | |
| [Beyondsoft Calendar](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096) | |
| [Bowtie Chart by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380838) | [วิดีโอ](https://youtu.be/So5xKMSpVJI) |
| [Box and Whisker chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380831) | |
| [Box and Whisker chart by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381351) | [วิดีโอ](https://youtu.be/JoHaFLfhXdo) |
| [Brick Chart by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380836) | [วิดีโอ](https://youtu.be/hA3DOsvn2xY) |
| [Bubble Chart by Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381340) | |
| [Bullet Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380755) | [วิดีโอ](https://youtu.be/AOlsFYkfkcw) |
| [Bullet Chart by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380953) | [วิดีโอ](https://youtu.be/mtvUNl9bMjA) |
| [Calendar by Tallan](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381146) | |
| [Candlestick by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380952) | [วิดีโอ](https://youtu.be/nT_18gyRxPo) |
| [Card with States by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380967) | |
| [Chiclet Slicer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380756) | |
| [Chord](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380761) | [วิดีโอ](https://youtu.be/AQvd2FhRyCI) |
| [Circular Gauge by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380837) | [วิดีโอ](https://youtu.be/9NHXALkBXuY) |
| [Cluster Map](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380806) | |
| [Cylindrical Gauge by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380874) | [วิดีโอ](https://youtu.be/DgdoWi7Gcxo) |
| [Dial Gauge](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381184) | |
| [Dot Plot](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380760) | |
| [Dot Plot by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380949) | [วิดีโอ](https://youtu.be/By16pX9KT40) |
| [Drilldown Cartogram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381045) | |
| [Drilldown Choropleth](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381044) | |
| [Drill-down column chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380857) | [วิดีโอ](https://youtu.be/lBy2gQQ5YsQ) |
| [Drill-down column chart for time based data](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881) | [วิดีโอ](https://youtu.be/T_mRou18vx0) |
| [Drill-down donut chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | [วิดีโอ](https://youtu.be/AUVFrSHmPeo) |
| [Dual KPI](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380774) | |
| [Dynamic Tooltip by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380983) | [วิดีโอ](https://youtu.be/Z-tl97BpEr0) |
| [Enhanced Scatter](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380762) | [วิดีโอ](https://youtu.be/xCfM0cjM4do) |
| [Enlighten Aquarium](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381112) | |
| [Enlighten Slicer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380960) | |
| [Enlighten Stack Shuffle](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380849) | |
| [Enlighten Waffle Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380850) | |
| [Force-Directed Graph](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380764) | [วิดีโอ](https://youtu.be/YsTa7uyJ4sg) |
| [Funnel with Source by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381334) | [วิดีโอ](https://youtu.be/R_EcimsLI8U) |
| [Gantt](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380765) | [วิดีโอ](https://youtu.be/qJ7s_KrGiUU) |
| [Gantt Chart by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381364) | [วิดีโอ](https://youtu.be/vJLV9JRCpI8) |
| [Globe Data Bars](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381344) | |
| [Grid by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380825) | [วิดีโอ](https://youtu.be/VOPoDJgZfOY) |
| [Hierarchy Chart by Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381333) | [วิดีโอ](https://youtu.be/0ZGzJaq_KT4) |
| [Histogram Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380776) | |
| [Histogram with points by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381032) | [วิดีโอ](https://youtu.be/-ILF--wExrw) |
| [Horizontal Funnel by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380846) | [วิดีโอ](https://youtu.be/SudZei68PPo) |
| [Image by CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381297) | |
| [Image Grid](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381355) | |
| [Infographic Designer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380898) | |
| [KPI Chart by Akvelon](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381432) | |
| [KPI Column by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380996) | [วิดีโอ](https://youtu.be/rU0xoOlIq1U) |
| [KPI Grid โดย MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380947) | [วิดีโอ](https://youtu.be/dM4PvZh71V0) |
| [KPI Indicator](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380832) | |
| [KPI Ticker by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380946) | [วิดีโอ](https://youtu.be/cudG4gsZ2V8) |
| [Linear Gauge by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380821) | [วิดีโอ](https://youtu.be/7_jFaM30dkc) |
| [LineDot Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380766) | |
| [Mekko Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380785) | [วิดีโอ](https://youtu.be/90FLCKpgicA) |
| [ภาพรวม โดย CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381477) | |
| [Play Axis (Dynamic Slicer)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380981) | |
| [Power KPI](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381083) | [วิดีโอ](https://youtu.be/IvfIP3E6-1Q) |
| [Power KPI Matrix](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381299) | [วิดีโอ](https://youtu.be/1enze8pcGzY) |
| [Pulse Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006) | [วิดีโอ](https://youtu.be/DQWdcQtjDVw) |
| [Quadrant Chart by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381011) | [วิดีโอ](https://youtu.be/ppBnyhqWNC0) |
| [Radar Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380771) | |
| [Ring Chart by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824) | [วิดีโอ](https://youtu.be/pDToHDFHnq8) |
| [Rotating Chart by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381007) | [วิดีโอ](https://youtu.be/d5xBCMmb3hU) |
| [Sankey Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380777) | [วิดีโอ](https://youtu.be/WWP9wVUHGaA) |
| [Scroller](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381018) | |
| [Smart Filter by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380859) | [วิดีโอ](https://youtu.be/gcJsDDRQq28) |
| [Sparkline by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380910) | [วิดีโอ](https://youtu.be/0m3Vnvso9tY) |
| [Graph](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380772) | |
| [Sunburst](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380767) | |
| [Synoptic Panel by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380873) | |
| [Table Heatmap](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380818) | |
| [Tachometer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380937) | [วิดีโอ](https://youtu.be/C3OXdETbS9o) |
| [Text Filter](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381309) | |
| [Text Wrapper by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380826) | |
| [Thermometer by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380847) | [วิดีโอ](https://youtu.be/SPX9mgrAdBc) |
| [ตัวแบ่งเวลา](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380798) | |
| [Timeline Slicer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380786) | [วิดีโอ](https://youtu.be/ozMtZ4_NZ10) |
| [ไทม์ไลน์ โดย CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381427) | [วิดีโอ](https://youtu.be/szNi9YgXFJc) |
| [Tornado chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380768) | [วิดีโอ](https://www.youtube.com/watch?v=AQvd2FhRyCI) |
| [Trading Chart by MAQ Software](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380823) | [วิดีโอ](https://youtu.be/xhTR6y6J9Ko) |
| [Ultimate Variance](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381140) | [วิดีโอ](https://youtu.be/pDYF8iZxERs) |
| [Ultimate Waterfall](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380956) | [วิดีโอ](https://youtu.be/0BZsVCQdEkc) |
| [รายชื่อผู้ใช้ โดย CloudScope](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381426) | |
| [Waffle Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381049) | [วิดีโอ](https://youtu.be/1vRqYUsm3Vk) |
| [Word Cloud](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380752) | [วิดีโอ](https://youtu.be/AblTenl9fqo) |

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งานเครื่องมือสำหรับนักพัฒนาวิชวลแบบกำหนดเอง (ตัวอย่าง)](service-custom-visuals-getting-started-with-developer-tools.md)      
[รายการเพลย์ลิสต์ วิชวลแบบกำหนดเองของ Microsoft บน YouTube](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[การแสดงข้อมูลใน Power BI](visuals/power-bi-report-visualizations.md)  
[การแสดงข้อมูลแบบกำหนดเองใน Power BI](power-bi-custom-visuals.md)  
[การเผยแพร่วิชวลแบบกำหนดเองไปยัง Microsoft AppSource](developer/office-store.md)  
ถ้าคุณมีคำถามเพิ่มเติม [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


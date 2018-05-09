---
title: ฝังรายงานโดยใช้ iFrame
description: เซิร์ฟเวอร์รายงาน Power BI สามารถติดตั้งตัวเองได้รวดเร็วมาก จากการดาวน์โหลด การติดตั้ง และการกำหนดค่า คุณควรจะพร้อมทำงานภายในไม่กี่นาที
services: powerbi
documentationcenter: ''
author: markingmyname
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
ms.date: 11/09/2017
ms.author: maghan
ms.openlocfilehash: 56835bfb25c8c930099fadf710137f69fa89fc2e
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/30/2018
---
# <a name="quickstart-embed-a-power-bi-report-using-an-iframe-and-url-parameters"></a>เริ่มการใช้งานด่วน: ฝังรายงาน Power BI โดยใช้ iFrame และพารามิเตอร์ URL

คุณสามารถฝังรายงานต่างๆโดยใช้ iFrame ในแอปพลิเคชันของคุณ 

## <a name="url-parameter"></a>พารามิเตอร์ URL

URL สำหรับรายงาน คุณสามารถเพิ่มพารามิเตอร์สตริงแบบสอบถาม`?rs:Embed=true`ได้

ตัวอย่างเช่น:

```
http://myserver/reports/powerbi/Sales?rs:embed=true
```

สิ่งนี้จะทำงานบนรายงานทุกชนิดภายในเซิร์ฟเวอร์รายงาน Power BI

## <a name="iframe"></a>iFrame

เมื่อคุณมี URL ของคุณ คุณสามารถสร้าง iFrame ภายในเว็บเพจเพื่อโฮสต์รายงาน

ตัวอย่างเช่น:

```
<iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
```

## <a name="url-filter"></a>ตัวกรอง URL

คุณสามารถเพิ่มพารามิเตอร์สตริงแบบสอบถามไปยัง URL เพื่อกรองข้อมูลที่ส่งกลับในรายงาน Power BI

ไวยากรณ์ที่ตรงไปตรงมา เช่น เริ่มต้นด้วย URL ของรายงาน เพิ่มเครื่องหมายคำถาม และไวยากรณ์ตัวกรองนี้

URL?filter=***ตาราง***/***ฟิลด์*** eq '***ค่า***'

คำนึงถึงข้อควรพิจารณาเหล่านี้:

- **ชื่อตาราง**และ**เขตข้อมูล**จำเป็นต้องระบุ **แต่ค่า**ไม่จำเป็น
- คุณสามารถกรองรายงานที่มีเขตข้อมูลที่ถูกซ่อนจากมุมมองรายงาน
- **ค่า**ต้องอยู่ระหว่างเครื่องหมายอัญประกาศเดี่ยว
- ชนิดเขตข้อมูลจะต้องเป็นสตริง
- ชื่อตารางและเขตข้อมูลต้องไม่มีช่องว่าง

###  <a name="example-filter-on-a-field"></a>ตัวอย่าง: ตัวกรองบนเขตข้อมูล

ใช้เป็นตัวอย่าง เช่น [ตัวอย่างการวิเคราะห์ร้านค้าปลีก](../sample-datasets.md) ระบุว่านี่คือ URL สำหรับรายงานบนเซิร์ฟเวอร์รายงานในโฟลเดอร์ที่ชื่อว่า "power bi":

```
https://report-server/reports/power-bi/Retail-Analysis-Sample
```

คุณเห็นการแสดงภาพแผนที่ในตัวอย่างการวิเคราะห์ร้านค้าปลีกที่แสดงร้านค้าใน North Carolina และรัฐอื่นๆ

![การแสดงภาพของแผนที่ตัวอย่างการวิเคราะห์ร้านค้าปลีก](media/quickstart-embed/report-server-retail-analysis-sample-map.png)

*NC*เป็นค่าสำหรับ North Carolina ที่ถูกเก็บไว้ใน**เขตข้อมูล**ดินแดนของการ**ตาราง**ร้านค้า ดังนั้น การกรองรายงานเพื่อแสดงข้อมูลเฉพาะสำหรับร้านค้าใน North Carolina เพิ่มข้อมูลต่อไปนี้ลงใน URL:

?filter=Store/Territory eq 'NC'

ขณะนี้รายงานถูกกรองสำหรับ North Carolina แล้ว เช่น การแสดงภาพทั้งหมดบนหน้ารายงานเพื่อแสดงข้อมูลสำหรับ North Carolina เท่านั้น

![การแสดงภาพที่กรองตัวอย่างการวิเคราะห์ร้านค้าปลีก](media/quickstart-embed/report-server-retail-analysis-sample-filtered-map.png)

### <a name="create-a-dax-formula-to-filter-on-multiple-values"></a>สร้างสูตร DAX เพื่อกรองข้อมูลสำหรับค่าหลายค่า

อีกวิธีหนึ่งเพื่อกรองหลายเขตข้อมูลคือการสร้างคอลัมน์จากการคำนวณลงใน Power BI Desktop ที่รวมเขตข้อมูลสองเขตเป็นค่าเดียว จากนั้น คุณจะสามารถกรองค่านั้นได้

ตัวอย่างเช่น ตัวอย่างการวิเคราะห์ร้านค้าปลีกมีเขตข้อมูลสองเขต: ดินแดนและสาขา ใน Power BI Desktop คุณสามารถ[สร้างคอลัมน์จากการคำนวณ](../desktop-tutorial-create-calculated-columns.md)(เขตข้อมูล) ที่เรียกว่า TerritoryChain ได้ โปรดจำไว้ว่า ชื่อ**เขตข้อมูล**ต้องไม่มีช่องว่าง นี่คือสูตร DAX สำหรับคอลัมน์นั้น

TerritoryChain = [Territory] & "-" & [Chain]

เผยแพร่รายงานไปยังเซิร์ฟเวอร์รายงาน Power BI จากนั้นใช้สตริงแบบสอบถาม URL ในการกรองเพื่อแสดงข้อมูลสำหรับร้านค้า Lindseys ใน NC เท่านั้น

```
https://report-server/reports/power-bi/Retail-Analysis-Sample?filter=Store/TerritoryChain eq 'NC-Lindseys'

```

## <a name="next-steps"></a>ขั้นตอนถัดไป

[เริ่มต้นใช้งานด่วน: สร้างรายงาน Power BI สำหรับเซิร์ฟเวอร์รายงาน Power BI](quickstart-create-powerbi-report.md)  
[เริ่มต้นใช้งานด่วน: สร้างรายงานที่มีการแบ่งหน้าสำหรับเซิร์ฟเวอร์รายงาน Power BI](quickstart-create-paginated-report.md)  

คุณมีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
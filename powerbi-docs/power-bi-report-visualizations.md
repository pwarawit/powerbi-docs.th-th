---
title: ภาพรวมของการแสดงภาพรายงานในบริการของ Power BI และ Power BI Desktop
description: ภาพรวมของการแสดงภาพรายงาน (วิชวล) ใน Microsoft Power BI
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: SYk_gWrtKvM
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/21/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: f0e0dc02fc07849c68c00ce857da0ccbeb2d76df
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34240198"
---
# <a name="visualizations-in-power-bi-reports"></a>การแสดงภาพในรายงาน Power BI
การแสดงภาพ (หรือวิชวล) แสดงข้อมูลเชิงลึกค้นพบแล้วในข้อมูล รายงาน Power BI อาจมีหน้าเดียวกับหนึ่งวิชวล หรืออาจมีหลายหน้าที่เต็มไปด้วยวิชวล ในบริการของ Power BI วิชวลสามารถ[ถูกปักหมุดจากรายงานไปยังแดชบอร์ด](service-dashboard-pin-tile-from-report.md)ได้ 

การแยกความแตกต่างระหว่าง*ผู้สร้าง*รายงานและ*ผู้บริโภค*รายงานเป็นเรื่องสำคัญ ถ้าคุณเป็นบุคคลที่สร้างหรือปรับเปลี่ยนรายงาน คุณถือเป็นผู้สร้าง  ผู้สร้างมีสิทธิ์แก้ไขรายงานและชุดข้อมูลพื้นฐานของรายงานนั้น ใน Power BI Desktop นี่หมายความว่า คุณสามารถเปิดชุดข้อมูลในมุมมองข้อมูล และสร้างวิชวลในมุมมองรายงาน ในบริการของ Power BI นี่หมายความว่า คุณสามารถเปิดชุดข้อมูลหรือรายงานในตัวแก้ไขรายงาน ใน[มุมมองการแก้ไข](service-reading-view-and-editing-view.md) ถ้ารายงานหรือแดชบอร์ด[ถูกแชร์ให้กับคุณ](service-shared-with-me.md) คุณกำลังเป็น**ผู้บริโภค**รายงาน คุณจะสามารถดู และโต้ตอบกับรายงานและวิชวลในนั้น แต่คุณไม่สามารถบันทึกการเปลี่ยนแปลง

มีชนิดของวิชวลต่าง ๆ มากมาย จากบานหน้าต่าง การจัดรูปแบบการแสดงข้อมูล BI Power 

![](media/power-bi-report-visualizations/power-bi-visualizations.png)

และสำหรับตัวเลือกเพิ่มเติมยิ่งขึ้นไปอีก โปรดไป[ไซต์ชุมชน Microsoft AppSource](https://appsource.microsoft.com) เพื่อค้นหา และดาวน์โหลด[วิชวลแบบกำหนดเอง](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals&page=1)จาก Microsoft และชุมชน    

<iframe width="560" height="315" src="https://www.youtube.com/embed/SYk_gWrtKvM?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


  ถ้าคุณยังใหม่กับ Power BI หรือต้องการการทบทวน ใช้ลิงก์ด้านล่างเพื่อเรียนรู้พื้นฐานของการแสดงภาพใน Power BI  อีกวิธีหนึ่งคือ ใช้ตารางเนื้อหาของเรา (อยู่ตลอดด้านซ้ายของบทความนี้) เพื่อค้นหาข้อมูลอีกมากที่เป็นประโยชน์

## <a name="add-a-visualization-in-power-bi"></a>เพิ่มการแสดงภาพใน Power BI
[สร้างการแสดงภาพ](power-bi-report-add-visualizations-i.md)ในหน้าของรายงานของคุณ เรียกดู[รายการการแสดงภาพที่มี และบทช่วยสอนการแสดงภาพที่มี](power-bi-visualization-types-for-reports-and-q-and-a.md) 

## <a name="upload-a-custom-visualization-and-use-it-in-power-bi"></a>อัปโหลดการแสดงภาพแบบกำหนดเอง และใช้ใน Power BI
เพิ่มการแสดงภาพแบบกำหนดเอง ที่คุณสร้างขึ้นด้วยตัวเอง หรือว่าคุณพบใน[ไซต์ชุมชน Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) รู้สึกมีความคิดสร้างสรรค์ขึ้นมาไหม? เจาะลึกลงในโค้ดต้นฉบับของเรา และใช้[เครื่องมือสำหรับนักพัฒนา](service-custom-visuals-getting-started-with-developer-tools.md)ของเรา เพื่อสร้างการแสดงภาพชนิดใหม่ และ[แชร์กับชุมชน](developer/office-store.md)

## <a name="change-the-visualization-type"></a>การเปลี่ยนชนิดของการแสดงภาพ
ลอง[เปลี่ยนชนิดของการแสดงภาพ](power-bi-report-change-visualization-type.md) เพื่อดูว่าแบบไหนที่ดีที่สุดสำหรับข้อมูลของคุณ

## <a name="pin-the-visualization"></a>ปักหมุดการแสดงภาพ
ในบริการของ Power BI เมื่อคุณมีการแสดงภาพตามแบบคุณที่ต้องการแล้ว คุณสามารถ[ปักหมุดไปยังแดชบอร์ด](service-dashboard-pin-tile-from-report.md)ให้เป็นไทล์ได้ ถ้าคุณเปลี่ยนการแสดงภาพที่ถูกใช้ในรายงานหลังจากที่คุณปักหมุดแล้ว ไทล์ในแดชบอร์ดจะไม่เปลี่ยนแปลง - ถ้าแผนภูมิเส้น ไทล์ในแดชบอร์ดก็ยังคงเป็นแผนภูมิเส้น แม้ว่าคุณทำเปลี่ยนเป็นในแผนภูมิโดนัทแล้วในรายงาน

## <a name="next-steps"></a>ขั้นตอนถัดไป
[ชนิดการแสดงภาพใน Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
[รายงานใน Power BI](service-reports.md)  
[แดชบอร์ดใน Power BI](service-dashboards.md)  
[Power BI แนวคิดพื้นฐาน](service-basic-concepts.md)  
มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


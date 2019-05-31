---
title: ภาพรวมของการแสดงภาพรายงานในบริการของ Power BI และ Power BI Desktop
description: ภาพรวมของการแสดงภาพรายงาน (วิชวล) ใน Microsoft Power BI
author: mihart
ms.author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: SYk_gWrtKvM
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/28/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: d470a262bd8a5e6590746fb07889b1230f5cfc25
ms.sourcegitcommit: 8bf2419b7cb4bf95fc975d07a329b78db5b19f81
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "66375664"
---
# <a name="visualizations-in-power-bi-reports"></a>การแสดงภาพในรายงาน Power BI

การแสดงภาพ (หรือวิชวล) แสดงข้อมูลเชิงลึกค้นพบแล้วในข้อมูล รายงาน Power BI อาจมีหน้าเดียวกับหนึ่งวิชวล หรืออาจมีหลายหน้าที่เต็มไปด้วยวิชวล ในบริการของ Power BI วิชวลสามารถ[ถูกปักหมุดจากรายงานไปยังแดชบอร์ด](../service-dashboard-pin-tile-from-report.md)ได้

จำเป็นต้องทำให้ความแตกต่างระหว่างรายงาน*นัก*และรายงาน*ผู้บริโภค*ถ้าคุณเป็นบุคคลที่สร้าง หรือปรับเปลี่ยนรายงาน จาก นั้นคุณจะออกแบบ  ตัวออกแบบมีสิทธิ์แก้ไขรายงานและชุดข้อมูลเบื้องต้น ใน Power BI Desktop นี่หมายความว่า คุณสามารถเปิดชุดข้อมูลในมุมมองข้อมูล และสร้างวิชวลในมุมมองรายงาน ในบริการ Power BI ซึ่งหมายความว่า คุณสามารถเปิดชุดข้อมูลหรือรายงานในตัวแก้ไขรายงานใน[มุมมองการแก้ไข](../consumer/end-user-reading-view.md) ถ้ารายงานหรือแดชบอร์ด[ถูกแชร์ให้กับคุณ](../consumer/end-user-shared-with-me.md) คุณกำลังเป็น**ผู้บริโภค**รายงาน คุณจะสามารถดู และโต้ตอบกับรายงานและวิชวลในนั้น แต่คุณไม่สามารถบันทึกการเปลี่ยนแปลงหลัก

มีชนิดของวิชวลต่าง ๆ มากมาย จากบานหน้าต่าง การจัดรูปแบบการแสดงข้อมูล BI Power

![](media/power-bi-report-visualizations/power-bi-templates.png)

และสำหรับตัวเลือกเพิ่มเติม โปรดไปที่[ไซต์ชุมชน Microsoft AppSource](https://appsource.microsoft.com) เพื่อค้นหา และ[ดาวน์โหลด](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals)[การแสดงผลด้วยภาพแบบกำหนดเอง](../developer/custom-visual-develop-tutorial.md) จาก Microsoft และชุมชน

<iframe width="560" height="315" src="https://www.youtube.com/embed/SYk_gWrtKvM?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


  ถ้าคุณยังใหม่กับ Power BI หรือต้องการการทบทวน ใช้ลิงก์ด้านล่างเพื่อเรียนรู้พื้นฐานของการแสดงภาพใน Power BI  อีกวิธีหนึ่งคือ ใช้ตารางเนื้อหาของเรา (อยู่ตลอดด้านซ้ายของบทความนี้) เพื่อค้นหาข้อมูลอีกมากที่เป็นประโยชน์

## <a name="add-a-visualization-in-power-bi"></a>เพิ่มการแสดงภาพใน Power BI

[สร้างการแสดงภาพ](power-bi-report-add-visualizations-i.md)ในหน้าของรายงานของคุณ เรียกดู[รายการการแสดงภาพที่มี และบทช่วยสอนการแสดงภาพที่มี](power-bi-visualization-types-for-reports-and-q-and-a.md) 

## <a name="upload-a-custom-visualization-and-use-it-in-power-bi"></a>อัปโหลดการแสดงภาพแบบกำหนดเอง และใช้ใน Power BI

เพิ่มการแสดงภาพแบบกำหนดเอง ที่คุณสร้างขึ้นด้วยตัวเอง หรือว่าคุณพบใน[ไซต์ชุมชน Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) รู้สึกมีความคิดสร้างสรรค์? เจาะลึกลงในโค้ดต้นฉบับของเรา และใช้[เครื่องมือสำหรับนักพัฒนา](../developer/custom-visual-develop-tutorial.md)เพื่อสร้างการแสดงภาพชนิดใหม่ และ[แชร์กับชุมชน](../developer/office-store.md) หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับการพัฒนาการแสดงภาพแบบกำหนดเอง โปรดไปที่ [การพัฒนาภาพแบบกำหนดเองสำหรับ Power BI](../developer/custom-visual-develop-tutorial.md)

## <a name="change-the-visualization-type"></a>การเปลี่ยนชนิดของการแสดงภาพ

ลอง[เปลี่ยนชนิดของการแสดงภาพ](power-bi-report-change-visualization-type.md) เพื่อดูว่าแบบไหนที่ดีที่สุดสำหรับข้อมูลของคุณ

## <a name="pin-the-visualization"></a>ปักหมุดการแสดงภาพ

ในบริการของ Power BI เมื่อคุณมีการแสดงภาพตามแบบคุณที่ต้องการแล้ว คุณสามารถ[ปักหมุดไปยังแดชบอร์ด](../service-dashboard-pin-tile-from-report.md)ให้เป็นไทล์ได้ ถ้าคุณเปลี่ยนการแสดงภาพที่ถูกใช้ในรายงานหลังจากที่คุณปักหมุดแล้ว ไทล์ในแดชบอร์ดจะไม่เปลี่ยนแปลง - ถ้าแผนภูมิเส้น ไทล์ในแดชบอร์ดก็ยังคงเป็นแผนภูมิเส้น แม้ว่าคุณทำเปลี่ยนเป็นในแผนภูมิโดนัทแล้วในรายงาน

## <a name="limitations-and-considerations"></a>ข้อจำกัดและข้อควรพิจารณา
- ขึ้นอยู่กับแหล่งข้อมูลและจำนวนของเขตข้อมูล (หน่วยวัดหรือคอลัมน์), วิชวลอาจโหลดได้ช้าลง  เราขอแนะนำให้จำกัดภาพเพื่อ 10 20 เขตข้อมูลผลรวม ทั้งเหตุผลในการอ่านและประสิทธิภาพการทำงาน 

- ขีดจำกัดบนสำหรับวิชวลมีเขตข้อมูล 100 (หน่วยวัดหรือคอลัมน์) ถ้าไม่สามารถโหลดวิชวลของคุณ ลดจำนวนของเขตข้อมูล   

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [ชนิดการแสดงภาพใน Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
* [การแสดงผลด้วยภาพแบบกำหนดเอง](../power-bi-custom-visuals.md)
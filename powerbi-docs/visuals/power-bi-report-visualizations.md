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
ms.date: 07/01/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: aabc58e34e5ba61f44673905450c8feb8d6ace47
ms.sourcegitcommit: e67bacbfc5638ee97e3d2e0e7f5bd2d9aac78f9c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/02/2019
ms.locfileid: "67532251"
---
# <a name="visualizations-in-power-bi-reports"></a>การแสดงภาพในรายงาน Power BI

การแสดงภาพ (หรือเรียกสั้น ๆ ว่าวิชวล) จะแสดงข้อมูลเชิงลึกที่ค้นพบในข้อมูล รายงาน Power BI อาจมีหน้าเดียวกับหนึ่งวิชวล หรืออาจมีหลายหน้าที่เต็มไปด้วยวิชวล ในบริการของ Power BI วิชวลสามารถ[ถูกปักหมุดจากรายงานไปยังแดชบอร์ด](../service-dashboard-pin-tile-from-report.md)ได้

สิ่งสำคัญคือต้องสร้างความแตกต่างระหว่าง *ผู้ออกแบบ*รายงาน และ*ผู้ใช้*รายงาน  ถ้าคุณเป็นผู้สร้างหรือแก้ไขรายงาน คุณจะกลายเป็นผู้ออกแบบ  ผู้ออกแบบมีสิทธิ์แก้ไขรายงานและชุดข้อมูลพื้นฐานของรายงานนั้น ใน Power BI Desktop นี่หมายความว่า คุณสามารถเปิดชุดข้อมูลในมุมมองข้อมูล และสร้างวิชวลในมุมมองรายงาน ในบริการของ Power BI นี่หมายความว่าคุณสามารถเปิดชุดข้อมูลหรือรายงานในตัวแก้ไขรายงานใน [มุมมองการแก้ไข](../consumer/end-user-reading-view.md) ถ้ารายงานหรือแดชบอร์ด[ถูกแชร์ให้กับคุณ](../consumer/end-user-shared-with-me.md) คุณกำลังเป็น**ผู้บริโภค**รายงาน คุณจะสามารถดู และโต้ตอบกับรายงานและวิชวลในนั้นได้ แต่คุณไม่สามารถบันทึกการเปลี่ยนแปลงที่สำคัญ

มีชนิดของวิชวลต่าง ๆ มากมาย จากบานหน้าต่าง การจัดรูปแบบการแสดงข้อมูล BI Power

![](media/power-bi-report-visualizations/power-bi-templates.png)

และสำหรับตัวเลือกเพิ่มเติม โปรดไปที่[ไซต์ชุมชน Microsoft AppSource](https://appsource.microsoft.com) เพื่อค้นหา และ[ดาวน์โหลด](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals)[การแสดงผลด้วยภาพแบบกำหนดเอง](../developer/custom-visual-develop-tutorial.md) จาก Microsoft และชุมชน

<iframe width="560" height="315" src="https://www.youtube.com/embed/SYk_gWrtKvM?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


ถ้าคุณยังใหม่กับ Power BI หรือต้องการการทบทวน ใช้ลิงก์ด้านล่างเพื่อเรียนรู้พื้นฐานของการแสดงภาพใน Power BI  อีกวิธีหนึ่งคือ ใช้ตารางเนื้อหาของเรา (อยู่ตลอดด้านซ้ายของบทความนี้) เพื่อค้นหาข้อมูลอีกมากที่เป็นประโยชน์

## <a name="add-a-visualization-in-power-bi"></a>เพิ่มการแสดงภาพใน Power BI

[สร้างการแสดงภาพ](power-bi-report-add-visualizations-i.md)ในหน้าของรายงานของคุณ เรียกดู[รายการการแสดงภาพที่มี และบทช่วยสอนการแสดงภาพที่มี](power-bi-visualization-types-for-reports-and-q-and-a.md) 

## <a name="upload-a-custom-visualization-and-use-it-in-power-bi"></a>อัปโหลดการแสดงภาพแบบกำหนดเอง และใช้ใน Power BI

เพิ่มการแสดงภาพแบบกำหนดเอง ที่คุณสร้างขึ้นด้วยตัวเอง หรือว่าคุณพบใน[ไซต์ชุมชน Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) รู้สึกมีความคิดสร้างสรรค์? เจาะลึกลงในโค้ดต้นฉบับของเรา และใช้[เครื่องมือสำหรับนักพัฒนา](../developer/custom-visual-develop-tutorial.md)เพื่อสร้างการแสดงภาพชนิดใหม่ และ[แชร์กับชุมชน](../developer/office-store.md) หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับการพัฒนาการแสดงภาพแบบกำหนดเอง โปรดไปที่ [การพัฒนาภาพแบบกำหนดเองสำหรับ Power BI](../developer/custom-visual-develop-tutorial.md)

## <a name="personalize-your-visualization-pane-preview"></a>ปรับแต่งบานหน้าต่างการแสดงภาพของคุณ (ตัวอย่าง)

ถ้าคุณพบว่าตัวคุณเองใช้วิชวลแบบกำหนดเองเหมือนกันในหลาย ๆ รายงาน คุณสามารถปักหมุดการแสดงภาพแบบกำหนดเองไปยังบานหน้าต่างการแสดงภาพของคุณ เมื่อต้องการปักหมุดการแสดงภาพ คลิกขวาบนภาพเพื่อปักหมุดไปยังบานหน้าต่าง

![ปักหมุดไปยังบานหน้าต่างการแสดงภาพ](media/power-bi-report-visualizations/power-bi-pin-custom-visual-option.png)

เมื่อปักหมุดวิชวลแล้ว วิชวลจะย้ายขึ้นเพื่อต่อเข้ากับวิชวลภายในตัวอื่น ๆ วิชวลนี้จะเชื่อมโยงกับบัญชีที่ลงชื่อเข้าใช้ของคุณตอนนี้ ดังนั้นรายงานใหม่ใด ๆ ที่คุณสร้างจะประกอบด้วยวิชวลนี้โดยอัตโนมัติ เสมือนว่าคุณได้ลงชื่อเข้าใช้แล้ว ซึ่งทำให้การกำหนดมาตรฐานบนวิชวลเฉพาะง่ายมากโดยไม่ต้องเพิ่มวิชวลลงในรายงานเดียวทุกฉบับ

![บานหน้าต่างการแสดงภาพที่ปรับแต่งแล้ว](media/power-bi-report-visualizations/power-bi-personalized-visualization-pane.png)

ขณะที่คุณสมบัตินี้อยู่ในตัวอย่าง คุณจะเห็นวิชวลที่ปักหมุดไว้ใน Power BI Desktop เท่านั้น นอกจากนี้ คุณต้องลงชื่อเข้าใช้คุณสมบัตินี้เพื่อให้สามารถใช้งานได้

## <a name="change-the-visualization-type"></a>การเปลี่ยนชนิดของการแสดงภาพ

ลอง[เปลี่ยนชนิดของการแสดงภาพ](power-bi-report-change-visualization-type.md) เพื่อดูว่าแบบไหนที่ดีที่สุดสำหรับข้อมูลของคุณ

## <a name="pin-the-visualization"></a>ปักหมุดการแสดงภาพ

ในบริการของ Power BI เมื่อคุณมีการแสดงภาพตามแบบคุณที่ต้องการแล้ว คุณสามารถ[ปักหมุดไปยังแดชบอร์ด](../service-dashboard-pin-tile-from-report.md)ให้เป็นไทล์ได้ ถ้าคุณเปลี่ยนการแสดงภาพที่ถูกใช้ในรายงานหลังจากที่คุณปักหมุดแล้ว ไทล์ในแดชบอร์ดจะไม่เปลี่ยนแปลง - ถ้าแผนภูมิเส้น ไทล์ในแดชบอร์ดก็ยังคงเป็นแผนภูมิเส้น แม้ว่าคุณทำเปลี่ยนเป็นในแผนภูมิโดนัทแล้วในรายงาน

## <a name="limitations-and-considerations"></a>ข้อจำกัดและข้อควรพิจารณา
- วิชวลอาจโหลดช้า ทั้งขึ้นอยู่กับแหล่งข้อมูลและจำนวนของเขตข้อมูล (หน่วยวัดหรือคอลัมน์)  เราขอแนะนำให้จำกัดวิชวลให้เหลือเพียง 10-20 เขตข้อมูล ทั้งนี้เพื่อเหตุผลในการอ่านและประสิทธิภาพการทำงาน 

- ขีดจำกัดสูงสุดสำหรับวิชวลอยู่ที่ 100 เขตข้อมูล (หน่วยวัดหรือคอลัมน์) ถ้าไม่สามารถโหลดวิชวลได้ ให้ลดจำนวนของเขตข้อมูล   

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [ชนิดการแสดงภาพใน Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
* [การแสดงผลด้วยภาพแบบกำหนดเอง](../power-bi-custom-visuals.md)

---
title: ภาพรวมของการแสดงภาพรายงานในบริการของ Power BI และ Power BI Desktop
description: ภาพรวมของการแสดงภาพรายงาน (วิชวล) ใน Microsoft Power BI
author: mihart
ms.author: mihart
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/05/2020
LocalizationGroup: Visualizations
ms.openlocfilehash: 65a6ab132cccc56d96f5ac22fef5d80f59f96ca9
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83277559"
---
# <a name="visualizations-in-power-bi-reports"></a>การแสดงภาพในรายงาน Power BI

[!INCLUDE[consumer-appliesto-yyyn](../includes/consumer-appliesto-yyyn.md)]    

การแสดงภาพ (หรือเรียกสั้น ๆ ว่าวิชวล) จะแสดงข้อมูลเชิงลึกที่ค้นพบในข้อมูล รายงาน Power BI อาจมีหน้าเดียวกับหนึ่งวิชวล หรืออาจมีหลายหน้าที่เต็มไปด้วยวิชวล ในบริการของ Power BI คุณสามารถ[ปักหมุดวิชวลจากรายงานไปยังแดชบอร์ด](../create-reports/service-dashboard-pin-tile-from-report.md)ได้

สิ่งสำคัญคือต้องสร้างความแตกต่างระหว่าง *ผู้ออกแบบ*รายงาน และ*ผู้ใช้*รายงาน  ถ้าคุณเป็นผู้สร้างหรือแก้ไขรายงาน คุณจะกลายเป็นผู้ออกแบบ  ผู้ออกแบบมีสิทธิ์แก้ไขรายงานและชุดข้อมูลพื้นฐานของรายงานนั้น ใน Power BI Desktop นี่หมายความว่า คุณสามารถเปิดชุดข้อมูลในมุมมองข้อมูล และสร้างวิชวลในมุมมองรายงาน ในบริการของ Power BI นี่หมายความว่าคุณสามารถเปิดชุดข้อมูลหรือรายงานในตัวแก้ไขรายงานใน [มุมมองการแก้ไข](../consumer/end-user-reading-view.md) ถ้ารายงานหรือแดชบอร์ด[ถูกแชร์ให้กับคุณ](../consumer/end-user-shared-with-me.md) คุณกำลังเป็น*ผู้บริโภค*รายงาน คุณจะสามารถดูและโต้ตอบกับรายงานและวิชวลของรายงานได้ แต่คุณจะไม่สามารถทำการเปลี่ยนแปลงได้มากเท่าที่*นักออกแบบ*สามารถทำได้

มีวิชวลชนิดต่าง ๆ มากมายให้คุณเลือกใช้งานจากบานหน้าต่างการจัดรูปแบบการแสดงข้อมูล Power BI โดยตรง

![บานหน้าต่างที่มีไอคอนสำหรับการจัดรูปแบบการแสดงข้อมูลแต่ละชนิด](media/power-bi-report-visualizations/power-bi-icons.png)

และสำหรับตัวเลือกเพิ่มเติมยิ่งขึ้นไปอีก โปรดไปที่ [ไซต์ชุมชน Microsoft AppSource](https://appsource.microsoft.com) เพื่อค้นหา และ[ดาวน์โหลด](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) [วิชวล Power BI](../developer/visuals/custom-visual-develop-tutorial.md) จาก Microsoft และชุมชน

ถ้าคุณยังใหม่กับ Power BI หรือต้องการการทบทวน ใช้ลิงก์ด้านล่างเพื่อเรียนรู้พื้นฐานของการแสดงภาพใน Power BI  อีกวิธีหนึ่งคือ ใช้ตารางเนื้อหาของเรา (อยู่ตลอดด้านซ้ายของบทความนี้) เพื่อค้นหาข้อมูลอีกมากที่เป็นประโยชน์

## <a name="add-a-visualization-in-power-bi"></a>เพิ่มการแสดงภาพใน Power BI

[สร้างการแสดงภาพ](power-bi-report-add-visualizations-i.md)ในหน้าของรายงานของคุณ เรียกดู[รายการการแสดงภาพที่มี และบทช่วยสอนการแสดงภาพที่มี](power-bi-visualization-types-for-reports-and-q-and-a.md) 

## <a name="upload-a-custom-visualization-and-use-it-in-power-bi"></a>อัปโหลดการแสดงภาพแบบกำหนดเอง และใช้ใน Power BI

เพิ่มการแสดงภาพแบบกำหนดเอง ที่คุณสร้างขึ้นด้วยตัวเอง หรือว่าคุณพบใน[ไซต์ชุมชน Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) รู้สึกมีความคิดสร้างสรรค์? เจาะลึกลงในโค้ดต้นฉบับของเรา และใช้[เครื่องมือสำหรับนักพัฒนา](../developer/visuals/custom-visual-develop-tutorial.md)เพื่อสร้างการแสดงภาพชนิดใหม่ และ[แชร์กับชุมชน](../developer/visuals/office-store.md) หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับการพัฒนาการแสดงภาพแบบกำหนดเอง โปรดไปที่ [การพัฒนาภาพแบบกำหนดเองสำหรับ Power BI](../developer/visuals/custom-visual-develop-tutorial.md)

## <a name="personalize-your-visualization-pane-preview"></a>ปรับแต่งบานหน้าต่างการแสดงภาพของคุณ (ตัวอย่าง)

ถ้าคุณพบว่าตัวคุณเองใช้วิชวลแบบกำหนดเองเหมือนกันในหลาย ๆ รายงาน คุณสามารถปักหมุดการแสดงภาพแบบกำหนดเองไปยังบานหน้าต่างการแสดงภาพของคุณ เมื่อต้องการปักหมุดการแสดงภาพ คลิกขวาบนภาพเพื่อปักหมุดไปยังบานหน้าต่าง

![ปักหมุดไปยังบานหน้าต่างการแสดงภาพ](media/power-bi-report-visualizations/power-bi-pin-custom-visual-option.png)

เมื่อปักหมุดวิชวลแล้ว วิชวลจะย้ายขึ้นเพื่อต่อเข้ากับวิชวลภายในตัวอื่น ๆ วิชวลนี้จะเชื่อมโยงกับบัญชีที่ลงชื่อเข้าใช้ของคุณตอนนี้ ดังนั้นรายงานใหม่ใดก็ตามที่คุณสร้างจะประกอบด้วยวิชวลนี้โดยอัตโนมัติ เสมือนว่าคุณได้ลงชื่อเข้าใช้แล้ว ซึ่งทำให้การกำหนดมาตรฐานบนวิชวลเฉพาะง่ายมากโดยไม่ต้องเพิ่มวิชวลลงในรายงานเดียวทุกฉบับ

![บานหน้าต่างการแสดงภาพที่ปรับแต่งแล้ว](media/power-bi-report-visualizations/power-bi-personalized-visualization-pane.png)

ขณะที่คุณสมบัตินี้อยู่ในตัวอย่าง คุณจะเห็นวิชวลที่ปักหมุดไว้ใน Power BI Desktop เท่านั้น นอกจากนี้ คุณต้องลงชื่อเข้าใช้คุณสมบัตินี้เพื่อให้สามารถใช้งานได้

## <a name="change-the-visualization-type"></a>การเปลี่ยนชนิดของการแสดงภาพ

ลอง[เปลี่ยนชนิดของการแสดงภาพ](power-bi-report-change-visualization-type.md) เพื่อดูว่าแบบไหนที่ดีที่สุดสำหรับข้อมูลของคุณ

## <a name="pin-the-visualization"></a>ปักหมุดการแสดงภาพ

ในบริการของ Power BI เมื่อคุณมีการแสดงภาพตามแบบคุณที่ต้องการแล้ว คุณสามารถ[ปักหมุดไปยังแดชบอร์ด](../create-reports/service-dashboard-pin-tile-from-report.md)ให้เป็นไทล์ได้ ถ้าคุณเปลี่ยนการแสดงภาพที่ถูกใช้ในรายงานหลังจากที่คุณปักหมุดแล้ว ไทล์ในแดชบอร์ดจะไม่เปลี่ยนแปลง - ถ้าแผนภูมิเส้น ไทล์ในแดชบอร์ดก็ยังคงเป็นแผนภูมิเส้น แม้ว่าคุณทำเปลี่ยนเป็นในแผนภูมิโดนัทแล้วในรายงาน

## <a name="limitations-and-considerations"></a>ข้อจำกัดและข้อควรพิจารณา
- วิชวลอาจโหลดช้า ทั้งขึ้นอยู่กับแหล่งข้อมูลและจำนวนของเขตข้อมูล (หน่วยวัดหรือคอลัมน์)  เราขอแนะนำให้จำกัดวิชวลให้เหลือเพียง 10-20 เขตข้อมูล ทั้งนี้เพื่อเหตุผลในการอ่านและประสิทธิภาพการทำงาน 

- ขีดจำกัดสูงสุดสำหรับวิชวลอยู่ที่ 100 เขตข้อมูล (หน่วยวัดหรือคอลัมน์) ถ้าไม่สามารถโหลดวิชวลได้ ให้ลดจำนวนของเขตข้อมูล   

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [ชนิดการแสดงภาพใน Power BI](power-bi-visualization-types-for-reports-and-q-and-a.md)
* [วิชวล Power BI](../developer/visuals/power-bi-custom-visuals.md)

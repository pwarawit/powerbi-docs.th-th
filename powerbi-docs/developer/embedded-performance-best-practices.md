---
title: แนวทางปฏิบัติที่ดีที่สุดเพื่อประสิทธิภาพการทำงานของ Power BI Embedded
description: บทความนี้มีคำแนะนำสำหรับแนวทางปฏิบัติที่ดีที่สุดเพื่อการวิเคราะห์แบบฝัง
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-embedded
ms.topic: conceptual
ms.date: 12/12/2018
ms.openlocfilehash: d0f4ca29e30e5f6e6176f036dc535601eb580471
ms.sourcegitcommit: 298db44200b78b1281b3ae6dfe7cce7a89865ec9
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/13/2018
ms.locfileid: "53329889"
---
# <a name="power-bi-embedded-performance-best-practices"></a>แนวทางปฏิบัติที่ดีที่สุดเพื่อประสิทธิภาพการทำงานของ Power BI Embedded

บทความนี้มีคำแนะนำสำหรับการแสดงรายงาน แดชบอร์ด และไทล์ในแอปพลิเคชันของคุณได้เร็วขึ้น

## <a name="embed-parameters"></a>พารามิเตอร์แบบฝัง

เมธอด Powerbi.embed() รับพารามิเตอร์บางอย่างเพื่อฝังรายงาน แดชบอร์ด หรือไทล์ พารามิเตอร์เหล่านี้มีผลกระทบต่อประสิทธิภาพการทำงาน

### <a name="embed-url"></a>URL แบบฝัง

หลีกเลี่ยงการสร้าง URL แบบฝังด้วยตัวคุณเอง แต่คุณควรตรวจสอบให้แน่ใจว่าคุณได้รับ URL แบบฝัง โดยการเรียก API [รับรายงาน](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Freports%2Fgetreportsingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256168308&sdata=22lkqRM2w1MQfrM8dooedaPqqIU8PufTq9TT4VDzRo0%3D&reserved=0), [รับแดชบอร์ด](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Fdashboards%2Fgetdashboardsingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256168308&sdata=nfWRgbSoXVF42Rg%2Ba9491u19uksXp%2FAyz%2Fa%2Ba7%2FCtdA%3D&reserved=0) หรือ[รับไทล์](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Frest%2Fapi%2Fpower-bi%2Fdashboards%2Fgettilesingroup&data=02%7C01%7CMark.Ghanayem%40microsoft.com%7C07ca68ceb37a48e3f3de08d64968707a%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636777110256178318&sdata=LgZ27TynNpqQJDrb3aHWGQXIS%2FzichAO9De5M2uhF1Q%3D&reserved=0) เราได้เพิ่มพารามิเตอร์ใหม่ใน URL ที่เรียกว่า **_config_** ใช้สำหรับการปรับปรุงประสิทธิภาพการทำงาน

### <a name="permissions"></a>สิทธิ์

ระบุสิทธิ**ดู** หากคุณไม่ต้องการฝังรายงานใน **โหมดแก้ไข** โค้ดที่ฝังด้วยวิธีนี้จะไม่เริ่มต้นคอมโพเนนต์ซึ่งใช้สำหรับโหมดแก้ไข

### <a name="filters-bookmarks-and-slicers"></a>ตัวกรอง บุ๊กมาร์ก และตัวแบ่งส่วนข้อมูล

โดยปกติ วิชวลในรายงานจะถูกบันทึกด้วยข้อมูลที่แคช ข้อมูลที่แคชถูกนำมาใช้เพื่อประสิทธิภาพการทำงานที่ดีมากขึ้น รายงานจะแสดงข้อมูลที่แคชขณะดำเนินการคิวรี ถ้ามีตัวกรอง บุ๊กมาร์ก หรือตัวแบ่งส่วนข้อมูล ข้อมูลที่แคชจะไม่เกี่ยวข้อง จากนั้น วิชวลจะแสดงเฉพาะหลังจากเรียกใช้คิวรีวิชวลเท่านั้น

ถ้าคุณฝังรายงานด้วยตัวกรองเดียวกัน ให้บันทึกรายงานด้วยตัวกรองที่ใช้ไปแล้วเพื่อหลีกเลี่ยงการส่งรายการตัวกรองในการกำหนดค่าโหลด

## <a name="preload"></a>พรีโหลด

ใช้ API *พรีโหลด* ของ JavaScript เพื่อปรับปรุงประสิทธิภาพการทำงานของผู้ใช้ปลายทาง
Powerbi.preload() ดาวน์โหลด javascript ไฟล์ css และ วัตถุอื่น ๆ ซึ่งถูกใช้ในภายหลังเพื่อฝังในรายงาน

เรียกพรีโหลดหากคุณไม่ได้ฝังรายงานไว้ทันที ตัวอย่างเช่น หากคุณฝังรายงานไว้ด้วยการคลิกปุ่ม จะเป็นการดีสำหรับการเรียกพรีโหลดเมื่อโหลดหน้าก่อนหน้า จากนั้น เมื่อผู้ใช้แอปพลิเคชันคลิกที่ปุ่ม การแสดงภาพจะเร็วขึ้น

## <a name="measure-performance"></a>วัดประสิทธิภาพการทำงาน

เพื่อวัดประสิทธิภาพการทำงาน โปรดใช้:

1. โหลดแล้ว: เวลาจนกว่ารายงานจะเริ่มต้นได้ (ผู้ใช้ไม่เห็น spinny)
2. แสดงผลแล้ว: เวลาจนกว่ารายงานทั้งหมดจะแสดงผลโดยใช้ข้อมูลจริง เหตุการณ์ที่แสดงผลถูกเรียกใช้ในแต่ละครั้งที่มีการแสดงผลรายงานอีกครั้ง (นั่นคือหลังจากใช้ตัวกรอง) ในการวัดรายงานก่อน คุณควรแน่ใจว่าคุณทำการคำนวณในเหตุการณ์ที่เกิดขึ้นครั้งแรกแล้ว

แสดงข้อมูลที่แคชเมื่อพร้อมใช้งาน แต่เรายังไม่มีเหตุการณ์สำหรับข้อมูลนี้

## <a name="update-tools-and-sdk-packages"></a>เครื่องมืออัปเดตและแพคเกจ SDK

ปรับปรุงเครื่องมือและแพคเกจ SDK ให้ทันสมัยอยู่เสมอ

* ใช้ [Power Bi Desktop](https://powerbi.microsoft.com/en-us/desktop/) เวอร์ชันล่าสุดเสมอ

* ติดตั้ง [Power BI client SDK](https://github.com/Microsoft/PowerBI-JavaScript) เวอร์ชันล่าสุด เรายังคงมีการปรับปรุงประสิทธิภาพเพิ่มเติมอย่างต่อเนื่อง ดังนั้นอย่าลืมติดตามเป็นครั้งคราว

* แพคเกจที่จะติดตั้ง:
    * แพคเกจ Npm: powerbi-client
    * แพคเกจ NuGet: Microsoft.PowerBI.JavaScript

> [!Note]
> โปรดทราบว่าเวลาโหลดขึ้นอยู่กับองค์ประกอบที่เกี่ยวข้องกับรายงานและข้อมูลเป็นหลัก เช่น จำนวนของวิชวล ขนาดของข้อมูล และความซับซ้อนของคิวรีและการวัดที่คำนวณได้ โปรดทำตาม[แนวทางปฏิบัติที่ดีที่สุด](../power-bi-reports-performance.md)เพื่อปรับปรุงเวลาการโหลดรายงาน

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [รายงานประสิทธิภาพ](../power-bi-reports-performance.md)
* [วิธีการแก้ไขปัญหา Power BI Embedded](embedded-troubleshoot.md)
* [คำถามที่พบบ่อยสำหรับ Power BI Embedded](embedded-faq.md)

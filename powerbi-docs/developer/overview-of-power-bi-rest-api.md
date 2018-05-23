---
title: ฉันสามารถใช้ Power BI API ทำอะไรได้บ้าง
description: ฉันสามารถใช้ Power BI API ทำอะไรได้บ้าง
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 07/20/2017
ms.author: maghan
ms.openlocfilehash: 47dd0ab87b78e344de176ebe22a1e5dc9753b9b0
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/17/2018
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>นักพัฒนาสามารถใช้ Power BI API ทำอะไรได้บ้าง
Power BI แสดงแดชบอร์ดที่สามารถโต้ตอบกับผู้ใช้ และสามารถสร้างและปรับปรุงข้อมูลจากแหล่งข้อมูลที่หลากหลายในเวลาจริง คุณสามารถสร้างแอปที่ทำงานร่วมกับแดชบอร์ด Power BI ในเวลาจริงได้ โดยใช้ภาษาการเขียนโปรแกรมใด ๆ ที่รองรับการเรียกใช้ REST คุณยังสามารถรวมไทล์และรายงาน Power BI เข้าไปในแอป

นักพัฒนายังสามารถสร้างการแสดงภาพจากข้อมูลของพวกเขาเอง ที่สามารถใช้ในรายงานและแดชบอร์ดที่โต้ตอบกับผู้ใช้ได้ 

ต่อไปนี้เป็นตัวอย่าง สิ่งที่คุณสามารถทำได้ด้วย Power BI API

| **เมื่อต้องการทำสิ่งต่อไปนี้** | **ให้ไปที่** |
| --- | --- |
| ฝังแดชบอร์ด รายงาน และไทล์ สำหรับผู้ใช้ Power BI และผู้ที่ไม่ใช้ Power BI (ข้อมูลที่แอปเป็นเจ้าของ) |[คุณจะฝัง แดชบอร์ด รายงาน และไทล์ Power BI ของคุณได้อย่างไร](embedding-content.md) |
| ขยายเวิร์กโฟลว์ทางธุรกิจที่มีอยู่แล้ว โดยการพุชข้อมูลสำคัญลงในแดชบอร์ด Power BI |[การพุชข้อมูลลงในแดชบอร์ด](walkthrough-push-data.md) |
| นำเข้าไฟล์ Power BI Desktop |[นำเข้าไฟล์ PBIX](https://msdn.microsoft.com/library/mt243837.aspx) |
| การรับรองความถูกต้องกับ Power BI |[การรับรองความถูกต้องกับ Power BI](get-azuread-access-token.md) |
| สร้างวิชวลแบบกำหนดเอง |[ใช้เครื่องมือสำหรับนักพัฒนา มาสร้างวิชวลแบบกำหนดเอง](../service-custom-visuals-getting-started-with-developer-tools.md) |

> [!NOTE]
> Power BI API ยังคงเรียก พื้นที่ทำงานแอป ว่า กลุ่ม เมื่อใดที่อ้างอิงถึงกลุ่ม หมายความว่าคุณกำลังทำงานกับพื้นที่ทำงานแอป
> 
> 

## <a name="power-bi-developer-samples"></a>ตัวอย่างสำหรับนักพัฒนา Power BI
ตัวอย่างสำหรับนักพัฒนา Power BI มีไฟล์ที่เอาไว้ใช้ฝังแดชบอร์ด รายงาน และไทล์

[ตัวอย่างสำหรับนักพัฒนา Power BI](https://github.com/Microsoft/PowerBI-Developer-Samples)

* ตัวอย่างภายใน **App Owns Data** สำหรับใช้ฝังกรณี ผู้ที่ไม่ได้ใช้ Power BI
* ตัวอย่างภายใน **User Owns Data** สำหรับใช้ฝังกรณี ผู้ใช้ Power BI

## <a name="github-repositories"></a>ที่เก็บ GitHub
* [.NET SDK](https://github.com/Microsoft/PowerBI-CSharp)
* [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)
* [วิชวลแบบกำหนดเอง](https://github.com/Microsoft/PowerBI-visuals)

## <a name="developer-tools"></a>เครื่องมือสำหรับนักพัฒนา
ต่อไปนี้คือ เครื่องมือที่คุณสามารถใช้เพื่อช่วยการพัฒนาสิ่งต่าง ๆ สำหรับ Power BI

* [ตัวอย่างการฝังด้วย JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[การพุชข้อมูลลงในชุดข้อมูล](walkthrough-push-data.md)  
[เริ่มต้นใช้งานเครื่องมือสำหรับนักพัฒนาวิชวลแบบกำหนดเอง](../service-custom-visuals-getting-started-with-developer-tools.md) 
[แหล่งอ้างอิง Power BI REST API](https://msdn.microsoft.com/library/mt147898.aspx)  

ถ้าคุณมีคำถามเพิ่มเติม [ลองถามชุมชน Power BI](http://community.powerbi.com/)


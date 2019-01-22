---
title: ข้อจำกัดของ Power BI REST API
description: 'Power BI REST API มีข้อจำกัดดังต่อไปนี้:'
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: df17563d384359fe33123ed87743754bb33bf04d
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54278001"
---
# <a name="power-bi-rest-api-limitations"></a>ข้อจำกัดของ Power BI REST API  
  
**การโพสต์แถว**  
  
* สูงสุด 75 คอลัมน์
* สูงสุด 75 ตาราง
* สามารถขอแถวได้สูงสุด 10,000 แถวต่อหนึ่งโพสต์  
* ภายใน 1 ชั่วโมงสามารถเพิ่มแถวได้ 1,000,000 แถวต่อหนึ่งชุดข้อมูล  
* สามารถส่งคำขอโพสต์แถวได้สูงสุด 5 คำขอต่อหนึ่งชุดข้อมูล  
* ภายใน 1 นาทีสามารถส่งคำขอ 120 โพสต์แถวต่อหนึ่งชุดข้อมูล
* ถ้าตารางมีแถว 250,000 แถวหรือมากกว่า จะสามารถส่งคำขอได้ 120 โพสต์แถวต่อ 1ชั่วโมงสำหรับแต่ละชุดข้อมูล    
* สามารถเก็บแถวได้สูงสุด 200,000 แถวต่อ 1 ตารางในชุดข้อมูล FIFO  
* สามารถเก็บแถวได้สูงสุด 5,000,000 แถวต่อ 1 ตารางในชุดข้อมูลที่ชื่อ ' ไม่มีข้อบังคับสำหรับการเก็บข้อมูล'  
* ขั้นตอนการโพสต์แถวอนุญาตให้มีเพียง 4000 ตัวอักษรต่อค่าตัวเลขในสตริงคอลัมน์
  
## <a name="see-also"></a>ดูเพิ่มเติม

[ข้อจำกัดและข้อปฏิบัติของบริการ Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-service-limits-restrictions)   
[ภาพรวมของ Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/)
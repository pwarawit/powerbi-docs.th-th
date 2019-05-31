---
title: ข้อจำกัดของ Power BI REST API
description: 'Power BI REST API มีข้อจำกัดดังต่อไปนี้:'
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 6699167cecebea5085eff4621c077096fd4c6c2e
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "61385154"
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
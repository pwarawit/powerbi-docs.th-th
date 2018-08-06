---
title: นักพัฒนาสามารถทำอะไรกับ Power BI ได้บ้าง
description: Power BI มีหลากหลายตัวเลือกสำหรับนักพัฒนา ซึ่งมีช่วงตั้งแต่การฝังเพื่อกำหนดวิชวลเองและการสตรีมชุดข้อมูล
author: markingmyname
ms.author: maghan
ms.date: 05/25/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 07fb8d365a6fe4a874b057a71a90a99fc8a9e5fa
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34564707"
---
# <a name="what-can-developers-do-with-power-bi"></a>นักพัฒนาสามารถทำอะไรกับ Power BI ได้บ้าง

นักพัฒนามีตัวเลือกอื่นในการพยายามใส่เนื้อหา Power BI ลงในแอปพลิเคชัน ตัวเลือกเหล่านี้รวมถึง**ที่ฝังด้วย Power BI** **วิชวลแบบกำหนดเอง**และ**พุชข้อมูลลงใน Power BI**

## <a name="embedding"></a>การฝังตัว
บริการ Power BI (SaaS) และบริการ Power BI Embedded ใน Azure (PaaS) มี API สำหรับการฝังสำหรับแดชบอร์ดและรายงาน ซึ่งหมายความว่าคุณมีชุดความสามารถและการเข้าถึงคุณลักษณะล่าสุดของ Power BI อย่างเช่น แดชบอร์ด เกตเวย์ และพื้นที่ทำงานแอปฯ เมื่อทำการฝังเนื้อหา

คุณสามารถเข้าถึง[เครื่องมือประสบการณ์การเตรียมความพร้อม](https://aka.ms/embedsetup) เพื่อเริ่มต้นใช้งานได้อย่างรวดเร็ว และดาวน์โหลดแอปพลิเคชันตัวอย่างได้

เลือกโซลูชันที่เหมาะกับคุณ:
* [การฝังตัวสำหรับลูกค้าของคุณ](embedding.md#embedding-for-your-customers) จะมอบความสามารถในการฝังแดชบอร์ดและรายงานสำหรับผู้ใช้ที่ไม่มีบัญชี Power BI เรียกใช้โซลูชัน[การฝังตัวสำหรับลูกค้าของคุณ](https://aka.ms/embedsetup/AppOwnsData)
* [การฝังตัวสำหรับองค์กรของคุณ](embedding.md#embedding-for-your-organization) ให้คุณสามารถขยายบริการของ Power BI เรียกใช้โซลูชัน[การฝังตัวสำหรับองค์กรของคุณ](https://aka.ms/embedsetup/UserOwnsData)

![ตัวอย่าง PBIE](media/what-can-you-do/what-can-you-do-02.png)

## <a name="develop-custom-visuals"></a>พัฒนาวิชวลแบบกำหนดเอง
วิชวลแบบกำหนดเองจะช่วยให้คุณสามารถสร้างภาพของคุณเองสำหรับการใช้งานภายในรายงาน Power BI วิชวลแบบกำหนดเองจะถูกเขียนในภาษา TypeScript ซึ่งเป็นเซตใหญ่ของ JavaScript TypeScript สนับสนุนคุณลักษณะขั้นสูงและสิทธิ์การเข้าถึงฟังก์ชัน ES6/ES7 บางอย่าง การกำหนดลักษณะวิชวลจะได้รับการจัดการโดยใช้ cascading styles sheets (css). เพื่อความสะดวกของคุณ เราใช้ Less เป็นพรีคอมไพเลอร์ซึ่งสนับสนุนคุณลักษณะขั้นสูงบางอย่าง เช่น การซ้อน ตัวแปร เงื่อนไข ลูป ฯลฯ ถ้าคุณไม่ต้องการใช้คุณลักษณะเหล่านั้น คุณเพียงแค่เขียน plain css ลงใน less file

![ตัวอย่าง CV](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>ส่งข้อมูลไปยัง Power BI
คุณสามารถใช้ API Power BI เพื่อส่งข้อมูลไปยังชุดข้อมูล ซึ่งทำให้คุณสามารถเพิ่มแถวลงในตารางภายในชุดข้อมูลได้ จากนั้น ข้อมูลใหม่จะสามารถสะท้อนผลในไทล์บนแดชบอร์ด และในวิชวลภายในรายงานของคุณ

![ตัวอย่างการส่งข้อมูล](media/what-can-you-do/powerbi-push-data.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[การฝังด้วย Power BI](embedding.md)  
[เผยแพร่วิชวลแบบกำหนดเองไปยัง Office store](office-store.md)  
[การพุชข้อมูลลงในแดชบอร์ด](walkthrough-push-data.md)

---
title: การวิเคราะห์แบบฝังตัวด้วย Power BI
description: Power BI มี API เพื่อใช้การวิเคราะห์แบบฝังตัวสำหรับแดชบอร์ดและรายงานในแอปพลิเคชัน เรียนรู้เพิ่มเติมเกี่ยวกับการฝังด้วย Power BI ทั้งในสภาพแวดล้อม PaaS และสภาพแวดล้อม SaaS โดยใช้ซอฟต์แวร์การวิเคราะห์แบบฝังตัว เครื่องมือการวิเคราะห์แบบฝังตัว หรือเครื่องมือข่าวกรองธุรกิจอัจฉริยะแบบฝังตัว
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: overview
helpviewer_keywords:
- embedded analytics
- embedding
- Power BI embedding
- app owns data
- user owns data
- Power BI APIs
ms.custom: seodec18
ms.date: 05/15/2019
ms.openlocfilehash: a212691f2af877e3b86e021a4f48644f4fa6e8e3
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051066"
---
# <a name="embedded-analytics-with-power-bi"></a>การวิเคราะห์แบบฝังตัวด้วย Power BI

บริการ Power BI (SaaS) และบริการ Power BI Embedded ใน Azure (PaaS) มี API สำหรับการฝังสำหรับแดชบอร์ดและรายงาน เมื่อมีการฝังเนื้อหา นี้ให้คุณเข้าถึงคุณลักษณะ Power BI ล่าสุดเช่นแดชบอร์ด เกตเวย์ และพื้นที่ทำงานแอป

คุณสามารถเข้าถึง[เครื่องมือตั้งค่าการฝังตัว](https://aka.ms/embedsetup)เพื่อเริ่มต้นใช้งานได้อย่างรวดเร็ว และดาวน์โหลดแอปพลิเคชันตัวอย่างได้

เลือกโซลูชันที่เหมาะกับคุณ:

* [การฝังตัวสำหรับองค์กรของคุณ](embedding.md#embedding-for-your-organization) ให้คุณสามารถขยายบริการของ Power BI การทำเช่นนี้ ดำเนินการ[ฝังตัวสำหรับองค์กรของคุณ](https://aka.ms/embedsetup/UserOwnsData)โซลูชัน
* [การฝังสำหรับลูกค้าของคุณ](embedding.md#embedding-for-your-customers)ช่วยให้คุณสามารถฝังแดชบอร์ดและรายงานสำหรับผู้ใช้ที่ไม่มีบัญชี Power BI การทำเช่นนี้ ดำเนินการ[ฝังตัวสำหรับลูกค้าของคุณ](https://aka.ms/embedsetup/AppOwnsData)โซลูชัน

![ตัวอย่าง PBIE](media/what-can-you-do/what-can-you-do-02.png)

## <a name="use-apis"></a>ใช้ Api

มีสองสถานการณ์หลักสำหรับการฝังเนื้อหา Power BI:
- การฝังสำหรับผู้ใช้ขององค์กรของคุณ (ที่มีสิทธิ์การใช้งาน Power BI) 
 
- การฝังสำหรับผู้ใช้ของคุณและลูกค้าที่ไม่ต้องใช้สิทธิ์การใช้งาน Power BI 

การ[Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/)สำหรับทั้งสองสถานการณ์

สำหรับลูกค้าและผู้ใช้ที่มีใบอนุญาต Power BI คุณสามารถฝังแดชบอร์ดและรายงานลงในแอปพลิเคชันแบบกำหนดเองโดยใช้ API เดียวกันเพื่อให้บริการแก่องค์กรหรือลูกค้าของคุณ ลูกค้าของคุณดูข้อมูลจัดการโดยแอปพลิเคชัน ยัง ผู้ใช้ Power BI ขององค์กรของคุณมีตัวเลือกเพิ่มเติมให้ดู*ข้อมูลของพวกเขา*โดยตรง ใน Power BI หรือ ในบริบทของโปรแกรมประยุกต์ที่ฝังตัว คุณสามารถใช้ประโยชน์สูงสุดจาก JavaScript และ REST API สำหรับความต้องการในการฝังของคุณ

เมื่อต้องการทำความเข้าใจวิธีการทำงานของฝัง ดู[ตัวอย่างฝัง JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/)

## <a name="embedding-for-your-organization"></a>การฝังสำหรับองค์กรของคุณ

**การฝังตัวสำหรับองค์กรของคุณ** ให้คุณสามารถขยายบริการของ Power BI ฝังนี้จำเป็นต้องลงชื่อเข้าใช้ของผู้ใช้ของแอปพลิเคชันของคุณในบริการ Power BI เพื่อดูเนื้อหา เมื่อบุคคลใดบุคคลหนึ่งในองค์กรลงชื่อเข้าใช้ พวกเขาสามารถเข้าถึงแดชบอร์ดและรายงานที่พวกเขาเป็นเจ้าของ หรือที่แชร์กับบุคคลเหล่านั้นในบริการ Power BI เท่านั้น

ตัวอย่างการฝังองค์กรมีแอปพลิเคชันภายในเช่น[SharePoint Online](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/), [(คุณต้องมีสิทธิ์ผู้ดูแลระบบ) การรวมกับ Microsoft Teams](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/)และ[Microsoft Dynamics](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard).

เมื่อต้องฝังสำหรับองค์กรของคุณ ดู[บทช่วยสอน: ฝังเนื้อหา Power BI ลงในแอปพลิเคชันสำหรับองค์กรของคุณ](embed-sample-for-your-organization.md)

ความสามารถในการทำงานด้วยตนเอง เช่น แก้ไข บันทึก และอื่นๆ จะพร้อมใช้งานผ่าน [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript) เมื่อมีการฝังสำหรับผู้ใช้ Power BI

คุณสามารถไป[เครื่องมือตั้งค่า Embedding](https://aka.ms/embedsetup/UserOwnsData)สามารถเริ่มต้น และดาวน์โหลดแอปพลิเคชันตัวอย่างที่แนะนำคุณเกี่ยวกับการรวมรายงานสำหรับองค์กรของคุณ ได้

## <a name="embedding-for-your-customers"></a>การฝังสำหรับลูกค้าของคุณ

**การฝังสำหรับลูกค้าของคุณ**ช่วยให้คุณฝังแดชบอร์ดและรายงานสำหรับผู้ใช้ที่ไม่มีบัญชี Power BI ฝังนี้จะเรียกว่า*Power BI Embedded*

[Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md)จะเป็น**Microsoft Azure**บริการที่ช่วยให้นักพัฒนาและผู้จำหน่ายซอฟต์แวร์อิสระ (Isv) ได้อย่างรวดเร็ว ฝังภาพ รายงาน และแดชบอร์ดลงในแอปพลิเคชัน ฝังนี้สามารถทำผ่าน ตามความจุ ต่อชั่วโมงปริมาณข้อมูลต้นแบบ

![การฝังโฟลว์การฝังสำหรับลูกค้าของคุณ](media/embedding/powerbi-embed-flow.png)

Power BI Embedded มีประโยชน์สำหรับ ISV นักพัฒนาซอฟต์แวร์ และลูกค้า ตัวอย่างเช่น ISV สามารถเริ่มต้นสร้างภาพฟรีด้วย Power BI Desktop โดยการลดความพยายามพัฒนาการวิเคราะห์ภาพ Isv บรรลุเวลาที่รวดเร็วการตลาด และโดดเด่นคู่แข่งกับประสบการณ์การใช้งานข้อมูลประเภทอื่น Isv ยังสามารถเลือกค่าธรรมเนียมพิเศษสำหรับค่าเพิ่มเติมที่พวกเขาสร้างกับวิเคราะห์แบบฝังตัว

ด้วย Power BI Embedded ลูกค้าของคุณไม่จำเป็นต้องทราบอะไรเลยเกี่ยวกับ Power BI คุณสามารถใช้สองวิธีการสร้างแอปพลิเคชันแบบฝังตัว:
- Power BI Pro บัญชี 
- โครงร่างสำคัญของบริการ 

บัญชี Power BI Pro ทำหน้าที่เป็นบัญชีหลักของแอปพลิเคชันของคุณ (ให้คิดว่าเป็นบัญชีพร็อกซี) บัญชีนี้ช่วยให้คุณสามารถสร้างโทเค็นที่มีการเข้าถึงแอปพลิเคชันของแดชบอร์ด Power BI และรายงาน แบบฝัง

[บริการหลัก](embed-service-principal.md)สามารถฝังเนื้อหา Power BI ลงในแอปพลิเคชันโดยใช้โทเค็น**เฉพาะแอป**เท่านั้น ซึ่งยังอนุญาตให้คุณสามารถสร้างโทเค็นที่มีการเข้าถึงแอปพลิเคชันของแดชบอร์ด Power BI และรายงาน แบบฝัง

ใช้ Power BI Embedded นักพัฒนาสามารถใช้เวลาที่มุ่งสร้างของแอปพลิเคชันของพวกเขาฟังก์ชันหลักแทนที่ใช้เวลาพัฒนาภาพ และวิเคราะห์ พวกเขาสามารถตอบสนองความต้องการรายงานและแดชบอร์ดลูกค้า และฝังได้อย่างง่ายดาย ด้วย Api เป็นเอกสารทั้งหมดและและ Sdk อย่างรวดเร็ว การเปิดใช้งานการสำรวจข้อมูลที่ค้นหาได้ง่ายในแอปทำให้ ISV ช่วยให้ลูกค้าทำการตัดสินใจได้อย่างรวดเร็วเนื่องจากมีข้อมูลจากอุปกรณ์

> [!IMPORTANT]
> ในขณะที่ฝังจำเป็นต้องใช้บริการของ Power BI ลูกค้าของคุณไม่จำเป็นต้องมีบัญชี Power BI เพื่อดูเนื้อหาแบบฝังตัวของแอปพลิเคชันของคุณ 

เมื่อคุณพร้อมที่จะย้ายไปยังการผลิต ต้องกำหนดความจุเฉพาะให้กับพื้นที่ทำงานของแอป Power BI Embedded ใน Microsoft Azure มี [ความจุเฉพาะ](azure-pbie-create-capacity.md)ให้ใช้กับแอปพลิเคชันของคุณ

สำหรับรายละเอียดการฝัง ดู[วิธีการฝังเนื้อหา Power BI](embed-sample-for-customers.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป

ตอนนี้คุณสามารถลองฝังเนื้อหา Power BI ไปยังแอปพลิเคชัน หรือลองฝังเนื้อหา Power BI สำหรับลูกค้าของคุณ

> [!div class="nextstepaction"]
> [ฝังตัวสำหรับองค์กรของคุณ](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Power BI Embedded คืออะไร](azure-pbie-what-is-power-bi-embedded.md)

> [!div class="nextstepaction"]
>[ฝังสำหรับลูกค้าของคุณ](embed-sample-for-customers.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](http://community.powerbi.com/)

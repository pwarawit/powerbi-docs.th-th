---
title: พัฒนาเซิร์ฟเวอร์รายงาน Power BI ด้วย REST APIs
description: REST API ให้เข้าโปรแกรมวัตถุในแค็ตตาล็อกของเซิร์ฟเวอร์รายงาน Power BI
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 05/25/2018
ms.openlocfilehash: 8f35b7a3c19751b4537a49fa8cb30f4347f080ed
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770764"
---
# <a name="develop-with-the-rest-apis-for-power-bi-report-server"></a>พัฒนาเซิร์ฟเวอร์รายงาน Power BI ด้วย REST APIs

เซิร์ฟเวอร์รายงาน Power BI สนับสนุน Representational State Transfer (REST) APIs REST API เป็นจุดบริการที่สนับสนุนการดำเนินงาน HTTP (วิธีการ) ซึ่งให้ สร้าง บริการ เรียก อัปเดต หรือลบทรัพยากรภายในเซิร์ฟเวอร์รายงาน

REST API ให้เข้าโปรแกรมวัตถุในแค็ตตาล็อกของเซิร์ฟเวอร์รายงาน Power BI ตัวอย่างของวัตถุคือ แฟ้ม รายงาน KPIs แหล่งข้อมูล ชุดข้อมูล แผนการรีเฟรช การสมัครใช้งาน และอื่น ๆ เมื่อใช้ REST API คุณสามารถลำดับชั้นของแฟ้ม ค้นหาเนื้อหาของแฟ้ม หรือดาวน์โหลดคำนิยามรายงาน และอื่นๆ คุณสามารถสร้าง อัปเดต และลบวัตถุต่างๆ ได้อีกด้วย ตัวอย่างของการทำงานกับวัตถุคือการอัปโหลดรายงาน ดำเนินงานแผนการรีเฟรช ลบแฟ้มและอื่นๆ

[!INCLUDE [GDPR-related guidance](../includes/gdpr-hybrid-note.md)]

## <a name="components-of-a-rest-api-requestresponse"></a>ส่วนประกอบของคำขอ/คำตอบ REST API

สามารถแยกคู่คำขอ/คำตอบ REST API เป็นส่วนประกอบได้ 5 ส่วน:

* **คำขอ URI**ซึ่งประกอบด้วย: `{URI-scheme} :// {URI-host} / {resource-path} ? {query-string}` แม้ว่าคำขอ URI จะอยู่ในส่วนหัวของข้อความคำขอ เรานำส่วนนี้แยกออกต่างหากที่นี่เนื่องจากภาษาหรือเฟรมเวิร์กส่วนใหญให้คุณส่งส่วนนี้แยกต่างหากจากข้อความคำขอ
  
  * แบบแผน URI: ระบุโพรโทคอลที่ใช้ในการส่งคำขอ ตัวอย่างเช่น`http`หรือ`https`
  * โฮสต์ URI: ระบุชื่อโดเมนหรือที่อยู่ IP ของเซิร์ฟเวอร์ที่โฮสต์จุดปลายทางบริการ REST เช่น`myserver.contoso.com`
  * เส้นทางของทรัพยากร: ระบุทรัพยากรหรือคอลเลกชันทรัพยากร ซึ่งอาจรวมถึงเซกเมนต์หลายรายการที่บริการใช้ ในการกำหนดการเลือกทรัพยากรเหล่านั้น ตัวอย่างเช่น:`CatalogItems(01234567-89ab-cdef-0123-456789abcdef)/Properties`สามารถใช้เพื่อให้ได้คุณสมบัติที่ระบุไว้สำหรับ CatalogItem
  * Query string (ตัวเลือก): ให้พารามิเตอร์เพิ่มเติมอย่างง่าย เช่น เกณฑ์การเลือกเวอร์ชันหรือทรัพยากรของ API
* เขตข้อมูลส่วนหัวของข้อความคำขอ HTTP :
  
  * [เมธอด HTTP](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html) ที่ต้องใส่ (หรือที่เรียกว่าการดำเนินการ หรือ คำสั่งการกระทำ) ซึ่งบอกบริการว่าคุณกำลังขอการดำเนินการประเภทใด บริการรายงานของ REST API สนับสนุนเมธอดต่อไปนี้: DELETE, GET, HEAD, PUT, POST และ PATCH
  * เขตข้อมูลส่วนหัวที่เป็นตัวเลือก ตามที่ URI และเมธอด HTTP ต้องการ
* HTTP เพิ่มเติม**ร้องขอเขตข้อมูลตัวเนื้อความ**เพื่อสนับสนุน URI และการดำเนินการ HTTP ตัวอย่างเช่น การดำเนินการ POST ประกอบด้วยวัตถุที่เข้ารหัส MIME ที่ส่งผ่านเป็นพารามิเตอร์ที่ซับซ้อน สำหรับ POST หรือการดำเนินการ PUT คุณควรระบุชนิดการเข้ารหัสแบบ MIME สำหรับตัวเนื้อความใน`Content-type`ส่วนหัวของคำขอด้วย บริการบางอย่างกำหนดให้คุณใช้ MIME บางชนิด เช่น`application/json`
* เขตข้อมูล**ส่วนหัวของข้อความคำตอบ** HTTP:
  
  * [รหัสสถานะ HTTP](http://www.w3.org/Protocols/HTTP/HTRESP.html) ตั้งแต่รหัสความสำเร็จ 2xx จนถึงรหัสข้อผิดพลาด 4xx หรือ 5xx อีกวิธีหนึ่งคือ อาจส่งกลับรหัสสถานะที่บริการกำหนด ตามที่ระบุในเอกสาร API
  * เขตข้อมูลส่วนหัวที่เป็นตัวเลือก ตามที่ต้องใส่เพื่อสนับสนุนคำตอบสนองคำขอ เช่น`Content-type`ส่วนหัวของคำตอบ
* เขตข้อมูล**เนื้อหาของข้อความคำตอบ** HTTP เพิ่มเติม:
  
  * วัตถุตอบสนองที่เข้ารหัส MIME จะถูกส่งกลับในตัวเนื้อหาคำตอบ HTTP เช่น คำตอบจาก GET เมธอดที่กำลังส่งข้อมูลกลับ โดยทั่วไปแล้ว วัตถุเหล่านี้จะถูกส่งกลับในรูปแบบที่มีโครงสร้าง เช่น JSON หรือ XML ตามที่ระบุโดย`Content-type`ส่วนหัวของคำตอบ

## <a name="api-documentation"></a>เอกสาร API

เรียกใช้ REST API ที่ทันสมัยสำหรับเอกสาร API ที่ทันสมัย REST API ถูกสร้างบนข้อมูลจำเพาะของ OpenAPI (ซึ่งคือ ข้อมูลจำเพาะ swagger) และเอกสารมีพร้อมใช้งานบน[SwaggerHub](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0) นอกเหนือจากการสร้างเอกสาร API SwaggerHub ช่วยสร้างไลบรารีไคลเอ็นต์ในหลายภาษา – JavaScript, TypeScript, C#, Java, Python, Ruby และอื่น ๆ

## <a name="testing-api-calls"></a>การทดสอบการเรียกใช้ API

เครื่องมือสำหรับการทดสอบข้อความคำขอ/การตอบสนอง HTTP คือ[Fiddler](http://www.telerik.com/fiddler) Fiddler คือ พร็อกซี่ที่ดีบักเว็บฟรีที่สามารถดักคำขอของ REST ซึ่งทำให้วิเคราะห์ข้อความคำขอ/ คำตอบ HTTP ง่ายขึ้น

## <a name="next-steps"></a>ขั้นตอนถัดไป

ตรวจทาน API ที่พร้อมใช้งานบน [SwaggerHub](https://app.swaggerhub.com/apis/microsoft-rs/PBIRS/2.0)

มีตัวอย่างบน[GitHub](https://github.com/Microsoft/Reporting-Services) ตัวอย่างรวมถึงแอป HTML5 ที่สร้างบน TypeScript, React และ webpack พร้อมกับตัวอย่าง PowerShell

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
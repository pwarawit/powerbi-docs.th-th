---
title: นักพัฒนา Power BI ในหลักสูตรหนึ่งวัน
description: หลักสูตรที่ใช้วิดีโอนี้จะช่วยให้คุณเป็นนักพัฒนาแอปที่มีความรู้ทางเทคนิคที่จำเป็นสำหรับการฝังเนื้อหา Power BI
author: peter-myers
ms.reviewer: yana.berkovich
featuredvideoid: dv-ep90wse8
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: tutorial
ms.date: 06/01/2020
ms.author: v-pemyer
ms.openlocfilehash: 82f9ffaeb98610dd9ae5986031638c5086749937
ms.sourcegitcommit: 7fba2caf3bd7ed93a7ecb6a6b9ba2da26de27395
ms.contentlocale: th-TH
ms.lasthandoff: 06/06/2020
ms.locfileid: "84467044"
---
# <a name="power-bi-developer-in-a-day-course"></a>นักพัฒนา Power BI ในหลักสูตรหนึ่งวัน

หลักสูตรวิดีโอ**นักพัฒนา Power BI ในหนึ่งวัน** ช่วยให้คุณเป็นนักพัฒนาแอปที่มีความรู้ทางเทคนิคที่จำเป็นในการฝังเนื้อหา Power BI ซึ่งประกอบด้วยเนื้อหาที่สามารถดูได้3 ชั่วโมง 20 นาที - พร้อมให้บริการตามความต้องการและไม่มีค่าใช้จ่าย นอกจากนี้ยังมี[ชุดการเรียนรู้ด้วยตนเอง](#self-study-kit)ที่คุณสามารถดาวน์โหลดและใช้เพื่อดำเนินการชุดของแล็บทั้งห้าแบบให้เสร็จสมบูรณ์ได้

หลักสูตรได้รับการออกแบบมาโดยเฉพาะสำหรับนักพัฒนาแอปที่มีประสบการณ์ ดังนั้น จึงเป็นประโยชน์ถ้าคุณมีประสบการณ์ในการพัฒนา:

- ASP.NET
- Visual C#
- HTML
- JavaScript

ความคุ้นเคยกับ Power BI จะเป็นประโยชน์ แต่ไม่ใช่สิ่งที่จำเป็น เราจะแนะนำแนวคิดหลักให้กับคุณ

เมื่อคุณจบหลักสูตรนี้แล้ว คุณจะทราบวิธี:

> [!div class="checklist"]
> - รับการเข้าถึงโดยใช้แอป Azure AD และโทเค็น
> - ทำงานกับ Power BI REST API
> - ฝังเนื้อหา Power BI ในแอปของคุณ
> - รวมเนื้อหา Power BI ในแอปของคุณโดยใช้ Power BI JavaScript API
> - บังคับใช้การรักษาความปลอดภัยระดับแถว (RLS) เพื่อให้แน่ใจว่าผู้ใช้แอปจะเห็นข้อมูลที่ถูกต้อง
> - เลือกสิทธิ์การใช้งานที่เหมาะสมเพื่อให้ตรงกับความต้องการของคุณ

ชมวิดีโอต้อนรับและวิดีโอแนะนำเพื่อเริ่มหลักสูตร

> [!VIDEO https://www.youtube.com/embed/dv-ep90wse8]

## <a name="course-outline"></a>โครงร่างหลักสูตร

[หลักสูตร 20 วิดีโอ](https://www.youtube.com/playlist?list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)ถูกจัดระเบียบเป็นเจ็ดโมดูล เราแนะนำให้คุณดูวิดีโอตามลำดับที่บันทึก เริ่มต้นด้วยวิดีโอ 01 และจบด้วยวิดีโอ 20

- **บทนำ**
  - วิดีโอ 01: [ยินดีต้อนรับและการแนะนำหลักสูตร](https://www.youtube.com/watch?v=dv-ep90wse8&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
  - วิดีโอ 02: [ชุดการเรียนรู้ด้วยตนเอง](https://www.youtube.com/watch?v=X0P9Mdqx7sY&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
- **โมดูล 01: ภาพรวม Power BI**
  - วิดีโอ 03: [ภาพรวม Power BI - ส่วนที่1](https://www.youtube.com/watch?v=LD3RlDdRi-0&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
  - วิดีโอ 04: [ภาพรวม Power BI - ส่วนที่2](https://www.youtube.com/watch?v=jmHXlHI5hn0&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
  - วิดีโอ 05: [ภาพรวม Power BI - ส่วนที่3](https://www.youtube.com/watch?v=uujSR_7cfL4&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
- **โมดูล 02: การวิเคราะห์ Power BI แบบฝังตัว**
  - วิดีโอ 06: [การวิเคราะห์ Power BI แบบฝังตัว  -ส่วนที่ 1](https://www.youtube.com/watch?v=2QBnfUwnuMk&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
  - วิดีโอ 07: [การวิเคราะห์ Power BI แบบฝังตัว - ส่วนที่ 2](https://www.youtube.com/watch?v=7Jda5x7Qe7Q&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
- **โมดูล 03: กำลังรับการเข้าถึง**
  - วิดีโอ 08: [กำลังรับการเข้าถึง](https://www.youtube.com/watch?v=3dYCMTsDT3c&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
- **โมดูล 04: การฝังเนื้อหา Power BI**
  - วิดีโอ 09: [การฝังเนื้อหา Power BI - ส่วนที่ 1](https://www.youtube.com/watch?v=caKS8PQJnyo&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
  - วิดีโอ 10: [การฝังเนื้อหา Power BI - ส่วนที่2](https://www.youtube.com/watch?v=XbYt8ZX3q9k&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
  - วิดีโอ 11: [การฝังเนื้อหา Power BI - ส่วนที่ 3](https://www.youtube.com/watch?v=mXmFrHuYVh8&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
  - วิดีโอ 12: [การฝังเนื้อหา Power BI - ส่วนที่ 4](https://www.youtube.com/watch?v=9YNm90K8FhA&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
  - วิดีโอ 13: [การฝังเนื้อหา Power BI - ส่วนที่ 5](https://www.youtube.com/watch?v=hnZ7IWHrMFU&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
- **โมดูล 05: รวมเนื้อหาด้วย Power BI JavaScript API**
  - วิดีโอ 14: [การรวมเนื้อหาด้วย Power BI JavaScript API - ส่วนที่ 1](https://www.youtube.com/watch?v=wmeEEHQmQqw&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
  - วิดีโอ 15: [การรวมเนื้อหาด้วย Power BI JavaScript API - ส่วนที่ 2](https://www.youtube.com/watch?v=TSEjZl0dGfM&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
- **โมดูล 06: การบังคับใช้การรักษาความปลอดภัยระดับแถว**
  - วิดีโอ 16: [การบังคับใช้การรักษาความปลอดภัยระดับแถว - ส่วนที่ 1](https://www.youtube.com/watch?v=8O4hzGI8FFg&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
  - วิดีโอ 17: [การบังคับใช้การรักษาความปลอดภัยระดับแถว - ส่วนที่ 2](https://www.youtube.com/watch?v=8mxg8LtLx4I&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
  - วิดีโอ 18: [การบังคับใช้การรักษาความปลอดภัยระดับแถว - ส่วนที่ 3](https://www.youtube.com/watch?v=OdgtbIIM9pk&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
- **โมดูล 07: สิทธิ์การใช้งานการฝัง Power BI**
  - วิดีโอ 19: [สิทธิ์การใช้งานการฝัง Power BI](https://www.youtube.com/watch?v=ipmip6ARnks&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)
- **เนื้อหาโบนัส**
  - วิดีโอ 20: [เครื่องมือ Playground สำหรับ Power BI แบบฝังตัว](https://www.youtube.com/watch?v=U3qeQRwWhRc&list=PL1N57mwBHtN1AGWHnJMhtvJCIG_IlC07D)

## <a name="self-study-kit"></a>ชุดการเรียนรู้ด้วยตนเอง

คุณสามารถดาวน์โหลดและตั้งค่าชุดการเรียนรู้ด้วยตนเองได้  ซึ่งประกอบด้วยเนื้อหาการนำเสนอและแล็บปฏิบัติการสาธิตทั้งห้าดังนี้: สำหรับข้อมูลเพิ่มเติม ให้ดูวิดีโอ[ชุดการเรียนรู้ด้วยตนเอง](https://www.youtube.com/watch?v=X0P9Mdqx7sY)

เพื่อดำเนินการแล็บให้เสร็จสมบูรณ์ คุณจะต้องใช้ Windows PC (Windows 7 หรือใหม่กว่า) และติดตั้งซอฟต์แวร์ต่อไปนี้:

- [Power BI Desktop](../fundamentals/desktop-get-the-desktop.md) เวอร์ชันล่าสุด
- Visual Studio 2015 หรือใหม่กว่า เราขอแนะนำให้ใช้ [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/) คุณสามารถใช้รุ่น**ชุมชน**ได้ ซึ่งเป็นแบบฟรีและเหมาะสำหรับสถานการณ์การเรียนรู้ ต้องมีการติดตั้งปริมาณงาน **ASP.NET และการพัฒนาเว็บ**
- เว็บเบราว์เซอร์[ได้รับการสนับสนุนโดย Power BI](../power-bi-browsers.md) เราขอแนะนำ Microsoft Edge

ทำตามขั้นตอนเหล่านี้เพื่อติดตั้ง:

1. ใช้ [ลิงก์นี้](https://aka.ms/deviad-student) เพื่อดาวน์โหลดชุดการเรียนรู้ด้วยตนเอง (.zip) ลงในเครื่องพีซีของคุณ
1. เปิดคุณสมบัติไฟล์ และทำครื่องหมายที่ “ยกเลิกการบล็อก” (Windows อาจตั้งค่าสถานะไฟล์เป็นอาจไม่น่าเชื่อถือ)
1. แยกเนื้อหาไฟล์ไปยังโฟลเดอร์ในระบบไฟล์ของคุณ เราขอแนะนำให้คุณสร้างโฟลเดอร์ที่จะค้นหาได้ง่าย โดยอาจตั้งชื่อเป็น **การฝึกอบรม** เอกสารประกอบแล็บจะอ้างอิงไปยังตำแหน่งที่ตั้งนี้เป็น **&lt;CourseFolder&gt;**

หลังจากแยกเนื้อหาแล้ว คุณจะมีโฟลเดอร์ **PowerBIPRIAD** และคุณจะพบโฟลเดอร์ต่อไปนี้ภายในโฟลเดอร์ดังกล่าวด้วย:

- **Lab01A** (และโฟลเดอร์แล็บอื่นๆ ทั้งหมด) โฟลเดอร์แล็บประกอบด้วยเอกสารประกอบแล็บ และแหล่งข้อมูลแล็บ ซึ่งอาจหมายรวมถึงไฟล์โซลูชันและแอสเซทต่างๆ
- **MySolution**: โฟลเดอร์นี้จัดเก็บไฟล์โซลูชันของคุณ คำแนะนำในแล็บจะตรงกับคุณเมื่อใช้งาน
- **Presentation**: โฟลเดอร์นี้ประกอบด้วยไฟล์การนำเสนอหลักสูตร ซึ่งพร้อมใช้งานในรูปแบบเอกสาร PDF

### <a name="get-started-with-the-kit"></a>เริ่มต้นใช้งานชุดข้อมูล

เราขอแนะนำให้คุณรับชมหลักสูตรออนไลน์ก่อน คุณสามารถอ้างอิงกลับไปยังทฤษฎีการนำเสนอโดยการเปิดไฟล์ **&lt;CourseFolder&gt;\PowerBIDevIAD\Presentation\PowerBIDevIAD_Presentation.pdf** ได้ ไฟล์การนำเสนอประกอบด้วยสไลด์แล็บห้าแล็บ ซึ่งระบุเวลาในการนำทฤษฎีสู่การปฏิบัติ นอกจากนี้ ยังหมายรวมถึงลิงก์แหล่งข้อมูลจำนวนมาก ที่จะช่วยให้คุณสามารถค้นหาเนื้อหาที่เกี่ยวข้องได้

เมื่อคุณพร้อมที่จะเริ่มต้นแล็บแห่งแรก ให้เปิดไฟล์ **&lt;CourseFolder&gt;\PowerBIDevIAD\Lab01A\PowerBIDevIAD_Lab01A.pdf** เอกสารนี้จะแนะนำคุณในการลงชื่อเข้าใช้บริการของ Power BI และเตรียมรายงาน Power BI

> [!NOTE]
> คุณมีหน้าที่รับผิดชอบในการมีบัญชี Power BI ของตนเอง หากคุณไม่ได้มีบัญชีอยู่แล้ว ดูที่ [ลงทะเบียน Power BI เป็นรายบุคคล](../service-self-service-signup-for-power-bi.md)
>
> บัญชีของคุณจะต้องมีสิทธิ์การใช้งาน Power BI Pro หรือคุณยังคงสามารถยอมรับสิทธิ์การใช้งานรุ่นทดลอง Power BI Pro ได้ — ข้อเสนอที่สามารถยอมรับได้เพียงครั้งเดียวเท่านั้น นอกจากนี้บัญชีของคุณต้องไม่มีการสำรองโทเค็นแบบฝังฟรีที่พร้อมใช้งานกับใบอนุญาต Power BI Pro
>
> นอกจากนี้ คุณต้องยินยอมให้มีการจัดเก็บรหัสผ่านของคุณไว้ใข้อความเปล่าในโซลูชันแล็บ การจัดเก็บข้อมูลที่สำคัญไม่ใช่แนวทางปฏิบัติที่แนะนำ - ซึ่งทำได้เพื่อลดความซับซ้อนของแล็บ หากคุณต้องการเข้ารหัสรหัสผ่านของคุณ คุณจะต้องใช้ตรรกะด้วยตัวคุณเอง
>
> พิจารณาการสร้างบัญชี Power BI สำหรับการใช้งานแบบเอกสิทธิ์เฉพาะการใช้งานในแล็บ คุณสามารถสร้างบัญชีผู้ใช้ฟรีด้วยโดเมนสาธารณะเช่น [https://outlook.live.com](https://outlook.live.com)และจากนั้นใช้เพื่อลงชื่อเข้าใช้ Power BI และยอมรับสิทธิ์การใช้งานรุ่นทดลอง Power BI Pro

## <a name="instructor-kit"></a>ชุดผู้สอน

ใช้ [ลิงก์นี้](https://aka.ms/deviad-instructor) เพื่อดาวน์โหลดชุดผู้สอน (.zip) ลงในเครื่องพีซีของคุณ คุณจะพบบันทึกย่อการตั้งค่าในชั้นเรียนในสไลด์ที่หนึ่งในสำรับสไลด์ของ PowerPoint

## <a name="next-steps"></a>ขั้นตอนถัดไป

สำหรับข้อมูลเพิ่มเติมที่เกี่ยวข้องกับบทความนี้ โปรดดูทรัพยากรต่อไปนี้:

- มีคำถามหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
- มีข้อเสนอแนะไหม [สนับสนุนแนวคิดในการปรับปรุง Power BI](https://ideas.powerbi.com/)

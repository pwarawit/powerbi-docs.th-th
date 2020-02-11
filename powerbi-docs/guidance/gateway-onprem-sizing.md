---
title: ขนาดเกตเวย์ข้อมูลภายในองค์กร
description: คำแนะนำสำหรับการทำงานในการปรับขนาดเกตเวย์ข้อมูลภายในองค์กร
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/30/2019
ms.author: v-pemyer
ms.openlocfilehash: 4f289bf319bf29de8f8765d55bf3400048420af5
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/29/2020
ms.locfileid: "76829063"
---
# <a name="on-premises-data-gateway-sizing"></a>ขนาดเกตเวย์ข้อมูลภายในองค์กร

บทความนี้มุ่งเป้าที่ผู้ดูแลระบบ Power BI ที่จำเป็นต้องติดตั้งและจัดการ [เกตเวย์ข้อมูลภายในองค์กร](../service-gateway-onprem.md)

จำเป็นต้องใช้เกตเวย์เมื่อ Power BI ต้องเข้าถึงข้อมูลที่ไม่สามารถใช้งานได้โดยตรงผ่านทางอินเทอร์เน็ต สามารถติดตั้งได้บนเซิร์ฟเวอร์ภายในองค์กรหรือ VM-hosted Infrastructure-as-a-Service (IaaS)

## <a name="gateway-workloads"></a>ปริมาณงานเกตเวย์

เกตเวย์ข้อมูลภายในองค์กรรองรับได้สองปริมาณงาน เป็นสิ่งสำคัญที่คุณต้องทำความเข้าใจปริมาณงานเหล่านี้ก่อนที่เราจะพูดคุยเกี่ยวกับการปรับขนาดเกตเวย์และคำแนะนำ

### <a name="cached-data-workload"></a>ปริมาณงานข้อมูลที่แคช

ปริมาณงาน _ข้อมูลที่แคชไว้_ ดึงและแปลงแหล่งข้อมูลต้นฉบับสำหรับการโหลดลงในชุดข้อมูล Power BI สามารถทำได้ในสามขั้นตอน:

1. **การเชื่อมต่อ**: เกตเวย์เชื่อมต่อกับข้อมูลต้นทาง
1. **การเรียกและการแปลงข้อมูล**: ข้อมูลจะถูกเรียกใช้ และเมื่อจำเป็น จะถูกแปลง เมื่อใดก็ตามที่เป็นไปได้ Power Query mashup engine จะส่งขั้นตอนการแปลงไปยังแหล่งข้อมูล - ซึ่งเรียกว่า _[การพับคิวรี](power-query-folding.md)_ เมื่อไม่สามารถทำได้ การแปลงจะต้องทำโดยเกตเวย์ ในกรณีนี้ เกตเวย์จะใช้ทรัพยากร CPU และหน่วยความจำมากขึ้น
1. **ถ่ายโอน**: ข้อมูลถูกถ่ายโอนไปยังบริการของ Power BI —การเชื่อมต่ออินเทอร์เน็ตที่เชื่อถือได้และรวดเร็วเป็นสิ่งสำคัญโดยเฉพาะอย่างยิ่งสำหรับจำนวนข้อมูลขนาดใหญ่

![แผนผังจะแสดงเกตเวย์ข้อมูลภายในองค์กรที่เชื่อมต่อกับแหล่งที่มาภายในองค์กร: ฐานข้อมูลเชิงสัมพันธ์ สมุดงาน Excel และไฟล์ CSV เกตเวย์ดึงและแปลงข้อมูล](media/gateway-onprem-sizing/gateway-onprem-workload-cached-data.png)

### <a name="live-connection-and-directquery-workloads"></a>ปริมาณงานการเชื่อมต่อสดและ DirectQuery

ปริมาณงาน _การเชื่อมต่อสดและ DirectQuery_ ส่วนใหญ่จะทำงานในโหมดพาส-ทรู บริการของ Power BI ส่งคิวรีและตอบสนองของเกตเวย์ด้วยผลลัพธ์คิวรี โดยทั่วไป ผลลัพธ์คิวรีมีขนาดเล็ก

- สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการเชื่อมต่อสด ดู [ชุดข้อมูลในบริการของ Power BI (แบบจำลองข้อมูลที่โฮสต์ภายนอก)](../service-datasets-understand.md#external-hosted-models)
- สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ DirectQuery ดู [โหมดชุดข้อมูลในบริการของ Power BI (โหมด DirectQuery)](../service-dataset-modes-understand.md#directquery-mode)

ปริมาณงานนี้จำเป็นต้องมีทรัพยากรของ CPU สำหรับคิวรีของเส้นทางและผลลัพธ์คิวรี โดยปกติแล้วจะมีความต้องการ CPU น้อยกว่าปริมาณการแคชข้อมูลที่จำเป็น โดยเฉพาะอย่างยิ่งเมื่อจำเป็นต้องแปลงข้อมูลสำหรับการแคช

การเชื่อมต่อที่เชื่อถือได้ รวดเร็ว และสม่ำเสมอ เป็นสิ่งสำคัญที่ต้องตรวจสอบให้แน่ใจว่าผู้ใช้รายงานมีประสบการณ์ตอบสนองในลักษณะนี้

![แผนผังจะแสดงเกตเวย์ข้อมูลภายในองค์กรที่เชื่อมต่อกับแหล่งที่มาภายในองค์กร:  ฐานข้อมูลแบบตารางและแบบความสัมพันธ์ใน Analysis Services เกตเวย์ทำงานส่วนใหญ่ในโหมดพาส-ทรู](media/gateway-onprem-sizing/gateway-onprem-workload-liveconnection-directquery.png)

## <a name="sizing-considerations"></a>ข้อควรพิจารณาเกี่ยวกับการปรับขนาด

การกำหนดขนาดที่ถูกต้องสำหรับเครื่องเกตเวย์ของคุณอาจขึ้นอยู่กับตัวแปรดังต่อไปนี้:

- สำหรับปริมาณงานของข้อมูลแคช:
  - จำนวนการรีเฟรชชุดข้อมูลพร้อมกัน
  - ชนิดของแหล่งข้อมูล (ฐานข้อมูลเชิงสัมพันธ์ ฐานข้อมูลการวิเคราะห์ ฟีดข้อมูล หรือไฟล์)
  - ปริมาณข้อมูลที่จะเรียกใช้จากแหล่งข้อมูล
  - การแปลงใดๆ ที่จำเป็นต้องทำโดย Power Query mashup engine
  - ปริมาณของข้อมูลที่จะถ่ายโอนไปยังบริการของ Power BI
- สำหรับปริมาณงานการเชื่อมต่อสดและ DirectQuery:
  - จำนวนผู้ใช้รายงานที่เกิดขึ้นพร้อมกัน
  - จำนวนการแสดงผลด้วยภาพบนหน้ารายงาน (แต่ละวิชวลจะส่งอย่างน้อยหนึ่งคิวรี)
  - ความถี่ของการอัปเดตแคชคิวรีของแดชบอร์ด Power BI
  - จำนวนรายงานแบบเรียลไทม์ใช้คุณลักษณะ[การรีเฟรชหน้าโดยอัตโนมัติ](../desktop-automatic-page-refresh.md)
  - ไม่ว่าชุดข้อมูลจะบังคับใช้ [การรักษาความปลอดภัยระดับแถว (RLS)](../desktop-rls.md) หรือไม่

โดยทั่วไป แล้วปริมาณงานการเชื่อมต่อสดและ DirectQuery จำเป็นต้องมี CPU เพียงพอ ในขณะที่ปริมาณงานแคชข้อมูลจำเป็นต้องใช้ CPU และหน่วยความจำมากขึ้น ปริมาณงานทั้งสองขึ้นอยู่กับการเชื่อมต่อที่ดีกับบริการของ Power BI และแหล่งข้อมูล

> [!NOTE]
> ความจุ Power BI กำหนดขีดจำกัดในการรีเฟรชแบบจำลองแบบขนาน และอัตราความเร็วการเชื่อมต่อสดและ DirectQuery การปรับขนาดของเกตเวย์ของคุณเพื่อส่งข้อมูลมากกว่าที่บริการของ Power BI สนับสนุนไม่ได้ส่งผลใดๆ เกิดขึ้น ขีดจำกัดมีความแตกต่างตาม Premium SKU (และ SKU ที่มีขนาดเท่ากัน) สำหรับข้อมูลเพิ่มเติม ให้ดู [Power BI Premium คืออะไร (โหนดความจุ)](../service-premium-what-is.md#capacity-nodes)

## <a name="recommendations"></a>คำแนะนำ

คำแนะนำในการปรับขนาดเกตเวย์ขึ้นอยู่กับตัวแปรจำนวนมาก ในส่วนนี้ เราจะให้คำแนะนำทั่วไปที่คุณสามารถนำไปพิจารณาดูได้

### <a name="initial-sizing"></a>การปรับขนาดเริ่มต้น

อาจเป็นเรื่องยากที่จะประเมินขนาดที่ถูกต้องได้อย่างแม่นยำ เราขอแนะนำให้คุณเริ่มต้นด้วยเครื่องที่มีแกน CPU อย่างน้อย 8 คอร์ RAM 8 GB และอะแดปเตอร์เครือข่ายหลายจิกะบิต จากนั้นคุณสามารถวัดปริมาณงานเกตเวย์ทั่วไปได้โดยการบันทึกตัวนับของ CPU และหน่วยความจำระบบ สำหรับข้อมูลเพิ่มเติม ดูที่ [การตรวจสอบและปรับประสิทธิภาพการทำงานของเกตเวย์ข้อมูลภายในองค์กรให้เหมาะสม](/data-integration/gateway/service-gateway-performance)

### <a name="connectivity"></a>การเชื่อมต่อ

วางแผนสำหรับการเชื่อมต่อที่ดีที่สุดที่เป็นไปได้ระหว่างบริการของ Power BI กับเกตเวย์ของคุณ และเกตเวย์ของคุณกับแหล่งข้อมูล

- มุ่งมั่นเพื่อความน่าเชื่อถือ ความรวดเร็ว และเวลาในการตอบสนองที่ต่ำและสม่ำเสมอ
- กำจัด - หรือลด - การกระโดดของเครื่องระหว่างเกตเวย์และแหล่งข้อมูลของคุณ
- ลบการควบคุมเครือข่ายใดๆ ที่กำหนดโดยเลเยอร์พร็อกซีไฟร์วอลล์ของคุณ สำหรับข้อมูลเพิ่มเติมเกี่ยวกับจุดสิ้นสุด Power BI ดู [URL Power BI สำหรับการอนุญาตพิเศษ](../power-bi-whitelist-urls.md)
- กำหนดค่า [Azure ExpressRoute](/azure/expressroute/expressroute-introduction) เพื่อสร้างการเชื่อมต่อส่วนตัวที่มีการจัดการไปยัง Power BI
- สำหรับแหล่งข้อมูลใน Azure VMs ตรวจสอบให้แน่ใจว่า VMs [colocate กับบริการของ Power BI](../service-admin-where-is-my-tenant-located.md)
- สำหรับปริมาณงานการเชื่อมต่อสดไปยัง SQL Server Analysis Services (SSAS) ที่เกี่ยวข้องกับ RLS แบบไดนามิก ตรวจสอบให้แน่ใจว่ามีการเชื่อมต่อที่ดีระหว่างเครื่องเกตเวย์และ Active Directory ภายในองค์กร

### <a name="clustering"></a>การทำคลัสเตอร์

สำหรับการปรับใช้งานขนาดใหญ่ คุณสามารถสร้างเกตเวย์ของการติดตั้งคลัสเตอร์ได้ คลัสเตอร์หลีกเลี่ยงจุดเดียวของความล้มเหลว และสามารถโหลดการรับส่งข้อมูลสมดุลข้ามเกตเวย์ คุณสามารถ:

- ติดตั้งเกตเวย์หนึ่งรายการหรือมากกว่าได้ในคลัสเตอร์
- แยกปริมาณงานไปยังเกตเวย์แบบสแตนด์อโลน หรือคลัสเตอร์ของเซิร์ฟเวอร์เกตเวย์ได้

สำหรับข้อมูลเพิ่มเติม ดู [การจัดการคลัสเตอร์เกตเวย์ข้อมูลภายในองค์กรที่มีความพร้อมใช้งานสูงและการปรับสมดุลการโหลด](/data-integration/gateway/service-gateway-high-availability-clusters)

### <a name="dataset-design-and-settings"></a>การออกแบบชุดข้อมูลและการตั้งค่า

การออกแบบชุดข้อมูลและการตั้งค่าอาจส่งผลต่อปริมาณงานเกตเวย์ หากต้องการลดปริมาณงานเกตเวย์ คุณสามารถพิจารณาการดำเนินการต่อไปนี้

สำหรับชุดข้อมูลที่นำเข้า:

- กำหนดค่าการรีเฟรชข้อมูลน้อยลง
- กำหนดค่า [การรีเฟรชแบบเพิ่มทีละส่วน](../service-premium-incremental-refresh.md) เพื่อลดจำนวนข้อมูลที่จะถ่ายโอน
- เมื่อใดที่เป็นไปได้ ตรวจสอบแน่ใจว่ามี [การพับคิวรี](power-query-folding.md)เกิดขึ้น
- โดยเฉพาะอย่างยิ่งสำหรับข้อมูลขนาดใหญ่หรือความจำเป็นสำหรับผลลัพธ์ที่มีความแฝงต่ำ ให้แปลงการออกแบบเป็นแบบจำลอง DirectQuery หรือ [แบบรวม](../service-dataset-modes-understand.md#composite-mode)

สำหรับชุดข้อมูล DirectQuery:

- ปรับแหล่งข้อมูล แบบจำลอง และการออกแบบรายงานให้เหมาะสม สำหรับข้อมูลเพิ่มเติม ดู [คำแนะนำแบบจำลอง DirectQuery ใน Power BI Desktop](directquery-model-guidance.md)
- สร้าง [การรวม](../desktop-aggregations.md) เพื่อแคชผลลัพธ์ในระดับที่สูงขึ้น เพื่อลดจำนวนคำขอ DirectQuery
- จำกัดช่วง [การรีเฟรชหน้าอัตโนมัติ](../desktop-automatic-page-refresh.md) ในการออกแบบรายงานและการตั้งค่าความจุ
- โดยเฉพาะอย่างยิ่งเมื่อบังคับใช้ RLS แบบไดนามิก ให้จำกัดความถี่ในการอัปเดตแคชของแดชบอร์ด
- โดยเฉพาะอย่างยิ่งสำหรับข้อมูลที่มีขนาดเล็กหรือสำหรับข้อมูลถาวร ให้แปลงการออกแบบเป็นแบบจำลองการนำเข้าหรือ [แบบรวม](../service-dataset-modes-understand.md#composite-mode)

สำหรับชุดข้อมูลการเชื่อมต่อสด:

- โดยเฉพาะอย่างยิ่งเมื่อบังคับใช้ RLS แบบไดนามิก ให้จำกัดความถี่ในการอัปเดตแคชของแดชบอร์ด

## <a name="next-steps"></a>ขั้นตอนถัดไป

สำหรับข้อมูลเพิ่มเติมที่เกี่ยวข้องกับบทความนี้ โปรดดูทรัพยากรต่อไปนี้:

- [คำแนะนำสำหรับการปรับใช้เกตเวย์ข้อมูลจาก Power BI](../service-gateway-deployment-guidance.md)
- [กำหนดค่าการตั้งค่าพร็อกซีสำหรับเกตเวย์ข้อมูลภายในองค์กร](/data-integration/gateway/service-gateway-proxy)
- [การตรวจสอบและปรับประสิทธิภาพการทำงานของเกตเวย์ข้อมูลภายในองค์กรให้เหมาะสม](/data-integration/gateway/service-gateway-performance)
- [แก้ไขปัญหาเกตเวย์-Power BI](../service-gateway-onprem-tshoot.md)
- [แก้ไขปัญหาเกตเวย์ข้อมูลภายในองค์กร](/data-integration/gateway/service-gateway-tshoot)
- [ความสำคัญของการพับคิวรี](power-query-folding.md)
- มีคำถามหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
- มีข้อเสนอแนะไหม [สนับสนุนแนวคิดในการปรับปรุง Power BI](https://ideas.powerbi.com)
---
title: คำแนะนำการปรับให้เหมาะสมสำหรับ Power BI
description: คำแนะนำการปรับให้เหมาะสมสำหรับ Power BI
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/16/2020
ms.author: v-pemyer
ms.openlocfilehash: f189ea2944f86a3caabfbc51ae5b2887bc7c89bb
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83278618"
---
# <a name="optimization-guide-for-power-bi"></a>คำแนะนำการปรับให้เหมาะสมสำหรับ Power BI

บทความนี้ให้คำแนะนำที่จะช่วยให้นักพัฒนาและผู้ดูแลระบบสามารถผลิตและบำรุงรักษาโซลูชัน Power BI ที่เหมาะสมได้ คุณสามารถเพิ่มประสิทธิภาพโซลูชันของคุณในเลเยอร์สถาปัตยกรรมที่แตกต่างกันได้ เลเยอร์ประกอบไปด้วย:

- แหล่งข้อมูล
- แบบจำลองข้อมูล
- การแสดงภาพประกอบ รวมถึงแดชบอร์ด รายงาน Power BI และรายงานเลขหน้า Power BI
- สภาพแวดล้อม รวมถึงความจุ เกตเวย์ข้อมูล และเครือข่าย

## <a name="optimizing-the-data-model"></a>ปรับรูปแบบข้อมูลให้เหมาะสมยิ่งขึ้น

โมเดลข้อมูลรองรับการทำงานการสร้างภาพข้อมูลทั้งหมด รูปแบบข้อมูลเป็นโฮสต์ภายนอกหรือโฮสต์ภายใน และใน Power BI เรียกว่าเป็น_ชุดข้อมูล_ สิ่งสำคัญคือต้องเข้าใจตัวเลือกของคุณและเลือกประเภทชุดข้อมูลที่เหมาะสมสำหรับโซลูชันของคุณด้วย มีโหมดชุดข้อมูลที่สามโหมดคือ: นำเข้า, DirectQuery และแบบผสม สำหรับข้อมูลเพิ่มเติม โปรดดู[ชุดข้อมูลในบริการ Power BI](../connect-data/service-datasets-understand.md) และโหมดชุดข้อมูล[ในบริการ Power BI](../connect-data/service-dataset-modes-understand.md)

สำหรับคำแนะนำโหมดชุดข้อมูลเฉพาะ โปรดดู:

- [เทคนิคการลดข้อมูลเพื่อการนำเข้าการสร้างแบบจำลอง](import-modeling-data-reduction.md)
- [คำแนะนำแบบจำลอง DirectQuery ใน Power BI Desktop](directquery-model-guidance.md)
- [คำแนะนำแบบจำลองแบบรวมใน Power BI Desktop](composite-model-guidance.md)

## <a name="optimizing-visualizations"></a>การจัดรูปแบบการแสดงข้อมูล

การแสดงภาพ Power BI สามารถเป็นแดชบอร์ด รายงาน Power BI หรือรายงานเลขหน้า Power BI ได้ แต่ละคนมีสถาปัตยกรรมที่แตกต่างกันและแต่ละคนก็มีแนวทางของตนเอง 

### <a name="dashboards"></a>แดชบอร์ด

สิ่งสำคัญคือต้องเข้าใจว่า Power BI จะเก็บแคชสำหรับไทล์แดชบอร์ดของคุณ - ยกเว้นไทล์รายงานสด และไทล์สตรีม สำหรับข้อมูลเพิ่มเติม โปรดดู[การรีเฟรชข้อมูลใน Power BI](../connect-data/refresh-data.md#tile-refresh) หากชุดข้อมูลของคุณบังคับใช้[การรักษาความปลอดภัยระดับแถว (RLS)](../admin/service-admin-rls.md)แบบไดนามิก  โปรดทำให้แน่ใจว่าคุณได้ทำความเข้าใจผลกระทบด้านประสิทธิภาพเนื่องจากไทล์จะแคชต่อผู้ใช้แต่ละคน

เมื่อคุณปักหมุดไทล์รายงานสดไปยังแดชบอร์ด ไทล์เหล่านั้นจะไม่ได้รับบริการจากแคชคิวรี แต่จะทำงานเหมือนกับรายงาน และสร้างคิวรีไปยังให้กับคอร์ส่วนหลังได้ทันที

ซึ่งก็เป็นไปตามชื่อ การดึงข้อมูลจากแคชคิวรี มีประสิทธิภาพที่ดีกว่าและสม่ำเสมอกว่าการพึ่งพาแหล่งข้อมูล วิธีหนึ่งที่ใช้ประโยชน์จากความสามารถนี้ คือให้แดชบอร์ดเป็นเพจเริ่มต้นสำหรับผู้ใช้ของคุณ ปักหมุดวิชวลที่เรียกใช้บ่อยและมีการร้องขออย่างมากไปยังแดชบอร์ด ด้วยวิธีนี้ แดชบอร์ดที่กลายเป็น "ปราการด่านแรก" ซึ่งมีประสิทธิภาพที่เสมอต้นเสมอปลาย และโหลดบนความจุที่น้อยลง ผู้ใช้ยังคงสามารถคลิกเข้าไปในรายงานเพื่อวิเคราะห์รายละเอียดได้

สำหรับ DirectQuery และชุดข้อมูลการเชื่อมต่อสด แคชของคิวรีนี้จะมีการอัปเดตเป็นระยะๆ ด้วยการคิวรีแหล่งข้อมูล ตามค่าเริ่มต้น การดำเนินการนี้จะเกิดจะเกิดขึ้นทุกชั่วโมงแม้ว่าคุณจะสามารถกำหนดค่าความถี่ที่แตกต่างกันในการตั้งค่าชุดข้อมูลได้ก็ตาม ทุกๆ การอัปเดตแคชจะส่งคิวรีไปยังแหล่งข้อมูลพื้นฐานเพื่ออัปเดตแคช จำนวนคิวที่สร้างขึ้น จะขึ้นอยู่กับจำนวนวิชวลที่ปักหมุดไปยังแดชบอร์ดที่ใช้แหล่งข้อมูลนั้น โปรดสังเกตว่า ถ้าเปิดใช้งานความปลอดภัยระดับแถว คิวรีจะสร้างขึ้นสำหรับแต่ละบริบทความปลอดภัยที่แตกต่างกัน ตัวอย่างเช่น พิจารณาว่ามีสองบทบาทที่แตกต่างกันที่จัดประเภทผู้ใช้ของคุณแ ละพวกเขามีสองมุมมองที่แตกต่างกันของข้อมูล ในระหว่างการรีเฟรชแคชของคิวรี Power BI จะสร้างชุดคิวรีที่สอง

### <a name="power-bi-reports"></a>รายงาน Power BI

มีคำแนะนำหลายอย่างในการเพิ่มประสิทธิภาพการออกแบบรายงาน Power BI

> [!NOTE]
> เมื่อรายงานยึดตามชุดข้อมูล DirectQuery สำหรับการปรับแต่งการออกแบบรายงานเพิ่มเติม ให้ดู[คำแนะนำโมเดล DirectQuery ใน Power BI Desktop (ปรับให้เหมาะสมกับการออกแบบรายงาน)](directquery-model-guidance.md#optimize-report-designs)

#### <a name="apply-the-most-restrictive-filters"></a>ใช้ตัวกรองที่เข้มงวดที่สุด

ยิ่งวิชวลต้องแสดงข้อมูลมากขึ้นเท่าไร วิชวลจะยิ่งโหลดช้าลงเท่านั้น แม้ว่าหลักนี้จะดูตรงไปตรงมา แต่ก็ลืมได้ง่าย ตัวอย่างเช่น: สมมติว่าคุณมีชุดข้อมูลขนาดใหญ่ ยิ่งกว่าชุดข้อมูลนั้น คุณจะสร้างรายงานด้วยตาราง ผู้ใช้ปลายทางใช้ตัวแบ่งส่วนข้อมูลบนหน้าเพื่อเข้าถึงแถวที่พวกเขาต้องการ – โดยทั่วไปแล้วพวกเขาสนใจเฉพาะแถวไม่กี่สิบแถว

ข้อผิดพลาดที่พบบ่อยคือ ไม่มีการกรองมุมมองตามค่าเริ่มต้นของตาราง - นั่นคือแถวทั้งหมดที่มีซึ่งอาจมีมากกว่า 100 ล้านแถว ข้อมูลสำหรับแถวเหล่านี้จะโหลดลงในหน่วยความจำ และขยายข้อมูลกลับทุกครั้งที่รีเฟรช การประมวลผลนี้จะสร้างการโหลดหน่วยความจำขนาดใหญ่ แนวทางการแก้ไข: ใช้ตัวกรอง "Top N" เพื่อลดจำนวนสูงสุดของรายการที่ตารางแสดง คุณสามารถตั้งค่าจำนวนรายการสูงสุดให้มากกว่าจำนวนที่ผู้ใช้ต้องการ เช่น 10,000 รายการ ผลลัพธ์คือประสบการณ์การใช้งานของผู้ใช้ไม่เปลี่ยนแปลง แต่การใช้หน่วยความจำจะลดลงอย่างมาก และที่สำคัญที่สุดคือการปรับปรุงประสิทธิภาพการทำงาน

แนวทางเดียวกันกับข้างบน เป็นแนวทางที่แนะนำสำหรับวิชวลทั้งหมดในรายงานของคุณ ถามตัวคุณเอง ข้อมูลทั้งหมดในวิชวลนี้จำเป็นหรือไม่? มีวิธีการกรองข้อมูลที่แสดงในวิชวลโดยที่ส่งผลต่อประสบการณ์การใช้งานของผู้ใช้ปลายทางน้อยที่สุดหรือไม่ โปรดจำไวว่า ตารางอาจใช้ทรัพยากรสูง

#### <a name="limit-visuals-on-report-pages"></a>จำกัดวิชวลบนหน้ารายงาน

หลักการด้านบนสามารถนำไปใช้กับจำนวนการแสดงผลด้วยภาพบนรายงานใดรายงานหนึ่งได้ เราแนะนำให้คุณจำกัดจำนวนของการแสดงผลด้วยภาพบนรายงาน ให้มีการแสดงผลด้วยภาพเฉพาะเท่าที่จำเป็นเท่านั้น [หน้าดูข้อมูลแบบละเอียด](report-drillthrough.md)และ[คำแนะนำเครื่องมือสำหรับหน้ารายงาน](report-page-tooltips.md) เป็นวิธีที่ยอดเยี่ยมเพื่อเพิ่มรายละเอียดโดยไม่ต้องใส่การแสดงผลด้วยภาพลงในหน้า

#### <a name="evaluate-custom-visual-performance"></a>ประเมินประสิทธิภาพการแสดงผลด้วยภาพแบบกำหนดเอง

ตรวจสอบให้แน่ใจว่าได้ทดสอบแต่ละวิชวลแบบกำหนดเองอย่างละเอียดเพื่อให้แน่ใจว่ามีประสิทธิภาพการทำงานสูง วิชวล Power BI ที่ปรับแต่งได้ไม่ดี สามารถส่งผลเสียต่อประสิทธิภาพการทำงานของทั้งรายงาน

### <a name="power-bi-paginated-reports"></a>Power BI รายงานเลขหน้า

การออกแบบรายงานที่มีการแบ่งหน้าของ Power BI สามารถปรับให้เหมาะสมได้โดยใช้การออกแบบแนวทางปฏิบัติที่ดีที่สุดกับการเรียกข้อมูลของรายงาน สำหรับข้อมูลเพิ่มเติม โปรดดู[คำแนะนำการเรียกข้อมูลสำหรับรายงานที่มีการแบ่งหน้า](report-paginated-data-retrieval.md)

นอกจากนี้ โปรดตรวจสอบให้แน่ใจว่าความจุของคุณมีหน่วยความจำเพียงพอที่จัดสรรให้กับ[ปริมาณรายงานที่มีการแบ่งหน้า](../admin/service-admin-premium-workloads.md#paginated-reports)

## <a name="optimizing-the-environment"></a>การปรับสภาพแวดล้อมให้เหมาะสม

คุณสามารถปรับสภาพแวดล้อม Power BI ให้เหมาะสมได้โดยการกำหนดค่าการตั้งค่าความจุ การปรับขนาดเกตเวย์ข้อมูล และลดเวลาแฝงของเครือข่าย

### <a name="capacity-settings"></a>การตั้งค่าความจุ

เมื่อใช้ความจุเฉพาะ — พร้อมใช้งานกับ Power BI Premium (P Sku) หรือ Power BI Embedded (Sku, A4-A6) — คุณสามารถจัดการการตั้งค่าความจุได้ สำหรับข้อมูลเพิ่มเติม ดู [การจัดการความจุแบบพรีเมียม](../admin/service-premium-capacity-manage.md) สำหรับคำแนะนำเกี่ยวกับวิธีการปรับใช้ความจุของคุณให้เหมาะสม โปรดดู[การปรับใช้ความจุแบบพรีเมียมให้เหมาะสม](../admin/service-premium-capacity-optimize.md)

### <a name="gateway-sizing"></a>การปรับขนาดเกตเวย์

จำเป็นต้องใช้เกตเวย์เมื่อ Power BI ต้องเข้าถึงข้อมูลที่ไม่สามารถใช้งานได้โดยตรงผ่านทางอินเทอร์เน็ต คุณสามารถติดตั้ง[เกตเวย์ข้อมูลภายในองค์กร](../connect-data/service-gateway-onprem.md)บนเซิร์ฟเวอร์ภายในองค์กร หรือ Infrastructure-as-a-Service (IaaS) ที่เป็นโฮสต์ของ VM

หากต้องการทำความเข้าใจเกี่ยวกับปริมาณงานเกตเวย์และคำแนะนำในการปรับขนาด ให้ดู[การปรับขนาดเกตเวย์ข้อมูลภายในองค์กร](gateway-onprem-sizing.md)

### <a name="network-latency"></a>เวลาแฝงในการส่งข้อมูลบนเครือข่าย

เวลาแฝงในการส่งข้อมูลบนเครือข่าย ส่งผลต่อประสิทธิภาพของรายงานได้ โดยการเพิ่มเวลาของคำขอที่จะไปถึงบริการของ Power BI และเวลาของการตอบกลับมา ผู้เช่าใน Power BI จะถูกกำหนดภูมิภาคให้เฉพาะ

> [!TIP]
> เมื่อต้องการกำหนดว่าผู้เช่า Power BI ของคุณจะอยู่ที่ใด ให้ดูที่[ผู้เช่า Power BI ของฉันอยู่ที่ไหน](../admin/service-admin-where-is-my-tenant-located.md)

เมื่อผู้ใช้จากผู้เช่าเข้าถึงบริการของ Power BI คำขอของพวกเขาจะกำหนดเส้นทางไปยังขอบเขตนี้เสมอ เมื่อคำขอเข้าถึงบริการของ Power BI แล้ว บริการอาจส่งคำขอเพิ่มเติม – ตัวอย่างเช่น ไปยังแหล่งข้อมูลพื้นฐานหรือเกตเวย์ข้อมูล – ซึ่งจะได้รับผลกระทบจากเวลาแฝงบนเครือข่ายด้วย

เครื่องมือเช่น [Azure Speed Test](https://azurespeedtest.azurewebsites.net/) สามารถหาเวลาแฝงบนเครือข่ายระหว่างไคลเอ็นต์และขอบเขตของ Azure ได้ โดยทั่วไป พยายามให้แหล่งข้อมูล เกตเวย์ และคลัสเตอร์ Power BI ของคุณอยู่ใกล้กันมากที่สุด เพื่อลดผลกระทบของเวลาแฝงบนเครือข่าย โดยเฉพาะเมื่อพวกเขาอาศัยอยู่ภายในภูมิภาคเดียวกัน ถ้าเเวลาแฝงบนเครือข่ายคือปัญหา ให้ลองย้ายเกตเวย์และแหล่งข้อมูลมาใกล้กับคลัสเตอร์ Power BI ของคุณมากขึ้นโดยการวางไว้ด้านในเครื่องเสมือนที่โฮสต์แบบคลาวด์

## <a name="monitoring-performance"></a>การตรวจสอบประสิทธิภาพ

คุณสามารถตรวจสอบประสิทธิภาพการทำงานเพื่อระบุประสิทธิภาพที่อยุ่ระดับคอขวดได้ คิวรีที่ช้า - หรือการแสดงผลด้วยภาพของรายงาน - ควรมีเป้าหมายในการปรับให้เหมาะสมอย่างต่อเนื่อง สามารถทำการตรวจสอบได้ในเวลาการออกแบบใน Power BI Desktop หรือในปริมาณการผลิตในความจุ Power BI Premium สำหรับข้อมูลเพิ่มเติม โปรดดูที่[การตรวจสอบประสิทธิภาพการทำงานของรายงานใน Power BI](monitor-report-performance.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับบทความนี้ โปรดดูทรัพยากรต่อไปนี้:

- [คำแนะนำ Power BI](index.yml)
- [การตรวจสอบประสิทธิภาพการทำงานของรายงาน](monitor-report-performance.md)
- เอกสารทางเทคนิค: [วางแผนการใช้งาน Power BI Enterprise](https://go.microsoft.com/fwlink/?linkid=2057861)
- มีคำถามหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
- มีข้อเสนอแนะไหม [สนับสนุนแนวคิดในการปรับปรุง Power BI](https://ideas.powerbi.com/)





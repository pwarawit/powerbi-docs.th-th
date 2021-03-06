---
title: บทนำชุดข้อมูลทั้งพื้นที่ทำงาน
description: เรียนรู้วิธีที่คุณสามารถแชร์ชุดข้อมูลกับผู้ใช้ทั้งองค์กร จากนั้นพวกเขาสามารถสร้างรายงานที่ยึดตามชุดข้อมูลของคุณในพื้นที่ทำงานของตนเอง
author: maggiesMSFT
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 04/30/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 5f79411d7eedc97e99aabc8b44dbf12a22696bba
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85236877"
---
# <a name="intro-to-datasets-across-workspaces"></a>บทนำชุดข้อมูลทั้งพื้นที่ทำงาน

ข่าวกรองธุรกิจเป็นกิจกรรมการทำงานร่วมกัน เป็นสิ่งสำคัญในการสร้างชุดข้อมูลที่ได้มาตรฐานซึ่งอาจเป็น “แหล่งข้อมูลความจริงแหล่งเดียว” การค้นหาและการนำชุดข้อมูลที่ได้มาตรฐานเหล่านั้นมาใช้ใหม่เป็นสิ่งสำคัญ เมื่อผู้สร้างข้อมูลที่เชี่ยวชาญในองค์กรของคุณจะสร้างและแชร์ชุดข้อมูลที่ปรับแต่งแล้ว ผู้สร้างรายงานสามารถเริ่มต้นใช้ชุดข้อมูลเหล่านั้นเพื่อสร้างรายงานที่ถูกต้อง แล้วองค์กรของคุณจะมีข้อมูลที่สอดคล้องกันสำหรับการตัดสินใจ และการพัฒนาข้อมูลที่สมบูรณ์แบบ

![เลือกชุดข้อมูลที่แชร์](media/service-datasets-across-workspaces/power-bi-select-shared-dataset.png)

ใน Power BI ผู้สร้างชุดข้อมูลสามารถควบคุมผู้ที่สามารถเข้าถึงข้อมูลได้โดยใช้[สิทธิ์ในการสร้าง](service-datasets-build-permissions.md) ผู้สร้างชุดข้อมูลยังสามารถ*รับรอง*หรือ*เลื่อนระดับ*ชุดข้อมูลเพื่อให้ผู้อื่นสามารถค้นหาได้ ด้วยวิธีนั้น ผู้เขียนรายงานจะทราบว่าชุดข้อมูลใดที่มีคุณภาพสูงและเป็นทางการและพวกเขาสามารถใช้ชุดข้อมูลเหล่านั้นได้ทุกที่ที่พวกเขาเขียนใน Power BI ผู้ดูแลระบบผู้เช่ามีการตั้งค่าผู้เช่าใหมเป็น[ควบคุมการใช้ชุดข้อมูลทั้งพื้นที่ทำงาน](service-datasets-admin-across-workspaces.md)

## <a name="dataset-sharing-and-the-new-workspace-experience"></a>การแชร์ชุดข้อมูลและประสบการณ์การใช้งานพื้นที่ทำงานใหม่

การสร้างรายงานที่ยึดตามชุดข้อมูลในพื้นที่ทำงานแตกต่างกัน และการคัดลอกรายงานไปยังพื้นที่ทำงานแตกต่างกันจะควบคู่ไปกับ[ประสบการณ์การใช้งานพื้นที่ทำงานใหม่](../collaborate-share/service-create-the-new-workspaces.md):

- ในบริการ เมื่อคุณเปิดแค็ตตาล็อกชุดข้อมูลจากประสบการณ์พื้นที่ทำงานใหม่ แค็ตตาล็อกชุดข้อมูลจะแสดงชุดข้อมูลที่อยู่ในพื้นที่ทำ งานของฉัน และในพื้นที่ทำงานที่มีประสบการณ์การใช้งานของพื้นที่ทำงานใหม่อันอื่น 
- เมื่อคุณเปิดแค็ตตาล็อกชุดข้อมูลจากพื้นที่ทำงานแบบคลาสสิก เฉพาะคุณเท่านั้นที่เห็นชุดข้อมูลในพื้นที่ทำงานนั้น ซึ่งไม่ได้อยู่ในพื้นที่ทำงานอื่น ๆ
- ใน Power BI Desktop คุณสามารถเผยแพร่รายงานที่เชื่อมต่อแบบสดกับพื้นที่ทำงานที่แตกต่างกัน ตราบใดที่ชุดข้อมูลเหล่านั้นอยู่ในพื้นที่ทำงานประสบการณ์การใช้งานใหม่
- เมื่อคัดลอกรายงานทั้งพื้นที่ทำงาน พื้นที่ทำงานเป้าหมายต้องเป็นพื้นที่ทำงานประสบการณ์การใช้งานใหม่

## <a name="discover-datasets"></a>ค้นพบชุดข้อมูล

เมื่อสร้างรายงานด้านบนของชุดข้อมูลที่มีอยู่ ขั้นตอนแรกคือการเชื่อมต่อกับชุดข้อมูล ในบริการ Power BI หรือ Power BI Desktop อ่านเกี่ยวกับ [การค้นพบชุดข้อมูลจากพื้นที่ทำงานแตกต่างกัน](service-datasets-discover-across-workspaces.md)

## <a name="copy-a-report"></a>คัดลอกรายงาน

เมื่อคุณพบรายงานที่คุณชอบในพื้นที่ทำงานหรือแอป คุณสามารถทำสำเนา และปรับเปลี่ยนให้พอดีกับความต้องการของคุณ คุณไม่ต้องกังวลเกี่ยวกับการสร้างแบบจำลองข้อมูล แบบจำลองจะถูกสร้างไว้แล้วสำหรับคุณ และการแก้ไขรายงานที่มีอยู่นั้นง่ายกว่าการเริ่มจากศูนย์ อ่านเพิ่มเติมเกี่ยวกับ[การคัดลอกรายงาน](service-datasets-copy-reports.md)

## <a name="build-permission-for-datasets"></a>สิทธิในการสร้างสำหรับชุดข้อมูล

ด้วยชนิดของสิทธิ์ในการสร้าง ถ้าคุณเป็นผู้สร้างชุดข้อมูล คุณสามารถกำหนดได้ว่าผู้ใดในองค์กรของคุณสามารถสร้างเนื้อหาใหม่ในชุดข้อมูลของคุณได้ ผู้ที่มีสิทธิ์ในการสร้างยังสามารถสร้างเนื้อหาใหม่ในชุดข้อมูลที่อยู่นอก Power BI เช่น แผ่นงาน Excel ที่ผ่านการวิเคราะห์ใน Excel, XMLA และส่งออก อ่านเพิ่มเติมเกี่ยวกับ[สิทธิในการสร้าง](service-datasets-build-permissions.md)

## <a name="promotion-and-certification"></a>การเลื่อนระดับและการออกใบรับรอง

ถ้าคุณสร้างชุดข้อมูล เมื่อคุณสร้างชุดข้อมูลที่ผู้อื่นสามารถใช้ประโยชน์ได้ คุณสามารถทำให้ง่ายต่อการค้นหาได้โดย[การเลื่อนระดับชุดข้อมูลของคุณ](service-datasets-promote.md) คุณอาจร้องขอให้ผู้เชี่ยวชาญในองค์กรของคุณ[รับรองชุดข้อมูลของคุณ](service-datasets-certify.md)ได้

## <a name="licensing"></a>สิทธิ์การใช้งาน

คุณลักษณะเฉพาะและประสบการณ์การใช้งานที่สร้างขึ้นบนความสามารถของชุดข้อมูลที่ใช้ร่วมกันจะได้รับสิทธิการใช้งานตามสถานการณ์สมมติที่มีอยู่ ตัวอย่างเช่น:

- โดยทั่วไป การค้นพบและการเชื่อมต่อกับชุดข้อมูลที่แชร์จะพร้อมใช้งานสำหรับทุกคน – ซึ่งไม่ใช่คุณลักษณะที่จำกัดเฉพาะพรีเมียม
- ผู้ใช้ที่ไม่มีใบอนุญาต Pro จะสามารถใช้ชุดข้อมูลได้เฉพาะพื้นที่ทำงานสำหรับการเขียนรายงานเท่านั้น หากชุดข้อมูลเหล่านั้นอยู่ในพื้นที่ทำงานของฉันส่วนบุคคลของผู้ใช้หรือในพื้นที่ทำงานสำรองแบบพรีเมียม ข้อจำกัดการอนุญาตเดียวกันจะมีผลบังคับใช้ไม่ว่าจะเป็นผู้เขียนรายงานใน Power BI Desktop หรือในบริการของ Power BI
- การคัดลอกรายงานระหว่างพื้นที่ทำงานจำเป็นต้องมีสิทธิ์การใช้งานระดับ Pro
- การคัดลอกรายงานจากแอปต้องมีสิทธิใช้งานระดับ Pro ตามที่ต้องการสำหรับชุดเนื้อหาขององค์กร
- การเลื่อนระดับและการรับรองชุดข้อมูลต้องมีสิทธิ์การใช้งานระดับ Pro

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด

- ในฐานะผู้เผยแพร่แอป คุณต้องแน่ใจว่าผู้ชมของคุณสามารถเข้าถึงชุดข้อมูลภายนอกของพื้นที่ทำงาน ไม่เช่นนั้น ผู้ใช้จะพบกับปัญหาต่าง ๆ เมื่อใช้แอปของคุณ เช่น รายงานจะไม่ยอมเปิดโดยไม่มีการเข้าถึงชุดข้อมูล และไทล์แดชบอร์ดจะแสดงเป็นล็อก นอกจากนี้ ผู้ใช้จะไม่สามารถเปิดแอปได้หากรายการแรกในการนำทางคือรายงานที่ไม่มีการเข้าถึงชุดข้อมูล
- การสร้างรายงานที่ด้านบนของชุดข้อมูลในพื้นที่ทำงานแตกต่างกันจำเป็นต้องมีประสบการณ์การใช้งานพื้นที่ทำงานใหม่ที่ทั้งสองด้าน: รายงานต้องอยู่ในประสบการณ์การใช้งานพื้นที่ทำงานใหม่ และชุดข้อมูลต้องอยู่ในประสบการณ์การใช้งานพื้นที่ทำงานใหม่ คุณสามารถคัดลอกรายงานในประสบการณ์พื้นที่ทำงานใหม่ไปยังประสบการณ์พื้นที่ทำงานใหม่อื่นที่ไม่ใช่พื้นที่ทำงานแบบคลาสสิกหรือพื้นที่ทำงานของฉันได้ 
- ในพื้นที่ทำงานแบบคลาสสิก ประสบการณ์การใช้งานการค้นหาชุดข้อมูลจะแสดงเฉพาะชุดข้อมูลในพื้นที่ทำงานนั้นเท่านั้น
- การออกแบบ "เผยแพร่บนเว็บ" ไม่สามารถใช้ได้กับรายงานที่ยึดตามชุดข้อมูลที่ใช้ร่วมกัน
- ถ้ามีคน 2 คนเป็นสมาชิกของพื้นที่ทำงานที่กำลังเข้าถึงชุดข้อมูลที่ใช้ร่วมกัน เป็นไปได้ว่ามีเพียงหนึ่งคนเท่านั้นที่สามารถดูชุดข้อมูลที่เกี่ยวข้องในพื้นที่ทำงาน เฉพาะผู้ที่มีสิทธิการเข้าถึงแบบอ่านเป็นอย่างน้อยในชุดข้อมูลเท่านั้นที่สามารถเห็นชุดข้อมูลที่ใช้ร่วมกันได้ 

## <a name="next-steps"></a>ขั้นตอนถัดไป

- [เลื่อนระดับชุดข้อมูล](service-datasets-promote.md)
- [รับรองชุดข้อมูล](service-datasets-certify.md)
- [ควบคุมการใช้ชุดข้อมูลทั้งพื้นที่ทำงาน](service-datasets-admin-across-workspaces.md)
- มีคำถามหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)

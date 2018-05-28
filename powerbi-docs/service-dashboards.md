---
title: แดชบอร์ด Power BI คืออะไร?
description: แดชบอร์ดเป็นคุณลักษณะสำคัญของบริการ Power BI
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 02a88f04d3c23746da702db043c1992267baf054
ms.sourcegitcommit: 998b79c0dd46d0e5439888b83999945ed1809c94
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/17/2018
---
# <a name="dashboards-in-power-bi-service"></a>แดชบอร์ดในบริการ Power BI

***แดชบอร์ด*** Power BI เป็นแบบหน้าเดียว ซึ่งมักเรียกว่าพื้นที่ว่างเปล่าที่ใช้การแสดภาพเพื่อบอกเล่าเรื่องราวหนึ่ง ๆ ได้ เนื่องจากจำกัดอยู่เพียงหนึ่งหน้า แดชบอร์ดทีี่ออกแบบมาอย่างดีจะประกอบด้วยองค์ประกอบที่สำคัญที่สุดของเรื่องราวเท่านั้น

![แดชบอร์ด](media/service-dashboards/power-bi-dashboard2.png)

การแสดงภาพที่คุณเห็นบนแดชบอร์ดเรียกว่า*ไทล์* และจะถูก*ปักหมุด*ไปยังแดชบอร์ดจากรายงาน ถ้าคุณไม่คุ้นเคยกับ Power BI คุณสามารถเรียนรู้ข้อมูลพื้นฐานได้โดยการอ่าน[แนวคิดพื้นฐานของ Power BI](service-basic-concepts.md)

> [!NOTE]
> แดชบอร์ดเป็นคุณลักษณะของบริการ Power BI ไม่สามารถใช้งานได้บน Power BI Desktop เราไม่สามารถสร้างแดชบอร์ดในสำหรับมือถือได้ แต่สามารถ[ดูและแชร์](mobile-apps-view-dashboard.md)บนมือถือได้
> 
> 

การแสดงภาพบนแดชบอร์ดมาจากรายงาน และแต่ละรายงานจะยึดตามชุดข้อมูลชุดเดียว อันที่จริง วิธีหนึ่งในการนึกภาพแดชบอร์ดคือ ทางเข้าไปยังรายงานและชุดข้อมูลพื้นฐาน การเลือกการแสดงภาพนำคุณไปยังรายงาน (และชุดข้อมูล) ที่ใช้เพื่อสร้างการแสดงภาพดังกล่าว

![ไดอะแกรมจะแสดงความสัมพันธ์ระหว่างแดชบอร์ด รายงาน และชุดข้อมูล](media/service-dashboards/power-bi-diagram.png)

## <a name="advantages-of-dashboards"></a>ข้อดีของแดชบอร์ด
แดชบอร์ดเป็นวิธีที่ยอดเยี่ยมในการตรวจดูธุรกิจของคุณ ในการค้นหาคำตอบ และดูเมตริกที่สำคัญที่สุดของคุณอย่างรวดเร็ว การแสดงภาพบนแดชบอร์ดอาจมาจากหนึ่งหรือหลายชุดข้อมูลพื้นฐาน และจากรายงานหนึ่งหรือหลายรายงานพื้นฐาน แดชบอร์ดรวมข้อมูลภายในองค์กรและข้อมูลที่เกิดจากระบบคลาวด์ ให้มุมมองแบบรวมโดยไม่คำนึงถึงตำแหน่งที่ข้อมูลอยู่

แดชบอร์ดไม่ได้เป็นเพียงภาพที่สวยงาม เนื่องจากแดชบอร์ดสามารถโต้ตอบได้สูงและเราสามารถกำหนดเองได้สูง รวมถึงมีการอัปเดตไทล์เมื่อมีการเปลี่ยนแปลงข้อมูลพื้นฐาน

## <a name="dashboards-versus-reports"></a>แดชบอร์ดเทียบกับรายงาน
เรามักสับสนระหว่าง[รายงาน](service-reports.md)กับแดชบอร์ดเนื่องจากทั้งสองเป็นพื้นที่ที่กรอกข้อมูลด้วยการแสดงภาพเหมือนกัน แต่แดชบอร์ดกับรายงานมีความแตกต่างที่สำคัญบางประการ

| **ขีดความสามารถ** | **แดชบอร์ด** | **รายงาน** |
| --- | --- | --- |
| หน้า |หนึ่งหน้า |อย่างน้อยหนึ่งหน้า |
| แหล่งข้อมูล |อย่างน้อยหนึ่งรายงานและอย่างน้อยหนึ่งชุดข้อมูลต่อแดชบอร์ด |ชุดข้อมูลเดียวต่อรายงาน |
| พร้อมใช้งานใน Power BI Desktop |ไม่ใช่ |ใช่ สามารถสร้างและดูรายงานในเดสก์ท็อป |
| ปักหมุด |สามารถปักหมุดการแสดงภาพที่มีอยู่ (ไทล์) ไปยังแดชบอร์ดอื่น ๆ ของคุณได้จากแดชบอร์ดปัจจุบันเท่านั้น |สามารถปักหมุดการแสดงภาพ (เป็นไทล์) ไปยังแดชบอร์ดอื่น ๆ ของคุณได้ สามารถปักหมุดทั้งหน้ารายงานไปยังแดชบอร์ดใด ๆ ของคุณได้ |
| สมัครสมาชิก |ไม่สามารถสมัครสมาชิกไปยังแดชบอร์ด |สามารถสมัครใช้งานไปยังหน้ารายงานได้ |
| กำลังกรอง |ไม่สามารถกรองหรือแบ่งส่วนได้ |มีหลายวิธีในการกรอง ทำไฮไลท์ และแบ่งส่วน |
| ตั้งค่าการแจ้งเตือน |สามารถสร้างการแจ้งเตือนไปยังอีเมลของคุณเมื่อเป็นไปตามเงื่อนไขบางประการ |ไม่ใช่ |
| คุณลักษณะ |สามารถตั้งค่าแดชบอร์ดหนึ่งเป็นแดชบอร์ด "แนะนำ" ของคุณได้ |ไม่สามารถสร้างรายงานที่แนะนำได้ |
| สอบถามภาษาธรรมชาติ |พร้อมใช้งานจากแดชบอร์ด |ไม่พร้อมใช้งานจากรายงาน |
| สามารถเปลี่ยนประเภทการแสดงภาพ |หมายเลข อันที่จริงแล้ว หากเจ้าของรายงานเปลี่ยนประเภทการแสดงภาพในรายงาน การแสดงภาพที่ปักหมุดอยู่ในแดชบอร์ดจะไม่อัปเดต |ใช่ |
| สามารถดูตารางชุดข้อมูลพื้นฐานและพื้นที่ข้อมูลได้ |หมายเลข สามารถส่งออกข้อมูล แต่ไม่สามารถมองเห็นตารางและช่องข้อมูลในแดชบอร์ด |ใช่ สามารถดูตารางชุดข้อมูล ช่องข้อมูล และค่าได้ |
| สามารถสร้างการแสดงภาพได้ |จำกัดสำหรับการเพิ่มวิดเจ็ตไปยังแดชบอร์ดโดยใช้ "เพิ่มไทล์" |สามารถสร้างชนิดต่าง ๆ ของภาพ เพิ่มภาพแบบกำหนดเอง แก้ไขภาพและอื่น ๆ อีกมากได้ด้วยสิทธิ์การแก้ไข |
| การเลือกกำหนด |สามารถทำสิ่งต่าง ๆ ด้วยการแสดงภาพ (ไทล์) เช่น การย้ายและจัดเรียง ปรับขนาด เพิ่มการเชื่อมโยง เปลี่ยนชื่อ ลบ และแสดงเต็มหน้าจอ แต่ข้อมูลและการแสดงภาพเป็นแบบอ่านอย่างเดียว |ในมุมมองการอ่าน คุณสามารถเผยแพร่ ฝัง กรอง ส่งออก ดาวน์โหลดเป็น .pbix ดูเนื้อหาที่เกี่ยวข้อง สร้างรหัส QR วิเคราะห์ใน Excel และอื่น ๆ ได้  ในมุมมองการแก้ไข คุณสามารถทำทุกสิ่งที่กล่าวมาแล้วได้ และสามารถทำสิ่งอื่น ๆ ได้อีกมาก |

## <a name="dashboard-creators-and-dashboard-consumers"></a>สำหรับผู้สร้างแดชบอร์ดและผู้บริโภคแดชบอร์ด
คุณอาจเป็นผู้ที่สร้างแดชบอร์ดเพื่อใช้งานด้วยตนเอง หรือเพื่อแชร์กับเพื่อนร่วมงาน ทั้งนีี้ขึ้นอยู่กับบทบาทของคุณ คุณต้องการเรียนรู้วิธีการสร้างและแชร์แดชบอร์ด หรือคุณอาจเป็นบุคคลที่ได้รับแดชบอร์ดจากผู้อื่น คุณต้องการเรียนรู้วิธีการทำความเข้าใจและโต้ตอบกับแดชบอร์ด

ต่อไปนี้คือหัวข้อที่แยกตามบทบาทเพื่อช่วยให้คุณเริ่มต้นใช้งาน

Power BI Pro จำเป็นสำหรับทั้งการแชร์แดชบอร์ด และดูแดชบอร์ดที่แชร์

### <a name="if-you-will-be-creating-and-sharing-dashboards"></a>ถ้าคุณเป็นผู้สร้างและการแชร์แดชบอร์ด
* ใช้หนึ่งในตัวอย่างของเราเพื่อ[สร้างแดชบอร์ดจากรายงาน](service-dashboard-create.md)
* เรียนรู้เกี่ยวกับ[ไทล์แดชบอร์ด](service-dashboard-tiles.md)และวิธีที่แตกต่างกันทั้งหมดในการปักหมุดไทล์เหล่านั้นไปยังแดชบอร์ด
* ช่วยผู้บริโภคแดชบอร์ดของคุณโดยการสร้างแดชบอร์ดที่[ทำงานได้ดีกับการสอบถามภาษาธรรมชาติสำหรับคำถามและคำตอบ](service-prepare-data-for-q-and-a.md)และกับ[การดูข้อมูลเชิงลึกแบบรวดเร็ว](service-insights-optimize.md)
* ค้นหาวิธีที่แตกต่างกันทั้งหมดที่คุณสามารถ[แชร์แดชบอร์ดกับเพื่อนร่วมงาน](service-how-to-collaborate-distribute-dashboards-reports.md)ได้

### <a name="if-you-will-be-receiving-and-consuming-dashboards"></a>ถ้าคุณจะได้รับและใช้แดชบอร์ด
* สร้างความคุ้นเคยกับแดชบอร์ดโดยเข้าดูหนึ่งใน[ตัวอย่าง](sample-tutorial-connect-to-the-samples.md)ของเรา
* เรียนรู้เกี่ยวกับ[ไทล์แดชบอร์ด](service-dashboard-tiles.md)และสิ่งที่จะเกิดขึ้นเมื่อคุณเลือกหนึ่งแดชบอร์ด
* ไม่ชอบหน้าตาของแดชบอร์ด?  คุณสามารถ[ปรับขนาด ย้าย และเปลี่ยนชื่อไทล์](service-dashboard-edit-tile.md)ได้
* ต้องการติดตามไทล์แดชบอร์ดแต่ละรายการและได้รับอีเมลเมื่อถึงขีดจำกัดหนึ่งหรือไม่? [สร้างการแจ้งเตือนบนไทล์](service-set-data-alerts.md)
* เพลิดเพลินกับการถามคำถามเกี่ยวกับแดชบอร์ดของคุณ เรียนรู้วิธีใช้ [การถามตอบ Power BI](power-bi-tutorial-q-and-a.md) เพื่อถามคำถามเกี่ยวกับข้อมูลของคุณและรับคำตอบในรูปแบบการแสดงภาพ

> [!TIP]
> ถ้าคุณไม่พบสิ่งที่คุณกำลังค้นหาที่นี่ ใช้สารบัญทางด้านซ้าย
> 
> 

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เริ่มต้นใช้งาน Power BI](service-get-started.md)  
[Power BI - แนวคิดพื้นฐาน](service-basic-concepts.md)  
[Power BI Premium คืออะไร?](service-premium.md)  

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](http://community.powerbi.com/)

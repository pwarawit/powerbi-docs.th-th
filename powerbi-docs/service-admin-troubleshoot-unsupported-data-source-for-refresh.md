---
title: แก้ไขปัญหาแหล่งข้อมูลไม่รองรับสำหรับการรีเฟรช
description: แก้ไขปัญหาแหล่งข้อมูลไม่รองรับสำหรับการรีเฟรช
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 12/06/2017
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 32c42f21eafa7118ed3977340517aeebe8c4219b
ms.sourcegitcommit: e5cf19e16112c7dad1591c3b38d232267ffb3ae1
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/17/2019
ms.locfileid: "72542901"
---
# <a name="troubleshooting-unsupported-data-source-for-refresh"></a>แก้ไขปัญหาแหล่งข้อมูลไม่รองรับสำหรับการรีเฟรช
คุณอาจเห็นข้อผิดพลาดเมื่อพยายามที่จะกำหนดค่าชุดข้อมูลสำหรับรีเฟรชตามกำหนดการ

        You cannot schedule refresh for this dataset because it gets data from sources that currently don’t support refresh.

ซึ่งเกิดขึ้นเมื่อแหล่งข้อมูลที่คุณใช้ที่อยู่ภายใน Power BI Desktop ไมสนับสนุนการรีเฟรช คุณจะต้องค้นหาแหล่งข้อมูลที่คุณกำลังใช้และการเปรียบเทียบแหล่งข้อมูลดังกล่าวกับรายการของแหล่งข้อมูลที่สนับสนุนที่[รีเฟรชข้อมูลใน Power BI](refresh-data.md) 

## <a name="find-the-data-source"></a>ค้นหาแหล่งข้อมูล
ถ้าคุณไม่แน่ใจว่ามีการใช้แหล่งข้อมูลใด คุณสามารถค้นหาได้โดยการใช้ขั้นตอนต่อไปนี้ภายใน Power BI Desktop  

1. ใน Power BI Desktop ตรวจสอบให้แน่ใจว่าคุณอยู่บนพื้นที่**รายงาน**  
   ![บานหน้าต่างรายงานบนเดสก์ท็อป](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-report-pane.png)
2. เลือก**แก้ไขแบบสอบถาม**จากแถบ Ribbon  
   ![แก้ไขคิวรี](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-edit-queries.png)
3. เลือก**ตัวแก้ไขขั้นสูง**  
   ![ตัวแก้ไขขั้นสูง](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-advanced-editor.png)
4. สร้างบันทึกย่อของผู้ให้บริการที่อยู่ในรายการสำหรับแหล่งข้อมูล  ในตัวอย่างนี้ ผู้ให้บริการคือ ActiveDirectory  
   ![ตัวให้บริการแหล่งข้อมูล](media/service-admin-troubleshoot-unsupported-data-source-for-refresh/tshoot-provider.png)
5. เปรียบเทียบผู้ให้บริการด้วยรายการของแหล่งข้อมูลที่สนับสนุนที่พบใน[รีเฟรชข้อมูลใน Power BI](refresh-data.md)  คุณจะพบว่า Active Directory ไม่ใช่แหล่งข้อมูลที่สนับสนุนสำหรับรีเฟรช  

## <a name="next-steps"></a>ขั้นตอนถัดไป
[รีเฟรชข้อมูล](refresh-data.md)  
[เกตเวย์ Power BI - ส่วนบุคคล](service-gateway-personal-mode.md)  
[เกตเวย์ข้อมูลภายในองค์กร](service-gateway-onprem.md)  
[การแก้ไขปัญหาเกตเวย์ข้อมูลในองค์กร](service-gateway-onprem-tshoot.md)  
[แก้ไขปัญหาเกตเวย์ Power BI - ส่วนบุคคล](service-admin-troubleshooting-power-bi-personal-gateway.md)  

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](http://community.powerbi.com/)


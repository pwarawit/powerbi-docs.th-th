---
title: ผสาน หรือผนวก แหล่งข้อมูลภายในองค์กรและในระบบคลาวด์
description: ใช้เกตเวย์ข้อมูลภายในองค์กร เพื่อผสานหรือผนวก แหล่งข้อมูลภายในองค์กรและในระบบคลาวด์ ในคิวรีเดียวกัน
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 06/06/2018
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 7b863af882604be8c2c59fd21f26cd8441f9e170
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54272664"
---
# <a name="merge-or-append-on-premises-and-cloud-data-sources"></a>ผสาน หรือผนวก แหล่งข้อมูลภายในองค์กรและในระบบคลาวด์

เกตเวย์ข้อมูลภายในองค์กร ให้คุณสามารถผสานหรือผนวกแหล่งข้อมูล ภายในองค์กรและในระบบคลาวด์ ในคิวรีเดียวกัน ซึ่งจะมีประโยชน์เมื่อคุณต้องการผสมข้อมูลจากหลายแหล่งข้อมูลเข้าด้วยกัน โดยไม่ต้องใช้คิวรีที่แยกต่างหาก

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

- [เกตเวย์ที่ติดตั้ง](service-gateway-install.md)ภายในคอมพิวเตอร์
- ไฟล์ Power BI Desktop ที่มีคิวรีที่รวมแหล่งข้อมูลภายในองค์กรและในระบบคลาวด์

1. ที่มุมบนขวาของบริการของ Power BI เลือกไอคอนรูปเฟือง ![ไอคอนเฟืองตั้งค่า](media/service-gateway-mashup-on-premises-cloud/icon-gear.png) > **จัดการเกตเวย์**

    ![จัดการเกตเวย์](media/service-gateway-mashup-on-premises-cloud/manage-gateways.png)

2. เลือกเกตเวย์ที่คุณต้องการกำหนดค่า

3. ภายใต้**การตั้งค่าคลัสเตอร์เกตเวย์** เลือก**อนุญาตให้แหล่งข้อมูลระบบคลาวด์ของผู้ใช้รีเฟรชผ่านคลัสเตอร์เกตเวย์นี้** > **นำไปใช้**

    ![รีเฟรชผ่านคลัสเตอร์เกตเวย์นี้](media/service-gateway-mashup-on-premises-cloud/refresh-gateway-cluster.png)

4. ภายใต้คลัสเตอร์เกตเวย์นี้ เพิ่ม[แหล่งข้อมูลในองค์กร](service-gateway-enterprise-manage-scheduled-refresh.md#add-a-data-source)ใด ๆ ที่ใช้ในคิวรีของคุณ คุณไม่จำเป็นต้องเพิ่มแหล่งข้อมูลระบบคลาวด์ตรงนี้

5. อัปโหลดไฟล์ Power BI Desktop พร้อมคิวรีที่รวมแหล่งข้อมูลภายในองค์กรและในระบบคลาวด์ของคุณ ไปยังบริการของ Power BI

6. บนหน้า**การตั้งค่าชุดข้อมูล**สำหรับชุดข้อมูลใหม่:

   - สำหรับแหล่งข้อมูลภายในองค์กร เลือกเกตเวย์ที่เกี่ยวข้องกับแหล่งข้อมูลนี้

   - ภายใต้**ข้อมูลประจำตัวของแหล่งข้อมูล** แก้ไขข้อมูลประจำตัวแหล่งข้อมูลคลาวด์ที่จำเป็น

     ![การตั้งค่าชุดข้อมูล](media/service-gateway-mashup-on-premises-cloud/dataset-settings.png)

7. เมื่อตั้งค่าข้อมูลประจำตัวบนระบบคลาวด์แล้ว คุณสามารถรีเฟรชชุดข้อมูลได้ โดยใช้ตัวเลือก**รีเฟรชเดี๋ยวนี้** หรือกำหนดเวลาการรีเฟรชเป็นระยะได้


## <a name="next-steps"></a>ขั้นตอนถัดไป

เพื่อเรียนรู้เพิ่มเติมเกี่ยวกับการรีเฟรชข้อมูลสำหรับเกตเวย์ ดู[การใช้แหล่งข้อมูลสำหรับการรีเฟรชตามกำหนดเวลา](service-gateway-enterprise-manage-scheduled-refresh.md#using-the-data-source-for-scheduled-refresh)
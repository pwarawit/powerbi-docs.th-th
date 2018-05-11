---
title: กำหนดค่าพร็อกซีสำหรับเกตเวย์ข้อมูลภายในองค์กร
description: ข้อมูลเกี่ยวกับการกำหนดค่าพร็อกซีสำหรับเกตเวย์ข้อมูลภายในองค์กร
services: powerbi
documentationcenter: ''
author: mgblythe
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 11/21/2017
ms.author: mblythe
LocalizationGroup: Gateways
ms.openlocfilehash: 130f4dcea4bc168bd71cd6d8c7c623bfca95d259
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/08/2018
---
# <a name="configuring-proxy-settings-for-the-on-premises-data-gateway"></a>กำหนดค่าพร็อกซีสำหรับเกตเวย์ข้อมูลภายในองค์กร
สภาพแวดล้อมการทำงานของคุณ อาจบังคับให้คุณต้องเข้าถึงอินเทอร์เน็ตผ่านทางพร็อกซี ซึ่งอาจทำให้เกตเวย์ข้อมูลภายในองค์กรไม่สามารถเชื่อมต่อกับบริการได้

## <a name="does-your-network-use-a-proxy"></a>เครือข่ายของคุณใช้พร็อกซีหรือไม่
โพสต์บน superuser.com ต่อไปนี้ อธิบายวิธีที่คุณสามารถทดลองว่า คุณมีพร็อกซีบนเครือข่ายของคุณหรือไม่

[จะทราบว่าฉันกำลังใช้พร็อกซีเซิร์ฟเวอร์ไหนได้อย่างไร (SuperUser.com)](https://superuser.com/questions/346372/how-do-i-know-what-proxy-server-im-using)

## <a name="configuration-file-location-and-default-configuration"></a>ตำแหน่งของไฟล์กำหนดค่า และค่าเริ่มต้น
ข้อมูลพร็อกซี กำหนดค่าโดยแฟ้มกำหนดค่าของ .NET ตำแหน่งที่ตั้ง และชื่อไฟล์ จะแตกต่างกันขึ้นอยู่กับเกตเวย์ที่คุณกำลังใช้

### <a name="on-premises-data-gateway"></a>เกตเวย์ข้อมูลภายในองค์กร
มีแฟ้มกำหนดค่าหลักอยู่สองแฟ้มที่เกี่ยวข้องกับเกตเวย์ข้อมูลภายในองค์กร

**การกำหนดค่า**

แฟ้มแรกใช้สำหรับหน้าจอการกำหนดค่า ที่ไปใช้กำหนดค่าให้กับเกตเวย์จริง ๆ ถ้าคุณกำลังมีปัญหาในการกำหนดค่าเกตเวย์ นี่คือไฟล์คุณต้องการดู

    C:\Program Files\On-premises data gateway\enterprisegatewayconfigurator.exe.config

**บริการ Windows**

แฟ้มที่สองใช้สำหรับบริการ windows ที่ใช้โต้ตอบกับบริการของ Power BI และจัดการตามคำร้องขอ

    C:\Program Files\On-premises data gateway\Microsoft.PowerBI.EnterpriseGateway.exe.config

## <a name="configuring-proxy-settings"></a>การกำหนดค่าพร็อกซี
ค่าเริ่มต้นของพร็อกซีกำหนดไว้ดังนี้

    <system.net>
        <defaultProxy useDefaultCredentials="true" />
    </system.net>

ค่าเริ่มต้นทำงานได้กับ การรับรองความถูกต้องของ Windows ถ้าพร็อกซีของคุณใช้วิธีรับรองความถูกต้องอื่น คุณจะต้องเปลี่ยนการตั้งค่า ถ้าคุณไม่แน่ใจ คุณควรติดต่อผู้ดูแลเครือข่ายของคุณ

ถ้าต้องการเรียนรู้เพิ่มเติมเกี่ยวกับการกำหนดค่าต่าง ๆ ของพร็อกซีในแฟ้มกำหนดค่าของ .NET ดูที่ [ค่า defaultProxy (การตั้งค่าเครือข่าย)](https://msdn.microsoft.com/library/kd3cf2ex.aspx)

## <a name="changing-the-gateway-service-account-to-a-domain-user"></a>การเปลี่ยนแปลงบัญชีบริการเกตเวย์ไปยังผู้ใช้โดเมน
เมื่อกำหนดค่าพร็อกซีไปใช้ค่าเริ่มต้นสำหรับข้อมูลประจำตัว ตามที่อธิบายไว้ด้านบน คุณอาจพบปัญหาการรับรองความถูกต้องกับพร็อกซีของคุณ เนื่องจากตามปกติแล้ว บัญชีบริการเริ่มต้น คือ SID ของบริการ ไม่ใช่ผู้ใช้โดเมนที่ต้องรับรองความถูกต้อง คุณสามารถเปลี่ยนบัญชีบริการเกตเวย์ เพื่อให้มีการรับรองความถูกต้องกับพร็อกซีของคุณ

> [!NOTE]
> ขอแนะนำให้ คุณใช้บัญชีผู้ใช้บริการที่มีการจัดการ เพื่อหลีกเลี่ยงที่ต้องรีเซ็ตรหัสผ่าน เรียนรู้วิธีสร้าง [บัญชีผู้ใช้บริการที่มีการจัดการ](https://technet.microsoft.com/library/dd548356.aspx)ภายใน Active Directory
> 
> 

### <a name="change-the-on-premises-data-gateway-service-account"></a>เปลี่ยนบัญชีบริการของเกตเวย์ข้อมูลภายในองค์กร
1. เปลี่ยนบัญชีบริการของ Windows สำหรับ **บริการของเกตเวย์ข้อมูลภายในองค์กร**
   
    บัญชีเริ่มต้นของบริการนี้คือ *NT SERVICE\PBIEgwService* คุณจะต้องการเปลี่ยนบัญชีนี้ไปเป็น บัญชีผู้ใช้โดเมน ภายในโดเมน Active Directory ของคุณ หรือไม่ก็ ต้องการเปลี่ยนไปใช้ บัญชีผู้ใช้บริการที่มีการจัดการ เพื่อจะไม่ต้องเปลี่ยนรหัสผ่าน
   
    คุณจะเปลี่ยนบัญชีผู้ใช้ตรงแท็บ**เข้าสู่ระบบ** ภายในหน้าคุณสมบัติของ บริการของ Windows
2. รีสตาร์ท**บริการเกตเวย์ข้อมูลภายในองค์กร**
   
    จากพร้อมท์คำสั่งของผู้ดูแลระบบ เรียกคำสั่งต่อไปนี้
   
        net stop PBIEgwService
   
        net start PBIEgwService
3. เริ่ม**โปรแกรมตั้งค่าบริการเกตเวย์ข้อมูลภายในองค์กร** คุณสามารถเลือก ปุ่มเริ่มต้น ของ Windows แล้วค้นหา*เกตเวย์ข้อมูลภายในองค์กร*
4. ลงชื่อเข้าใช้ไปยัง Power BI
5. คืนค่าเกตเวย์โดยใช้คีย์การกู้คืน
   
    ซึ่งจะทำให้บัญชีบริการใหม่ สามารถถอดรหัสข้อมูลประจำตัวสำหรับแหล่งข้อมูล

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เกตเวย์ข้อมูลภายในองค์กร (โหมดส่วนตัว)](service-gateway-personal-mode.md)
[ข้อมูลไฟร์วอลล์](service-gateway-onprem-tshoot.md#firewall-or-proxy)  
ถ้าคุณมีคำถามเพิ่มเติม [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)

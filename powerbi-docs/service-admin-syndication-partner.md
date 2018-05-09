---
title: ไม่สามารถเพิ่ม Power BI กับคู่ค้า O365
description: ไม่สามารถเพิ่ม Power BI กับคู่ค้า syndication สำหรับ Office 365 รูปแบบ syndication เป็นรูปแบบการจัดซื้อแบบหนึ่ง ที่ใช้โดย Office 365
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
ms.date: 09/05/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: ace24b392668b5459d21a451319fd54eb6430371
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/08/2018
---
# <a name="unable-to-add-power-bi-to-office-365-partner-subscription"></a>ไม่สามารถเพิ่ม Power BI กับ Office 365 ที่สมัครผ่านคู่ค้า
Office 365 อนุญาตให้บริษัทสามารถขายต่อ Office 365 โดยรวมเข้ากับโซลูชันของพวกเขาเอง และให้ลูกค้าปลายทาง มีที่ติดต่อเดียว สำหรับการจัดซื้อ การเรียกเก็บเงิน และการสนับสนุน

ถ้าคุณกำลังสนใจจัดหา Power BI ควบคู่ไปกับการสมัครใช้งาน Office 365 เราขอแนะนำให้ติดต่อกับคู่ค้าของคุณ ถ้าคู่ค้าของคุณไม่มี Power BI ให้บริการ คุณมีทางเลือกหลายทางให้พิจารณา

1. คุณจะสามารถซื้อบริการนี้จากช่องทางอื่น ไม่ว่าจาก Microsoft โดยตรง หรือจากอีกคู่ค้าหนึ่ง ทางเลือกนี้ อาจไม่มีให้กับลูกค้าได้ทุกกลุ่ม ขึ้นอยู่กับความสัมพันธ์ของพวกเขากับคู่ค้า คุณสามารถตรวจสอบได้ โดยไปที่**พอร์ทัลผู้ดูแลระบบของ Office 365** > **เรียกเก็บเงิน** > **สมัครใช้งาน** ถ้าคุณเห็น**สมัครใช้งาน** คุณสามารถขอรับบริการจาก Microsoft โดยตรง หรือไม่ก็ติดต่อคู่ค้าอื่นที่นำเสนอ Power BI
   
    ![](media/service-admin-syndication-partner/billingsub.png)
2. ถ้าคุณไม่เห็น**สมัครใช้งาน** แสดงอยู่ภายใต้**เรียกเก็บเงิน** แสดงว่าคุณไม่สามารถซื้อจาก Microsoft โดยตรงหรือผ่านคู่ค้าอื่นได้ 
   
   ![](media/service-admin-syndication-partner/billing.png)

ถ้าคุณไม่สามารถซื้อ Power BI โดยตรง และขึ้นอยู่กับชนิดของการสมัครใช้งาน Power BI ที่คุณสนใจ คุณยังคงมีตัวเลือกบางอย่าง

[Power BI (ฟรี)](#power-bi-free)

[Power BI Pro และ Premium](#power-bi-pro)

## <a name="power-bi-free"></a>Power BI (ฟรี)
ถ้าคุณพอใจกับข้อเสนอแบบฟรีสำหรับ Power BI คุณสามารถลงทะเบียนสำหรับบริการฟรี ตามค่าเริ่มต้น แต่ละลงชื่อสมัครใช้งานรายบุคคล หรือที่เรียกว่าการสมัครแบบเฉพาะกิจ (ad-hoc) จะถูกปิดไม่ให้ใช้งาน เมื่อคุณพยายามลงทะเบียนกับ Power BI คุณจะเห็นข้อความที่ระบุว่า แผนก IT ของคุณได้ปิดการลงทะเบียนสำหรับ Microsoft Power BI

    Your IT department has turned off signup for Microsoft Power BI.

![](media/service-admin-syndication-partner/sorry.png)

ถ้าต้องการเปิดให้สมัครใช้งานเฉพาะกิจ คุณต้องติดต่อกับคู่ค้าของคุณและขอให้เขาเปิดให้ใช้งาน ถ้าคุณเป็นผู้ดูแลระบบผู้เช่าของคุณ และทราบวิธีการใช้คำสั่ง Azure Active Directory ใน PowerShell คุณสามารถเปิดใช้งานการสมัครใช้เฉพาะกิจด้วยตัวคุณเอง [ศึกษาเพิ่มเติม](https://technet.microsoft.com/library/jj151815.aspx)

1. คุณจำเป็นต้อง ลงชื่อเข้าใช้ Azure Active Directory โดยใช้ข้อมูลประจำตัว Office 365 ของคุณ บรรทัดแรกจะถามข้อมูลประจำตัวของคุณ บรรทัดสองจะเชื่อมต่อกับ Azure Active Directory
   
        $msolcred = get-credential
        connect-msolservice -credential $msolcred
   
    ![](media/service-admin-syndication-partner/aad-signin.png)
2. ทันทีที่คุณลงชื่อเข้าใช้แล้ว คุณสามารถใช้คำสั่งต่อไปนี้เพื่อเปิดให้ลงทะเบียนเข้าใช้ฟรี
   
        Set-MsolCompanySettings -AllowAdHocSubscriptions $true

## <a name="power-bi-pro-and-premium"></a>Power BI Pro และ Premium
ถ้าคุณต้องการสมัครใช้งาน Power BI Pro หรือ Power BI Premium คุณกับคู่ค้าของคุณจะต้องพิจารณาทางเลือกต่าง ๆ ด้วยกัน

* คู่ค้าของคุณตกลงที่จะเพิ่ม Power BI ลงในรายการผลิตภัฑณฑ์ของพวกเขาเพื่อให้คุณสามารถซื้อจากพวกเขาได้
* คู่ค้าของคุณสามารถเปลี่ยนรูปแบบของคุณให้สามารถซื้อ Power BI โดยตรงจาก Microsoft หรือคู่ค้าอื่นที่มี Power BI ได้

วิดีโอนี้ อธิบายรูปแบบ syndication ของ Office 365 และการซื้อ Power BI:

<iframe width="560" height="315" src="https://www.youtube.com/embed/C357phT94A8" frameborder="0" allowfullscreen></iframe>

## <a name="next-steps"></a>ขั้นตอนถัดไป
[จัดการ Azure AD ด้วย Windows PowerShell](https://technet.microsoft.com/library/jj151815.aspx)  
[Power BI Premium - มันคืออะไร?](service-premium.md)

ถ้าคุณมีคำถามเพิ่มเติม [ลองถามชุมชน Power BI](http://community.powerbi.com/)


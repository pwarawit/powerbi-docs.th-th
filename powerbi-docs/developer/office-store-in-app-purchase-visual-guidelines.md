---
title: อาจจำเป็นต้องซื้อเพิ่ม - คำแนะนำการใช้วิชวล Power BI
description: เรียนรู้วิธีที่คุณสามารถเผยแพร่วิชวลแบบกำหนดเองของคุณไปยัง AppSource เพื่อให้บุคคลอื่นสามารถค้นหาและใช้งานผ่านการซื้อได้
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/26/2018
ms.openlocfilehash: 9ef7890c6f80845a9e6d1bd02e35778ed866ff54
ms.sourcegitcommit: 35d763dfc75c229204d36fd8b35c1e860786b707
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/27/2018
ms.locfileid: "52332220"
---
# <a name="guidelines-for-power-bi-visuals-with-additional-purchases"></a>คำแนะนำการใช้วิชวลของ Power BI ที่มีการซื้อเพิ่มเติม

จนกระทั่งเมื่อไม่นานมานี้ **Marketplace (AppSource)** ยอมรับเฉพาะวิชวล Power BI ที่ฟรีเท่านั้น นโยบายนี้มีการเปลี่ยนแปลงโดยที่วิชวลที่มีแท็กราคา "อาจจำเป็นต้องซื้อเพิ่ม" จะถูกส่งไปยัง **AppSource** วิชวลที่อาจจำเป็นต้องซื้อเพิ่มเติมมีลักษณะคล้ายกับ Add-in ที่ซื้อเพิ่มภายในแอป (IAP) ในร้านสำนักงาน นักพัฒนาสามารถส่งวิชวลเหล่านี้เพื่อขอการรับรองหลังจากทีมงาน **AppSource** อนุมัติและหลังจากตรวจสอบให้แน่ใจว่าสอดคล้องกับข้อกำหนดการรับรองตามที่อธิบายไว้ใน [บทความวิชวลแบบกำหนดเองที่ผ่านการรับรอง](../power-bi-custom-visuals-certified.md)

> [!Note]
> สำหรับวิชวลที่ผ่านการรับรอง จะต้องไม่เข้าถึงบริการหรือแหล่งข้อมูลภายนอก

## <a name="whats-changing-in-the-submission-process"></a>มีอะไรเปลี่ยนแปลงในกระบวนการส่งหรือไม่

นักพัฒนาอัปโหลดวิชวล IAP ไปยัง AppSource ผ่านหน้าแดชบอร์ดของผู้ขายตามที่ได้กำหนดไว้สำหรับวิชวลฟรี เพื่อแสดงให้เห็นว่าวิชวลที่ส่งมามีคุณลักษณะ IAP นักพัฒนาควรเขียนไว้ในบันทึกย่อบนแดชบอร์ดผู้ขายว่า: "วิชวลที่มีการซื้อเพิ่มภายในแอป" นอกจากนี้นักพัฒนาจำเป็นต้องแจ้งคีย์ใบอนุญาตและโทเค็นเพื่อให้ทีมงานตรวจสอบสามารถตรวจสอบคุณลักษณะ IAP ได้ เมื่อวิชวลได้รับการตรวจสอบและอนุมัติแล้ว การลงรายการ AppSource สำหรับวิชวล IAP จะระบุว่า 'อาจจำเป็นต้องซื้อเพิ่ม' ภายใต้ตัวเลือกการกำหนดราคา

## <a name="what-is-a-power-bi-visual-with-iap-features"></a>วิชวล Power BI ที่มีคุณลักษณะ IAP คืออะไร?

วิชวล IAP เป็นวิชวลที่ไม่เสียค่าใช้จ่ายและเสนอคุณลักษณะฟรี แต่ยังมีคุณลักษณะเพิ่มเติมซึ่งอาจมีการเรียกเก็บเงินเพิ่มเติมเพื่อให้สามารถใช้งานได้ นักพัฒนาต้องแจ้งผู้ใช้ในคำอธิบายของวิชวลเกี่ยวกับคุณลักษณะที่ต้องซื้อเพิ่มเติมเพื่อใช้งาน ปัจจุบัน Microsoft ไม่ได้มี application programming interfaces (APIs) แบบเนทีฟเพื่อสนับสนุนการซื้อเพิ่มภายในแอปและ Add-ins นักพัฒนาอาจใช้ระบบการชำระเงินอื่นสำหรับการซื้อเหล่านั้น ดูที่ [นโยบาย](https://docs.microsoft.com/office/dev/store/validation-policies#2-apps-or-add-ins-can-display-certain-ads) ของร้านค้าของเรา

## <a name="logo-guidelines"></a>หลักเกณฑ์เกี่ยวกับโลโก้

ส่วนนี้จะอธิบายข้อกำหนดสำหรับการเพิ่มโลโก้และรูปแบบโลโก้ในวิชวล

> [!NOTE]
> โลโก้สามารถใช้ได้เฉพาะในโหมดแก้ไขเท่านั้น โลโก้ไม่สามารถแสดงในโหมดมุมมองได้

![คำนิยาม](media/office-store-in-app-purchase-visual-guidelines/definitions.png)

![things-to-keep](media/office-store-in-app-purchase-visual-guidelines/things-to-keep-in-mind.png)

![things-to](media/office-store-in-app-purchase-visual-guidelines/things-to-avoid.png)

![size-and-format ](media/office-store-in-app-purchase-visual-guidelines/size-and-format.png)

![margins-and](media/office-store-in-app-purchase-visual-guidelines/margins-and-sizes.png)

![edit-mode](media/office-store-in-app-purchase-visual-guidelines/logos-in-edit-mode.png)

## <a name="best-practices"></a>แนวทางปฏิบัติที่ดีที่สุด

### <a name="visual-landing-page"></a>หน้าเริ่มต้นของวิชวล

ใช้หน้าเริ่มต้นเพื่อชี้แจงให้ผู้ใช้ทราบพวกเขาสามารถใช้วิชวลของคุณได้อย่างไรและสามารถซื้อใบอนุญาตได้ที่ไหน อย่าใส่วิดีโอที่เรียกใช้งานโดยอัตโนมัติ เพิ่มเฉพาะเนื้อหาที่ช่วยปรับปรุงประสบการณ์ของผู้ใช้ เช่น ข้อมูลหรือลิงก์เกี่ยวกับรายละเอียดการซื้อใบอนุญาตและวิธีใช้คุณลักษณะ IAP เท่านั้น

### <a name="license-key-and-token"></a>คีย์ใบอนุญาตและโทเค็น

เพื่อความสะดวกของผู้ใช้ เพิ่มคีย์ใบอนุญาตหรือโทเค็นที่เกี่ยวข้องกับเขตข้อมูลที่ด้านบนของบานหน้าต่างการจัดรูปแบบ เพื่อให้ผู้ใช้สามารถค้นหาได้ง่ายขึ้น

## <a name="next-steps"></a>ขั้นตอนถัดไป

เรียนรู้วิธีที่คุณสามารถเผยแพร่วิชวลแบบกำหนดเองของคุณไปยัง [AppSource](office-store.md) เพื่อให้บุคคลอื่นสามารถค้นหาและใช้งาน

---
title: วิธีการแชร์งานของคุณใน Power BI
description: ใน Power BI คุณสามารถทำงานร่วมกัน และแชร์แดชบอร์ด รายงาน ไทล์ และแอป ด้วยวิธีต่าง ๆ กัน แต่ละวิธีมีข้อดีของมันเอง
author: maggiesMSFT
ms.author: maggies
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/12/2020
LocalizationGroup: Share your work
ms.openlocfilehash: c71467a279ed3a2304d6af82f7493dac97425c4f
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83348102"
---
# <a name="ways-to-share-your-work-in-power-bi"></a>วิธีการแชร์งานของคุณใน Power BI

คุณได้สร้างแดชบอร์ดและรายงานแล้ว คุณอาจอยากทำงานร่วมกับเพื่อนร่วมงานของคุณด้วย ตอนนี้ คุณต้องการให้ผู้อื่นมีสิทธิ์เข้าถึง อะไรคือวิธีดีที่สุดในการแจกจ่ายสิทธิ์นั้น? ในบทความนี้ เราจะเปรียบเทียบตัวเลือกสำหรับการทำงานร่วมกัน และการแชร์ใน Power BI เหล่านี้:

* ทำงานร่วมกับเพื่อนร่วมงานเพื่อสร้างรายงานและแดชบอร์ดที่มีความหมาย ใน*พื้นที่ทำงาน*
* รวมแดชบอร์ดและรายงานเหล่านั้นลงใน*แอป* และแจกจ่ายกับกลุ่มที่ใหญ่ขึ้นหรือทั้งองค์กรของคุณ
* สร้าง*ชุดข้อมูลที่แชร์*ที่เพื่อนร่วมงานของคุณสามารถใช้เป็นเกณฑ์สำหรับรายงานของตนในพื้นที่ทำงานของตน
* แชร์แดชบอร์ดหรือรายงานกับบางคน จากบริการหรือแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
* ใส่คำอธิบายประกอบและแชร์จากแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
* ฝังรายงานใน Microsoft Teams
* พิมพ์รายงาน
* *ฝัง*รายงานในพอร์ทัลที่ปลอดภัยหรือเว็บไซต์สาธารณะ
* สร้าง*แอปเทมเพลต*ที่คุณสามารถแจกจ่ายให้กับผู้ใช้ Power BI ภายนอกผ่านทาง Microsoft AppSource

ไม่ว่าคุณจะเลือกตัวเลือกไหนเพื่อแชร์เนื้อหาของคุณ คุณต้องมี[สิทธิ์การใช้งาน Power BI Pro](../fundamentals/service-features-license-type.md) หรือเนื้อหาจำเป็นต้องอยู่ใน[ความจุพรีเมียม](../admin/service-premium-what-is.md) ข้อกำหนดสิทธิ์การใช้งานสำหรับผู้ร่วมงานที่จะดูเนื้อหาของคุณ จะแตกต่างกันไป ขึ้นอยู่กับตัวเลือกที่คุณเลือก ส่วนต่อไปนี้คือรายละเอียด 

![แอปในบริการของ Power BI](media/service-how-to-collaborate-distribute-dashboards-reports/power-bi-apps-new-look.png)

*แอปในบริการของ Power BI*

## <a name="collaborate-in-a-workspace"></a>ทำงานร่วมกันในพื้นที่ทำงาน

เมื่อทีมทำงานร่วมกัน พวกเขาต้องเข้าถึงเอกสารเดียวกันเพื่อให้สามารถร่วมมือกันได้อย่างรวดเร็ว ในพื้นที่ทำงาน Power BI ทีมมาร่วมกันเพื่อแชร์ความเป็นเจ้าของและการจัดการแดชบอร์ด รายงาน ชุดข้อมูล และเวิร์กบุ๊ก ในบางครั้ง ผู้ใช้ Power BI จัดระเบียบพื้นที่ทำงานของพวกเขาโดยยึดตามโครงสร้างองค์กร แต่บางครั้งพวกเขาสร้างพื้นที่ทำงานสำหรับโครงการเฉพาะ องค์กรอื่นๆ ยังคงใช้หลายพื้นที่ทำงานเพื่อจัดเก็บรายงานหรือแดชบอร์ดเวอร์ชั่นอื่นที่พวกเขาใช้ 

พื้นที่ทำงานให้บทบาทที่กำหนดว่าเพื่อนร่วมงานของคุณมีสิทธิ์ใด คุณสามารถใช้บทบาทเหล่านั้นกำหนดว่าใครสามารถจัดการพื้นที่ทำงานทั้งหมด หรือแก้ไขเนื้อหาและแจกจ่ายเนื้อหา

![พื้นที่ทำงาน](media/service-how-to-collaborate-distribute-dashboards-reports/power-bi-workspace.png)

คุณอาจใส่เนื้อหาในพื้นที่ทำงานของฉันและแชร์พื้นที่ทำงานจากส่วนนั้น แต่พื้นที่ทำงานเป็นการทำงานร่วมกันที่ดีกว่าพื้นที่ทำงานของฉันเนื่องจากให้ความเป็นเจ้าของร่วมในเนื้อหา คุณและทีมของคุณทั้งหมดสามารถอับเดตหรือ หรือให้ผู้อื่นเข้าถึงได้ง่าย พื้นที่ทำงานของฉันถูกใช้ โดยบุคคลต่างๆ เพียงครั้งเดียวหรือเพื่อเนื้อหาส่วนบุคคล

มาลองจินตนาการว่าคุณสร้างแดชบอร์ดที่คุณจำเป็นต้องใช้ร่วมกับเพื่อนร่วมงานของคุณเสร็จแล้ว วิธีที่ดีที่สุดในการให้พวกเขาสามารถเข้าถึงแดชบอร์ดคืออะไร? คำตอบขึ้นอยู่กับหลายปัจจัย 

- ถ้าเพื่อนร่วมงานต้องการอัปเดตแดชบอร์ดอย่างต่อเนื่อง หรือต้องการเข้าถึงเนื้อหาทั้งหมดในพื้นที่ทำงาน ให้เพิ่มเข้าไปในพื้นที่ทำงาน 
- ถ้าเพื่อนร่วมงานเพียงต้องดูแดชบอร์ดนั้นและไม่ใช่เนื้อหาทั้งหมดในพื้นที่ทำงาน คุณสามารถเลือกตัวเลือกได้ ถ้าบางคนต้องการเพียงหนึ่งแดชบอร์ด การแชร์แดชบอร์ดนั้นจะเป็นโซลูชันที่ดีที่สุด
- อย่างไรก็ตาม ถ้าแดชบอร์ดเป็นส่วนหนึ่งของชุดเนื้อหาที่ใหญ่กว่าที่คุณต้องแจกจ่ายให้กับเพื่อนร่วมงานหลายคน การเผยแพร่*แอป*น่าจะเป็นตัวเลือกที่ดีที่สุด

Power BI มีประสบการณ์การใช้งานพื้นที่ทำงานใหม่ อ่าน[สร้างพื้นที่ทำงานใหม่](service-create-the-new-workspaces.md)เพื่อดูวิธีการเปลี่ยนแปลงพื้นที่ทำงาน 

## <a name="distribute-insights-in-an-app"></a>แจกจ่ายข้อมูลเชิงลึกในแอป

สมมุติว่า คุณต้องการแจกจ่ายแดชบอร์ดของคุณให้กับผู้ชมในองค์กรของคุณ คุณและเพื่อนร่วมงานของคุณได้สร้าง*พื้นที่ทำงาน* จากนั้นจึงได้สร้างและกำหนดแดชบอร์ด รายงาน และชุดข้อมูลในพื้นที่ทำงาน ในตอนนี้ คุณเลือกแดชบอร์ดและรายงานที่คุณต้องการ และเผยแพร่เป็นแอปไปยังกลุ่มหนึ่งหรือทั่วทั้งองค์กรของคุณ

![ไอคอนเผยแพร่แอป](media/service-how-to-collaborate-distribute-dashboards-reports/power-bi-publish-app.png)

สามารถค้นหาและติดตั้งแอปได้ง่าย ๆ ในบริการของ Power BI ([https://app.powerbi.com](https://app.powerbi.com)) คุณสามารถส่งลิงก์โดยตรงไปยังแอป ให้กับผู้ใช้ทางธุรกิจ หรือพวกเขาสามารถค้นหาได้ใน AppSource ถ้าผู้ดูแลระบบ Power BI ของคุณ ให้สิทธิ์แก่คุณ คุณสามารถติดตั้งแอปลงในบัญชีผู้ใช้ Power BI ของเพื่อนร่วมงานคุณโดยอัตโนมัติ อ่านเพิ่มเติมเกี่ยวกับ[การเผยแพร่แอปของคุณ](service-create-distribute-apps.md)

หลังจากที่พวกเขาติดตั้งแอปแล้ว พวกเขาสามารถดูแอปในเบราว์เซอร์หรืออุปกรณ์เคลื่อนที่ของพวกเขา

สำหรับผู้ใช้ที่จะดูแอปของคุณ พวกเขาจำเป็นต้องมีสิทธิ์การใช้งาน Power BI Pro ด้วย หรือแอปต้องเก็บไว้ในความจุ Power BI Premium อ่าน[Power BI Premium คืออะไร](../admin/service-premium-what-is.md)สำหรับรายละเอียด

คุณสามารถเผยแพร่แอปไปยังบุคคลภายนอกองค์กรของคุณได้เช่นกัน พวกเขาสามารถดูและโต้ตอบกับเนื้อหาแอป แต่ไม่สามารถแชร์แอปกับผู้อื่นได้ ตอนนี้ คุณสามารถสร้าง*แอปเทมเพลม* ปรับใช้กับลูกค้า Power BI

## <a name="share-a-dataset"></a>แชร์ชุดข้อมูล

ต้องยอมรับว่า บางคนมีทักษะมากกว่าในการสร้างรูปแบบข้อมูลคุณภาพสูง ออกแบบมาอย่างดีในรายงานของตน คุณอาจจะเป็นบุคคลนั้นก็ได้ ทั้งองค์กรของคุณสามารถใช้ประโยชน์จากการใช้รูปแบบข้อมูลที่ออกแบบมาอย่างดีเดียวกัน *ชุดข้อมูลที่แชร์*จะเติมบทบาทนั้น เมื่อคุณสร้างรายงานด้วยรูปแบบข้อมูลที่ทุกคนควรใช้ คุณสามารถบันทึกรายงานดังกล่าวไปยังบริการของ Power BI และให้สิทธิ์การใช้กับบุคคลเหมาะสม จากนั้น พวกเขาสามารถสร้างรายงานของตนบนชุดข้อมูลของคุณได้ ด้วยวิธีดังกล่าว ทุกคนจะยึดรายงานของตนด้วยข้อมูลเดียวกัน และมองเห็น "ความจริง" ในทิศทางเดียวกัน

![ค้นหาชุดข้อมูลที่ใช้ร่วมกัน](media/service-how-to-collaborate-distribute-dashboards-reports/power-bi-shared-datasets.png)

อ่านเพิ่มเติมเกี่ยวกับ[การสร้างและการใช้ชุดข้อมูลที่แชร์](../connect-data/service-datasets-across-workspaces.md)

## <a name="share-dashboards-and-reports"></a>แชร์แดชบอร์ดและรายงาน

สมมติว่า คุณสร้างแดชบอร์ดและรายงานในพื้นที่ทำงานของฉันหรือในพื้นที่ทำงานเสร็จสมบูรณ์แล้ว และคุณต้องการให้บางคนสามารถเข้าถึงได้ วิธีหนึ่งคือการ*แชร์*ให้พวกเขา 

![แชร์รายงาน](media/service-how-to-collaborate-distribute-dashboards-reports/power-bi-share-report.png)

คุณต้องมีสิทธิ์การใช้งาน Power BI Pro เพื่อแชร์เนื้อหาของคุณ และบุคคลที่คุณแชร์ด้วยก็ต้องมีสิทธิ์ดังกล่าวเช่นกัน หรือเนื้อหาจำเป็นต้องอยู่ในพื้นที่ทำงานใน[ความจุ Premium](../admin/service-premium-what-is.md) เมื่อคุณแชร์แดชบอร์ดหรือรายงาน ผู้รับสามารถดู และโต้ตอบกับข้อมูล แต่ไม่สามารถแก้ไขได้ พวกเขาจะเห็นข้อมูลเดียวกันกับที่คุณเห็นในแดชบอร์ดและรายงาน นอกจากว่าจะมีความปลอดภัยระดับแถว (RLS) ใช้กับชุดข้อมูลพื้นฐาน เพื่อนร่วมงานที่คุณแชร์ด้วย สามารถแชร์ต่อไปให้เพื่อนร่วมงานของพวกเขาอีกที ถ้าคุณอนุญาต 

คุณสามารถแชร์ให้กับบุคคลภายนอกองค์กรได้ด้วย พวกเขาสามารถดู และโต้ตอบกับแดชบอร์ด หรือรายงานได้ แต่ไม่สามารถแชร์ได้ 

อ่านเพิ่มเติมเกี่ยวกับ[การแชร์แดชบอร์ดและรายงาน](service-share-dashboards.md)จากบริการของ Power BI คุณยังสามารถเพิ่มตัวกรองเข้ากับลิงก์ และ[แชร์มุมมองที่กรองแล้วของรายงานคุณ](service-share-reports.md)ได้

## <a name="annotate-and-share-from-the-power-bi-mobile-apps"></a>ใส่คำอธิบายประกอบ และแชร์จากแอป Power BI สำหรับอุปกรณ์เคลื่อนที่

ในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่ สำหรับ iOS และ Android คุณสามารถใส่คำอธิบายประกอบไทล์ รายงาน หรือ วิชวล แล้วแชร์ให้กับใครก็ได้ผ่านทางอีเมล

![ใส่คำอธิบายประกอบ และแชร์ในแอปสำหรับอุปกรณ์เคลื่อนที่](media/service-how-to-collaborate-distribute-dashboards-reports/power-bi-iphone-annotate.png)

คุณกำลังแชร์สแนปช็อตของไทล์ รายงาน หรือ วิชวล และผู้รับของคุณจะเห็นเหมือนกับตอนที่คุณส่งเมล เมลยังมีลิงก์ไปยังแดชบอร์ดหรือรายงาน ถ้าพวกเขามีสิทธิ์การใช้งาน Power BI Pro หรือเนื้อหาอยู่ใน[ความจุพรีเมียม](../admin/service-premium-what-is.md) และคุณได้แชร์วัตถุกับพวกเขาแล้ว พวกเขาสามารถเปิดดูได้ คุณสามารถส่งสแนปช็อตของไทล์ให้กับใครก็ได้ &#151; ไม่เพียงแต่ผู้ร่วมงานในโดเมนอีเมลเดียวกันเท่านั้น

อ่านเพิ่มเติมเกี่ยวกับ[การใส่คำอธิบายประกอบ และการแชร์ไทล์ รายงาน และวิชวล](../consumer/mobile/mobile-annotate-and-share-a-tile-from-the-mobile-apps.md)จากแอปสำหรับอุปกรณ์เคลื่อนที่ Android และ iOS

คุณยังสามารถ[แชร์สแนปช็อตของไทล์](../consumer/mobile/mobile-windows-10-phone-app-get-started.md)จากแอป Power BI สำหรับอุปกรณ์ที่ Windows 10 ได้

## <a name="embed-a-report-in-microsoft-teams"></a>ฝังรายงานใน Microsoft Teams

เพิ่มการทำงานร่วมกันซึ่งขับเคลื่อนด้วยข้อมูลในองค์กรของคุณโดยการฝังรายงาน Power BI และรายงาน Power BI ที่ระบุหมายเลขหน้าใน Microsoft Teams คุณสามารถเพิ่มแท็บ Power BI แยกต่างหากสำหรับรายงานแต่ละรายการ และกำหนดชื่อรายงานหรือชื่ออื่น ๆ ให้แต่ละแท็บ เพื่อนร่วมงานของคุณสามารถดูรายงานของคุณได้ในแท็บ Power BI ใน Teams นอกจากนี้ พวกเขายังสามารถเปิดหน้าต่างการสนทนาและข้อคิดเห็นบนรายงานใน Teams โดยตรงได้ อ่านข้อมูลเพิ่มเติมเกี่ยวกับ [การฝังรายงานใน Microsoft Teams](service-embed-report-microsoft-teams.md)

## <a name="print-or-save-as-pdf-or-other-static-file"></a>พิมพ์ หรือบันทึกเป็น PDF หรือไฟล์แบบคงที่อื่น ๆ

คุณสามารถพิมพ์ หรือบันทึกเป็น PDF (หรือรูปแบบไฟล์แบบคงที่อื่น ๆ) สำหรับทั้งแดชบอร์ด ไทล์แดชบอร์ด หน้ารายงาน หรือการแสดงภาพจากบริการของ Power BI รายงานสามารถพิมพ์ออกมาหนึ่งหน้าในแต่ละครั้งเท่านั้น คุณไม่สามารถพิมพ์รายงานทั้งหมดในครั้งเดียว อ่านเพิ่มเติมเกี่ยวกับ[การพิมพ์ หรือการบันทึกเป็นไฟล์แบบคงที่](../consumer/end-user-print.md)

## <a name="embed-reports-in-secure-portals-or-public-web-sites"></a>ฝังรายงานในพอร์ทัลที่ปลอดภัยหรือเว็บไซต์สาธารณะ

### <a name="embed-in-secure-portals"></a>ฝังในพอร์ทัลที่ปลอดภัย

คุณสามารถฝังรายงาน Power BI ในพอร์ทัลหรือเว็บไซต์ที่ผู้ใช้ของคุณควรจะเห็นได้  
**การฝังใน SharePoint Online**  และตัวเลือก **แบบฝัง** ในบริการ Power BI ช่วยให้คุณสามารถฝังรายงานสำหรับผู้ใช้ภายในของคุณได้อย่างปลอดภัย 

- **ฝังใน SharePoint Online**ทำงานกับ Power BI web part สำหรับ SharePoint Online ซึ่งจะมอบประสบการณ์การลงชื่อเข้าระบบครั้งเดียวโดยมีการควบคุมวิธีการฝังรายงาน 
- **การฝัง**ทำงานร่วมกับพอร์ทัลหรือเว็บไซต์ใดก็ได้ที่รองรับเนื้อหาการฝังโดยใช้ URL หรือ iFrame 

ตัวเลือกใดที่คุณเลือก Power BI จะบังคับใช้สิทธิ์และความปลอดภัยของข้อมูลทั้งหมดก่อนที่ผู้ใช้จะสามารถดูเนื้อหาได้ ผู้ที่ดูรายงานนั้นจำเป็นต้องมีใบอนุญาตที่เหมาะสม เพิ่มเติมเกี่ยวกับ [การฝังใน SharePoint Online ](service-embed-report-spo.md) และตัวเลือก [ฝัง](service-embed-secure.md) ใน Power BI

### <a name="publish-to-public-web-sites"></a>เผยแพร่ไปยังเว็บไซต์สาธารณะ

ด้วยตัวเลือก **เผยแพร่สู่เว็บ** คุณสามารถเผยแพร่รายงาน Power BI ไปยังทั้งอินเทอร์เน็ต โดยการฝังตัวการแสดงภาพลงในบล็อกโพสต์ เว็บไซต์ สื่อทางสังคม และการสื่อสารทางออนไลน์อื่น ๆ บนอุปกรณ์ใดก็ได้ ทุกคนบนอินเทอร์เน็ตสามารถดูรายงานของคุณ และคุณไม่สามารถควบคุมว่าใครสามารถดูสิ่งที่คุณได้เผยแพร่แล้ว พวกเขาไม่จำเป็นต้องมีใบอนุญาต Power BI การเผยแพร่ไปยังเว็บ มีเฉพาะรายงานที่คุณสามารถแก้ไขได้เท่านั้น คุณไม่สามารถเผยแพร่รายงานไปยังเว็บ ถ้ารายงานถูกแชร์มาให้คุณ หรือ ถ้ารายงานอยู่ในแอป อ่านเพิ่มเติมเกี่ยวกับ[การเผยแพร่ไปยังเว็บ](service-publish-to-web.md)

>[!Warning]
>ใช้[เผยแพร่ไปยังเว็บ](service-publish-to-web.md)เท่านั้นเมื่อต้องแชร์เนื้อหาต่อสาธารณะ ไม่ใช่เพื่อการแชร์ภายใน

## <a name="create-and-deploy-template-apps"></a>สร้างและปรับใช้แอปเทมเพลต

*แอปเทมเพลต*ได้รับการออกแบบมาเพื่อเผยแพร่สู่สาธารณะ ส่วนใหญ่ใน Microsoft AppSource คุณสร้างแอป และมีการเข้ารหัสเพียงเล็กน้อยหรือไม่มีเลย คุณสามารถปรับใช้กับลูกค้า Power BI ได้ ลูกค้าของคุณเชื่อมต่อกับข้อมูลของตนเอง และสร้างอินสแตนซ์ของบัญชีของตนเอง อ่านเพิ่มเติมเกี่ยวกับ[แอปเทมเพลตของ Power BI](../connect-data/service-template-apps-overview.md)


## <a name="next-steps"></a>ขั้นตอนถัดไป

* [แชร์แดชบอร์ดกับเพื่อนร่วมงานและผู้อื่น](service-share-dashboards.md)
* [สร้างและเผยแพร่แอปใน Power BI](service-create-distribute-apps.md)
* [ฝังรายงานในพอร์ทัลความปลอดภัยหรือเว็บไซต์](service-embed-secure.md)

มีคำติชมหรือไม่ ไปที่[ไซต์ชุมชน Power BI](https://community.powerbi.com/) พร้อมกับคำแนะนำของคุณ

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)
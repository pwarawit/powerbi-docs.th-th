---
title: การบำรุงรักษาตามแผนของ Power BI
description: ข้อมูลสำหรับผู้ดูแลระบบเกี่ยวกับวิธีการวางแผนการบำรุงรักษาสำหรับ Power BI จะส่งผลต่อองค์กรของพวกเขาและขั้นตอนถัดไปที่พวกเขาอาจจำเป็นต้องดำเนินการ
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/19/2020
ms.author: kfollis
ms.custom: MC
ROBOTS: NOINDEX
LocalizationGroup: Admin
ms.openlocfilehash: 13bbf23c075fb1f58c2af71ae0a082d4e539d023
ms.sourcegitcommit: 2131f7b075390c12659c76df94a8108226db084c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/03/2020
ms.locfileid: "87537699"
---
# <a name="power-bi-planned-maintenance"></a>การบำรุงรักษาตามแผนของ Power BI

การบำรุงรักษาที่วางแผนไว้สำหรับบริการของ Power BI เป็นส่วนหนึ่งที่จำเป็นของความมุ่งมั่นของเราในการผลิตผลิตภัณฑ์ที่เชื่อถือได้ให้กับลูกค้าของเรา เมื่อเกิดการบำรุงรักษาตามแผนการบริการของ Power BI จะไม่สามารถใช้งานได้ในองค์กรของคุณเป็นเวลาชั่วขณะ ผู้ใช้อาจไม่สามารถเข้าถึงบริการของ Power BI ได้และการดำเนินการในพื้นหลังอาจไม่สำเร็จ หลังจากหน้าต่างการบำรุงรักษา เเราคาดหวังว่าบริการจะทำงานตามปกติและการดำเนินการทั้งแบบโต้ตอบและพื้นหลังจะประสบความสำเร็จ  

การบำรุงรักษาได้รับการวางแผนให้เกิดขึ้นนอกช่วงเวลาทำการปกติเพื่อช่วยลดผลกระทบใดๆ ก็ตามที่อาจะเกิดขึ้นกับองค์กรของคุณ สำหรับองค์กรที่มีผู้ใช้ทั่วโลก เรารู้ว่า "นอกช่วงเวลาทำการปกติ" อาจส่งผลกระทบต่อคุณแตกต่างกัน เราขออภัยสำหรับผลกระทบใดๆ ด็ตามที่เกิดขึ้นกับผู้ใช้ของคุณ เรากำลังทำงานอย่างหนักเพื่อปรับปรุง Power BI และปรับลดหน้าต่างการบำรุงรักษาเหล่านี้

หากองค์กรของคุณได้รับผลกระทบ เราจะแจ้งให้คุณทราบล่วงหน้า ผู้ดูแล Microsoft 365 จะเห็นการแจ้งเตือนล่วงหน้าในศูนย์ข้อความ Microsoft 365 และจะได้รับอีเมล นอกจากนี้ ลูกค้าด้วยสัญญาการสนับสนุน Premier จะได้รับการแจ้งเตือนผ่านทีมบัญชี Microsoft ของพวกเขา

## <a name="actions-to-take-now"></a>การดำเนินการที่จะใช้ในขณะนี้

* ผู้ดูแลระบบ Microsoft 365 ควร[ตรวจสอบศูนย์ข้อความ](https://admin.microsoft.com/Adminportal/Home#/MessageCenter) สำหรับข้อความเกี่ยวกับการบำรุงรักษาตามแผนไว้ของ Power BI แชร์ข้อความกับบุคคลที่ควรทราบแต่อาจไม่มีสิทธิ์ในการเข้าถึงศูนย์ข้อความ
* ถ้าคุณไม่ใช่ผู้ดูแลระบบ Microsoft 365 โปรดมีส่วนร่วมกับแผนกไอทีหรือทีมสนับสนุนภายในของคุณเพื่อถามเกี่ยวกับการบำรุงรักษาใดๆ ก็ตามที่กำลังจะเกิดขึ้น

## <a name="actions-to-take-when-maintenance-is-complete"></a>การดำเนินการที่จะดำเนินการเมื่อการบำรุงรักษาเสร็จสมบูรณ์

* ผู้ใช้ควรรีเฟรชหน้าต่างเบราว์เซอร์ที่เปิดอยู่
* ผู้ใช้แอป Power BI บนโทรศัพท์มือถือจะต้องตรวจสอบว่ามีการใช้แอปเวอร์ชันล่าสุดและต้องออกจากระบบแล้วลงชื่อกลับเข้าไปในแอปอีกครั้ง ตรวจสอบร้านค้าแอปของโทรศัพท์มือถือของคุณหรือตรวจสอบหน้า [Power BI สำหรับโทรศัพท์มือถือ](https://powerbi.microsoft.com/mobile/)ของเรา
* ลูกค้าที่มีการแก้ไขหรือเผยแพร่รายงานที่ใช้ภาพขององค์กรไม่ว่าจะอยู่ภายในเครื่องหรือจาก OneDrive และตำแหน่งที่ตั้งของ SharePoint จะต้องนำเข้าภาพผ่านทางที่จัดเก็บภาพขององค์กรหรือดาวน์โหลด .PBIX ที่อัปเดตแล้วก่อนเผยแพร่ สำหรับข้อมูลเพิ่มเติมเกี่ยวกับภาพขององค์กร ให้ดู[ภาพขององค์กร](organizational-visuals.md)
* หากเวิร์กบุ๊ก Excel ที่ใช้ฟีเจอร์วิเคราะห์ใน Excel ไม่ได้เฟรช คุณอาจต้องอัปเดตสตริงการเชื่อมต่อหรือดาวน์โหลดการเชื่อมต่อ ODC ใหม่สำหรับชุดข้อมูลนั้น โปรดดูที่[วิเคราะห์ใน Excel](../collaborate-share/service-analyze-in-excel.md#connect-to-power-bi-data) เพื่อศึกษาข้อมูลเพิ่มเติม
* ลิงก์ไปยัง Power BI embedded ในเนื้อหาอาจล้มเหลวในการเชื่อมต่อเมื่อการบำรุงรักษาเสร็จสมบูรณ์ ตัวอย่างเช่น ลิงก์แบบฝังตัวใน SharePoint หรือ Teams อาจส่งผลให้เกิดข้อผิดพลาดของผู้ใช้ ในการแก้ไขปัญหานี้ คุณต้องสร้างลิงก์แบบฝังตัวใหม่ใน Power BI จากนั้นอัปเดตตำแหน่งที่ใช้งานอยู่ สำหรับข้อมูลเพิ่มเติมเกี่ยวกับลิงก์แบบฝังตัว ให้ดู[ฝังส่วนเว็บรายงานใน SharePoint Online](../collaborate-share/service-embed-report-spo.md) และ[ ทำงานร่วมกันใน Microsoft Teams กับ Power BI ](../collaborate-share/service-collaborate-microsoft-teams.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [เปิดใช้งานการแจ้งเตือนการหยุดชะงักของบริการ](service-interruption-notifications.md)
* [ติดตามการเปลี่ยนแปลงที่กำลังจะเกิดขึ้นในศูนย์ข้อความ](https://docs.microsoft.com/microsoft-365/admin/manage/message-center?view=o365-worldwide)

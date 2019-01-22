---
title: แก้ไขปัญหาเมื่อเริ่มต้น Power BI Desktop
description: แก้ไขปัญหาเมื่อเริ่มต้น Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: f527fa17ab242f6835ca99a3ff3ef3e2525a001f
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54277146"
---
# <a name="resolve-issues-when-power-bi-desktop-will-not-launch"></a>แก้ไขปัญหาเมื่อ Power BI Desktop เปิดไม่ขึ้น
ใน**Power BI Desktop** ผู้ใช้ที่ติดตั้งและใช้งานเวอร์ชันก่อนหน้า **เกตเวย์ข้อมูลภายในองค์กร Power BI** สามารถถูกบล็อกจากการเปิดใช้งาน Power BI Desktop เนื่องจากนโยบายข้อจำกัดในระดับผู้ดูแลเกตเวย์ Power BI ภายในองค์กร ได้วางและตั้งชื่อไปป์บนเครื่อง 

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>แก้ไขปัญหาด้วยเกตเวย์ข้อมูลในองค์กรและ Power BI Desktop
มีสามตัวเลือกเพื่อแก้ไขปัญหาเกี่ยวข้องกับเกตเวย์ข้อมูลในองค์กร และเปิดใช้งาน Power BI Desktop

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>การแก้ปัญหาที่ 1: ติดตั้งเกตเวย์ข้อมูลภายในองค์กร Power BI เวอร์ชันล่าสุด
เกตเวย์ข้อมูลภายในองค์กร Power BI เวอร์ชันล่าสุดไม่จำกัดการตั้งชื่อไปป์บนเครื่องคอมพิวเตอร์ และอนุญาตให้ Power BI Desktop เพื่อเปิดใช้งานได้อย่างถูกต้อง ถ้าคุณจำเป็นต้องดำเนินต่อโดยใช้เกตเวย์ข้อมูลภายในองค์กร Power BI นี่คือวิธีแก้ไขแนะนำ คุณสามารถดาวน์โหลดเวอร์ชันล่าสุดของเกตเวย์ข้อมูลภายในองค์กร Power BI จาก[ตำแหน่งที่ตั้งนี้](https://go.microsoft.com/fwlink/?LinkId=698863)ได้ โปรดทราบว่า ลิงก์เป็นลิงก์ดาวน์โหลดโดยตรงเพื่อการดำเนินการติดตั้ง

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-windows-service"></a>การแก้ปัญหาที 2: ถอนการติดตั้งหรือหยุด Windows service ของเกตเวย์ข้อมูลองค์กร Power BI
ถ้าคุณไม่จำเป็นต้องใช้เกตเวย์ข้อมูลภายในองค์กร Power BI คุณสามารถถอนการติดตั้ง หรือคุณสามารถหยุด Windows service ของเกตเวย์ข้อมูลองค์กร Power BI ซึ่งจะลบข้อจำกัดนโยบาย และอนุญาตให้ Power BI Desktop ทำงาน

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>การแก้ปัญหาที่ 3: เรียกใช้ Power BI Desktop กับสิทธิ์ผู้ดูแลระบบ
อีกวิธีหนึ่งคือ คุณสามารถเปิดใช้ Power BI Desktop แบบผู้ดูแล ซึ่งอนุญาตให้ Power BI Desktop เปิดใช้งานอย่างเรียบร้อย ยังคงแนะนำให้คุณติดตั้งเวอร์ชันล่าสุดของเกตเวย์ข้อมูลภายในองค์กร Power BI ตามที่อธิบายไว้ก่อนหน้าในบทความนี้

สิ่งสำคัญคือต้องทราบว่า Power BI Desktop ได้รับการออกแบบเป็นสถาปัตยกรรมแบบหลายกระบวนการ และกระบวนการต่างๆ เหล่านี้สื่อสารโดยใช้เนมไปป์ Windows อาจมีกระบวนการอื่นที่รบกวนเนมไปป์เหล่านั้น สาเหตุที่พบได้บ่อยที่สุดสำหรับการรบกวนดังกล่าวคือ ความปลอดภัย รวมถึงสถานการณ์ที่ซอฟต์แวร์ป้องกันไวรัส หรือไฟร์วอลล์อาจบล็อกไปป์ หรือเปลี่ยนเส้นทางปริมาณการใช้งานไปยังพอร์ตเฉพาะ การเปิดใช้งาน Power BI Desktop ด้วยสิทธิ์ของผู้ดูแลระบบอาจแก้ปัญหาดังกล่าว ถ้าไม่สามารถเปิดการใช้งานด้วยสิทธิ์ของผู้ดูแลได้ ให้ติดต่อผู้ดูแลระบบของคุณเพื่อพิจารณาว่ามีการใช้กฎความปลอดภัยใดที่ป้องกันไม่ให้เนมไปป์สื่อสารได้อย่างถูกต้อง และอนุญาต Power BI Desktop และกระบวนการย่อยที่เกี่ยวข้อง

## <a name="resolve-issues-when-connecting-to-sql-server"></a>แก้ไขปัญหาเมื่อเชื่อมต่อกับ SQL Server
ถ้าคุณพบข้อผิดพลาดที่คล้ายกับข้อผิดพลาดต่อไปนี้ เมื่อเชื่อมต่อกับฐานข้อมูล SQL Server คุณมักจะสามารถแก้ไขปัญหาได้ด้วยการเปิดใช้งาน **Power BI Desktop** ในฐานะเป็นผู้ดูแล จากนั้นทำการเชื่อมต่อ SQL Server:

    "An error happened while reading data from the provider: 'Could not load file or assembly 'System.EnterpriseServices, Version=4.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxx' or one of its dependencies. Either a required impersonation level was not provided, or the provided impersonation level is invalid. (Exception from HRESULT: 0x80070542)'"

หลังจากเรียกใช้ในฐานะเป็นผู้ดูแลระบบและสร้างการเชื่อมต่อดังกล่าว DLL ที่จำเป็นต้องมีได้รับการลงทะเบียนอย่างถูกต้อง หลังจากนั้น การเรียกใช้ Power BI Desktop ในฐานะเป็นผู้ดูแลระบบก็ไม่จำเป็นอีกต่อไป

## <a name="help-with-other-issues-when-launching-power-bi-desktop"></a>ความช่วยเหลือปัญหาอื่น ๆ เมื่อเปิดใช้ Power BI Desktop
เราจะมุ่งมั่นที่จะครอบคลุมปัญหาที่เกิดขึ้นกับ**Power BI Desktop**ให้มากที่สุด เราดูปัญหาที่อาจจะมีผลกระทบต่อลูกค้าเป็นประจำ และรวมเอาไว้ในบทความของเรา

ถ้าปัญหาเกี่ยวกับการเปิดใช้งาน **Power BI Desktop** จะไม่เชื่อมโยงกับเกตเวย์ข้อมูลในองค์กร หรือเมื่อการแก้ปัญหาก่อนหน้านี้ใช้ไม่ได้ผล คุณสามารถส่งเรื่องไปยัง [ฝ่ายสนับสนุน Power BI](https://support.powerbi.com) (https://support.powerbi.com) เพื่อช่วยระบุและแก้ไขปัญหาของคุณ

สำหรับปัญหาอื่นๆ ที่คุณอาจพบได้ในอนาคตกับ**Power BI Desktop** (เราหวังว่าจะไม่มน้อยที่สุด) จะเป็นประโยชน์มากเมื่อต้องการเปิดใช้งานการติดตาม และรวบรวมไฟล์บันทึก ที่จะแยกและระบุปัญหาได้ได้ดียิ่งขึ้น เมื่อต้องการเปิดใช้งานการติดตาม ให้เลือก**ไฟล์ > ตัวเลือกและการตั้งค่า > ตัวเลือก**แล้วเลือก**การวินิจฉัย**จากนั้น ตรวจสอบ**เปิดใช้งานการติดตาม**ภายใต้*ตัวเลือกการวินิจฉัย* เราตระหนัก**Power BI Desktop**ต้องเรียกใช้การตั้งค่าตัวเลือกนี้ ซึ่งจะเป็นประโยชน์มากสำหรับปัญหาที่เกี่ยวข้องกับการเปิดใช้งาน **Power BI Desktop** ในอนาคต


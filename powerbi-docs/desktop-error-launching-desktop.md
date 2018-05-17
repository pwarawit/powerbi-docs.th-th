---
title: แก้ไขปัญหาเมื่อเริ่มต้น Power BI Desktop
description: แก้ไขปัญหาเมื่อเริ่มต้น Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 43263afb63fa0350a240cae602f4a2acf8ef8edd
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/12/2018
---
# <a name="resolve-issues-when-power-bi-desktop-will-not-launch"></a>แก้ไขปัญหาเมื่อ Power BI Desktop เปิดไม่ขึ้น
ใน**Power BI Desktop** ผู้ใช้ที่ติดตั้งและใช้งานเวอร์ชันก่อนหน้า **เกตเวย์ข้อมูลภายในองค์กร Power BI** สามารถถูกบล็อกจากการเปิดใช้งาน Power BI Desktop เนื่องจากนโยบายข้อจำกัดในระดับผู้ดูแลเกตเวย์ Power BI ภายในองค์กร ได้วางและตั้งชื่อไปป์บนเครื่อง 

## <a name="resolve-issues-with-the-on-premises-data-gateway-and-power-bi-desktop"></a>แก้ไขปัญหาด้วยเกตเวย์ข้อมูลในองค์กรและ Power BI Desktop
มีสามตัวเลือกเพื่อแก้ไขปัญหาเกี่ยวข้องกับเกตเวย์ข้อมูลในองค์กร และเปิดใช้งาน Power BI Desktop

### <a name="resolution-1-install-the-latest-version-of-power-bi-on-premises-data-gateway"></a>การแก้ปัญหาที่ 1 ติดตั้งเกตเวย์ข้อมูลภายในองค์กร Power BI เวอร์ชันล่าสุด
เกตเวย์ข้อมูลภายในองค์กร Power BI เวอร์ชันล่าสุดไม่จำกัดการตั้งชื่อไปป์บนเครื่องคอมพิวเตอร์ และอนุญาตให้ Power BI Desktop เพื่อเปิดใช้งานได้อย่างถูกต้อง ถ้าคุณจำเป็นต้องดำเนินต่อโดยใช้เกตเวย์ข้อมูลภายในองค์กร Power BI นี่คือวิธีแก้ไขแนะนำ คุณสามารถดาวน์โหลดเวอร์ชันล่าสุดของเกตเวย์ข้อมูลภายในองค์กร Power BI จาก[ตำแหน่งที่ตั้งนี้](https://go.microsoft.com/fwlink/?LinkId=698863)ได้ โปรดทราบว่า ลิงก์เป็นลิงก์ดาวน์โหลดโดยตรงเพื่อการดำเนินการติดตั้ง

### <a name="resolution-2-uninstall-or-stop-the-power-bi-on-premises-data-gateway-windows-service"></a>การแก้ปัญหาที 2 ถอนการติดตั้งหรือหยุด Windows service ของเกตเวย์ข้อมูลองค์กร Power BI
ถ้าคุณไม่จำเป็นต้องใช้เกตเวย์ข้อมูลภายในองค์กร Power BI คุณสามารถถอนการติดตั้ง หรือคุณสามารถหยุด Windows service ของเกตเวย์ข้อมูลองค์กร Power BI ซึ่งจะลบข้อจำกัดนโยบาย และอนุญาตให้ Power BI Desktop ทำงาน

### <a name="resolution-3-run-power-bi-desktop-with-administrator-privilege"></a>การแก้ปัญหาที่ 3 เรียกใช้ Power BI Desktop กับสิทธิ์ผู้ดูแลระบบ
อีกวิธีหนึ่งคือ คุณสามารถเปิดใช้ Power BI Desktop แบบผู้ดูแล ซึ่งอนุญาตให้ Power BI Desktop เปิดใช้งานอย่างเรียบร้อย ยังคงแนะนำให้คุณติดตั้งเวอร์ชันล่าสุดของเกตเวย์ข้อมูลภายในองค์กร Power BI ตามที่อธิบายไว้ก่อนหน้าในบทความนี้

## <a name="help-with-other-issues-when-launching-power-bi-desktop"></a>ความช่วยเหลือปัญหาอื่น ๆ เมื่อเปิดใช้ Power BI Desktop
เราจะมุ่งมั่นที่จะครอบคลุมปัญหาที่เกิดขึ้นกับ**Power BI Desktop**ให้มากที่สุด เราดูปัญหาที่อาจจะมีผลกระทบต่อลูกค้าจำนวนมากอย่างเป็นประจำ และรวมเอาไว้ในบทความของเรา

ถ้าปัญหาเกี่ยวกับการเปิดใช้งาน**Power BI Desktop**จะไม่เชื่อมกับเกตเวย์ข้อมูลในองค์กร หรือเมื่อการแก้ปัญหาก่อนหน้านี้ใช้ไม่ได้ คุณสามารถส่งเรื่องไปยัง[ฝ่ายสนับสนุน Power BI](https://support.powerbi.com)( https://support.powerbi.com) เพื่อช่วยระบุและแก้ไขปัญหาของคุณ

สำหรับปัญหาอื่นๆ ที่คุณอาจพบได้ในอนาคตกับ**Power BI Desktop** (เราหวังว่าจะไม่มน้อยที่สุด) จะเป็นประโยชน์มากเมื่อต้องการเปิดใช้งานการติดตาม และรวบรวมไฟล์บันทึก ที่จะแยกและระบุปัญหาได้ได้ดียิ่งขึ้น เมื่อต้องการเปิดใช้งานการติดตาม ให้เลือก**ไฟล์ > ตัวเลือกและการตั้งค่า > ตัวเลือก**แล้วเลือก**การวินิจฉัย**จากนั้น ตรวจสอบ**เปิดใช้งานการติดตาม**ภายใต้*ตัวเลือกการวินิจฉัย* เราตระหนัก**Power BI Desktop**ต้องเรียกใช้การตั้งค่าตัวเลือกนี้ ซึ่งจะเป็นประโยชน์มากสำหรับปัญหาที่เกี่ยวข้องกับการเปิดใช้งาน **Power BI Desktop** ในอนาคต

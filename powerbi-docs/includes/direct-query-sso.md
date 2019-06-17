---
title: รวมไฟล์
description: รวมไฟล์
services: powerbi
author: mgblythe
ms.service: powerbi
ms.topic: include
ms.date: 05/31/2019
ms.author: mblythe
ms.openlocfilehash: 94b6959b6bcbf250e54a353e8b725b6c9e5a2e30
ms.sourcegitcommit: c539726c9c180e899a8a34443e3fda2b9848beb2
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/31/2019
ms.locfileid: "66448409"
---
## <a name="single-sign-on"></a>ลงชื่อเข้าระบบครั้งเดียว

หลังจากที่คุณเผยแพร่ยังชุดข้อมูล Azure SQL DirectQuery ไปยังบริการแล้ว คุณสามารถอนุญาตให้ผู้ใช้งานของคุณลงชื่อเข้าระบบครั้งเดียว (SSO) ได้ผ่าน OAuth2 ของ Azure Active Directory (Azure AD)

เมื่อต้องการเปิดใช้งาน SSO ไปที่การตั้งค่าสำหรับชุดข้อมูล เปิดแท็บ**แหล่งข้อมูล** แล้วเลือกกล่อง SSO

![กำหนดค่ากล่องโต้ตอบ Azure SQL DQ](media/direct-query-sso/sso-dialog.png)

เมื่อเปิดใช้งานตัวเลือก SSO และผู้ใช้ของคุณเข้าถึงรายงานที่สร้างขึ้นบนยอดของแหล่งข้อมูล Power BI จะส่งข้อมูลประจำตัวที่รับรองความถูกต้อง Azure AD ของผู้ใช้ในการสอบถามไปยังฐานข้อมูล Azure SQL หรือคลังข้อมูล ซึ่งจะช่วยให้ Power BI เป็นไปตามการตั้งค่าความปลอดภัยที่มีการกำหนดค่าในระดับแหล่งข้อมูล

ตัวเลือก SSO จะมีผลต่อชุดข้อมูลทั้งหมดที่ใช้แหล่งข้อมูลนี้ แต่จะไม่มีผลต่อวิธีการรับรองความถูกต้องที่ใช้สำหรับสถานการณ์สมมติการนำเข้า

> [!Note]
> ไม่รองรับ Azure Multi-Factor Authentication (MFA) ผู้ใช้ที่ต้องการใช้ SSO กับ Azure SQL DirectQuery ต้องได้รับการยกเว้น MFA
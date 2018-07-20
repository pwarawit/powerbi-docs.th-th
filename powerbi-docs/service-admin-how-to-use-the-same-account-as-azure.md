---
title: การใช้บัญชีเดียวกันสำหรับ Power BI และ Azure
description: วิธีใช้บัญชีเดียวกันสำหรับเข้าสู่ระบบ Power BI และ Azure
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 375a251e7515ad33396cc4cf5ebb0ee715ab0330
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34254044"
---
# <a name="using-the-same-account-for-power-bi-and-azure"></a>การใช้บัญชีเดียวกันสำหรับ Power BI และ Azure
ถ้าคุณเป็นทั้งผู้ใช้ Power BI และ Azure คุณอาจต้องการใช้บัญชีเดียวกันสำหรับเข้าสู่ระบบทั้งสอง เพื่อคุณจะได้ไม่เป็นต้องพิมพ์รหัสผ่านของคุณซ้ำสองครั้ง

Power BI ลงชื่อคุณเข้าใช้ ด้วยบัญชีองค์กรของคุณ ซึ่งเชื่อมโยงกับที่อยู่อีเมลงานหรือโรงเรียนของคุณ  Azure ลงชื่อคุณเข้าใช้ ด้วยบัญชี Microsoft หรือบัญชีองค์กรของคุณ

ถ้าคุณต้องการใช้บัญชีเดียวกันสำหรับทั้ง Azure และ Power BI ให้แน่ใจว่าได้ลงชื่อเข้าใช้ Azure ด้วยบัญชีองค์กรของคุณ

**เกิดอะไรขึ้นถ้าฉันลงชื่อเข้าใช้ Azure ด้วยบัญชี Microsoft ของฉันไปแล้ว?**

คุณสามารถเพิ่มบัญชีผู้ใช้องค์กรของคุณเป็นผู้ดูแลร่วมใน Azure  ต่อไปนี้คือวิธีการ:

1. ลงชื่อเข้าใช้ [Azure Management Portal](http://manage.windowsazure.com/) ถ้าคุณเป็นผู้ใช้ในหลายไดเรกทอรีใน Azure คลิก**การสมัครใช้งาน**และกรองเพื่อดูเฉพาะไดเรกทอรีและการสมัครใช้งานที่คุณต้องการแก้ไข
2. ในบานหน้าต่างนำทาง คลิก**ตั้งค่า** คลิก**ผู้ดูแลระบบ** แล้วคลิก**เพิ่ม**
3. ใส่ที่อยู่อีเมลที่เชื่อมโยงกับบัญชีองค์กรของคุณ
4. เลือกการสมัครใช้งานที่คุณต้องการเข้าถึงด้วยบัญชีองค์กรของคุณ แล้ว คลิกที่เครื่องหมายถูก

ครั้งถัดไปที่คุณลงชื่อเข้าใช้ Azure Management Portal ให้ใช้ที่อยู่อีเมลองค์กรของคุณ

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


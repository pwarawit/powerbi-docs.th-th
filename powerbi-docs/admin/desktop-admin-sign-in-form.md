---
title: วิธีที่ผู้ดูแลระบบสามารถจัดการกับแบบฟอร์มการลงชื่อเข้าใช้ Power BI Desktop
description: เรียนรู้วิธีที่คุณจะสามารถจัดการกับแบบฟอร์มการลงชื่อเข้าใช้เริ่มต้นเมื่อเปิด Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 04/15/2019
ms.author: davidi
ms.openlocfilehash: 49b7d1129f73e146db1e34b1ec7d39a176cb37ed
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85228918"
---
# <a name="administrators-manage-the-power-bi-desktop-sign-in-form"></a>ผู้ดูแลระบบ: จัดการแบบฟอร์มการลงชื่อเข้าใช้ Power BI Desktop
ในครั้งแรกที่ Power BI Desktop เปิดตัว แบบฟอร์มการลงชื่อเข้าใช้จะปรากฏขึ้น สามารถกรอกข้อมูล หรือลงชื่อเข้าใช้ Power BI เพื่อดำเนินการต่อได้ ผู้ดูแลระบบจัดการแบบฟอร์มนี้โดยใช้รีจิสทรีคีย์ 

![แบบฟอร์มการลงชื่อเข้าใช้เริ่มต้นสำหรับ Power BI Desktop](media/desktop-admin-sign-in-form/sign-in-form.png)

ผู้ดูแลระบบใช้รีจิสทรีคีย์ต่อไปนี้เพื่อปิดการใช้งานแบบฟอร์มลงชื่อเข้าใช้ ซึ่งยังสามารถใช้กับทั้งองค์กรโดยใช้นโยบายส่วนกลาง

```
Key: HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```
คุณยังสามารถลองใช้คีย์ต่อไปนี้ซึ่งสามารถทำงานได้ดีกับลูกค้าบางรายตามการกำหนดค่าของพวกเขา:

```
Key: HKEY_CURRENT_USER\SOFTWARE\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```

ค่าของ 0 จะปิดการใช้งานกล่องโต้ตอบ




มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)


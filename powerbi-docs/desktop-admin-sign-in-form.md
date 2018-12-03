---
title: วิธีที่ผู้ดูแลระบบสามารถจัดการกับแบบฟอร์มการลงชื่อเข้าใช้ Power BI Desktop
description: เรียนรู้วิธีที่คุณจะสามารถจัดการกับแบบฟอร์มการลงชื่อเข้าใช้เริ่มต้นเมื่อเปิด Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 11/28/2018
ms.author: davidi
ms.openlocfilehash: 3c92063c82c370bd59ecd7bfa2798ae60a3b425d
ms.sourcegitcommit: 05303d3e0454f5627eccaa25721b2e0bad2cc781
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/28/2018
ms.locfileid: "52578255"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>วิธีที่ผู้ดูแลระบบสามารถจัดการกับแบบฟอร์มการลงชื่อเข้าใช้ Power BI Desktop
ในครั้งแรกที่ Power BI Desktop เปิดตัว แบบฟอร์มการลงชื่อเข้าใช้จะปรากฏขึ้น สามารถกรอกข้อมูล หรือลงชื่อเข้าใช้ Power BI เพื่อดำเนินการต่อได้ ผู้ดูแลระบบจัดการแบบฟอร์มนี้โดยใช้รีจิสทรีคีย์ 

![แบบฟอร์มการลงชื่อเข้าใช้เริ่มต้นสำหรับ Power BI Desktop](media/desktop-admin-sign-in-form/sign-in-form.png)

ผู้ดูแลระบบใช้รีจิสทรีคีย์ต่อไปนี้เพื่อปิดการใช้งานแบบฟอร์มลงชื่อเข้าใช้ ซึ่งยังสามารถใช้กับทั้งองค์กรโดยใช้นโยบายส่วนกลาง

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

ค่าของ 0 จะปิดการใช้งานกล่องโต้ตอบ

คุณมีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


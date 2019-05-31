---
title: ตัวเชื่อมต่อบุคคลสามใน Power BI ที่เชื่อถือได้
description: วิธีการเชื่อถือตัวเชื่อมต่อบริษัทลงใน Power BI
author: cpopell
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/3/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 30b7457c6149320c43f24b967a842382821b01b1
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "65607778"
---
# <a name="trusting-third-party-connectors"></a>ความเชื่อถือของบุคคลสามตัวเชื่อมต่อ

## <a name="why-do-you-need-trusted-third-party-connectors"></a>เหตุใดคุณจึงต้องตัวเชื่อมต่อบุคคลสามที่เชื่อถือได้หรือไม่

ใน Power BI เราโดยทั่วไปแล้วขอแนะนำให้เก็บ 'ส่วนขยายความปลอดภัยของข้อมูล' ระดับในระดับสูงกว่า ซึ่งป้องกันไม่ให้โหลดของรหัสที่ไม่ได้รับการรับรอง โดย Microsoft อย่างไรก็ตาม อาจมีหลายกรณีที่คุณต้องการโหลดตัวเชื่อมต่อเฉพาะ - รายการคุณเขียน หรือรูปภาพให้กับคุณ โดยที่ปรึกษาหรือผู้จัดจำหน่ายภายนอกเส้นทางใบรับรอง Microsoft

นักพัฒนาของตัวเชื่อมต่อแบบกำหนดสามารถลงชื่อเข้าใช้ ด้วยใบรับรอง และให้ข้อมูลที่คุณจำเป็นต้องโหลดอย่างปลอดภัยโดยไม่ต้องลดการตั้งค่าความปลอดภัยของคุณ

ถ้าคุณต้องการเรียนรู้เพิ่มเติมเกี่ยวกับการตั้งค่าความปลอดภัย คุณสามารถอ่านเกี่ยวกับพวกเขา[นี่](https://docs.microsoft.com/power-bi/desktop-connector-extensibility)ได้

## <a name="using-the-registry-to-trust-third-party-connectors"></a>ใช้รีจิสทรีความเชื่อถือของบุคคลสามตัวเชื่อมต่อ

ความเชื่อถือของบุคคลสามตัวเชื่อมต่อใน Power BI สามารถทำ โดยการใส่รหัสประจำตัวของใบรับรองที่คุณต้องการเชื่อถือในค่ารีจิสทรีที่ระบุ ถ้ารหัสประจำตัวนี้ตรงกับรหัสประจำตัวของใบรับรองบนตัวเชื่อมต่อที่คุณต้องการโหลด คุณจะไม่สามารถโหลดในระดับความปลอดภัย 'แนะนำ' ของ Power BI 

The registry path is HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Power BI Desktop. ตรวจสอบว่า เส้นทางมี หรือสร้างรายการ เราเลือกตำแหน่งที่ตั้งนี้เนื่องจากจะถูกควบคุม โดยนโยบายด้าน IT ตลอดจนดูแลภายในเครื่องจำเป็นต้องมีสิทธิ์ในการแก้ไขเป็นหลัก 

![ตั้งค่า Power BI Desktop รีจิสทรี ด้วยไม่มีคีย์สามที่เชื่อถือได้](media/desktop-trusted-third-party-connectors/desktoptrustedthird1.png)

เพิ่มค่าใหม่ภายใต้เส้นทางระบุไว้ข้างต้น ชนิดควรเป็น "หลายค่า สตริง" (REG_MULTI_SZ), และและควรเรียกว่า "TrustedCertificateThumbprints" 

![Power BI Desktop รีจิสทรี ด้วยรายการสำหรับตัวเชื่อมต่อบุคคลสามที่เชื่อถือได้แต่ไม่มีคีย์](media/desktop-trusted-third-party-connectors/desktoptrustedthird2.png)

เพิ่ม thumbprints ของใบรับรองคุณต้องการเชื่อถือ คุณสามารถเพิ่มใบรับรองจำนวนมาก โดยใช้ "\0" เป็นตัวคั่น หรือ registry editor ขวา -> คลิกปรับเปลี่ยน และใส่รหัสประจำตัวแต่ละบรรทัดใหม่ ตัวอย่างรหัสประจำตัวถูกนำมาจากใบรับรองที่เซ็นชื่อด้วยตนเอง 

 ![ตั้งค่า Power BI Desktop รีจิสทรี ด้วยคีย์สามเชื่อถือได้](media/desktop-trusted-third-party-connectors/desktoptrustedthird3.png)

ถ้าคุณได้ทำตามคำแนะนำอย่างถูกต้อง และได้รับรหัสประจำตัวเหมาะสม โดยนักพัฒนาของคุณ คุณควรตอนนี้สามารถได้อย่างปลอดภัยเชื่อถือตัวเชื่อมต่อลงทะเบียน ด้วยใบรับรองเกี่ยวข้อง

## <a name="how-to-sign-connectors"></a>วิธีการลงชื่อเข้าใช้ตัวเชื่อมต่อ

ถ้าคุณมีตัวเชื่อมต่อแบบคุณหรือนักพัฒนาจำเป็นต้องลงชื่อเข้าใช้ คุณสามารถอ่านได้ในเอกสาร Power Query [นี่](https://docs.microsoft.com/power-query/handlingconnectorsigning)ได้

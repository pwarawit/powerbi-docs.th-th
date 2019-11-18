---
title: ส่งผ่านพารามิเตอร์รายงานใน URL สำหรับรายงานที่มีการแบ่งหน้า - ตัวสร้างรายงาน Power BI
description: หัวข้อนี้อธิบายวิธีการส่งผ่านพารามิเตอร์รายงานไปยังรายงานโดยรวมใน URL รายงานที่มีการแบ่งหน้า
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.reviewer: cfinlan
ms.custom: ''
ms.date: 08/29/2019
ms.openlocfilehash: 44e56613a69069351f21aa7d515fc2bb296e6728
ms.sourcegitcommit: 01de0b01f66f28ca45b8d309d7864f261d6c9a85
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/16/2019
ms.locfileid: "74128255"
---
# <a name="pass-a-report-parameter-in-a-url-for-a-paginated-report-in-power-bi"></a>ส่งผ่านพารามิเตอร์รายงานใน URL สำหรับรายงานที่มีการแบ่งหน้าใน Power BI 

คุณสามารถส่งผ่านพารามิเตอร์รายงานไปยังรายงานโดยรวมไว้ใน URL รายงานที่มีการแบ่งหน้า พารามิเตอร์คิวรีทั้งหมดสามารถมีพารามิเตอร์รายงานที่สอดคล้องกันได้ ดังนั้นคุณส่งผ่านพารามิเตอร์คิวรีไปยังรายงานโดยผ่านพารามิเตอร์รายงานที่สอดคล้องกัน คุณจำเป็นต้องใช้คำนำหน้าชื่อพารามิเตอร์ด้วย `rp:` สำหรับ Power BI เพื่อจดจำใน URL 

พารามิเตอร์รายงานต้องตรงตามตัวพิมพ์ใหญ่-เล็ก และใช้อักขระพิเศษเหล่านี้: 

- ช่องว่างในส่วนพารามิเตอร์ของ URL จะถูกแทนที่ด้วยเครื่องหมายบวก (+)  ตัวอย่างเช่น: 

    ```rp:Holiday=Christmas+Day```

- เครื่องหมายอัฒภาคในส่วนใด ๆ ของสตริงที่จะถูกแทนที่ด้วยอักขระ `%3A`

เบราว์เซอร์ควรดำเนินการเข้ารหัส URL ที่เหมาะสมโดยอัตโนมัติ คุณไม่จำเป็นต้องเข้ารหัสอักขระใด ๆ ด้วยตนเอง 

เมื่อต้องการตั้งค่าพารามิเตอร์รายงานภายใน URL ให้ใช้ไวยากรณ์ต่อไปนี้: 

```
rp:parameter=value
```

ตัวอย่างเช่น เมื่อต้องการระบุสองพารามิเตอร์ "Salesperson" และ "State" ที่กำหนดไว้ในรายงานในพื้นที่ทำงานของฉัน คุณจะต้องใช้ URL ต่อไปนี้: 

```
https://app.powerbi.com/groups/me/rdlreports/xxxxxxx-abc7-40f0-b456-febzf9cdda4d?rp:Salesperson=Tie+Bear&rp:State=Utah 
```

เมื่อต้องการระบุพารามิเตอร์สองรายการเดียวกันที่กำหนดในรายงานในแอป คุณจะต้องใช้ URL ต่อไปนี้: 

```
https://app.powerbi.com/groups/me/apps/xxxxxxx-c4c4-4217-afd9-3920a0d1e2b0/rdlreports/b1d5e659-639e-41d0-b733-05d2bca9853c?rp:Salesperson=Tiggee&State=Utah 
```

เมื่อต้องการส่งค่า null สำหรับพารามิเตอร์ ให้ใช้ไวยากรณ์ต่อไปนี้: 

```
parameter:isnull=true
```

ตัวอย่างเช่น:

```
rp:SalesOrderNumber:isnull=true
```

เมื่อต้องการส่งค่า Boolean ให้ใช้ 0 สำหรับ False และ 1 สำหรับ True เมื่อต้องการส่งค่า Float ให้ใส่ตัวคั่นทศนิยมของตำแหน่งที่ตั้งเซิร์ฟเวอร์

> [!NOTE]
> ถ้ารายงานของคุณมีพารามิเตอร์รายงานที่มีค่าเริ่มต้นและค่าของคุณสมบัติ **พร้อมท์** เป็น **false** (นั่นคือ**ผู้ใช้พร้อมท์** ไม่ได้เลือกคุณสมบัติในโปรแกรมจัดการรายงาน) จากนั้นคุณจะไม่สามารถส่งค่าสำหรับพารามิเตอร์รายงานนั้นได้ภายใน URL ซึ่งช่วยให้ผู้ดูแลระบบมีตัวเลือกในการป้องกันผู้ใช้ปลายมิให้เพิ่มหรือแก้ไขค่าของพารามิเตอร์รายงานบางอย่าง

## <a name="additional-examples"></a>ตัวอย่างเพิ่มเติม 

ตัวอย่าง URL ต่อไปนี้ประกอบด้วยพารามิเตอร์แบบหลายค่า "Salesperson” รูปแบบสำหรับพารามิเตอร์หลายค่าคือการทำซ้ำชื่อพารามิเตอร์สำหรับแต่ละค่า 

```
https://app.powerbi.com/groups/me/rdlreports/xxxxxxx-abc7-40f0-b456-febzf9cdda4d?rp:Salesperson=Tie+Bear&rp:Salesperson=Mickey 
```

ตัวอย่าง URL ต่อไปนี้จะส่งพารามิเตอร์เดียวของ SellStartDate  ที่มีค่า "7/1/2005" สำหรับเซิร์ฟเวอร์รายงานโหมดเนทิฟ

```
https://app.powerbi.com/groups/me/rdlreports/xxxxxxx-abc7-40f0-b456-febzf9cdda4d?rp:SellStartDate=7/1/2005
```

## <a name="next-steps"></a>ขั้นตอนถัดไป

- [พารามิเตอร์ URL ในรายงานที่มีการแบ่งหน้าใน Power BI](report-builder-url-parameters.md)
- [รายงานแบบแบ่งหน้าใน Power BI Premium คืออะไร](paginated-reports-report-builder-power-bi.md)

---
title: API ที่เก็บข้อมูลภายในใน Power BI Visuals
description: บทความนี้อธิบายวิธีการใช้ API ของ Power BI Visuals เพื่อเข้าถึงที่เก็บข้อมูลภายในเครื่องของเบราว์เซอร์
author: uve
ms.author: v-grniki
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 10/31/2019
ms.openlocfilehash: f69a3c8928b8079f79b8a6dd5f5b132235a7089c
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/09/2019
ms.locfileid: "73879882"
---
# <a name="local-storage-api"></a>API ที่เก็บข้อมูลภายใน

API ที่เก็บข้อมูลภายในคือ API ที่วิชวลแบบกำหนดเองสามารถใช้เพื่อร้องขอการโฮสต์ในการบันทึกหรือโหลดข้อมูลจากที่จัดเก็บของอุปกรณ์ ซึ่งแยกออกมาในแง่ที่ว่ามีการแยกการเข้าถึงที่เก็บข้อมูลระหว่างวิชวลชนิดที่แตกต่างกัน

## <a name="sample"></a>ตัวอย่าง

ถ้าวิชวลแบบกำหนดเองควรเพิ่มตัวนับบางตัวทุกครั้งที่มีการเรียกใช้วิธีการอัปเดต แต่ค่าตัวนับควรคงไว้และไม่ได้ตั้งค่าใหม่ในทุกครั้งที่เริ่มต้นวิชวล:

```typescript
export class Visual implements IVisual {
        // ...
        private updateCountName: string = 'updateCount';
        private updateCount: number;
        private storage: ILocalVisualStorageService;
        // ...

        constructor(options: VisualConstructorOptions) {
            // ...
            this.storage = options.host.storageService;
            // ...

            this.storage.get(this.updateCountName).then(count =>
            {
                this.updateCount = +count;
            })
            .catch(() =>
            {
                this.updateCount = 0;
                this.storage.set(this.updateCountName, this.updateCount.toString());
            });
            // ...
        }

        public update(options: VisualUpdateOptions) {
            // ...
            this.updateCount++;
            this.storage.set(this.updateCountName, this.updateCount.toString());
            // ...
        }
}
```

## <a name="known-limitations-and-issues"></a>ข้อจำกัดและปัญหาที่ทราบ

API ที่เก็บข้อมูลภายในจะไม่ถูกเปิดใช้งานสำหรับวิชวลแบบกำหนดเองตามค่าเริ่มต้น ถ้าคุณต้องการเปิดใช้งานสำหรับวิชวลแบบกำหนดเอง โปรดส่งคำขอไปยังฝ่ายสนับสนุนวิชวลแบบกำหนดเองของ Power BI `pbicvsupport@microsoft.com`

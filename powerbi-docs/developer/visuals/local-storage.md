---
title: API ที่เก็บข้อมูลภายในใน Power BI Visuals
description: บทความนี้อธิบายวิธีการใช้ API ของ Power BI Visuals เพื่อเข้าถึงที่เก็บข้อมูลภายในเครื่องของเบราว์เซอร์
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 01/21/2019
ms.openlocfilehash: e2cb11ea9be85916e6b5557e7933f6a6b5a7159a
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/14/2020
ms.locfileid: "79380605"
---
# <a name="local-storage-api"></a>API ที่เก็บข้อมูลภายใน

API ที่เก็บข้อมูลภายในคือ API ที่วิชวลแบบกำหนดเองสามารถใช้เพื่อร้องขอให้โฮสต์ทำการบันทึกหรือโหลดข้อมูลจากที่จัดเก็บของอุปกรณ์ ซึ่งแยกจากกันได้โดยการแยกการเข้าถึงพื้นที่เก็บข้อมูลระหว่างวิชวลชนิดที่แตกต่างกัน

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

API ที่เก็บข้อมูลภายในจะไม่ถูกเปิดใช้งานสำหรับวิชวล Power BI ตามค่าเริ่มต้น ถ้าคุณต้องการเปิดใช้งานสำหรับวิชวล Power BI ของคุณ โปรดส่งคำขอไปยังฝ่ายสนับสนุนวิชวล Power BI `pbicvsupport@microsoft.com`  
**โปรดทราบว่าวิชวลของคุณควรมีอยู่ใน [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals) และ [ได้รับการรับรอง](https://powerbi.microsoft.com/en-us/documentation/powerbi-custom-visuals-certified/)**

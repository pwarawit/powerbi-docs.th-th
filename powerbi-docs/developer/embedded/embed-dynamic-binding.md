---
title: เชื่อมต่อรายงานไปยังชุดข้อมูลโดยใช้การผูกแบบไดนามิก
description: เรียนรู้วิธีการฝังรายงานโดยใช้การผูกแบบไดนามิก
author: KesemSharabi
ms.author: kesharab
ms.topic: how-to
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 11/07/2019
ms.openlocfilehash: ba63b8be32600428075b9304a5a29fef62a9d6c8
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85236856"
---
# <a name="connect-a-report-to-a-dataset-using-dynamic-binding"></a>เชื่อมต่อรายงานไปยังชุดข้อมูลโดยใช้การผูกแบบไดนามิก 

เมื่อเชื่อมต่อรายงานกับชุดข้อมูล คุณสามารถใช้การผูกแบบไดนามิก การเชื่อมต่อระหว่างรายงานและชุดข้อมูล จะเรียกว่า *การผูก* เมื่อมีการกำหนดว่าจะผูกข้อมูลไว้ที่จุดของการฝัง ซึ่งตรงข้ามกับที่กำหนดไว้ก่อนหน้านี้ การผูกดังกล่าวจะเรียกว่า การผูกแบบไดนามิก

เมื่อทำการฝังรายงาน Power BI โดยใช้*การผูกแบบไดนามิก* คุณสามารถเชื่อมต่อรายงานเดียวกันกับชุดข้อมูลที่แตกต่างกันได้ ทั้งนี้ขึ้นอยู่กับข้อมูลประจำตัวของผู้ใช้

ซึ่งหมายความว่าคุณสามารถใช้รายงานเดียวเพื่อแสดงข้อมูลที่แตกต่างกันได้ ทั้งนี้ขึ้นอยู่กับชุดข้อมูลที่เชื่อมต่ออยู่ ตัวอย่างเช่น รายงานที่แสดงมูลค่ายอดขายสำหรับการค้าปลีกสามารถเชื่อมต่อกับชุดข้อมูลผู้ค้าปลีกที่แตกต่างกัน และให้ผลลัพธ์ที่แตกต่างกันได้ โดยขึ้นอยู่กับชุดข้อมูลของผู้ค้าปลีกที่เชื่อมต่ออยู่

รายงานและชุดข้อมูลไม่จำเป็นต้องอยู่ในพื้นที่ทำงานเดียวกัน พื้นที่ทำงานทั้งสอง (พื้นที่หนึ่งประกอบด้วยรายงาน และอีกหนึ่งประกอบด้วยชุดข้อมูล) ต้องถูกกำหนดไปยัง[ความจุ](azure-pbie-create-capacity.md)

ในฐานะที่เป็นส่วนหนึ่งของกระบวนการฝัง ตรวจสอบให้แน่ใจว่าคุณ *สร้างโทเค็นที่มีสิทธิ์เพียงพอ* และ *ปรับเปลี่ยนออบเจ็กต์การกำหนดค่า* แล้ว

## <a name="generating-a-token-with-sufficient-permissions"></a>การสร้างโทเค็นที่มีสิทธิ์เพียงพอ

การผูกแบบไดนามิกสนับสนุนทั้งสถานการณ์ *การฝังสำหรับองค์กรของคุณ* และ *การฝังสำหรับลูกค้าของคุณ* ตารางด้านล่างนี้อธิบายถึงข้อควรพิจารณาสำหรับแต่ละสถานการณ์สมมติ

|สถานการณ์สมมติ  |ความเป็นเจ้าของข้อมูล  |โทเค็น  |ข้อกำหนด  |
|---------|---------|---------|---------|
|*การฝังสำหรับองค์กรของคุณ*    |ผู้ใช้เป็นเจ้าของข้อมูล         |โทเค็นการเข้าถึงสำหรับผู้ใช้ Power BI         |ผู้ใช้ที่ใช้โทเค็น Azure AD ต้องมีสิทธิ์ที่เหมาะสมสำหรับอาร์ทิแฟกต์ทั้งหมด         |
|*การฝังสำหรับลูกค้าของคุณ*     |แอปเป็นเจ้าของข้อมูล         |โทเค็นการเข้าถึงสำหรับผู้ใช้ที่ไม่ได้ใช้งาน Power BI         |ต้องมีสิทธิ์สำหรับทั้งรายงานและชุดข้อมูลที่ผูกไว้แบบไดนามิก ใช้ [API เพื่อสร้างโทเค็นการฝังสำหรับหลายรายการ](embed-sample-for-customers.md#multiEmbedToken) เพื่อสร้างโทเค็นการฝังที่สนับสนุนหลายอาติเฟค         |

## <a name="adjusting-the-config-object"></a>ปรับเปลี่ยนออบเจ็กต์การกำหนดค่า
เพิ่ม `datasetBinding` ไปยังออบเจ็กต์การกำหนดค่า ใช้ตัวอย่างด้านล่างเป็นข้อมูลอ้างอิง

```javascript
var config = {
    type: 'report',
    tokenType: models.TokenType.Embed,
    accessToken: accessToken,
    embedUrl: embedUrl,
    id: "reportId", // The wanted report id
    permissions: permissions,

    // -----  Adjustment required for dynamic binding ---- //
    datasetBinding: {
        datasetId: "notOriginalDatasetId",  // </The wanted dataset id
    }
    // ---- End of dynamic binding adjustment ---- //
};

// Get a reference to the embedded report HTML element
var embedContainer = $('#embedContainer')[0];

// Embed the report and display it within the div container
var report = powerbi.embed(embedContainer, config);
```

## <a name="next-steps"></a>ขั้นตอนถัดไป

หากคุณไม่คุ้นเคยกับการฝังใน Power BI ให้อ่านบทช่วยสอนเหล่านี้เพื่อเรียนรู้วิธีการฝังเนื้อหา Power BI ของคุณ:
* [บทช่วยสอน: เนื้อหา Power BI ที่ฝังลงในแอปพลิเคชันสำหรับลูกค้าของคุณ](embed-sample-for-customers.md)
* [บทช่วยสอน: ฝังเนื้อหา Power BI ลงในแอปพลิเคชันสำหรับองค์กรของคุณ](embed-sample-for-your-organization.md)
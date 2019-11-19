---
title: ผูกพันแบบไดนามิก
description: เรียนรู้วิธีการฝังรายงานโดยใช้การผูกโยงแบบไดนามิก
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 09/25/2019
ms.openlocfilehash: 8b42b397f726e492eda80a99eb730c215eb17ccb
ms.sourcegitcommit: 23ad768020a9daf129f69a462a2d46d59d2349d2
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/22/2019
ms.locfileid: "72776248"
---
# <a name="dynamic-binding"></a>ผูกพันแบบไดนามิก

การผูกโยงแบบไดนามิกช่วยให้สามารถใช้งานการเลือกชุดข้อมูลแบบไดนามิกในขณะที่ฝังรายงานได้ รายงานและชุดข้อมูลไม่จำเป็นต้องอยู่ในพื้นที่ทำงานเดียวกัน ผู้ใช้ปลายทางจะเห็นผลลัพธ์ที่แตกต่างกัน โดยขึ้นอยู่กับชุดข้อมูลที่เลือก

พื้นที่ทำงานทั้งคู่ (อันหนึ่งประกอบด้วยรายงาน และอีกอันประกอบด้วยชุดข้อมูล) จะต้องถูกกำหนดไว้ในความจุ

การฝังรายงานโดยใช้การผูกโยงแบบไดนามิกมีสองขั้นตอน:
1. สร้างโทเค็น
2. ปรับเปลี่ยนออบเจ็กต์การกำหนดค่า

## <a name="generating-a-token"></a>สร้างโทเค็น
เมื่อต้องการสร้างโทเค็น ให้ใช้ [API สำหรับการสร้างโทเค็นแบบฝังตัวในหลายรายการ](embed-sample-for-customers.md#multiEmbedToken)

การผูกโยงแบบไดนามิกได้รับการสนับสนุนสำหรับสถานการณ์การฝังทั้งสองแบบได้แก่ *การฝังสำหรับองค์กรของคุณ* และ *การฝังสำหรับลูกค้าของคุณ*

| วิธีแก้                   | โทเค็น                               | ข้อกำหนด                                                                                                                                                  |
|---------------------------------|-------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *การฝังสำหรับองค์กรของคุณ* | โทเค็นการเข้าถึงสำหรับผู้ใช้ Power BI     | ผู้ใช้ที่ใช้โทเค็น Azure AD ต้องมีสิทธิ์ที่เหมาะสมสำหรับอาร์ทิแฟกต์ทั้งหมด                                                                    |
| *การฝังสำหรับลูกค้าของคุณ*    | โทเค็นการเข้าถึงสำหรับผู้ใช้ที่ไม่ได้ใช้งาน Power BI | ต้องมีสิทธิ์สำหรับทั้งรายงานและชุดข้อมูลที่ผูกไว้แบบไดนามิก ใช้ API ใหม่เพื่อสร้างโทเค็นแบบฝังตัวที่สนับสนุนอาร์ทิแฟกต์หลายรายการ |

## <a name="adjusting-the-config-object"></a>ปรับเปลี่ยนออบเจ็กต์การกำหนดค่า
เพิ่ม `datasetBinding` ไปยังออบเจ็กต์การกำหนดค่า ใช้ตัวอย่างที่ด้านล่างของหน้าเพื่อเป็นข้อมูลอ้างอิง

หากคุณไม่คุ้นเคยกับการฝังใน Power BI ให้อ่านบทช่วยสอนเหล่านี้เพื่อเรียนรู้วิธีการฝังเนื้อหา Power BI ของคุณ:
* [ฝังเนื้อหา Power BI ลงในแอปพลิเคชันสำหรับลูกค้าของคุณ](embed-sample-for-customers.md)
* [บทช่วยสอน: ฝังเนื้อหา Power BI ลงในแอปพลิเคชันสำหรับองค์กรของคุณ](embed-sample-for-your-organization.md)

 ### <a name="example"></a>ตัวอย่าง:
```javascript
var config = {
    type: 'report',
    tokenType: models.TokenType.Embed,
    accessToken: accessToken,
    embedUrl: embedUrl,
    id: "reportId", // The wanted report id
    permissions: permissions,

    /////////////////////////////////////////////
    // Adjustment required for dynamic binding //
    datasetBinding: {
        datasetId: "notOriginalDatasetId",  // </The wanted dataset id
    }
    // End of dynamic binding adjustment            //
    /////////////////////////////////////////////
};

// Get a reference to the embedded report HTML element
var embedContainer = $('#embedContainer')[0];

// Embed the report and display it within the div container
var report = powerbi.embed(embedContainer, config);
```
---
title: ถามตอบใน Power BI Embedded
description: Power BI Embedded ให้คุณสามารถรวม ถามตอบ เข้าไปในแอปพลิเคชัน และอนุญาตให้ผู้ใช้ของคุณถามคำถามด้วยภาษาธรรมชาติ
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 11/20/2017
ms.openlocfilehash: 5a3a7b91b0c97a75923876caff205ffb9abfce70
ms.sourcegitcommit: c395fe83d63641e0fbd7c98e51bbab224805bbcc
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/21/2019
ms.locfileid: "74265183"
---
# <a name="qa-in-power-bi-embedded"></a>ถามตอบใน Power BI Embedded

Power BI Embedded ให้คุณสามารถรวม ถามตอบ เข้าไปในแอปพลิเคชัน และอนุญาตให้ผู้ใช้ของคุณถามคำถามด้วยภาษาธรรมชาติ และได้รับคำตอบทันทีในรูปวิชวล เช่นแผนภูมิ หรือกราฟ

![การโต้ตอบกับถามตอบ ในเฟรมฝังตัว](media/qanda/embedded-qanda.gif)

มีสองโหมดสำหรับการฝังตัวถามตอบ ในแอปพลิเคชันของคุณ: **โต้ตอบ** และ**เฉพาะผลลัพธ์** โหมด**โต้ตอบ** ช่วยให้คุณสามารถพิมพ์คำถาม และแสดงคำถามอยู่ภายในวิชวล ถ้าคุณมีคำถามที่บันทึกไว้ หรือตั้งค่าคำถามที่คุณต้องการแสดง คุณสามารถใช้โหมด**เฉพาะผลลัพธ์** โดยการใส่คำถามของคุณในการกำหนดค่าการฝังตัวได้

ลองมาดูรหัส JavaScript ว่ามีลักษณะเป็นอย่างไร

```javascript
// Embed configuration used to describe the what and how to embed.
// This object is used when calling powerbi.embed within the JavaScript API.
// You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
var config= {
    type: 'qna',
    tokenType:   models.TokenType.Embed | models.TokenType.Aad,
    accessToken: access token value,
    embedUrl:    https://app.powerbi.com/qnaEmbed (groupId to be appended as query parameter if required),
    datasetIds:  array of requested data set ids (at the moment we support only one dataset),
    viewMode:    models.QnaMode.Interactive | models.QnaMode.ResultOnly,
    question:    optional parameter for Explore mode (QnaMode.Interactive) and mandatory for Render Result mode (QnaMode.ResultOnly)
};

// Get a reference to the embedded QNA HTML element
var qnaContainer = $('#qnaContainer')[0];

// Embed the QNA and display it within the div container.
var qna = powerbi.embed(qnaContainer, config);
```

## <a name="set-question"></a>ตั้งค่าคำถาม

ถ้าคุณใช้**โหมดผลลัพธ์** ด้วยคำถามที่ตั้งค่าไว้ คุณสามารถเพิ่มเติมคำถามลงในเฟรม และให้ตอบทันทีแทนที่ผลลัพธ์เดิม วิชวลที่ตรงกับคำถามใหม่จะถูกแสดงแทน

ตัวอย่างหนึ่งของการใช้งานนี้ คือรายการคำถามที่ถามบ่อย ผู้ใช้สามารถไปตามคำถามต่าง ๆ และได้รับคำตอบภายในส่วนฝังตัวเดียวกัน

**โค้ดส่วนย่อสำหรับใช้ใน JS SDK:**  

```javascript
// Get a reference to the embedded Q&A HTML element
var qnaContainer = $('#qnaContainer')[0];

// Get a reference to the embedded Q&A.
qna = powerbi.get(qnaContainer);

qna.setQuestion("This year sales")
    .then(function (result) {
        …….
    })
    .catch(function (errors) {
        …….
    });
```

## <a name="visual-rendered-event"></a>เหตุการณ์การแสดงผลวิชวล

สำหรับโหมด**โต้ตอบ** แอปพลิเคชันสามารถรับการแจ้งเตือน เหตุการณ์ข้อมูลถูกเปลี่ยนแปลง ทุกครั้งที่วิชวลเปลี่ยนแปลงตามคำถามที่กำลังพิมพ์เข้าไป

การฟังเหตุการณ์ *visualRendered* ให้คุณสามารถบันทึกคำถามไว้ใช้ภายหลัง 

**โค้ดส่วนย่อสำหรับใช้ใน JS SDK:**  

```javascript
// Get a reference to the embedded Q&A HTML element
var qnaContainer = $('#qnaContainer')[0];

// Get a reference to the embedded Q&A.
qna = powerbi.get(qnaContainer);

// qna.off removes a given event listener if it exists.
qna.off("visualRendered");

// qna.on will add an event listener.
qna.on("visualRendered", function(event) {
     …….
});
```

## <a name="embed-token"></a>โทเค็นสำหรับฝังตัว

สร้างโทเค็นฝังตัวจากชุดข้อมูล เพื่อเริ่มส่วนถามตอบ สำหรับข้อมูลเพิ่มเติม ดูที่[สร้างโทเค็น](https://docs.microsoft.com/rest/api/power-bi/embedtoken)

## <a name="next-steps"></a>ขั้นตอนถัดไป

ถ้าต้องการทดลองการฝังตัวถามตอบ ดู[ตัวอย่างการฝังตัวด้วย JavaScript](https://microsoft.github.io/PowerBI-JavaScript/demo/)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)

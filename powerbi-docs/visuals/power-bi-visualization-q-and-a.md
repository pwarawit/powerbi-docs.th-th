---
title: ใช้วิชวลถามตอบของ Power BI
description: วิธีการตั้งค่าวิชวลถามตอบของ Power BI
author: mihart
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/19/2019
ms.author: mohaali
ms.openlocfilehash: 78a74d2d49ac9eabb7d63f467c9838d370d5c314
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/09/2019
ms.locfileid: "73870840"
---
# <a name="introduction-to-power-bi-qa-visual"></a>บทนำเกี่ยวกับวิชวลถามตอบของ Power BI

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

## <a name="what-is-the-qa-visual"></a>วิชวลถามตอบคืออะไร

วิชวลถามตอบช่วยให้ผู้ใช้สามารถถามคำถามที่เป็นภาษาธรรมชาติและรับคำตอบในรูปแบบของวิชวลได้ 

![ภาพรวมของวิชวลถามตอบ](../natural-language/media/qna-visual-walkthrough.gif)

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

วิชวลถามตอบสามารถใช้เป็นเครื่องมือเพื่อช่วยให้ *ผู้ใช้งาน* ได้รับคำตอบสำหรับข้อมูลของพวกเขาอย่างรวดเร็ว และโดย*ผู้ออกแบบ* เพื่อสร้างวิชวลในรายงานโดยการคลิกสองครั้งที่ใดก็ได้บนรายงานและการใช้ภาษาธรรมชาติเพื่อเริ่มต้นใช้งาน เช่นเดียวกับวิชวลอื่นๆ วิชวลถามตอบสามารถทำการกรองข้าม/การไฮไลต์แบบเชื่อมโยง และยังสนับสนุนบุ๊กมาร์กได้ วิชวลถามตอบยังสนับสนุนธีมและตัวเลือกการจัดรูปแบบเริ่มต้นอื่น ๆ ที่พร้อมใช้งานภายใน Power BI

วิชวลถามตอบประกอบด้วยสี่องค์ประกอบหลัก

- กล่องคำถาม กล่องนี้เป็นตำแหน่งที่ผู้ใช้สามารถพิมพ์คำถามของตน และจะแสดงคำแนะนำเพื่อช่วยตอบคำถามของพวกเขา
- รายการของคำถามที่แนะนำที่มีการเติมข้อมูลไว้ล่วงหน้า
- ไอคอนเพื่อแปลงวิชวลถามตอบเป็นวิชวลมาตรฐาน 
- ไอคอนเพื่อเปิดเครื่องมือถามตอบที่ช่วยให้ผู้ออกแบบสามารถกำหนดค่ากลไกจัดการภาษาธรรมชาติเบื้องต้น

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

1. บทช่วยสอนนี้ใช้[ไฟล์ PBIX ตัวอย่างการขายและการตลาด](https://download.microsoft.com/download/9/7/6/9767913A-29DB-40CF-8944-9AC2BC940C53/Sales%20and%20Marketing%20Sample%20PBIX.pbix) 

1. จากด้านบนซ้ายของแถบเมนู Power BI Desktop เลือก **ไฟล์** > **เปิด**
   
2. ค้นหาสำเนาของ **ไฟล์ PBIX ตัวอย่างการขายและการตลาด**

1. เปิดไฟล์ในมุมมองรายงาน ![สกรีนช็อตของไอคอนมุมมองรายงาน](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. เลือก ![สกรีนช็อตของแท็บสีเหลือง](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) หากต้องการเพิ่มหน้าใหม่


ถ้าคุณเห็นข้อผิดพลาดเมื่อสร้างวิชวลถามตอบ ตรวจสอบให้แน่ใจว่าได้ดูส่วน[ข้อจำกัด](../natural-language/q-and-a-limitations.md) เพื่อดูว่าการกำหนดค่าแหล่งข้อมูลได้รับการสนับสนุนหรือไม่

## <a name="create-a-qa-visual-using-a-suggested-question"></a>สร้างวิชวลถามตอบโดยใช้คำถามที่แนะนำ
ในแบบฝึกหัดนี้ เราจะเลือกหนึ่งในคำถามที่แนะนำเพื่อสร้างวิชวลถามตอบ 

1. เริ่มต้นบนหน้ารายงานที่ว่างเปล่าและเลือกไอคอนวิชวลถามตอบจากบานหน้าต่างการแสดงภาพ

    ![บานหน้าต่างการแสดงภาพที่มีไอคอนวิชวลถามตอบที่ระบุ](media/power-bi-visualization-q-and-a/power-bi-icon.png)

2. ลากเส้นขอบเพื่อปรับขนาดวิชวล

    ![วิชวลถามตอบบนพื้นที่รายงาน](media/power-bi-visualization-q-and-a/power-bi-qna.png)

3. หากต้องการสร้างวิชวล เลือกหนึ่งในคำถามที่แนะนำหรือเริ่มพิมพ์ลงในกล่องคำถาม ในตัวอย่างนี้ เราได้เลือก**รัฐทางภูมิศาสตร์ตามผลรวมของรายได้**. Power BI เหมาะที่สุดในการเลือกชนิดของวิชวลที่จะใช้ ในกรณีนี้ คือแผนที่

    ![แผนที่วิชวลถามตอบ](media/power-bi-visualization-q-and-a/power-bi-map.png)

    แต่คุณสามารถบอก Power BI ว่าจะใช้วิชวลชนิดใดโดยการเพิ่มลงในคิวรีภาษาธรรมชาติของคุณ โปรดทราบว่าไม่ใช่วิชวลทุกชนิดที่จะทำงานหรือเข้ากับข้อมูลของคุณ ตัวอย่างเช่น ข้อมูลนี้จะไม่สร้างแผนภูมิแบบกระจายที่มีความหมาย แต่จะใช้เป็นแผนที่แบบเติม

    ![วิชวลถามตอบที่เป็นแผนที่แบบเติม](media/power-bi-visualization-q-and-a/power-bi-specify-map.png)

## <a name="create-a-qa-visual-using-a-natural-language-query"></a>สร้างวิชวลถามตอบโดยใช้คิวรีภาษาธรรมชาติ
ในตัวอย่างข้างต้น เราได้เลือกหนึ่งในคำถามที่แนะนำเพื่อสร้างวิชวลถามตอบ  ในแบบฝึกหัดนี้ เราจะพิมพ์คำถามของเราเอง ในขณะที่เราพิมพ์คำถามของเรา Power BI จะช่วยเราด้วยการกรอกข้อมูลอัตโนมัติ การให้คำแนะนำ และคำติชม

ถ้าคุณไม่แน่ใจว่าคำถามชนิดใดที่ต้องถามหรือคำศัพท์ที่จะใช้ ให้ขยาย **แสดงคำแนะนำทั้งหมด** หรือค้นหาในบานหน้าต่างเขตข้อมูลซึ่งสามารถพบได้ตามด้านขวาของพื้นที่ทำงาน การดำเนินการนี้จะทำให้คุณคุ้นเคยกับศัพท์และเนื้อหาของชุดข้อมูลการตลาดและการขาย

![พื้นที่ทำงานที่มีบานหน้าต่างแสดงคำแนะนำทั้งหมดและเขตข้อมูลที่ระบุ](media/power-bi-visualization-q-and-a/power-bi-terminology.png)


1. พิมพ์คำถามในเขตข้อมูลถามตอบ Power BI เพิ่มขีดเส้นใต้สีแดงเป็นคำที่ไม่รู้จัก เมื่อใดก็ตามที่เป็นไปได้ Power BI จะช่วยกำหนดคำที่ไม่รู้จัก  ในตัวอย่างแรกด้านล่าง ให้เลือกคำแนะนำใดก็ตามที่จะใช้ได้กับเรา  

    ![การพิมพ์คำถามในกล่องคำถามสำหรับถามตอบ](media/power-bi-visualization-q-and-a/power-bi-red-suggest.png)

2. ในขณะที่เราพิมพ์คำถามเพิ่มเติม Power BI ช่วยให้เราทราบว่าระบบไม่เข้าใจคำถามและพยายามช่วยเหลือ ในตัวอย่างด้านล่าง Power BI จะถามเราว่า "คุณหมายถึง ..." และแสดงให้เห็นวิธีการที่แตกต่างกันในการตั้งคำถามของเราโดยใช้ศัพท์จากชุดข้อมูลของเรา 

    ![วิชวลถามตอบที่แสดงคำแนะนำ](media/power-bi-visualization-q-and-a/power-bi-define.png)

5. ด้วยความช่วยเหลือของ Power BI เราสามารถตั้งคำถามด้วยศัพท์ที่เป็นที่รู้จักทั้งหมดได้ Power BI จะแสดงผลลัพธ์เป็นแผนภูมิเส้น 

    ![ผลลัพธ์ของวิชวลถามตอบ](media/power-bi-visualization-q-and-a/power-bi-type.png)


6. ลองเปลี่ยนวิชวลเป็นแผนภูมิคอลัมน์ 

    ![วิชวลถามตอบที่เพิ่ม "เป็นแผนภูมิคอลัมน์" ลงในคำถาม](media/power-bi-visualization-q-and-a/power-bi-specify-visual.png)

## <a name="format-and-customize-the-qa-visual"></a>จัดรูปแบบและปรับแต่งวิชวลถามตอบ
วิชวลถามตอบสามารถปรับแต่งได้โดยใช้บานหน้าต่างการจัดรูปแบบและโดยการใช้ธีม 

### <a name="apply-a-theme"></a>นำธีมไปใช้
เมื่อคุณเลือกธีม ธีมดังกล่าวจะถูกนำไปใช้กับหน้ารายงานทั้งหมด มีธีมมากมายให้เลือก ลองใช้จนกว่าคุณจะได้รูปลักษณ์ที่คุณต้องการ 

1. ในแถบเมนู ให้เลือกแท็บ**หน้าแรก**และเลือก**สลับธีม**. 

    ![Desktop พร้อมธีมการสลับที่เลือก](media/power-bi-visualization-q-and-a/power-bi-themes.png)

    
    
2. ในตัวอย่างนี้ เราได้เลือก**ธีมเพิ่มเติม** > **ปลอดภัยสำหรับคนตาบอดสี**

    ![วิชวลถามตอบที่ใช้ธีมตาบอดสี](media/power-bi-visualization-q-and-a/power-bi-color-blind.png)

### <a name="format-the-qa-visual"></a>จัดรูปแบบวิชวลถามตอบ
จัดรูปแบบวิชวลถามตอบ เขตข้อมูลคำถาม และวิธีการแสดงคำแนะนำ คุณสามารถเปลี่ยนทุกอย่างจากพื้นหลังของชื่อเรื่องให้เป็นสีโฮเวอร์สำหรับคำที่ไม่รู้จัก ต่อไปนี้เราได้เพิ่มพื้นหลังสีเทาลงในกล่องคำถามและเปลี่ยนเส้นใต้เป็นสีเหลืองและสีเขียว ชื่อเรื่องอยู่กึ่งกลางและมีพื้นหลังสีเหลือง 

![วิชวลถามตอบที่แสดงผลการจัดรูปแบบของเรา](media/power-bi-visualization-q-and-a/power-bi-q-and-a-format.png)

## <a name="convert-your-qa-visual-into-a-standard-visual"></a>แปลงวิชวลถามตอบเป็นวิชวลมาตรฐาน
เราได้จัดรูปแบบแผนภูมิคอลัมน์ที่ปลอดภัยสำหรับคนตาบอดสีแล้วเล็กน้อย - เพิ่มชื่อและเส้นขอบ ในตอนนี้ เราพร้อมที่จะแปลงเป็นวิชวลมาตรฐานในรายงานของเราและยังมีการปักหมุดไปยังแดชบอร์ดด้วย

เลือกไอคอน ![ไอคอนรูปเฟือง](media/power-bi-visualization-q-and-a/power-bi-convert-icon.png)เพื่อ**เปลี่ยนผลการถามตอบนี้เป็นวิชวลมาตรฐาน**

![วิชวลถามตอบที่มีลูกศรชี้ไปยังไอคอนวิชวลมาตรฐาน](media/power-bi-visualization-q-and-a/power-bi-visual-convert.png)

วิชวลนี้ไม่ใช่วิชวลถามตอบอีกต่อไป แต่เป็นแผนภูมิคอลัมน์มาตรฐาน ซึ่งสามารถปักหมุดไปยังแดชบอร์ด ในรายงาน วิชวลนี้จะทำงานเหมือนกับวิชวลมาตรฐานอื่นๆ โปรดทราบว่าบานหน้าต่างการแสดงภาพจะแสดงไอคอนแผนภูมิคอลัมน์ที่เลือกไว้แทนไอคอนวิชวลถามตอบ

ถ้าคุณกำลังใช้***บริการของ Power BI*** คุณสามารถปักหมุดวิชวลไปยังแดชบอร์ดโดยการเลือกไอคอนปักหมุดได้ในขณะนี้ 


![บริการของ Power BI ที่มีไอคอนปักหมุดที่ระบุ](media/power-bi-visualization-q-and-a/power-bi-pin.png)


## <a name="advanced-features-of-the-qa-visual"></a>คุณลักษณะขั้นสูงของวิชวลถามตอบ
การเลือกไอคอนรูปเฟืองจะเปิดบานหน้าต่างเครื่องมือวิชวลถามตอบ 

![วิชวลถามตอบที่มีไอคอนเครื่องมือที่เลือก](media/power-bi-visualization-q-and-a/power-bi-q-and-a-tooling.png)

ใช้บานหน้าต่างเครื่องมือเพื่อสอนศัพท์ถามตอบที่เครื่องมือไม่รู้จัก จัดการกับศัพท์เหล่านั้น และจัดการคำถามที่แนะนำสำหรับชุดข้อมูลและรายงานนี้ ในบานหน้าต่างเครื่องมือ คุณยังสามารถตรวจสอบคำถามที่ได้รับการถามโดยใช้วิชวลถามตอบนี้ และดูคำถามที่ได้รับการตั้งค่าสถานะโดยผู้ใช้ หากต้องการเรียนรู้เพิ่มเติม ดู[ข้อมูลเครื่องมือถามตอบ](../natural-language/q-and-a-tooling-intro.md)

![บานหน้าต่างเครื่องมือถามตอบ](media/power-bi-visualization-q-and-a/power-bi-q-and-a-tooling-pane.png)

## <a name="considerations-and-troubleshooting"></a>ข้อควรพิจารณาและการแก้ไขปัญหา
วิชวลถามตอบจะทำงานร่วมกับ Office และ Bing เพื่อพยายามจับคู่คำทั่วไปที่ไม่รู้จักกับเขตข้อมูลในชุดข้อมูลของคุณ  

## <a name="next-steps"></a>ขั้นตอนถัดไป

มีหลายวิธีที่คุณสามารถรวมภาษาธรรมชาติได้ สำหรับข้อมูลเพิ่มเติม ให้ดูบทความต่อไปนี้:

* [เครื่องมือถามตอบ](../natural-language/q-and-a-tooling-intro.md)
* [แนวทางปฏิบัติที่ดีที่สุดของการถามตอบ](../natural-language/q-and-a-best-practices.md)
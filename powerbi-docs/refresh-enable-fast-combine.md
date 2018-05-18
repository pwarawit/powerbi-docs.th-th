---
title: ปิดใช้งานการตั้งค่าความเป็นส่วนตัว
description: วิธีการเปิดใช้งานการรวมด่วนภายในเกตเวย์ส่วนบุคคลเพื่อปิดใช้งานการตั้งค่าความเป็นส่วนตัวสำหรับรีเฟรช
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 02/06/2018
ms.author: davidi
LocalizationGroup: Data refresh
ms.openlocfilehash: b8ec52f3c8bcb4051bd0ac9064786ddbfd15d9fe
ms.sourcegitcommit: 1fe3ababba34c4e7aea08adb347ec5430e0b38e4
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/22/2018
---
# <a name="disable-privacy-setting-in-power-bi-gateway---personal"></a>ปิดใช้งานการตั้งค่าความเป็นส่วนตัวใน Power BI Gateway - Personal
> [!NOTE]
> มีเกตเวย์ส่วนบุคคลเวอร์ชันใหม่สำหรับ Power BI ที่เรียกว่า **เกตเวย์ข้อมูลภายในองค์กร (โหมดส่วนบุคคล)** บทความต่อไปนี้จะอธิบายถึงเวอร์ชันก่อนหน้าของเกตเวย์ส่วนบุคคล ที่เรียกว่า **Power BI Gateway - Personal** ซึ่งจะถูกยกเลิก และหยุดทำงานหลังจากวันที่ 31 กรกฎาคม 2017 สำหรับข้อมูลเกี่ยวกับเวอร์ชันใหม่ของเกตเวย์ส่วนบุคคลรวมถึงวิธีการติดตั้งเวอร์ชันใหม่ ดูที่[**บทความเกตเวย์ข้อมูลภายในองค์กร (โหมดส่วนบุคคล)**](service-gateway-personal-mode.md) การรวมด่วนจะพร้อมใช้งานในเวอร์ชันใหม่ของเกตเวย์ส่วนบุคคล และได้อธิบายไว้ในบทความดังกล่าวด้วย
> 
> 

คุณอาจได้รับข้อผิดพลาดดังต่อไปนีตามการตั้งค่าความเป็นส่วนตัวสำหรับแหล่งข้อมูลของคุณเมื่อใช้กับเกตเวย์ส่วนบุคคล

> *เกิดข้อผิดพลาดขึ้นในระหว่างประมวลผลข้อมูลในชุดข้อมูล*
> 
> *[ไม่สามารถรวมข้อมูล] &lt;ส่วนแบบสอบถาม&gt;/&lt;... &gt;/ &lt;... &gt; กำลังเข้าถึงแหล่งข้อมูลที่มีระดับความเป็นส่วนตัวที่ไม่สามารถใช้ร่วมกันได้ โปรดสร้างชุดรวมข้อมูลนี้อีกครั้ง*
> 
> 

เพื่อหลีกเลี่ยงข้อผิดพลาดนี้ คุณสามารถเปิดใช้ **การรวมด่วน**ได้ **การรวมด่วน**จะละเว้นการตั้งค่าความเป็นส่วนตัวที่อนุญาตให้รวมแหล่งข้อมูลที่แตกต่างกันได้

> [!NOTE]
> จะไม่มีการพิิจารณาระดับความเป็นส่วนตัวเมื่อมีการรวมข้อมูล ซึ่งอาจมีการเปิดเผยข้อมูลที่อ่อนไหวหรือเป็นความลับต่อแหล่งข้อมูลอื่นได้เมื่อมีการรวมข้อมูล
> 
> 

## <a name="what-is-fast-combine"></a>การรวมด่วนคืออะไร
เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับระดับความเป็นส่วนตัวและการรวมด่วน คุณสามารถดูที่ [ระดับความเป็นส่วนตัว](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)ได้ ตามค่าเริ่มต้น ระดับความเป็นส่วนตัวจะถูกกำหนดเป็นส่วนตัวซึ่งอาจทำให้เกิดข้อผิดพลาดที่กล่าวถึงข้างต้น ทั้งนี้ เนื่องจากการตั้งค่าเป็นส่วนตัวจะแยกแหล่งข้อมูลจากแหล่งข้อมูลอื่น ตัวอย่างในกรณีที่สิ่งนี้อาจเป็นปัญหา ได้แก่ การที่แบบสอบถามมีการกำหนดพารามิเตอร์การป้อนข้อมูลจากแหล่งข้อมูลอื่น

การเปิดใช้การรวมด่วนจะละเว้นการตั้งค่าส่วนตัวและอนุญาตให้มีการดำเนินการเกิดขึ้น

## <a name="turn-on-fast-combine"></a>การเปิดใช้การรวมด่วน
คุณสามารถใช้ขั้นตอนต่อไปนี้เพื่อเปิดใช้งานการรวมด่วนสำหรับเกตเวย์ส่วนบุคคลของคุณ เกตเวย์ข้อมูลในองค์กรไม่มีการตั้งค่านี้

1. เปิด **ConnectorConfig.xml**  ซึ่งอาจเป็นหนึ่งในสองตำแหน่งบนเครื่องของคุณ  ถ้าคุณเป็นผู้ดูแลระบบบนคอมพิวเตอร์ ตำแหน่งจะเป็นดังนี้
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    ถ้าคุณไม่ใช่ผู้ดูแลระบบ ตำแหน่งจะเป็นดังนี้
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
    
2. เพิ่มองค์ประกอบ**&lt;EnableFastCombine&gt;** ที่มีค่า true เป็นไฟล์กำหนดค่า การเพิ่มองค์ประกอบนี้จะเปิดใช้ **การรวมด่วน**
   
   <pre><code>&lt;EnableFastCombine&gt;true&lt;/EnableFastCombine&gt;</code></pre>
   
   ![](media/refresh-enable-fast-combine/configfile.png)
3. จบการทำงานและเปิดใช้หน้าจอการกำหนดค่าเกตเวย์ใหม่
4. คุณจะเห็นสถานะที่แจ้งให้คุณทราบว่า มีการเปิดใช้งานการรวมด่วน
   
   ![](media/refresh-enable-fast-combine/fastcombineenabled.png)

## <a name="turn-off-fast-combine"></a>ปิดใช้การรวมด่วน
1. เปิด **ConnectorConfig.xml**  ซึ่งอาจเป็นหนึ่งในสองตำแหน่งบนเครื่องของคุณ  ถ้าคุณเป็นผู้ดูแลระบบบนคอมพิวเตอร์ ตำแหน่งจะเป็นดังนี้
   
    <pre><code>C:\Program Files\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>
   
    ถ้าคุณไม่ใช่ผู้ดูแลระบบ ตำแหน่งจะเป็นดังนี้
   
    <pre><code>C:\Users\[username]\AppData\Local\Power BI Personal Gateway\1.0\Configurator\Connector</code></pre>

2. ลบองค์ประกอบ **&lt;EnableFastCombine&gt;** ออกจากไฟล์กำหนดค่า การลบองค์ประกอบนี้จะปิดใช้ **การรวมด่วน**
3. จบการทำงานและเปิดใช้หน้าจอการกำหนดค่าเกตเวย์ใหม่
4. คุณจะไม่เห็นสถานะที่แจ้งให้คุณทราบว่า มีการเปิดใช้งาน **การรวมด่วน** อีกต่อไป

## <a name="next-steps"></a>ขั้นตอนถัดไป
[เกตเวย์ข้อมูลภายในองค์กร (โหมดส่วนตัว) - เวอร์ชันใหม่ของเกตเวย์ส่วนบุคคล](service-gateway-personal-mode.md)
[ระดับความเป็นส่วนตัว](https://support.office.com/article/Privacy-levels-Power-Query-CC3EDE4D-359E-4B28-BC72-9BEE7900B540)  
[งานแบบสอบถามทั่วไปใน Power BI Desktop](desktop-common-query-tasks.md)  
มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


---
title: ติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI
description: เรียนรู้วิธีติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/24/2019
ms.author: maggies
ms.openlocfilehash: c118e3c2f8b30635982a37c47da9fb9e337aff05
ms.sourcegitcommit: d12d84583e65ebecc8aa947b0cd5720cffdc7978
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/25/2019
ms.locfileid: "54907543"
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>ติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI
เรียนรู้วิธีติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI

เมื่อต้องสร้างรายงาน Power BI สำหรับเซิร์ฟเวอร์รายงาน Power BI คุณจำเป็นต้องดาวน์โหลดและติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI การเผยแพร่นี้จะแตกต่างจาก Power BI Desktop ที่ใช้กับบริการ Power BI ตัวอย่างเช่น เวอร์ชัน Power BI Desktop สำหรับบริการ Power BI จะมีคุณลักษณะตัวอย่างที่ไม่พร้อมใช้งานในเวอร์ชันเซิร์ฟเวอร์รายงาน Power BI จนกระทั่งหลังจากที่มีการเผยแพร่แล้ว การใช้การเผยแพรนี้จะทำให้แน่ใจว่า เซิร์ฟเวอร์รายงานสามารถโต้ตอบกับรายงานและแบบจำลองเวอร์ชันที่ทราบแล้วได้ 

ข่าวดีก็คือ คุุณสามารถติดตั้ง Power BI Desktop และ Power BI Desktop ที่ปรับให้เหมาะสมสำหรับเซิร์ฟเวอร์รายงาน Power BI ได้โดยควบคู่กันไปบนคอมพิวเตอร์เครื่องเดียวกัน

## <a name="download-and-install-power-bi-desktop"></a>ดาวน์โหลด และติดตั้ง Power BI Desktop

วิธีที่ง่ายที่สุดเพื่อให้แน่ใจว่าคุณมีเวอร์ชันล่าสุดของ Power BI Desktop ที่ปรับให้เหมาะสมสำหรับเซิร์ฟเวอร์รายงาน Power BI ก็คือ การเริ่มต้นจากพอร์ทัลเว็บของเซิร์ฟเวอร์รายงานของคุณ

1. ในพอร์ทัลเว็บเซิร์ฟเวอร์รายงาน เลือก **ดาวน์โหลด**ลูกศร > **Power BI Desktop**

    ![ดาวน์โหลด Power BI Desktop จากพอร์ทัลของเว็บ](media/install-powerbi-desktop/report-server-download-web-portal.png)

    หรือไปที่ [Microsoft Power BI Desktop](https://go.microsoft.com/fwlink/?linkid=2055039) (ที่ปรับให้เหมาะกับเซิร์ฟเวอร์รายงาน Power BI - มกราคม 2019) ในศูนย์ดาวน์โหลดของ Microsoft โดยตรง

2. ในหน้าศูนย์ดาวน์โหลด เลือก**ดาวน์โหลด**

3. ขึ้นอยู่กับคอมพิวเตอร์ของคุณ เลือก: 

    - **PBIDesktopRS.msi** (เวอร์ชัน 32 บิต) หรือ

    - **PBIDesktopRS_x64.msi** (เวอร์ชัน 64 บิต)

1. หลังจากที่คุณดาวน์โหลดตัวติดตั้งแล้ว ให้เรียกใช้ตัวช่วยติดตั้ง Power BI Desktop (มกราคม 2019)

2. ในตอนท้ายของการติดตั้ง ทำเครื่องหมายที่**เริ่มต้น Power BI Desktop ทันที**
   
    จะเริ่มต้นโดยอัตโนมัติ และคุณก็พร้อมที่จะไปต่อ

## <a name="verify-youre-using-the-correct-version"></a>ตรวจสอบว่าคุณกำลังใช้เวอร์ชันที่ถูกต้อง
เป็นเรื่องง่ายเมื่อต้องการตรวจสอบว่าคุณกำลังใช้ Power BI Desktop ที่ถูกต้องอยู่: ดูที่เปิดใช้งานหน้าจอหรือแถบชื่อเรื่องภายใน Power BI Desktop แถบชื่อเรื่องจะระบุเดือนและปีที่มีการเผยแพร่ นอกจากนี้ สีโลโก้ Power BI จะกลับกันโดยสีเหลืองจะอยู่บนพื้นดำแทนที่เป็นสีดำบนพื้นเหลือง

![แถบชื่อเรื่องสำหรับ Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI](media/install-powerbi-desktop/power-bi-report-server-desktop-jan-2019.png)

เวอร์ชัน Power BI Desktop สำหรับบริการ Power BI จะไม่มีเดือนและปีในแถบชื่อเรื่อง

## <a name="file-extension-association"></a>การเชื่อมโยงนามสกุลไฟล์
ถ้าคุณติดตั้งทั้ง Power BI Desktop และ Power BI Desktop ที่ปรับให้เหมาะสมสำหรับเซิร์ฟเวอร์รายงาน Power BI บนเครื่องเดียวกัน การติดตั้งล่าสุดของ Power BI Desktop จะมีการเชื่อมโยงไฟล์กับไฟล์ .pbix ดังนั้นแล้วเมื่อคุณดับเบิลคลิกที่ไฟล ์.pbix ก็จะเปิดใช้ Power BI Desktop ที่คุณได้ทำการติดตั้งล่าสุด

ถ้าคุณมี Power BI Desktop อยู่ แล้วติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสมสำหรับเซิร์ฟเวอร์รายงาน Power BI ไฟล์ pbix ทั้งหมดก็จะเปิดใน Power BI Desktop ที่ปรับให้เหมาะสมสำหรับเซิร์ฟเวอร์รายงาน Power BI ตามค่าเริ่มต้น ถ้าคุณต้องการให้ Power BI Desktop เป็นค่าเริ่มต้นแทนสำหรับเปิดใช้งานเมื่อเปิดไฟล์ .pbix ให้ติดตั้ง [ Power BI Desktop จาก Microsoft Store ใหม่](http://aka.ms/pbidesktopstore)

คุณสามารถเปิด Power BI Desktop เวอร์ชันที่คุณต้องการใช้ก่อนได้เสมอ จากนั้น ให้เปิดไฟล์จากภายใน Power BI Desktop

การแก้ไขรายงาน Power BI จากภายในเซิร์ฟเวอร์รายงาน Power BI หรือการสร้างรายงาน Power BI ใหม่จากพอร์ทัลเว็บมักจะเปิด Power BI Desktop เวอร์ชันที่ถูกต้องเสมอ

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด
รายงาน Power BI ในเซิร์ฟเวอร์รายงาน Power BI ในบริการของ Power BI (http://app.powerbi.com)และในแอปสำหรับอุปกรณ์เคลื่อนที่ Power BI ทำงานได้เกือบจะเหมือนกัน แต่จะมีบางคุณลักษณ์ที่แตกต่างกัน

### <a name="in-a-browser"></a>ในเบราว์เซอร์
รายงานในเซิร์ฟเวอร์รายงาน Power BI สนับสนุนการแสดงภาพทั้งหมด รวมถึง:

* วิชวลแบบกำหนดเอง

รายงานในเซิร์ฟเวอร์รายงาน Power BI ไม่สนับสนุน:

* วิชวล R
* แผนที่ ArcGIS
* การนำทางแบบแสดงเส้นนำทาง
* คุณลักษณะที่เป็นตัวอย่างใน Power BI Desktop

### <a name="in-the-power-bi-mobile-apps"></a>ในแอปสำหรับอุปกรณ์เคลื่อนที่ Power BI
รายงานในเซิร์ฟเวอร์รายงาน Power BI สนับสนุนฟังก์ชันพื้นฐานทั้งหมดใน[แอปสำหรับอุปกรณ์เคลื่อนที่ Power BI](../consumer/mobile/mobile-apps-for-mobile-devices.md) รวมถึง:

* [เค้าโครงรายงานโทรศัพท์](../desktop-create-phone-report.md): คุณสามารถปรับรายงานให้เหมาะสมกับแอปสำหรับอุปกรณ์เคลื่อนที่ Power BI ได้ บนโทรศัพท์มือถือของคุณ รายงานที่ปรับให้เหมาะสมมีไอคอนพิเศษ ![ไอคอนเค้าโครงรายงานโทรศัพท์](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-icon.png) และเค้าโครงที่เหมาะกับมือถือ
  
    ![รายงานที่ปรับให้เหมาะสมสำหรับมือถือ](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-report.png)

รายงานในเซิร์ฟเวอร์รายงาน Power BI ไม่สนับสนุนคุณลักษณะเหล่านี้ในแอปสำหรับอุปกรณ์เคลื่อนที่ Power BI:

* วิชวล R
* แผนที่ ArcGIS
* การแสดงผลด้วยภาพแบบกำหนดเอง
* การนำทางแบบแสดงเส้นนำทาง
* Geofiltering หรือรหัสแท่ง

## <a name="power-bi-desktop-for-earlier-versions-of-power-bi-report-server"></a>Power BI Desktop สำหรับเซิร์ฟเวอร์รายงาน Power BI เวอร์ชันก่อนหน้านี้

ถ้าเซิร์ฟเวอร์รายงานของคุณเป็นเวอร์ชันก่อนหน้า คุณจำเป็นต้องมี Power BI Desktop เวอร์ชันที่สอดคล้องกัน นี่คือ เวอร์ชันก่อนหน้า

- Microsoft Power BI Desktop ([ปรับให้เหมาะสมสำหรับเซิร์ฟเวอร์รายงาน Power BI - มิถุนายน 2018](https://www.microsoft.com/download/details.aspx?id=57271))

## <a name="next-steps"></a>ขั้นตอนถัดไป
หลังจากที่ติดตั้ง Power BI Desktop แล้ว คุณสามารถเริ่มการสร้างรายงาน Power BI ได้

[สร้างรายงาน Power BI สำหรับเซิร์ฟเวอร์รายงาน Power BI](quickstart-create-powerbi-report.md)  
[เซิร์ฟเวอร์รายงาน Power BI คืออะไร](get-started.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](https://community.powerbi.com/)


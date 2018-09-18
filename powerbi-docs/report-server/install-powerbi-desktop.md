---
title: ติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI
description: เรียนรู้วิธีติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/24/2018
ms.author: maggies
ms.openlocfilehash: d3b7ace4fe611cc55965f96f770caf7b4ebf21b1
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/12/2018
ms.locfileid: "44726397"
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>ติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI
เรียนรู้วิธีติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI

เมื่อต้องสร้างรายงาน Power BI สำหรับเซิร์ฟเวอร์รายงาน Power BI คุณจำเป็นต้องดาวน์โหลดและติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI การเผยแพร่นี้จะแตกต่างจาก Power BI Desktop ที่ใช้กับบริการ Power BI ตัวอย่างเช่น เวอร์ชัน Power BI Desktop สำหรับบริการ Power BI จะมีคุณลักษณะตัวอย่างที่ไม่พร้อมใช้งานในเวอร์ชันเซิร์ฟเวอร์รายงาน Power BI จนกระทั่งหลังจากที่มีการเผยแพร่แล้ว การใช้การเผยแพรนี้จะทำให้แน่ใจว่า เซิร์ฟเวอร์รายงานสามารถโต้ตอบกับรายงานและแบบจำลองเวอร์ชันที่ทราบแล้วได้ 

ข่าวดีก็คือ คุุณสามารถติดตั้ง Power BI Desktop และ Power BI Desktop ที่ปรับให้เหมาะสมสำหรับเซิร์ฟเวอร์รายงาน Power BI ได้โดยควบคู่กันไปบนคอมพิวเตอร์เครื่องเดียวกัน

## <a name="download-and-install-power-bi-desktop"></a>ดาวน์โหลดและติดตั้ง Power BI Desktop

วิธีที่ง่ายที่สุดเพื่อให้แน่ใจว่าคุณมีเวอร์ชันล่าสุดของ Power BI Desktop ที่ปรับให้เหมาะสมสำหรับเซิร์ฟเวอร์รายงาน Power BI ก็คือ การเริ่มต้นจากพอร์ทัลเว็บของเซิร์ฟเวอร์รายงานของคุณ

1. ในพอร์ทัลเว็บเซิร์ฟเวอร์รายงาน เลือก **ดาวน์โหลด**ลูกศร > **Power BI Desktop**

    ![ดาวน์โหลด Power BI Desktop จากพอร์ทัลเว็บ](media/install-powerbi-desktop/report-server-download-web-portal.png)

    หรือคุณสามารถไปที่ [Microsoft Power BI Desktop](https://www.microsoft.com/download/details.aspx?id=56723) (ปรับให้เหมาะสมแล้วสำหรับเซิร์ฟเวอร์รายงาน Power BI - มีนาคม 2018) ในศูนย์ดาวน์โหลดของ Microsoft ได้โดยตรง

2. ในหน้าศูนย์ดาวน์โหลด เลือก **ดาวน์โหลด**

3. ขึ้นอยู่กับคอมพิวเตอร์ของคุณ เลือก: 

    - **PBIDesktopRS.msi** (เวอร์ชัน 32 บิต) หรือ

    - **PBIDesktopRS_x64.msi** (เวอร์ชัน 64 บิต)

1. หลังจากที่คุณดาวน์โหลดตัวติดตั้ง เรียกใช้ตัวช่วยสร้างการตั้งค่า Power BI Desktop (ตุลาคม 2017)
2. ในตอนท้ายของการติดตั้ง ตรวจสอบ **เริ่มต้น Power BI Desktop ตอนนี้**
   
    ซึ่งจะเริ่มต้นโดยอัตโนมัติ และคุณก็พร้อมทำงานต่อได้

## <a name="verify-you-are-using-the-correct-version"></a>ตรวจสอบว่า คุณกำลังใช้เวอร์ชันที่ถูกต้อง
คุณสามารถตรวจสอบว่า คุณกำลังใช้ Power BI Desktop ที่ถูกต้อง ได้โดยการค้นหาหน้าจอเปิดใช้งานหรือแถบชื่อเรื่องแถบภายใน Power BI Desktop แถบชื่อเรื่องจะระบุเดือนและปีที่มีการเผยแพร่

![แถบชื่อเรื่องสำหรับ Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI](media/quickstart-create-powerbi-report/report-server-desktop-march-2018.png)

เวอร์ชัน Power BI Desktop สำหรับบริการ Power BI จะไม่มีเดือนและปีในแถบชื่อเรื่อง

## <a name="file-extension-association"></a>การเชื่อมโยงนามสกุลไฟล์
ถ้าคุณติดตั้งทั้ง Power BI Desktop และ Power BI Desktop ที่ปรับให้เหมาะสมสำหรับเซิร์ฟเวอร์รายงาน Power BI บนเครื่องเดียวกัน การติดตั้งล่าสุดของ Power BI Desktop ก็จะมีการเชื่อมโยงไฟล์กับ .pbix ซึ่งหมายความว่า เมื่อคุณดับเบิลคลิกที่ไฟล์ pbix ก็จะเปิดใช้ Power BI Desktop ที่มีการติดตั้งล่าสุด

ถ้าคุณมี Power BI Desktop อยู่ แล้วติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI ไฟล์ pbix ทั้งหมดก็จะเปิดใน Power BI Desktop ที่ปรับให้เหมาะสมสำหรับเซิร์ฟเวอร์รายงาน Power BI ตามค่าเริ่มต้น ถ้าคุณต้องการให้ Power BI Desktop เป็นค่าเริ่มต้นแทนสำหรับเปิดใช้งานเมื่อเปิดไฟล์ pbix ให้ติดตั้ง Power BI Desktop จากบริการ Power BI

คุณสามารถเปิด Power BI Desktop เวอร์ชันที่คุณต้องการใช้ก่อนได้เสมอ จากนั้น ให้เปิดไฟล์จากภายใน Power BI Desktop

การแก้ไขรายงาน Power BI จากภายในเซิร์ฟเวอร์รายงาน Power BI หรือการสร้างรายงาน Power BI ใหม่จากพอร์ทัลเว็บจะเปิด Power BI Desktop เวอร์ชันที่ถูกต้องเสมอ

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด
รายงานในเซิร์ฟเวอร์รายงาน Power BI และบริการของ Power BI (http://powerbi.com) ทำงานเกือบเหมือนกัน แต่มีความแตกต่างในบางคุณลักษณะ

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

* [เค้าโครงรายงานโทรศัพท์](../desktop-create-phone-report.md): คุณสามารถรายงานให้เหมาะสำหรับแอปสำหรับอุปกรณ์เคลื่อนที่ Power BI ได้ บนโทรศัพท์มือถือของคุณ รายงานที่ปรับให้เหมาะสมมีไอคอนพิเศษ ![ไอคอนเค้าโครงรายงานโทรศัพท์](media/quickstart-create-powerbi-report/power-bi-rs-mobile-optimized-icon.png) และเค้าโครงที่เหมาะกับมือถือ
  
    ![รายงานที่ปรับให้เหมาะสมสำหรับมือถือ](media/quickstart-create-powerbi-report/power-bi-rs-mobile-optimized-report.png)

รายงานในเซิร์ฟเวอร์รายงาน Power BI ไม่สนับสนุนคุณลักษณะเหล่านี้ในแอปสำหรับอุปกรณ์เคลื่อนที่ Power BI:

* วิชวล R
* แผนที่ ArcGIS
* การแสดงผลด้วยภาพแบบกำหนดเอง
* การนำทางแบบแสดงเส้นนำทาง
* Geofiltering หรือรหัสแท่ง

## <a name="power-bi-desktop-for-earlier-versions-of-power-bi-report-server"></a>Power BI Desktop สำหรับเซิร์ฟเวอร์รายงาน Power BI เวอร์ชันก่อนหน้านี้

ถ้าเซิร์ฟเวอร์รายงานของคุณเป็นเวอร์ชันก่อนหน้า คุณจำเป็นต้องมี Power BI Desktop เวอร์ชันที่สอดคล้องกัน ในที่นี้ มีสองเวอร์ชันก่อนหน้า

- Microsoft Power BI Desktop ([ปรับให้เหมาะสมสำหรับ เซิร์ฟเวอร์รายงาน Power BI - ตุลาคม 2017](https://www.microsoft.com/download/details.aspx?id=56136))
- Microsoft Power BI Desktop ([ปรับให้เหมาะสมสำหรับ เซิร์ฟเวอร์รายงาน Power BI - มิถุนายน 2017](https://www.microsoft.com/download/details.aspx?id=55330))

## <a name="next-steps"></a>ขั้นตอนถัดไป
หลังจากที่ติดตั้ง Power BI Desktop แล้ว คุณสามารถเริ่มการสร้างรายงาน Power BI ได้

[สร้างรายงาน Power BI สำหรับเซิร์ฟเวอร์รายงาน Power BI](quickstart-create-powerbi-report.md)  
[เซิร์ฟเวอร์รายงาน Power BI คืออะไร](get-started.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)


---
title: ฝังรายงานโดยใช้ iFrame
description: ฝังรายงานเซิร์ฟเวอร์รายงาน Power BI ใน iFrame ใน SharePoint Server
author: markingmyname
ms.author: maghan
ms.date: 05/04/2018
ms.topic: quickstart
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 4730bef0e7f1fc47a4a59a0129640760714fe2e0
ms.sourcegitcommit: 80961ace38ff9dac6699f81fcee0f7d88a51edf4
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/13/2019
ms.locfileid: "56223340"
---
# <a name="quickstart-embed-a-power-bi-report-server-report-using-an-iframe-in-sharepoint-server"></a>เริ่มต้นใช้งานด่วน: ฝังรายงานเซิร์ฟเวอร์รายงาน Power BI โดยใช้ iFrame ใน SharePoint Server

ในการเริ่มต้นด่วนนี้ คุณจะได้เรียนรู้วิธีการฝังรายงานเซิร์ฟเวอร์รายงาน Power BI โดยใช้ iFrame ในหน้า SharePoint ถ้าคุณกำลังทำงานกับ SharePoint Online เซิร์ฟเวอร์รายงาน Power BI ต้องสามารถเข้าถึงแบบสาธารณะได้ ใน SharePoint Online, Power BI Web Part ที่ทำงานกับบริการของ Power BI ไม่ทำงานกับเซิร์ฟเวอร์รายงาน Power BI 

![ตัวอย่าง iFrame](media/quickstart-embed/quickstart_embed_01.png)
## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
* คุณจะต้องมี[เซิร์ฟเวอร์รายงาน Power BI](https://powerbi.microsoft.com/report-server/) ที่ติดตั้งและกำหนดค่าแล้ว
* คุณจะต้องมี [Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI](install-powerbi-desktop.md) ติดตั้งแล้ว
* คุณจะต้องมีสภาพแวดล้อม [SharePoint](https://docs.microsoft.com/sharepoint/install/install) ที่ติดตั้งและกำหนดค่าแล้ว

## <a name="creating-the-power-bi-report-server-report-url"></a>การสร้าง URL รายงานเซิร์ฟเวอร์รายงาน Power BI

1. ดาวน์โหลดตัวอย่างจาก GitHub - [การสาธิตบล็อก](https://github.com/Microsoft/powerbi-desktop-samples)

    ![ดาวน์โหลดไฟล์ PBIX ตัวอย่าง](media/quickstart-embed/quickstart_embed_14.png)

2. เปิดไฟล์ PBIX ตัวอย่างจาก GitHub ใน **Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI**

    ![เครื่องมือ PBI RS Desktop](media/quickstart-embed/quickstart_embed_02.png)

3. บันทึกรายงานไปยัง**เซิร์ฟเวอร์รายงาน Power BI** 

    ![บันทึก PBI RS](media/quickstart-embed/quickstart_embed_03.png)

4. ดูรายงานใน**พอร์ทัลของเว็บ**

    ![พอร์ทัลของเว็บ](media/quickstart-embed/quickstart_embed_04.png)

### <a name="capturing-the-url-parameter"></a>การจับพารามิเตอร์ URL

เมื่อคุณมี URL ของคุณแล้ว คุณสามารถสร้าง iFrame ภายในหน้า SharePoint เพื่อโฮสต์รายงาน สำหรับ URL รายงานเซิร์ฟเวอร์รายงาน Power BI ใด ๆ คุณสามารถเพิ่มพารามิเตอร์ querystring `?rs:embed=true` เพื่อฝังรายงานของคุณลงใน iFrame ได้ 

   ตัวอย่างเช่น:
    ``` 
    http://myserver/reports/powerbi/Sales?rs:embed=true
    ```
## <a name="embedding-a-power-bi-report-server-report-in-a-sharepoint-iframe"></a>การฝังรายงานเซิร์ฟเวอร์รายงาน Power BI ใน SharePoint iFrame

1. นำทางไปยัง SharePoint หน้า**เนื้อหาของไซต์**

    ![หน้าเนื้อหาของไซต์](media/quickstart-embed/quickstart_embed_05.png)

2. เลือกหน้าที่คุณต้องการเพิ่มรายงานของคุณ

    ![แอปหน้าเนื้อหาของไซต์](media/quickstart-embed/quickstart_embed_06.png)

3. เลือกที่รูปเฟืองด้านบนขวา แล้วเลือก**แก้ไขหน้า**

    ![ตัวเลือกแก้ไขหน้า](media/quickstart-embed/quickstart_embed_07.png)

4. เลือก**เพิ่ม Web Part**

    ![เพิ่ม Web Part](media/quickstart-embed/quickstart_embed_08.png)

5. ภายใต้**ประเภท** เลือก**สื่อและเนื้อหา** ภายใต้**ส่วน** เลือก**ตัวแก้ไขเนื้อหา** แล้วเลือก**เพิ่ม**

    ![เลือกตัวแก้ไขเนื้อหา Web Part](media/quickstart-embed/quickstart_embed_09.png) ![เลือกเพิ่ม](media/quickstart-embed/quickstart_embed_091.png)

6. เลือก**คลิกที่นี่เพื่อเพิ่มเนื้อหาใหม่**

    ![เพิ่มเนื้อหาใหม่](media/quickstart-embed/quickstart_embed_10.png)

7. ใน ribbon เลือกแท็บ**รูปแบบข้อความ** แล้วเลือก**แก้ไขแหล่งข้อมูล**

     ![แก้ไขแหล่งข้อมูล](media/quickstart-embed/quickstart_embed_11.png)

8. ในหน้าต่างแก้ไขแหล่งข้อมูล วางรหัส iFrame ของคุณ แล้วเลือกตกลง

    ![รหัส iFrame](media/quickstart-embed/quickstart_embed_12.png)

     ตัวอย่างเช่น:
     ```html
     <iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
     ```

9. ใน ribbon เลือกแท็บ**หน้า** และเลือก**หยุดการแก้ไข**

    ![หยุดการแก้ไข](media/quickstart-embed/quickstart_embed_13.png)

10. ตอนนี้ คุณควรจะเห็นรายงานบนหน้า

    ![ตัวอย่าง iFrame](media/quickstart-embed/quickstart_embed_01.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป

[เริ่มต้นใช้งานด่วน: สร้างรายงาน Power BI สำหรับเซิร์ฟเวอร์รายงาน Power BI](quickstart-create-powerbi-report.md)  
[เริ่มต้นใช้งานด่วน: สร้างรายงานแบบแบ่งหน้าสำหรับเซิร์ฟเวอร์รายงาน Power BI](quickstart-create-paginated-report.md)  

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](https://community.powerbi.com/) 
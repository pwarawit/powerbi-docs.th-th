---
title: ฝังรายงานเซิร์ฟเวอร์รายงาน Power BI โดยใช้ iFrame ใน SharePoint Server
description: บทความนี้แสดงวิธีการฝังรายงานเซิร์ฟเวอร์รายงาน Power BI ใน iFrame ใน SharePoint Server
author: maggiesMSFT
ms.author: maggies
ms.date: 08/12/2019
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.custom: mvc
ms.openlocfilehash: 4e7616ec3ce6552130848bc0508bf8b9ac8ac965
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/09/2020
ms.locfileid: "75762611"
---
# <a name="embed-a-power-bi-report-server-report-using-an-iframe-in-sharepoint-server"></a>ฝังรายงานเซิร์ฟเวอร์รายงาน Power BI โดยใช้ iFrame ใน SharePoint Server

ในบทความนี้ คุณจะได้เรียนรู้วิธีการฝังรายงานเซิร์ฟเวอร์รายงาน Power BI โดยใช้ iFrame ในหน้า SharePoint ถ้าคุณกำลังทำงานกับ SharePoint Online เซิร์ฟเวอร์รายงาน Power BI ต้องสามารถเข้าถึงแบบสาธารณะได้ ใน SharePoint Online, Power BI Web Part ที่ทำงานกับบริการของ Power BI ไม่ทำงานกับเซิร์ฟเวอร์รายงาน Power BI  

![ตัวอย่าง iFrame](media/quickstart-embed/quickstart_embed_01.png)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น
* ติดตั้งและกำหนดค่า [เซิร์ฟเวอร์รายงาน Power BI](https://powerbi.microsoft.com/report-server/) แล้ว
* ติดตั้ง [Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI](install-powerbi-desktop.md) แล้ว
* ติดตั้งและกำหนดค่า [SharePoint](https://docs.microsoft.com/sharepoint/install/install) แล้ว
* สามารถรองรับ Internet Explorer 11 ได้เฉพาะเมื่อมีการตั้งค่าโหมดเอกสารเป็นโหมด IE11 (Edge) หรือเมื่อใช้ SharePoint Online คุณอาจใช้เบราว์เซอร์อื่นๆ ที่รองรับกับ SharePoint ภายในองค์กรและ SharePoint Online

## <a name="create-the-power-bi-report-url"></a>สร้าง URL ของรายงาน Power BI

1. ดาวน์โหลดตัวอย่างจาก GitHub [การสาธิตบล็อก](https://github.com/Microsoft/powerbi-desktop-samples) เลือก **โคลนหรือดาวน์โหลด**, จากนั้นเลือก **ดาวน์โหลด ZIP**

    ![ดาวน์โหลดไฟล์ PBIX ตัวอย่าง](media/quickstart-embed/quickstart_embed_14.png)

2. Unzip ไฟล์และเปิดไฟล์ .pbix ตัวอย่างใน Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI

    ![เครื่องมือ PBI RS Desktop](media/quickstart-embed/quickstart_embed_02.png)

3. บันทึกรายงานไปยัง**เซิร์ฟเวอร์รายงาน Power BI** 

    ![บันทึก PBI RS](media/quickstart-embed/quickstart_embed_03.png)

4. ดูรายงานในพอร์ทัลของเว็บเซิร์ฟเวอร์รายงาน Power BI

    ![เว็บพอร์ทัล](media/quickstart-embed/quickstart_embed_04.png)

### <a name="capture-the-url-parameter"></a>จับภาพพารามิเตอร์ URL

หลังจากคุณมี URL ของคุณแล้ว คุณสามารถสร้าง iFrame ภายในหน้า SharePoint เพื่อโฮสต์รายงาน สำหรับ URL ของรายงานเซิร์ฟเวอร์รายงาน Power BI เพิ่มพารามิเตอร์สตริงคิวรีต่อไปนี้เพื่อฝังรายงานของคุณใน SharePoint iFrame: `?rs:embed=true`

   ตัวอย่างเช่น:
    ``` 
    https://myserver/reports/powerbi/Sales?rs:embed=true
    ```
## <a name="embed-the-report-in-a-sharepoint-iframe"></a>ฝังรายงานใน SharePoint iFrame

1. นำทางไปยัง SharePoint หน้า**เนื้อหาของไซต์**

    ![หน้าเนื้อหาของไซต์](media/quickstart-embed/quickstart_embed_05.png)

2. เลือกหน้าที่คุณต้องการเพิ่มรายงานของคุณ

    ![แอปหน้าเนื้อหาของไซต์](media/quickstart-embed/quickstart_embed_06.png)

3. เลือกที่ไอคอนรูปเฟืองด้านบนขวา แล้วเลือก**แก้ไขหน้า**

    ![ตัวเลือกแก้ไขหน้า](media/quickstart-embed/quickstart_embed_07.png)

4. เลือก **เพิ่ม Web Part**

5. ภายใต ้**ประเภท** เลือก **สื่อและเนื้อหา** ภายใต ้**ส่วน** เลือก**ตัวแก้ไขเนื้อหา** แล้วเลือก**เพิ่ม**

    ![เลือก Web Part ตัวแก้ไขเนื้อหา](media/quickstart-embed/quickstart_embed_09.png)

6. เลือก**คลิกที่นี่เพื่อเพิ่มเนื้อหาใหม่**

7. จากเมนูด้านบน เลือก **จัดรูปแบบข้อความ**แล้วเลือก**แก้ไขแหล่งข้อมูล**

     ![แก้ไขแหล่งข้อมูล](media/quickstart-embed/quickstart_embed_11.png)

8. ในหน้าต่าง**แก้ไขแหล่งข้อมูล** วางรหัส iFrame ของคุณใน**HTML Source** แล้วเลือก **ตกลง**

    ![รหัส iFrame](media/quickstart-embed/quickstart_embed_12.png)

     ตัวอย่างเช่น:
     ```html
     <iframe width="800" height="600" src="https://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
     ```

9. ในเมนูด้านบน เลือก**หน้า**แล้วเลือก**หยุดการแก้ไข**

    ![หยุดการแก้ไข](media/quickstart-embed/quickstart_embed_13.png)

    รายงานจะปรากฏขึ้นบนหน้า

    ![ตัวอย่าง iFrame](media/quickstart-embed/quickstart_embed_01.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป

- [สร้างรายงาน Power BI สำหรับเซิร์ฟเวอร์รายงาน Power BI](quickstart-create-powerbi-report.md)  
- [สร้างรายงานที่มีการแบ่งหน้าสำหรับเซิร์ฟเวอร์รายงาน Power BI](quickstart-create-paginated-report.md)  

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/) 

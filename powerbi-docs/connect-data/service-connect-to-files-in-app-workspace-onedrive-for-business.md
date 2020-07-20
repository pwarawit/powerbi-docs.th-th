---
title: เชื่อมต่อกับไฟล์ใน OneDrive สำหรับพื้นที่ทำงาน Power BI
description: อ่านเกี่ยวกับการจัดเก็บ และการเชื่อมต่อกับไฟล์ Excel, CSV และ Power BI Desktop บน OneDrive สำหรับพื้นที่ทำงานของ Power BI
author: maggiesMSFT
ms.reviewer: lukasz
ms.service: powerbi
ms.topic: how-to
ms.date: 04/15/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 0016c5af8d8e9e154abf3c9e94dc6330a73d358d
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/10/2020
ms.locfileid: "86216262"
---
# <a name="connect-to-files-stored-in-onedrive-for-your-power-bi-workspace"></a>เชื่อมต่อไปยังไฟล์ที่จัดเก็บไว้ใน OneDrive สำหรับพื้นที่ทำงานของ Power BI ของคุณ
หลังจากที่คุณ [สร้างพื้นที่ทำงานใน Power BI](../collaborate-share/service-create-distribute-apps.md) คุณสามารถจัดเก็บไฟล์ Excel, CSV และ Power BI Desktop ของคุณบน OneDrive for Business สำหรับพื้นที่ทำงานของ Power BI ของคุณ คุณสามารถปรับปรุงแฟ้มที่คุณเก็บไว้ใน OneDrive การอัปเดตเหล่านั้นมีผลในรายงาน Power BI และแดชบอร์ดที่ยึดตามไฟล์เหล่านั้นโดยอัตโนมัติ 

> [!NOTE]
> ประสบการณ์พื้นที่ทำงานใหม่จะเปลี่ยนความสัมพันธ์ระหว่างพื้นที่ทำงาน Power BI และ Microsoft 365 Group คุณจะไม่สามารถสร้าง Microsoft 365 Group โดยอัตโนมัติทุกครั้งที่คุณสร้างพื้นที่ทำงานใหม่ อ่านเกี่ยวกับ [สร้างพื้นที่ทำงานใหม่](../collaborate-share/service-create-the-new-workspaces.md)

การเพิ่มไฟล์ลงในพื้นที่ทำงานของคุณเป็นกระบวนการแบบสองขั้นตอน: 

1. ก่อนอื่น คุณ[อัปโหลดไฟล์ไปยัง OneDrive for Business](service-connect-to-files-in-app-workspace-onedrive-for-business.md#1-upload-files-to-the-onedrive-for-business-for-your-workspace)สำหรับพื้นที่ทำงานของคุณ
2. แล้วคุณ[เชื่อมต่อกับไฟล์เหล่านั้นจาก Power BI](service-connect-to-files-in-app-workspace-onedrive-for-business.md#2-import-excel-files-as-datasets-or-as-excel-online-workbooks)

> [!NOTE]
> พื้นที่ทำงานใช้ได้กับ [Power BI Pro](../fundamentals/service-features-license-type.md) เท่านั้น
> 

## <a name="1-upload-files-to-the-onedrive-for-business-for-your-workspace"></a>1 อัปโหลดไฟล์ไปยัง OneDrive for Business สำหรับพื้นที่ทำงานของคุณ
1. ใน Power BI service เลือกลูกศรอยู่ถัดจากพื้นที่ทำงาน > เลือกจุดไข่ปลา ( **...** ) ถัดจากชื่อพื้นที่ทำงานของคุณ 
   
   ![ภาพหน้าจอของพื้นที่ทำงาน Power BI ที่แสดงชื่อพื้นที่ทำงานที่เลือก](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-ellipsis.png)
2. เลือก**ไฟล์**เพื่อเปิด OneDrive for Business สำหรับพื้นที่ทำงานบน Microsoft 365
   
   > [!NOTE]
   > ถ้าคุณไม่เห็น**ไฟล์**บนเมนูพื้นที่ทำงาน ให้เลือก**สมาชิก**เพื่อเปิด OneDrive for Business สำหรับพื้นที่ทำงาน ที่นั่น เลือก**ไฟล์** Microsoft 365 ตั้งค่าตำแหน่งที่เก็บข้อมูล OneDrive สำหรับไฟล์พื้นที่ทำงานของกลุ่มของแอปของคุณ กระบวนการนี้อาจใช้เวลาสักครู่
   > 
   > 
3. ที่นี่ คุณสามารถอัปโหลดไฟล์ไปยัง OneDrive for Business สำหรับพื้นที่ทำงานของคุณ เลือก**อัปโหลด**และนำทางไปยังไฟล์ของคุณ
   
   ![ภาพหน้าจอของ OneDrive for Business ที่แสดงวิธีการนำทางเพื่ออัปโหลดไฟล์](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grpfilesonedrive.png)

## <a name="2-import-excel-files-as-datasets-or-as-excel-online-workbooks"></a>2 นำเข้าไฟล์ Excel ในฐานะชุดข้อมูลหรือในฐานะสมุดงาน Excel Online
เมื่อไฟล์ของคุณอยู่ใน OneDrive for Business สำหรับพื้นที่ทำงาน คุณมีตัวเลือกดังนี้ คุณสามารถ: 

* [นำเข้าข้อมูลจากเวิร์กบุ๊ก Excel เป็นชุดข้อมูล](service-get-data-from-files.md) จากนั้นใช้ข้อมูลเพื่อสร้างรายงานและแดชบอร์ดที่คุณสามารถดูในเว็บเบราว์เซอร์ และบนอุปกรณ์มือถือ
* หรือ[เชื่อมต่อกับเวิร์กบุ๊ก Excel เต็มใน Power BI](service-excel-workbook-files.md)และแสดงไว้เหมือนกับที่จะปรากฏขึ้นใน Excel Online

### <a name="import-or-connect-to-the-files-in-your-workspace"></a>นำเข้า หรือเชื่อมต่อกับไฟล์ในพื้นที่ทำงานของคุณ
1. ใน Power BI ให้สลับไปยังพื้นที่ทำงาน ดังนั้นชื่อพื้นที่ทำงานจะอยู่ที่มุมบนซ้าย 
2. เลือก**รับข้อมูล**ที่ด้านล่างของบานหน้าต่างนำทาง 
   
   ![ภาพหน้าจอของปุ่มรับข้อมูล ที่แสดงในบานหน้าต่างนำทาง](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-get-data-button.png)
3. ในกล่อง**ไฟล์** เลือก**รับ**
   
   ![ภาพหน้าจอของกล่องโต้ตอบไฟล์ ที่แสดงปุ่มรับ](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_getfiles.png)
4. เลือก**OneDrive** - *ชื่อพื้นที่ทำงานของคุณ*
   
    ![ภาพหน้าจอของไทล์สามตัวเพื่อเลือกพื้นที่ทำงานของคุณ ที่แสดงไฟล์ภายในเครื่อง OneDrive และ SharePoint](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_grp_one_drive_shrpt.png)
5. เลือกไฟล์คุณต้อง > **เชื่อมต่อ**
   
    ในจุดนี้คุณตัดสินใจว่า จะ[นำเข้าข้อมูลจากสมุดงาน Excel](service-get-data-from-files.md)หรือ[เชื่อมต่อไปยังเวิร์กบุ๊ก Excel ทั้งหมด](service-excel-workbook-files.md)
6. เลือก**นำเข้า**หรือ**เชื่อมต่อ**
   
    ![ภาพหน้าจอของกล่องโต้ตอบ OneDrive for Business ที่แสดงนำเข้าจาก Excel หรือเชื่อมต่อกับ Excel](media/service-connect-to-files-in-app-workspace-onedrive-for-business/pbi_importexceldataorwholecrop.png)
7. ถ้าคุณเลือก**นำเข้า** แล้วเวิร์กบุ๊กปรากฏขึ้นบนแท็บ**ชุดข้อมูล** 
   
    ![ภาพหน้าจอของพื้นที่ทำงานใน Power BI ที่แสดงแท็บชุดข้อมูล](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-import.png)
   
    ถ้าคุณเลือก**เชื่อมต่อ**แล้วเวิร์กบุ๊กอยู่บนแท็บ**สมุดงาน**
   
    ![ภาพหน้าจอของพื้นที่ทำงานใน Power BI ที่แสดงแท็บสมุดงาน](media/service-connect-to-files-in-app-workspace-onedrive-for-business/power-bi-app-excel-file-connect.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [สร้างแอปและพื้นที่ทำงานใน Power BI](../collaborate-share/service-create-distribute-apps.md)
* [นำเข้าข้อมูลจากเวิร์กบุ๊ก Excel](service-get-data-from-files.md)
* [เชื่อมต่อไปยังเวิร์กบุ๊ก Excel ทั้งหมด](service-excel-workbook-files.md)
* มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)
* มีคำติชมหรือไม่ เยี่ยมชม[แนวคิด Power BI](https://ideas.powerbi.com/forums/265200-power-bi)

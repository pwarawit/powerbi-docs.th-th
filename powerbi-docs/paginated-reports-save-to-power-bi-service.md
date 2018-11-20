---
title: เผยแพร่รายงานแบบแบ่งหน้าไปยังบริการของ Power BI | Microsoft Docs
description: ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการเผยแพร่รายงานแบบแบ่งหน้าไปยังบริการของ Power BI โดยการอัปโหลดจากคอมพิวเตอร์ของคุณเอง
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: report-builder
ms.topic: conceptual
ms.date: 11/05/2018
ms.author: maggies
ms.openlocfilehash: 6f2d1a4e4de87ea6eb63826b59286a9abd54b94f
ms.sourcegitcommit: b23fdcc0ceff5acd2e4d52b15b310068236cf8c7
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/07/2018
ms.locfileid: "51268856"
---
# <a name="publish-a-paginated-report-to-the-power-bi-service"></a>เผยแพร่รายงานแบบแบ่งหน้าไปยังบริการของ Power BI

ในบทความนี้ คุณจะได้เรียนรู้เกี่ยวกับการเผยแพร่รายงานแบบแบ่งหน้าไปยังบริการของ Power BI โดยการอัปโหลดจากคอมพิวเตอร์ของคุณเอง คุณสามารถอัปโหลดรายงานแบบแบ่งหน้าไปยัง "พื้นที่ทำงานของฉัน" หรือพื้นที่ทำงานอื่นได้ ตราบเท่าที่พื้นที่ทำงานนั้นอยู่ในความจุ Premium มองหาไอคอนรูปข้าวหลามตัด ![ไอคอนรูปข้าวหลามตัดของความจุ Power BI Premium](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) ถัดจากชื่อพื้นที่ทำงาน 

ถ้าแหล่งข้อมูลของรายงานของคุณอยู่ในองค์กร คุณต้อง[สร้างเกตเวย์](#create-a-gateway-to-an-on-premises-data-source)หลังจากที่อัปโหลดรายงานแล้ว

## <a name="add-a-workspace-to-a-premium-capacity"></a>เพิ่มพื้นที่ทำงานไปยังความจุพรีเมียม

ถ้าพื้นที่ทำงานไม่มีไอคอนรูปข้าวหลามตัด ![ไอคอนรูปข้าวหลามตัดของความจุ Power BI Premium](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) อยู่ถัดจากชื่อ คุณต้องเพิ่มพื้นที่ทำงานไปยังความจุพรีเมียม 

1. เลือก**พื้นที่ทำงาน** เลือกจุดไข่ปลา (**...**) ที่อยู่ถัดจากชื่อของพื้นที่ทำงาน จากนั้นเลือก**แก้ไขพื้นที่ทำงาน**

    ![เลือก แก้ไขพื้นที่ทำงาน](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace.png)

1. ในกล่องโต้ตอบ **แก้ไขพื้นที่ทำงาน** ให้คุณขยาย**ขั้นสูง** จากนั้นเลื่อน **ความจุเฉพาะ** ไปยัง **เปิด**

    ![เลือกความจุเฉพาะ](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-edit-workspace-dialog.png)

   คุณอาจไม่สามารถเปลี่ยนได้ ถ้าเปลี่ยนไม่ได้ โปรดติดต่อผู้ดูแลความจุ Power BI Premium เพื่อให้สิทธิ์ในการกำหนดกับคุณ เพื่อเพิ่มพื้นที่ทำงานไปยังความจุพรีเมียม


## <a name="upload-a-paginated-report"></a>อัปโหลดรายงานแบบแบ่งหน้า

1. สร้างรายงานแบบแบ่งหน้าในตัวสร้างรายงานและบันทึกลงคอมพิวเตอร์ของคุณ

1. เปิดบริการของ Power BI ในเบราเซอร์และเรียกดูพื้นที่ทำงาน Premium ที่คุณต้องการเผยแพร่รายงาน มองหาไอคอนรูปข้าวหลามตัด ![ไอคอนรูปข้าวหลามตัดของความจุ Power BI Premium](media/paginated-reports-save-to-power-bi-service/premium-diamond.png) ที่อยู่ถัดจากชื่อ 

1. เลือก**รับข้อมูล**

    ![การรับข้อมูลของ Power BI](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-get-data.png)

1. ในกล่อง**ไฟล์** เลือก**รับ**

    ![การรับไฟล์ของ Power BI](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-files-get.png)

1. เลือก**ไฟล์ภายในเครื่อง** > เรียกดูรายงานแบบแบ่งหน้า > **เปิด**

    ![เลือกไฟล์ภายในเครื่อง](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-local-file.png)

1. เลือก**ดำเนินการต่อ** > **แก้ไขข้อมูลประจำตัว**

    ![เลือกแก้ไขข้อมูลประจำตัว](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-edit-credentials.png)

1. กำหนดข้อมูลประจำตัว > **ลงชื่อเข้าใช้**

    ![แก้ไขรหัสประจำตัว](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-credentials.png)

   คุณจะเห็นรายงานของคุณอยู่ในรายการรายงาน

    ![รายงานแบบแบ่งหน้าในรายการรายงาน](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-wwi-report.png)

1. เลือกเพื่อเปิดในบริการของ Power BI ถ้ามีพารามิเตอร์ คุณต้องเลือกก่อนที่คุณจะสามารถดูรายงานได้
 
    ![เลือกพารามิเตอร์](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-select-parameters.png)

## <a name="create-a-gateway"></a>สร้างเกตเวย์

เช่นเดียวกันกับรายงาน Power BI อื่นๆ หากแหล่งข้อมูลของรายงานอยู่ในองค์กร คุณต้องสร้างหรือเชื่อมต่อเกตเวย์เพื่อเข้าถึงข้อมูล

1. ที่ถัดจากชื่อรายงาน ให้คุณเลือก**จัดการ**

   ![จัดการรายงานแบบแบ่งหน้า](media/paginated-reports-save-to-power-bi-service/power-bi-paginated-manage.png)

1. ดูบทความบริการของ Power BI [ติดตั้งเกตเวย์](service-gateway-install.md) สำหรับรายละเอียดและขั้นตอนถัดไป

### <a name="gateway-limitations"></a>ข้อจำกัดเกตเวย์

ในขณะนี้เกตเวย์ไม่รองรับพารามิเตอร์หลายค่า


## <a name="next-steps"></a>ขั้นตอนถัดไป

- [ดูรายงานแบบแบ่งหน้าในบริการของ Power BI](paginated-reports-view-power-bi-service.md)
- [รายงานแบบแบ่งหน้าใน Power BI Premium คืออะไร (ตัวอย่าง)](paginated-reports-report-builder-power-bi.md)


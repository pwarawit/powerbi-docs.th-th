---
title: ค้นหาผู้ใช้ Power BI ที่มีการลงชื่อเข้าใช้
description: ถ้าคุณเป็นผู้ดูแลระบบผู้เช่า และต้องการดูบุคคลที่มีการลงชื่อเข้าใช้ Power BI คุณสามารถใช้รายงานการเข้าถึงและการใช้งานของ Azure Active Directory เพื่อให้สามารถมองเห็นได้
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 4f9b69e863b71fda0cece06df7065740bd55463e
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85228882"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>ค้นหาผู้ใช้ Power BI ที่มีการลงชื่อเข้าใช้

หากคุณเป็นผู้ดูแลระบบผู้เช่า และต้องการดูบุคคลที่ลงชื่อเข้าใช้ Power BI ให้ใช้ [รายงานการเข้าถึงและการใช้งานของ Azure Active Directory](/azure/active-directory/reports-monitoring/concept-sign-ins) เพื่อให้สามารถมองเห็นได้

> [!NOTE]
> แม้รายงาน**ลงชื่อเข้าใช้**จะให้ข้อมูลที่เป็นประโยชน์ แต่ก็ไม่สามารถระบุประเภทสิทธิการใช้งานที่ผู้ใช้แต่ละคนมีได้ การใช้ศูนย์การจัดการ Microsoft 365 เพื่อดูสิทธิ์การใช้งาน

## <a name="requirements"></a>ความต้องการ

ผู้ใช้ใด ๆ (รวมถึงที่ไม่ใช่ผู้ดูแลระบบ) สามารถดูรายงานการลงชื่อเข้าใช้ของตนเองได้ แต่คุณต้องตรงตามข้อกำหนดต่อไปนี้เพื่อดูรายงานผู้ใช้ทั้งหมด

* ผู้เช่าของคุณต้องมีสิทธิการใช้งาน Azure Active Directory Premium ที่เกี่ยวเนื่อง

* คุณต้องอยู่ในหนึ่งบทบาทต่อไปนี้: ผู้ดูแลระบบส่วนกลาง, ผู้ ดูแลรักษาความปลอดภัย หรือ ผู้อ่านความปลอดภัย

## <a name="use-the-azure-portal-to-view-sign-ins"></a>ใช้พอร์ทัล Azure เพื่อดูการลงชื่อเข้าใช้

หากต้องการดูกิจกรรมการลงชื่อเข้าใช้ ให้ปฏิบัติตามขั้นตอนเหล่านี้

1. ใน **พอร์ทัล Azure** เลือก **Azure Active Directory**

1. ใต้ **การตรวจสอบ** เลือก **ลงชื่อเข้า**
   
    ![สกรีนช็อตของ Azure UI พร้อมตัวเลือก Azure Active Directory และลงชื่อเข้าใช้ที่เน้น](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. กรองแอปพลิเคชันตาม **Microsoft Power BI** หรือ **Power BI Gateway** อย่างใดอย่างหนึ่ง แล้วเลือก **นำไปใช้**

    **Microsoft Power BI** จะกรองไปยังกิจกรรมการลงชื่อเข้าใช้ที่เกี่ยวข้องกับบริการ ในขณะที่ **Power BI Gateway** จะกรองกิจกรรมการลงชื่อเข้าใช้ที่เจาะจงเกตเวย์ข้อมูลภายในองค์กร
   
    ![สกรีนช็อตของตัวกรองลงชื่อเข้าพร้อมด้วยเขตข้อมูลของแอปพลิเคชันที่เน้น](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>ส่งออกข้อมูล

คุณสามารถ[ดาวน์โหลดรายงานลงชื่อเข้าใช้](/azure/active-directory/reports-monitoring/quickstart-download-sign-in-report)ในรูปแบบไฟล์ CSV หรือไฟล์ JSON ได้

![สกรีนช็อตของปุ่มดาวน์โหลด](media/service-admin-access-usage/download-sign-in-data-csv.png)

ที่ด้านบนของรายงาน**ลงชื่อเข้าใช้** เลือก**ดาวน์โหลด** แล้วเลือกหนึ่งในตัวเลือกต่อไปนี้:

* **CSV** เพื่อดาวน์โหลดไฟล์ CSV สำหรับข้อมูลที่ถูกกรองในขณะนี้

* **JSON** เพื่อดาวน์โหลดไฟล์ JSON สำหรับข้อมูลที่ถูกกรองในขณะนี้

## <a name="data-retention"></a>การเก็บรักษาข้อมูล

ข้อมูลที่เกี่ยวข้องกับการลงชื่อเข้าใช้สามารถใช้งานได้สูงสุด 30 วัน สำหรับข้อมูลเพิ่มเติม ดู[นโยบายการเก็บรักษาข้อมูลรายงานของ Azure Active Directory](/azure/active-directory/reports-monitoring/reference-reports-data-retention)

## <a name="next-steps"></a>ขั้นตอนถัดไป

[ใช้การตรวจสอบภายในองค์กรของคุณ](service-admin-auditing.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
---
title: ค้นหาผู้ใช้ Power BI ที่มีการลงชื่อเข้าใช้
description: ถ้าคุณเป็นผู้ดูแลผู้เช่า และต้องการดูบุคคลที่มีการลงชื่อเข้าใช้ Power BI คุณสามารถใช้รายงานการเข้าถึงและการใช้งานของ Azure Active Directory เพื่อให้สามารถมองเห็นได้
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/31/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: f685a900465cc0f1b635aad7609aaae4356da6b3
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54284644"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>ค้นหาผู้ใช้ Power BI ที่มีการลงชื่อเข้าใช้

หากคุณเป็นผู้ดูแลผู้เช่า และต้องการดูบุคคลที่ลงชื่อเข้าใช้ Power BI ให้ใช้ [รายงานการเข้าถึงและการใช้งานของ Azure Active Directory](/azure/active-directory/reports-monitoring/concept-sign-ins) เพื่อให้สามารถมองเห็นได้

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> แม้รายงานกิจกรรมนี้จะให้ข้อมูลที่เป็นประโยชน์ แต่ก็ไม่สามารถระบุชนิดสิทธิ์การใช้งานที่ผู้ใช้แต่ละคนมีได้ การใช้ศูนย์การจัดการ Office 365 เพื่อดูสิทธิ์การใช้งาน

## <a name="requirements"></a>ข้อกำหนด

ผู้ใช้ใด ๆ (รวมถึงที่ไม่ใช่ผู้ดูแลระบบ) สามารถดูรายงานการลงชื่อเข้าใช้ของตนเองได้ แต่คุณต้องตรงตามข้อกำหนดต่อไปนี้เพื่อดูรายงานผู้ใช้ทั้งหมด

* ผู้เช่าของคุณต้องมีสิทธิ์การใช้งาน Azure AD Premium ที่เกี่ยวเนื่อง

* คุณต้องได้รับมอบหมายหน้าที่ดังต่อไปนี้: ผู้ดูแลระบบส่วนกลาง ผู้ดูแลความปลอดภัย หรือตัวอ่านความปลอดภัย

## <a name="use-the-azure-portal-to-view-sign-ins"></a>ใช้พอร์ทัล Azure เพื่อดูการลงชื่อเข้าใช้

หากต้องการดูกิจกรรมการลงชื่อเข้าใช้ ให้ปฏิบัติตามขั้นตอนเหล่านี้

1. ใน **พอร์ทัล Azure** เลือก **Azure Active Directory**

1. ใต้ **การตรวจสอบ** เลือก **ลงชื่อเข้า**
   
    ![การลงชื่อเข้าใช้ Azure AD](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. กรองแอปพลิเคชันตาม **Microsoft Power BI** หรือ **Power BI Gateway** อย่างใดอย่างหนึ่ง แล้วเลือก **นำไปใช้**

    **Microsoft Power BI** จะกรองไปยังกิจกรรมการลงชื่อเข้าใช้ที่เกี่ยวข้องกับบริการ ในขณะที่ **Power BI Gateway** จะกรองกิจกรรมการลงชื่อเข้าใช้ที่เจาะจงเกตเวย์ข้อมูลในองค์กร
   
    ![ตัวกรองการลงชื่อเข้าใช้](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>ส่งออกข้อมูล

คุณมีสองตัวเลือกในการส่งออกข้อมูลการเข้าสู่ระบบ: ดาวน์โหลดไฟล์ csv หรือใช้ PowerShell ที่ด้านบนของรายงานการลงชื่อเข้าใช้ ให้เลือกหนึ่งในตัวเลือกต่อไปนี้:

* **ดาวน์โหลด** เพื่อดาวน์โหลดไฟล์ csv สำหรับข้อมูลที่ถูกกรองในขณะนี้

* **สคริปต์** เพื่อดาวน์โหลดสคริปต์ของ PowerShell สำหรับข้อมูลที่ถูกกรองในขณะนี้ คุณสามารถอัปเดตตัวกรองในสคริปต์ตามความจำเป็น

![ดาวน์โหลดไฟล์ csv หรือสคริปต์](media/service-admin-access-usage/download-sign-in-data-csv.png)

## <a name="data-retention"></a>การเก็บรักษาข้อมูล

ข้อมูลที่เกี่ยวข้องกับการลงชื่อเข้าใช้สามารถใช้งานได้สูงสุด 30 วัน สำหรับข้อมูลเพิ่มเติม ดู[นโยบายการเก็บรักษาข้อมูลรายงานของ Azure Active Directory](/azure/active-directory/reports-monitoring/reference-reports-data-retention)

## <a name="next-steps"></a>ขั้นตอนถัดไป

[ใช้การตรวจสอบภายในองค์กรของคุณ](service-admin-auditing.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](https://community.powerbi.com/)


---
title: ติดตามสถานภาพบริการ Power BI ใน Office 365
description: เรียนรู้วิธีการดูสถานภาพบริการปัจจุบันและในอดีตในศูนย์การจัดการ Microsoft 365
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 05/14/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 37108c88b3a4f1efe2d324d2b182276252072d78
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "65710430"
---
# <a name="track-power-bi-service-health-in-office-365"></a>ติดตามสถานภาพบริการ Power BI ใน Office 365

ศูนย์การจัดการ Microsoft 365 มีเครื่องมือสำคัญสำหรับผู้ดูแลระบบ Power BI เครื่องมือมีข้อมูลในอดีต และปัจจุบันเกี่ยวกับสถานภาพบริการ เมื่อต้องการเข้าถึงข้อมูลสุขภาพบริการ คุณต้องอยู่ในหนึ่งบทบาทต่อไปนี้:

* ผู้ดูแลระบบบริการ Power BI

* ผู้ดูแลระบบส่วนกลางของ Office 365

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับบทบาท ดู[บทบาทผู้ดูแลระบบที่เกี่ยวข้องกับ Power BI](service-admin-administering-power-bi-in-your-organization.md#administrator-roles-related-to-power-bi)

1. ลงชื่อเข้าใช้ [ศูนย์การจัดการ Microsoft 365](https://portal.office.com/adminportal)

1. จากแถบนำทางด้านซ้าย เลือก**แสดงทั้งหมด** > **สถานภาพ** > **สถานภาพบริการ** หน้าสถานภาพบริการปรากฏขึ้น:

    ![สกรีนช็อตของศูนย์การจัดการ Microsoft 365 ด้วยสถานภาพและบริการสถานภาพตัวเรียก](media/service-admin-health/service-health-tile.png)

1. จาก**บริการทั้งหมด**รายการ เลือก**คำแนะนำ**หรือ**เหตุการณ์**และตรวจสอบผลลัพธ์ ในสกรีนช็อตด้านล่าง คุณเห็นหนึ่งในสามคำแนะนำที่ใช้งานอยู่

    ![สกรีนช็อตของหน้าสถานภาพบริการด้วยคำแนะนำที่สามสำหรับ Power BI และแสดงตัวเลือกรายละเอียดที่เรียกว่าออก](media/service-admin-health/active-advisories.png)

1. เมื่อต้องการดูข้อมูลเพิ่มเติม เลือก**แสดงรายละเอียด**สำหรับรายการ ในสกรีนช็อตด้านล่าง คุณเห็นรายละเอียดเพิ่มเติม รวมถึงการปรับปรุงสถานะล่าสุด

    ![รายละเอียดสกรีนช็อตของคำแนะนำ](media/service-admin-health/advisory-details.png)

    เลื่อนลงเพื่อดูข้อมูลเพิ่มเติม จากนั้นปิดบานหน้าต่างเมื่อคุณทำเสร็จแล้ว

1. เมื่อต้องดูข้อมูลในอดีตทั่วทั้งบริการ ในมุมขวาบนของคำ**สถานภาพบริการ**หน้า เลือก**ดูประวัติ** จากนั้นเลือก **7 วันที่ผ่าน**หรือ **30 วันที่ผ่าน** 

1. เมื่อต้องการกลับไปยังสถานภาพบริการปัจจุบัน เลือก**ดูสถานะปัจจุบัน**
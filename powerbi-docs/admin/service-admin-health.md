---
title: ติดตามสถานภาพบริการ Power BI ใน Microsoft 365
description: เรียนรู้วิธีการดูสถานภาพบริการปัจจุบันและในอดีตในศูนย์การจัดการ Microsoft 365
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 610fe7ea2188d40d42ab91a355df68bc07bb0d84
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/23/2020
ms.locfileid: "85228520"
---
# <a name="track-power-bi-service-health-in-microsoft-365"></a>ติดตามสถานภาพบริการ Power BI ใน Microsoft 365

ศูนย์การจัดการ Microsoft 365 มีเครื่องมือที่สำคัญสำหรับผู้ดูแลระบบ Power BI เครื่องมือนี้รวมข้อมูลปัจจุบันและอดีตเกี่ยวกับสุขภาพบริการ หากต้องการเข้าถึงข้อมูลบริการสุขภาพ คุณต้องได้รับหน้าที่เป็นหนึ่งในตำแหน่งต่อไปนี้:

* ผู้ดูแลระบบบริการ Power BI

* ผู้ดูแลระบบส่วนกลาง

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับบทบาท ดู[บทบาทผู้ดูแลระบบที่เกี่ยวข้องกับ Power BI](service-admin-administering-power-bi-in-your-organization.md#administrator-roles-related-to-power-bi)

1. ลงชื่อเข้าใช้ [ศูนย์การจัดการ Microsoft 365](https://portal.office.com/adminportal)

1. จากบานหน้าต่างนำทาง ให้เลือก**แสดง** > **บริการสุขภาพ** > **ทั้งหมด** หน้าบริการสุขภาพจะปรากฏ:

    ![สกรีนช็อตของศูนย์การเรียกตัวจัดการ Microsoft 365 ด้วยตัวเลือกสุขภาพและความสมบูรณ์ของบริการออกมา](media/service-admin-health/service-health-tile.png)

1. จากรายการ **บริการทั้งหมด**ให้เลือก**คำแนะนำ** หรือ **เหตุการณ์**และตรวจสอบผลลัพธ์ ในสกรีนช็อตด้านล่าง คุณจะเห็นหนึ่งในสามคำแนะนำที่ใช้งานอยู่

    ![สกรีนช็อตของการเรียกหน้าบริการสุขภาพที่มีสามคำแนะนำสำหรับ Power BI และแสดงรายละเอียดตัวเลือกออกมา](media/service-admin-health/active-advisories.png)

1. เมื่อต้องการดูข้อมูลเพิ่มเติม เลือก**แสดงรายละเอียด**สำหรับรายการ ในสกรีนช็อตด้านล่าง คุณจะเห็นรายละเอียดเพิ่มเติม รวมถึงการปรับปรุงสถานะล่าสุดด้วย

    ![สกรีนช็อตของรายละเอียดคำแนะนำ](media/service-admin-health/advisory-details.png)

    เลื่อนลงเพื่อดูข้อมูลเพิ่มเติม จากนั้นปิดบานหน้าต่างเมื่อคุณทำเสร็จแล้ว

1. ในการดูข้อมูลในอดีตทั่วทั้งบริการ ที่มุมบนขวาของ**หน้าบริการสุขภาพ** เลือก**ดูประวัติ** จากนั้นเลือก **7 วันที่ผ่าน**หรือ **30 วันที่ผ่าน** 

1. เมื่อต้องการกลับไปยังสถานภาพบริการปัจจุบัน เลือก**ดูสถานะปัจจุบัน**
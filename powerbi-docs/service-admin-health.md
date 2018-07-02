---
title: ติดตามสถานภาพบริการ Power BI ใน Office 365
description: เรียนรู้วิธีการดูสถานภาพบริการปัจจุบันและในอดีตในศูนย์การจัดการ Office 365
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 05/09/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: fdef5ce49836fcd4b65b98f5eb92c2b565ce69f1
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34292052"
---
# <a name="track-power-bi-service-health-in-office-365"></a>ติดตามสถานภาพบริการ Power BI ใน Office 365

ศูนย์การจัดการ Office 365 มีเครื่องมือสำคัญสำหรับผู้ดูแล Power BI รวมถึงข้อมูลในอดีต และปัจจุบันเกี่ยวกับสถานภาพบริการ ในการเข้าถึงข้อมูลนี้ คุณต้องอยู่ในหนึ่งบทบาทต่อไปนี้: ผู้ดูแลระบบบริการ Power BI หรือผู้ดูแลระบบส่วนกลาง Office 365 สำหรับข้อมูลเพิ่มเติมเกี่ยวกับบทบาท ดู[บทบาทผู้ดูแลระบบที่เกี่ยวข้องกับ Power BI](service-admin-administering-power-bi-in-your-organization.md#administrator-roles-related-to-power-bi)


1. ลงชื่อเข้าใช้[ศูนย์การจัดการ Office 365](https://portal.office.com/adminportal)

2. เลือกไทล์**สถานภาพบริการ

    ![ไทล์สถานภาพบริการ](media/service-admin-health/service-health-tile.png)

3. ในรายการปัจจุบันเลือก **คำแนะนำ N**หรือ**เหตุการณ์ N**และตรวจสอบผลลัพธ์ ในกราฟิกด้านล่าง คุณจะเห็นหนึ่งในสามคำแนะนำที่ใช้งานอยู่

    ![คำแนะนำที่ใช้งานอยู่](media/service-admin-health/active-advisories.png)

4. เมื่อต้องการดูข้อมูลเพิ่มเติม เลือก**แสดงรายละเอียด**สำหรับรายการ ในกราฟิกด้านล่าง คุณจะเห็นรายละเอียดเพิ่มเติม รวมถึงการปรับปรุงสถานะล่าสุดด้วย

    ![รายละเอียดคำแนะนำ](media/service-admin-health/advisory-details.png)

    เลื่อนลงเพื่อดูข้อมูลเพิ่มเติม จากนั้นปิดบานหน้าต่างเมื่อคุณทำเสร็จแล้ว

5. ในการดูข้อมูลในอดีตทั่วทั้งบริการ ที่มุมบนขวาของรายการหลัก เลือก**ดูประวัติ** จากนั้นเลือก **7 วันที่ผ่าน**หรือ **30 วันที่ผ่าน** เมื่อต้องการกลับไปยังสถานภาพบริการปัจจุบัน เลือก**ดูสถานะปัจจุบัน**
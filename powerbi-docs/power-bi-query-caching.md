---
title: การแคชคิวรีใน Power BI Premium
description: การแคชคิวรีใน Power BI Premium
author: maggiesMSFT
manager: kfile
ms.reviewer: bhmerc
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/03/2019
ms.author: maggies
LocalizationGroup: ''
ms.openlocfilehash: fbfd8c98743144e0c9604aca4174d6ef32916e77
ms.sourcegitcommit: de0b72915183a8a784d3227838bd704c1c209422
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/04/2019
ms.locfileid: "58914287"
---
# <a name="query-caching-in-power-bi-premium"></a>การแคชคิวรีใน Power BI Premium

องค์กรที่มี Power BI Premium สามารถใช้ประโยชนจาก*การแคชคิวรี*เพื่อให้รายงานที่เกี่ยวข้องกับชุดข้อมูลแสดงผลเร็วขึ้น การแคชคิวรีแนะนำความจุ Premium เพื่อใช้บริการการแคชในพื้นที่เพื่อรักษาผลลัพธ์คิวรี หลีกเลี่ยงแหล่งข้อมูลแฝงในการคำนวณผลลัพธ์เหล่านั้น

> [!IMPORTANT]
> การแคชคิวรีจะพร้อมใช้งานบน Power BI Premium ไม่สามารถใช้กับชุดข้อมูล LiveConnect ที่ใช้ประโยชน์จาก Azure Analysis Services หรือ SQL Server Analysis Services

ผลลัพธ์คิวรีที่แคชไว้จะใช้เฉพาะกับผู้ใช้และบริบทชุดข้อมูล และควรคำนึงถึงกฎความปลอดภัยเสมอ ในปัจจุบัน มีบริการแคชคิวรีสำหรับหน้าเริ่มต้นที่คุณไปถึง กล่าวคือ คิวรีไม่ได้ถูกแคชเมื่อคุณโต้ตอบกับรายงาน การแคชสะท้อนถึงบุ๊กมาร์กส่วนบุคคลและตัวกรองแบบถาวร [ไทล์แดชบอร์ด](service-dashboard-tiles.md)ที่ขับเคลื่อนโดยคิวรีเดียวกันจะได้ประโยชน์เมื่อมีการแคชคิวรี โดยเฉพาะอย่างยิ่งประสิทธิภาพจะได้รับประโยชน์เมื่อชุดข้อมูลมีการเข้าถึงบ่อยครั้ง และไม่จำเป็นต้องรีเฟรชบ่อยครั้ง การแคชคิวรียังสามารถลดการโหลดความจุแบบ Premium ของคุณโดยการลดจำนวนคิวรีโดยรวมได้

คุณสามารถควบคุมพฤติกรรมการแคชคิวรี่ได้ที่หน้า**การตั้งค่า** สำหรับชุดข้อมูลในบริการ Power BI การตั้งค่าที่เป็นไปได้มีอยู่สามวิธีด้วยกัน:

- **ค่าเริ่มต้นความจุ**: ชุดข้อมูลสืบทอดการตั้งค่าจากความจุ Premium ผู้ดูแลระบบความจุ Power BI Premium จะควบคุมค่าเริ่มต้นความจุ

- **ปิด**: อย่าใช้การแคชคิวรี่สำหรับชุดข้อมูลนี้

- **เปิด**: ใช้การแคชคิวรี่สำหรับชุดข้อมูลนี้

![กล่องโต้ตอบการแคชคิวรี](media/power-bi-query-caching/power-bi-query-caching.png)

> [!NOTE]
> เมื่อคุณเปลี่ยนการตั้งค่าการแคชจาก**เปิด**เป็น**ปิด** ผลลัพธ์คิวรีที่บันทึกไว้ก่อนหน้านี้ทั้งหมดสำหรับชุดข้อมูลจะถูกลบออกจากแคชความจุ คุณสามารถปิดใช้งานการแคชอย่างชัดแจ้ง หรือโดยการเปลี่ยนกลับไปเป็นการตั้งค่าความจเริ่มต้นุที่ผู้ดูแลระบบตั้งค่าเป็น**ปิด** การปิดอาจก่อให้เกิดความล่าช้าเล็กน้อยในครั้งถัดไปที่ซึ่งรายงานเรียกใช้คิวรีกับชุดข้อมูลนี้ ความล่าช้ามีสาเหตุมาจากคิวรีรายงานที่เรียกใช้ตามคำขอ และไม่ได้ใช้ประโยชน์จากผลลัพธ์ที่บันทึกไว้ นอกจากนี้ ชุดข้อมูลที่กำหนดอาจจำเป็นต้องโหลดลงในหน่วยความจำก่อนที่จะสามารถให้บริการคิวรีได้


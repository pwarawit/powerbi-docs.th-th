---
title: ใช้ลิงก์ OneDrive for Business ใน Power BI Desktop
description: ใช้ลิงก์ OneDrive for Business ใน Power BI Desktop
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 706703985242284725fb4fc2d42bf46e54c605c7
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "76709707"
---
# <a name="use-onedrive-for-business-links-in-power-bi-desktop"></a>ใช้ลิงก์ OneDrive for Business ใน Power BI Desktop
หลายคนมีเวิร์กบุ๊ก Excel ที่จัดเก็บไว้ใน OneDrive for Business ที่จะเหมาะสำหรับใช้งานกับ Power BI Desktop  ด้วย Power BI Desktop คุณสามารถใช้ลิงก์ออนไลน์สำหรับไฟล์ Excel ที่จัดเก็บไว้ใน OneDrive for Business เพื่อสร้างรายงานและวิชวลได้  คุณสามารถใช้บัญชีผู้ใช้กลุ่ม OneDrive for Business หรือบัญชีผู้ใช้บุคคล OneDrive for Business ของคุณก็ได้

การรับลิงก์ออนไลน์จาก OneDrive for Business ต้องใช้ขั้นตอนที่เฉพาะเจาะจงสองสามขั้นตอน ส่วนต่อไปนี้จะอธิบายขั้นตอนดังกล่าว ให้คุณสามารถแชร์ลิงก์ของไฟล์ระหว่างกลุ่ม ระหว่างเครื่อง และกับเพื่อนร่วมงานของคุณ

## <a name="get-a-link-from-excel"></a>รับลิงก์จาก Excel 
1. นำทางไปยังที่ตั้ง OneDrive for Business ของคุณโดยใช้เบราว์เซอร์ คลิกขวาไฟล์ที่คุณต้องการใช้ และเลือก**เปิดใน Excel**
   
   > [!NOTE]
   > อินเทอร์เฟซบนเบราว์เซอร์ของคุณอาจไม่เหมือนรูปต่อไปนี้ มีหลายวิธีในการเลือก**เปิดใน Excel** สำหรับไฟล์ในอินเทอร์เฟซบนเบราว์เซอร์ OneDrive for Business ของคุณ คุณสามารถใช้ทางเลือกใด ๆ ที่ทำให้คุณสามารถเปิดไฟล์ใน Excel
   > 
   > 
   
   ![](media/desktop-use-onedrive-business-links/odb-links_02.png)
2. ใน Excel ให้เลือก**ไฟล์** > **ข้อมูล**จากนั้นเลือก **คัดลอกเส้นทาง** ด้านบน **ป้องกันเวิร์กบุ๊ก**
   
   ![](media/desktop-use-onedrive-business-links/onedrive-copy-path.png)

## <a name="use-the-link-in-power-bi-desktop"></a>ใช้ลิงก์ใน Power BI Desktop
ใน Power BI Desktop คุณสามารถใช้ลิงก์ที่คุณเพิ่งคัดลอกไปยังคลิปบอร์ด ทำตามขั้นตอนต่อไปนี้:

1. ใน Power BI Desktop ให้เลือก **รับข้อมูล** > **เว็บ**
   
   ![](media/desktop-use-onedrive-business-links/power-bi-web-link-onedrive.png)
2. ด้วยตัวเลือก **พื้นฐาน** ที่เลือกไว้ วางลิงก์ในกล่องโต้ตอบ **จากเว็บ**
3. ลบสตริง *?web=1* ออกที่จุดสิ้นสุดของลิงก์เพื่อให้ Power BI Desktop สามารถนำทางไปยังไฟล์ของคุณอย่างถูกต้อง จากนั้นเลือก**ตกลง**
   
    ![](media/desktop-use-onedrive-business-links/power-bi-web-link-confirmation.png) 
4. ถ้า Power BI Desktop พร้อมท์คุณสำหรับข้อมูลประจำตัว เลือก **Windows** (สำหรับไซต์ SharePoint ภายในองค์กร) หรือ **บัญชีองค์กร** (สำหรับ Office 365 หรือ ไซต์ OneDrive for Business) อย่างใดอย่างหนึ่ง
   
   ![](media/desktop-use-onedrive-business-links/odb-links_06.png)

   กล่องโต้ตอบ**ตัวนำทาง**จะปรากฏขึ้น ช่วยให้คุณสามารถเลือกจากรายการของตาราง แผ่นงาน และช่วงที่พบในเวิร์กบุ๊ก Excel จากที่นั่น คุณสามารถใช้ไฟล์ OneDrive for Business เช่นเดียวกับไฟล์ Excel อื่น ๆ ได้ คุณสามารถสร้างรายงานและใช้ในชุดข้อมูลได้เช่นเดียวกับที่คุณต้องการกับแหล่งข้อมูลอื่น ๆ

> [!NOTE]
> หากต้องการใช้ไฟล์ OneDrive for Business เป็นแหล่งข้อมูลในบริการของ Power BI ที่เปิดใช้งาน **การบริการรีเฟรช** สำหรับไฟล์ดังกล่าว ตรวจสอบให้แน่ใจว่า คุณเลือก **OAuth2** เป็น **วิธีการรับรองความถูกต้อง**เมื่อกำหนดค่าการตั้งค่าการรีเฟรชของคุณ มิฉะนั้น คุณอาจพบข้อผิดพลาด (เช่น*ไม่สามารถปรับปรุงข้อมูลประจำตัวสำหรับแหล่งข้อมูล*) เมื่อคุณพยายามเชื่อมต่อ หรือรีเฟรชได้ การเลือก **OAuth2** ให้เป็นวิธีการรับรองความถูกต้อง เป็นการแก้ไขข้อผิดพลาดข้อมูลประจำตัวนั้น
> 
> 


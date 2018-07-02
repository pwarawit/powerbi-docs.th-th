---
title: เชื่อมต่อกับฐานข้อมูล Oracle
description: ขั้นตอนและการดาวน์โหลดที่จำเป็นต้องเชื่อมต่อ Oracle กับ Power BI Desktop
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 4/24/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: a56097c02c9f3af63151d0a38e14fdc580e4ee9e
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34291016"
---
# <a name="connect-to-an-oracle-database"></a>เชื่อมต่อกับฐานข้อมูล Oracle
เมื่อต้องการเชื่อมต่อกับฐานข้อมูล Oracle ด้วย**Power BI Desktop** ซอฟต์แวร์ไคลเอ็นต์ Oracle ที่ถูกต้องต้องติดตั้งบนคอมพิวเตอร์ที่ใช้งาน Power BI Desktop ซึ่งซอฟต์แวร์ไคลเอ็นต์ Oracle ที่คุณใช้ขึ้นอยู่กับเวอร์ชันของ Power BI Desktop ที่คุณได้ติดตั้ง เวอร์ชัน**32 บิต**หรือ**เวอร์ชัน 64 บิต**

**เวอร์ชันที่รองรับ** Oracle 9 และรุ่นใหม่กว่า ซอฟต์แวร์ไคลเอ็นต์ Oracle 8.1.7 และภายหลัง

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>หา Power BI Desktop ที่ติดตั้งอยู่เวอร์ชันใด
เมื่อต้องการตรวจสอบเวอร์ชันของ Power BI Desktop ที่ถูกติดตั้ง ให้เลือก**ไฟล์ > วิธีใช้ > เกี่ยวกับ**แล้ว ตรวจสอบการบรรทัด**เวอร์ชัน:** ในรูปต่อไปนี้ Power BI Desktop เวอร์ชัน 64 บิตถูกติดตั้ง

![](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>ติดตั้งไคลเอ็นต์ Oracle
สำหรับเวอร์ชัน**32 บิต**ของ Power BI Desktop ใช้ลิงก์ต่อไปนี้เพื่อดาวน์โหลดและติดตั้ง Oracle Client**32 บิต**

* [32-bit Oracle Data Access Components (ODAC) with Oracle Developer Tools for Visual Studio (12.1.0.2.4)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

สำหรับเวอร์ชัน**64 บิต**ของ Power BI Desktop ใช้ลิงก์ต่อไปนี้เพื่อดาวน์โหลด และติดตั้งไคลเอนต์ Oracle**64 บิต**

* [64-bit ODAC 12c Release 4 (12.1.0.2.4) for Windows x64](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## <a name="connect-to-an-oracle-database"></a>เชื่อมต่อกับฐานข้อมูล Oracle
เมื่อติดตั้งโปรแกรมควบคุมไคลเอ็นต์ Oracle ที่ตรงกัน คุณสามารถเชื่อมต่อกับฐานข้อมูล Oracle เมื่อต้องทำการเชื่อมต่อ ให้ทำตามขั้นตอนต่อไปนี้

1. จากหน้าต่างการรับข้อมูล เลือก**ฐานข้อมูล > ฐานข้อมูล Oracle**
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. ในกล่องโต้ตอบ**ฐานข้อมูล Oracle**ที่ปรากฏขึ้น ให้ใส่ชื่อของเซิร์ฟเวอร์ และเลือก**เชื่อมต่อ** ถ้าต้องใช้ SID คุณสามารถระบุด้วยรูปแบบ: *ServerName/SID* โดยที่ SID เป็นชื่อที่ไม่ซ้ำของฐานข้อมูลได้ ถ้ารูปแบบ *ServerName/SID* ไม่ทำงาน ลองใช้ *ServerName/ServiceName* โดยที่ ServiceName เป็นนามแฝงที่ใช้เมื่อเชื่อมต่อ
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_3.png)
3. ถ้าคุณต้องการนำเข้าข้อมูลโดยใชคิวรี่ของฐานข้อมูลแบบเนทีฟ คุณสามารถใส่คิวรีของคุณในกล่อง**คำสั่ง SQL** ที่สามารถขยายตัวส่วน**ตัวเลือกขั้นสูง**ของกล่องโต้ตอบ**ฐานข้อมูล Oracle**
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. เมื่อมีป้อนข้อมูลของฐานข้อมูล Oracle ของคุณลงในกล่องโต้ตอบฐานข้อมูล Oracle (รวมถึงข้อมูลประกอบใดๆ เช่น SID หรือคิวรี่ฐานข้อมูลเนทีฟ) ให้เลือก**ตกลง**เพื่อเชื่อมต่อ
5. ถ้าฐานข้อมูล Oracle ต้องใช้ข้อมูลประจำตัวผู้ใช้ฐานข้อมูล ให้ป้อนข้อมูลประจำตัวเหล่านั้นในกล่องโต้ตอบเมื่อได้รับการขอจากระบบ


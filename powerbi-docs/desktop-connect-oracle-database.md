---
title: เชื่อมต่อกับฐานข้อมูล Oracle
description: ขั้นตอนและการดาวน์โหลดที่จำเป็นต้องเชื่อมต่อ Oracle กับ Power BI Desktop
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 4126a5f4fc7b8a398d39cad7c14e87e179ab3175
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/12/2018
ms.locfileid: "30975226"
---
# <a name="connect-to-an-oracle-database"></a>เชื่อมต่อกับฐานข้อมูล Oracle
เมื่อต้องการเชื่อมต่อกับฐานข้อมูล Oracle ด้วย**Power BI Desktop** ซอฟต์แวร์ไคลเอ็นต์ Oracle ที่ถูกต้องต้องติดตั้งบนคอมพิวเตอร์ที่ใช้งาน Power BI Desktop ซึ่งซอฟต์แวร์ไคลเอ็นต์ Oracle ที่คุณใช้ขึ้นอยู่กับเวอร์ชันของ Power BI Desktop ที่คุณได้ติดตั้ง เวอร์ชัน**32 บิต**หรือ**เวอร์ชัน 64 บิต**

**เวอร์ชันที่รองรับ** Oracle 9 และรุ่นใหม่กว่า ซอฟต์แวร์ไคลเอ็นต์ Oracle 8.1.7 และภายหลัง

## <a name="determining-which-version-of-power-bi-desktop-is-installed"></a>หา Power BI Desktop ที่ติดตั้งอยู่เวอร์ชันใด
เมื่อต้องการตรวจสอบเวอร์ชันของ Power BI Desktop ที่ถูกติดตั้ง ให้เลือก**ไฟล์ > วิธีใช้ > เกี่ยวกับ**แล้ว ตรวจสอบการบรรทัด**เวอร์ชัน:** ในรูปต่อไปนี้ Power BI Desktop เวอร์ชัน 64 บิตถูกติดตั้ง

![](media/desktop-connect-oracle-database/connect-oracle-database_1.png)

## <a name="installing-the-oracle-client"></a>ติดตั้งไคลเอ็นต์ Oracle
สำหรับเวอร์ชัน**32 บิต**ของ Power BI Desktop ใช้ลิงก์ต่อไปนี้เพื่อดาวน์โหลด และติดตั้งไคลเอนต์ Oracle**32 บิต**

* [32-bit Oracle Data Access Components (ODAC) with Oracle Developer Tools for Visual Studio (12.1.0.2.4)](http://www.oracle.com/technetwork/topics/dotnet/utilsoft-086879.html)

สำหรับเวอร์ชัน**64 บิต**ของ Power BI Desktop ใช้ลิงก์ต่อไปนี้เพื่อดาวน์โหลด และติดตั้งไคลเอนต์ Oracle**64 บิต**

* [64-bit ODAC 12c Release 4 (12.1.0.2.4) for Windows x64](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html)

## <a name="connect-to-an-oracle-database"></a>เชื่อมต่อกับฐานข้อมูล Oracle
เมื่อติดตั้งโปรแกรมควบคุมไคลเอ็นต์ Oracle ที่ตรงกัน คุณสามารถเชื่อมต่อกับฐานข้อมูล Oracle เมื่อต้องทำการเชื่อมต่อ ให้ทำตามขั้นตอนต่อไปนี้

1. จากหน้าต่างการรับข้อมูล เลือก**ฐานข้อมูล > ฐานข้อมูล Oracle**
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_2.png)
2. ในกล่องโต้ตอบ**ฐานข้อมูล Oracle**ที่ปรากฏขึ้น ให้ใส่ชื่อของเซิร์ฟเวอร์ และเลือก**เชื่อมต่อ** ถ้าจำเป็นต้องมี SID คุณสามารถระบด้วยรูปแบบ *ServerName/SID*
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_3.png)
3. ถ้าคุณต้องการนำเข้าข้อมูลโดยใชคิวรี่ของฐานข้อมูลแบบเนทีฟ คุณสามารถใส่คิวรีของคุณในกล่อง**คำสั่ง SQL** ที่สามารถขยายตัวส่วน**ตัวเลือกขั้นสูง**ของกล่องโต้ตอบ**ฐานข้อมูล Oracle**
   
   ![](media/desktop-connect-oracle-database/connect-oracle-database_4.png)
4. เมื่อมีป้อนข้อมูลของฐานข้อมูล Oracle ของคุณลงในกล่องโต้ตอบฐานข้อมูล Oracle (รวมถึงข้อมูลประกอบใดๆ เช่น SID หรือคิวรี่ฐานข้อมูลเนทีฟ) ให้เลือก**ตกลง**เพื่อเชื่อมต่อ
5. ถ้าฐานข้อมูล Oracle ต้องใช้ข้อมูลประจำตัวผู้ใช้ฐานข้อมูล ให้ป้อนข้อมูลประจำตัวเหล่านั้นในกล่องโต้ตอบเมื่อได้รับการขอจากระบบ


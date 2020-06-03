---
title: ภาพรวมบริการหลัก
description: ภาพรวมบริการหลัก
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 04/05/2020
ms.custom: include file
ms.openlocfilehash: 8482278d9054228dedafb6bd1b37368f5a4b5dce
ms.sourcegitcommit: cd64ddd3a6888253dca3b2e3fe24ed8bb9b66bc6
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/03/2020
ms.locfileid: "84315835"
---
บริการหลักคือวิธีการรับรองความถูกต้องที่สามารถใช้เพื่ออนุญาตให้แอปพลิเคชัน  Azure AD เข้าถึงเนื้อหาบริการของ Power BI และ API

เมื่อคุณสร้างแอป Azure Active Directory (Azure AD)  [วัตถุบริการหลัก](https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object) จะถูกสร้างขึ้น วัตถุบริการหลัก ซึ่งเป็นที่รู้จักกันว่า *บริการหลัก* จะช่วยให้ Azure AD รับรองความถูกต้องของแอปของคุณ เมื่อรับรองความถูกต้องแล้ว แอปจะสามารถเข้าถึงแหล่งข้อมูลผู้เช่า Azure AD

ในการรับรองความถูกต้อง บริการหลักจะใช้ *รหัส แอปพลิเคชัน* ของแอป Azure AD และหนึ่งในรายการต่อไปนี้:

* ข้อมูลลับของแอปพลิเคชัน
* ใบรับรอง
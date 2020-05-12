---
title: ภาพรวมบริการหลัก
description: ภาพรวมบริการหลัก
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 04/05/2020
ms.custom: include file
ms.openlocfilehash: 7fc4412a66602fe3a6548c3e1afb06de788da90d
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "82615965"
---
บริการหลักคือวิธีการรับรองความถูกต้องที่สามารถใช้เพื่ออนุญาตให้แอปพลิเคชัน  Azure AD เข้าถึงเนื้อหาบริการของ Power BI และ API

เมื่อคุณสร้างแอป Azure Active Directory (Azure AD)  [วัตถุบริการหลัก](https://docs.microsoft.com/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object) จะถูกสร้างขึ้น วัตถุบริการหลัก ซึ่งเป็นที่รู้จักกันว่า *บริการหลัก* จะช่วยให้ Azure AD รับรองความถูกต้องของแอปของคุณ เมื่อรับรองความถูกต้องแล้ว แอปจะสามารถเข้าถึงแหล่งข้อมูลผู้เช่า Azure AD

ในการรับรองความถูกต้อง บริการหลักจะใช้ *รหัส แอปพลิเคชัน* ของแอป Azure AD และหนึ่งในรายการต่อไปนี้:
* ข้อมูลลับของแอปพลิเคชัน
* ใบรับรอง
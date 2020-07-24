---
title: ข้อจำกัดบริการหลัก
description: ข้อจำกัดบริการหลัก
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 06/06/2020
ms.custom: include file
ms.openlocfilehash: 569d7dfe251183962a14de1c42d85ee2e58950af
ms.sourcegitcommit: d8acf2fb0318708a3e8e1e259cb3747b0312b312
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/15/2020
ms.locfileid: "86401692"
---
## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด

* บริการหลักจะทำงานร่วมกับ[พื้นที่ทำงานใหม่](../collaborate-share/service-create-the-new-workspaces.md)เท่านั้น
* **ความจุเฉพาะของฉัน** ไม่ได้รับการสนับสนุนเมื่อใช้บริการหลัก
* ต้องใช้ความจุเฉพาะเมื่อย้ายไปยังการผลิต
* คุณไม่สามารถลงชื่อเข้าใช้พอร์ทัล Power BI ด้วยบริการหลัก
* คุณจำเป็นต้องมีสิทธิ์ของผู้ดูแลระบบ Power BI เพื่อเปิดใช้งานบริการหลักในการตั้งค่านักพัฒนาภายในพอร์ทัลผู้ดูแลระบบของ Power BI
* แอปพลิเคชัน [แบบฝังตัวสำหรับองค์กรของคุณ](../developer/embedded/embed-sample-for-your-organization.md) ไม่สามารถใช้บริการหลักได้
* [Dataflows](../transform-model/service-dataflows-overview.md) การจัดการไม่ได้รับการสนับสนุน
* ปัจจุบัน โครงร่างสำคัญของบริการไม่สนับสนุนผู้ดูแลระบบ APIs
* เมื่อใช้โครงร่างสำคัญของบริการด้วยแหล่งข้อมูล [Azure Analysis Services](https://docs.microsoft.com/azure/analysis-services/analysis-services-overview) โครงร่างสำคัญของบริการจะต้องมีสิทธิ์อินสแตนซ์ Azure Analysis Services การใช้กลุ่มความปลอดภัยที่ประกอบด้วยโครงร่างสำคัญของบริการสำหรับวัตถุประสงค์นี้ไม่ได้ผล
* บริการหลักไม่สามารถเข้าถึงแหล่งข้อมูลในเกตเวย์ได้ในขณะนี้ เช่น คุณไม่สามารถเพิ่มบริการหลักเป็นผู้ใช้แหล่งข้อมูลในเกตเวย์

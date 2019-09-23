---
title: Power BI ใช้นโยบายการเก็บข้อมูลโดยอัตโนมัติสำหรับข้อมูลแบบเรียลไทม์
description: เรียนรู้เกี่ยวกับนโยบายการเก็บข้อมูลโดยอัตโนมัติในบริการ Power BI
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 07726535246f8b115402373c315062151177d27c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "61347333"
---
# <a name="automatic-retention-policy-for-real-time-data"></a>นโยบายการเก็บข้อมูลโดยอัตโนมัติสำหรับข้อมูลแบบเรียลไทม์

นโยบายการเก็บข้อมูลโดยอัตโนมัติในบริการ Power BI คือ พารามิเตอร์สตริงคิวรีที่อนุญาตให้การเก็บข้อมูลใหม่สามารถล้างข้อมูลเก่าโดยอัตโนมัติในขณะที่ยังคงรักษาความต่อเนื่องของข้อมูลใหม่ที่จะลงในแดชบอร์ดของคุณ นโยบายการเก็บข้อมูลครั้งแรกจะเรียกว่า*ข้อมูลไหนเข้าก่อนข้อมูลนั้นออกก่อน (FIFO)* เมื่อเปิดใช้งานจะสามารถเก็บรวบรวมข้อมูลในตารางจนกว่าจะถึง 200,000 แถว เมื่อข้อมูลที่เกินกว่า 200,000 แถว ระบบจะค่อยๆ ทิ้งแถวเดิมในชุดข้อมูลออกไป ซึ่งจะอยู่ระหว่างแถวที่ 200,000 ถึงแถวที่ 210,000 ของข้อมูลล่าสุดเท่านั้น  
  
<center>

![นโยบายการเก็บข้อมูล](media/api-Automatic-retention-policy-for-real-time-data/retention-policy.png) 

</center>

นโยบายการเก็บข้อมูลจะเปิดใช้งานเมื่อคุณสร้างชุดข้อมูลครั้งแรก สิ่งที่คุณต้องทำคือการเพิ่มพารามิเตอร์คิวรี "นโยบายการเก็บข้อมูลค่าเริ่มต้น" เข้าไปยังชุดข้อมูล POST ของคุณจากนั้นให้เรียกใช้และตั้งค่าเท่ากับ*basicFIFO*  
  
    POST https://api.powerbi.com/v1.0/myorg/datasets?defaultRetentionPolicy={None | basicFIFO}
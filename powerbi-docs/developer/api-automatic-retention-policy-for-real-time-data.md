---
title: Power BI ใช้นโยบายการเก็บข้อมูลโดยอัตโนมัติสำหรับข้อมูลแบบเรียลไทม์
description: เรียนรู้เกี่ยวกับนโยบายการเก็บข้อมูลโดยอัตโนมัติในบริการ Power BI
author: markingmyname
manager: kfile
ms.author: maghan
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 9b5923c7bd92b1fe53ebb7ab9416aca8cece3cfa
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54294391"
---
# <a name="automatic-retention-policy-for-real-time-data"></a>นโยบายการเก็บข้อมูลโดยอัตโนมัติสำหรับข้อมูลแบบเรียลไทม์

นโยบายการเก็บข้อมูลโดยอัตโนมัติในบริการ Power BI คือ พารามิเตอร์สตริงคิวรีที่อนุญาตให้การเก็บข้อมูลใหม่สามารถล้างข้อมูลเก่าโดยอัตโนมัติในขณะที่ยังคงรักษาความต่อเนื่องของข้อมูลใหม่ที่จะลงในแดชบอร์ดของคุณ นโยบายการเก็บข้อมูลครั้งแรกจะเรียกว่า*ข้อมูลไหนเข้าก่อนข้อมูลนั้นออกก่อน (FIFO)* เมื่อเปิดใช้งานจะสามารถเก็บรวบรวมข้อมูลในตารางจนกว่าจะถึง 200,000 แถว เมื่อข้อมูลที่เกินกว่า 200,000 แถว ระบบจะค่อยๆ ทิ้งแถวเดิมในชุดข้อมูลออกไป ซึ่งจะอยู่ระหว่างแถวที่ 200,000 ถึงแถวที่ 210,000 ของข้อมูลล่าสุดเท่านั้น  
  
<center>

![นโยบายการเก็บข้อมูล](media/api-Automatic-retention-policy-for-real-time-data/retention-policy.png) 

</center>

นโยบายการเก็บข้อมูลจะเปิดใช้งานเมื่อคุณสร้างชุดข้อมูลครั้งแรก สิ่งที่ต้องทำคือเพิ่มคิวรีพารามิเตอร์ "defaultRetentionPolicy" เข้าไปยังชุดข้อมูลโพสต์ของคุณจากนั้นให้เรียกใช้และตั้งค่าเท่ากับ*basicFIFO*  
  
    POST https://api.powerbi.com/v1.0/myorg/datasets?defaultRetentionPolicy={None | basicFIFO}
---
title: เชื่อมต่อกับฐานข้อมูล Google BigQuery ใน Power BI Desktop
description: เชื่อมต่อและใช้ Google BigQuery ใน Power BI Desktop ได้อย่างง่ายดาย
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: e47dd26c6a8433777f0c4d3ef15cce41225cf03a
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "65514668"
---
# <a name="connect-to-a-google-bigquery-database-in-power-bi-desktop"></a>เชื่อมต่อกับฐานข้อมูล Google BigQuery ใน Power BI Desktop
ใน Power BI Desktop คุณสามารถเชื่อมต่อกับฐานข้อมูล Google **BigQuery** และใช้ข้อมูลพื้นฐานได้เช่นเดียวกับแหล่งข้อมูลอื่น ๆ ใน Power BI Desktop

## <a name="connect-to-google-bigquery"></a>เชื่อมต่อกับ Google BigQuery
การเชื่อมต่อกับฐานข้อมูล Google **BigQuery** เลือก**รับข้อมูล**จากริบบิ้น**หน้าแรก** ใน Power BI Desktop เลือก**ฐานข้อมูล**จากหมวดทางด้านซ้าย แล้วคุณจะเห็น **Google BigQuery**

![รับกล่องโต้ตอบข้อมูลสำหรับ Google BigQuery](media/desktop-connect-bigquery/connect_bigquery_01.png)

ในหน้าต่าง **Google BigQuery** ที่ปรากฏขึ้น ให้ลงชื่อเข้าใช้บัญชีผู้ใช้ Google BigQuery แล้วเลือก**เชื่อมต่อ**

![ลงชื่อเข้าใช้ Google BigQuery](media/desktop-connect-bigquery/connect_bigquery_02.png)

เมื่อคุณลงชื่อเข้าใช้แล้ว คุณจะเห็นหน้าต่างต่อไปนี้ที่ระบุว่าคุณได้รับการตรวจสอบสิทธิ์แล้ว 

![ลงชื่อเข้าใช้ Google](media/desktop-connect-bigquery/connect_bigquery_02b.png)

เมื่อเชื่อมต่อเสร็จเรียบร้อยแล้ว หน้าต่าง**ตัวนำทาง**จะปรากฏขึ้น และแสดงข้อมูลที่พร้อมใช้งานบนเซิร์ฟเวอร์ ซึ่งคุณสามารถเลือกองค์ประกอบหนึ่งรายการหรือหลายรายการเพื่อนำเข้าและใช้ใน**Power BI Desktop** ได้

![ข้อมูลจาก Google BigQuery](media/desktop-connect-bigquery/connect_bigquery_03.png)

## <a name="considerations-and-limitations"></a>ข้อควรพิจารณาและข้อจำกัด
มีข้อจำกัดและข้อควรพิจารณาบางอย่างเกี่ยวกับตัวเชื่อมต่อ Google **BigQuery**:

* ตัวเชื่อมต่อ Google BigQuery มีให้บริการใน Power BI Desktop และบริการของ Power BI ในบริการ Power BI สามารถเข้าถึงตัวเชื่อมต่อได้โดยใช้การเชื่อมต่อแบบคลาวด์กับคลาวด์จาก Power BI ไปยัง Google BigQuery

คุณสามารถใช้ Power BI กับ **โครงการการเรียกเก็บเงิน**ของ Google BigQuery ได้ ตามค่าเริ่มต้น Power BI จะใช้โครงการแรกจากรายการที่ส่งคืนให้สำหรับผู้ใช้ การกำหนดลักษณะการทำงานของโครงการเรียกเก็บเงินเมื่อใช้กับ Power BI ให้ทำตามขั้นตอนต่อไปนี้:

 * ระบุตัวเลือกต่อไปนี้ใน M พื้นฐานในขั้นตอนแหล่งข้อมูล ซึ่งสามารถกำหนดเองโดยใช้ **Power Query Editor** ใน Power BI Desktop:

    ```Source = GoogleBigQuery.Database([BillingProject="Include-Billing-Project-Id-Here"])```

## <a name="next-steps"></a>ขั้นตอนถัดไป
มีข้อมูลหลากหลายประเภทที่คุณสามารถเชื่อมต่อโดยใช้ Power BI Desktop สำหรับข้อมูลเพิ่มเติมเกี่ยวกับแหล่งข้อมูล โปรดดูทรัพยากรต่อไปนี้:

* [Power BI Desktop คืออะไร](desktop-what-is-desktop.md)
* [แหล่งข้อมูลใน Power BI Desktop](desktop-data-sources.md)
* [จัดรูปทรงและรวมข้อมูลด้วย Power BI Desktop](desktop-shape-and-combine-data.md)
* [เชื่อมต่อกับเวิร์กบุ๊ก Excel ใน Power BI Desktop](desktop-connect-excel.md)   
* [ป้อนข้อมูลลงใน Power BI Desktop โดยตรง](desktop-enter-data-directly-into-desktop.md)   


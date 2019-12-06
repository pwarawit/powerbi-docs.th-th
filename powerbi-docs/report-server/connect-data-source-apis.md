---
title: เปลี่ยนแปลงชุดอักขระการเชื่อมต่อต้นทางของข้อมูลผ่าน PowerShell
description: เปลี่ยนสตริงการเชื่อมต่อแหล่งข้อมูลโดยใช้ API ใน PowerShell - เซิร์ฟเวอร์รายงาน Power BI
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 10/24/2019
ms.author: maggies
ms.openlocfilehash: 77716514ffbb6dc8d3f128ada85276b46bf7af05
ms.sourcegitcommit: 17f45a81b0dcbf9e3f1fb2a551584170baecd320
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/25/2019
ms.locfileid: "72923676"
---
# <a name="change-data-source-connection-strings-in-power-bi-reports-with-powershell---power-bi-report-server"></a>เปลี่ยนสตริงการเชื่อมต่อแหล่งข้อมูลในรายงาน Power BI ด้วย PowerShell - เซิร์ฟเวอร์รายงาน Power BI

คุณสามารถเปลี่ยนสตริงการเชื่อมต่อแหล่งข้อมูลในรายงาน Power BI ในเซิร์ฟเวอร์รายงาน Power BI โดยใช้ API ใน PowerShell 

1. ติดตั้งแอปเพล็ตคำสั่ง PowerShell ของเซิร์ฟเวอร์รายงาน Power BI ค้นหาคำแนะนำเกี่ยวกับแอปเพล็ตคำสั่งและการติดตั้งที่ [https://github.com/Microsoft/ReportingServicesTools](https://github.com/Microsoft/ReportingServicesTools) 

2. ดึงข้อมูลแหล่งข้อมูลที่มีอยู่สำหรับไฟล์ Power BI ผ่านทางแอปเพล็ตคำสั่ง PowerShell

    ```powershell
    Get-RsRestItemDataSource -RsItem '/MyPbixReport'
    ```

    วิธีการดูข้อมูลสำหรับแหล่งข้อมูลแรกที่มีอยู่ในรายงาน Power BI: 

    ```powershell
    $dataSources[0]
    ```

3. อัปเดตข้อมูลการเชื่อมต่อและข้อมูลประจำตัวตามความจำเป็น ถ้าการอัปเดตสตริงการเชื่อมต่อและแหล่งข้อมูลทำให้ใช้ข้อมูลประจำตัวที่เก็บไว้ คุณจำเป็นต้องใส่รหัสผ่านของบัญชี 

    วิธีการอัปเดตสตริงการเชื่อมต่อแหล่งข้อมูล

    ```powershell
    $dataSources[0].ConnectionString = 'data source=myCatalogServer;initial catalog=ReportServer;persist security info=False' 
    ```

    วิธีการเปลี่ยนชนิดข้อมูลประจำตัวของแหล่งข้อมูล:

    ```powershell
    $dataSources[0].DataModelDataSource.AuthType = 'Integrated'
    ```

    วิธีการเปลี่ยนชื่อผู้ใช้/รหัสผ่านของแหล่งข้อมูล:

    ```powershell
    $dataSources[0].DataModelDataSource.Username = 'domain\user
    ```
    ```powershell
    $dataSources[0].DataModelDataSource.Secret = 'password'
    ```

4. บันทึกข้อมูลประจำตัวที่อัปเดตแล้วกลับไปยังเซิร์ฟเวอร์

    ```powershell
    Set-RsRestItemDataSource -RsItem '/MyPbixReport' -RsItemType 'PowerBIReport' -DataSources $dataSources
    ```

## <a name="next-steps"></a>ขั้นตอนถัดไป

[แหล่งข้อมูลรายงานที่มีการแบ่งหน้าในเซิร์ฟเวอร์รายงาน Power BI](connect-data-sources.md) 

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](https://community.powerbi.com/)

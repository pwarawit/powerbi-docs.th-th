---
title: PowerShell cmdlet, REST Api และ.NET SDK สำหรับผู้ดูแลระบบ
description: เรียนรู้เกี่ยวกับวิธีคุณสามารถจัดการ Power BI ด้วยสคริปต์และ การเขียนโปรแกรม Api
author: mgblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 1d4b579d00b2ecb0ce67fc66d90588e9f301e7c3
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/09/2019
ms.locfileid: "73856686"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>PowerShell cmdlet, REST Api และ.NET SDK สำหรับการจัดการ Power BI
Power BI ช่วยให้ผู้ดูแลระบบสามารถเขียนสคริปต์งานทั่วไปด้วย cmdlet ของ PowerShell และยังยอมให้ใช้ REST Api และ .NET SDK สำหรับการพัฒนาโซลูชันการดูแลระบบ หัวข้อนี้แสดงรายการ cmdlet และวิธีของ SDK ที่เหมือนกันและจุดปลายทางของ REST API สำหรับข้อมูลเพิ่มเติม ให้ด:

- PowerShell [ดาวน์โหลด](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/)และ[เอกสาร](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
- REST API [เอกสาร ](https://docs.microsoft.com/rest/api/power-bi/admin)
- .NET SDK [ดาวน์โหลด](https://www.nuget.org/packages/Microsoft.PowerBI.Api/)

> Cmdlets ด้านล่างนี้ควรถูกเรียกใช้ร่วมกับ `-Scope Organization` ในการดูแลระบบของผู้เช่า

| **ชื่อ Cmdlet** | **นามแฝง** | **เมธอด SDK** | **ปลายทางของ REST API** | **คำอธิบาย** |
| --- | --- | --- | --- | --- |
| `Get-PowerBIDatasource` | N/A | `Datasets_GetDataSourcesAsAdmin` | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | รับแหล่งข้อมูลสำหรับชุดข้อมูลที่ระบุ |
| `Get-PowerBIDataset` | N/A | `Datasets_GetDatasetsAsAdmin` | /v1.0/myorg/admin/datasets | รับรายการทั้งหมดของชุดข้อมูลในผู้เช่า Power BI |
| `Get-PowerBIWorkspace` | `Get-PowerBIGroup` | `Groups_GetGroupsAsAdmin` | /v1.0/myorg/admin/groups | รับรายการทั้งหมดของชุดข้อมูลในผู้เช่า Power BI |
| `Add-PowerBIWorkspaceUser` | `Add-PowerBIGroupUser` | `Groups_AddUserAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/users | เพิ่มผู้ใช้เป็นสมาชิกของพื้นที่ทำงานที่ระบุ |
| `Remove-PowerBIWorkspaceUser` | `Remove-PowerBIGroupUser` | `Groups_DeleteUserAsAdmin` | / v1.0/myorg/admin/groups/{groupId}/users/{user } | ลบผู้ใช้จากรายการสมาชิกของพื้นที่ทำงานที่ระบุ |
| `Restore-PowerBIWorkspace` |`Restore-PowerBIGroup` | `Groups_RestoreDeletedGroupAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/restore | คืนค่าพื้นที่ทำงานที่ถูกลบ |
| `Set-PowerBIWorkspace` |`Set-PowerBIGroup` | `Groups_UpdateGroupAsAdmin` | / v1.0/myorg/admin/groups/{groupId } | ปรับปรุงคุณสมบัติของพื้นที่ทำงานที่ระบุ |
| `Get-PowerBIDataset -WorkspaceId` | N/A | `Groups_GetDatasetsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id }/ชุดข้อมูล | รับชุดข้อมูลอยู่ภายในพื้นที่ทำงานที่ระบุ |
| `Get-PowerBIReport` | N/A | `Reports_GetReportsAsAdmin` | /v1.0/myorg/admin/reports | รับรายการทั้งหมดของชุดข้อมูลในผู้เช่า Power BI |
| `Get-PowerBIDashboard` | N/A | `Dashboards_GetDashboardsAsAdmin` | /v1.0/myorg/admin/dashboards | รับรายการทั้งหมดของแดชบอร์ดในผู้เช่า Power BI |
| `Get-PowerBIDashboard -WorkspaceId` | N/A | `Groups_GetDashboardsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id }/แดชบอร์ด | รับแดชบอร์ดภายในพื้นที่ทำงานที่ระบุ |
| `Get-PowerBITile` | `Get-PowerBIDashboardTile` | `Dashboards_GetTilesAsAdmin` | /v1.0/myorg/admin/dashboards/{dashboard\_id}/ไทล์ | รับไทล์ของแดชบอร์ดที่ระบุ |
| `Get-PowerBIReport` | N/A | `Groups_GetReportsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/รายงาน | รับรายงานภายในพื้นที่ทำงานที่ระบุ |
| `Get-PowerBIImport` | N/A | `Imports_GetImportsAsAdmin` | /v1.0/myorg/admin/imports | รับรายการนำเข้าทั้งหมดในผู้เช่า Power BI |
| `Connect-PowerBIServiceAccount` | `Login-PowerBI` &  `Login-PowerBIServiceAccount` | N/A | N/A | ลงชื่อเข้าใช้ Power BI และเริ่มต้นเซสชัน |
| `Disconnect-PowerBIServiceAccount` | `Logout-PowerBI` & `Logout-PowerBIServiceAccount` | N/A | N/A | ออกจากระบบของ Power BI และปิดเซสชันที่มีอยู่ |
| `Invoke-PowerBIRestMethod`| N/A | N/A | N/A | ส่งเรียกใช้ REST API แบบกำหนดเองไปยัง Power BI |
| `Get-PowerBIAccessToken`| N/A | N/A | N/A | รับโทเค็นการเข้าถึง Power BI ในเซสชัน |
| `Resolve-PowerBIError`| N/A | N/A | N/A | รับข้อมูลข้อผิดพลาดสำหรับการเรียกใช้ cmdlet ที่ไม่ประสบความสำเร็จ |

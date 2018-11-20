---
title: PowerShell cmdlet, REST Api และ.NET SDK สำหรับผู้ดูแลระบบ
description: เรียนรู้เกี่ยวกับวิธีคุณสามารถจัดการ Power BI ด้วยสคริปต์และ การเขียนโปรแกรม Api
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: overview
ms.date: 06/25/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: f4455fef5a2ed0e7ee23ff8ca3a0b626cd695838
ms.sourcegitcommit: a1b7ca499f4ca7e90421511e9dfa61a33333de35
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/10/2018
ms.locfileid: "51508002"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>PowerShell cmdlet, REST Api และ.NET SDK สำหรับการจัดการ Power BI
Power BI ช่วยให้ผู้ดูแลระบบสามารถเขียนสคริปต์งานทั่วไปด้วย cmdlet ของ PowerShell และยังยอมให้ใช้ REST Api และ .NET SDK สำหรับการพัฒนาโซลูชันการดูแลระบบ หัวข้อนี้แสดงรายการ cmdlet และวิธีของ SDK ที่เหมือนกันและจุดปลายทางของ REST API สำหรับข้อมูลเพิ่มเติม ให้ด:

  - PowerShell [ดาวน์โหลด](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/)และ[เอกสาร](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
  - REST API [เอกสาร ](https://docs.microsoft.com/rest/api/power-bi/admin)
  - .NET SDK [ดาวน์โหลด](https://www.nuget.org/packages/Microsoft.PowerBI.Api/) 


| **ชื่อ Cmdlet** | **เมธอด SDK** | **ปลายทางของ REST API**  | **คำอธิบาย** |
| --- | --- | --- | --- |
| **รับ PowerBIDatasource** | ชุดข้อมูล\_GetDataSourcesAsAdmin | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | รับแหล่งข้อมูลสำหรับชุดข้อมูลที่ระบุ |
| **รับ PowerBIDataset** | ชุดข้อมูล\_GetDatasetsAsAdmin | /v1.0/myorg/admin/datasets | รับรายการทั้งหมดของชุดข้อมูลในผู้เช่า Power BI |
| **รับ-PowerBIWorkspace** | กลุ่ม\_GetGroupsAsAdmin | /v1.0/myorg/admin/groups | รับรายการทั้งหมดของชุดข้อมูลในผู้เช่า Power BI |
| **เพิ่ม-PowerBIWorkspaceUser** | กลุ่ม\_AddUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users | เพิ่มผู้ใช้เป็นสมาชิกของพื้นที่ทำงานที่ระบุ |
| **ลบ PowerBIWorkspaceUser** | กลุ่ม\_DeleteUserAsAdmin | / v1.0/myorg/admin/groups/{groupId}/users/{user } | ลบผู้ใช้จากรายการสมาชิกของพื้นที่ทำงานที่ระบุ |
| **คืนค่า-PowerBIWorkspace** | กลุ่ม\_RestoreDeletedGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId}/restore | คืนค่าพื้นที่ทำงานที่ถูกลบ |
| **ตั้งค่า-PowerBIWorkspace** | กลุ่ม\_UpdateGroupAsAdmin | / v1.0/myorg/admin/groups/{groupId } | ปรับปรุงคุณสมบัติของพื้นที่ทำงานที่ระบุ |
| **รับ PowerBIDataset - WorkspaceId** | กลุ่ม\_GetDatasetsAsAdmin | /v1.0/myorg/admin/groups/{group\_id }/ชุดข้อมูล | รับชุดข้อมูลอยู่ภายในพื้นที่ทำงานที่ระบุ |
| **ส่งออก-PowerBIReport** | รายงาน\_ExportReportAsAdmin | N/A | ส่งออกรายงานที่ระบุไปยังไฟล์ภายในเครื่อง |
| **รับ PowerBIReport** | รายงาน\_GetReportsAsAdmin | /v1.0/myorg/admin/reports | รับรายการทั้งหมดของชุดข้อมูลในผู้เช่า Power BI |
| **รับ PowerBIDashboard** | แดชบอร์ด\_GetDashboardsAsAdmin | /v1.0/myorg/admin/dashboards | รับรายการทั้งหมดของแดชบอร์ดในผู้เช่า Power BI |
| **รับ-PowerBIDashboard -WorkspaceId** | กลุ่ม\_GetDashboardsAsAdmin | /v1.0/myorg/admin/groups/{group\_id }/แดชบอร์ด | รับแดชบอร์ดภายในพื้นที่ทำงานที่ระบุ |
| **รับ PowerBITile - DashboardId** | แดชบอร์ด\_GetTilesAsAdmin | /v1.0/myorg/admin/dashboards/{dashboard\_id}/ไทล์ | รับไทล์ของแดชบอร์ดที่ระบุ |
| **รับ-PowerBIReport -WorkspaceId** | กลุ่ม\_GetReportsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/รายงาน | รับรายงานภายในพื้นที่ทำงานที่ระบุ |
| **รับ PowerBIImport** | นำเข้า\_GetImportsAsAdmin | /v1.0/myorg/admin/imports | รับรายการนำเข้าทั้งหมดในผู้เช่า Power BI |
| **เชื่อมต่อ-PowerBIServiceAccount** | N/A | N/A | ลงชื่อเข้าใช้ Power BI และเริ่มต้นเซสชัน |
| **ยุติเชื่อมต่อ-PowerBIServiceAccount** | N/A | N/A | ออกจากระบบของ Power BI และปิดเซสชันที่มีอยู่ |
| **เรียกใช้ PowerBIRestMethod** | N/A | N/A | ส่งเรียกใช้ REST API แบบกำหนดเองไปยัง Power BI |
| **รับ PowerBIAccessToken** | N/A | N/A | รับโทเค็นการเข้าถึง Power BI ในเซสชัน |
| **แก้ไข-PowerBIError** | N/A | N/A | รับข้อมูลข้อผิดพลาดสำหรับการเรียกใช้ cmdlet ที่ไม่ประสบความสำเร็จ |
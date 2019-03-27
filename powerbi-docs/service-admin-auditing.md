---
title: ใช้การตรวจสอบภายในองค์กรของคุณ
description: เรียนรู้วิธีการใช้การตรวจสอบภายในด้วย Power BI เพื่อตรวจติดตามและตรวจสอบการกระทำต่าง ๆ ที่ดำเนินการ คุณสามารถใช้ศูนย์การรักษาความปลอดภัยและการปฏิบัติตามนโยบายได้ หรือใช้ PowerShell
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Administration
ms.openlocfilehash: 27776b251734d025e4dcde9f525f321008647455
ms.sourcegitcommit: 20ae9e9ffab6328f575833be691073de2061a64d
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 03/22/2019
ms.locfileid: "58383496"
---
# <a name="using-auditing-within-your-organization"></a>ใช้การตรวจสอบภายในองค์กรของคุณ

การทราบว่าใครกำลังดำเนินการอะไร และในรายการใดใน Power BI ของคุณ เป็นสิ่งสำคัญที่สามารถช่วยให้องค์กรของคุณปฏิบัติตามข้อกำหนดได้ เช่น การปฏิบัติตามข้อบังคับการประชุมและการจัดการบันทึกต่าง ๆ ใช้การตรวจสอบ Power BI เพื่อตรวจสอบการกระทำที่ผู้ใช้ดำเนินการ เช่น "ดูรายงาน" และ "ดูแดชบอร์ด" คุณไม่สามารถใช้การตรวจสอบเพื่อตรวจสอบสิทธิ์

คุณทำงานกับการตรวจสอบในศูนย์การรักษาความปลอดภัยและการปฏิบัติตามนโยบาย Office 365 หรือใช้ PowerShell การตรวจสอบขึ้นอยู่กับหน้าที่การใช้งานใน Exchange Online ซึ่งถูกเตรียมพร้อมใช้งานมาโดยอัตโนมัติเพื่อรองรับ Power BI 

คุณสามารถกรองข้อมูลการตรวจสอบภายในได้ตามช่วงวัน ผู้ใช้ แดชบอร์ด รายงาน ชุดข้อมูล และประเภทกิจกรรมได้ นอกจากนี้ คุณยังสามารถดาวน์โหลดกิจกรรมในรูปแบบไฟล์ csv (คั่นด้วยจุลภาคค่า) เพื่อทำการวิเคราะห์แบบออฟไลน์ได้

## <a name="requirements"></a>ข้อกำหนด

คุณต้องเป็นไปตามข้อกำหนดเหล่านี้เพื่อเข้าถึงบันทึกการตรวจสอบภายใน:

* การเข้าถึงบันทึกการตรวจสอบใน Exchange Online ได้คุณจะต้องได้รับการแต่งตั้งให้เป็นผู้ดูแลระบบส่วนกลาง, ได้รับมอบหมายให้เข้าถึงบันทึกการตรวจสอบหรือได้รับอนุญาตให้สามารถเข้าดูข้อมูลได้อย่างเดียวเท่านั้น ตามค่าเริ่มต้น หน้าที่เหล่านี้จะถูกกำหนดให้กับกลุ่มจัดการปฏิบัติตามกฎระเบียบและการจัดการองค์กรบนหน้า**สิทธิ์**ในศูนย์การจัดการ Exchange

    เมื่อต้องการให้ผู้ใช้ที่ไม่ใช่ผู้ดูแลระบบเข้าถึงบันทึกการตรวจสอบบัญชีคุณต้องเพิ่มผู้ใช้คนนั้นให้เป็นสมาชิกของกลุ่มที่มีหน้าที่เหล่านี้ อีกวิธีหนึ่งคือ คุณสามารถสร้างกลุ่มแบบกำหนดหน้าที่เองในศูนย์การจัดการ Exchange และกำหนดหน้าที่ให้เข้าถึงบันทึกการตรวจสอบหรือดูบันทึกการตรวจสอบได้เท่านั้นให้กับกลุ่มนี้ จากนั้นเพิ่มบัญชีผู้ไม่ใช่คนดูแลระบบเข้าไปยังกลุ่มใหม่นี้ สำหรับข้อมูลเพิ่มเติม ดูได้ที่[การจัดการหน้าที่ให้กับกลุ่มใน Exchange Online](/Exchange/permissions-exo/role-groups)

    หากคุณไม่สามารถเข้าไปที่ศูนย์การจัดการ Exchange จากศูนย์การจัดการ Microsoft 365 ได้ให้ไปที่ https://outlook.office365.com/ecpและลงชื่อเข้าโดยใช้ข้อมูลประจำตัวของคุณ

* ถ้าคุณมีสิทธิ์เข้าถึงบันทึกการตรวจสอบภายใจ แต่ไม่ใช่ผู้ดูแลระบบส่วนกลางหรือผู้ดูแลระบบบริการ Power BI คุณจะไม่สามารถเข้าถึงพอร์ทัล Power BI ผู้ดูแลระบบได้ ในกรณีนี้ คุณต้องใช้ลิงก์ตรงไปยัง [ศูนย์การรักษาความปลอดภัยและการปฏิบัติตามนโยบาย Office 365](https://sip.protection.office.com/#/unifiedauditlog)

## <a name="accessing-your-audit-logs"></a>การเข้าถึงบันทึกการตรวจสอบของคุณ

หากต้องการเข้าถึงรายการบันทึก ก่อนอื่นให้ตรวจสอบให้แน่ใจว่าได้เปิดใช้งานการบันทึกใน Power BI สามารถดูข้อมูลเพิ่มเติมได้ที่ [บันทึกการตรวจสอบ](service-admin-portal.md#audit-logs) ในเอกสารประกอบของพอร์ทัลผู้ดูแลระบบ สามารถมีการหน่วงเวลาสูงสุด 48 ชั่วโมง ตั้งแต่การเปิดใช้งานการตรวจสอบ จนสามารถดูข้อมูลการตรวจสอบได้ ถ้าคุณยังไม่เห็นข้อมูลในทันที ดูบันทึกการตรวจสอบในภายหลัง อาจมีความล่าช้าแบบเดียวกันระหว่าง เวลาที่ได้รับสิทธิ์ในการดูบันทึกการตรวจสอบ จนถึงเวลาที่สามารถเข้าถึงแฟ้มบันทึก

บันทึกการตรวจสอบ Power BI จะพร้อมใช้งานโดยตรงผ่าน [ศูนย์การรักษาความปลอดภัยและการปฏิบัติตามนโยบาย Office 365](https://sip.protection.office.com/#/unifiedauditlog) และยังมีลิงก์จากพอร์ทัลผู้ดูแลระบบ Power BI:

1. ใน Power BI เลือก **ไอคอนเฟือง** มุมขวาด้านบน จากนั้นเลือก **พอร์ทัลผู้ดูแลระบบ**

   ![พอร์ทัลผู้ดูแลระบบ](media/service-admin-auditing/powerbi-admin.png)

1. เลือก**บันทึกการตรวจสอบ**

1. เลือก **ไปที่ศูนย์การจัดการ Microsoft 365**

   ![ไปที่ศูนย์การจัดการ Microsoft 365](media/service-admin-auditing/audit-log-o365-admin-center.png)

## <a name="search-only-power-bi-activities"></a>ค้นหากิจกรรม Power BI เท่านั้น

จำกัดผลลัพธ์เป็นกิจกรรม Power BI เท่านั้น โดยปฏิบัติตามขั้นตอนต่อไปนี้ สำหรับรายการของกิจกรรม โปรดดูรายการของ [กิจกรรมที่ตรวจสอบโดย Power BI](#activities-audited-by-power-bi) ภายหลังในบทความนี้

1. ที่หน้า **ค้นหาบันทึกการตรวจสอบ** ใต้ **ค้นหา** เลือกรายการดรอปดาวน์สำหรับ **กิจกรรม**

2. เลือก **กิจกรรม Power BI**

   ![บันทึกการตรวจสอบค้นหา](media/service-admin-auditing/audit-log-search-filter-by-powerbi.png)

3. เลือกที่ใดก็ได้ภายนอกกล่องการเลือกเพื่อปิด

ในตอนนี้ ระบบจะกรองการค้นหาของคุณให้เป็นเฉพาะกิจกรรม Power BI เท่านั้น

## <a name="search-the-audit-logs-by-date"></a>ค้นหาบันทึกการตรวจสอบตามวัน

คุณสามารถค้นหาบันทึกตามช่วงวันที่ได้โดยใช้เขตข้อมูล **วันเริ่มต้น** และ **วันที่สิ้นสุด** ระบบจะเลือกเจ็ดวันที่ผ่านมาตามค่าเริ่มต้น วันและเวลาจะแสดงในรูปแบบเวลามาตรฐานสากล (UTC) ช่วงวันที่สูงสุดที่คุณสามารถระบุได้คือ 90 วัน 

จะมีข้อผิดพลาดแสดงถ้าเลือกช่วงวันมีค่ามากกว่า 90 วัน หากคุณกำลังใช้ช่วงวันที่สูงสุด 90 วัน เลือกเวลาปัจจุบันสำหรับ **วันเริ่มต้น** มิฉะนั้น คุณจะได้รับข้อความข้อผิดพลาดที่แจ้งว่า วันเริ่มต้นอยู่ก่อนหน้าวันสิ้นสุด หากคุณเปิดการตรวจสอบภายในช่วง 90 วันที่ผ่านมา ช่วงวันที่จะไม่สามารถเริ่มก่อนวันที่ที่เปิดใช้งานการตรวจสอบ

![ค้นหาตามวันที่](media/service-admin-auditing/search-audit-log-by-date.png)

## <a name="search-the-audit-logs-by-users"></a>ค้นหาบันทึกการตรวจสอบตามผู้ใช้งาน

คุณสามารถค้นหารายการบันทึกการตรวจสอบสำหรับกิจกรรมต่าง ๆ ที่ดำเนินการโดยผู้ใช้ที่ระบุได้ หากต้องการดำเนินการนี้ ให้ใส่ชื่อผู้ใช้อย่างน้อยหนึ่งชื่อในเขตข้อมูล **ผู้ใช้** ชื่อผู้ใช้มีลักษณะเหมือนที่อยู่อีเมล กล่าวคือ เป็นบัญชีที่ผู้ใช้ใช้เข้าสู่ระบบ Power BI ปล่อยให้กล่องนี้ว่างไว้เพื่อกลับไปยังรายการสำหรับผู้ใช้ทั้งหมด (และบัญชีบริการ) ในองค์กรของคุณ

![ค้นหาตามผู้ใช้งาน](media/service-admin-auditing/search-audit-log-by-user.png)

## <a name="view-search-results"></a>ดูผลลัพธ์การค้นหา

หลังจากที่เลือก **ค้นหา** ระบบจะโหลดผลลัพธ์การค้นหา และจะแสดงอยู่ใต้ **ผลลัพธ์** หลังจากนั้นสักครู่ เมื่อเสร็จสิ้นการค้นหา จำนวนของผลลัพธ์ที่พบจะแสดงขึ้น ระบบจะสามารถแสดงเหตุการณ์ได้สูงสุด 1000 เหตุการณ์ หากมีเหตุการณ์มากกว่า 1000 เหตุการณ์ที่ตรงกับเกณฑ์การค้นหา ระบบจะแสดง 1000 เหตุการณ์ใหม่ล่าสุด

### <a name="view-the-main-results"></a>ดูผลลัพธ์หลัก

พื้นที่ **ผลลัพธ์** ประกอบด้วยข้อมูลต่อไปนี้สำหรับแต่ละเหตุการณ์ที่ส่งกลับโดยการค้นหา เลือกส่วนหัวของคอลัมน์ใต้ **ผลลัพธ์** เพื่อเรียงลำดับผลลัพธ์

| **แผนภูมิคอลัมน์** | **คำนิยาม** |
| --- | --- |
| วันที่ |วันและเวลา (ในรูปแบบ UTC) ที่เกิดเหตุการณ์ |
| ที่อยู่ IP |อยู่ IP ของอุปกรณ์ที่ใช้เมื่อบันทึกกิจกรรม ที่อยู่ IP จะแสดงในรูปแบบที่อยู่ IPv4 หรือ IPv6 |
| ผู้ใช้ |ผู้ใช้ (หรือบัญชีบริการ) ซึ่งเป็นผู้ที่ดำเนินการกระทำที่ก่อให้เกิดเหตุการณ์ |
| กิจกรรม |กิจกรรมที่ดำเนินการโดยผู้ใช้ ค่านี้สอดคล้องกับกิจกรรมที่คุณเลือกไว้ในรายการดรอปดาวน์ของ **กิจกรรม** สำหรับเหตุการณ์จากบันทึกการตรวจสอบผู้ดูแลระบบ Exchange ค่าในคอลัมน์นี้เป็น cmdlet Exchange |
| รายการ |ออบเจ็กต์จะถูกสร้างขึ้นหรือปรับเปลี่ยนเป็นผลลัพธ์ของกิจกรรมที่สอดคล้องกัน ตัวอย่างเช่น ไฟล์ที่มีการดูหรือถูกปรับเปลี่ยน หรือบัญชีผู้ใช้ที่มีการอัปเดต ไม่ใช่ทุกกิจกรรมที่่มีค่าในคอลัมน์นี้ |
| รายละเอียด |รายละเอียดเพิ่มเติมเกี่ยวกับกิจกรรม ไม่ใช่ทุกกิจกรรมที่จะมีค่านี้ |

### <a name="view-the-details-for-an-event"></a>ดูรายละเอียดของเหตุการณ์หนึ่ง ๆ

คุณสามารถดูรายละเอียดเพิ่มเติมเกี่ยวกับเหตุการณ์ได้ โดยการคลิกบันทึกเหตุการณ์ในรายการผลลัพธ์การค้นหา หน้า **รายละเอียด** จะแสดงขึ้น ซึ่งประกอบด้วยคุณสมบัติโดยละเอียดจากบันทึกเหตุการณ์ คุณสมบัติเหล่านี้จะแสดงโดยขึ้นอยู่กับบริการ Office 365 ที่เหตุการณ์นั้นเกิดขึ้น 

หากต้องการให้แสดงรายละเอียดเพิ่มเติม ให้เลือก **ข้อมูลเพิ่มเติม** รายการ Power BI ทั้งหมดมีค่า 20 สำหรับคุณสมบัติ RecordType สำหรับข้อมูลเกี่ยวกับคุณสมบัติอื่น ๆ ดู [คุณสมบัติโดยละเอียดในบันทึกการตรวจสอบ](/office365/securitycompliance/detailed-properties-in-the-office-365-audit-log/)

   ![รายละเอียดการตรวจสอบ](media/service-admin-auditing/audit-details.png)

## <a name="export-search-results"></a>ส่งออกผลลัพธ์การค้นหา

หากต้องการส่งออกบันทึกการตรวจสอบ Power BI เป็นไฟล์ csv ให้ปฏิบัติตามขั้นตอนดังต่อไปนี้

1. เลือก**ส่งออกผลลัพธ์**

1. เลือก**บันทึกผลลัพธ์ที่โหลด**หรือ**ดาวน์โหลดผลลัพธ์ทั้งหมด** อย่างใดอย่างหนึ่ง

    ![ส่งออกผลลัพธ์](media/service-admin-auditing/export-auditing-results.png)

## <a name="use-powershell-to-search-audit-logs"></a>ใช้ PowerShell เพื่อค้นหาบันทึกการตรวจสอบ

คุณยังสามารถใช้ PowerShell เพื่อเข้าถึงบันทึกการตรวจสอบโดยยึดตามการเข้าสู่ระบบของคุณได้ ตัวอย่างต่อไปนี้แสดงวิธีการเชื่อมต่อไปยัง Exchange Online PowerShell และใช้คำสั่ง [Search-UnifiedAuditLog](/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog?view=exchange-ps/) เพื่อดึงรายการบันทึกการตรวจสอบ Power BI หากต้องการให้สคริปต์ทำงาน คุณต้องได้รับการกำหนดสิทธิ์อย่างเหมาะสม ตามที่อธิบายไว้ในการส่วนของ[ข้อกำหนด](#requirements)

```powershell
Set-ExecutionPolicy RemoteSigned

$UserCredential = Get-Credential

$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection

Import-PSSession $Session
Search-UnifiedAuditLog -StartDate 9/11/2018 -EndDate 9/15/2018 -RecordType PowerBI -ResultSize 1000 | Format-Table | More
```

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการเชื่อมต่อกับ Exchange Online ดู[เชื่อมต่อกับ Exchange Online PowerShell](/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell/) ตัวอย่างอื่นของการใช้ PowerShell ด้วยบันทึกการตรวจสอบ ดู [การใช้บันทึกการตรวจสอบโดยใช้ Power BI และ PowerShell เพื่อกำหนดสิทธิ์การใช้งาน Power BI Pro](https://powerbi.microsoft.com/blog/using-power-bi-audit-log-and-powershell-to-assign-power-bi-pro-licenses/)

## <a name="activities-audited-by-power-bi"></a>กิจกรรมที่ตรวจสอบโดย Power BI

กิจกรรมต่อไปนี้ได้รับการตรวจสอบ โดย Power BI

| ชื่อที่เรียกง่าย                                     | ชื่อการดำเนินการ                              | บันทึกย่อ                                  |
|---------------------------------------------------|---------------------------------------------|------------------------------------------|
| เพิ่มแหล่งข้อมูลไปยังเกตเวย์ Power BI แล้ว             | AddDatasourceToGateway                      |                                          |
| เพิ่มการเข้าถึงโฟลเดอร์ Power BI แล้ว                      | AddFolderAccess                             | ยังไม่ได้ใช้ในปัจจุบัน                       |
| เพิ่มสมาชิกกลุ่ม Power BI แล้ว                      | AddGroupMembers                             |                                          |
| ผู้ดูแลระบบแนบบัญชีเก็บข้อมูลกระแสข้อมูลไปยังผู้เช่า | AdminAttachedDataflowStorageAccountToTenant | ยังไม่ได้ใช้ในปัจจุบัน                       |
| ชุดข้อมูล Power BI ที่วิเคราะห์แล้ว                         | AnalyzedByExternalApplication               |                                          |
| วิเคราะห์รายงาน Power BI แล้ว                          | AnalyzeInExcel                              |                                          |
| ผูกชุดข้อมูล Power BI ไปยังเกตเวย์แล้ว                | BindToGateway                               |                                          |
| เปลี่ยนแปลงสถานะความจุแล้ว                            | ChangeCapacityState                         |                                          |
| เปลี่ยนแปลงการกำหนดผู้ใช้ความจุแล้ว                  | UpdateCapacityUsersAssignment               |                                          |
| เปลี่ยนแปลงการเชื่อมต่อชุดข้อมูล Power BI แล้ว              | SetAllConnections                           |                                          |
| เปลี่ยนผู้ดูแลระบบเกตเวย์ Power BI แล้ว                   | ChangeGatewayAdministrators                 |                                          |
| เปลี่ยนผู้ใช้แหล่งข้อมูลเกตเวย์ Power IB แล้ว        | ChangeGatewayDatasourceUsers                |                                          |
| สร้างชุดเนื้อหา Power BI ขององค์กรแล้ว      | CreateOrgApp                                |                                          |
| สร้างแอป Power BI แล้ว                              | CreateApp                                   |                                          |
| สร้างแดชบอร์ด Power BI แล้ว                        | CreateDashboard                             |                                          |
| สร้างกระแสข้อมูล Power BI แล้ว                         | CreateDataflow                              |                                          |
| สร้างชุดข้อมูล Power BI แล้ว                          | CreateDataset                               |                                          |
| สร้างการสมัครใช้งานอีเมล Power BI แล้ว               | CreateEmailSubscription                     |                                          |
| สร้างโฟลเดอร์ Power BI แล้ว                           | CreateFolder                                |                                          |
| เกตเวย์ Power BI ที่สร้างขึ้น                          | CreateGateway                               |                                          |
| สร้างกลุ่ม Power BI แล้ว                            | CreateGroup                                 |                                          |
| สร้างรายงาน Power BI แล้ว                           | CreateReport                                |                                          |
| กระแสข้อมูลที่ย้ายไปยังบัญชีเก็บข้อมูลภายนอก     | DataflowMigratedToExternalStorageAccount    | ยังไม่ได้ใช้ในปัจจุบัน                       |
| การให้สิทธิ์กระแสข้อมูลที่เพิ่มเข้าไป                        | DataflowPermissionsAdded                    | ยังไม่ได้ใช้ในปัจจุบัน                       |
| การให้สิทธิ์กระแสข้อมูลที่ถูกลบ                      | DataflowPermissionsRemoved                  | ยังไม่ได้ใช้ในปัจจุบัน                       |
| ลบชุดเนื้อหา Power BI ขององค์กรแล้ว      | DeleteOrgApp                                |                                          |
| ลบข้อคิดเห็น Power BI แล้ว                          | DeleteComment                               |                                          |
| ลบแดชบอร์ด Power BI แล้ว                        | DeleteDashboard                             | ยังไม่ได้ใช้ในปัจจุบัน                       |
| ลบกระแสข้อมูล Power BI แล้ว                         | DeleteDataflow                              | ยังไม่ได้ใช้ในปัจจุบัน                       |
| ลบชุดข้อมูล Power BI แล้ว                          | DeleteDataset                               |                                          |
| ลบการสมัครใช้งานอีเมล Power BI แล้ว               | DeleteEmailSubscription                     |                                          |
| ลบโฟลเดอร์ Power BI แล้ว                           | DeleteFolder                                |                                          |
| ลบการเข้าถึงโฟลเดอร์ Power BI แล้ว                    | DeleteFolderAccess                          | ยังไม่ได้ใช้ในปัจจุบัน                       |
| เกตเวย์ Power BI ที่ตรวจพบ                          | DeleteGateway                               |                                          |
| ลบกลุ่ม Power BI แล้ว                            | DeleteGroup                                 |                                          |
| ลบรายงาน Power BI แล้ว                           | DeleteReport                                |                                          |
| ค้นพบแหล่งข้อมูลสำหรับชุดข้อมูล Power BI แล้ว          | GetDatasources                              |                                          |
| รายงาน Power BI ที่ดาวน์โหลด                        | DownloadReport                              |                                          |
| แก้ไขการให้สิทธิ์ใบรับรอง Power BI แล้ว          | EditCertificationPermission                 | ยังไม่ได้ใช้ในปัจจุบัน                       |
| แก้ไขแดชบอร์ด Power BI แล้ว                         | EditDashboard                               | ยังไม่ได้ใช้ในปัจจุบัน                       |
| แก้ไขชุดข้อมูล Power BI แล้ว                           | EditDataset                                 |                                          |
| แก้ไขคุณสมบัติของชุดข้อมูล Power BI แล้ว                | EditDatasetProperties                       | ยังไม่ได้ใช้ในปัจจุบัน                       |
| แก้ไขรายงาน Power BI แล้ว                            | EditReport                                  |                                          |
| ส่งออกกระแสข้อมูล Power BI แล้ว                        | ExportDataflow                              |                                          |
| ส่งออกข้อมูลภาพรายงาน Power BI แล้ว              | ExportReport                                |                                          |
| ส่งออกข้อมูลไทล์ Power BI แล้ว                       | ExportTile                                  |                                          |
| การเพิ่มสิทธิ์กระแสข้อมูลล้มเหลว                | FailedToAddDataflowPermissions              | ยังไม่ได้ใช้ในปัจจุบัน                       |
| การลบสิทธิ์กระแสข้อมูลล้มเหลว             | FailedToRemoveDataflowPermissions           | ยังไม่ได้ใช้ในปัจจุบัน                       |
| สร้างโทเค็น SAS ของกระแสข้อมูล Power BI แล้ว             | GenerateDataflowSasToken                    |                                          |
| สร้างโทเค็นแบบฝังตัวของ Power BI แล้ว                    | GenerateEmbedToken                          |                                          |
| นำเข้าไฟล์ไปยัง Power BI แล้ว                         | นำเข้า                                      |                                          |
| ติดตั้ง Power BI แล้ว                            | InstallApp                                  |                                          |
| โยกย้ายพื้นที่ทำงานของแอปไปยังความจุแล้ว                  | MigrateWorkspaceIntoCapacity                |                                          |
| โพสต์ข้อคิดเห็น Power BI แล้ว                           | PostComment                                 |                                          |
| พิมพ์แดชบอร์ด Power BI แล้ว                        | PrintDashboard                              |                                          |
| พิมพ์หน้ารายงาน Power BI แล้ว                      | PrintReport                                 |                                          |
| เผยแพร่รายงาน Power BI ไปยังเว็บแล้ว                  | PublishToWebReport                          |                                          |
| ได้รับข้อมูลลับสำหรับกระแสข้อมูล Power BI จาก Key Vault แล้ว  | ReceiveDataflowSecretFromKeyVault           | ยังไม่ได้ใช้ในปัจจุบัน                       |
| ลบแหล่งข้อมูลออกจากเกตเวย์ Power BI แล้ว         | RemoveDatasourceFromGateway                 |                                          |
| ลบสมาชิกกลุ่ม Power BI แล้ว                    | DeleteGroupMembers                          |                                          |
| ลบพื้นที่ทำงานออกจากความจุแล้ว                 | RemoveWorkspacesFromCapacity                |                                          |
| เปลี่ยนชื่อแดชบอร์ด Power BI แล้ว                        | RenameDashboard                             |                                          |
| ร้องขอการรีเฟรชกระแสข้อมูล Power BI แล้ว               | RequestDataflowRefresh                      | ยังไม่ได้ใช้ในปัจจุบัน                       |
| ร้องขอการรีเฟรชชุดข้อมูล Power BI แล้ว                | RefreshDataset                              |                                          |
| เรียกคืนพื้นที่ทำงาน Power BI แล้ว                     | GetWorkspaces                               |                                          |
| ตั้งค่าการรีเฟรชตามกำหนดเวลาบนกระแสข้อมูล Power BI        | SetScheduledRefreshOnDataflow               |                                          |
| ตั้งค่าการรีเฟรชตามกำหนดเวลาบนชุดข้อมูล Power BI         | SetScheduledRefresh                         |                                          |
| แชร์แดชบอร์ด Power BI แล้ว                         | ShareDashboard                              |                                          |
| แชร์รายงาน Power BI แล้ว                            | ShareReport                                 |                                          |
| เริ่มใช้งาน Power BI เวอร์ชั่นทดลองใช้ที่ขยายเวลา                   | OptInForExtendedProTrial                    | ยังไม่ได้ใช้ในปัจจุบัน                       |
| เริ่มต้นใช้งานเวอร์ชันทดลองของ Power BI แล้ว                            | OptInForProTrial                            |                                          |
| เข้าควบคุมแหล่งข้อมูล Power BI แล้ว                   | TakeOverDataset                          |                                          |
| เข้าควบคุมชุดข้อมูล Power BI แล้ว                        | TakeOverDataset                             |                                          |
| ยกเลิกเผยแพร่แอป Power BI แล้ว                          | UnpublishApp                                |                                          |
| อัปเดตการตั้งค่าการกำกับดูแลทรัพยากรความจุ      | UpdateCapacityResourceGovernanceSettings    | ปัจจุบันไม่อยู่ในศูนย์การจัดการ Microsoft 365 |
| อัปเดตผู้ดูแลความจุแล้ว                            | UpdateCapacityAdmins                        |                                          |
| อัปเดตชื่อที่แสดงความจุแล้ว                     | UpdateCapacityDisplayName                   |                                          |
| อัปเดตการตั้งค่า Power BI ขององค์กรแล้ว          | UpdatedAdminFeatureSwitch                   |                                          |
| อัปเดตแอป Power BI แล้ว                              | UpdateApp                                   |                                          |
| อัปเดตกระแสข้อมูล Power BI แล้ว                         | UpdateDataflow                              |                                          |
| อัปเดตแหล่งข้อมูลสำหรับชุดข้อมูล Power BI แล้ว             | UpdateDatasources                           |                                          |
| อัปเดตพารามิเตอร์สำหรับชุดข้อมูล Power BI แล้ว               | UpdateDatasetParameters                     |                                          |
| อัปเดตการสมัครใช้งานอีเมล Power BI แล้ว               | UpdateEmailSubscription                     |                                          |
| อัปเดตโฟลเดอร์ Power BI แล้ว                           | UpdateFolder                                |                                          |
| อัปเดตการเข้าถึงโฟลเดอร์ Power BI แล้ว                    | UpdateFolderAccess                          |                                          |
| อัปเดตข้อมูลประจำตัวแหล่งข้อมูลเกตเวย์ Power IB แล้ว  | UpdateDatasourceCredentials                 |                                          |
| ดูแดชบอร์ด Power BI แล้ว                         | ViewDashboard                               |                                          |
| ดูกระแสข้อมูล Power BI แล้ว                          | ViewDataflow                                |                                          |
| ดูรายงาน Power BI แล้ว                            | ViewReport                                  |                                          |
| ดูไทล์ Power BI แล้ว                              | ViewTile                                    |                                          |
| ดูเมตริกการใช้งาน Power BI แล้ว                     | ViewUsageMetrics                            |                                          |
|                                                   |                                             |                                          |

## <a name="next-steps"></a>ขั้นตอนถัดไป

[การดูแลระบบ Power BI คืออะไร?](service-admin-administering-power-bi-in-your-organization.md)  

[พอร์ทัลผู้ดูแล Power BI](service-admin-portal.md)  

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](http://community.powerbi.com/)

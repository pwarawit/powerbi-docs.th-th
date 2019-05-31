---
title: แก้ไขปัญหาการรีเฟรชตามกำหนดเวลาในเซิร์ฟเวอร์รายงาน Power BI
description: บทความนี้อธิบายถึงทรัพยากรมีให้เพื่อใช้แก้ไขปัญหา รีเฟรชตามกำหนดเวลาในเซิร์ฟเวอร์รายงาน Power BI
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 11/01/2017
ms.author: mblythe
ms.openlocfilehash: f4638250cb2ae245dc9ce222e43c7a87de6e395d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "61200307"
---
# <a name="troubleshoot-scheduled-refresh-in-power-bi-report-server"></a>แก้ไขปัญหาการรีเฟรชตามกำหนดเวลาในเซิร์ฟเวอร์รายงาน Power BI
บทความนี้อธิบายถึงทรัพยากรมีให้เพื่อใช้แก้ไขปัญหา รีเฟรชตามกำหนดเวลาในเซิร์ฟเวอร์รายงาน Power BI

เมื่อมีปัญหาใหม่ ๆ เกิดขึ้น บทความนี้จะถูกปรับปรุงด้วยข้อมูลที่จะช่วยคุณได้

## <a name="common-issues"></a>ปัญหาที่พบบ่อย
ต่อไปนี้คือ ปัญหาที่พบได้บ่อย ที่คุณอาจจะเจอขณะพยายามกำหนดเวลารีเฟรชสำหรับรายงาน 

### <a name="driver-related-problems"></a>ปัญหาที่เกี่ยวข้องกับโปรแกรมควบคุม
การเชื่อมต่อกับแหล่งข้อมูลต่าง ๆ อาจจำเป็นต้องมีการติดตั้งโปรแกรมควบคุมจากบุคคลที่สาม เพื่อให้เชื่อมต่อได้สำเร็จ ไม่เพียงคุณจำเป็นต้องติดตั้งบนเครื่องที่คุณกำลังใช้ Power BI Desktop เท่านั้น แต่คุณยังจำเป็นต้องติดตั้งโปรแกรมควบคุมนั้นอยู่บนเซิร์ฟเวอร์รายงานด้วย

โปรแกรมควบคุมอาจจะมาในรูป 32 บิต และ 64 บิต ตรวจสอบให้แน่ใจว่าได้ติดตั้งไดรเวอร์ 64 Power BI บิต เนื่องจากเซิร์ฟเวอร์รายงานเป็นแบบ 64 บิต

โปรดอ้างอิงไปยังผู้ผลิต สำหรับรายละเอียดเกี่ยวกับวิธีการติดตั้ง และกำหนดค่าโปรแกรมควบคุมจากบุคคลที่สาม

### <a name="memory-pressure"></a>หน่วยความจำไม่เพียงพอ
หน่วยความจำไม่เพียงพอ สามารถเกิดขึ้นได้เมื่อรายงานต้องใช้หน่วยความจำเพิ่มขึ้น เพื่อประมวลผลและแสดงผล การรีเฟรชตามกำหนดเวลาบนรายงาน อาจต้องการหน่วยความจำบนเครื่องเป็นจำนวนมาก โดยเฉพาะอย่างยิ่งสำหรับรายงานที่มีขนาดใหญ่ ปัญหาหน่วยความจำไม่เพียงพอ อาจก่อให้เกิดความล้มเหลวในการรายงาน และมีโอกาสทำให้เซิร์ฟเวอร์รายงานหยุดทำงาน

ถ้าคุณกำลังประสบปัญหาเรื่องหน่วยความจำอยู่เสมอ มันอาจถึงเวลาแล้วที่จะมองไปที่การปรับใช้แบบแนวกว้าง เพื่อกระจายการใช้ทรัพยากร คุณยังสามารถกำหนดได้ว่า จะใช้เซิร์ฟเวอร์รายงานตัวไหนเพื่อรีเฟรช ด้วยการตั้งค่า `IsDataModelRefreshService` ภายใน rsreportserver.config ได้ ด้วยการตั้งค่านี้ คุณสามารถกำหนดหนึ่งหรือหลายเซิร์ฟเวอร์ ให้เป็นเซิร์ฟเวอร์ front end เพื่อจัดการกับรายงานตามความต้องการ และมีชุดของเซิร์ฟเวอร์อีกชุดที่จะใช้สำหรับรีเฟรชตามกำหนดเวลาเท่านั้น

สำหรับข้อมูลเกี่ยวกับวิธีการตรวจสอบอินสแตนซ์ Analysis Services ดู[ตรวจสอบอินสแตนซ์ Analysis Services](https://docs.microsoft.com/sql/analysis-services/instances/monitor-an-analysis-services-instance)

สำหรับข้อมูลเกี่ยวกับการตั้งค่าหน่วยความจำภายใน Analysis Services ดู[คุณสมบัติหน่วยความจำ](https://docs.microsoft.com/sql/analysis-services/server-properties/memory-properties)

### <a name="kerberos-configuration"></a>การกำหนดค่า Kerberos
การเชื่อมต่อกับแหล่งข้อมูลด้วยข้อมูลประจำตัว Windows อาจจำเป็นต้องกำหนดการมอบหมายที่มีข้อจำกัดของ Kerberos เพื่อให้การเชื่อมต่อสำเร็จ สำหรับข้อมูลเพิ่มเติมเกี่ยวกับวิธีการกำหนดค่าการมอบหมายที่มีข้อจำกัดของ Kerberos ดู[การกำหนดค่า Kerberos เพื่อใช้กับ Power BI](configure-kerberos-powerbi-reports.md)

## <a name="known-issues"></a>ปัญหาที่ทราบแล้ว
ข้อมูลเกี่ยวกับปัญหาที่ทราบแล้ว จะแสดงอยู่ที่นี่เมื่อมีข้อมูลพร้อมให้บริการ

## <a name="configuration-settings"></a>การกำหนดค่า
การตั้งค่าต่อไปนี้อาจมีผลต่อการรีเฟรชตามกำหนดเวลา การตั้งค่าที่ตั้งจากภายใน SQL Server Management Studio (SSMS) จะมีผลกับทุก ๆ เซิร์ฟเวอร์รายงาน ภายในการปรับใช้แบบแนวกว้าง การตั้งค่าที่กำหนดใน rsreportserver.config จะมีผลเฉพาะเซิร์ฟเวอร์ที่ตั้งค่านั้น

**การตั้งค่าภายใน SSMS:**

| การตั้งค่า | คำอธิบาย |
| --- | --- |
| MaxFileSizeMb |ขนาดไฟล์สูงสุดสำหรับรายงานที่อัปโหลด ค่าเริ่มต้นคือ 1000 MB (1 GB) ค่าสูงสุดคือ 2000 MB (2 GB) |
| ModelCleanupCycleMinutes |กำหนดว่ารูปแบบมีการตรวจสอบบ่อยแค่ไหน เพื่อลบออกจากหน่วยความจำ ค่าเริ่มต้นคือ 15 นาที |
| ModelExpirationMinutes |กำหนดว่าเวลานานเท่าไรนับจากการใช้งานล่าสุด ที่รูปแบบจะหมดอายุและลบออกจากหน่วยความจำ ค่าเริ่มต้นคือ 60 นาที |
| ScheduleRefreshTimeoutMinutes |กำหนดว่าการรีเฟรชข้อมูลสามารถใช้เวลานานแค่ไหน สำหรับแต่ละโหมด ค่าเริ่มต้นคือ 120 นาที ไม่มีขีดจำกัดสูงสุด |

**การตั้งค่าภายใน rsreportserver.config:**

```xml
<Configuration>
    <Service>
        <PollingInterval>10</PollingInterval>
        <IsDataModelRefreshService>false</IsDataModelRefreshService>
        <MaxQueueThreads>0</MaxQueueThreads>
    </Service>
</Configuration>
```

## <a name="tools-for-troubleshooting"></a>เครื่องมือสำหรับการแก้ไขปัญหา
### <a name="logs-relevant-for-scheduled-refresh-of-power-bi-reports"></a>บันทึกที่เกี่ยวข้องกับการรีเฟรชตามกำหนดเวลาของรายงาน Power BI
แฟ้มบันทึกที่เก็บข้อมูลเกี่ยวกับการรีเฟรชตามกำหนดเวลาได้แก่ ล็อกของ RSPowerBI_ บันทึกดังกล่าวอยู่ในโฟลเดอร์ LogFiles ของตำแหน่งการติดตั้งเซิร์ฟเวอร์รายงานของคุณ 

```
C:\Program Files\Microsoft Power BI Report Server\PBIRS\LogFiles\RSPowerBI_*.log
```

**เงื่อนไขข้อผิดพลาด**

```
2017-10-20 02:00:09.5188|ERROR|744|Error Processing Data Model Refresh: SessionId: e960c25e-ddd4-4763-aa78-0e5dceb53472, Status: Error Model can not be refreshed because not all the data sources are embedded, Exception Microsoft.PowerBI.ReportServer.AsServer.InvalidDataSourceException: Model can not be refreshed because not all the data sources are embedde
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.CanModelRefresh(IEnumerable`1 dataSources)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
```

***การรีเฟรชที่สำเร็จ***

```
2017-10-25 15:23:41.9370|INFO|6|Handling event with data: TimeEntered: 10/25/2017 8:23:41 PM, Type: Event, SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, EventType: DataModelRefresh
2017-10-25 15:23:41.9370|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Data Refresh.
2017-10-25 15:23:41.9370|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Retrieving PBIX AsDatabaseInfo.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Verifying all the data sources are embedded.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Verifying connection strings are valid.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Streaming model to Analysis Server.
2017-10-25 15:23:42.7603|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Refreshing the model.
2017-10-25 15:23:51.5258|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Removing credentials from the model.
2017-10-25 15:23:51.6508|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Saving model to the catalog.
```

**ข้อมูลประจำตัวไม่ถูกต้อง**

```
2017-10-20 08:22:01.5595|INFO|302|Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Starting Refreshing the model.
2017-10-20 08:22:02.3758|ERROR|302|Error Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Error Failed to refresh the model, Exception Microsoft.AnalysisServices.OperationException: Failed to save modifications to the server. Error returned: 'The credentials provided for the SQL source are invalid. (Source at rosecatalog;reportserver.). The exception was raised by the IDbCommand interface.
'.
   at Microsoft.AnalysisServices.Tabular.Model.SaveChanges(SaveOptions saveOptions)
   at Microsoft.PowerBI.ReportServer.AsServer.TOMWrapper.RefreshModel(Database database)
   at Microsoft.PowerBI.ReportServer.AsServer.AnalysisServicesServer.RefreshDatabase(String databaseName, IEnumerable`1 dataSources)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.RefreshDatabase(AsDatabaseInfo asDatabaseInfo)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
2017-10-20 08:22:02.4588|ERROR|302|Error Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Error Failed Data Refresh, Exception Microsoft.AnalysisServices.OperationException: Failed to save modifications to the server. Error returned: 'The credentials provided for the SQL source are invalid. (Source at rosecatalog;reportserver.). The exception was raised by the IDbCommand interface.
'.
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.ExecuteActionWithLogging(Action methodToExecute, String description, String localizedDescription, String messageInFailure, RefreshInfo refreshInfo, DataAccessors dataAccessors, ReportEventType operation, Int64 size, Boolean isDataRetrieval, Boolean showInExecutionLog)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.RefreshData(RefreshInfo refreshInfo)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
```

#### <a name="enabling-verbose-logging"></a>เปิดใช้งานการบันทึกแบบละเอียด
เปิดใช้งานการบันทึกแบบละเอียด ในเซิร์ฟเวอร์รายงาน Power BI จะเหมือนกับใน SQL Server Reporting Services

1. เปิด `<install directory>\PBIRS\ReportServer\bin\ReportingServicesService.exe.config`
2. ภายใต้ `<system.diagnostics>` เปลี่ยน **DefaultTraceSwitch** เป็น **4**
3. ภายใต้ `<RStrace>` เปลี่ยน **Components** เป็น **all:4** 

### <a name="executionlog"></a>บันทึกการดำเนินการ
เมื่อใดก็ตามที่มีการแสดงผลรายงาน Power BI หรือดำเนินการกับแผนการรีเฟรชตามกำหนดเวลา รายการใหม่จะถูกเพิ่มลงในบันทึกการดำเนินการในฐานข้อมูล รายการดังกล่าวจะปรากฏอยู่ในมุมมอง **ExecutionLog3** ภายในฐานข้อมูลแค็ตตาล็อกของเซิร์ฟเวอร์รายงาน

รายการบันทึกการดำเนินการสำหรับรายงาน Power BI แตกต่างจากรายการสำหรับรายงานชนิดอื่น

* คอลัมน์ TimeRendering จะมีค่าเป็น 0 เสมอ การแสดงผลของรายงาน Power BI เกิดขึ้นในเบราว์เซอร์ ไม่ได้อยู่ในเซิร์ฟเวอร์
* มีค่า Request Types ได้ 2 แบบและการดำเนินการที่เกิดขึ้นต่อมา:
  * **แบบโต้ตอบ**: เมื่อใดก็ตามที่มีการดูรายงาน
    * **ASModelStream**: เมื่อรูปแบบข้อมูลถูกสตรีมไปยัง Analysis Services จากแค็ตตาล็อก
    * **ConceptualSchema**: เมื่อผู้ใช้คลิกดูรายงาน
    * **QueryData**: เมื่อใดก็ตามที่ข้อมูลมีการร้องขอจากไคลเอ็นต์
  * **รีเฟรชแค**: เมื่อใดก็ตามที่มีการดำเนินการตามแผนการรีเฟรชตามกำหนดเวลา
    * **ASModelStream**: เมื่อใดก็ตามที่รูปแบบข้อมูลถูกสตรีมไปยัง Analysis Services จากแค็ตตาล็อก
    * **DataRefresh**: เมื่อใดก็ตามที่มีการรีเฟรชข้อมูลจากแหล่งข้อมูลหนึ่งหรือหลายแหล่ง
    * **SaveToCatalog**: เมื่อใดก็ตามตัวที่รูปแบบข้อมูลถูกบันทึกกลับไปยังแค็ตตาล็อก

## <a name="analysis-services"></a>Analysis Services
อาจมีบางครั้งที่คุณต้องการปรับแก้ Analysis Services เพื่อวินิจฉัยปัญหา หรือปรับค่าขีดจำกัดหน่วยความจำ

> [!IMPORTANT]
> ค่าเหล่านี้จะถูกตั้งค่าใหม่ทุกครั้งที่คุณอัปเกรดเซิร์ฟเวอร์รายงาน ตรวจสอบให้แน่ใจว่ามีการเก็บสำเนาของการเปลี่ยนแปลงของคุณ และนำกลับมาใช้ถ้าจำเป็น
> 
> 

### <a name="install-location"></a>ตำแหน่งที่ติดตั้ง
ค่าเริ่มต้นของตำแหน่งที่ติดตั้งเซิร์ฟเวอร์รายงาน Power BI และ Analysis Services มีดังนี้

`C:\Program Files\Microsoft Power BI Report Server\PBIRS\ASEngine`

### <a name="configuring-analysis-services-settings-msmdsrvini"></a>การกำหนดค่า Analysis Services (msmdsrv.ini)
ในไดเรกทอรี `<install directory>\PBIRS\ASEngine` คุณจะพบแฟ้ม *msmdsrv.ini* ซึ่งคุณสามารถใช้ควบคุมการตั้งค่าต่าง ฯ ของ Analysis Services เมื่อคุณเปิดไฟล์นี้ คุณจะเห็นได้ทันทีว่า แฟ้มนี้ไม่มีการตั้งค่าทุกค่าที่คุณคาดว่าจะมีในแฟ้ม msmdsrv.ini 

เนื่องจากว่า กระบวนการ Analysis Services จริงที่เรียกใช้โดยเซิร์ฟเวอร์รายงาน Power BI จะเรียกใช้ภายใน `<install directory>\PBIRS\ASEngine\workspaces` ในโฟลเดอร์นั้น คุณจะเห็นแฟ้ม *msmdsrv.ini* แบบเต็มที่คุณคุ้นเคย สิ่งสำคัญคือ ต้องไม่ปรับเปลี่ยนแฟ้มภายในโฟลเดอร์พื้นที่ทำงาน เพราะมันจะถูกเขียนทับทุกครั้งที่เปิดใช้ Analysis Services ถ้าคุณต้องการควบคุมการตั้งค่า โปรดปรับเปลี่ยน msmdsrv.ini ในไดเรกทอรี `<install directory>\PBIRS\ASEngine`

การตั้งค่าต่อไปนี้จะถูกตั้งค่าใหม่ ทุกครั้งที่เปิดใช้ Analysis Services การเปลี่ยนแปลงใด ๆ ที่คุณทำกับค่าเหล่านี้จะไม่มีผล

* ConfigurationSettings\PrivateProcess
* ConfigurationSettings\DataDir
* ConfigurationSettings\LogDir
* ConfigurationSettings\TempDir
* ConfigurationSettings\BackupDir
* ConfigurationSettings\AllowedBrowsingFolders
* ConfigurationSettings\CrashReportsFolder
* ConfigurationSettings\ExtensionDir
* ConfigurationSettings\Port
* ConfigurationSettings\DeploymentMode
* ConfigurationSettings\ServerLocation
* ConfigurationSettings\TMCompatabilitySKU
* ConfigurationSettings\FlightRecorder\TraceDefinitionFile

### <a name="profiling-the-local-analysis-services-process"></a>การทำโพรไฟล์กระบวนการ Analysis Services ภายในเครื่อง
การติดตาม SQL Profiler สามารถเรียกใช้ได้ในเครื่องของ Analysis Services สำหรับการวินิจฉัยปัญหา เมื่อต้องการเชื่อมต่อกับอินสแตนซ์ Analysis Services ภายในเครื่อง ให้ทำสิ่งต่อไปนี้

การติดตาม SQL Server Profiler จะรวมอยู่ในการ[ดาวน์โหลด SQL Server Management Studio (SSMS)](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms) เรียบร้อยแล้ว

1. เริ่มต้น **SQL Server Profiler** ด้วยสิทธิ์ผู้ดูแล
2. เลือกปุ่ม**การติดตามใหม่**
3. ในกล่องโต้ตอบ**เชื่อมต่อกับเซิร์ฟเวอร์** เลือก**Analysis Services** และใส่ **localhost:5132** สำหรับชื่อเซิร์ฟเวอร์
4. ในกล่องโต้ตอบ**คุณสมบัติการติดตาม** เลือกเหตุการณ์คุณต้องการบันทึก และเลือก**เรียกใช้**

## <a name="lock-pages-in-memory-windows-privilege"></a>สิทธิ์ Windows ในการล็อกหน้าในหน่วยความจำ
ถ้าคุณพบว่า คุณจะไม่สามารถแสดงรายงาน Power BI การกำหนดสิทธิ์**ล็อกหน้าในหน่วยความจำ** ให้กับบัญชีบริการที่เรียกใช้งาน เซิร์ฟเวอร์รายงาน Power BI อาจช่วยได้ สำหรับข้อมูลเพิ่มเติมเกี่ยวกับวิธีการกำหนดค่า**ล็อกหน้าในหน่วยความจำ** ดู[สิทธิ์การใช้งาน Windows ที่กำหนดให้กับบัญชีบริการ Analysis Services](https://docs.microsoft.com/sql/analysis-services/instances/configure-service-accounts-analysis-services#bkmk_winpriv)

คำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)


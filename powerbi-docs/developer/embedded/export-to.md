---
title: ส่งออกรายงาน API Power BI
description: เรียนรู้วิธีการส่งออกรายงาน Power BI เป็น PDF
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 03/24/2020
ms.openlocfilehash: 472797cf30d6b88a59af5b3846e9b710bf4607c7
ms.sourcegitcommit: 81407c9ccadfa84837e07861876dff65d21667c7
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 04/13/2020
ms.locfileid: "81267514"
---
# <a name="export-power-bi-report-to-file-preview"></a>ส่งออกรายงาน Power BI ไปยังไฟล์ (ตัวอย่าง)

`exportToFile`API เปิดใช้งานการส่งออกรายงาน Power BI โดยใช้การเรียกใช้ REST รูปแบบไฟล์ต่อไปนี้ได้รับการรองรับ:
* **.pptx** (PowerPoint)
* **.pdf**
* **.png**
    * ขณะที่ส่งออกในรูปแบบ .png รายงานที่มีหลายหน้าจะถูกบีบอัดเป็นไฟล์ .zip
    * แต่ละไฟล์ใน .zip จะแสดงหน้ารายงาน
    * ชื่อหน้าจะเหมือนกับค่าที่ส่งกลับของ API [รับหน้า](https://docs.microsoft.com/rest/api/power-bi/reports/getpages)หรือ[รับหน้าในกลุ่ม](https://docs.microsoft.com/rest/api/power-bi/reports/getpagesingroup)

## <a name="usage-examples"></a>ตัวอย่างการใช้งาน

คุณสามารถใช้ฟีเจอร์การส่งออกได้หลายวิธี นี่เป็นตัวอย่างสองตัวอย่าง:

* **ส่งไปยังปุ่มพิมพ์** - ในแอปพลิเคชันของคุณ ให้สร้างปุ่มที่เมื่อคลิกที่จะทริกเกอร์งานการส่งออก งานสามารถส่งออกรายงานที่เป็น .pdf หรือ .pptx และเมื่อเสร็จสมบูรณ์ ผู้ใช้จะสามารถรับไฟล์เป็นการดาวน์โหลดได้ คุณสามารถใช้บุ๊กมาร์กส่งออกรายงานในสถานะที่ระบุ รวมถึงตัวกรองที่กำหนดค่า ตัวแบ่งส่วนข้อมูล และการตั้งค่าเพิ่มเติมได้ ในฐานะที่เป็น API แบบอะซิงโครนัส อาจใช้เวลาสักครู่ก่อนที่ไฟล์จะพร้อมใช้งาน

* **ไฟล์แนบอีเมล** - ส่งอีเมลโดยอัตโนมัติในช่วงเวลาที่ตั้งค่า ด้วยรายงาน .pdf ที่แนบมา สถานการณ์นี้อาจเป็นประโยชน์ถ้าคุณต้องการส่งรายงานรายสัปดาห์ไปยังฝ่ายบริหารโดยอัตโนมัติ

## <a name="using-the-api"></a>การใช้ API

ก่อนที่จะใช้ API ให้ยืนยันว่ามีการเปิดใช้งาน[การตั้งค่าผู้เช่าผู้ดูแลระบบ](../../service-admin-portal.md#tenant-settings)ดังต่อไปนี้:
* **ส่งออกรายงานในรูปแบบงานนำเสนอ PowerPoint หรือเอกสาร PDF** - เปิดใช้งานโดยค่าเริ่มต้น
* **ส่งออกรายงานเป็นไฟล์รูปภาพ** - จำเป็นสำหรับ *.png* เท่านั้นและปิดใช้งานตามค่าเริ่มต้น

API เป็นแบบอะซิงโครนัส เมื่อมีการเรียกใช้ API [exportToFile](https://docs.microsoft.com/rest/api/power-bi/reports/exporttofile) จะทริกเกอร์งานการส่งออก หลังจากทริกเกอร์งานส่งออก ให้ใช้[การโพลล์](https://docs.microsoft.com/rest/api/power-bi/reports/getexporttofilestatus)เพื่อติดตามงานจนกว่าจะเสร็จสมบูรณ์

ในระหว่างการโพลล์ API จะส่งกลับตัวเลขที่แสดงถึงจำนวนการทำงานที่เสร็จสมบูรณ์ งานในแต่ละงานส่งออกจะถูกคำนวณตามจำนวนหน้าของรายงาน จะมีหน้าทั้งหมดเท่าๆ กัน ตัวอย่างเช่น ถ้าคุณกำลังส่งออกรายงานที่มี 10 หน้าและการโพลล์ส่งกลับ 70 หน้า นั่นหมายความว่า API ได้รับการประมวลผล 7 จาก 10 หน้าในงานส่งออก

เมื่อการส่งออกเสร็จสิ้น การเรียกใช้ API การโพลล์จะส่งคืน [URL ของ Power BI](https://docs.microsoft.com/rest/api/power-bi/reports/getfileofexporttofile) สำหรับรับไฟล์ URL จะพร้อมใช้งานเป็นเวลา 24 ชั่วโมง

## <a name="supported-features"></a>ฟีเจอร์ที่ได้รับการรองรับ

### <a name="selecting-which-pages-to-print"></a>การเลือกหน้าเพื่อพิมพ์

ระบุหน้าที่คุณต้องการพิมพ์ตามค่าส่งคืนการ[รับหน้า](https://docs.microsoft.com/rest/api/power-bi/reports/getpages)หรือ[รับหน้าในกลุ่ม](https://docs.microsoft.com/rest/api/power-bi/reports/getpagesingroup) คุณยังสามารถระบุลำดับของหน้าที่คุณกำลังส่งออกได้

### <a name="bookmarks"></a>บุ๊กมาร์ก

 คุณสามารถใช้ API `exportToFile` เพื่อส่งออกรายงานในสถานะที่ระบุทางโปรแกรมได้หลังจากใช้ตัวกรอง การดำเนินการนี้ทำได้โดยใช้ความสามารถของ[บุ๊กมาร์ก](../../consumer/end-user-bookmarks.md) หากต้องการส่งออกรายงานโดยใช้บุ๊กมาร์กให้ใช้ [API บุ๊กมาร์ก JavaScript](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Bookmarks)

 ตัวอย่างเช่น คุณสามารถใช้`capturedBookmark.state`วิธีการของบุ๊กมาร์กเพื่อจับภาพการเปลี่ยนแปลงผู้ใช้ที่ระบุที่ทำกับรายงาน จากนั้นส่งออกในสถานะปัจจุบัน

ไม่รองรับ[บุ๊กมาร์กส่วนบุคคล](../../consumer/end-user-bookmarks.md#personal-bookmarks)และ[ตัวกรองแบบถาวร](https://powerbi.microsoft.com/blog/announcing-persistent-filters-in-the-service/)

### <a name="authentication"></a>การรับรองความถูกต้อง

คุณสามารถรับรองความถูกต้องได้โดยใช้ผู้ใช้ (หรือผู้ใช้หลัก) หรือ [หลักบริการ](embed-service-principal.md)

### <a name="row-level-security-rls"></a>การรักษาความปลอดภัยระดับแถว (RLS)

ด้วย[การรักษาความปลอดภัยระดับแถว (RLS)](embedded-row-level-security.md) คุณสามารถส่งออกรายงานที่แสดงข้อมูลที่สามารถมองเห็นได้เฉพาะผู้ใช้บางรายเท่านั้น ตัวอย่างเช่น ถ้าคุณกำลังส่งออกรายงานยอดขายที่กำหนดไว้กับบทบาทภูมิภาค คุณสามารถกรองรายงานเพื่อให้แสดงเฉพาะภูมิภาคที่ระบุเท่านั้นได้

หากต้องการส่งออกโดยใช้ RLS คุณต้องมีสิทธิ์ต่อไปนี้:
* สิทธิ์การเขียนและแชร์ต่อสำหรับชุดข้อมูลที่มีการเชื่อมต่อกับรายงาน
* ถ้ารายงานอยู่ในพื้นที่ทำงาน v1 คุณจะต้องเป็นผู้ดูแลระบบพื้นที่ทำงาน
* ถ้ารายงานอยู่ในพื้นที่ทำงาน v2 คุณจะต้องเป็นผู้ดูแลระบบพื้นที่ทำงาน

### <a name="data-protection"></a>การป้องกันข้อมูล

รูปแบบ .pdf และ .pptx รองรับ[ป้ายชื่อระดับความลับ](../../admin/service-security-data-protection-overview.md#sensitivity-labels-in-power-bi) หากคุณส่งออกรายงานที่มีป้ายชื่อระดับความลับในรูปแบบ .pdf หรือ .pptx ไฟล์ที่ส่งออกจะแสดงรายงานที่มีป้ายชื่อระดับความลับ

รายงานที่มีป้ายชื่อระดับความลับ จะไม่สามารถส่งออกในรูปแบบ .pdf หรือ .pptx โดยใช้ [หลักบริการ](embed-service-principal.md) ได้

### <a name="localization"></a>การแปลเป็นภาษาท้องถิ่น

เมื่อใช้ `exportToFile` API คุณสามารถผ่านท้องถิ่นที่คุณต้องการได้ การตั้งค่าการแปลมีผลต่อวิธีการแสดงรายงาน ตัวอย่างเช่น โดยการเปลี่ยนการจัดรูปแบบโดยอ้างอิงจากเครื่องที่เลือก

## <a name="concurrent-requests"></a>คำขอที่เกิดขึ้นพร้อมกัน

`exportToFile` รองรับคำของานการส่งออกที่เกิดขึ้นพร้อมกัน ตารางด้านล่างแสดงจำนวนของงานที่คุณสามารถเรียกใช้ในเวลาเดียวกันได้โดยขึ้นอยู่กับ SKU รายงานของคุณ คำขอที่เกิดขึ้นพร้อมกันจะอ้างอิงไปยังหน้ารายงาน ตัวอย่างเช่น 20 หน้าในคำขอการส่งออกในหนึ่ง A6 SKU จะได้รับการประมวลผลพร้อมๆ กัน การดำเนินการนี้จะใช้เวลาพอๆ กันกับการส่งคำขอการส่งออก 20 ครั้งต่อหนึ่งหน้า

งานที่เกินจำนวนคำขอที่เกิดขึ้นพร้อมกันจะไม่ยุติลง ตัวอย่างเช่น ถ้าคุณส่งออกสามหน้าใน A1 SKU งานแรกจะเรียกใช้ และสองงานหลังจะต้องสองรอบการดำเนินการถัดไป

|Azure SKU  |Office SKU  |หน้ารายงานที่เกิดขึ้นพร้อมกันสูงสุด  |
|-----------|------------|-----------|
|A1         |EM1         |1          |
|A2         |EM2         |2          |
|A3         |EM3         |3          |
|A4         |P1          |6          |
|A5         |P2          |12         |
|A6         |P3          |24         |

## <a name="limitations"></a>ข้อจำกัด

* รายงานที่คุณกำลังส่งออกต้องอยู่บนความจุพรีเมียมหรือแบบฝัง
* ชุดข้อมูลที่คุณกำลังส่งออกต้องอยู่บนความจุ
* สำหรับการแสดงตัวอย่างสาธารณะ จำนวนหน้ารายงาน Power BI ที่ส่งออกต่อชั่วโมงจะถูกจำกัดไว้ที่ 50 หน้าต่อความจุ
* รายงานที่ส่งออกต้องมีขนาดไฟล์ไม่เกิน 250 MB
* เมื่อส่งออกในรูปแบบ .png ป้ายชื่อความระดับความลับจะไม่ได้รับการสนับสนุน
* รายงานที่มีป้ายชื่อระดับความลับ จะไม่สามารถส่งออกในรูปแบบ .pdf หรือ .pptx โดยใช้ [หลักบริการ](embed-service-principal.md) ได้
* จำนวนหน้าซึ่งสามารถรวมอยู่ในรายงานที่ส่งออกได้คือ 30 หากรายงานมีหลายหน้า API จะส่งคืนข้อผิดพลาดและงานส่งออกจะถูกยกเลิก
* ไม่รองรับ[บุ๊กมาร์กส่วนบุคคล](../../consumer/end-user-bookmarks.md#personal-bookmarks)และ[ตัวกรองแบบถาวร](https://powerbi.microsoft.com/blog/announcing-persistent-filters-in-the-service/)
* การแสดงผลด้วยภาพของ Power BI ที่แสดงในรายการด้านล่างไม่ได้รับการรองรับ เมื่อรายงานที่มีการแสดงผลด้วยภาพเหล่านี้ถูกส่งออก ส่วนของรายงานที่ประกอบด้วยการแสดงผลด้วยภาพดังกล่าวจะไม่แสดง และจะแสดงสัญลักษณ์ข้อผิดพลาด
    * การแสดงผลด้วยภาพของ Power BI ที่ไม่ผ่านการจัดการ
    * วิชวล R
    * PowerApps
    * การแสดงผลด้วยภาพของ Python
    * Visio

## <a name="code-examples"></a>ตัวอย่างรหัส

เมื่อคุณสร้างงานส่งออก มีสามขั้นตอนเพื่อการปฏิบัติตามดังนี้:

1. ส่งคำขอการส่งออก
2. การโพลล์
3. การรับไฟล์

หัวข้อนี้มีตัวอย่างสำหรับแต่ละขั้นตอน

### <a name="step-1---sending-an-export-request"></a>ขั้นตอนที่ 1 - ส่งคำขอส่งออก

ขั้นตอนแรกคือการส่งคำขอส่งออก ในตัวอย่างนี้ คำขอส่งออกจะถูกส่งไปยังหน้าที่ระบุ

```csharp
/////// Export sample ///////
private async Task<string> PostExportRequest(
    Guid reportId,
    Guid groupId,
    FileFormat format,
    IList<string> pageNames = null /* Get the page names from the GetPages API */)
{
    var powerBIReportExportConfiguration = new PowerBIReportExportConfiguration
    {
        Settings = new ExportReportSettings
        {
            Locale = "en-us",
        },
        // Note that page names differ from the page display names.
        // To get the page names use the GetPages API.
        Pages = pageNames?.Select(pn => new ExportReportPage(Name = pn)).ToList(),
    };
    var exportRequest = new ExportReportRequest
    {
        Format = format,
        PowerBIReportConfiguration = powerBIReportExportConfiguration,
    };
    var export = await Client.Reports.ExportToFileInGroupAsync(groupId, reportId, exportRequest);
    // Save the export ID, you'll need it for polling and getting the exported file
    return export.Id;
}
```

### <a name="step-2---polling"></a>ขั้นตอนที่ 2 - การโพลล์

หลังจากที่คุณส่งคำขอส่งออก ให้ใช้การโพลล์เพื่อระบุว่าไฟล์ส่งออกที่คุณรออยู่พร้อมหรือไม่

```csharp
private async Task<Export> PollExportRequest(
    Guid reportId,
    Guid groupId,
    string exportId /* Get from the ExportToAsync response */,
    int timeOutInMinutes,
    CancellationToken token)
{
    Export exportStatus = null;
    DateTime startTime = DateTime.UtcNow;
    const int c_secToMillisec = 1000;
    do
    {
        if (DateTime.UtcNow.Subtract(startTime).TotalMinutes > timeOutInMinutes || token.IsCancellationRequested)
        {
            // Error handling for timeout and cancellations 
            return null;
        }
        var httpMessage = await Client.Reports.GetExportToFileStatusInGroupWithHttpMessagesAsync(groupId, reportId, exportId);
        exportStatus = httpMessage.Body;
        // You can track the export progress using the PercentComplete that's part of the response
        SomeTextBox.Text = string.Format("{0} (Percent Complete : {1}%)", exportStatus.Status.ToString(), exportStatus.PercentComplete);
        if (exportStatus.Status == ExportState.Running || exportStatus.Status == ExportState.NotStarted)
        {
            // The recommended waiting time between polling requests can be found in the RetryAfter header
            // Note that this header is only populated when the status is either Running or NotStarted
            var retryAfter = httpMessage.Response.Headers.RetryAfter;
            var retryAfterInSec = retryAfter.Delta.Value.Seconds;
            await Task.Delay(retryAfterInSec * c_secToMillisec);
        }
    }
    // While not in a terminal state, keep polling
    while (exportStatus.Status != ExportState.Succeeded && exportStatus.Status != ExportState.Failed);
    return exportStatus;
}
```

### <a name="step-3---getting-the-file"></a>ขั้นตอนที่ 3 - การรับไฟล์

เมื่อการโพลล์ส่งคืน URL ให้ใช้ตัวอย่างนี้เพื่อรับไฟล์ที่ได้รับ

```csharp
private async Task<ExportedFile> GetExportedFile(
    Guid reportId,
    Guid groupId,
    Export export /* Get from the GetExportStatusAsync response */)
{
    if (export.Status == ExportState.Succeeded)
    {
        var fileStream = await Client.Reports.GetFileOfExportToFileAsync(groupId, reportId, export.Id);
        return new ExportedFile
        {
            FileStream = fileStream,
            FileSuffix = export.ResourceFileExtension,
        };
    }
    return null;
}
public class ExportedFile
{
    public Stream FileStream;
    public string FileSuffix;
}
```

### <a name="end-to-end-example"></a>ตัวอย่างแบบต้นจนจบ

นี่คือตัวอย่างแบบต้นจนจบสำหรับการส่งออกรายงาน ตัวอย่างนี้รวมไปถึงขั้นตอนต่อไปนี้:
1. [ส่งคำขอการส่งออก](#step-1---sending-an-export-request)
2. [การโพลล์](#step-2---polling)
3. [การรับไฟล์](#step-3---getting-the-file)

```csharp
private async Task<ExportedFile> ExportPowerBIReport(
    Guid reportId,
    Guid groupId,
    FileFormat format,
    int pollingtimeOutInMinutes,
    CancellationToken token,
    IList<string> pageNames = null /* Get the page names from the GetPages API */)
{
    try
    {
        var exportId = await PostExportRequest(reportId, groupId, format, pageNames);
        var export = await PollExportRequest(reportId, groupId, exportId, pollingtimeOutInMinutes, token);
        if (export == null || export.Status != ExportState.Succeeded)
        {
            // Error, failure in exporting the report
            return null;
        }
        return await GetExportedFile(reportId, groupId, export);
    }
    catch
    {
        // Error handling
        throw;
    }
}
```

## <a name="next-steps"></a>ขั้นตอนถัดไป

ตรวจทานวิธีการฝังเนื้อหาสำหรับลูกค้าและองค์กรของคุณ:

> [!div class="nextstepaction"]
>[ส่งออกรายงานที่มีการแบ่งหน้าไปยังไฟล์](export-paginated-report.md)

> [!div class="nextstepaction"]
>[ฝังสำหรับลูกค้าของคุณ](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[ฝังตัวสำหรับองค์กรของคุณ](embed-sample-for-your-organization.md)

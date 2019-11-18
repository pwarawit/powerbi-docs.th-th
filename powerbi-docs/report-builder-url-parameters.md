---
title: พารามิเตอร์ URL ในรายงานที่มีการแบ่งหน้า - ตัวสร้างรายงาน Power BI
description: หัวข้อนี้อธิบายการใช้งานทั่วไปสำหรับพารามิเตอร์รายงานของตัวสร้างรายงานที่มีการแบ่งหน้าใน Power BI คุณสมบัติต่างๆ ที่คุณสามารถตั้งค่าและเพิ่มเติมอีกมาก
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.reviewer: cfinlan
ms.custom: ''
ms.date: 09/10/2019
ms.openlocfilehash: e39864081ce4dd1ad415224454b75404e882e9ce
ms.sourcegitcommit: 01de0b01f66f28ca45b8d309d7864f261d6c9a85
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/16/2019
ms.locfileid: "74128304"
---
# <a name="url-parameters-in-paginated-reports-in-power-bi"></a>พารามิเตอร์ URL ในรายงานที่มีการแบ่งหน้าใน Power BI

คุณสามารถส่งคำสั่งไปยังรายงานที่มีการแบ่งหน้าใน Power BI ได้โดยการเพิ่มพารามิเตอร์ลงใน URL ตัวอย่างเช่น คุณอาจมีการดูรายงานโดยใช้ชุดค่าพารามิเตอร์รายงานที่ระบุ คุณจะย่อส่วนข้อมูลนี้ใน URL โดยใช้พารามิเตอร์การเข้าถึง URL ที่กำหนดไว้ล่วงหน้า คุณสามารถปรับแต่งวิธีการที่ Power BI ประมวลผลรายงานเพิ่มเติมได้ โดยการฝังพารามิเตอร์สำหรับรูปแบบการแสดงผล หรือสำหรับลักษณะที่แสดงกของแถบเครื่องมือรายงาน จากนั้นคุณสามารถวาง URL นี้ลงในอีเมลหรือหน้าเว็บโดยตร งเพื่อให้ผู้อื่นสามารถดูรายงานของคุณในลักษณะเดียวกันกับในเบราว์เซอร์ 

ต่อไปนี้คือการดำเนินการที่คุณสามารถดำเนินการผ่านพารามิเตอร์การเข้าถึง URL: 

- ส่งพารามิเตอร์รายงานไปยังรายงาน 
- เริ่มต้นการส่งออกเนื้อหารายงานในรูปแบบไฟล์ที่ได้รับการสนับสนุน 
- ซ่อนหรือดูบานหน้าต่างพารามิเตอร์ 
- ระบุการตั้งค่า DeviceInfo 

สำหรับรายการทั้งหมดของคำสั่งและการตั้งค่าที่พร้อมใช้งานผ่านการเข้าถึง URL โปรดดูที่  [การอ้างอิงพารามิเตอร์การเข้าถึง URL](#url-access-parameter-reference) ภายหลังในบทความนี้ 

## <a name="url-access-concepts"></a>แนวคิดการเข้าถึง URL 

คำขอ URL ไปยัง Power BI ประกอบด้วยพารามิเตอร์ที่ได้รับการประมวลผลโดยบริการ วิธีที่บริการจัดการกับคำขอ URL ขึ้นอยู่กับพารามิเตอร์ คำนำหน้าพารามิเตอร์ และประเภทของรายการที่รวมอยู่ใน URL ฟังก์ชัน URL ของรายงานที่มีการแบ่งหน้าเข้ากันได้กับเบราว์เซอร์และแอปพลิเคชันส่วนใหญ่ที่รองรับการจัดการ URL มาตรฐาน 

## <a name="url-access-syntax"></a>ไวยากรณ์การเข้าถึง URL 

คำขอ URL อาจมีหลายพารามิเตอร์ที่แสดงอยู่ในลำดับใดก็ได้ พารามิเตอร์คิวรีจะต้องแยกด้วยเครื่องหมาย (&) คู่ชื่อและค่าจะต้องคั่นด้วยเครื่องหมายเท่ากับ (=) ตัวอย่างเช่น:

```
powerbiserviceurl?rp:parametervalueh&rdl:parameter=value  
```

## <a name="syntax-description"></a>คำอธิบายไวยากรณ์ 

### <a name="powerbiserviceurl"></a>powerbiserviceurl 

URL บริการบนเว็บของผู้เช่า Power BI ตัวอย่างเช่น: 

**&** ใช้เพื่อแยกคู่ชื่อและค่าของพารามิเตอร์การเข้าถึง URL

**คำนำหน้า** คำนำหน้าสำหรับพารามิเตอร์ URL (ตัวอย่างเช่น rp: หรือ rdl) ที่ระบุการดำเนินการในบริการของ Power BI 

> [!NOTE]
> พารามิเตอร์รายงานจำเป็นต้องใช้คำนำหน้าพารามิเตอร์และตรงตามตัวพิมพ์ใหญ่-เล็ก 

**พารามิเตอร์** ชื่อพารามิเตอร์ 

### <a name="value"></a>ค่า 

ข้อความ URL ที่สอดคล้องกับค่าของพารามิเตอร์ที่ใช้ 

สำหรับตัวอย่างของการส่งพารามิเตอร์รายงานบน URL ให้ดู  [ส่งพารามิเตอร์รายงานใน URL](report-builder-url-pass-parameters.md)

## <a name="url-access-parameter-reference"></a>การอ้างอิงพารามิเตอร์การเข้าถึง URL

คุณสามารถใช้พารามิเตอร์ต่อไปนี้เป็นส่วนหนึ่งของ URL เพื่อกำหนดค่าลักษณะที่แสดงของรายงานที่มีการแบ่งหน้าใน Power BI พารามิเตอร์ทั่วไปส่วนใหญ่จะแสดงอยู่ในส่วนนี้ พารามิเตอร์ต้องตรงตามตัวพิมพ์ใหญ่-เล็กและเริ่มต้นด้วยคำนำหน้าพารามิเตอร์ `rdl:` ถ้าเกี่ยวข้องกับรูปแบบเอาต์พุต  

### <a name="report-commands-rdl"></a>คำสั่งรายงาน (`rdl:`) 

**รูปแบบการส่งออก** ระบุรูปแบบที่จะแสดงและส่งออกรายงาน ค่าที่ใช้ได้คือ:
 
- PPTX (PowerPoint)
- MHTML 
- รูปภาพ 
- EXCELOPENXML (EXCEL) 
- WORDOPENXML (WORD) 
- CSV 
- PDF 
- XML 

**Device Info (ข้อมูลอุปกรณ์)** คุณอาจระบุพารามิเตอร์ผลลัพธ์เพิ่มเติมที่เฉพาะเจาะจงสำหรับรูปแบบการส่งออกต่อไปนี้ได้ 

PDF:

- rdl:AccessiblePDF=true/false
- rdl:Columns=integer
- rdl:ColumnSpacing=decimal(in)
- rdl:DpiX=integer
- rdl:DpiY=integer
- rdl:EndPage=integer
- rdl:HumanReadablePDF=true/false
- rdl:MarginBottom=decimal(in)
- rdl:MarginLeft=decimal(in)
- rdl:MarginRight=decimal(in)
- rdl:MarginTop=decimal(in)
- rdl:PageHeight=decimal(in)
- rdl:PageWidth=decimal(in)
    - rdl:StartPage=integer
    
CSV:

- rdl:Encoding=string
- rdl:ExcelMode=true/false
- rdl:FieldDelimiter=string
- rdl:FileExtension=string
- rdl:NoHeader=true/false
- rdl:Qualifier=string
- rdl:RecordDelimiter=string
- rdl:SuppressLineBreaks=true/false
    - rdl:UseFormattedValues=true/false
    
WORDOPENXML (WORD):

- rdl:AutoFit=string -> True/False/Never/Default
- rdl:ExpandToggles=true/false
- rdl:FixedPageWidth=true/false
- rdl:OmitHyperlinks=true/false
- rdl:OmitDrillthroughs=true/false

EXCELOPENXML (EXCEL):

- rdl:OmitDocumentMap=true/false
- rdl:OmitFormulas=true/false
    - rdl:SimplePageHeaders=true/false
    
PPTX (PowerPoint):
 
- rdl:Columns=integer
- rdl:ColumnSpacing=decimal(in)
- rdl:DpiX=integer
- rdl:DpiY=integer
- rdl:EndPage=integer
- rdl:MarginBottom=decimal(in)
- rdl:MarginLeft=decimal(in)
- rdl:MarginRight=decimal(in)
- rdl:MarginTop=decimal(in)
- rdl:PageHeight=decimal(in)
- rdl:PageWidth=decimal(in)
- rdl:StartPage=integer
    - rdl:UseReportPageSize=true/false

XML:

- rdl:XSLT=string
- rdl:MIMEType=string
- rdl:UseFormattedValues=true/false
- rdl:Indented=true/false
- rdl:OmitNamespace=true/false
- rdl:OmitSchema=true/false
- rdl:Encoding=string
- rdl:FileExtension=string
- rdl:Schema=true/false

## <a name="next-steps"></a>ขั้นตอนถัดไป

- [ส่งพารามิเตอร์รายงานใน URL สำหรับรายงานที่มีการแบ่งหน้าใน Power BI](report-builder-url-pass-parameters.md)
- [รายงานแบบแบ่งหน้าใน Power BI Premium คืออะไร](paginated-reports-report-builder-power-bi.md)

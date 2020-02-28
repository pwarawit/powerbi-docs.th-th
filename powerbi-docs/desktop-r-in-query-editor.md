---
title: ใช้ R ในตัวแก้ไข Power Query
description: ใช้ R ในตัวแก้ไข Power Query ของ Power BI Desktop สำหรับการวิเคราะห์ขั้นสูง
author: davidiseminger
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/28/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: a157b674cd96c10081168ac5258e5b2f6145f09d
ms.sourcegitcommit: cde65bb8b1bed1ee8cf512651afeb829ddc155de
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/19/2020
ms.locfileid: "77464965"
---
# <a name="use-r-in-power-query-editor"></a>ใช้ R ในตัวแก้ไข Power Query

[ภาษา R ](https://mran.microsoft.com/documents/what-is-r) คือภาษาการเขียนโปรแกรมที่มีประสิทธิภาพที่นักสถิติ นักวิทยาศาสตร์ข้อมูล และนักวิเคราะห์ข้อมูลใช้งาน คุณสามารถใช้ R ในในตัวแก้ไข Power Query ของ Power BI Desktop เพื่อ:

* เตรียมแบบจำลองข้อมูล

* สร้างรายงาน

* ทำการล้างข้อมูล การปรับรูปแบบข้อมูลขั้นสูง และการวิเคราะห์ชุดข้อมูลซึ่งรวมถึงการขาดข้อมูลที่สมบูรณ์ การคาดการณ์ การทำคลัสเตอร์ และอื่น ๆ  

## <a name="install-r"></a>ติดตั้ง R

คุณสามารถดาวน์โหลด R ได้ฟรีจาก[หน้าดาวน์โหลด Revolution Open](https://mran.revolutionanalytics.com/download/) และ [CRAN Repository](https://cran.r-project.org/bin/windows/base/)

## <a name="install-mice"></a>ติดตั้ง mice

ในฐานะที่เป็นข้อกำหนดเบื้องต้น คุณต้องติดตั้ง [ไลบรารี mice](https://www.rdocumentation.org/packages/mice/versions/3.5.0/topics/mice) ในสภาพแวดล้อม R ของคุณ หากไม่มี mice โค้ดสคริปต์ตัวอย่างจะทำงานไม่ถูกต้อง แพคเกจ mice ใช้วิธีการใดวิธีการหนึ่งในการจัดการกับข้อมูลที่ขาดหายไป

หากต้องการติดตั้งไลบรารี mice:

1. เปิดใช้งานโปรแกรม R.exe (ตัวอย่างเช่น C:\Program Files\Microsoft\R Open\R-3.5.3\bin\R.exe)  

2. เรียกใช้คำสั่งติดตั้งจากพร้อมท์ R:

   ``` 
   install.packages('mice') 
   ```

## <a name="use-r-in-power-query-editor"></a>ใช้ R ในตัวแก้ไข Power Query

เพื่อสาธิตการใช้ R ในตัวแก้ไข Power Query เราจะใช้ตัวอย่างชุดข้อมูลตลาดหุ้นที่มีอยู่ในไฟล์ .csv และทำงานผ่านขั้นตอนต่อไปนี้:

1. [ดาวน์โหลดไฟล์ EuStockMarkets_NA.csv](https://download.microsoft.com/download/F/8/A/F8AA9DC9-8545-4AAE-9305-27AD1D01DC03/EuStockMarkets_NA.csv) จดจำตำแหน่งที่คุณบันทึกไว้

1. โหลดไฟล์ลงใน Power BI Desktop จากแท็บ **หน้าแรก** ให้เลือก **รับข้อมูล** > **Text/CSV**

   ![เลือก Text/CSV](media/desktop-r-in-query-editor/r-in-query-editor_1.png)

1. เลือกไฟล์ EuStockMarkets_NA.csv จากนั้นเลือก **เปิด** ข้อมูล CSV จะแสดงในกล่องโต้ตอบ **ไฟล์ Text/CSV**

   ![เลือกไฟล์ CSV](media/desktop-r-in-query-editor/r-in-query-editor_2.png)

1. เลือก **โหลด** เพื่อโหลดข้อมูลจากไฟล์ หลังจากที่ Power BI ได้โหลดข้อมูลแล้ว ตารางใหม่จะปรากฏขึ้นในบานหน้าต่าง **เขตข้อมูล**

   ![ข้อมูลในบานหน้าต่างเขตข้อมูล](media/desktop-r-in-query-editor/r-in-query-editor_3.png)

1. หากต้องการเปิดตัวแก้ไข Power Query จากริบบอน**หน้าแรก** ให้เลือก**แก้ไขคิวรี**

   ![เลือกแก้ไขคิวรี](media/desktop-r-in-query-editor/r-in-query-editor_4.png)

1. จากแท็บ **แปลง** ให้เลือก **เรียกใช้สคริปต์ R** ตัวแก้ไข **เรียกใช้สคริปต์ R** จะแสดงขึ้นมา แถว 15 และ 20 มีข้อมูลที่หายไปเช่นเดียวกับแถวอื่น ๆ ที่คุณไม่สามารถดูได้ในรูป ขั้นตอนต่อไปนี้แสดงวิธีที่ R สามารถใส่ข้อมูลในแถวเหล่านั้นให้สมบูรณ์

   ![เลือก เรียกใช้สคริปต์ R](media/desktop-r-in-query-editor/r-in-query-editor_5d.png)

1. สำหรับตัวอย่างนี้ ให้ใส่โค้ดสคริปต์ต่อไปนี้ในกล่อง**สคริปต์t**ของหน้าต่าง **เรียกใช้สคริปต์ R** แทนที่ *&lt;พาธไฟล์ของคุณ&gt;* ด้วยพาธไปยัง EuStockMarkets_NA.csv บนระบบไฟล์ภายในเครื่องของคุณ ตัวอย่างเช่น C:/Users/John Doe/Documents/Microsoft/EuStockMarkets_NA.csv

    ```r
       dataset <- read.csv(file="<Your File Path>/EuStockMarkets_NA.csv", header=TRUE, sep=",")
       library(mice)
       tempData <- mice(dataset,m=1,maxit=50,meth='pmm',seed=100)
       completedData <- complete(tempData,1)
       output <- dataset
       output$completedValues <- completedData$"SMI missing values"
    ```

    > [!NOTE]
    > คุณอาจจำเป็นต้องเขียนทับตัวแปรที่ชื่อว่า *output* เพื่อสร้างชุดข้อมูลใหม่อย่างถูกต้องด้วยตัวกรองที่ใช้

7. เลือก**ตกลง** ตัวแก้ไข Power Query จะแสดงคำเตือนเกี่ยวกับความเป็นส่วนตัวของข้อมูล

   ![คำเตือนเกี่ยวกับความเป็นส่วนตัวของข้อมูล](media/desktop-r-in-query-editor/r-in-query-editor_6.png)
8. ภายในข้อความเตือน ให้เลือก **ดำเนินการต่อ** ในกล่องโต้ตอบ **ระดับความเป็นส่วนตัว** ที่ปรากฏขึ้น ให้ตั้งค่าแหล่งข้อมูลทั้งหมดเป็น **สาธารณะ** เพื่อให้สคริปต์ R ทำงานได้อย่างถูกต้องในบริการ Power BI 

   ![กล่องโต้ตอบระดับความเป็นส่วนตัว](media/desktop-r-in-query-editor/r-in-query-editor_7.png)

   สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการตั้งค่าความเป็นส่วนตัวและผลกระทบของการตั้งค่า โปรดดู[ระดับความเป็นส่วนตัวของ Power BI Desktop](desktop-privacy-levels.md)

 9. เลือก **บันทึก** เพื่อเรียกใช้สคริปต์ 

   โปรดสังเกตคอลัมน์ใหม่ในบานหน้าต่าง**เขตข้อมูล**ที่เรียกว่า **completedValues** คอลัมน์นี้มีองค์ประกอบข้อมูลบางอย่างหายไป เช่น ในแถวที่ 15 และ 18 โปรดดูที่วิธี R จัดการเรื่องเหล่านั้นที่ในหัวข้อถัดไป

   ด้วยสคริปต์ R เพียงห้าบรรทัด ตัวแก้ไข Power Query จะกรอกค่าหายไปด้วยแบบจำลองการคาดการณ์

## <a name="create-visuals-from-r-script-data"></a>สร้างวิชวลจากข้อมูลสคริปต์ R

ตอนนี้เราสามารถสร้างวิชวลเพื่อดูว่าโค้ดสคริปต์ R ที่มีไลบรารี mice ทำการเติมค่าที่ขาดหายไปเสร็จสมบูรณ์แล้วหรือยัง

![วิชวลสคริปต์ R (R Script Visual)](media/desktop-r-in-query-editor/r-in-query-editor_8a.png)

คุณสามารถบันทึกวิชวลที่สมบูรณ์ทั้งหมดในรูปแบบไฟล์ .pbix ของ Power BI Desktop ไฟล์เดียวและใช้แบบจำลองข้อมูล รวมถึงสคริปต์ R ในบริการ Power BI

> [!NOTE]
> คุณสามารถ[ดาวน์โหลดไฟล์ .pbix ](https://download.microsoft.com/download/F/8/A/F8AA9DC9-8545-4AAE-9305-27AD1D01DC03/Complete%20Values%20with%20R%20in%20PQ.pbix)ด้วยขั้นตอนที่สมบูรณ์เหล่านี้

หลังจากที่คุณอัปโหลดไฟล์ .pbix ไปยังบริการของ Power BI แล้ว คุณจำเป็นต้องดำเนินการขั้นตอนเพิ่มเติมเพื่อเปิดใช้งานการรีเฟรชข้อมูลบริการและวิชวลที่อัปเดต:  

* **เปิดใช้งานการรีเฟรชตามกำหนดการสำหรับชุดข้อมูล**: เมื่อต้องการเปิดใช้งานการรีเฟรชตามกำหนดการสำหรับสมุดงานที่มีชุดข้อมูลของคุณด้วยสคริปต์ R โปรดดู [การกำหนดค่าการรีเฟรชตามกำหนดการ](refresh-scheduled-refresh.md) บทความนี้ยังรวมถึงข้อมูลเกี่ยวกับเกตเวย์ส่วนบุคคล

* **ติดตั้งเกตเวย์ส่วนบุคคล**: คุณต้องมีเกตเวย์ส่วนบุคคลที่ติดตั้งอยู่บนเครื่องที่มีไฟล์และ R ตั้งอยู่ บริการของ Power BI เข้าถึงสมุดงานนั้นและแสดงวิชวลที่อัปเดตแล้วอีกครั้ง สำหรับข้อมูลเพิ่มเติม โปรดดู[ใช้เกตเวย์ส่วนบุคคลใน Power BI](service-gateway-personal-mode.md)

## <a name="limitations"></a>ข้อจำกัด

มีข้อจำกัดบางอย่างของการคิวรีและสคริปต์ R ที่ถูกสร้างขึ้นในตัวแก้ไข Power Query:

* การตั้งค่าแหล่งข้อมูล R ทั้งหมดต้องได้รับการตั้งค่าเป็น**สาธารณะ** ขั้นตอนอื่น ๆ ทั้งหมดในคิวรีของตัวแก้ไข Power Query จะต้องเป็นแบบสาธารณะเช่นกัน 

   เมื่อต้องการตั้งค่าแหล่งข้อมูล ใน Power BI Desktop เลือก**ไฟล์** > **ตัวเลือกและการตั้งค่า** > **การตั้งค่าแหล่งข้อมูล**

   ![ค้นหาการตั้งค่าแหล่งข้อมูล](media/desktop-r-in-query-editor/r-in-query-editor_9.png)

   ในกล่องโต้ตอบ**การตั้งค่าแหล่งข้อมูล** ให้เลือกแหล่งข้อมูลหนึ่งแหล่งขึ้นไปจากนั้นเลือก**แก้ไขสิทธิ์** ตั้งค่า**ระดับความเป็นส่วนตัว**เป็น**สาธารณะ**

   ![กล่องโต้ตอบการตั้งค่าแหล่งข้อมูล](media/desktop-r-in-query-editor/r-in-query-editor_10.png)  
  
* เมื่อต้องการกำหนดเวลาการรีเฟรชของวิชวล R หรือชุดข้อมูลของคุณ ให้เปิดใช้งานการรีเฟรชตามกำหนดเวลา และติดตั้งเกตเวย์ส่วนบุคคลในคอมพิวเตอร์ที่มีสมุดงานและ R 

มีหลากหลายสิ่งที่คุณสามารถทำได้ด้วย R และคิวรีแบบกำหนดเอง สำรวจและจัดรูปร่างข้อมูลของคุณตามที่คุณต้องการให้ปรากฏ

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [บทนำเรื่อง R](https://mran.microsoft.com/documents/what-is-r) 

* [เรียกใช้สคริปต์ R ใน Power BI Desktop](desktop-r-scripts.md) 

* [ใช้ R IDE ภายนอกกับ Power BI](desktop-r-ide.md) 

* [สร้างวิชวลโดยใช้แพ็คเกจ R ในบริการ Power BI](service-r-packages-support.md)

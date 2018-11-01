---
title: การรักษาความปลอดภัยระดับแถวแบบไดนามิกกับรูปแบบตารางข้อมูล Analysis Services ใน Power BI
description: การรักษาความปลอดภัยระดับแถวแบบไดนามิกกับรูปแบบตารางข้อมูล Analysis Services
author: selvarms
manager: amitaro
ms.reviewer: davidi
editor: davidi
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: tutorial
ms.date: 10/21/2017
ms.author: selvar
LocalizationGroup: Connect to data
ms.openlocfilehash: c49750ef51c1b8bacc36946d2d5c75a08abb36d7
ms.sourcegitcommit: 60fb46b61ac73806987847d9c606993c0e14fb30
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/25/2018
ms.locfileid: "50101588"
---
# <a name="dynamic-row-level-security-with-analysis-services-tabular-model"></a>การรักษาความปลอดภัยระดับแถวแบบไดนามิกกับรูปแบบตารางข้อมูล Analysis Services
บทช่วยสอนนี้จะแสดงให้เห็นขั้นตอนที่จำเป็นในการใช้**การรักษาความปลอดภัยระดับแถว**ภายใน**รูปแบบตารางข้อมูล Analysis Services** ของคุณและแสดงวิธีใช้ในรายงาน Power BI ขั้นตอนนี้ให้คุณทำตามและเรียนรู้ขั้นตอนต่างๆ ที่จำเป็นโดยกรอกข้อมูลในชุดข้อมูลตัวอย่าง

ใในการสอน ขั้นตอนต่อไปนี้จะอธิบายรายละเอียดในสิ่งที่คุณต้องทำเพื่อรักษาความปลอดภัยระดับแถวไดนามิกในรูปแบบตารางข้อมูล Analysis Services:

* สร้างตารางความปลอดภัยใหม่ในฐานข้อมูล **AdventureworksDW2012**
* สร้างแบบจำลองแบบตารางด้วยตารางที่มีข้อเท็จจริงและมิติข้อมูลที่จำเป็น
* กำหนดบทบาทและสิทธิ์สำหรับผู้ใช้
* ปรับใช้รูปแบบไปยังอินสแตนซ์**ตาราง Analysis Services**
* ใช้ Power BI Desktop เพื่อสร้างรายงานที่แสดงข้อมูลที่ตรงกับผู้ใช้รายงาน
* ปรับใช้รายงานไปยัง**บริการของ Power BI**
* สร้างแดชบอร์ดใหม่จากรายงาน และสุดท้าย
* แชร์แดชบอร์ดกับเพื่อนร่วมงานของคุณ

ในการทำตามขั้นตอนในบทช่วยสอนนี้ คุณต้องใช้ฐานข้อมูล **AdventureworksDW2012** ซึ่งคุณสามารถดาวน์โหลดได้จาก**[พื้นที่เก็บข้อมูล](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)**

## <a name="task-1-create-the-user-security-table-and-define-data-relationship"></a>งานที่ 1: สร้างตารางความปลอดภัยของผู้ใช้และกำหนดความสัมพันธ์ข้อมูล
มีบทความตีพิมพ์มากมายที่อธิบายถึงวิธีกำหนดระดับการรักษาความปลอดภัยแบบไดนามิกระดับแถวด้วยรูปแบบ**ตาราง SQL Server Analysis Services (SSAS)** สำหรับตัวอย่างของเรา เราทำตามบทความ[ใช้การรักษาความปลอดภัยแบบไดนามิกโดยใช้ตัวกรองแถว](https://msdn.microsoft.com/library/hh479759.aspx) ขั้นตอนต่อไปนี้จะนำคุณไปสู่งานแรกในบทช่วยสอนนี้:

1. สำหรับตัวอย่างของเรา เราใช้ฐานข้อมูลเชิงสัมพันธ์**AdventureworksDW2012** ในฐานข้อมูลนั้น ให้สร้างตาราง **DimUserSecurity** ดังแสดงในรูปต่อไปนี้ สำหรับตัวอย่างนี้ เราใช้ SQL Server Management Studio (SSMS) เพื่อสร้างตาราง
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable.png)
2. เมื่อสร้างและบันทึกตารางแล้ว เราจำเป็นต้องสร้างความสัมพันธ์ระหว่างคอลัมน์ **DimUserSecurity** ของตาราง **SalesTerritoryID** และคอลัมน์ **DimSalesTerritory** ของตาราง **SalesTerritoryKey** ดังแสดงในรูปต่อไปนี้ ซึ่งสามารถทำได้จาก **SSMS** โดยคลิกขวาที่ตาราง **DimUserSecurity** และเลือก**ออกแบบ** จากนั้นเลือก **ตัวออกแบบตาราง -> ความสัมพันธ์...** จากเมนู
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_keys.png)
3. บันทึกตาราง จากนั้น เพิ่มข้อมูลผู้ใช้อีกสองสามแถวลงในตารางอีกครั้งโดยคลิกขวาที่ตาราง **DimUserSecurity** จากนั้นเลือก **แก้ไขแถวบน 200 แถว** เมื่อคุณได้เพิ่มผู้ใช้เหล่านี้ แถวของตาราง **DimUserSecurity** จะเหมือนกับรูปภาพต่อไปนี้:
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_users.png)
   
   เราจะกลับมาหาผู้ใช้เหล่านี้ในงานที่กำลังจะเกิดขึ้น
4. ถัดไป เราจะทำ *การรวมภายใน* กับตาราง **DimSalesTerritory** ซึ่งจะแสดงรายละเอียดภูมิภาคที่เกี่ยวข้องกับผู้ใช้ โค้ดต่อไปนีดำเนินการ *การรวมภายใน* และรูปภาพต่อไปนี้แสดงให้เห็นว่าตารางจะปรากฏขึ้นเมื่อ*การรวมภายใน* ประสบความสำเร็จ
   
       select b.SalesTerritoryCountry, b.SalesTerritoryRegion, a.EmployeeID, a.FirstName, a.LastName, a.UserName from [dbo].[DimUserSecurity] as a join  [dbo].[DimSalesTerritory] as b on a.[SalesTerritoryKey] = b.[SalesTerritoryID]
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/createusersecuritytable_join_users.png)
5. โปรดสังเกตว่าภาพด้านบนแสดงข้อมูล เช่น ผู้ใช้รายใดเป็นผู้รับผิดชอบพื้นที่การขายใด ข้อมูลดังกล่าวแสดงขึ้นเนื่องจากความสัมพันธ์ที่เราสร้างขึ้นใน**ขั้นตอนที่ 2** นอกจากนี้ โปรดทราบว่าผู้ใช้ ซึ่งคือ **Jon Doe เป็นส่วนหนึ่งของพื้นที่การขายในออสเตรเลีย** เราจะไปหา John Doe อีกครั้งในขั้นตอนและงานที่จะเกิดขึ้น

## <a name="task-2-create-the-tabular-model-with-facts-and-dimension-tables"></a>งานที่ 2: สร้างแบบจำลองตารางด้วยตารางข้อเท็จจริงและมิติข้อมูล
1. เมื่อคลังข้อมูลเชิงสัมพันธ์ของคุณเสร็จเรียบร้อยแล้ว ก็ถึงเวลาที่คุณจะกำหนดแบบจำลองตารางของคุณ สามารถสร้างแบบจำลองได้โดยใช้ **SQL Server Data Tools (SSDT)** หากต้องการทราบข้อมูลเพิ่มเติมเกี่ยวกับวิธีกำหนดแบบจำลองตาราง โปรดดูที่ [สร้างโครงการแบบจำลองตารางใหม่](https://msdn.microsoft.com/library/hh231689.aspx)
2. นำเข้าตารางที่จำเป็นทั้งหมดลงในแบบจำลอง ดังที่แสดงด้านล่าง
   
    ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/ssdt_model.png)
3. เมื่อคุณนำเข้าตารางที่จำเป็น คุณต้องกำหนดบทบาทที่เรียกว่า **SalesTerritoryUsers** ที่มีสิทธิ์แบบ**อ่าน** ซึ่งสามารถทำได้โดยคลิกที่เมนู**แบบจำลอง**ใน SQL Server Data Tools จากนั้น คลิก**บทบาท** ในกล่องโต้ตอบ**ตัวจัดการบทบาท** ให้คลิก**สร้าง**
4. ใต้แท็บ**สมาชิก**ใน**ตัวจัดการบทบาท** ให้เพิ่มผู้ใช้ที่เรากำหนดไว้ในตาราง **DimUserSecurity** ใน**งาน 1 - ขั้นตอนที่ 3**
   
    ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/rolemanager.png)
5. ถัดไป เพิ่มฟังก์ชันที่ถูกต้องสำหรับตาราง **DimSalesTerritory** และ **DimUserSecurity** ตามที่แสดงด้านล่าง ใต้แท็บ**ตัวกรองแถว**
   
    ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/rolemanager_complete.png)
6. ในขั้นตอนนี้ เราใช้ฟังก์ชัน **LOOKUPVALUE** เพื่อส่งคืนค่าสำหรับคอลัมน์ซึ่งชื่อของผู้ใช้ Windows จะเหมือนกับชื่อผู้ใช้ที่ส่งกลับโดยฟังก์ชัน **USERNAME** จากนั้นจะสามารถจำกัดการสืบค้นข้อมูลซึ่งค่าที่ส่งกลับโดยค่าที่ตรงกันกับ **LOOKUPVALUE** ในตารางเดียวกัน หรือตารางที่เกี่ยวข้องได้ ในคอลัมน์**ตัวกรอง DAX** ให้พิมพ์สูตรต่อไปนี้:
   
       =DimSalesTerritory[SalesTerritoryKey]=LOOKUPVALUE(DimUserSecurity[SalesTerritoryID], DimUserSecurity[UserName], USERNAME(), DimUserSecurity[SalesTerritoryID], DimSalesTerritory[SalesTerritoryKey])
    ในสูตรนี้ ฟังก์ชัน **LOOKUPVALUE** จะส่งกลับค่าทั้งหมดสำหรับคอลัมน์ **DimUserSecurity [SalesTerritoryID]** ซึ่ง **DimUserSecurity [UserName]** จะเหมือนกับชื่อผู้ใช้ปัจจุบันที่เข้าสู่ระบบ Windows และ **DimUserSecurity [SalesTerritoryID]** จะเหมือนกับ **DimSalesTerritory [SalesTerritoryKey]**
   
    > [!IMPORTANT]
    > โปรดทราบว่า [USERELATIONSHIP](https://msdn.microsoft.com/query-bi/dax/userelationship-function-dax) ของฟังก์ชัน DAX จะไม่ได้รับการรองรับหากใช้การรักษาความปลอดภัยระดับแถว

   ชุด SalesTerritoryKey ของการขายที่ส่งกลับโดย **LOOKUPVALUE** จะใช้เพื่อจำกัดแถวที่แสดงใน **DimSalesTerritory** เฉพาะแถวที่ **SalesTerritoryKey** ของแถวที่อยู่ในชุดของรหัสที่ส่งกลับโดยฟังก์ชัน **LOOKUPVALUE** จะปรากฏขึ้น
8. สำหรับตาราง **DimUserSecurity** ในคอลัมน์**ตัวกรอง DAX** ให้พิมพ์สูตรต่อไปนี้:
   
       =FALSE()

    สูตรนี้จะระบุว่า คอลัมน์ทั้งหมดจะแก้เป็นเงื่อนไขบูลีนเท็จ ดังนั้น ไม่มีคอลัมน์สำหรับตาราง**DimUserSecurity** ที่สามารถสอบถามได้
1. ในตอนนี้ เราจำเป็นต้องประมวลผล และปรับใช้แบบจำลอง คุณสามารถอ้างอิงไปยัง[บทความการปรับใช้](https://msdn.microsoft.com/library/hh231693.aspx)สำหรับความช่วยเหลือในการปรับใช้แบบจำลอง

## <a name="task-3-adding-data-sources-within-your-on-premises-data-gateway"></a>งานที่ 3: การเพิ่มแหล่งข้อมูลภายในเกตเวย์ข้อมูลในองค์กรของคุณ
1. เมื่อแบบจำลองแบบตารางของคุณมีการปรับใช้ และพร้อมสำหรับการใช้ คุณต้องเพิ่มการเชื่อมต่อแหล่งข้อมูลไปยังเซิร์ฟเวอร์ Analysis Services แบบตารางในองค์กร ภายในพอร์ทัล Power BI ของคุณ
2. เพื่อให้**บริการของ Power BI** สามารถเข้าถึงบริการการวิเคราะห์ของคุณในสถานที่ คุณจำเป็นต้องติดตั้ง**[เกตเวย์ข้อมูลภายในองค์กร](service-gateway-onprem.md)** และกำหนดค่าในสภาพแวดล้อมของคุณ
3. เมื่อเกตเวย์ได้รับการกำหนดค่าอย่างถูกต้อง คุณต้องสร้างการเชื่อมต่อแหล่งข้อมูลสำหรับอินสแตนซ์ของตาราง **Analysis Services** ของคุณ บทความนี้จะช่วยให้คุณ[เพิ่มแหล่งข้อมูลภายในพอร์ทัล Power BI](service-gateway-enterprise-manage-ssas.md)
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/pbi_gateway.png)
4. เมื่อขั้นตอนก่อนหน้าเสร็จสมบูรณ์ เกตเวย์จะถูกกำหนดค่าและพร้อมสำหรับการโต้ตอบ กับแหล่งข้อมูล**Analysis Services** ในองค์กรของคุณ

## <a name="task-4-creating-report-based-on-analysis-services-tabular-model-using-power-bi-desktop"></a>งานที่ 4: การสร้างรายงานที่ยึดตามรูปแบบตารางข้อมูล Analysis Services โดยใช้ Power BI desktop
1. เปิดใช้งาน **Power BI Desktop** และเลือก**รับข้อมูล > ฐานข้อมูล**
2. จากรายการของแหล่งข้อมูล ให้เลือก**ฐานข้อมูล SQL Server Analysis Services** และเลือก**เชื่อมต่อ**
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata.png)
3. กรอกรายละเอียดอินสแตนซ์ของ **Analysis Services** แบบตาราง และเลือก**เชื่อมต่อแบบไลฟ์** เลือก**ตกลง** ด้วย**Power BI** การรักษาความปลอดภัยแบบไดนามิกจะใช้ได้เฉพาะกับ**การเชื่อมต่อแบบไลฟ์** เท่านั้น
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata_connectlive.png)
4. คุณจะเห็นว่า แบบจำลองที่ถูกปรับใช้อยู่ในอินสแตนซ์ของ **Analysis Services** เลือกแบบจำลองที่เกี่ยวข้อง แล้วเลือก**ตกลง**
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/getdata_connectlive.png)
5. ขณะนี้ **Power BI Desktop** จะแสดงเขตข้อมูลทั้งหมดที่พร้อมใช้งาน ทางด้านขวาของพื้นที่ทำงานในบานหน้าต่าง**เขตข้อมูล**
6. ในบานหน้าต่าง**เขตข้อมูล**ทางด้านขวา ให้เลือกการวัด **SalesAmount** จากตาราง **FactInternetSales** และมิติ **SalesTerritoryRegion** จากตาราง **SalesTerritory**
7. เราจะเก็บรายงานนี้อย่างง่ายๆ ดังนั้นเราจะไม่เพิ่มคอลัมน์ใดๆ อีกในตอนนี้ เมื่อต้องการแสดงสื่อความหมายของข้อมูลให้มากขึ้น เราจะสามารถเปลี่ยนการแสดงภาพเป็น**แผนภูมิโดนัท**
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/donut_chart.png)
8. เมื่อรายงานของคุณพร้อมแล้ว คุณสามารถเผยแพร่ไปยังพอร์ทัล Power BI ได้โดยตรง จาก ribbon ของ**หน้าแรก**ใน **Power BI Desktop**ให้เลือก**เผยแพร่**

## <a name="task-5-creating-and-sharing-a-dashboard"></a>งานที่ 5: การสร้างและการแชร์แดชบอร์ด
1. คุณได้สร้างรายงานและคลิก**เผยแพร่**ใน **Power BI Desktop** แล้ว ดังนั้น จึงมีการเผยแพร่รายงานไปยังบริการของ **Power BI** ตอนนี้ รายงานอยู่ในบริการ สภาพการการรักษาความปลอดภัยแบบจำลองของเราถูกแสดงให้เห็นได้โดยใช้ตัวอย่างที่เราได้สร้างขึ้นในขั้นตอนก่อนหน้านี้
   
   ในบทบาทของเขา **ผู้จัดการฝ่ายขาย - สุมิตร** สามารถดูข้อมูลจากทุกภูมิภาคการขาย ดังนั้น เขาจึงสร้างรายงานนี้ (รายงานที่สร้างขึ้นในขั้นตอนงานก่อนหน้านี้) และเผยแพร่ไปยังบริการของ Power BI
   
   เมื่อเขาเผยแพร่รายงาน เขาจะสร้างแดชบอร์ดในบริการของ Power BI ซึ่งเรียกว่า **TabularDynamicSec** โดยอิงกับรายงานนั้น ในภาพต่อไปนี้ โปรดสังเกตว่า Sales Manager (สุมิตร) สามารถดูข้อมูลที่เกี่ยวข้องกับพื้นที่การขายทั้งหมดได้
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/donut_chart_1.png)
2. ตอนนี้ สุมิตรแชร์แดชบอร์ดกับเพื่อนร่วมงานของเขา Jon Doe ซึ่งเป็นผู้รับผิดชอบการขายในภูมิภาคออสเตรเลีย
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/user_jon_doe.png)
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/pbi_dashboard.png)
3. เมื่อ Jon Doe ลงชื่อเข้าใช้บริการของ **Power BI** และดูหน้าแดชบอร์ดที่แบ่งปันซึ่ง Sumit สร้างไว้ Jon Doe ควรเห็น**เฉพาะ**ยอดขายจากภูมิภาคของเขาที่เขาเป็นผู้รับผิดชอบ ดังนั้น Jon Doe จะลงชื่อเข้าใช้ และเข้าสู่หน้าแดชบอร์ดที่สุมิตรใช้ร่วมกับเขา และ Jon Doe จะเห็น**เฉพาะ**ยอดขายจากภูมิภาคออสเตรเลีย
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/dashboard_jon_doe.png)
4. ขอแสดงความยินดี! การรักษาความปลอดภัยระดับแถวไดนามิกที่กำหนดไว้ในรูปแบบตารางข้อมูล **Analysis Services** ในองค์กรได้แสดงงานและปฏิบัติตามข้อกำหนดในบริการของ **Power BI** อย่างประสบความสำเร็จ Power BI ใช้คุณสมบัติ **effectiveusername** เพื่อส่งข้อมูลประจำตัวผู้ใช้ Power BI ปัจจุบันไปยังแหล่งข้อมูลในองค์กรเพื่อเรียกใช้คิวรี

## <a name="task-6-understanding-what-happens-behind-the-scenes"></a>งานที่ 6: ทำความเข้าใจกับสิ่งที่เกิดขึ้นเบื้องหลัง
1. งานนี้อนุมานว่าคุณคุ้นเคยกับ SQL Profiler เนื่องจากคุณจำเป็นต้องจับภาพการติดตามโปรไฟล์ของ SQL Server ในอินสแตนซ์ตารางแบบ SSAS ในองค์กรของคุณ
2. เซสชันได้รับการเตรียมใช้งานทันทีที่ผู้ใช้ (ในกรณีนี้คือ Jon Doe ) เข้าถึงแดชบอร์ดในบริการของ Power BI คุณสามารถพบว่า บทบาท **salesterritoryusers** มีผลทันที โดยชื่อผู้ใช้ที่มีประสิทธิภาพมีฐานะเป็น **<EffectiveUserName>jondoe@moonneo.com</EffectiveUserName>**
   
       <PropertyList><Catalog>DefinedSalesTabular</Catalog><Timeout>600</Timeout><Content>SchemaData</Content><Format>Tabular</Format><AxisFormat>TupleFormat</AxisFormat><BeginRange>-1</BeginRange><EndRange>-1</EndRange><ShowHiddenCubes>false</ShowHiddenCubes><VisualMode>0</VisualMode><DbpropMsmdFlattened2>true</DbpropMsmdFlattened2><SspropInitAppName>PowerBI</SspropInitAppName><SecuredCellValue>0</SecuredCellValue><ImpactAnalysis>false</ImpactAnalysis><SQLQueryMode>Calculated</SQLQueryMode><ClientProcessID>6408</ClientProcessID><Cube>Model</Cube><ReturnCellProperties>true</ReturnCellProperties><CommitTimeout>0</CommitTimeout><ForceCommitTimeout>0</ForceCommitTimeout><ExecutionMode>Execute</ExecutionMode><RealTimeOlap>false</RealTimeOlap><MdxMissingMemberMode>Default</MdxMissingMemberMode><DisablePrefetchFacts>false</DisablePrefetchFacts><UpdateIsolationLevel>2</UpdateIsolationLevel><DbpropMsmdOptimizeResponse>0</DbpropMsmdOptimizeResponse><ResponseEncoding>Default</ResponseEncoding><DirectQueryMode>Default</DirectQueryMode><DbpropMsmdActivityID>4ea2a372-dd2f-4edd-a8ca-1b909b4165b5</DbpropMsmdActivityID><DbpropMsmdRequestID>2313cf77-b881-015d-e6da-eda9846d42db</DbpropMsmdRequestID><LocaleIdentifier>1033</LocaleIdentifier><EffectiveUserName>jondoe@moonneo.com</EffectiveUserName></PropertyList>
3. ตามคำขอชื่อผู้ใช้ที่มีประสิทธิภาพ Analysis Services จะแปลงคำขอเป็นข้อมูลประจำตัว moonneo\jondoe จริงหลังจากคิวรี Active Directory ในเครื่อง เมื่อ **Analysis Services** ได้รับข้อมูลประจำตัวจริงจาก Active Directory จากนั้น โดยอิงกับการเข้าถึงและสิทธิ์ที่ผู้ใช้มีสำหรับข้อมูล **Analysis Services** จะแสดงเฉพาะข้อมูลที่บุคคลนั้นได้รับอนุญาตเท่านั้น
4. หากมีกิจกรรมอื่นๆ เกิดขึ้นกับแดชบอร์ด เช่น ถ้า Jon Doe ไปจากแดชบอร์ดไปยังรายงานพื้นฐาน ด้วย SQL Profiler คุณจะเห็นคิวรีเฉพาะอย่างไปยังรูปแบบตารางข้อมูล Analysis Services ในฐานะเป็นคิวรี DAX
   
   ![](media/desktop-tutorial-row-level-security-onprem-ssas-tabular/profiler1.png)
5. นอกจากนี้ คุณยังสามารถดูคิวรี DAX ที่กำลังดำเนินการเพื่อใส่ข้อมูลในรายงาน
   
   ```
   EVALUATE
     ROW(
       "SumEmployeeKey", CALCULATE(SUM(Employee[EmployeeKey]))
     )
   
   <PropertyList xmlns="urn:schemas-microsoft-com:xml-analysis">``
             <Catalog>DefinedSalesTabular</Catalog>
             <Cube>Model</Cube>
             <SspropInitAppName>PowerBI</SspropInitAppName>
             <EffectiveUserName>jondoe@moonneo.com</EffectiveUserName>
             <LocaleIdentifier>1033</LocaleIdentifier>
             <ClientProcessID>6408</ClientProcessID>
             <Format>Tabular</Format>
             <Content>SchemaData</Content>
             <Timeout>600</Timeout>
             <DbpropMsmdRequestID>8510d758-f07b-a025-8fb3-a0540189ff79</DbpropMsmdRequestID>
             <DbPropMsmdActivityID>f2dbe8a3-ef51-4d70-a879-5f02a502b2c3</DbPropMsmdActivityID>
             <ReturnCellProperties>true</ReturnCellProperties>
             <DbpropMsmdFlattened2>true</DbpropMsmdFlattened2>
             <DbpropMsmdActivityID>f2dbe8a3-ef51-4d70-a879-5f02a502b2c3</DbpropMsmdActivityID>
           </PropertyList>
   ```

## <a name="considerations"></a>ข้อควรพิจารณา
มีข้อควรพิจารณาบางอย่างเมื่อทำงานกับการรักษาความปลอดภัยระดับแถว SSAS และ Power BI:

1. การรักษาความปลอดภัยระดับแถวในองค์กรด้วย Power BI จะใช้ได้เฉพาะกับการเชื่อมต่อแบบไลฟ์เท่านั้น
2. การเปลี่ยนแปลงข้อมูลหลังจากประมวลผลแบบจำลองจะพร้อมใช้งานในทันทีสำหรับผู้ใช้ (ผู้ที่เข้าถึงรายงานด้วย**การเชื่อมต่อแบบไลฟ์**) จากบริการของPower BI


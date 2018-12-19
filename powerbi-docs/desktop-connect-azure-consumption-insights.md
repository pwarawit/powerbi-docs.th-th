---
title: เชื่อมต่อกับข้อมูล Azure Consumption Insights (เบต้า)
description: เชื่อมต่อกับ Azure และรับข้อมูลเชิงลึกเกี่ยวกับปริมาณการใช้และการใช้งานโดยใช้ Power BI Desktop ได้อย่างง่ายดาย
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 706fe9f3014ef14ff34100ff336fbf04b44e709c
ms.sourcegitcommit: cd85d88fba0d9cc3c7a4dc03d2f35d2bd096759b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 12/12/2018
ms.locfileid: "53281042"
---
# <a name="connect-to-azure-consumption-insights-in-power-bi-desktop-beta"></a>เชื่อมต่อกับ Microsoft Azure Consumption Insights (Beta) ใน Power BI Desktop (Beta)
ด้วยตัวเชื่อมต่อ**Azure Consumption Insights** คุณสามารถใช้ **Power BI Desktop**เพื่อเชื่อมต่อกับ Azure และรับข้อมูลเชิงลึกและข้อมูลเกี่ยวกับการใช้บริการ Azure ขององค์กรของคุณได้ คุณยังสามารถสร้างหน่วยวัด คอลัมน์แบบกำหนดเอง และรูปภาพเพื่อรายงาน และแชร์เกี่ยวกับการใช้งาน Azure ขององค์กรของคุณ รุ่นนี้**Azure Consumption Insights**ตัวเชื่อมต่ออยู่ในรุ่นเบต้า และจะมีการเปลี่ยนแปลง

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_01.png)

ในบทความนี้ คุณเรียนรู้วิธีการเชื่อมต่อโดยใช้ตัวเชื่อมต่อ **Azure Consumption Insights**และรับข้อมูลที่คุณต้องการ วิธีการโยกย้ายจากใช้ตัวเชื่อมต่อ Azure Enterprise และคุณจะพบการแมปของ*คอลัมน์รายละเอียดการใช้งาน*พร้อมใช้งานใน API**ACI** (Azure Consumption Insights)

## <a name="connect-to-azure-consumption-insights"></a>เชื่อมต่อกับ Azure Consumption Insights
เพื่อเชื่อมต่อโดยใช้ตัวเชื่อมต่อ **Azure Consumption Insights**อย่างเรียบร้อย คุณจำเป็นต้องมีสิทธิ์เข้าถึงฟีเจอร์ Enterprise ภายในพอร์ทัล Azure

เพื่อเชื่อมต่อโดยใช้ตัวเชื่อมต่อ **Azure Consumption Insights** เลือก**รับข้อมูล**จากริบบอน**หน้าแรก** ใน**Power BI Desktop** เลือก**บริการออนไลน์**จากประเภททางด้านซ้าย แล้วคุณจะเห็น **Microsoft Azure Consumption Insights (Beta)** เลือก **เชื่อมต่อ**

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_01b.png)

ในกล่องโต้ตอบที่ปรากฏขึ้น แสดง*หมายเลขการลงทะเบียน*ของคุณ

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_02.png)

* คุณสามารถรับหมายเลขการลงทะเบียนของคุณจาก[Azure Enterprise Portal](https://ea.azure.com) ในตำแหน่งที่ตั้งที่แสดงในรูปต่อไปนี้
  
  ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_08.png)
  
  เวอร์ชันนี้ของตัวเชื่อมต่อรองรับเฉพาะการลงทะเบียนแบบองค์กรจาก https://ea.azure.com ลงทะเบียนเรียนประเทศจีนใช้ไม่ได้ในขณะนี้

ถัดไป แสดง*Access key*เพื่อเชื่อมต่อของคุณ

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_03.png)

* Access key สำหรับการลงทะเบียนของคุณ สามารถพบได้ใน[Azure Enterprise Portal](https://ea.azure.com)
  
  ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_09.png)

เมื่อคุณใส่ของคุณ*แป้นการเข้าถึง*และเลือก**เชื่อมต่อ**บานหน้าต่าง**ตัวนำทาง**จะปรากฏขึ้น และแสดงตารางเก้าตารางที่พร้อมใช้งานสำหรับคุณ: 
* **งบประมาณ**: มีรายละเอียดงบประมาณเพื่อดูค่าใช้จ่ายจริงหรือใช้งานกับเป้าหมายงบประมาณที่มีอยู่ 
* **Marketplace**: มีค่าธรรมเนียม Azure Marketplace ตามการใช้งาน
* **ใบราคา**: มีอัตราการใช้โดยตัววัดสำหรับการลงทะเบียน
* **RICharges**: มีค่าใช้จ่ายเชื่อมโยงกับอินสแตนซ์ที่สงวนไว้ของคุณมากกว่า 24 เดือนที่ผ่านมา
* **RIRecommendations_Single**: คำแนะนำในการซื้อมีอินสแตนซ์ที่สงวนไว้ตามแนวโน้มการใช้งานของคุณในการสมัครใช้งานเดียวช่วง 7, 30 หรือ 60 วัน
* **RIRecommendations_Single**: คำแนะนำในการซื้อมีอินสแตนซ์ที่สงวนไว้ตามแนวโน้มการใช้งานของคุณในการสมัครใช้งานในช่วง 7, 30 หรือ 60 วัน
* **RIUsage**: มีรายละเอียดของปริมาณการใช้สำหรับอินสแตนซ์สงวนไว้ของคุณที่มีอยู่ช่วงเดือนที่ผ่านมา
* **สรุป**: แสดงข้อมูลสรุปรายเดือนผ่านยอดดุล ซื้อใหม่ Azure Marketplace ค่าบริการ ปรับปรุง และค่าใช้จ่ายเกิน
* **UsageDetails**: มีการแบ่งรายละเอียดของปริมาณการใช้และค่าใช้จ่ายโดยประมาณสำหรับการลงทะเบียน

คุณสามารถเลือกกล่องกาเครื่องหมายข้างตารางใดๆ เพื่อดูตัวอย่าง คุณสามารถเลือกโดยการติ๊กกล่องด้านข้างชื่อของพวกเขาอย่างน้อยหนึ่งตาราง จาก นั้นเลือก**การโหลด**

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_04b.png)

> [!NOTE]
> ตาราง*Summary*และ*PriceSheet*มีเฉพาะ API Key ในระดับลงทะเบียน นอกจากนี้ ตามค่าเริ่มต้นข้อมูลในตารางเหล่านี้มีข้อมูลของเดือนปัจจุบันสำหรับ*การใช้งาน*และ*PriceSheet* ตาราง*Summary*และ*MarketPlace*จะไม่จำกัดเฉพาะเดือนปัจจุบัน
> 
> 

เมื่อคุณเลือก**โหลด**ข้อมูลที่ถูกโหลดไปยัง**Power BI Desktop**  ตัวเชื่อมต่อจะโหลดข้อมูลตามค่าเริ่มต้นของตารางระยะเวลา  ถ้าคุณต้องการกำหนดระยะเวลาเอง[คุณสามารถตั้งค่าคิวรีแบบกำหนดเอง](https://docs.microsoft.com/en-us/power-bi/desktop-connect-azure-consumption-insights#using-azure-consumption-insights)ได้

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_05.png)

เมื่อข้อมูลที่คุณเลือกถูกโหลด ตารางและเขตข้อมูลที่คุณเลือก สามารถเห็นได้ในบานหน้าต่าง**เขตข้อมูล**

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_06.png)

## <a name="using-azure-consumption-insights"></a>ใช้ Azure Consumption Insights
เพื่อใช้ตัวเชื่อมต่อ**Azure Consumption Insights** คุณจำเป็นต้องมีสิทธิ์เข้าถึงฟีเจอรEnterprise ภาย Azure portal

เพื่อเชื่อมต่อโดยใช้ตัวเชื่อมต่อ **Azure Consumption Insights**อย่างเรียบร้อย คุณสามารถสร้างหน่วยวัดและคอลัมน์แบบกำหนดเองของคุณเองโดยใช้**ตัวแก้ไขคิวรี**และคุณสามารถสร้างภาพ รายงาน และแดชบอร์ดที่คุณสามารถใช้ร่วมกันใน **Power BI service**

Azure ยังประกอบด้วยคอลเลกชันตัวอย่างคิวรี่ ที่คุณสามารถเรียกใช้ด้วยคิวรี่ว่างเปล่า เพื่อจะทำเช่นนั้น ในริบบอน**หน้าแรก** ของ**Power BI Desktop**เลือกลูกศรดรอปดาวน์ใน**รับข้อมูล**แล้ว เลือก**คิวรี่ว่างเปล่า** คุณยังสามารถทำเช่นนี้ใน**ตัวแก้ไขคิวรี**โดยการคลิกขวาที่บานหน้าต่าง**คิวรี่**ด้านซ้าย และเลือก**คิวรีใหม่ > คิวรีว่างเปล่า**จากเมนูที่ปรากฏ

ในการ**แถบสูตร** พิมพ์ต่อไปนี้

    = MicrosoftAzureConsumptionInsights.Contents

คอลเลกชันของตัวอย่างปรากฏ ดังที่แสดงในรูปต่อไปนี้

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_07.png)

เมื่อทำงานกับรายงานและสร้างคิวรี่ ให้ใชตามต่อไปนี้

* เมื่อต้องกำหนดจำนวนเดือนที่เริ่มต้นจากวันที่ปัจจุบัน ให้ใช้*numberOfMonth*
  * ใช้ค่าระหว่าง 1 และ 36 เพื่อแสดงจำนวนเดือนที่คุณต้องการนำเข้าจากวันปัจจุบัน เราขอแนะนำให้เริ่มไม่มากกว่า 12 เดือนของข้อมูล เพื่อหลีกเลี่ยงขีดจำกัดกับข้อจำกัดการนำเข้า รวมทั้งขนาดข้อมูลที่ได้รับอนุญาตสำหรับคิวรี่ใน Power BI
* เพ่อกำหนดระยะเวลาของเดือนในหน้าต่างเวลาในอดีต ให้ใช้*startBillingDataWindow*และ*endBillingDataWindow*
* *อย่า*ใช้*numberOfMonth*ร่วมกับ*startBillingDataWindow*หรือ*endBillingDataWindow*

## <a name="migrating-from-the-azure-enterprise-connector"></a>โอนย้ายมาจากตัวเชื่อมต่อ Azure Enterprise
ลูกค้าบางคนสร้างรูปภาพขึ้นโดยใช้*Azure Enterprise Connector (Beta)* ซึ่งจะไม่ต่อและเนื่องในท้ายที่สุด จะถูกแทนที่ด้วยตัวเชื่อมต่อ**Azure Consumption Insights** ตัวเชื่อมต่อ**Azure Consumption Insights** มีฟีเจอร์และการปรับปรุงดังต่อไปนี้

* แหล่งข้อมูลเพิ่มเติมที่พร้อมใช้งานสำหรับ*สรุปยอดดุล*และ*การซื้อของ Marketplace*
* พารามิเตอร์ใหม่และขั้นสูง เช่น*startBillingDataWindow*และ*endBillingDataWindow*
* ประสิทธิภาพการทำงานและตอบสนองได้ดียิ่งขึ้น

เพื่อช่วยให้ลูกค้าเปลี่ยนไปยังตัวเชื่อมต่อ**Azure Consumption Insight**ที่ใหม่กว่า และเพื่อเก็บรักษางานที่พวกเขาได้ทำสำเร็จในการสร้างแดชบอร์ดหรือรายงานแบบกำหนดเอง ขั้นตอนต่อไปนี้แสดงวิธีการย้ายไปยังตัวเชื่อมต่อตัวใหม่

### <a name="step-1-connect-to-azure-using-the-new-connector"></a>ขั้นตอนที่ 1: เชื่อมต่อกับ Azure โดยใช้ตัวเชื่อมต่อใหม่
ขั้นตอนแรกคือการ เชื่อมต่อโดยใช้ตัวเชื่อมต่อ**Azure Consumption Insight** ซึ่งถูกอธิบายไว้ก่อนหน้าในบทความนี้โดยละเอียดแล้ว ในขั้นตอนนี้ เลือก**รับข้อมูล > คิวรีว่าง**จากริบบอน**หน้าแรก** ใน**Power BI Desktop**

### <a name="step-2-use-the-advanced-editor-to-create-a-query"></a>ขั้นตอนที่ 2: ใช้ตัวแก้ไขขั้นสูงเพื่อสร้างแบบสอบถาม
ใน**ตัวแก้ไขคิวรี**เลือก**ตัวแก้ไขขั้นสูง**จากส่วน**คิวรี่**ของการริบบอน**หน้าแรก** ในหน้าต่าง**ตัวแก้ไขขั้นสูง**ที่ปรากฎขึ้น ให้ใสคิวรี่ต่อไปนี้

    let    
        enrollmentNumber = "100",
        optionalParameters = [ numberOfMonth = 6, dataType="DetailCharges" ],
        data = MicrosoftAzureConsumptionInsights.Contents(enrollmentNumber, optionalParameters)   
    in     
        data

![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_10.png)

แน่นอน คุณจะต้องแทนค่าของ*enrollmentNumber*ด้วยหมายเลขทะเบียนของคุณเอง ซึ่งคุณสามารถรับได้จากการ[Azure Enterprise Portal](https://ea.azure.com) พารามิเตอร์*numberOfMonth*คือกี่เดือนของข้อมูลที่คุณต้องการย้อนกลับ จากข้อมูลปัจจุบัน ให้ใช้ศูนย์ (0) สำหรับเดือนปัจจุบัน

เมื่อคุณเลือก**เสร็จสิ้น**ในหน้าต่าง **ตัวแก้ไขขั้นสูง** การแสดงตัวอย่างจะรีเฟรชและคุณจะเห็นข้อมูลจากช่วงเดือนที่ระบุในตาราง เลือก**ปิดและใช้**และย้อนกลับ

### <a name="step-3-move-measures-and-custom-columns-to-the-new-report"></a>ขั้นตอนที่ 3: ย้ายหน่วยวัดและคอลัมน์แบบกำหนดเองลงในรายงานใหม่
ถัดไป คุณจะต้องย้ายคอลัมน์แบบกำหนดเองหรือหน่วยวัดที่คุณสร้างใดๆ ลงในตารางรายละเอียดใหม่ นี้เป็นขั้นตอน

1. เปิด Notepad (หรือตัวแก้ไขข้อความอื่น)
2. เลือกการวัดที่คุณต้องการย้าย คัดลอกข้อความจากฟิลด์ *สูตร* และวางใน Notepad
   
   ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_11.png)
3. เปลี่ยนชื่อ*Query1*เป็นชื่อตารางรายละเอียดต้นฉบับ
4. สร้างหน่วยวัดและคอลัมน์แบบกำหนดเองใหม่ในตารางของคุณ โดยการคลิกขวาบนตารางของคุณ แล้วเลือก**หน่วยวัดใหม่**ตัด และวางหน่วยวัดที่เก็บไว้และคอลัมน์ของคุณจนกว่าจะเสร็จสิ้น

### <a name="step-4-re-link-tables-that-had-relationships"></a>ขั้นตอนที่ 4: เชื่อมโยงตารางที่มีความสัมพันธ์ใหม่
แดชบอร์ดหลายตัวมีตารางเพิ่มเติมที่ถูกใชเพื่อการค้นหาหรือการกรอง เช่นตารางวันหรือตารางที่ใช้สำหรับโครงการแบบกำหนดเอง เมื่อมีการปรับความสัมพันธ์ดังกล่าว จะช่วยแก้ปัญหาส่วนใหญ่ นี่คือวิธีการทำ

- ในการแท็บ**การสร้างแบบจำลอง**ใน**Power BI Desktop**ให้เลือก**จัดการความสัมพันธ์**เพื่อแสดงหน้าต่างที่ช่วยให้คุณจัดการความสัมพันธ์ภายในแบบจำลอง เชื่อมโยงตารางของคุณใหม่ ตามที่คุณต้องการ
   
    ![](media/desktop-connect-azure-consumption-insights/azure-consumption-insights_12.png)

### <a name="step-5-verify-your-visuals-and-adjust-field-formatting-as-needed"></a>ขั้นตอนที่ 5: ตรวจสอบรูปภาพของคุณ และการปรับเปลี่ยนเขตข้อมูลการจัดรูปแบบตามที่ต้องการ
เมื่อคุณไดมาถึงจุดนี้ รูปภาพ ตาราง และ drill-downs ดั้งเดิมของคุณควรทำงานตามที่คาดไว้ อย่างไรก็ตาม อาจมีการจัดรูปแบบเล็กน้อยบางอย่าง เพื่อให้สิ่งต่างๆเป็นอย่างที่คุณต้องการ ใช้เวลาของเวลาในการดูแต่ละแดชบอร์ดและรูปภาพของคุณ เมื่อต้องการให้แน่ใจว่ามันเป็นไปตามแบบที่คุณต้องการ

## <a name="using-the-azure-consumption-and-insights-aci-api-to-get-consumption-data"></a>โดยใช้ Azure Consumption and Insights (ACI) API เพื่อรับข้อมูลปริมาณการใช้
Azure ยังบริการ[ **Azure Consumption and Insights (ACI) API**](https://azure.microsoft.com/blog/announcing-general-availability-of-consumption-and-charge-apis-for-enterprise-azure-customers/) คุณสามารถสร้างโซลูชันแบบกำหนดเองของคุณเองเพื่อรวบรวม รายงาน และแสดงข้อมูลปริมาณการใช้ Azure โดยใช้ ACI API

### <a name="mapping-names-and-usage-details-between-the-portal-the-connector-and-the-api"></a>การแมปชื่อและรายละเอียดการใช้งานระหว่างพอร์ทัล ตัวเชื่อมต่อ และ API
คอลัมน์และชื่อของรายละเอียดในพอร์ทัล Azure จะคล้ายกันใน API และตัวเชื่อมต่อ แตไม่เหมือนกันเสมอไป เพื่อช่วยทำให้ชัดเจน ตารางต่อไปนี้แสดงการแมประหว่าง API ตัวเชื่อมต่อ และคอลัมน์ที่คุณเห็นใน Azure Portal นอกจากนี้ยัง มีระบุเป็นว่าคอลัมนที่เก่า สำหรับข้อมูลเพิ่มเติมและข้อกำหนดของข้อกำหนดเหล่านี้ ให้ดู[พจนานุกรมข้อมูลการเรียกเก็บเงินของ Azure](https://docs.microsoft.com/azure/billing/billing-enterprise-api-usage-detail)

| ACI Connector / ContentPack ColumnName | ชื่อคอลัมน์ API ACI | ชื่อคอลัมน์ EA | ล้าสมัย / ปัจจุบันสำหรับความเข้ากันได้กับรุ่นก่อนหน้า |
| --- | --- | --- | --- |
| AccountName |accountName |ชื่อบัญชี |ไม่ใช่ |
| AccountId |accountId | |ใช่ |
| AcccountOwnerId |accountOwnerEmail |AccountOwnerId |ไม่ใช่ |
| AdditionalInfo |additionalInfo |AdditionalInfo |ไม่ใช่ |
| AdditionalInfold | | |ใช่ |
| ปริมาณการใช้ |consumedQuantity |ปริมาณการใช้ |ไม่ใช่ |
| บริการที่ใช้ไป |consumedService |บริการที่ใช้ไป |ไม่ใช่ |
| ConsumedServiceId |ConsumedServiceId | |ใช่ |
| ค่าใช้จ่าย |ค่าใช้จ่าย |ExtendedCost |ไม่ใช่ |
| ศูนย์ต้นทุน |costCenter |ศูนย์ต้นทุน |ไม่ใช่ |
| วันที่ |วันที่ |วันที่ |ไม่ |
| วัน | |วัน |ไม่ใช่ |
| DepartmentName |departmentName |ชื่อแผนก |ไม่ใช่ |
| DepartmentID |departmentId | |ใช่ |
| ID อินสแตนซ์ | | |ใช่ |
| InstanceId |instanceId |ID อินสแตนซ์ |ไม่ใช่ |
| ตำแหน่งที่ตั้ง | | |ใช่ |
| ประเภทตัววัด |meterCategory |ประเภทตัววัด |ไม่ใช่ |
| ID ตัววัด | | |ใช่ |
| ชื่อตัววัด |meterName |ชื่อตัววัด |ไม่ใช่ |
| ขอบเขตตัววัด |meterRegion |ขอบเขตตัววัด |ไม่ใช่ |
| ประเภทย่อยของตัววัด |meterSubCategory |ประเภทย่อยของตัววัด |ไม่ใช่ |
| MeterId |MeterId |ID ตัววัด |ไม่ใช่ |
| เดือน | |เดือน |ไม่ใช่ |
| ผลิตภัณฑ์ |ผลิตภัณฑ์ |ผลิตภัณฑ์ |ไม่ใช่ |
| ProductID |ProductID | |ใช่ |
| กลุ่มทรัพยากร |resourceGroup |กลุ่มทรัพยากร |ไม่ใช่ |
| ตำแหน่งที่ตั้งของทรัพยากร |resourceLocation |ตำแหน่งที่ตั้งของทรัพยากร |ไม่ใช่ |
| ResourceGroupId | | |ใช่ |
| ResourceLocationId |ResourceLocationId | |ใช่ |
| ResourceRate |ResourceRate |ResourceRate |ไม่ใช่ |
| ServiceAdministratorId |ServiceAdministratorId |ServiceAdministratorId |ไม่ใช่ |
| ServiceInfo1 |ServiceInfo1 |ServiceInfo1 |ไม่ใช่ |
| ServiceInfo1Id | | |ใช่ |
| ServiceInfo2 |ServiceInfo2 |ServiceInfo2 |ไม่ใช่ |
| ServiceInfo2Id | | |ใช่ |
| ตัวระบุบริการของร้านค้า |storeServiceIdentifier |ตัวระบุบริการของร้านค้า |ไม่ใช่ |
| StoreServiceIdentifierId | | |ใช่ |
| ชื่อการสมัครใช้งาน |subscriptionName |ชื่อการสมัครใช้งาน |ไม่ใช่ |
| แท็ก |แท็ก |แท็ก |ไม่ใช่ |
| TagsId | | |ใช่ |
| หน่วยวัด |unitOfMeasure |หน่วยวัด |ไม่ใช่ |
| ปี | |ปี |ไม่ใช่ |
| SubscriptionId |SubscriptionId |SubscriptionId |ใช่ |
| SubscriptionGuid |SubscriptionGuid |SubscriptionGuid |ไม่ใช่ |

## <a name="next-steps"></a>ขั้นตอนถัดไป
มีข้อมูลหลากหลายประเภทที่คุณสามารถเชื่อมต่อโดยใช้ Power BI Desktop สำหรับข้อมูลเพิ่มเติมเกี่ยวกับแหล่งข้อมูล โปรดดูทรัพยากรต่อไปนี้:

* [Power BI Desktop คืออะไร](desktop-what-is-desktop.md)
* [แหล่งข้อมูลใน Power BI Desktop](desktop-data-sources.md)
* [จัดรูปทรงและรวมข้อมูลด้วย Power BI Desktop](desktop-shape-and-combine-data.md)
* [เชื่อมต่อกับเวิร์กบุ๊ก Excel ใน Power BI Desktop](desktop-connect-excel.md)   
* [ป้อนข้อมูลลงใน Power BI Desktop โดยตรง](desktop-enter-data-directly-into-desktop.md)   


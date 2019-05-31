---
title: การรวม Azure Machine Learning ใน Power BI (ตัวอย่าง)
description: เรียนรู้วิธีใช้ Machine Learning ด้วย Power BI
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/02/2019
ms.author: davidi
LocalizationGroup: conceptual
ms.openlocfilehash: 6c09392566805f2857c50784f16c0e3f9d4b5697
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "61232524"
---
# <a name="azure-machine-learning-integration-in-power-bi-preview"></a>การรวม Azure Machine Learning ใน Power BI (ตัวอย่าง)

องค์กรมากมายใช้แบบจำลอง **Machine Learning** เพื่อข้อมูลเชิงลึกและการคาดการณ์เกี่ยวกับธุรกิจของตนเองที่ดีกว่า ความสามารถในการแสดงผลด้วยภาพจากแบบจำลองเหล่านี้ในรายงานและแดชบอร์ดรวมถึงการวิเคราะห์อื่นๆ ของคุณสามารถช่วยเผยแพร่ข้อมูลเชิงลึกเหล่านี้ให้แก่ผู้ใช้ทางธุรกิจที่ต้องการมากที่สุดได้  ขณะนี้ Power BI ช่วยให้การรวมข้อมูลเชิงลึกจากแบบจำลองที่โฮสต์บนบริการ Azure Machine Learning โดยใช้ลักษณะการชี้และคลิกโดยตรงได้อย่างง่ายดาย

หากต้องการใช้ความสามารถนี้ นักวิทยาศาสตร์ข้อมูลสามารถให้สิทธิ์เข้าถึงแบบจำลอง Azure ML ไปยังนักวิเคราะห์ BI โดยใช้พอร์ทัล Azure ได้อย่างง่ายดาย  จากนั้น ณ จุดเริ่มต้นของแต่ละเซสชัน Power Query จะค้นพบแบบจำลอง Azure MLทั้งหมดที่ผู้ใช้ได้เข้าถึง และแสดงเป็นฟังก์ชัน Power Query แบบไดนามิก  จากนั้นผู้ใช้จะสามารถเรียกใช้ฟังก์ชันเหล่านั้นโดยการเข้าถึงจาก Ribbon ในตัวแก้ไข Power Query หรือโดยการเรียกฟังก์ชัน M โดยตรง นอกจากนี้ Power BI ยังรวมคำขอการเข้าถึงโดยอัตโนมัติเมื่อเรียกแบบจำลอง Azure ML สำหรับชุดของแถวเพื่อบรรลุประสิทธิภาพการทำงานที่ดีกว่า

ฟังก์ชันนี้จะได้รับการรองรับเฉพาะกระแสข้อมูล Power BI และ Power Query แบบออนไลน์ในบริการของ Power BI

หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับกระแสข้อมูล โปรดดู [การเตรียมข้อมูลด้วยตนเองใน Power BI](service-dataflows-overview.md)

หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับ Azure Machine Learning โปรดดู:

- ภาพรวม:  [บริการ Azure Machine Learning คืออะไร](https://docs.microsoft.com/azure/machine-learning/service/overview-what-is-azure-ml)
- เริ่มต้นใช้งานด่วนและบทช่วยสอนสำหรับ Azure Machine Learning:  [เอกสารประกอบ Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/)

## <a name="granting-access-to-the-azure-ml-model-to-a-power-bi-user"></a>การให้สิทธิ์เข้าถึงแบบจำลอง Azure ML แก่ผู้ใช้ Power BI

หากต้องการเข้าถึงแบบจำลอง Azure ML จาก Power BI ผู้ใช้จะต้องมีการสมัครใช้งาน Azure ที่มีการเข้าถึงแบบ **อ่าน**  นอกจากนี้:

- แบบจำลอง Machine Learning Studio ต้องใช้การเข้าถึงแบบ **อ่าน** สำหรับบริการบนเว็บ Studio Machine Learning
- แบบจำลองบริการ Machine Learning ต้องใช้การเข้าถึงแบบ **อ่าน** สำหรับบริการพื้นที่ทำงาน Studio Machine Learning

ขั้นตอนในบทความนี้จะอธิบายวิธีให้สิทธิ์ใช้งานแก่ผู้ใช้ Power BI ในการเข้าถึงแบบจำลองที่โฮสต์บนบริการ Azure ML เพื่อให้ผู้ใช้สามารถเข้าถึงแบบจำลองนี้เป็นฟังก์ชัน Power Query  โปรดดู [จัดการการเข้าถึง RBAC และพอร์ทัล Azure](https://docs.microsoft.com/azure/role-based-access-control/role-assignments-portal) สำหรับรายละเอียดอื่นๆ

1. ลงชื่อเข้าใช้ไปยัง [พอร์ทัล Azure](https://portal.azure.com)

2. ไปที่หน้า **การสมัครใช้งาน** คุณสามารถค้นหาหน้า **การสมัครใช้งาน** ผ่านรายการ **บริการทั้งหมด** ในเมนูนำทางด้านซ้ายของพอร์ทัล Azure

    ![หน้าการสมัครใช้งาน Azure](media/service-machine-learning-integration/machine-learning-integration_01.png)

3. เลือกการสมัครใช้งานของคุณ

    ![เลือกการสมัครใช้งานของคุณ](media/service-machine-learning-integration/machine-learning-integration_02.png)

4. เลือก **ควบคุมการเข้าถึง (IAM)** แล้วเลือกปุ่ม **เพิ่ม**

    ![การควบคุมการเข้าถึง IAM](media/service-machine-learning-integration/machine-learning-integration_03.png)

5. เลือกบทบาทเป็น **ผู้อ่าน** เลือกผู้ใช้ Power BI ที่คุณต้องการให้สิทธิ์เข้าถึงแบบจำลอง Azure ML

    ![เลือกบทบาทเป็นผู้อ่าน](media/service-machine-learning-integration/machine-learning-integration_04.png)

6. เลือก**บันทึก**

7. ทำซ้ำขั้นตอนที่สามถึงหกเพื่อให้สิทธิ์การเข้าถึงแบบ **ผู้อ่าน** แก่ผู้ใช้สำหรับบริการบนเว็บ Machine Learning Studio เฉพาะ *หรือ* พื้นที่ทำงานบริการ Machine Learning ที่โฮสต์แบบจำลอง


## <a name="schema-discovery-for-machine-learning-service-models"></a>การค้นพบ Schema สำหรับแบบจำลองบริการ  Machine Learning

นักวิทยาศาสตร์ข้อมูลใช้ Python เป็นหลักเพื่อพัฒนาหรือแม้กระทั่งปรับใช้ แบบจำลอง Machine Learning ของตนเองสำหรับแบบจำลองบริการ Machine Learning  ต่างจาก Machine Learning Studio ซึ่งช่วยให้งานการสร้างไฟล์ Schema สำหรับแบบจำลองเป็นไปโดยอัตโนมัติ ในกรณีของบริการ Machine Learning นักวิทยาศาสตร์ข้อมูลต้องสร้างไฟล์ Schema อย่างชัดเจนโดยใช้ Python

ไฟล์ Schema นี้ต้องรวมอยู่ใน

## <a name="invoking-the-azure-ml-model-in-power-bi"></a>การเรียกแบบจำลอง Azure ML ใน Power BI

คุณสามารถเรียกแบบจำลอง Azure ML ใดๆ ที่คุณได้รับสิทธิ์เข้าถึงได้ โดยตรงจากตัวแก้ไข Power Query ในกระแสข้อมูลของคุณ หากต้องการเข้าถึงแบบจำลอง Azure ML ให้เลือกปุ่ม **แก้ไข** สำหรับเอนทิตีที่คุณต้องการเติมแต่งด้วยข้อมูลเชิงลึกจากแบบจำลอง Azure ML ของคุณดังที่แสดงในรูปภาพต่อไปนี้

![บริการของ Power BI - แก้ไขเอนทิตี](media/service-machine-learning-integration/machine-learning-integration_05.png)

การเลือกปุ่ม **แก้ไข** เพื่อเปิดตัวแก้ไข Power Query สำหรับเอนทิตีในกระแสข้อมูลของคุณ

![ตัวแก้ไข Power Query](media/service-machine-learning-integration/machine-learning-integration_06.png)

เลือกปุ่ม **ข้อมูลเชิงลึก AI** ใน Ribbon จากนั้นเลือกโฟลเดอร์ _แบบจำลอง Azure Machine Learning_ จากเมนูการนำทางด้านซ้าย แบบจำลอง Azure ML ทั้งหมดที่คุณสามารถเข้าถึงได้จะแสดงที่นี่เป็นฟังก์ชัน Power Query นอกจากนี้ พารามิเตอร์ที่ป้อนเข้าสำหรับแบบจำลอง Azure ML จะแมปเป็นพารามิเตอร์ของฟังก์ชัน Power Query ที่สอดคล้องกันโดยอัตโนมัติ

หากต้องการเรียกแบบจำลอง Azure ML คุณสามารถระบุคอลัมน์ของเอนทิตีที่เลือกใดๆ ก็ได้ เป็นข้อมูลป้อนเข้าจากดรอปดาวน์ นอกจากนี้คุณยังสามารถระบุค่าคงที่เพื่อใช้เป็นข้อมูลป้อนเข้าได้ โดยสลับไอคอนคอลัมน์ไปทางซ้ายของกล่องโต้ตอบที่ป้อนเข้า

![เลือกคอลัมน์](media/service-machine-learning-integration/machine-learning-integration_07.png)

เลือก **การเรียก** เพื่อดูตัวอย่างผลลัพธ์ของแบบจำลอง Azure ML เป็นคอลัมน์ใหม่ในตารางเอนทิตี นอกจากนี้คุณจะเห็นการเรียกแบบจำลองเป็นขั้นตอนที่นำไปใช้สำหรับคิวรี

![เลือกการเรียก](media/service-machine-learning-integration/machine-learning-integration_08.png)

หากแบบจำลองส่งกลับพารามิเตอร์ผลลัพธ์หลายรายการ พารามิเตอร์เหล่านั้นจะถูกจัดกลุ่มเข้าด้วยกันเป็นระเบียนในคอลัมน์ผลลัพธ์ คุณสามารถขยายคอลัมน์เพื่อสร้างแต่ละพารามิเตอร์ผลลัพธ์ในคอลัมน์แยกต่างหากได้

![ขยายคอลัมน์](media/service-machine-learning-integration/machine-learning-integration_09.png)

เมื่อบันทึกกระแสข้อมูลของคุณแล้ว ระบบจะเรียกแบบจำลองโดยอัตโนมัติเมื่อมีการรีเฟรชกระแสข้อมูล สำหรับแถวใหม่หรือแถวที่ได้รับการอัปเดตใดๆ ในตารางเอนทิตี

## <a name="next-steps"></a>ขั้นตอนถัดไป

บทความนี้จะให้ภาพรวมของการรวม Machine Learning ลงในบริการ Power BI บทความต่อไปนี้อาจน่าสนใจและเป็นประโยชน์สำหรับคุณ 

* [บทช่วยสอน: เรียกใช้แบบจำลอง Machine Learning Studio ใน Power BI (ตัวอย่าง)](service-tutorial-invoke-machine-learning-model.md)
* [บทช่วยสอน: การใช้ Cognitive Services ใน Power BI](service-tutorial-use-cognitive-services.md)
* [Cognitive Services ใน Power BI (ตัวอย่าง)](service-cognitive-services.md)

คุณสามารถอ่านบทความเหล่านี้สำหรับข้อมูลเพิ่มเติมเกี่ยวกับกระแสข้อมูลได้:
* [การสร้างและใช้กระแสข้อมูลใน Power BI](service-dataflows-create-use.md)
* [ใช้เอนทิตีที่มีการคำนวณใน Power BI Premium](service-dataflows-computed-entities-premium.md)
* [ใช้ dataflows กับแหล่งข้อมูลภายในองค์กร](service-dataflows-on-premises-gateways.md)
* [ทรัพยากรสำหรับนักพัฒนาสำหรับ dataflows Power BI](service-dataflows-developer-resources.md)
* [ การรวมกระแสข้อมูลและ Azure Data Lake (ตัวอย่าง)](service-dataflows-azure-data-lake-integration.md)



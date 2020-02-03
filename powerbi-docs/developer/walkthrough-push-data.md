---
title: ส่งข้อมูลลงในชุดข้อมูล
description: ส่งข้อมูลลงในชุดข้อมูล Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/22/2019
ms.openlocfilehash: ceebf32f62395db8741eaf43cfc494652fbbbf98
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/29/2020
ms.locfileid: "76818812"
---
# <a name="push-data-into-a-power-bi-dataset"></a>ส่งข้อมูลลงในชุดข้อมูล Power BI

Power BI API ช่วยให้คุณสามารถส่งข้อมูลลงในชุดข้อมูล Power BI ได้ ในบทความนี้ เราจะแสดงวิธีการส่งชุดข้อมูลการตลาดการขายที่มีตารางผลิตภัณฑ์ลงในชุดข้อมูลที่มีอยู่

ก่อนที่คุณเริ่มต้นใช้งาน คุณจำเป็นต้องมี Azure Active Directory (Azure AD) และ[บัญชี Power BI](create-an-azure-active-directory-tenant.md)

## <a name="steps-to-push-data-into-a-dataset"></a>ขั้นตอนการส่งข้อมูลลงในชุดข้อมูล

* ขั้นตอนที่ 1: [ลงทะเบียนแอปกับ Azure AD](walkthrough-push-data-register-app-with-azure-ad.md)
* ขั้นตอนที่ 2: [รับโทเค็นการเข้าถึงการรับรองความถูกต้อง](walkthrough-push-data-get-token.md)
* ขั้นตอนที่ 3: [สร้างชุดข้อมูลใน Power BI](walkthrough-push-data-create-dataset.md)
* ขั้นตอนที่ 4: [รับชุดข้อมูลเพื่อเพิ่มแถวลงในตาราง Power BI](walkthrough-push-data-get-datasets.md)
* ขั้นตอนที่ 5: [เพิ่มแถวลงในตาราง Power BI](walkthrough-push-data-add-rows.md)

ในส่วนถัดไปคือการสนทนาทั่วไปของการดำเนินการ Power BI API ที่ส่งข้อมูล

## <a name="power-bi-api-operations-to-push-data"></a>การดำเนินการของ BI API power เพื่อส่งข้อมูล

คุณสามารถส่งแหล่งข้อมูลไปยัง Power BI ได้โดยใช้ Power BI REST API เมื่อแอปจะเพิ่มแถวไปยังชุดข้อมูล ไทล์แดชบอร์ดจะอัปเดตโดยอัตโนมัติด้วยข้อมูลใหม่ เมื่อต้องการส่งข้อมูล ใช้การดำเนินการ [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset) และ [PostRows](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows) เมื่อต้องการค้นหาชุดข้อมูล ให้ใช้การดำเนินการ[รับชุดข้อมูล](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets) คุณสามารถส่ง ID ของกลุ่มเพื่อทำงานกับกลุ่มได้จากการดำเนินการเหล่านี้ ใช้การดำเนินการ[รับชุดข้อมูล](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups)เพื่อรับรายการของรหัสกลุ่ม

ต่อไปนี้เป็นการดำเนินการเพื่อส่งข้อมูลลงในชุดข้อมูล:

* [โพสต์ชุดข้อมูล](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset)
* [รับชุดข้อมูล](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets)
* [โพสต์แถว](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows)
* [รับกลุ่ม](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups)

คุณสามารถสร้างชุดข้อมูลใน Power BI ได้โดยการส่งสตริง JavaScript Object Notation (JSON) ไปยังบริการ Power BI เมื่อต้องการเรียนรู้เพิ่มเติมเกี่ยวกับ JSON ดู[การแนะนำ JSON](https://json.org/)

สตริง JSON สำหรับชุดข้อมูลที่มีรูปแบบต่อไปนี้:

**Power BI ชุดข้อมูล JSON วัตถุ**

    {"name": "dataset_name", "tables":
        [{"name": "", "columns":
            [{ "name": "column_name1", "dataType": "data_type"},
             { "name": "column_name2", "dataType": "data_type"},
             { ... }
            ]
          }
        ]
    }

สำหรับตัวอย่างชุดข้อมูลการขายและการตลาดของเรา คุณจะผ่านสตริง JSON ดังที่แสดงด้านล่าง ในตัวอย่างนี้ **การขายและการตลาด**คือชื่อของชุดข้อมูล และ**ผลิตภัณฑ์**คือชื่อของตาราง หลังจากที่คุณกำหนดตาราง จากนั้นกำหนด schema ของตาราง สำหรับชุดข้อมูล **การขายและการตลาด** ตาราง schema มีคอลัมน์เหล่านี้: ProductID ผู้ผลิต ประเภท เซ็กเมนต์ ผลิตภัณฑ์ และ IsCompete

**ตัวอย่างชุดข้อมูลวัตถุ JSON**

    {
        "name": "SalesMarketing",
        "tables": [
            {
                "name": "Product",
                "columns": [
                {
                    "name": "ProductID",
                    "dataType": "int"
                },
                {
                    "name": "Manufacturer",
                    "dataType": "string"
                },
                {
                    "name": "Category",
                    "dataType": "string"
                },
                {
                    "name": "Segment",
                    "dataType": "string"
                },
                {
                    "name": "Product",
                    "dataType": "string"
                },
                {
                    "name": "IsCompete",
                    "dataType": "bool"
                }
                ]
            }
        ]
    }

คุณสามารถใช้ชนิดข้อมูลต่อไปนี้สำหรับสคีของตาราง Power BI

## <a name="power-bi-table-data-types"></a>ชนิดข้อมูลตาราง Power BI

| **ชนิดข้อมูล** | **ข้อจำกัด** |
| --- | --- |
| Int64 |Int64.MaxValue และ Int64.MinValue ไม่ได้รับอนุญาต |
| สองครั้ง |Double.MaxValue และค่า Double.MinValue ไม่ได้รับอนุญาต NaN ที่ไม่ได้รับการสนับสนุน + ค่าอนันต์และ - ค่าอนันต์ที่ไม่ได้รับการสนับสนุนในบางฟังก์ชัน (เช่น  Min, Max) |
| บูลีน |ไม่มี |
| วันที่เวลา |ในระหว่างการโหลดข้อมูล เราแบ่งนับค่าด้วยเศษส่วนวันให้กับตัวคูณทั้งหมดของ 1/300 วินาที (3.33ms) |
| สตริง |อนุญาตให้มีอักขระได้ถึง 128 K อักขระในขณะนี้ |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>เรียนรู้เพิ่มเติมเกี่ยวกับการส่งข้อมูลลงใน Power BI

เมื่อต้องเริ่มส่งข้อมูลลงในชุดข้อมูล ให้ดูที่[ขั้นตอนที่ 1: ลงทะเบียนแอปกับ Azure AD](walkthrough-push-data-register-app-with-azure-ad.md) ซึ่งอยู่ในบานหน้าต่างนำทาง

[ขั้นตอนถัดไป >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป

[ลงทะเบียนใช้งาน Power BI](create-an-azure-active-directory-tenant.md)  
[การแนะนำ JSON](https://json.org/)  
[ภาพรวมของ Power BI REST API](overview-of-power-bi-rest-api.md)  
มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](https://community.powerbi.com/)
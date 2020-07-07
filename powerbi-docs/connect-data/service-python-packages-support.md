---
title: เรียนรู้แพ็คเกจ Python ที่รองรับ
description: แพ็คเกจ Python ที่ได้รับการรองรับ และไม่รองรับใน Power BI
author: otarb
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/26/2020
ms.author: otarb
LocalizationGroup: Connect to data
ms.openlocfilehash: b1dc77d2ebf0803430ceeace7e14bfa62a6d2a60
ms.sourcegitcommit: e8b12d97076c1387088841c3404eb7478be9155c
ms.contentlocale: th-TH
ms.lasthandoff: 07/01/2020
ms.locfileid: "85785244"
---
# <a name="create-visuals-by-using-python-packages-in-the-power-bi-service"></a>สร้างวิชวลโดยใช้แพ็คเกจ Python ในบริการ Power BI
คุณสามารถใช้ [ภาษาคอมพิวเตอร์ Python](https://www.python.org/) ที่มีประสิทธิภาพเพื่อสร้างภาพในบริการ Power BI ได้ แพ็คเกจ Python หลายแพ็กเกจได้รับการรองรับในบริการ Power BI และหลายแพ็คเกจจะได้รับการรองรับตลอดเวลา

ส่วนต่อไปนี้ให้ตารางที่เรียงตามตัวอักษรของแพ็คเกจ Python ที่ได้รับการรองรับใน Power BI 

## <a name="request-support-for-a-new-python-package"></a>ขอรับการสนับสนุนสำหรับแพ็คเกจ Python ใหม่
แพ็คเกจ Python รองรับการ**บริการ Power BI**ที่พบในส่วนต่อไปนี้ ชื่อว่า**แพ็คเกจที่ได้รับการรองรับ** ถ้าคุณต้องการขอรับการรองรับให้กับแพ็คเกจ Python ที่ไม่พบในรายการที่แสดงอยู่ โปรดส่งคำขอของคุณมาที่ [Power BI Ideas](https://ideas.powerbi.com)

## <a name="requirements-and-limitations-of-python-packages"></a>แพ็คเกจข้อกำหนดและขีดจำกัดของ Python
มีข้อกำหนดและขีดจำกัดสำหรับแพคเกจ Python อยู่เล็กน้อยดังนี้:

* รันไทม์ของ Python ปัจจุบัน: Python 3.7.7.
* บริการ Power BI ส่วนใหญ่รองรับแพ็คเกจ Python ที่มีใบอนุญาตซอฟต์แวร์แบบเปิดและฟรี เช่น GPL-2 GPL-3 MIT+ และอื่น ๆ
* บริการ Power BI รองรับแพ็คเกจที่เผยแพร่ใน PyPI บริการไม่รองรับแพ็คเกจ Python ส่วนตัว หรือแบบกำหนดเอง แนะนำให้ผู้ใช้สร้างแพ็คเกจส่วนตัวของพวกเขาพร้อมใช้งานบน PyPI ก่อนที่จะร้องขอแพ็คเกจมีอยู่ในบริการ Power BI
* สำหรับภาพของ Python ใน **Power BI Desktop**คุณสามารถติดตั้งแพ็คเกจใดก็ได้รวมถึงแพ็คเกจ Python แบบกำหนดเอง
* สำหรับเหตุผลทางด้านความปลอดภัยและความเป็นส่วนตัว แพ็คเกจ Python ที่มีคิวรีจากไคลเอนต์-เซิร์ฟเวอร์ทั่วเครือข่ายเวิลด์ไวด์เว็บ  บริการนี้จะไม่รองรับ ระบบเครือข่ายบล็อกการกระทำดังกล่าว
* กระบวนการอนุมัติเพื่อรวมแพ็คเกจ Python ใหม่มีแผนภูมิต้นไม้ของความสัมพันธ์ โดยที่บางความสัมพันธ์ต้องมีการติดตั้งในการบริการที่ไม่รองรับก่อน

## <a name="python-packages-that-are-supported-in-power-bi"></a>แพ็คเกจ Python ที่ได้รับการรองรับใน Power BI
ตารางต่อไปนี้แสดงแพ็คเกจที่**ได้รับการสนับสนุน**ในบริการ Power BI


|        แพ็คเกจ        |   เวอร์ชัน   |                                   ลิงก์                                   |
|-----------------------|-------------|--------------------------------------------------------------------------|
|matplotlib|3.2.1|https://pypi.org/project/matplotlib|
|numpy|1.18.4|https://pypi.org/project/numpy|
|แพนด้า|1.0.1|https://pypi.org/project/pandas|
|scikit-learn|0.23.0|https://pypi.org/project/scikit-learn|
|scipy|1.4.1|https://pypi.org/project/scipy|
|s eaborn|0.10.1|https://pypi.org/project/seaborn|
|statsmodels|0.11.1|https://pypi.org/project/statsmodels|
|xgboost|1.1.0|https://pypi.org/project/xgboost|

## <a name="next-steps"></a>ขั้นตอนถัดไป
สำหรับข้อมูลเพิ่มเติมเกี่ยวกับ Python ใน Power BI โปรดดูที่บทความต่อไปนี้:

* [สร้างวิชวลของ Power BI โดยใช้ Python](desktop-python-visuals.md)
* [ขั้นตอนการเรียกใช้สคริปต์ Python ใน Power BI Desktop](desktop-python-scripts.md)
* [การใช้ Python ใน Query Editor](desktop-python-in-query-editor.md)

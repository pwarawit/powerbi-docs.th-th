---
title: ปกป้องข้อมูล Power BI พร้อมการระบเดิมของอุปกรณ์
description: เรียนรู้วิธีการกำหนดค่าแอป iOS ของคุณเพื่อกำหนดการระบุเพิ่มเติมก่อนที่คุณสามารถเข้าถึงข้อมูล Power BI ของคุณ
author: mshenhav
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 06/07/2019
ms.author: mshenhav
ms.openlocfilehash: a4ae7d7d61f4b377fe020fcc5f66f68ae7709ac7
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/09/2019
ms.locfileid: "73870165"
---
# <a name="protect-power-bi-app-with-face-id-touch-id-or-passcode"></a>ปกป้องแอป Power BI ด้วย Face ID, Touch ID หรือรหัสผ่าน 

ในหลายกรณี ข้อมูลที่จัดการใน Power BI จะถือเป็นความลับ และจำเป็นต้องได้รับการปกป้อง และการเข้าถึงได้โดยผู้ใช้ที่ได้รับอนุญาตเท่านั้น 

แอป iOS ของ Power BI ช่วยให้คุณปกป้องข้อมูลของคุณโดยการกำหนดค่าการระบุเพิ่มเติม คุณจำเป็นต้องระบุ Face ID, Touch ID หรือรหัสผ่านทุกครั้งที่คุณเปิดใช้แอป หรือเมื่อคุณนำแอปจากพื้นหลังไปยังพื้นหน้า

| ![iPhone](./media/tutorial-mobile-apps-ios-qna/iphone-logo-50-px.png) | ![iPad](./media/tutorial-mobile-apps-ios-qna/ipad-logo-50-px.png) |
|:--- |:--- |
| iPhone |iPad |

## <a name="turn-on-face-id-touch-id-or-passcode-in-app-setting"></a>เปิด Face ID, Touch ID หรือรหัสผ่านในการตั้งค่าแอป

เมื่อต้องใช้การระบุเพิ่มเติมใน Power BI ไปที่การตั้งค่าแอปภายใต้**ความเป็นส่วนตัวและการรักษาความปลอดภัย** คุณจะเห็นตัวเลือกในการเปิด Face ID, Touch ID หรือรหัสผ่านซึ่งขึ้นอยู่กับความสามารถของอุปกรณ์ของคุณ

![หน้าการตั้งค่าแอป iOS ของ Power BI](./media/mobile-ios-native-secure-access/mobile-ios-native-secured-setting.png)

ทันทีที่การตั้งค่านี้เปิดใช้งาน ทุกครั้งที่คุณเปิดใช้งาน Power BI หรือนำมันออกจากพื้นหลัง ระบบจะขอให้คุณระบุ ID ของคุณก่อนที่คุณสามารถเข้าถึงแอปได้ 

การตัดสินใจในการขอ Face ID, Touch ID หรือรหัสผ่านดำเนินการโดย iOS ซึ่งขึ้นอยู่กับความสามารถของอุปกรณ์ ถ้าอุปกรณ์ของคุณสนับสนุน Face ID คุณจำเป็นต้องใช้ Face ID ถ้าสนับสนุน Touch ID คุณจำเป็นต้องใช้ Touch ID ถ้าอุปกรณ์ของคุณรองรับทั้งสองระบบ จากนั้นคุณจำเป็นต้องระบุรหัสผ่าน

![Face ID ระบบ iOS ของ Power BI](./media/mobile-ios-native-secure-access/mobile-ios-native-secured-faceid.png)

## <a name="use-mdm-to-enforce-face-id-touch-id-or-passcode"></a>ใช้ MDM เพื่อบังคับใช้ Face ID, Touch ID หรือรหัสผ่าน

บางองค์กรมีนโยบายด้านความปลอดภัยและข้อกำหนดการปฏิบัติตามข้อบังคับที่บังคับใช้กับการระบุเพิ่มเติมก่อนที่คุณสามารถเข้าถึงข้อมูลที่มีความละเอียดอ่อนทางธุรกิจได้ 

แอป iOS สำหรับอุปกรณ์เคลื่อนของ Power BI ช่วยให้ผู้ดูแลระบบสามารถควบคุมการตั้งค่านั้น โดยแสดงการตั้งค่าการกำหนดค่าแอปจาก Microsoft Intune และโซลูชันการจัดการอุปกรณ์เคลื่อนที่ (MDM) อื่น ผู้ดูแลระบบสามารถใช้นโยบายการปกป้องแอปเพื่อเปิดการตั้งค่านี้สำหรับผู้ใช้ทั้งหมด หรือกลุ่มของผู้ใช้

|คีย์  |ชนิด  |คำอธิบาย  |
|---------|---------|---------|
| com.microsoft.powerbi.mobile.ForceDeviceAuthentication | บูลีน | ค่าเริ่มต้นเป็น False <br>เมื่อตั้งค่าเป็น True แอปจะบังคับผู้ใช้ให้ระบุตัวเองโดยใช้ Face ID, Touch ID หรือรหัสผ่านก่อนที่จะสามารถดูข้อมูล Power BI ในแอปได้ ผู้ใช้ที่ไม่มี Face ID, Touch ID หรือรหัสผ่านที่กำหนดค่าบนอุปกรณ์จำเป็นต้องกำหนดค่าก่อนจึงจะสามารถเข้าถึง Power BI ได้  |

## <a name="next-steps"></a>ขั้นตอนถัดไป

[ใช้ MDM เพื่อกำหนดค่าแอป iOS ของ Power BI จากระยะไกล](mobile-app-configuration.md)

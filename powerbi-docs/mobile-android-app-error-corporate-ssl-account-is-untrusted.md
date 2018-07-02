---
title: การแก้ไข “ไม่เชื่อถือใบรับรอง SSL ขององค์กรของคุณ”
description: เมื่อลงชื่อเข้าใช้แอป Android สำหรับ Power BI คุณอาจเห็นข้อความว่า "ไม่สามารถรับรองความถูกต้องเนื่องจากใบรับรอง SSL ขององค์กรของคุณไม่น่าเชื่อถือ
.": ''
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: maggies
ms.openlocfilehash: 494e148a62675aab1a6e799c4e4b61f022483d9f
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/26/2018
ms.locfileid: "34444968"
---
# <a name="fixing-corporate-ssl-certificate-is-untrusted---power-bi"></a>การแก้ไข “ไม่เชื่อถือใบรับรอง SSL ขององค์กรของคุณ” - Power BI
เมื่อลงชื่อเข้าใช้แอป Android บนมือถือสำหรับ Microsoft Power BI คุณอาจเห็นข้อความว่า "ไม่สามารถรับรองความถูกต้องเนื่องจากใบรับรอง SSL ขององค์กรของคุณไม่น่าเชื่อถือโดยอุปกรณ์นี้ โปรดติดต่อผู้ดูแลระบบไอทีของบริษัทของคุณ" 

สิ่งที่คุณต้องทำมักจะขึ้นอยู่กับระบบปฏิบัติการบนอุปกรณ Android ของคุณ แต่มีปัญหาอื่นๆที่อาจทำให้เกิดข้อผิดพลาดนี้

## <a name="on-android-7-or-later"></a>Android 7 หรือรุ่นใหม่กว่า
ค้นหาการอัปเดตสำหรับแอปที่มีชื่อว่า **Chrome** และติดตั้งการอัปเดต

## <a name="on-android-6-and-earlier"></a>Android 6 และรุ่นก่อนหน้านี้
อุปกรณ์ของคุณอาจต้องใช้ System Webview รุ่นที่อัปเดตแล้ว ซึ่งอาจติดตั้งในอุปกรณ์ของคุณและคุณเพียงแค่คลิก **อัปเดต**

หากไม่ได้ติดตั้ง System Webview ไว้ในอุปกรณ์ของคุณ:

1. ปิด Power BI บนอุปกรณ์ Android ของคุณ
2. เปิด Google Play Store และค้นหา **System Webview** โดย Google Inc.
3. ติดตั้ง
4. รีสตาร์ทแอป Power BI และลงชื่อเข้าใช้

## <a name="time-zone-settings"></a>การตั้งค่าเขตเวลา
การตั้งค่าเขตเวลาในอุปกรณ์อาจผิดพลาด 

ไปที่ **การตั้งค่า** > **ระบบ** > **วันที่และเวลา** เพื่อตรวจสอบ

## <a name="custom-authentication-server"></a>เซิร์ฟเวอร์การรับรองความถูกต้องแบบกำหนดเอง
หากคุณใช้เซิร์ฟเวอร์การรับรองความถูกต้องแบบกำหนดเอง ใบรับรอง SSL ในเซิร์ฟเวอร์การรับรองความถูกต้องขององค์กรอาจไม่ถูกต้อง โปรดติดต่อผู้ดูแลระบบไอทีขององค์กรเพื่อช่วยเหลือคุณ

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [ดาวน์โหลดแอป Android](http://go.microsoft.com/fwlink/?LinkID=544867) จาก Android app store.
* มีคำถามหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


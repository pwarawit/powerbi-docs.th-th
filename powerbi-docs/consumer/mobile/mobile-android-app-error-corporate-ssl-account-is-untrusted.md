---
title: การแก้ไข “ไม่เชื่อถือใบรับรอง SSL ขององค์กรของคุณ”
description: เมื่อลงชื่อเข้าใช้แอป Android สำหรับ Power BI คุณอาจเห็นข้อความว่า "ไม่สามารถรับรองความถูกต้องเนื่องจากใบรับรอง SSL ขององค์กรของคุณไม่น่าเชื่อถือ
.": ''
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: mshenhav
ms.openlocfilehash: de103412e21e0d26d20058e2d4e1fb9a8a5449bf
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "61341362"
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
หากคุณใช้เซิร์ฟเวอร์การรับรองความถูกต้องแบบกำหนดเอง ใบรับรอง SSL ในเซิร์ฟเวอร์การรับรองความถูกต้องขององค์กรอาจไม่ถูกต้อง โปรดทำงานร่วมกันกับฝ่าย IT ในองค์กรของคุณ เพื่อทดสอบการรับรองความถูกต้องของการกำหนดค่าเซิร์ฟเวอร์องค์กร โดยทำตามคำแนะนำใน[บทความนี้](https://support.microsoft.com/en-us/help/3203929/using-adal-to-authenticate-from-android-devices-fails-if-additional-ce)

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [ดาวน์โหลดแอป Android](http://go.microsoft.com/fwlink/?LinkID=544867) จาก Android app store.
* มีคำถามหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/) 


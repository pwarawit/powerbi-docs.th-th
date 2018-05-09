---
title: 'ข้อผิดพลาด: '
corporate: ''
ssl: ''
certificate: ''
is: ''
untrusted": ''
'-': ''
power: ''
bi": ''
description: เมื่อลงชื่อเข้าใช้แอป Android สำหรับ Power BI คุณอาจเห็นข้อความว่า "ไม่สามารถรับรองความถูกต้องเนื่องจากใบรับรอง SSL ขององค์กรของคุณไม่น่าเชื่อถือ
.": ''
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 4ef29c0cab96e21045f30805d7445aa34d37697a
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/13/2017
---
# <a name="error-corporate-ssl-certificate-is-untrusted---power-bi"></a>ข้อผิดพลาด “ใบรับรอง SSL ขององค์กรของคุณไม่น่าเชื่อถือ”- Power BI
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


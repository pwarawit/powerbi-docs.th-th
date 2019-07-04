---
title: อัปเดต ลบ และแยกแอปแม่แบบใน Power BI
description: วิธีการอัปเดต ลบ และแยกแอปแม่แบบ
author: teddybercovitz
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/10/2019
ms.author: tebercov
ms.openlocfilehash: 273734493c761739f9780e6a7fe6e781900723f9
ms.sourcegitcommit: 7d52401f50944feaaa112c84113ee47f606dbf68
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/13/2019
ms.locfileid: "67125889"
---
# <a name="update-delete-and-extract-template-app"></a>อัปเดต ลบ และแยกแอปแม่แบบ

หลังจากที่แอปของคุณอยู่ในผลิต คุณสามารถเริ่มต้นในขั้นตอนการทดสอบโดยไม่รบกวนแอปในการผลิต
## <a name="update-your-app"></a>อัปเดตแอปของคุณ


1. ในบานหน้าต่าง **การจัดการวางจำหน่าย** เลือก**สร้างแอป**
2. ย้อนกลับผ่านขั้นตอนการสร้างแอป
3. หลังจากที่คุณได้ตั้งค่า**Branding**, **เนื้อหา**, **ควบคุม**และ**Access**คุณเลือก**สร้างแอ**.
4. เลือก **ปิด** และกลับไปยัง**การจัดการวางจำหน่าย**

   คุณเห็นว่าคุณมีสองเวอร์ชันในขณะนี้: เวอร์ชันในผลิต รวมถึงเวอร์ชันใหม่ในการทดสอบ

    ![ทั้งสองเวอร์ชันของแอปแม่แบบ](media/service-template-apps-update-extract-delete/power-bi-template-app-update.png)

5. เมื่อคุณพร้อมที่จะเลื่อนระดับแอปของคุณไปยังการผลิตล่วงหน้าสำหรับการทดสอบภายนอกผู้เช่าของคุณเพิ่มเติม **ย้อนกลับไปที่บานหน้าต่างการจัดการวางจำหน่าย** **และเลือก เลื่อนแอป ถัดจากการทดสอบ**
6. ขณะนี้ลิงก์ของคุณได้ออนไลน์แล้ว ส่งไปยังพอร์ทัล Cloud Partner (CPP) อีกครั้งโดยทำตามขั้นตอนที่ [การอัปเดตข้อเสนอของแอป Power BI](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-update-existing-offer)
7. ใน CPP คุณต้อง**เผยแพร่**ข้อเสนอของคุณอีกครั้งและต้องให้ตรวจสอบอีกครั้ง

>[!NOTE]
>เลื่อนระดับแอปของคุณไปเป็นขั้นตอนการผลิตเฉพาะหลังจากที่แอปของคุณจะได้รับอนุมัติโดยพอร์ทัล Cloud Partner และคุณเผยแพร่แล้วเท่านั้น

## <a name="extract-workspace"></a>แยกพื้นที่ทำงาน
ด้วยความสามารถในการแยกการย้อนกลับเป็นเวอร์ชันก่อนหน้าของแอปเทมเพลตสามารถทำได้ง่ายขึ้น ขั้นตอนต่อไปนี้จะแยกเวอร์ชันแอปเฉพาะจากขั้นตอนต่าง ๆ ที่เผยแพร่ลงในพื้นที่ทำงานใหม่:

1. ในบานหน้าต่างการจัดการแผยแพร่ กด **(...)** เพิ่มจากนั้น**แยก**

    ![แยกเวอร์ชันแอปเทมเพล](media/service-template-apps-update-extract-delete/power-bi-template-app-extract.png) ![แยกเวอร์ชันแอปเทมเพลต](media/service-template-apps-update-extract-delete/power-bi-template-app-extract-dialog.png)
2. ในกล่องโต้ตอบ ใส่ชื่อสำหรับพื้นที่ทำงานที่จะแยกออกมา พื้นที่ทำงานใหม่จะถูกเพิ่ม

รีเซ็ตการกำหนดรุ่นของพื้นที่ทำงานใหม่ของคุณ คุณสามารถพัฒนาและกระจายแอปเทมเพลตจากพื้นที่ทำงานใหม่แยกออกมา

## <a name="delete-template-app-version"></a>ลบเวอรชันแอปเทมเพลต
เทมแพลตพื้นที่ทำงานแอปเป็นแหล่งข้อมูลของแอแม่แบบกระจายที่ใช้งานอยู่ เพื่อปกป้องผู้ใช้แอปเทมเพลต ผู้ใช้จะไม่สามารถลบพื้นที่ทำงานโดยไม่ต้องลบเวอร์ชันแอปที่สร้างขึ้นทั้งหมดในพื้นที่ทำงานก่อนหน้านี้ได้
การลบเวอร์ชันแอปยังเป็นการลบลบ URL ของแอปที่ไม่ทำงานอีกแล้วไปด้วย

1. ในบานหน้าต่างการจัดการเผยแพร่ กดเลือกจุดไข่ปลา **(...)** จากนั้น**ลบ**
 ![ลบเวอร์ชันแอปเทมเพลต](media/service-template-apps-update-extract-delete/power-bi-template-app-delete.png)
  ![ลบเวอร์ชันแอปเทมเพลต](media/service-template-apps-update-extract-delete/power-bi-template-app-delete-dialog.png)

>[!NOTE]
>ต้องแน่ใจว่าจะไม่ลบเวอร์ชันแอปหรือ**AppSource**ที่ลูกค้ากำลังใช้งานอยู่หรือแอปเหล่านั้นไม่สามารถใช้งานได้อีกต่อไป

## <a name="next-steps"></a>ขั้นตอนถัดไป

ดูวิธีการที่ลูกค้าของคุณโต้ตอบกับแอปแม่แบบของคุณใน[ติดตั้ง กำหนดเอง และเผยแพรแอปแม่แบบในองค์กรของคุณ](service-template-apps-install-distribute.md)

ดู[ข้อเสนอแอปพลิเคชัน BI Power](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer)สำหรับรายละเอียดเกี่ยวกับการแจกจ่ายแอปของคุณ
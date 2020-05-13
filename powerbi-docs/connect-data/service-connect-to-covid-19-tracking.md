---
title: การเชื่อมต่อรายงานการติดตาม COVID-19 ในสหรัฐอเมริกา
description: วิธีการรับและติดตั้งแอปเทมเพลตของเคส COVID-19 และวิธีการเชื่อมต่อกับข้อมูล
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/05/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 97e0a4f6e522997e6f132d1c3dbc493188ba66ba
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83275489"
---
# <a name="connect-to-the-covid-19-us-tracking-report"></a>การเชื่อมต่อรายงานการติดตาม COVID-19 ในสหรัฐอเมริกา
บทความนี้จะแจ้งวิธีการติดตั้งแอปเทมเพลตสำหรับรายงานการติดตาม COVID-19 และวิธีการเชื่อมต่อกับแหล่งข้อมูลให้คุณทราบ

![รายงานการติดตาม COVID-19 ในสหรัฐอเมริกา](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-title-screen.png)

สำหรับข้อมูลโดยละเอียดเกี่ยวกับตัวรายงาน รวมถึงการปฏิเสธความรับผิดชอบและข้อมูลเกี่ยวกับข้อมูล โปรดศึกษาจาก[ตัวอย่างการติดตาม COVID-19 ของรัฐแห่งสหรัฐอเมริกาและรัฐบาลท้องถิ่น](../create-reports/sample-covid-19-us.md)

หลังจากที่คุณได้ติดตั้งแอปเทมเพลตและเชื่อมต่อกับแหล่งข้อมูลแล้ว คุณสามารถปรับแต่งรายงานได้ตามความต้องการของคุณ จากนั้นคุณจะสามารถเผยแพร่รายงานออกเป็นแอปให้กับเพื่อนร่วมงานในองค์กรของคุณได้

## <a name="install-the-app"></a>ติดตั้งแอป

1. คลิกที่ลิงก์ต่อไปนี้เพื่อเข้าถึงแอป: [แอปเทมเพลตรายงานการติดตาม COVID-19 ในสหรัฐอเมริกา](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.covid19ms)

1. เมื่อคุณอยู่ในหน้า Appsource ของแอปให้คลิก [**รับทันที**](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.covid19ms)

    [![รายงานการติดตาม COVID-19 ในสหรัฐอเมริกาใน Appsource](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-appsource-icon.png)](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.covid19ms)

1. เมื่อมีข้อความแสดงขึ้น ให้คลิก **Install** หลังจากที่ติดตั้งแอปแล้ว คุณจะเห็นแอปบนหน้าแอปของคุณ

   ![รายงานการติดตาม COVID-19 ในสหรัฐอเมริกาบนหน้าแอป](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-apps-page-icon.png)

## <a name="connect-to-data-sources"></a>เชื่อมต่อกับแหล่งข้อมูล

1. คลิกที่ไอคอนบนหน้าแอปของคุณเพื่อเปิดแอป

1. บนหน้าจอเริ่มต้นที่ปรากฏขึ้น เลือก **เชื่อมต่อ**

   ![หน้าจอเริ่มต้นของแอปเทมเพลต](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-splash-screen.png)

1. กล่องโต้ตอบการลงชื่อเข้าใช้งานแบบสองขั้นตอนจะปรากฏขึ้น โดยจะมีขั้นตอนที่สองต่อจากขั้นตอนแรก ในทั้งสองขั้นตอน ให้ตั้งค่าระดับความเป็นส่วนตัวเป็นสาธารณะ

   ![กล่องโต้ตอบการลงชื่อเข้าใช้งานของรายงานการติดตาม COVID-19 ในสหรัฐอเมริกา](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-signin-dialog.png)

   รายงานจะเชื่อมต่อกับแหล่งข้อมูล ซึ่งจะมีข้อมูลล่าสุดแจ้งเข้าไปอยู่เสมอ ในช่วงเวลานี้ ตัวตรวจสอบกิจกรรมจะเปิดทำงาน

   ![กำลังรีเฟรชรายงานการติดตาม COVID-19 ในสหรัฐอเมริกา](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-refresh-monitor.png)

## <a name="schedule-report-refresh"></a>กำหนดเวลาการรีเฟรชรายงาน

เมื่อการรีเฟรชข้อมูลเสร็จสมบูรณ์ คุณจะอยู่ในพื้นที่ทำงานที่เชื่อมโยงกับแอป [ตั้งค่ากำหนดเวลาการรีเฟรช](../connect-data/refresh-scheduled-refresh.md)เพื่อให้ข้อมูลรายงานเป็นข้อมูลล่าสุดอยู่เสมอ

## <a name="customize-and-share"></a>ปรับแต่งตามความต้องการและแชร์

คุณสามารถดูรายละเอียดได้ที่[ปรับแต่งและแชร์แอป](../connect-data/service-template-apps-install-distribute.md#customize-and-share-the-app) ตรวจสอบให้มั่นใจว่าคุณได้อ่าน[ข้อความปฏิเสธความรับผิดชอบของรายงาน](../create-reports/sample-covid-19-us.md#disclaimers)ก่อนที่จะเผยแพร่หรือแจกจ่ายแอป

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [ตัวอย่างการติดตาม COVID-19 สำหรับรัฐของสหรัฐอเมริกาและรัฐบาลในท้องถิ่น](../create-reports/sample-covid-19-us.md)
* มีคำถามหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
* [แอปเทมเพลต Power BI คืออะไร](../connect-data/service-template-apps-overview.md)
* [ติดตั้งและแจกจ่ายแอปเทมเพลตในองค์กรของคุณ](../connect-data/service-template-apps-install-distribute.md)

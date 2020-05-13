---
title: เชื่อมต่อไปยังแดชบอร์ดการตอบสนองเหตุฉุกเฉินในระดับภูมิภาค
description: วิธีการรับและติดตั้งแดชบอร์ดการสนับสนุนการตัดสินใจของ COVID-19 สำหรับแอปเทมเพลตการตอบสนองเหตุฉุกเฉินในระดับภูมิภาคและวิธีการเชื่อมต่อกับข้อมูล
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/24/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 52522c03a285290fbc01da49328516f62ddfc60a
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83279238"
---
# <a name="connect-to-the-regional-emergency-response-dashboard"></a>เชื่อมต่อไปยังแดชบอร์ดการตอบสนองเหตุฉุกเฉินในระดับภูมิภาค
แดชบอร์ดการตอบสนองเหตุฉุกเฉินในระดับภูมิภาคคือคอมโพเนนต์รายงานของ[โซลูชันการตอบสนองเหตุฉุกเฉินของ Microsoft Power Platform](https://docs.microsoft.com/powerapps/sample-apps/regional-emergency-response/overview) ผู้ดูแลระบบระดับภูมิภาคสามารถดูแดชบอร์ดในผู้เช่า Power BI ของตน เพื่อให้พวกเขาสามารถดูข้อมูลและเมตริกที่สำคัญที่จะช่วยให้พวกเขาตัดสินใจได้อย่างมีประสิทธิภาพ

![รายงานของแอปแดชบอร์ดการตอบสนองเหตุฉุกเฉินในระดับภูมิภาค](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-report.png)

บทความนี้บอกวิธีการติดตั้งแอปการตอบสนองเหตุฉุกเฉินในระดับภูมิภาคโดยใช้แอปแดชบอร์ดการตอบสนองเหตุฉุกเฉินในระดับภูมิภาคและวิธีการเชื่อมต่อกับแหล่งข้อมูล

สำหรับข้อมูลโดยละเอียดเกี่ยวกับสิ่งที่แสดงในแดชบอร์ด โปรดดู [รับข้อมูลเชิงลึก](https://docs.microsoft.com/powerapps/sample-apps/regional-emergency-response/portals-admin-reporting#get-insights)

หลังจากที่คุณได้ติดตั้งแอปเทมเพลตและเชื่อมต่อกับแหล่งข้อมูลแล้ว คุณสามารถปรับแต่งรายงานได้ตามความต้องการของคุณ จากนั้นคุณจะสามารถเผยแพร่รายงานออกเป็นแอปให้กับเพื่อนร่วมงานในองค์กรของคุณได้

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

ก่อนที่จะติดตั้งแอปเทมเพลตนี้ คุณต้องติดตั้งและตั้งค่า[โซลูชันการตอบสนองเหตุฉุกเฉินในระดับภูมิภาค](https://docs.microsoft.com/powerapps/sample-apps/regional-emergency-response/deploy)ก่อน การติดตั้งโซลูชันนี้จะสร้างการอ้างอิงแหล่งข้อมูลที่จำเป็นเพื่อป้อนข้อมูลลงในแอป

เมื่อทำการติดตั้งโซลูชันการตอบสนองเหตุฉุกเฉินในระดับภูมิภาคแล้ว ให้จดบันทึก [URL ของสภาพแวดล้อมอินสแตนซ์ Common Data Service ของคุณ](https://docs.microsoft.com/powerapps/sample-apps/regional-emergency-response/deploy#step-5-configure-and-publish-power-bi-dashboard)เอาไว้ คุณจะต้องใช้ข้อมูลนี้เพื่อเชื่อมต่อแอปเทมเพลตเข้ากับข้อมูล

## <a name="install-the-app"></a>ติดตั้งแอป

1. คลิกที่ลิงก์ต่อไปนี้เพื่อเข้าถึงแอป: [แอปแดชบอร์ดการตอบสนองเหตุฉุกเฉินในระดับภูมิภาค](https://appsource.microsoft.com/product/power-bi/powerapps_cxo.regional_response)

1. บนหน้า AppSource สำหรับแอป ให้เลือก [**รับทันที**](https://appsource.microsoft.com/product/power-bi/powerapps_cxo.regional_response)

    [![แอปแดชบอร์ดการตอบสนองดหตุฉุกเฉินในระดับภูมิภาคใน AppSource](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-appsource-get-it-now.png)](https://appsource.microsoft.com/product/power-bi/powerapps_cxo.regional_response)

1. เลือก**ติดตั้ง** 

    ![ติดตั้งแอปแดชบอร์ดการตอบสนองเหตุฉุกเฉินในระดับภูมิภาค](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-select-install.png)

    หลังจากที่ติดตั้งแอปแล้ว คุณจะเห็นแอปบนหน้าแอปของคุณ

   ![แอปแดชบอร์ดการตอบสนองเหตุฉุกเฉินในระดับภูมิภาคบนหน้าแอป](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-apps-page-icon.png)

## <a name="connect-to-data-sources"></a>เชื่อมต่อกับแหล่งข้อมูล

1. เลือกไอคอนบนหน้าแอปของคุณเพื่อเปิดแอป

1. บนหน้าจอเริ่มต้น เลือก **สำรวจ**

   ![หน้าจอเริ่มต้นของแอปเทมเพลต](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-splash-screen.png)

   แอปจะเปิดขึ้นและแสดงข้อมูลตัวอย่าง

1. เลือกลิงก์ **เชื่อมต่อข้อมูลของคุณ** บนแบนเนอร์ที่ด้านบนของหน้า

   ![แอปแดชบอร์ดการตอบสนองเหตุฉุกเฉินในระดับภูมิภาคจะเชื่อมโยงข้อมูลของคุณ](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-connect-data.png)

1. ในกล่องโต้ตอบที่ปรากฏขึ้น ให้พิมพ์ [URL ของอินสแตนซ์ของสภาพแวดล้อม Common Data Service ของคุณ](https://docs.microsoft.com/powerapps/sample-apps/emergency-response/deploy-configure#publish-the-power-bi-dashboard) เช่น: https://[myenv].crm.dynamics.com เมื่อป้อนเสร็จเรียบร้อย ให้คลิก **ถัดไป**

   ![กล่องโต้ตอบ URL ของแอปแดชบอร์ดการตอบสนองเหตุฉุกเฉินในระดับภูมิภาค](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-url-dialog.png)

1. ในกล่องโต้ตอบที่ปรากฏขึ้นถัดไป ให้ตั้งค่าวิธีการรับรองความถูกต้องให้กับ **OAuth2** คุณไม่ต้องปรับเปลี่ยนการตั้งค่าระดับความเป็นส่วนตัวใด ๆ

   เลือก**ลงชื่อเข้าใช้**

   ![กล่องโต้ตอบการรับรองความถูกต้องของแอปแดชบอร์ดการตอบสนองเหตุฉุกเฉินในระดับภูมิภาค](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-authentication-dialog.png)

1. ที่หน้าจอลงชื่อเข้าใช้ของ Microsoft ใหลงชื่อเข้าใช้ Power BI

   ![หน้าจอลงชื่อเข้าใช้ของ Microsoft](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-microsoft-login.png)

   หลังจากที่คุณลงชื่อเข้าใช้แล้ว รายงานจะเชื่อมต่อเข้ากับแหล่งข้อมูลและจะได้รับข้อมูลล่าสุด ในช่วงเวลานี้ ตัวตรวจสอบกิจกรรมจะเปิดทำงาน

   ![กำลังดำเนินการรีเฟรชแอปแดชบอร์ดการตอบสนองเหตุฉุกเฉินในระดับภูมิภาค](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-refresh-monitor.png)

## <a name="schedule-report-refresh"></a>กำหนดเวลาการรีเฟรชรายงาน

เมื่อรีเฟรชข้อมูลแล้ว ให้[ตั้งค่ากำหนดเวลาการรีเฟรช](../connect-data/refresh-scheduled-refresh.md)เพื่อให้ข้อมูลรายงานเป็นข้อมูลล่าสุดอยู่เสมอ

1. ในแถบส่วนหัวด้านบนสุด เลือก **Power BI**

   ![เส้นทางของ Power BI](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-powerbi-breadcrumb.png)

1. ในหน้าต่างนำทางด้านซ้าย มองหาพื้นที่ทำงานของแดชบอร์ดการตอบสนองเหตุฉุกเฉินในระดับภูมิภาคที่อยู่ใน**พื้นที่ทำงาน** แล้วปฏิบัติตามคำแนะนำที่อธิบายไว้ในบทความ[กำหนดค่าการรีเฟรชตามกำหนดเวลา](../connect-data/refresh-scheduled-refresh.md)

## <a name="customize-and-share"></a>ปรับแต่งตามความต้องการและแชร์

คุณสามารถดูรายละเอียดได้ที่[ปรับแต่งและแชร์แอป](../connect-data/service-template-apps-install-distribute.md#customize-and-share-the-app) ตรวจสอบให้มั่นใจว่าคุณได้อ่าน[ข้อความปฏิเสธความรับผิดชอบของรายงาน](https://docs.microsoft.com/powerapps/sample-apps/regional-emergency-response/overview#disclaimer)ก่อนที่จะเผยแพร่หรือแจกจ่ายแอป

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [การทำความเข้าใจเกี่ยวกับแดชบอร์ดการตอบสนองเหตุฉุกเฉินในระดับภูมิภาค](https://docs.microsoft.com/powerapps/sample-apps/regional-emergency-response/portals-admin-reporting#get-insights)
* [ตั้งค่าและเรียนรู้เกี่ยวกับตัวอย่างเทมเพลตของการสื่อสารในภาวะวิกฤติใน Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/sample-crisis-communication-app)
* มีคำถามหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
* [แอปเทมเพลต Power BI คืออะไร](../connect-data/service-template-apps-overview.md)
* [ติดตั้งและแจกจ่ายแอปเทมเพลตในองค์กรของคุณ](../connect-data/service-template-apps-install-distribute.md)

---
title: เชื่อมต่อกับ Microsoft Graph Security ใน Power BI Desktop
description: เชื่อมต่อกับ Microsoft Graph Security API ใน Power BI Desktop ได้อย่างง่ายดาย
author: cpopell
manager: kfile
ms.reviewer: ''
ms.custom: seojan19
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/29/2019
ms.author: gepopell
LocalizationGroup: Connect to data
ms.openlocfilehash: 1594935d9dc156b03daff9e4447752bce2c0f06c
ms.sourcegitcommit: 88ac51106ec7d0ead8c2a1550a11afae0d502bb9
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/12/2019
ms.locfileid: "56086689"
---
# <a name="connect-to-microsoft-graph-security-in-power-bi-desktop"></a>เชื่อมต่อกับ Microsoft Graph Security ใน Power BI Desktop

คุณสามารถใช้ Power BI Desktop เพื่อเชื่อมต่อกับ Microsoft Graph Security API โดยใช้ตัวเชื่อมต่อ Microsoft Graph Security Power BI ซึ่งจะช่วยให้คุณสามารถสร้างแดชบอร์ดและรายงานที่ช่วยให้คุณสามารถรับข้อมูลเชิงลึกให้กับการรักษาความปลอดภัยของคุณที่เกี่ยวข้อง[การแจ้งเตือน](https://docs.microsoft.com/graph/api/resources/alert?view=graph-rest-1.0)และ[Secure Score](https://docs.microsoft.com/graph/api/resources/securescores?view=graph-rest-beta) [ Microsoft Graph security API](https://aka.ms/graphsecuritydocs)เชื่อมต่อ[โซลูชันการรักษาความปลอดภัยหลากหลาย](https://aka.ms/graphsecurityalerts)จาก Microsoft และคู่ค้าระบบนิเวศเพื่อเปิดใช้งานความสัมพันธ์ที่ง่ายดายยิ่งขึ้นต่อการแจ้งเตือน มอบการเข้าถึงข้อมูลตามบริบทที่สมบูรณ์ และลดความซับซ้อนของระบบอัตโนมัติ ซึ่งช่วยเพิ่มศักยภาพขององค์กรเพื่อรับข้อมูลเชิงลึกได้อย่างรวดเร็ว และดำเนินการทั่วทั้งผลิตภัณฑ์การรักษาความปลอดภัย พร้อมลดต้นทุนและความซับซ้อนของการสร้าง และบำรุงรักษาการรวมหลายรายการ

## <a name="prerequisites-to-connect-with-the-microsoft-graph-security-connector"></a>ข้อกำหนดเบื้องต้นเพื่อเชื่อมต่อกับตัวเชื่อมต่อ Microsoft Graph Security

* ในการใช้ตัวเชื่อมต่อ Microsoft Graph Security คุณจะต้อง*ระบุ* ความยินยอมของผู้ดูแลระบบผู้เช่า Azure Active Directory (AD) อย่างชัดเจนซึ่งเป็นส่วนหนึ่งของ[ข้อกำหนดการรับรองความถูกต้องของ Microsoft Graph Security ](https://aka.ms/graphsecurityauth). ความยินยอมนี้จำเป็นต้องใช้รหัสแอปพลิเคชันของตัวเชื่อมต่อ Microsoft Graph Security Power BI และชื่อ ซึ่งคุณยังสามารถค้นหาได้ใน[พอร์ทัล Azure](https://portal.azure.com):

   | คุณสมบัติ | ค่า |
   |----------|-------|
   | **ชื่อแอปพลิเคชัน** | `MicrosoftGraphSecurityPowerBIConnector` |
   | **รหัสแอปพลิเคชัน** | `cab163b7-247d-4cb9-be32-39b6056d4189` |
   |||

   ในการให้ความยินยอมสำหรับตัวเชื่อมต่อ ผู้ดูแลระบบผู้เช่า Azure AD ของคุณสามารถทำตามขั้นตอนเหล่านี้:

   * [ให้การยินยอมผู้ดูแลระบบผู้เช่าสำหรับแอปพลิเคชัน Azure AD](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent)

   * ในระหว่างการเรียกใช้แอปเชิงตรรกะของคุณครั้งแรก แอปของคุณสามารถขอความยินยอมจากผู้ดูแลระบบผู้เช่า Azure AD ของคุณผ่าน[ประสบการณ์การให้ความยิมยอมในการใช้งานแอปพลิเคชัน](https://docs.microsoft.com/azure/active-directory/develop/application-consent-experience)ได้
   
* บัญชีผู้ใช้ที่ใช้เพื่อลงชื่อเข้าใช้เพื่อเชื่อมโยงกับตัวเชื่อมต่อ Microsoft Graph Security Power BI ต้องเป็นสมาชิกของบทบาทผู้ดูแลระบบตัวอ่านระบบความปลอดภัยแบบจำกัดใน Azure AD (ตัวอ่านระบบความปลอดภัยหรือผู้ดูแลระบบความปลอดภัย) ทำตามขั้นตอนในส่วน[กำหนดบทบาท Azure AD ให้กับผู้ใช้](https://docs.microsoft.com/graph/security-authorization#assign-azure-ad-roles-to-users) 

## <a name="using-the-microsoft-graph-security-connector"></a>ใช้ตัวเชื่อมต่อ Microsoft Graph Security

ทำตามขั้นตอนเหล่านี้เพื่อใช้ตัวเชื่อมต่อ**Microsoft Graph Security**่:

1. เลือก**รับข้อมูล -> เพิ่มเติม...** จากริบบิ้น**หน้าแรก**ใน Power BI Desktop
2. เลือก **บริการออนไลน์** จากหมวดหมู่ทางด้านซ้าย
3. คลิกที่**Microsoft Graph Security (รุ่นเบต้า)**

    ![รับข้อมูล](media/desktop-connect-graph-security/GetData.PNG)
    
4. ในหน้าต่าง**Microsoft Graph Security**ที่ปรากฎขึ้น เลือกเวอร์ชันของ Microsoft Graph API เพื่อทำการคิวรี ตัวเลือกคือ v1.0 และรุ่นเบต้า

    ![เลือกเวอร์ชัน](media/desktop-connect-graph-security/selectVersion.PNG)
    
5. ลงชื่อเข้าใช้บัญชี Azure Active Directory เมื่อได้รับแจ้ง บัญชีนี้จำเป็นต้องอยู่ในบทบาท**ตัวอ่านการรักษาความปลอดภัย** ตามที่กล่าวถึงในส่วนข้อกำหนดเบื้องต้นด้านบน

    ![ลงชื่อเข้าใช้](media/desktop-connect-graph-security/SignIn.PNG)
    
6. ถ้าคุณเป็นผู้ดูแลระบบผู้เช่า**และ**คุณยังไม่ได้ให้ความยินยอมกับตัวเชื่อมต่อ Microsoft Graph Security Power BI (แอปพลิเคชัน) สำหรับข้อกำหนดเบื้องต้น คุณจะได้รับกล่องโต้ตอบต่อไปนี้ ตรวจสอบให้แน่ใจว่าได้เลือก "**ให้ความยินยอมในนามขององค์กรของคุณ**"

    ![ความยินยอมของผู้ดูแลระบบ](media/desktop-connect-graph-security/AdminConsent.PNG)
    
7. เมื่อคุณลงชื่อเข้าใช้แล้ว คุณจะเห็นหน้าต่างต่อไปนี้ที่ระบุว่าคุณได้รับการตรวจสอบสิทธิ์แล้ว เลือก **เชื่อมต่อ**

    ![ลงชื่อเข้าใช้แล้ว](media/desktop-connect-graph-security/SignedIn.PNG)
    
8. เมื่อคุณเชื่อมต่อสำเร็จ หน้าต่าง**ตัวนำทาง**จะปรากฏขึ้นตามมา และแสดงเอนทิตี้เช่น การแจ้งเตือน และอื่นๆ ที่พร้อมใช้งานใน[ Microsoft Graph Security API](https://aka.ms/graphsecuritydocs)สำหรับเวอร์ชันที่คุณเลือกในขั้นตอนก่อนหน้านี้ เลือกหนึ่งหรือหลายเอนทิตี้เพื่อนำเข้า และใช้ใน**Power BI Desktop** คลิก**โหลด**เพื่อดูผลลัพธ์ที่ระบุไว้ในขั้นตอนที่ 10

   ![ตารางการนำทาง](media/desktop-connect-graph-security/NavTable.PNG)
    
9. ถ้าคุณต้องการทำคิวรีขั้นสูงไปยัง Microsoft Graph Security API ให้เลือก**ระบุ URL ของ Microsoft Graph Security แบบกำหนดเองเพื่อกรองฟังก์ชัน**แสดงผลลัพธ์ ซึ่งจะช่วยให้คุณสามารถทำคิวรี[OData.Feed](https://docs.microsoft.com/power-bi/desktop-connect-odata) ไปยัง Microsoft Graph Security API ด้วยสิทธิ์ที่จำเป็นในการเข้าถึง API

   > [!NOTE]
   > ตัวอย่างของ ServiceUri ที่ถูกใช้ดังต่อไปนี้คือ`https://graph.microsoft.com/v1.0/security/alerts?$filter=Severity eq 'High'` ดู[พารามิเตอร์คิวรี ODATA ที่รองรับ Graph](https://docs.microsoft.com/graph/query-parameters)เพื่อสร้างคิวรีเพื่อกรอง สั่ง หรือเรียกคืนผลลัพธ์ส่วนใหญ่ล่าสุด

   ![Odata Feed](media/desktop-connect-graph-security/ODataFeed.PNG)
    
   เมื่อคุณเลือกฟังก์ชัน**Invoke**OData.Feed เพื่อเรียกใช้ API ซึ่งเปิดตัวแก้ไขคิวรีเพื่อให้คุณสามารถกรอง และปรับปรุงชุดข้อมูลที่คุณต้องการใช้ และจากนั้นจึงโหลดชุดข้อมูลที่ปรับแต่งแล้วนั้นลงใน Power BI Desktop

10. รูปภาพต่อไปนี้แสดงหน้าต่างผลลัพธ์สำหรับเอนทิตี้ Microsoft Graph Security ที่คุณคิวรี

   ![ผลลัพธ์](media/desktop-connect-graph-security/Result.PNG)
    

ตอนนี้คุณพร้อมที่จะใช้ข้อมูลที่นำเข้าจากตัวเชื่อมต่อ Microsoft Graph Security ใน Power BI Desktop เพื่อสร้างวิชวล รายงาน หรือโต้ตอบกับข้อมูลอื่น ๆ ที่คุณอาจต้องการเชื่อมโยงและต้องการนำเข้า เช่น สมุดงาน Excel อื่น ๆ ฐานข้อมูล หรือแหล่งข้อมูลอื่น ๆ

## <a name="next-steps"></a>ขั้นตอนถัดไป
* ดูตัวอย่าง Power BI และเทมเพลตที่ใช้ตัวเชื่อมต่อนี้ที่[ตัวอย่างรายงาน Microsoft Graph Security GitHub Power BI](https://aka.ms/graphsecuritypowerbiconnectorsamples)

* ตรวจสอบสถานการณ์ผู้ใช้บางรายและข้อมูลเพิ่มเติมที่[บล็อกโพสต์ Microsoft Graph Power BI Connector](https://aka.ms/graphsecuritypowerbiconnectorblogpost)

* มีข้อมูลหลากหลายประเภทที่คุณสามารถเชื่อมต่อโดยใช้ Power BI Desktop สำหรับข้อมูลเพิ่มเติมเกี่ยวกับแหล่งข้อมูล โปรดดูทรัพยากรต่อไปนี้:

    * [Power BI Desktop คืออะไร](desktop-what-is-desktop.md)
    * [แหล่งข้อมูลใน Power BI Desktop](desktop-data-sources.md)
    * [จัดรูปทรงและรวมข้อมูลด้วย Power BI Desktop](desktop-shape-and-combine-data.md)
    * [เชื่อมต่อกับเวิร์กบุ๊ก Excel ใน Power BI Desktop](desktop-connect-excel.md)
    * [ป้อนข้อมูลลงใน Power BI Desktop โดยตรง](desktop-enter-data-directly-into-desktop.md)

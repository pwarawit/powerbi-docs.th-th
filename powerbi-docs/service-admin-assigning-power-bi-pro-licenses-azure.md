---
title: 'เริ่มต้นใช้งานด่วน: กำหนดสิทธิ์การใช้งาน Power BI Pro ใน Azure'
description: เรียนรู้วิธีการกำหนดสิทธิ์การใช้งาน Power BI Pro เพื่อให้ผู้ใช้ของคุณสามารถเข้าถึงเนื้อหาและความสามารถทั้งหมดในบริการของ Power BI
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: quickstart
ms.date: 05/03/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: d092fc26f913028f7ce30ab6b2f860d75c5db2b7
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34294444"
---
# <a name="quickstart-assign-power-bi-pro-licenses-in-azure"></a>เริ่มต้นใช้งานด่วน: กำหนดสิทธิ์การใช้งาน Power BI Pro ใน Azure

Power BI Pro เป็นสิทธิ์การใช้งานสำหรับแต่ละบุคคล ที่ให้การเข้าถึงเนื้อหาและความสามารถทั้งหมดในบริการของ Power BI รวมถึงความสามารถในการแชร์เนื้อหาและทำงานร่วมกับผู้ใช้อื่นที่มีสิทธิ์การใช้งานแบบ Pro ได้ เฉพาะผู้ใช้แบบ Pro เท่านั้นที่สามารถเผยแพร่เนื้อหา หรือใช้เนื้อหาจากพื้นที่ทำงานจากแอป, แชร์แดชบอร์ด และสมัครสมาชิกแดชบอร์ดและรายงานได้ บทความนี้อธิบายวิธีการกำหนดสิทธิ์การใช้งาน Power BI Pro ใน Azure คุณยังสามารถ[กำหนดสิทธิ์การใช้งานใน Office 365](service-admin-assigning-power-bi-pro-licenses.md) ได้


## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

คุณต้องเป็นเจ้าของการสมัครใช้งาน Azure ที่ Power BI ใช้สำหรับการค้นหา Active Directory

คุณต้อง[ซื้อสิทธิ์การใช้งานอย่างน้อยหนึ่งสิทธิ์](service-admin-purchasing-power-bi-pro.md)ก่อนที่คุณจะเริ่ม


## <a name="assign-licenses-to-individual-user-accounts"></a>กำหนดสิทธิ์การใช้งานให้กับบัญชีผู้ใช้แต่ละราย

ทำตามขั้นตอนต่อไปนี้เพื่อกำหนดสิทธิ์การใช้งาน Power BI Pro ให้กับบัญชีผู้ใช้แต่ละราย:

1. เปิด[พอร์ทัล Azure](https://ms.portal.azure.com/#@microsoft.onmicrosoft.com/dashboard/private/39bc3cf7-31a4-43f6-954c-f2d69ca2f0) 

2. ในแถบนำทางด้านซ้าย คลิกที่ **Azure Active Directory**

    ![Azure Active Directory](media/service-admin-assigning-power-bi-pro-licenses-azure/service-assigning-power-bi-pro-licenses-01.png)

3. ภายใต้ **Azure Active Directory** เลือก**สิทธิ์การใช้งาน**

    ![สิทธิ์การใช้งาน](media/service-admin-assigning-power-bi-pro-licenses-azure/service-assigning-power-bi-pro-licenses-02.png)

4. ภายใต้**สิทธิ์การใช้งาน** เลือก**ผลิตภัณฑ์ทั้งหมด** จากนั้นเลือก **Power BI Pro** เพื่อแสดงรายการของผู้ใช้ที่มีสิทธิ์ใช้งาน

    ![สิทธิ์การใช้งาน - ผลิตภัณฑ์ทั้งหมด](media/service-admin-assigning-power-bi-pro-licenses-azure/service-assigning-power-bi-pro-licenses-03.png)

5. เลือก**กำหนด**เพื่อเพิ่มสิทธิ์การใช้งาน Power BI Pro ให้กับบัญชีผู้ใช้เพิ่มเติม

    ![กำหนดสิทธิ์การใช้งาน](media/service-admin-assigning-power-bi-pro-licenses-azure/service-assigning-power-bi-pro-licenses-04.png)


## <a name="next-steps"></a>ขั้นตอนถัดไป

ตอนนี้ คุณได้กำหนดสิทธิ์การใช้งานแล้ว เรียนรู้เพิ่มเติมเกี่ยวกับ Power BI Pro

[Power BI Pro ในองค์กรของคุณ](service-admin-power-bi-pro-in-your-organization.md)

[ค้นหาผู้ใช้ Power BI ที่มีการลงชื่อเข้าใช้](service-admin-access-usage.md)

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
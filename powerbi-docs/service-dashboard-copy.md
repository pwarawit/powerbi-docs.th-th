---
title: สร้างสำเนาของแดชบอร์ด Power BI
description: 'วิธีการทำซ้ำแดชบอร์ด Power BI '
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: fc255cda798b528acf7f782efac742872a442d41
ms.sourcegitcommit: 2aa83bd53faad6fb02eb059188ae623e26503b2a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/29/2019
ms.locfileid: "73021065"
---
# <a name="create-a-copy-of-a-dashboard-in-power-bi-service"></a>สร้างมุมมองโทรศัพท์สำหรับแดชบอร์ดใน Power BI
![แดชบอร์ด](media/service-dashboard-copy/power-bi-dashboard.png)

 มีเหตุผลมากมายว่าทำไมต้องคำสำเนาแดชบอร์ด คุณอาจต้องการทำการเปลี่ยนแปลง และทดสอบของประสิทธิภาพการทำงานกับต้นฉบับ หรือสร้างเวอร์ชันที่ต่างกันเล็กน้อยเพื่อกระจาย ให้ผู้ร่วมงาน ภูมิภาค หรือทีม บางครั้งเพื่อนร่วมงานชื่นชอบการออกแบบแดชบอร์ดของคุณ และต้องการใช้สำหรับรายงานเพื่อเสนอผู้จัดการของตน อาจะมีอีกเหตุผลหนึ่งถ้าคุณมีฐานข้อมูลใหม่ว่ามีโครงสร้างข้อมูลเดียวกันกับชนิดข้อมูลและต้องการใช้แดชบอร์ดที่คุณเคยสร้างอีกครั้ง ซึ่งสามารถทำได้เช่นกัน แต่อาจจำเป็นต้องทำงานบางอย่างใน Power BI Desktop 

แดชบอร์ดที่ถูกสร้าง(และถูกคัดลอก)โดยใช้ Power BI service และสามารถดูได้ในอุปกรณ์เคลื่อนที่ Power BI และ Power BI Embedded  แดชบอร์ดใช้งานใน Power BI Desktop ไม่ได้ 

เพื่อทำสำเนาของแดชบอร์ด คุณต้องเป็น*ผู้สร้าง*แดชบอร์ด แดชบอร์ดที่มีการแชร์กับคุณเป็นแอปไม่สามารถซ้ำกันได้

1. เปิดแดชบอร์ด
2. ที่มุมบนขวา ให้เลือก**ตัวเลือกเพิ่มเติม** (...) แล้วเลือก**ทำสำเนาแดชบอร์ด**
   
   ![เมนูจุดไข่ปลา](media/service-dashboard-copy/power-bi-dulicate.png)
3. ตั้งชื่อแดชบอร์ดแล้วเลือก**ทำสำเนา** 
   
   ![กล่องโต้ตอบทำซ้ำแดชบอร์ด](media/service-dashboard-copy/power-bi-name.png)
4. แดชบอร์ดใหม่จะถูกบันทึกในพื้นที่ทำงานเดียวกันเป็นต้นฉบับ 
   
   ![แถบแดชบอร์ด](media/service-dashboard-copy/power-bi-copied.png)

5.    เปิดแดชบอร์ดใหม่ละแก้ไขตามความจำเป็น นี่คือบางสิ่งที่คุณอาจต้องการทำต่อไป    
    a. [ย้าย เปลี่ยนชื่อ ปรับขนาด หรือแม้กั่งลบไทล์](service-dashboard-edit-tile.md)  
    b. แก้ไขรายละเอียดไทล์และไฮเปอร์ลิงก์ โดยเลือก**ตัวเลือกเพิ่มเติม** (...) ของไทล์ แล้วเลือก**แก้ไขรายละเอียด**  
    c. [เพิ่มไทล์ใหม่จากแถบเมนูแดชบอร์ด](service-dashboard-add-widget.md) (**เพิ่มไทล์**)  
    d. ปักหมุดไทล์ใหม่[จาก Q&A](service-dashboard-pin-tile-from-q-and-a.md)หรือ[จากรายงาน](service-dashboard-pin-tile-from-report.md)  
    e. เปลี่ยนชื่อแดชบอร์ด เปิดหรือปิด Q&A และตั้งค่าไทล์โฟลว์จากบานหน้าต่างการตั้งค่าแดชบอร์ด  (เลือกดรอปดาวน์**ตัวเลือกเพิ่มเติม** (... ) ของแดชบอร์ด และเลือก **การตั้งค่า**)  
    f. แชร์แดชบอร์ดของคุณโดยตรงกับเพื่อนร่วมงาน หรือเป็นส่วนหนึ่งของแอป Power BI 


## <a name="next-steps"></a>ขั้นตอนถัดไป
* [เคล็ดลับสำหรับการออกแบบแดชบอร์ด ที่ยอดเยี่ยม](service-dashboards-design-tips.md) 

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


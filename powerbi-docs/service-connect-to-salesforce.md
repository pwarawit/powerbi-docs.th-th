---
title: เชื่อมต่อกับ Salesforce ด้วย Power BI
description: Salesforce สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/30/2018
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 5cd858ad14c1a5fcf76ddf23dafdac2bb5585b10
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 09/21/2018
ms.locfileid: "46548269"
---
# <a name="connect-to-salesforce-with-power-bi"></a>เชื่อมต่อกับ Salesforce ด้วย Power BI
ด้วย Power BI คุณสามารถเชื่อมต่อกับบัญชี Salesforce.com ของคุณได้อย่างง่ายดาย สร้างการเชื่อมต่อนี้เพื่อดึงข้อมูลของคุณและมีแดชบอร์ด และรายงานที่เกี่ยวข้องที่ยึดตามข้อมูลของคุณโดยอัตโนมัติ

เชื่อมต่อกับ[ชุดเนื้อหา Salesforce](https://app.powerbi.com/getdata/services/salesforce)สำหรับ Power BI หรืออ่านเพิ่มเติมเกี่ยวกับการ[รวม Salesforce](https://powerbi.microsoft.com/integrations/salesforce)ด้วย Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-salesforce/pbi_getdata.png) 
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-salesforce/pbi_getservices.png) 
3. คลิก**Salesforce**และเลือก**รับ**  
   
   ![](media/service-connect-to-salesforce/salesforce.png)
4. เลือก**ลงชื่อเข้าใช้**เพื่อเริ่มต้นขั้นตอนการเข้าสู่ระบบ
   
    ![](media/service-connect-to-salesforce/dialog.png)
5. เมื่อมีข้อความถาม ให้ใส่ข้อมูลประจำตัวของ Salesforce คลิก**อนุญาต**เพื่อให้ Power BI สามารถเข้าถึงข้อมูล Salesforce พื้นฐานและข้อมูลของคุณ
   
   ![](media/service-connect-to-salesforce/sf_authorize.png)
6. กำหนดค่าสิ่งที่คุณต้องการนำเข้าลงใน Power BI โดยใช้ตัวเลือกรายการแบบดร๊อปดาวน์
   
   * **แดชบอร์ด**
     
     เลือกแดชบอร์ดที่กำหนดไว้ล่วงหน้าโดยยึดตาม persona (เช่น**ผู้จัดการฝ่ายขาย**) แดชบอร์ดเหล่านี้นำชุดข้อมูลมาตรฐานเฉพาะจาก Salesforce และจะไม่รวมเขตข้อมูลแบบกำหนดเอง
     
     ![](media/service-connect-to-salesforce/pbi_salesforcechooserole.png)
   * **รายงาน**
     
     เลือกอย่างน้อยหนึ่งรายงานแบบกำหนดเองจากบัญชี Salesforce ของคุณ รายงานเหล่านี้จะตรงกับมุมมองของคุณใน Salesforce และสามารถรวมข้อมูลจากเขตข้อมูลแบบกำหนดเองหรือวัตถุ
     
     ![](media/service-connect-to-salesforce/pbi_salesforcereports.png)
     
     ถ้าคุณไม่เห็นรายงานใดๆ ให้เพิ่มหรือสร้าบัญชี Salesforce ของคุณ แล้วลองเชื่อมต่ออีกครั้ง
7. คลิก **เชื่อมต่อ** เพื่อเริ่มกระบวนการนำเข้า ในระหว่างการนำเข้า คุณเห็นการแจ้งเตือนที่แสดงว่าการนำเข้ากำลังดำเนินการอยู่ เมื่อการนำเข้าเสร็จสมบูรณ์ คุณจะเห็นแดชบอร์ด รายงาน และชุดข้อมูลสำหรับข้อมูล Salesforce ของที่คุณแสดงอยู่ในบานหน้าต่างนำทางทางด้านซ้าย
   
   ![](media/service-connect-to-salesforce/pbi_getdatasalesforcedash.png)

คุณสามารถปรับเปลี่ยนแดชบอร์ดนี้เพื่อแสดงข้อมูลของคุณด้วยวิธีใดก็ตามที่คุณต้องการ คุณสามารถถามคำถาม Q&A หรือคลิกที่ไทล์เพื่อ[เปิดรายงานด้านใน](consumer/end-user-tiles.md)และ[เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [เปลี่ยนไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ด <<<<<<< ส่วนหัว
* [เลือกไทล์](consumer/end-user-tiles.md)เมื่อต้องเปิดรายงานพื้นฐาน =======
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานด้านใน
>>>>>>> 66fe62d8f200efd9cfeb465eeb5f370dbbaa63be
* แม้ว่าชุดข้อมูลของคุณจะถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้**รีเฟรชเดี๋ยวนี้**

## <a name="system-requirements-and-considerations"></a>ข้อกำหนดของระบบและข้อควรพิจารณา
- เชื่อมต่อกับบัญชีผลิตภัณฑ์ Salesforce ที่สามารถเข้าถึง API ที่เปิดใช้งาน
- สิทธิ์ที่มอบให้กับแอป Power BI ในระหว่างการเข้าสู่ระบบ
- บัญชีมีการเรียกใช้ API เพียงพอที่สามารถใช้งานดึงและรีเฟรชข้อมูล
- โทเค็นรับรองตัวตนที่จำเป็นกับการรีเฟรช ให้ทำให้แน่ใจว่า คุณมีชุดข้อมูล 5 ชุดหรือน้อยกว่า ชุดข้อมูล Salesforce ที่ถูกนำเข้า ด้วยที่ Salesforce มีขีดจำกัดของโทเค็นการรับรองความถูกต้อง 5 ตัวสำหรับแอปพลิเคชัน
- Salesforce Reports API มีข้อจำกัดที่สนับสนุนสูงสุด 2,000 แถวข้อมูล


## <a name="troubleshooting"></a>การแก้ไขปัญหา
ถ้าคุณพบข้อผิดพลาดใดๆ โปรดตรวจสอบความต้องการด้านบน โปรดทราบว่าความสามารถในการเข้าสู่ระบบแบบโดเมนแบบกำหนดเองหรือแบบ sandbox ยังไม่รองรับในขณะนี้

### <a name="unable-to-connect-to-the-remote-server-message"></a>ข้อความ “ไม่สามารถเชื่อมต่อกับเซิร์ฟเวอร์ระยะไกลได้”

ถ้าคุณได้รับข้อความ "ไม่สามารถเชื่อมต่อกับเซิร์ฟเวอร์ระยะไกล" เมื่อพยายามเชื่อมต่อกับบัญชี Salesforce ของคุณ ให้ดูโซลูชันนี้บนฟอรั่ม Outsystems: [ข้อความข้อผิดพลาดการลงชื่อเข้าระบบตัวเชื่อมต่อ Salesforce: ไม่สามารถเชื่อมต่อกับเซิร์ฟเวอร์ระยะไกลได้](https://www.outsystems.com/forums/Forum_TopicView.aspx?TopicId=17674&TopicName=log-in-error-message-unable-to-connect-to-the-remote-server&)


## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI คืออะไร](power-bi-overview.md)

[รับข้อมูล](service-get-data.md)


---
title: เชื่อมต่อกับ Salesforce ด้วย Power BI
description: Salesforce สำหรับ Power BI
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/30/2019
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: bc562c1c75f72e0ada23580aa0698f6463c129bb
ms.sourcegitcommit: 88e2a80b95b3e735689e75da7c35d84e24772e13
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/07/2019
ms.locfileid: "66814305"
---
# <a name="connect-to-salesforce-with-power-bi"></a>เชื่อมต่อกับ Salesforce ด้วย Power BI
ด้วย Power BI คุณสามารถเชื่อมต่อกับบัญชี Salesforce.com ของคุณได้อย่างง่ายดาย ด้วยการเชื่อมต่อนี้ คุณสามารถค้นคืนข้อมูล Salesforce ของคุณ และมีแดชบอร์ดและรายงานโดยอัตโนมัติที่ให้มา

อ่านเพิ่มเติมเกี่ยวกับ[การรวม Salesforce ](https://powerbi.microsoft.com/integrations/salesforce)ด้วย Power BI

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
1. ใน Power BI เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-salesforce/pbi_getdata.png) 
2. ในกล่อง**บริการ** เลือก**รับ**
   
   ![](media/service-connect-to-salesforce/pbi_getservices.png) 
3. เลือก**วิเคราะห์สำหรับ Salesforce**และเลือก**รับ**  
   
   ![](media/service-connect-to-salesforce/salesforce.png)
4. เลือก**ลงชื่อเข้าใช้**เพื่อเริ่มการลงชื่อเข้าใช้ในโฟลว์
   
    ![](media/service-connect-to-salesforce/dialog.png)
5. เมื่อมีข้อความถาม ให้ใส่ข้อมูลประจำตัวของ Salesforce คลิก**อนุญาต**และอนุญาตให้ Power BI เข้าถึงข้อมูล Salesforce พื้นฐานและข้อมูลของคุณ
   
   ![](media/service-connect-to-salesforce/sf_authorize.png)
6. กำหนดค่าสิ่งที่คุณต้องการนำเข้าลงใน Power BI โดยใช้ตัวเลือกรายการเลือกแบบดึงลง
   
   * **แดชบอร์ด**
     
     เลือกแดชบอร์ดที่กำหนดไว้ล่วงหน้าโดยยึดตาม persona (เช่น**ผู้จัดการฝ่ายขาย**) แดชบอร์ดเหล่านี้จะค้นคืนชุดข้อมูลมาตรฐานเฉพาะจาก Salesforce และจะไม่รวมเขตข้อมูลแบบกำหนดเอง
     
     ![](media/service-connect-to-salesforce/pbi_salesforcechooserole.png)
   * **รายงาน**
     
     เลือกอย่างน้อยหนึ่งรายงานแบบกำหนดเองจากบัญชี Salesforce ของคุณ รายงานเหล่านี้ตรงกับมุมมองของคุณใน Salesforce และสามารถรวมข้อมูลจากเขตข้อมูลแบบกำหนดเองหรือวัตถุ
     
     ![](media/service-connect-to-salesforce/pbi_salesforcereports.png)
     
     ถ้าคุณไม่เห็นรายงานใดๆ ให้เพิ่มหรือสร้าบัญชี Salesforce ของคุณ แล้วลองเชื่อมต่ออีกครั้ง

7. คลิก **เชื่อมต่อ** เพื่อเริ่มกระบวนการนำเข้า ในระหว่างการนำเข้า คุณเห็นการแจ้งเตือนที่แสดงว่าการนำเข้ากำลังดำเนินการอยู่ เมื่อการนำเข้าเสร็จสมบูรณ์ คุณเห็นแดชบอร์ด รายงาน และชุดข้อมูลสำหรับข้อมูล Salesforce ของที่คุณแสดงอยู่ในพื้นที่นำทางด้านซ้ายมือ
   
   ![](media/service-connect-to-salesforce/pbi_getdatasalesforcedash.png)

คุณสามารถปรับเปลี่ยนแดชบอร์ดเพื่อแสดงข้อมูลของคุณด้วยวิธีที่คุณต้องการ คุณสามารถถามคำถาม Q&A หรือ [เลือกไทล์](consumer/end-user-tiles.md) เพื่อเปิดรายงานด้านในและ[แก้ไข หรือลบไทล์ในแดชบอร์ดออก](service-dashboard-edit-tile.md)

**ฉันต้องทำอะไรตอนนี้**

* ลอง[ถามคำถามในกล่อง Q&A](consumer/end-user-q-and-a.md)ที่ด้านบนของแดชบอร์ด
* [แก้ไข หรือลบไทล์](service-dashboard-edit-tile.md)ในแดชบอร์ดออก
* [เลือกไทล์](service-dashboard-tiles.md)เพื่อเปิดรายงานด้านใน
* แม้ว่าชุดข้อมูลของคุณถูกกำหนดให้รีเฟรชรายวัน แต่คุณสามารถปรับเปลี่ยนกำหนดการรีเฟรช หรือลองรีเฟรชตามความต้องการได้โดยใช้ **รีเฟรชตอนนี้**

## <a name="system-requirements-and-considerations"></a>ข้อกำหนดของระบบและข้อควรพิจารณา

- เชื่อมต่อกับบัญชีผลิตภัณฑ์ Salesforce ที่สามารถเข้าถึง API ที่เปิดใช้งาน

- สิทธิที่มอบให้กับแอป Power BI ในระหว่างการลงชื่อเข้าใช้

- บัญชีมีการเรียกใช้ API เพียงพอที่สามารถใช้งานดึงและรีเฟรชข้อมูล

- โทเค็นรับรองตัวตนที่จำเป็นกับการรีเฟรช Salesforce มีขีดจำกัดของโทเค็นรับรองตัวตนห้าโทเค็นต่อแอปพลิเคชัน ดังนั้นเพื่อให้แน่ใจว่า คุณมีชุดข้อมูล Salesforce ที่นำเข้า 5 ชุดหรือน้อยกว่า

- Salesforce Reports API มีข้อจำกัดที่สนับสนุนสูงสุด 2,000 แถวข้อมูล


## <a name="troubleshooting"></a>การแก้ไขปัญหา

ถ้าคุณพบข้อผิดพลาดใด ๆ โดยบังเอิญ ให้ตรวจสอบความต้องการด้านบน 

ขณะนี้ยังไม่รองรับการลงชื่อเข้าใช้บนโดเมนระบบทดสอบหรือแบบกำหนดเอง

### <a name="unable-to-connect-to-the-remote-server-message"></a>ข้อความ “ไม่สามารถเชื่อมต่อกับเซิร์ฟเวอร์ระยะไกลได้”

ถ้าคุณได้รับข้อความ "ไม่สามารถเชื่อมต่อกับเซิร์ฟเวอร์ระยะไกล" เมื่อพยายามเชื่อมต่อกับบัญชี Salesforce ของคุณ ให้ดูโซลูชันนี้บนฟอรั่มต่อไปนี้: [ข้อความข้อผิดพลาดการลงชื่อเข้าใช้ระบบตัวเชื่อมต่อ Salesforce: ไม่สามารถเชื่อมต่อกับเซิร์ฟเวอร์ระยะไกลได้](https://www.outsystems.com/forums/Forum_TopicView.aspx?TopicId=17674&TopicName=log-in-error-message-unable-to-connect-to-the-remote-server&)


## <a name="next-steps"></a>ขั้นตอนถัดไป
[Power BI คืออะไร](power-bi-overview.md)

[แหล่งข้อมูลสำหรับบริการ Power BI](service-get-data.md)


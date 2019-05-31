---
title: เชื่อมต่อกับ GitHub ด้วย Power BI
description: GitHub สำหรับ Power BI
author: maggiesMSFT
manager: kfile
ms.reviewer: sarinas
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: b0f2bd53f1d8b82b70072446723c2ca3723eeacd
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: th-TH
ms.lasthandoff: 05/29/2019
ms.locfileid: "65608434"
---
# <a name="connect-to-github-with-power-bi"></a>เชื่อมต่อกับ GitHub ด้วย Power BI
บทความนี้แนะนำคุณเกี่ยวกับการดึงข้อมูลของคุณจากบัญชี GitHub ของคุณกับแอป Power BI เทมเพลต แอปเทมเพลสร้างพื้นที่ทำงานกับแดชบอร์ด ชุดของรายงาน และชุดข้อมูลเพื่อให้คุณสามารถสำรวจข้อมูล GitHub ของคุณ แอป GitHub สำหรับ Power BI แสดงข้อมูลเชิงลึกที่เก็บ GitHub ของคุณ เรียกว่า repo กับข้อมูลการจัดสรร ปัญหา คำขอดึงข้อมูล และผู้ใช้ที่ใช้งานอยู่

หลังจากที่คุณติดตั้งแอปเทมเพล คุณสามารถเปลี่ยนแดชบอร์ดและรายงาน จากนั้น คุณสามารถแจกจ่ายเป็นแอปให้เพื่อนร่วมงานในองค์กรของคุณ

เชื่อมต่อกับตัว[ปเทมเพล GitHub](https://app.powerbi.com/getdata/services/github)หรืออ่านเพิ่มเติมเกี่ยวกับการ[รวม GitHub](https://powerbi.microsoft.com/integrations/github)ด้วย Power BI

คุณยังสามารถลองการ[บทช่วยสอน GitHub](service-tutorial-connect-to-github.md)ได้ ซึ่งถูกติดตั้งข้อมูล GitHub จริงเกี่ยวกับ repo สาธารณะสำหรับเอกสารประกอบ Power BI

>[!NOTE]
>แอปเทมเพลจำเป็นต้องมีบัญชี GitHub ที่สามารถเข้าถึง repo รายละเอียดเพิ่มเติมเกี่ยวกับข้อกำหนดด้านล่าง

## <a name="how-to-connect"></a>วิธีการเชื่อมต่อ
[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]
   
3. เลือก**GitHub** \> **รับทันที**
4. ใน**ติดตั้งแอป Power BI นี้ใช่ไหม**เลือก**ติดตั้ง**
4. ในการ**แอ**บานหน้าต่าง เลือกแบบ**GitHub**ไทล์

    ![ไทล์ GitHub ใน Power BI](media/service-connect-to-github/power-bi-github-tile.png)

6. ใน**เริ่มต้นใช้งานแอปของคุณใหม่**เลือก**เชื่อมต่อข้อมูล**

    ![เริ่มต้นใช้งานแอปใหม่ของคุณ](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

5. ป้อนชื่อที่เก็บและเจ้าของที่เก็บ Repo ดูรายละเอียดที่ [การค้นหาพารามิเตอร์เหล่านี้](#FindingParams) ด้านล่าง
   
    ![ชื่อ Repo GitHub ใน Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect.png)

5. ใส่ข้อมูลประจำตัว GitHub ของคุณ (ขั้นตอนนี้อาจถูกข้ามไปถ้าคุณกำลังอยู่แล้วลงชื่อเข้าใช้ ด้วยเบราว์เซอร์ของคุณ) 
6. สำหรับ **วิธีการรับรองความถูกต้อง** ให้เลือก **oAuth2** \> **ลงชื่อเข้าใช้** 
7. ทำตามหน้าจอการรับรองความถูกต้อง GitHub ให้สิทธิ์ GitHub สำหรับสิทธิ์ของแอปเทมเพลต Power BI ไปยังข้อมูล GitHub
   
   ![อนุญาต power BI GitHub](media/service-connect-to-github/github_authorize.png)
   
    Power BI เชื่อมต่อกับ GitHub และข้อมูลของคุณ  ข้อมูลจะถูกรีเฟรชวันละหนึ่งครั้ง หลังจาก Power BI นำเข้าข้อมูล คุณเห็นเนื้อหาของพื้นที่ทำงาน GitHub ของคุณใหม่

## <a name="modify-and-distribute-your-app"></a>ปรับเปลี่ยน และแจกจ่ายแอปของคุณ

คุณติดตั้งแอปเทมเพล GitHub ซึ่งหมายความว่า คุณจะสร้างพื้นที่ทำงานแอป GitHub ในพื้นที่ทำงาน คุณสามารถเปลี่ยนรายงานและแดชบอร์ด และแจกจ่ายเป็นแอ*แอ*ให้เพื่อนร่วมงานในองค์กรของคุณได้ 

1. เลือกลูกศรถัดจากชื่อพื้นที่ทำงานในแถบนำทางด้านซ้าย คุณเห็นพื้นที่ทำงานประกอบด้วยแดชบอร์ดและรายงาน

    ![ในบานหน้าต่างนำทางด้านซ้าย](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav-expanded.png)

8. เลือกใหม่[แดชบอร์ด GitHub](https://powerbi.microsoft.com/integrations/github)    
    ![แดชบอร์ด GitHub ใน Power BI](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-new-dashboard.png)

3. เมื่อต้องดูเนื้อหาทั้งหมดของ GitHub พื้นที่ทำงานใหม่ ในแถบนำทางด้านซ้าย เลือก**พื้นที่ทำงาน** > **GitHub**
 
   ![พื้นที่ทำงาน GitHub ในบานหน้าต่างนำทางด้านซ้าย](media/service-connect-to-github/power-bi-github-left-nav.png)

    มุมมองนี้คือ รายการเนื้อหาสำหรับพื้นที่ทำงาน ในมุมขวาบน คุณเห็น**อัปเดตแอปฯ** เมื่อคุณพร้อมที่จะแจกจ่ายแอปของคุณให้เพื่อนร่วมงานของคุณ ที่อยู่ที่คุณจะเริ่มต้น 

    ![รายการเนื้อหา GitHub](media/service-connect-to-github/power-bi-github-content-list.png)

2. เลือก**รายงาน**และ**ชุดข้อมูล**เพื่อดูองค์ประกอบอื่น ๆ ในพื้นที่ทำงาน

    อ่านเกี่ยวกับ[แจกจ่ายแอ](service-create-distribute-apps.md)ให้เพื่อนร่วมงานของคุณ

## <a name="whats-included-in-the-app"></a>มีอะไรบ้างในแอป
ข้อมูลต่อไปนี้จะพร้อมใช้งานจาก GitHub ใน Power BI     

| ชื่อตาราง | คำอธิบาย |
| --- | --- |
| การสนับสนุน |ตารางจัดสรรให้เพิ่มทั้งหมด ลบ และยอมรับที่สร้าง โดยผู้ให้การสนับสนุนรวมต่อสัปดาห์ ผู้สนับสนุน 100 อันดับแรกถูกรวมไว้ |
| ปัญหา |รายการปัญหาทั้งหมดสำหรับ repo ที่เลือก และประกอบด้วยการคำนวณเช่นเวลาเฉลี่ยและเวลารวมเพื่อปิดข้อปัญหา รวมปัญหาที่เปิด รวมปัญหาที่ปิด ตารางนี้จะว่างเปล่าเมื่อไม่มีปัญหาใน repo |
| คำขอดึงข้อมูล |ตารางนี้ประกอบด้วย Pull Requests ทั้งหมดดึงของ repo และบุคคลที่ขอดึง ซึ่งยังประกอบด้วยคำนวณคำขอดึงข้อมูลเปิด ปิด และผลรวมจำนวน ระยะเวลาของ pull คำขอ และการร้องขอดึงข้อมูลเฉลี่ยใช้เวลานานขึ้น ตารางนี้จะว่างเปล่าเมื่อไม่มีปัญหาใน repo |
| ผู้ใช้ |ตารางนี้มีรายการของผู้ใช้ GitHub หรือผู้สนับสนุนที่ได้ทำการจัดสรร ที่เก็บข้อมูลปัญหา หรือได้รับการแก้ไขคำขอดึงข้อมูลสำหรับ repo ที่เลือก |
| หลักเป้าหมาย |มีเหตุการณ์สำคัญทั้งหมดสำหรับ repo ที่เลือก |
| DateTable |ตารางนี้ประกอบด้วยวันที่จากวันนี้ และปีในอดีตที่ช่วยให้คุณสามารถวิเคราะห์ข้อมูล GitHub ของคุณตามวัน |
| ContributionPunchCard |ตารางนี้สามารถใช้เป็นการ์ดความสามารถจัดสรรสำหรับ repo ที่เลือก ซึ่งแสดงยอมรับ โดยวันของสัปดาห์และชั่วโมงของวัน ตารางนี้ไม่ได้รับการเชื่อมต่อกับตารางอื่นในแบบจำลอง |
| RepoDetails |ตารางนี้มีรายละเอียดสำหรับ repo ที่เลือก |

## <a name="system-requirements"></a>ความต้องการของระบบ
* บัญชีผู้ใช้ GitHub ที่มีสิทธิ์เข้าถึง repo  
* สิทธิ์ที่มอบให้กับ Power BI สำหรับแอป GitHub ในระหว่างการเข้าสู่ระบบครั้งแรก ดูรายละเอียดด้านล่างในการยกเลิกการเข้าถึง  
* มีการเรียกใช้ API เพียงพอที่สามารถดึงและรีเฟรชข้อมูล  

### <a name="de-authorize-power-bi"></a>ยกเลิกอนุญาต Power BI
เมื่อต้องการยกเลิกอนุญาต Power BI จากการเชื่อมต่อกับ repo GitHub ของคุณ คุณสามารถยกเลิกการเข้าถึงใน GitHub ดู[ความช่วยเหลือ GitHub](https://help.github.com/articles/keeping-your-ssh-keys-and-application-access-tokens-safe/#reviewing-your-authorized-applications-oauth)หัวข้อสำหรับรายละเอียด

<a name="FindingParams"></a>
## <a name="finding-parameters"></a>การค้นหาพารามิเตอร์
คุณสามารถกำหนดเจ้าของและที่เก็บ โดยด repo ใน GitHub เอง

![ชื่อ repo และเจ้าของ](media/service-connect-to-github/github_ownerrepo.png)

ส่วนแรกของ "Azure" คือเจ้าของ และส่วนสอง "azure-sdk-for-php" เป็นส่วนเก็บข้อมูล  คุณเห็นสิ่งเหล่านี้เหมือนกันสองรายการใน URL repo

    <https://github.com/Azure/azure-sdk-for-php> .

## <a name="troubleshooting"></a>การแก้ไขปัญหา
ถ้าจำเป็น คุณสามารถตรวจสอบข้อมูลประจำตัว GitHub ของคุณ  

1. ในหน้าต่างเบราว์เซอร์อื่น ไปเว็บไซต์ GitHub และลงชื่อเข้าใช้ GitHub คุณสามารถเห็นว่าคุณกำลังเข้าสู่ระบบ ที่มุมขวาบนของไซต์ GitHub    
2. ใน GitHub นำทางไปยัง URL ของ repo ที่คุณวางแผนที่จะเข้าถึงใน Power BI ตัวอย่างเช่น: https://github.com/dotnet/corefx  
3. กลับไปที่ Power BI ลองเชื่อมต่อกับ GitHub ในกล่องโต้ตอบการกำหนดค่า GitHub ให้ใช้ชื่อของ repo และเจ้าของ repo สำหรับ repo ที่เดียวกัน  

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [บทช่วยสอน: เชื่อมต่อกับ repo GitHub ด้วย Power BI](service-tutorial-connect-to-github.md)
* [สร้างพื้นที่ทำงานใหม่ใน Power BI](service-create-the-new-workspaces.md)
* [ติดตั้งและใช้แอปฯใน Power BI](consumer/end-user-apps.md)
* [เชื่อมต่อกับแอป Power BI สำหรับบริการภายนอก](service-connect-to-services.md)
* มีคำถามหรือไม่ [ลองถามชุมชน Power BI](http://community.powerbi.com/)


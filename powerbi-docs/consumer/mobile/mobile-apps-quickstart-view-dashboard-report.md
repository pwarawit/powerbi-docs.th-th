---
title: 'การเริ่มต้นใช้งานด่วน: สำรวจแดชบอร์ดและรายงานในแอปสำหรับอุปกรณ์เคลื่อนที่'
description: ในการเริ่มต้นใช้งานด่วนนี้ คุณสำรวจแดชบอร์ดและรายงานตัวอย่างได้ในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: quickstart
ms.date: 11/16/2018
ms.author: maggies
ms.openlocfilehash: 6d5d543c3654da13592b24f4c70bc964eb7bddff
ms.sourcegitcommit: 46f1ba3f972f6e64bce05ad0fd527b27c49aedd6
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/20/2018
ms.locfileid: "52157275"
---
# <a name="quickstart-explore-dashboards-and-reports-in-the-power-bi-mobile-apps"></a>การเริ่มต้นใช้งานด่วน: แดชบอร์ดและรายงานในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
ในการเริ่มต้นใช้งานด่วนนี้ คุณสำรวจแดชบอร์ดและรายงานตัวอย่างได้ในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่บนโทรศัพท์ Android นอกจากนี้ คุณสามารถทำตามขั้นตอนในแอปสำหรับอุปกรณ์เคลื่อนอื่น ๆ ได้ 

นำไปใช้กับ:

| ![iPhone](./media/mobile-apps-quickstart-view-dashboard-report/iphone-logo-30-px.png) | ![iPad](./media/mobile-apps-quickstart-view-dashboard-report/ipad-logo-30-px.png) | ![Android](./media/mobile-apps-quickstart-view-dashboard-report/android-logo-30-px.png) | ![อุปกรณ์ Windows 10](./media/mobile-apps-quickstart-view-dashboard-report/win-10-logo-30-px.png) |
|:--- |:--- |:--- |:--- |
| iPhone | iPad | Android | Windows 10 |

แดชบอร์ดเป็นพอร์ทัลสำหรับวงจรชีวิตและกระบวนการของบริษัทของคุณ แดชบอร์ดคือภาพรวมหรือสถานที่เดียวที่สามารถตรวจสอบสถานะปัจจุบันของธุรกิจได้ รายงาน คือ มุมมองแบบโต้ตอบของข้อมูลของคุณที่มีการแสดงผลด้วยภาพที่แสดงการค้นพบและข้อมูลเชิงลึกแตกต่างจากข้อมูลนั้น 

![รายงานในโหมดแนวนอน](././media/mobile-apps-quickstart-view-dashboard-report/power-bi-android-quickstart-report.png)

## <a name="prerequisites"></a>ข้อกำหนดเบื้องต้น

### <a name="sign-up-for-power-bi"></a>ลงทะเบียนใช้งาน Power BI
ถ้าคุณไม่ได้ลงทะเบียน Power BI ให้[ลงทะเบียนรุ่นทดลองใช้ฟรี](https://app.powerbi.com/signupredirect?pbi_source=web)ก่อนที่คุณจะเริ่มต้นใช้งาน

### <a name="install-the-power-bi-for-android-app"></a>ติดตั้ง Power BI สำหรับแอป Android
[ดาวน์โหลด Power BI สำหรับแอป Android](http://go.microsoft.com/fwlink/?LinkID=544867)จาก Google Play

Power BI ทำงานบนอุปกรณ์ Android ที่ใช้ระบบปฏิบัติการ Android 5.0 หรือใหม่กว่า เพื่อตรวจสอบอุปกรณ์ของคุณ ไปที่**การตั้งค่า** > **เกี่ยวกับ** > **เวอร์ชันของ Android**

### <a name="download-the-retail-analysis-sample"></a>ดาวน์โหลดตัวอย่างการวิเคราะห์ร้านค้าปลีก
ขั้นตอนแรกในการเริ่มต้นใช้งานด่วน คือ การดาวน์โหลดตัวอย่างการวิเคราะห์การค้าปลีกทางการขายในบริการของ Power BI

1. เปิดบริการ Power BI ในเบราว์เซอร์ของคุณ (app.powerbi.com) และลงชื่อเข้าใช้

1. เลือกที่ไอคอนนำทางส่วนกลาง เพื่อเปิดการนำทางด้านซ้าย

    ![ไอคอนนำทางส่วนกลาง](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-android-quickstart-global-nav-icon.png)

2. ในบานหน้าต่างนำทางด้านซ้าย เลือก **พื้นที่ทำงาน** > **พื้นที่ทำงานของฉัน**

    ![พื้นที่ทำงานของฉัน](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-android-quickstart-my-workspace.png)

3. ที่มุมล่างซ้าย เลือก**รับข้อมูล**
   
    ![รับข้อมูล](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-get-data.png)

3. บนหน้า รับข้อมูล เลือกไอคอน**ตัวอย่าง**
   
   ![ไอคอนตัวอย่าง](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-samples-icon.png)

4. เลือก**ตัวอย่างการวิเคราะห์ร้านค้าปลีก**
 
    ![ตัวอย่างการวิเคราะห์การค้าปลีก](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-rs.png)
 
8. เลือก **เชื่อมต่อ**  
  
   ![ตัวอย่างการวิเคราะห์ด้านการขายปลีก - เชื่อมต่อ](./media/mobile-apps-quickstart-view-dashboard-report/retail16.png)
   
5. Power BI นำเข้าตัวอย่าง เพิ่มแดชบอร์ดใหม่ รายงาน และชุดข้อมูลลงในพื้นที่ทำงานของฉัน
   
   ![แดชบอร์ดตัวอย่างการวิเคราะห์การค้าปลีก](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-service-opportunity-sample.png)

ตอนนี้คุณก็พร้อมที่จะดูตัวอย่างบนอุปกรณ์ Android ของคุณแล้ว

## <a name="view-a-dashboard-on-your-android-device"></a>ดูแดชบอร์ดบนอุปกรณ์ Android ของคุณ
1. บนอุปกรณ์ Android ของคุณ เปิดแอป Power BI แล้วลงชื่อเข้าใช้ด้วยข้อมูลประจำตัวของบัญชีผู้ใช้ Power BI เดียวกันกับที่คุณใช้ในบริการ Power BI ในเบราว์เซอร์

1.  แตะปุ่มการนำทางส่วนกลาง ![ปุ่มการนำทางส่วนกลาง](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-iphone-global-nav-button.png).

2.  แตะ**พื้นที่ทำงาน** > **พื้นที่ทำงานของฉัน**

    ![พื้นที่ทำงานของฉัน](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-android-quickstart-workspaces.png)

3. แตะที่แดชบอร์ดตัวอย่างการวิเคราะห์ร้านค้าปลีกเพื่อเปิดขึ้น
 
    ![แดชบอร์ดในพื้นที่ทำงานของฉัน](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-android-quickstart-open-retail.png)
   
    สัญกรณ์ที่ด้านล่างของชื่อแดชบอร์ด (ในกรณีนี้คือตัวอักษร "C") แสดงวิธีการจัดประเภทข้อมูลในแต่ละแดชบอร์ด อ่านเพิ่มเติมเกี่ยวกับ[การจัดประเภทข้อมูลใน Power BI](../../service-data-classification.md)

    แดชบอร์ด Power BI จะมีลักษณะแตกต่างกันเล็กน้อยบน Android ของคุณ ไทล์ทั้งหมดจะปรากฏในขนาดเท่ากัน และถูกจัดเรียงทีละอันจากบนลงล่าง

4. แตะที่ไอคอนเครื่องหมายดอกจัน ![ไอคอนเครื่องหมายดอกจันรายการโปรด](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-android-quickstart-favorite-icon.png) ในแถบชื่อเรื่องเพื่อทำให้แดชบอร์ดของคุณเป็นรายการโปรด

    เมื่อคุณทำรายการโปรดในแอปสำหรับอุปกรณ์เคลื่อนที่เป็นรายการโปรด จะเป็นรายการโปรดในบริการ Power BI และในทางกลับกันด้วย

4. เลื่อนลงแล้วแตะแผนภูมิเส้นทึบ "ยอดขายของปีนี้ ยอดขายของปีที่แล้ว"

    ![แตะไทล์เพื่อไปยังโหมดโฟกัส](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-android-quickstart-tap-tile-fave.png)

    ไทล์จะเปิดขึ้นในโหมดโฟกัส

7. ในโหมดโฟกัส แตะ เม.ย.ในแผนภูมิ คุณจะเห็นค่าสำหรับเดือนเมษายนที่ด้านบนของแผนภูมิ

    ![ไทล์ในโหมดโฟกัส](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-android-quickstart-tile-focus.png)

8. แตะไอคอนรายงาน ![ไอคอนรายงาน](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-android-quickstart-report-icon.png) ที่มุมขวาบน รายงานที่เกี่ยวข้องกับไทล์นี้จะเปิดขึ้นในโหมดแนวนอน

    ![รายงานในโหมดแนวนอน](././media/mobile-apps-quickstart-view-dashboard-report/power-bi-android-quickstart-report.png)

9. แตะฟองสีเหลือง "Juniors 040 -" ในแผนภูมิฟอง คุณเห็นวิธีการไฮไลท์ค่าที่เกี่ยวข้องในแผนภูมิอื่น ๆ หรือไม่? 

    ![ไฮไลท์ค่าในรายงาน](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-android-quickstart-cross-highlight.png)

10. ปัดขึ้นเพื่อดูแถบเครื่องมือที่ด้านล่างและแตะไอคอนรูปดินสอ

    ![แตะที่ดินสอ](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-android-quickstart-tap-pencil.png)

11. แตะไอคอนหน้ายิ้มในแถบเครื่องมือใส่คำอธิบายประกอบ และเพิ่มบางหน้ายิ้มไปยังหน้ารายงานของคุณ
 
    ![ใส่คำอธิบายประกอบหน้า](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-android-quickstart-annotate.png)

12. แตะ**แชร์**ที่มุมบนขวา

1. กรอกข้อมูลอีเมลของของพวกเขาและเพิ่มข้อความ ถ้าคุณต้องการ  

    ![ข้อความอีเมลใหม่พร้อมสแนปช็อตและลิงก์](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-android-quickstart-send-snapshot.png)

    คุณสามาราถแชร์สแนปช็อตนี้กับใครก็ได้ ทั้งภายในและภายนอกองค์กรของคุณ หาผู้คนที่คุณแชร์อยู่ในองค์กรของคุณและมีบัญชี Power BI เป็นของตนเอง บุคคลเหล่านี้จะสามารถเปิดรายงานตัวอย่างการวิเคราะห์ร้านค้าปลีกได้ด้วยเช่นกัน

## <a name="clean-up-resources"></a>เพิ่มพื้นที่ทรัพยากร

หลังจากที่คุณเสร็จการเริ่มต้นด่วนนี้ คุณสามารถลบแดชบอร์ด, รายงาน และชุดข้อมูลตัวอย่างการวิเคราะห์ด้านการขายปลีก ถ้าคุณต้องการ

1. เปิดบริการ Power BI (app.powerbi.com) และลงชื่อเข้าสู่ระบบ

2. ในบานหน้าต่างนำทางด้านซ้าย เลือก**พื้นที่ทำงาน** > **พื้นที่ทำงานของฉัน**

    คุณสังเกตเห็นดาวสีเหลืองที่ระบุว่าเป็นรายการโปรดหรือไม่?

3. บนแท็บ**แดชบอร์ด** เลือกไอคอนถังขยะ**ลบ**ถัดจากแดชบอร์ดการวิเคราะห์ร้านค้าปลีก

    ![เลือกไอคอนลบ](./media/mobile-apps-quickstart-view-dashboard-report/power-bi-android-quickstart-delete-retail.png)

4. เลือกแท็บ**รายงาน** และทำขั้นตอนเดียวกันนี้สำหรับรายงานการวิเคราะห์ร้านค้าปลีก

5. เลือกแท็บ**ชุดข้อมูล** และทำสิ่งเดียวกันสำหรับชุดข้อมูลการวิเคราะห์ด้านการขายปลีก


## <a name="next-steps"></a>ขั้นตอนถัดไป

ในการเริ่มต้นใช้งานด่วนนี้ คุณสำรวจแดชบอร์ดและรายงานตัวอย่างได้ในอุปกรณ์ Android ของคุณ อ่านเพิ่มเติมเกี่ยวกับการทำงานในบริการ Power BI 

> [!div class="nextstepaction"]
> [เริ่มต้นใช้งานด่วน - ทำความรู้จักบริการของ Power BI](../end-user-experience.md)


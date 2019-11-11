---
title: รับการแจ้งเตือนในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
description: ศูนย์การแจ้งเตือนรวบรวมข้อมูล Power BI ของคุณที่เกี่ยวข้อง และส่งข้อมูลนั้นไปยังอุปกรณ์เคลื่อนที่ของคุณ
author: KesemSharabi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 01/16/2018
ms.author: mshenhav
ms.openlocfilehash: 22988b08209865e9f1f2c583a30aa40e48c249bc
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/09/2019
ms.locfileid: "73879243"
---
# <a name="get-notifications-in-the-power-bi-mobile-apps"></a>รับการแจ้งเตือนในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่
นำไปใช้กับ:

| ![iPhone](./media/mobile-apps-notification-center/iphone-logo-50-px.png) | ![iPad](./media/mobile-apps-notification-center/ipad-logo-50-px.png) | ![โทรศัพท์ Android](./media/mobile-apps-notification-center/android-phone-logo-50-px.png) | ![แท็บเล็ต Android](./media/mobile-apps-notification-center/android-tablet-logo-50-px.png) | ![Windows 10](./media/mobile-apps-notification-center/win-10-logo-50-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone |iPad |โทรศัพท์ Android |แท็บเล็ต Android |อุปกรณ์ Windows 10 |

การแจ้งเตือนจะนำข้อมูลที่เกี่ยวข้องกับประสบการณ์ Power BI ให้คุณ ในบริการของ Power BI หรือบนอุปกรณ์เคลื่อนที่ของคุณ เมื่อคุณเปิดการแจ้งเตือน คุณจะเห็นตัวดึงข้อมูลเรียงเป็นลำดับเกี่ยวกับ[การแจ้งเตือนที่คุณได้ตั้งค่า](mobile-set-data-alerts-in-the-mobile-apps.md)แดชบอร์ดใหม่ที่มีการแชร์กับคุณ การเปลี่ยนแปลงพื้นที่การทำงานกลุ่มของคุณ รายละเอียดเกี่ยวกับเหตุการณ์ใน Power BI และการประชุม และอื่นๆ

> [!NOTE]
> บนอุปกรณ์ iOS ในครั้งแรกที่คุณลงชื่อเข้าใช้[ปรับปรุงเวอร์ชันของแอป Power BI](https://powerbi.microsoft.com/mobile/)คุณจะเห็นข้อความถามว่า คุณต้องการให้ Power BI ส่งการแจ้งเตือนหรือไม่ คุณยังสามารถกำหนดวิธีที่ี Power BI จะแจ้งเตือนคุณใน**ตั้งค่า**สำหรับอุปกรณ์ของคุณ 
> 
> 

## <a name="view-notifications-on-your-mobile-device"></a>ดูการแจ้งเตือนบนอุปกรณ์เคลื่อนที่ของคุณ
1. เมื่อคุณได้รับการแจ้งเตือนบนอุปกรณ์เคลื่อนที่ ค่าเริ่มต้นจะทำให้ Power BI ส่งเสียงและแสดงแบนเนอร์การแจ้งเตือน
   
   ![แบนเนอร์การแจ้งเตือน](./media/mobile-apps-notification-center/power-bi-mobile-notification-banner.png)
   
   หรือ บน iPad:
   
   ![การแจ้งเตือน](./media/mobile-apps-notification-center/power-bi-ipad-notifications.png)
   
   คุณสามารถ[เปลี่ยนวิธีที่ Power BI จะแจ้งเตือนคุณ](mobile-apps-notification-center.md#change-or-turn-off-notifications-on-your-mobile-device)ได้
2. ถ้าคุณได้รับการแจ้งเตือน เมื่อคุณลงชื่อเข้าใช้ Power BI บนอุปกรณ์เคลื่อนที่ของคุณ คุณจะเห็นจุดสีเหลืองบนปุ่มนำทางส่วนกลางที่เรียกว่า![จุดแจ้งเตือน](./media/mobile-apps-notification-center/power-bi-android-menu-notifications-icon.png) (Android) หรือบนไอคอน**การแจ้งเตือน** 
   
   ![จุดการแจ้งเตือน](./media/mobile-apps-notification-center/power-bi-windows-10-notifications.png)
3. เลือกไอคอนการแจ้งเตือน ![ไอคอนการแจ้งเตือน](./media/mobile-apps-notification-center/power-bi-windows-10-notification-icon.png) (Windows 10)
   
    การแจ้งเตือนจะแสดงรายการล่าสุดที่ด้านบนสุด รวมถึงไฮไลท์ข้อความที่ยังไม่ได้อ่าน การแจ้งเตือนจะถูกเก็บไว้เป็น 90 วัน เว้นแต่ว่าคุณลบทิ้งเร็วกว่านั้น หรือเมื่อถึงขีดจำกัดสูงสุดที่ 100 การแจ้งเตือน
   
   ![รายการการแจ้งเตือน iOS](./media/mobile-apps-notification-center/power-bi-iphone-notifications-list.png)
4. เมื่อต้องละเว้นการแจ้งเตือน แตะ และกดค้างไว้ และเลือก**ยกเลิก**

## <a name="change-or-turn-off-notifications-on-your-mobile-device"></a>เปลี่ยน หรือปิดการแจ้งเตือนบนอุปกรณ์เคลื่อนที่ของคุณ
คุณสามารถเปลี่ยนวิธีที่ Power BI แจ้งเตือนคุณได้

1. บนอุปกรณ์ iOS ไปที่**ตั้งค่า** > **การแจ้งเตือน** 
   
    บนโทรศัพท์ Android ไปที่**ตั้งค่าการแจ้งเตือน**
   
    บนอุปกรณ์ Windows ใน**ตั้งค่า**ไปยัง**ระบบ** > **การแจ้งเตือนและการดำเนินการ**
2. ในรายการแอป เลือก**Power BI** 
3. ที่นี่คุณสามารถปิดการแจ้งเตือนทั้งหมด หรือเลือกการแจ้งเตือนที่คุณต้องการ
   
    **บน iPhone**
   
    ![เลือกการแจ้งเตือน](./media/mobile-apps-notification-center/power-bi-notifications-iphone-settings.png)
   
    **บนโทรศัพท์ Android**
   
    ![เลือกการแจ้งเตือน](./media/mobile-apps-notification-center/power-bi-notifications-android-settings.png)

    **บนอุปกรณ์ Windows 10**

    ![เลือกการแจ้งเตือน](./media/mobile-apps-notification-center/power-bi-notifications-windows10-settings.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป
* [การแจ้งเตือนข้อมูลในบริการของ Power BI](../../service-set-data-alerts.md)
* [ตั้งค่าการแจ้งเตือนข้อมูลในแอปบน iPhone (Power BI สำหรับ iOS)](mobile-set-data-alerts-in-the-mobile-apps.md)
* [ตั้งค่าการแจ้งเตือนข้อมูลในแอป Power BI สำหรับอุปกรณ์เคลื่อนที่สำหรับ Windows 10](mobile-set-data-alerts-in-the-mobile-apps.md)
* [ดาวน์โหลดเวอร์ชันล่าสุดของแอป Power BI](https://powerbi.microsoft.com/mobile/)สำหรับอุปกรณ์เคลื่อนที่


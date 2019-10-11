---
title: สร้างรายงาน Power BI สำหรับเซิร์ฟเวอร์รายงาน Power BI
description: เรียนรู้วิธีการสร้างรายงาน Power BI สำหรับเซิร์ฟเวอร์รายงาน Power BI ในขั้นตอนง่าย ๆ ไม่กี่ขั้นตอน
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 09/26/2019
ms.author: maggies
ms.openlocfilehash: f3a52e14271827a043f05d6b170e79718306aa99
ms.sourcegitcommit: d04b9e1426b8544ce16ef25864269cc43c2d9f7b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 10/01/2019
ms.locfileid: "71715252"
---
# <a name="create-a-power-bi-report-for-power-bi-report-server"></a>สร้างรายงาน Power BI สำหรับเซิร์ฟเวอร์รายงาน Power BI
คุณสามารถจัดเก็บ และจัดการรายงาน Power BI ภายในองค์กร ในพอร์ทัลของเว็บเซิร์ฟเวอร์รายงาน Power BI เช่นเดียวกับที่คุณสามารถจัดเก็บรายงาน Power BI ในระบบคลาวด์ในบริการของ Power BI (https://powerbi.com) ได้ คุณสร้างและแก้ไขรายงานใน Power BI Desktop แล้วเผยแพร่ไปยังพอร์ทัลของเว็บ จากนั้น ผู้อ่านรายงานในองค์กรของคุณ สามารถดูรายงานได้ในเบราว์เซอร์ หรือในแอปมือถือ Power BI บนอุปกรณ์เคลื่อนที่ของพวกเขา

![รายงาน Power BI ในพอร์ทัลของเว็บ](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

ต่อไปนี้เป็นสี่ขั้นตอนด่วน ที่ช่วยให้คุณเริ่มต้น

## <a name="step-1-install-power-bi-desktop-optimized-for-power-bi-report-server"></a>ขั้นตอนที่ 1: ติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI

ถ้าคุณเคยสร้างรายงาน Power BI ใน Power BI Desktop แล้ว คุณเกือบพร้อมที่จะสร้างรายงาน Power BI สำหรับเซิร์ฟเวอร์รายงาน Power BI เราขอแนะนำให้ติดตั้งเวอร์ชันของ Power BI Desktop ที่ปรับให้เหมาะสำหรับเซิร์ฟเวอร์รายงาน Power BI เพื่อให้คุณมั่นใจว่าเซิร์ฟเวอร์ และแอปจะซิงค์กันอยู่เสมอ คุณสามารถมี Power BI Desktop ทั้งสองเวอร์ชันบนคอมพิวเตอร์เครื่องเดียวกัน

1. ในพอร์ทัลของเว็บเซิร์ฟเวอร์รายงาน เลือกลูกศร**ดาวน์โหลด** > **Power BI Desktop**

    ![ดาวน์โหลด Power BI Desktop จากพอร์ทัลของเว็บ](media/quickstart-create-powerbi-report/report-server-download-web-portal.png)

    หรือไปที่หน้าหลัก [เซิร์ฟเวอร์รายงาน Power BI](https://powerbi.microsoft.com/report-server/) แล้วเลือก **ตัวเลือกการดาวน์โหลดขั้นสูง**

2. ในหน้าศูนย์ดาวน์โหลด เลือก**ดาวน์โหลด**

3. ขึ้นอยู่กับคอมพิวเตอร์ของคุณ เลือก:

    - **PBIDesktopRS.msi** (เวอร์ชัน 32 บิต) หรือ

    - **PBIDesktopRS_x64.msi** (เวอร์ชัน 64 บิต)

4. หลังจากดาวน์โหลดตัวติดตั้ง ให้เรียกใช้ตัวช่วยติดตั้ง Power BI Desktop (กันยายน 2019)

2. ในตอนท้ายของการติดตั้ง ทำเครื่องหมายที่**เริ่มต้น Power BI Desktop ทันที**
   
    จะเริ่มต้นโดยอัตโนมัติ และคุณก็พร้อมที่จะไปต่อ คุณสามารถแจ้งว่าคุณมีเวอร์ชั่นที่ถูกต้อง เนื่องจาก **Power BI Desktop (กันยายน 2019)** อยู่ในแถบรายการแจ้งชื่อ

    ![Power BI Desktop กันยายน 2019](media/quickstart-create-powerbi-report/power-bi-report-server-desktop-sept-2019.png)

3. ถ้าคุณไม่คุ้นเคยกับ Power BI Desktop ลองดูวิดีโอบนหน้าจอยินดีต้อนรับ
   
    ![หน้าจอเริ่มต้น Power BI Desktop](media/quickstart-create-powerbi-report/report-server-powerbi-desktop-start.png)

## <a name="step-2-select-a-data-source"></a>ขั้นตอนที่ 2: เลือกแหล่งข้อมูล
คุณสามารถเชื่อมต่อกับแหล่งข้อมูลที่หลากหลาย อ่านเพิ่มเติมเกี่ยวกับ[การเชื่อมต่อกับแหล่งข้อมูล](connect-data-sources.md)

1. จากหน้าจอยินดีต้อนรับ เลือก**รับข้อมูล**
   
    หรือบนการแท็บ**หน้าแรก** เลือก**รับข้อมูล**
2. เลือกแหล่งข้อมูลของคุณ - ในตัวอย่างนี้เป็น **Analysis Services**
   
    ![เลือกแหล่งข้อมูล](media/quickstart-create-powerbi-report/power-bi-report-server-get-data-ssas.png)
3. กรอกค่า**เซิร์ฟเวอร์** และใส่**ฐานข้อมูล**ถ้าจำเป็น ตรวจสอบให้แน่ใจว่าตัวเลือก**เชื่อมต่อแบบไลฟ์**ถูกเลือก > **ตกลง**
   
    ![ชื่อเซิร์ฟเวอร์](media/quickstart-create-powerbi-report/report-server-ssas-server-name.png)
4. เลือกเซิร์ฟเวอร์รายงานที่คุณจะบันทึกรายงานของคุณ
   
    ![เลือกเซิร์ฟเวอร์รายงาน](media/quickstart-create-powerbi-report/report-server-select-server.png)

## <a name="step-3-design-your-report"></a>ขั้นตอนที่ 3: ออกแบบรายงานของคุณ
เรื่องสนุกๆ อยู่ในส่วนนี้: คุณจะสร้างวิชวลที่แสดงข้อมูลของคุณ

ตัวอย่างเช่น คุณสามารถสร้างแผนภูมิกรวยของลูกค้าและจัดกลุ่มตามรายได้รายปี

![ออกแบบรายงาน](media/quickstart-create-powerbi-report/report-server-create-funnel.png)

1. ใน**การจัดรูปแบบการแสดงข้อมูล** เลือก**แผนภูมิกรวย**
2. ลากเขตข้อมูลที่จะนับลงใน **ค่า** ถ้าเขตข้อมูลไม่ใช่ตัวเลข Power BI Desktop จะทำการ*นับจำนวน*ค่าให้โดยอัตโนมัติ
3. ลากเขตข้อมูลที่จะจัดกลุ่มลงใน **กลุ่ม**

อ่านเพิ่มเติมเกี่ยวกับ[การออกแบบรายงาน Power BI](../desktop-report-view.md)

## <a name="step-4-save-your-report-to-the-report-server"></a>ขั้นตอนที่ 4: บันทึกรายงานของคุณไปยังเซิร์ฟเวอร์รายงาน
เมื่อรายงานของคุณพร้อมแล้ว คุณบันทึกไปยังเซิร์ฟเวอร์รายงาน Power BI ที่คุณเลือกในขั้นตอนที่ 2

1. บนเมนู**แฟ้ม** เลือก**บันทึกเป็น** > **เซิร์ฟเวอร์รายงาน Power BI**
   
    ![บันทึกไปยังเซิร์ฟเวอร์รายงาน](media/quickstart-create-powerbi-report/report-server-save-as-powerbi-report-server.png)
2. ตอนนี้ คุณสามารถดูรายงานได้ในพอร์ทัลของเว็บ
   
    ![ดูรายงานในพอร์ทัลของเว็บ](media/quickstart-create-powerbi-report/report-server-powerbi-report.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป
### <a name="power-bi-desktop"></a>Power BI Desktop
มีทรัพยากรที่ยอดเยี่ยมมากมายสำหรับการสร้างรายงานใน Power BI Desktop ลิงก์นี้เป็นจุดเริ่มต้นที่ดี

* [เริ่มต้นใช้งาน Power BI Desktop](../desktop-getting-started.md)
* การเรียนรู้ตามคำแนะนำ: [สำรวจ Power BI Desktop](/learn/modules/get-data-power-bi/2-getting-started-power-bi-desktop)

### <a name="power-bi-report-server"></a>เซิร์ฟเวอร์รายงาน Power BI
* [ติดตั้ง Power BI Desktop ที่ปรับให้เหมาะสำหรับ Power BI Report Server](install-powerbi-desktop.md)  
* [เซิร์ฟเวอร์รายงาน Power BI คืออะไร](get-started.md)  

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](https://community.powerbi.com/)

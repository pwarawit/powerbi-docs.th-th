---
title: เชื่อมต่อกับชุดข้อมูลในบริการ Power BI จาก Power BI Desktop
description: ใช้ชุดข้อมูลที่ใช้ทั่วไปเพื่อจัดการรายงาน Power BI Desktop หลายชิ้นในพื้นที่ทำงานหลายแห่ง พร้อมจัดการวงจรชีวิตรายงานของคุณ
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/13/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: b1d17aa0bb8eec070af5b72183da845e4843c093
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83289867"
---
# <a name="connect-to-datasets-in-the-power-bi-service-from-power-bi-desktop"></a>เชื่อมต่อกับชุดข้อมูลในบริการ Power BI จาก Power BI Desktop

คุณสามารถสร้างการเชื่อมต่อไปยังชุดข้อมูลที่ใช้ร่วมกันใน *บริการ Power BI* และสร้างรายงานที่แตกต่างกันที่มากมายจากชุดข้อมูลเดียวกัน คุณสามารถสร้างรูปแบบข้อมูลที่สมบูรณ์แบบได้ใน Power BI Desktop และเผยแพร่ไปยังบริการของ Power BI จากนั้น คุณและผู้อื่นสามารถสร้างรายงานต่างๆ ได้หลายรายการ ในไฟล์ *.pbix* ที่แยกต่างหาก จากรูปแบบข้อมูลทั่วไปแบบเดียวกัน และบันทึกไปยังพื้นที่ทำงานที่แตกต่าง ฟีเจอร์นี้เรียกว่า*การเชื่อมต่อ Power BI แบบสด*

![รับข้อมูลจากบริการของ Power BI](media/desktop-report-lifecycle-datasets/report-lifecycle_01.png)

มีการเรียงลำดับทั้งหมดของประโยชน์ของฟีเจอร์นี้ รวมถึงการนำมาใช้ที่ดีที่สุดซึ่งเราจะอภิปรายกันในบทความนี้ เราแนะนำให้คุณตรวจสอบ [ข้อควรพิจารณาและข้อจำกัด](#limitations-and-considerations) ของฟีเจอร์นี้

## <a name="using-a-power-bi-service-live-connection-for-report-lifecycle-management"></a>การใช้ Power BI service Live connection เพื่อการจัดการวงจรชีวิตรายงาน

ความท้าทายอย่างหนึ่งในความเป็นที่นิยมของ Power BI คือ การเพิ่มจำนวนรายงาน แดชบอร์ด และโมเดลข้อมูลพื้นฐาน มันง่ายมากในการสร้างรายงานที่บังคับใน Power BI Desktop แล้ว [เผยแพร่](../create-reports/desktop-upload-desktop-files.md) รายงานเหล่านั้นในบริการ Power BI และสร้างแดชบอร์ดที่ยิ่งใหญ่จากชุดข้อมูลเหล่านั้น เนื่องจากผู้คนมากมายมักจะใชชุดข้อมูลเดียวกัน หรือเกือบเหมือนกัน การตระหนักว่ารายงานชิ้นไหนอยู่ในชุดข้อมูลใด และชุดข้อมูลแต่ละชุดนั้นเป็นข้อมูลใหม่ขนาดไหนกลายเป็นเรื่องที่ท้าทาย Power BI service Live connection กล่าวถึงความท้าทายนั้น และทำการสร้าง แชร์ และขยายตามรายงานชุดข้อมูลทั่วไปและแดชบอร์ดได้ง่ายขึ้น และมีความคงเส้นคงวา

### <a name="create-a-dataset-everyone-can-use-then-share-it"></a>สร้างชุดข้อมูลที่ทุกคนสามารถใช้และแชร์ต่อได้

สมมติว่า Anna เป็นนักวิเคราะห์ทางธุรกิจใจทีมของคุณ Anna มีทักษะในการสร้างรูปแบบข้อมูลที่ดี ที่เรียกว่าชุดข้อมูล แอนนาสามารถสร้างชุดข้อมูลและรายงาน และแชร์รายงานนั้นในบริการของ Power BI ได้

![เผยแพร่ไปยังบริการ Power BI](media/desktop-report-lifecycle-datasets/report-lifecycle_02a.png)

ทุกคนรักรายงานและชุดข้อมูลของ Anna และตรงนี้เป็นจุดเริ่มต้นของปัญหา ทุกคนในทีมของ Anna จะพยายามสร้าง*ชุดข้อมูลเวอร์ชั่นของตนเอง*จากชุดข้อมูลนั้น ได้แชร์รายงานของตนกับทีม จึงทำให้มีรายงานจำนวนหลายชิ้นเกิดขึ้นมาโดยพลันจากชุดข้อมูลที่แตกต่างกันในพื้นที่ทำงานของทีมของคุณในบริการของ Power BI อันไหนเป็นชิ้นล่าสุด ชุดข้อมูลทั้งหมดเหมือนกันหรือไม่ หรือว่าแค่เกือบเหมือนกันเท่านั้น อะไรคือความแตกต่าง ด้วยฟีเจอร์การเชื่อมต่อบริการ Power BI ทุกอย่างจะเปลี่ยนแปลงไปในทางที่ดีกว่าได้ ในส่วนถัดไป เราจะได้เห็นวิธีที่ผู้อื่นสามารถใช้ชุดข้อมูลที่แอนนาเผยแพร่ไว้เพื่อรายงานของพวกเขาเอง ในพื้นที่ทำงานของพวกเขาเอง และเปิดให้ทุกคนสามารถใช้ชุดข้อมูลที่เผยแพร่อย่างเชื่อใจได้ในการสร้างรายงานที่เป็นเอกลักษณ์ของพวกเขา

### <a name="connect-to-a-power-bi-service-dataset-using-a-live-connection"></a>เชื่อมต่อชุดข้อมูลบริการ Power BI โดยใช้การเชื่อมต่อสด

Anna สร้างรายงานและสร้างชุดข้อมูลตามที่กำหนด Anna ได้เผยแพร่ไปยังบริการ Power BI รายงานแสดงในพื้นที่ทำงานของทีมในบริการ Power BI หาก Anna บันทึกไปยัง *พื้นที่ทำงานประสบการณ์ใหม่* แอนนาจะสามารถตั้งค่า *สิทธิ์ในการสร้าง* เพื่อให้พร้อมใช้งานสำหรับทุกคนที่เข้าและออกจากพื้นที่ทำงานของตนเพื่อดูและใช้งาน

หากต้องการเรียนรู้เพิ่มเติมเกี่ยวกับพื้นที่ทำงานที่มีประสบการณ์การใช้งานใหม่ โปรดดู[พื้นที่ทำงาน](../collaborate-share/service-new-workspaces.md)

ตอนนี้สมาชิกคนอื่น ๆ ในพื้นที่ทำงานของ Anna สามารถสร้างการเชื่อมต่อสดไปยังโมเดลข้อมูลที่ Anna แชร์ไว้ ใช้ฟีเจอร์ Power BI service live connection พวกเขาสามารถสร้างรายงานที่เป็นแบบฉบับของตนเอง จาก *ชุดข้อมูลดั้งเดิมของพวกเขา* ใน *พื้นที่ทำงานประสบการณ์ใหม่ของพวกเขาเอง* 

ในรูปต่อไปนี้ คุณจะเห็นวิธีที่ Anna สร้างรายงาน Power BI Desktop และพร้อมเผยแพร่ ซึ่งรวมถึงรูปโมเดลข้อมูล ไปยังบริการ Power BI จากนั้นผู้อื่นสามารถเชื่อมต่อกับรูปแบบข้อมูลของ Anna โดยใช้การเชื่อมต่อสดจากบริการของ Power BI และสร้างรายงานที่เป็นแบบฉบับของตนเองในพื้นที่ทำงานของตนโดยยึดตามชุดข้อมูลของ Anna

![รายงานหลายรายการตามชุดข้อมูลเดียวกัน](media/desktop-report-lifecycle-datasets/report-lifecycle_03.png)

> [!NOTE]
> ถ้าคุณบันทึกชุดข้อมูลของคุณไปยัง[พื้นที่ทำงานที่แชร์แบบคลาสสิก](../collaborate-share/service-create-workspaces.md) เฉพาะสมาชิกในพื้นที่ทำงานนั้นที่สร้างรายงานบนชุดข้อมูลของคุณ ในการติดตั้ง Power BI service live connection นั้นชุดข้อมูลที่คุณเชื่อมต่อจะต้องอยู่ในพื้นที่ทำงานที่ใช้ร่วมกันที่คุณเป็นสมาชิกอยู่
> 
> 

## <a name="step-by-step-for-using-the-power-bi-service-live-connection"></a>ขั้นตอนแต่ละขั้นตอนสำหรับการใช้การเชื่อมต่อสดจากบริการของ  Power BI

ในตอนนี้ให้เราทราบแล้วว่าการเชื่อมต่อสดจากบริการของ  Power BI มีประโยชน์อย่างไร และคุณจะสามารถใช้มันอย่างไรให้เกิดประโยชน์สูงสุดเพื่อรองรับการจัดการวงจรชีวิตรายงาน มาดูกันทีละขั้นตอนจากรายงานชุดข้อมูล อันเยี่ยมยอดของแอนนาไปจนถึงชุดข้อมูลที่ใช้ร่วมกันที่เพื่อนร่วมทีม Power BI ของเธอสามารถใช้ได้

### <a name="publish-a-power-bi-report-and-dataset"></a>เผยแพร่รายงาน Power BI และชุดข้อมูล

ขั้นตอนแรกในการจัดการวงจรชีวิตรายงานการเชื่อมต่อสดจากบริการของ Power BI คือการมีรายงานและชุดข้อมูลที่เพื่อนร่วมทีมต้องการใช้ ดังนั้น สิ่งแรกที่แอนนาต้องทำคือ*เผยแพร่*รายงานจาก Power BI Desktop เลือก **เผยแพร่** จากริบบิ้น **หน้าแรก** ใน Power BI Desktop

![เผยแพร่รายงาน](media/desktop-report-lifecycle-datasets/report-lifecycle_02a.png)

หากแอนนาไม่ได้ลงชื่อเข้าใช้บัญชีบริการของ Power BI แล้ว Power BI  จะพร้อมท์ให้แอนนาทำเช่นนั้น

![ลงชื่อเข้าใช้ Power BI Desktop](media/desktop-report-lifecycle-datasets/report-lifecycle_04.png)

จากที่นั่น แอนนาสามารถเลือกพื้นที่ทำงานปลายทางที่รายงานและชุดข้อมูลจะเผยแพร่ไป อย่าลืมว่า ถ้าแอนนาบันทึกในพื้นที่ทำงานที่มีประสบการณ์การใช้งานใหม่ ทุกคนที่มีสิทธิ์ในการสร้างจะสามารถเข้าถึงชุดข้อมูลนั้นได้ สิทธิ์ในการสร้างถูกตั้งค่าในบริการของ Power BI หลังจากการเผยแพร่ ถ้างานที่บันทึกลงในพื้นที่ทำงานแบบคลาสสิกเฉพาะสมาชิกทีมีสิทธิ์ในการเข้าถึงพื้นที่ทำงานที่รายงานเผยแพร่อยู่เท่านั้นที่จะสามารถเข้าถึงชุดข้อมูลของรายงานโดยใช้การเชื่อมต่อสดจากบริการของ Power BI

![เผยแพร่ไปยังบริการ Power BI](media/desktop-report-lifecycle-datasets/report-lifecycle_05.png)

กระบวนการเผยแพรเริ่มต้น และ Power BI Desktop จะแสดงความคืบหน้า

![กำลังอยู่ในระหว่างการเผยแพร่](media/desktop-report-lifecycle-datasets/report-lifecycle_06.png)

เมื่อเสร็จสมบูรณ์แล้ว Power BI Desktop จะแสดงความสำเร็จ และจะให้ลิงก์สองสามลิงก์เพื่อช่วยให้คุณสามารถเข้าไปดูรายงานในบริการ Power BI และลิงก์เพื่อรับข้อมูลเชิงลึกอย่างรวดเร็วเกี่ยวกับรายงาน

![การเผยแพร่สำเร็จแล้ว](media/desktop-report-lifecycle-datasets/report-lifecycle_07.png)

ตอนนี้รายงานของคุณกับชุดข้อมูลอยู่ในบริการของ Power BI แล้ว คุณยังสามารถ*เลื่อนระดับ*มันได้  การเพิ่มระดับหมายถึงคุณทำการพิสูจน์คุณภาพและความน่าเชื่อถือของมันแล้ว คุณสามารถขอรับ*การรับรอง*จากผู้มีอำนาจส่วนกลางในผู้เช่า Power BI ของคุณได้ ด้วยการรับรองอย่างใดอย่างหนึ่งเหล่านี้ ชุดข้อมูลของคุณจะปรากฏที่ด้านบนของรายการเมื่อบุคคลกำลังค้นหาชุดข้อมูล สำหรับข้อมูลเพิ่มเติม ดู [เลื่อนระดับชุดข้อมูลของคุณ](service-datasets-promote.md)

ขั้นตอนสุดท้ายที่ตั้งค่าการอนุญาตในการสร้างสำหรับชุดข้อมูลที่รายงานใช้อ้างอิง สิทธิ์ในการสร้างจะกำหนดผู้ที่สามารถดูและใช้ชุดข้อมูลของคุณได้ คุณสามารถตั้งค่าในพื้นที่ทำงาน หรือเมื่อคุณแชร์แอปจากพื้นที่ทำงานได้ สำหรับข้อมูลเพิ่มเติม ดู [การอนุญาตในการสร้างสำหรับชุดข้อมูลที่แชร์](service-datasets-build-permissions.md)

ถัดไป มาดูวิธีที่เพื่อนร่วมทีมอื่น ๆ ที่สามารถเข้าถึงพื้นที่ทำงานที่รายงานและชุดข้อมูล ถูกเผยแพร่แล้ว สามารถทำการเชื่อมต่อกับชุดข้อมูล และสร้างรายงานของพวกเขาเองได้

### <a name="establish-a-power-bi-service-live-connection-to-the-published-dataset"></a>สร้าง Power BI service live connection ไปยังชุดข้อมูลเผยแพร่แล้ว

ในการที่จะติดตั้งการเชื่อมต่อไปยังรายงานที่เผยแพร่อยู่ และสร้างรายงานของคุณเองตามชุดข้อมูลที่เผยแพร่อยู่นั้น ให้เลือก**รับข้อมูล**จากริบบิ้น**หน้าแรก** ใน Power BI Desktop เลือก**Power Platform** ในบานหน้าต่างด้านซ้าย แล้วเลือก **ชุดข้อมูล Power BI**

หากคุไม่ได้ลงชื่อ Power BI จะพร้อมให้คุณลงชื่อ เมื่อทำการลงชื่อ Power BI แสดงพื้นที่ทำงานที่คุณเป็นสมาชิกอยู่ คุณสามารถเลือกพื้นที่ทำงานใดที่มีชุดข้อมูลที่คุณต้องการสร้างการเชื่อมต่อแบบสดของบริการ Power BI

ชุดข้อมูลในรายการคือชุดข้อมูลที่แชร์ทั้งหมดที่คุณมีสิทธิ์ในการสร้างในพื้นที่ทำงานใด ๆ คุณสามารถค้นหาชุดข้อมูลที่เฉพาะ และดูชื่อ เจ้าของ พื้นที่ทำงานที่มีชุดข้อมูลและเมื่อมีการรีเฟรชล่าสุด คุณยังดูชุดข้อมูล **ENDORSEMENT** ที่ผ่านการรับรองหรือเลื่อนระดับที่ด้านบนของรายการ

![รายการชุดข้อมูลที่พร้อมใช้งาน](media/desktop-report-lifecycle-datasets/desktop-select-shared-dataset.png)

เมื่อคุณเลือก **สร้าง**, คุณจะสร้างการเชื่อมต่อแบบสดไปยังชุดข้อมูลที่เลือก Power BI Desktop โหลดเขตข้อมูลและค่าของพวกเขาที่คุณเห็นไปยัง Power BI Desktop ในเวลาจริง

![เขตข้อมูลชุดข้อมูลในบานหน้าต่างเขตข้อมูล](media/desktop-report-lifecycle-datasets/report-lifecycle_10.png)

ในตอนนี้ คุณและคนอื่นสามารถสร้าง และแชร์รายงานแบบกำหนดเอง จากชุดข้อมูลเดียวกันทั้งหมด การเข้าถึงนี้เป็นวิธีที่ดีที่สุดในการมีความรู้ของคนหนึ่งคนในการสร้างรูปแบบชุดข้อมูลที่ดี ดังเช่นที่ Anna สร้าง เพื่อร่วมทีมหลายคนสามารถใช้ชุดข้อมูลที่แขร์และสร้างรายงานด้วยตัวของพวกเขา

## <a name="limitations-and-considerations"></a>ข้อจำกัดและข้อควรพิจารณา

เมื่อใช้การเชื่อมต่อแบบสดของบริการของ Power BI จะมีข้อจำกัดและข้อควรพิจารณาถึงบางประการ

* เฉพาะผู้ใช้ที่มีสิทธิ์ในการสร้างสำหรับชุดข้อมูลเท่านั้นที่สามารถเชื่อมต่อกับชุดข้อมูลที่เผยแพร่แล้วโดยใช้การเชื่อมต่อแบบสดของบริการของ Power BI ได้
* เฉพาะผู้ใช้ฟรีเท่านั้นที่เห็นชุดข้อมูลจาก **พื้นที่ทำงานของฉัน** และในพื้นที่ทำงานแบบพรีเมียม
* ตั้งแต่การเชื่อมต่อนี้คือการเชื่อมต่อแบบสด การนำทางด้านซ้ายและการทำรูปแบบที่ไม่สามารถใช้ได้ คุณสามารถเพียงเชื่อมต่อไปยังชุดข้อมูลของแต่ละรายงาน ลักษณะพฤติกรรมนี้คล้ายคลึงกับพฤติกรรมเมื่อเชื่อมต่อไปยัง *SQL Server Analysis Services*
* ตั้งแต่การเชื่อมต่อนี้คือการเชื่อมต่อแบบสด รักษาความปลอดภัยระดับแถว (RLS) และการเชื่อมต่ออื่นๆ เช่นลักษณะพฤติกรรมของการเชื่อมต่อที่ถูกบังคับ นี่คือแบบเดียวกับเมื่อเชื่อมต่อกับ SQL Server Analysis Services
* ถ้าเจ้าของปรับเปลี่ยนไฟล์ *.pbix* ต้นฉบับที่ใช้ร่วมกัน ชุดข้อมูลและรายงานที่ใช้ร่วมกันในบริการ Power BI จะถูกเขียนทับ รายงานตามชุดข้อมูลดังกล่าวจะไม่ถูกเขียนทับ แต่เปลี่ยนแปลงใด ๆ กับชุดข้อมูลจะมีผลในรายงาน
* สมาชิกของพื้นที่ทำงานไม่สามารถเปลี่ยนทับรายงานต้นฉบับที่ใช้ร่วมกัน หากมีการพยายามที่จะเปลี่ยนทับรายงานต้นฉบับ จะมีข้อความเตือนขึ้นมาให้คุณเปลี่ยนชื่อไฟล์ และเผยแพร่
* ถ้าคุณลบชุดข้อมูลที่แชร์ในบริการของ Power BI แล้วรายงานอื่นๆ ตามชุดข้อมูลนั้นจะทำงานได้ไม่ถูกต้อง หรือแสดงวิชวลขึ้นมา
* สำหรับชุดเนื้อหา คุณต้องสร้างสำเนาชุดเนื้อหาก่อนที่ใช้เป็นพื้นฐานสำหรับการแชรรายงาน *.pbix* และชุดข้อมูลไปยังบริการ Power BI
* สำหรับชุดเนื้อหาจาก*องค์กรของฉัน*เมื่อทำการคัดลอกแล้ว คุณจะไม่สามารถแทนรายงานที่สร้างบนบริการและ/หรือรายงานที่สร้างขึ้นเป็นส่วนหนึ่งของการคัดลอก Content Pack ด้วยการเชื่อมต่อสดได้ หากมีการพยายามที่จะเปลี่ยนทับรายงานต้นฉบับ จะมีข้อความเตือนขึ้นมาให้คุณเปลี่ยนชื่อไฟล์ และเผยแพร่ ในสถานการณ์นี้ คุณสามารถแทนรายงานเชื่อมต่อสดที่เผยแพร่แล้วเท่านั้น
* การลบชุดข้อมูลที่แชร์ในบริการของ Power BI หมายความว่าไม่มีใครสามารถเข้าถึงชุดข้อมูลนั้นได้จาก Power BI Desktop
* รายงานที่แชร์ชุดข้อมูลร่วมกันบนบริการของ Power BI ไม่สนับสนุนการปรับใช้โดยอัตโนมัติโดยใช้ Power BI REST API
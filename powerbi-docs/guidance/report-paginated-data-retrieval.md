---
title: คำแนะนำการเรียกข้อมูลสำหรับรายงานที่มีการแบ่งหน้า
description: คำแนะนำสำหรับการสร้างแหล่งข้อมูลและชุดข้อมูลสำหรับรายงานที่มีการแบ่งหน้า Power BI
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 02/16/2020
ms.author: v-pemyer
ms.openlocfilehash: 511dc42a3090f838654cda84f596d34f02bb3439
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83275098"
---
# <a name="data-retrieval-guidance-for-paginated-reports"></a>คำแนะนำการเรียกข้อมูลสำหรับรายงานที่มีการแบ่งหน้า

บทความนี้มุ่งไปที่คุณเช่นเดียวกับผู้เขียนรายงานที่ออกแบบ Power BI [รายงานที่มีเลขหน้า](../paginated-reports/paginated-reports-report-builder-power-bi.md). ซึ่งจะให้คำแนะนำเพื่อช่วยให้คุณสามารถออกแบบการเรียกข้อมูลที่มีประสิทธิภาพและมีประสิทธิผล

## <a name="data-source-types"></a>ชนิดแหล่งข้อมูล

โดยปกติแล้ว รายงานจะสนับสนุนทั้งแหล่งข้อมูลเชิงสัมพันธ์และเชิงวิเคราะห์ นอกจากนี้ แหล่งข้อมูลเหล่านี้จะถูกจัดประเภทเพิ่มเติม เป็นบนระบบคลาวด์หรือภายในองค์กร แหล่งข้อมูลภายในองค์กร ไม่ว่าจะเป็นโฮสต์ภายในองค์กร หรือในเครื่องเสมือน จำเป็นต้องมีเกตเวย์ข้อมูล เพื่อให้ Power BI สามารถเชื่อมต่อได้ แหล่งข้อมูลบนระบบคลาวด์ หมายความว่า Power BI สามารถเชื่อมต่อได้โดยตรง โดยใช้การเชื่อมต่ออินเทอร์เน็ต

หากคุณเลือกประเภทแหล่งข้อมูล (อาจเป็นกรณีในโครงการใหม่) เราขอแนะนำให้คุณเลือกประเภทแหล่งข้อมูลแบบบนระบบคลาวด์ รายงานที่มีการแบ่งหน้าสามารถเชื่อมต่อกับเวลาแฝงเครือข่ายที่ลดลง โดยเฉพาะอย่างยิ่งเมื่อแหล่งข้อมูลอยู่ในภูมิภาคเดียวกับผู้เช่า Power BI ของคุณ นอกจากนี้ เป็นไปได้ที่จะเชื่อมต่อกับแหล่งข้อมูลดังกล่าวโดยใช้การลงชื่อเข้าระบบครั้งเดียว (SSO) ซึ่งหมายความว่าข้อมูลประจำตัวของผู้ใช้รายงานสามารถโฟลว์ไปยังแหล่งข้อมูลได้โดยอนุญาตให้มีสิทธิ์ในระดับแถวสำหรับแต่ละผู้ใช้ ในปัจจุบัน SSO ไม่ได้รับการสนับสนุนสำหรับแหล่งข้อมูลภายในองค์กร (หมายความว่า SQL Server Analysis Services ไม่สามารถบังคับใช้สิทธิ์ในระดับแถวของแต่ละผู้ใช้ได้)

> [!NOTE]
> ในขณะนี้ ยังไม่สามารถเชื่อมต่อกับฐานข้อมูลภายในองค์กรโดยใช้ SSO คุณยังสามารถบังคับให้สิทธิ์ระดับแถวได้ ทำได้โดยการส่งผ่านเขตข้อมูล **UserID** ที่มีอยู่แล้วภายในไปยังพารามิเตอร์คิวรีชุดข้อมูล แหล่งข้อมูลจะต้องจัดเก็บค่าชื่อหลักของผู้ใช้ (UPN) ในลักษณะที่สามารถกรองผลลัพธ์คิวรีได้อย่างถูกต้อง
>
> ตัวอย่างเช่น พิจารณาว่าพนักงานขายแต่ละรายจะถูกจัดเก็บเป็นแถวในตาราง **พนักงานขาย**  ตารางนี้มีคอลัมน์สำหรับ UPN และมีภูมิภาคการขายของพนักงานขายดังกล่าวด้วย ในเวลาที่ทำคิวรี ตารางจะถูกกรองโดย UPN ของผู้ใช้รายงาน และยังเกี่ยวข้องกับข้อเท็จจริงด้านการขายโดยใช้การรวมภายในอีกด้วย ด้วยวิธีนี้ คิวรีจะสามารถกรองแถวข้อเท็จจริงของการขายตามภูมิภาคการขายของผู้ใช้รายงานได้อย่างมีประสิทธิภาพ

### <a name="relational-data-sources"></a>แหล่งข้อมูลเชิงสัมพันธ์

โดยทั่วไป แหล่งข้อมูลเชิงสัมพันธ์เหมาะอย่างยิ่งกับรายงานลักษณะการดำเนินงาน เช่น ใบแจ้งหนี้สำหรับการขาย นอกจากนี้ ยังเหมาะสำหรับรายงานที่จำเป็นต้องเรียกดูชุดข้อมูลขนาดใหญ่ (มากกว่า 10,000 แถว) นอกจากนี้ แหล่งข้อมูลเชิงสัมพันธ์ยังสามารุกำหนดกระบวนงานที่จัดเก็บ ซึ่งสามารถดำเนินการโดยชุดข้อมูลรายงาน กระบวนงานที่จัดเก็บมีประโยชน์หลายประการ:

- การกำหนดพารามิเตอร์
- การเอนแคปซูเลชั่นของตรรกะการเขียนโปรแกรมอนุญาตให้มีการเตรียมข้อมูลที่ซับซ้อนมากขึ้น (ตัวอย่างเช่น ตารางชั่วคราวเคอร์เซอร์ หรือฟังก์ชันที่ผู้ใช้กำหนดสเกลาเอง)
- ความสามารถในการดูแลรักษาแบบปรับปรุงใหม่ ที่ช่วยให้สามารถอัปเดตตรรกะกระบวนงานที่จัดเก็บได้อย่างง่ายดาย ในบางกรณี สามารถดำเนินการได้โดยไม่จำเป็นต้องปรับเปลี่ยนและเผยแพร่รายงานที่มีการแบ่งหน้าใหม่ (ในกรณีที่ชื่อคอลัมน์และประเภทข้อมูลยังคงไม่เปลี่ยนแปลง)
- ประสิทธิภาพการทำงานที่ดีกว่า เนื่องจากแผนการดำเนินการถูกแคชเพื่อการนำมาใช้ใหม่
- การนำกระบวนงานที่จัดเก็บมาใช้ใหม่ในรายงานหลายรายการ

ใน Power BI Report Builder คุณจะสามารถใช้ตัวออกแบบคิวรีเชิงสัมพันธ์ในการสร้างคำสั่งคิวรีเชิงกราฟิกได้ แต่ใช้สำหรับแหล่งข้อมูล Microsoft เท่านั้น

### <a name="analytic-data-sources"></a>แหล่งข้อมูลเชิงวิเคราะห์

แหล่งข้อมูลเชิงวิเคราะห์เหมาะอย่างยิ่งกับรายงานการดำเนินงานและการวิเคราะห์ และสามารถส่งมอบผลลัพธ์คิวรีแบบสรุปได้อย่างรวดเร็ว แม้กับข้อมูลจำนวนมากขนาดใหญ่ มาตรวัดแบบจำลองและ KPI สามารถเอนแคปซูเลทกฎธุรกิจที่ซับซ้อนเพื่อให้สรุปข้อมูลสำเร็จ อย่างไรก็ตาม แหล่งข้อมูลเหล่านี้ไม่เหมาะกับรายงานที่จำเป็นต้องเรียกดูชุดข้อมูลขนาดใหญ่มาก (เกินกว่า 10,000 แถว)

ใน Power BI Report Builder คุณมีตัวออกแบบคิวรีให้เลือกสองแบบ: ตัวออกแบบคิวรีบริการด้านการวิเคราะห์ DAX และตัวออกแบบคิวรีบริการด้านการวิเคราะห์ MDX ตัวออกแบบเหล่านี้สามารถใช้สำหรับแหล่งข้อมูลทีมีชุดข้อมูล Power BI หรือรูปแบบ SQL Server Analysis Services หรือ Azure Analysis Services แบบตารางหรือหลายขนาด

เราขอแนะนำให้คุณใช้ตัวออกแบบคิวรี DAX เนื่องจากจะสามารถตอบสนองต่อความต้องการคิวรีของคุณได้ทั้งหมด ในกรณีที่แบบไม่จำลองไม่ได้กำหนดมาตรวัดที่คุณจำเป็นต้องใช้ คุณจะต้องสลับไปยังโหมดคิวรี ในโหมดนี้ คุณสามารถปรับแต่งคำสั่งคิวรีได้โดยการเพิ่มนิพจน์ (เพื่อให้สามารถสรุปได้สำเร็จ)

ตัวออกแบบคิวรี MDX บังคับให้แบบจำลองของคุณมีมาตรวัดด้วย ตัวออกแบบมีความสามารถสองประการที่ไม่รองรับในตัวออกแบบคิวรี DAX โดยเฉพาะอย่างยิ่ง ช่วยให้คุณสามารถ:

- กำหนดสมาชิกที่คำนวณในระดับคิวรีแล้ว (ใน MDX)
- กำหนดค่าภูมิภาคข้อมูลที่จะร้องขอ [ผลรวมเซิร์ฟเวอร์](/sql/reporting-services/report-design/report-builder-functions-aggregate-function) ในกลุ่มที่ไม่มีรายละเอียด ถ้ารายงานของคุณจำเป็นต้องแสดงสรุปของมาตรวัดแบบกึ่งหรือไม่มีส่วนเสริม (เช่น การคำนวณแบบข่าวกรองหรือการนับจำนวนที่แตกต่างกัน) อาจมีประสิทธิภาพมากขึ้นในการใช้ผลรวมเซิร์ฟเวอร์มากกว่า การดึงแถวรายละเอียดระดับต่ำและมีสรุปการคำนวณรายงาน

## <a name="query-result-size"></a>ขนาดผลลัพธ์คิวรี

โดยทั่วไป แนวทางปฏิบัติที่ดีที่สุดคือการเรียกเฉพาะข้อมูลที่จำเป็นตามรายงานของคุณ ดังนั้น ไม่ต้องเรียกคอลัมน์หรือแถวที่รายงานไม่บังคับ

เพื่อจำกัดแถว คุณควรใช้ตัวกรองแบบจำกัดที่สุด และกำหนดคิวรีแบบผลรวมเสมอ คิวรีแบบผลรวมจะจัดกลุ่มและสรุปข้อมูลต้นทาง เพื่อเรียกดูผลลัพธ์ความละเอียดที่สูงกว่า ตัวอย่างเช่น ลองพิจารณาว่ารายงานของคุณจำเป็นต้องนำเสนอผลสรุปยอดขายของพนักงานขาย แทนที่จะเรียกดูแถวใบสั่งซื้อการขาย ให้สร้างคิวรีชุดข้อมูลที่มีการจัดกลุ่มตามพนักงานขาย และะสรุปข้อมูลยอดขายสำหรับแต่ละกลุ่ม

## <a name="expression-based-fields"></a>เขตข้อมูลตามนิพจน์

คุณสามารถขยายชุดข้อมูลรายงานด้วยเขตข้อมูลที่ยึดตามนิพจน์ได้ ตัวอย่างเช่น ถ้าแหล่งข้อมูลของคุณเป็นชื่อและนามสกุลของลูกค้า คุณอาจต้องการเขตข้อมูลที่เชื่อมสองเขตข้อมูลเพื่อสร้างชื่อสกุลของลูกค้า เพื่อให้สามารถคำนวณรายการนี้ได้ คุณมีสองตัวเลือก คุณสามารถ:

- สร้าง _เขตข้อมูลที่คำนวณ_ ซึ่งเป็นเขตข้อมูลของชุดข้อมูลตามนิพจน์
- ใส่นิพจน์โดยตรงลงในคิวรีชุดข้อมูล (โดยใช้ภาษาดั้งเดิมของแหล่งข้อมูลของคุณ) ซึ่งแสดงผลในเขตข้อมูลชุดข้อมูลปกติ

เราขอแนะนำให้ใช้ตัวเลือกที่สอง หากทำได้ มีสองเหตุผลดีๆ ที่ทำให้การใส่นิพจน์ในคิวรีชุดข้อมูลโดยตรงดีกว่าอีกตัวเลือกหนึ่ง

- ซึ่งเป็นไปได้ว่าแหล่งข้อมูลของคุณได้รับการปรับให้เหมาะสมเพื่อประเมินนิพจน์ได้อย่างมีประสิทธิภาพมากกว่า Power BI (โดยเฉพาะกรณีสำหรับฐานข้อมูลเชิงสัมพันธ์)
- ประสิทธิภาพของรายงานได้รับการปรับปรุง เนื่องจากไม่จำเป็นต้องใช้ Power BI เพื่อแสดงรูปร่างเขตข้อมูลที่คำนวณก่อนการแสดงรายงาน เขตข้อมูลที่คำนวณสามารถขยายเวลาการแสดงรายงานออกไปได้อย่างชัดเจน เมื่อชุดข้อมูลเรียกดูแถวจำนวนมาก

## <a name="field-names"></a>ชื่อเขตข้อมูล

เมื่อคุณสร้างชุดข้อมูล เขตข้อมูลของชุดข้อมูลจะถูกตั้งชื่อโดยอัตโนมัติตามคอลัมน์ของคิวรี เป็นไปได้ที่ชื่อดังกล่าวอาจไม่สุภาพหรือใช้งานได้ยาก และเป็นไปได้อีกเช่นกันที่ชื่อคอลัมน์ของคิวรีต้นทางอาจประกอบด้วยอักขระต้องห้ามที่ไม่สามารถแสดงได้ในตัวระบุวัตถุของ Report Definition Language (RDL) (เช่น การเว้นว่าง และสัญลักษณ์ต่างๆ) ในกรณีนี้ อักขระต้องห้ามจะถูกแทนที่ด้วยอักขระขีดเส้นใต้ (_)

เราขอแนะนำให้คุณตรวจสอบก่อนว่าชื่อเขตข้อมูลทั้งหมดสุภาพ สั้นกระชับ แต่ยังคงมีความหมายที่เหมาะสมหรือไม่ หากไม่ใช่ เราขอแนะนำให้คุณเปลี่ยนชื่อใหม่ _ก่อน_ที่คุณจะเริ่มทำเค้าโครงรายงาน เนื่องากเขตข้อมูลทีเ่ปลี่ยนชื่อแล้วจะไม่สามารถเปลี่ยนได้ผ่านนิพจน์ที่ใช้ในเค้าโครงรายงานของคุณ หากคุณตัดสินใจเปลี่ยนชื่อเขตข้อมูลหลังจากที่คุณเริ่มทำเค้าโครงรายงานแล้ว คุณจะต้องค้นหาและอัปเดตนิพจน์ที่เสียหายทั้งหมด

## <a name="filter-vs-parameter"></a>ตัวกรอง เทียบกับพารามิเตอร์

มีแนวโน้มที่ดีไซน์รายงานที่มีการแบ่งหน้าของคุณจะมีพารามิเตอร์รายงาน โดยทั่วไป พารามิเตอร์รายงานจะใช้ในการแจ้งให้ผู้ใช้รายงานของคุณกรองรายงาน ในฐานะผู้เขียนรายงานที่มีการแบ่งหน้า คุณมีสองทางเลือกในการกรองรายงาน คุณสามารถแมปพารามิเตอร์รายงานกับ:

- _ตัวกรอง_ของชุดข้อมูล ซึ่งในกรณีนี้ ค่าพารามิเตอร์รายงานจะถูกใช้เพื่อกรองข้อมูลที่ได้รับมาโดยชุดข้อมูลแล้ว
- _พารามิเตอร์_ของชุดข้อมูล ซึ่งในกรณีนี้ ค่าพารามิเตอร์รายงาน จะถูกใส่ลงในคิวรีดั้งเดิมที่ส่งไปยังแหล่งข้อมูล

> [!NOTE]
> ชุดข้อมูลรายงานทั้งหมดจะถูกแคชไว้_ตามแต่ละเซสชัน_ได้สูงสุด 10 นาที _เกินกว่าการใช้ครั้งล่าสุด_ คุณสามารถใช้ชุดข้อมูลได้อีกครั้งเมื่อส่งค่าพารามิเตอร์ใหม่ (การกรอง) แสดงรายงานในรูปแบบที่แตกต่างกัน หรือโต้ตอบกับการออกแบบรายงานในบางวิธี เช่น การแสดงผลสลับหรือการเรียงลำดับ

จากนั้น ลองพิจารณาตัวอย่างของรายงานการขายที่มีพารามิเตอร์รายงานเดียวเพื่อกรองรายงานด้วยปีเดียว ชุดข้อมูลจะเรียกดูยอดขายสำหรับ_ทุกปี_ ซึ่งทำได้เนื่องจากพารามิเตอร์รายงานแมปกับตัวกรองชุดข้อมูล รายงานจะแสดงข้อมูลสำหรับปีที่ร้องขอซึ่งเป็นชุดย่อยของข้อมูลชุดข้อมูล เมื่อผู้ใช้รายงานเปลี่ยนพารามิเตอร์รายงานเป็นปีที่แตกต่างกันจากนั้น ดูรายงาน Power BI ไม่จำเป็นต้องเรียกใช้แหล่งข้อมูลใดๆ แทนที่จะเป็นเช่นนั้น จะใช้ตัวกรองอื่นกับชุดข้อมูลที่แคชอยู่แล้ว หลังจากที่ชุดข้อมูลถูกแคช การกรองอาจทำได้รวดเร็วมาก

ขณะนี้ ลองพิจารณาการออกแบบรายงานอื่น ในเวลานี้ การออกแบบรายงานจะแมปพารามิเตอร์รายงานของปียอดขายกับพารามิเตอร์ชุดข้อมูล ด้วยวิธีการนี้ Power BI จะใส่ค่าปีลงในคิวรีดั้งเดิม และชุดข้อมูลจะเรียกดูข้อมูลเฉพาะสำหรับปีดังกล่าวเท่านั้น ในแต่ละครั้ง ผู้ใช้รายงานจะเปลี่ยนแปลงค่าพารามิเตอร์รายงานประจำปี จากนั้น จะดูรายงาน ชุดข้อมูลจะเรียกดูผลลัพธ์ของคิวรีใหม่สำหรับปีดังกล่าว

วิธีการออกแบบทั้งสองแบบสามารถกรองข้อมูลรายงาน และการออกแบบทั้งสองแบบสามารถทำงานได้ดีสำหรับการออกแบบรายงานของคุณ อย่างไรก็ตาม การออกแบบที่ดีที่สุดจะขึ้นอยู่กับขนาดข้อมูลที่คาดหวัง ความผันผวนของข้อมูล และลักษณะการทำงานของผู้ใช้รายงานที่คาดหวัง

เราขอแนะนำให้ใช้_การกรองชุดข้อมูล_ เมื่อคุณคาดการณ์ว่าชุดข้อมูลย่อยอื่นของแถวชุดข้อมูลจะถูกนำมาใช้ใหม่หลายครั้ง (ดังนั้น จึงประหยัดเวลาการแสดงผล เนื่องจากไม่จำเป็นต้องเรียกดูข้อมูลใหม่) ในสถานการณ์สมมตินี้ คุณทราบว่า ต้นทุนการเรียกดูชุดข้อมูลที่มีขนาดใหญ่กว่าอาจถูกแลกเปลี่ยนตามจำนวนครั้งที่จะนำมาใช้ใหม่ ดังนั้น จึงเป็นประโยชน์สำหรับคิวรีที่ใช้เวลานานในการสร้าง แต่โปรดระมัดระวังว่า การแคชชุดข้อมูลขนาดใหญ่เป็นรายผู้ใช้ อาจส่งผลกระทบในเชิงลบต่อประสิทธิภาพการทำงาน และอัตราความเร็วของกำลังการผลิต

เราขอแนะนำให้ใช้ _การกำหนดพารามิเตอร์ของชุดข้อมูล_ เมื่อคุณคาดการณ์ว่า เป็นไปไม่ได้ที่ชุดย่อยอื่นของแถวชุดข้อมูลจะถูกร้องขอ หรือเมื่อจำนวนแถวชุดข้อมูลที่จะกรองมีแนวโน้มที่จะมีขนาดใหญ่มาก (และไม่มีประสิทธิภาพที่จะแคช) แนวทางการออกแบบนี้สามารถทำงานได้ดีเช่นกัน เมื่อที่เก็บข้อมูลของคุณมีความผันผวน ในกรณีนี้ การเปลี่ยนแปลงค่าพารามิเตอร์รายงานแต่ละค่าจะส่งผลในการเรียกดูข้อมูลล่าสุด

## <a name="non-native-data-sources"></a>แหล่งข้อมูลที่ไม่ใช่แบบดั้งเดิม

หากคุณต้องการพัฒนารายงานที่มีการแบ่งหน้าตามแหล่งข้อมูลที่ไม่ได้[รองรับตามรายงานที่มีการแบ่งหน้าแบบดั้งเดิม](../paginated-reports/paginated-reports-data-sources.md) คุณจะสามารถพัฒนาแบบจำลองข้อมูล Power BI Desktop ได้เป็นอันดับแรก ด้วยวิธีการนี้ คุณจะสามารถเชื่อมต่อกับ [แหล่งข้อมูลของ Power BI](../connect-data/power-bi-data-sources.md) ได้มากกว่า 100 รายการ หลังจากเผยแพร่ไปยังบริการของ Power BI คุณจะสามารถพัฒนารายงานที่มีการแบ่งหน้าที่เชื่อมต่อกับชุดข้อมูลของ Power BI

## <a name="data-integration"></a>การรวมข้อมูล

หากคุณต้องการรวมข้อมูลจากแหล่งข้อมูลหลายรายการ คุณมีสองตัวเลือก:

- **รวมชุดข้อมูลรายงาน**: หากแหล่งข้อมูล [รองรับตามรายงานที่มีการแบ่งหน้าแบบดั้งเดิม](../paginated-reports/paginated-reports-data-sources.md) คุณจะสามารถลองสร้างเขตข้อมูลที่คำนวณ ซึ่งใช้ฟังก์ชันของตัวสร้างรายงานคือ [Lookup](/sql/reporting-services/report-design/report-builder-functions-lookup-function) หรือ [LookupSet](/sql/reporting-services/report-design/report-builder-functions-lookupset-function)
- **พัฒนาแบบจำลอง Power BI Desktop**: อย่างไรก็ตาม มีแนวโน้มที่จะมีประสิทธิภาพมากกว่าหากคุณพัฒนาแบบจำลองข้อมูลใน Power BI Desktop คุณสามารถใช้ Power Query ในการรวมคิวรีต่างๆ ตาม [แหล่งข้อมูลที่รองรับ](../connect-data/power-bi-data-sources.md) หลังจากเผยแพร่ไปยังบริการของ Power BI คุณจะสามารถพัฒนารายงานที่มีการแบ่งหน้าที่เชื่อมต่อกับชุดข้อมูลของ Power BI

## <a name="sql-server-complex-data-types"></a>ประเภทข้อมูลที่ซับซ้อนของ SQL Server

เนื่องจาก SQL Server เป็นแหล่งข้อมูลภายในองค์กร Power BI จะต้องเชื่อมต่อผ่านทางเกตเวย์ อย่างไรก็ตาม เกตเวย์จะไม่รองรับการเรียกดูข้อมูลสำหรับประเภทข้อมูลที่ซับซ้อน ประเภทข้อมูลที่ซับซ้อนหมายรวมถึงประเภทภายในอย่า [งประเภทข้อมูลเชิงพื้นที](/sql/relational-databases/spatial/spatial-data-sql-server)่ GEOMETRY และ GEOGRAPHY และ [hierarchyid](/sql/t-sql/data-types/hierarchyid-data-type-method-reference) นอกจากนี้ ประเภทข้อมูลนี้ยังสามารถรวมประเภทที่กำหนดของผู้ใช้ที่ดำเนินการผ่านระดับชั้นของแอสเซมบลีในรันไทม์ภาษาทั่วไป (CLR) ของ Microsoft.NET Framework

การพล็อตข้อมูลเชิงพื้นที่และการวิเคราะห์ในการแสดงภาพแมปจำเป็นต้องใช้ข้อมูลเชิงพื้นที่ของ SQL Server ดังนั้น จึงไม่สามารถทำงานกับการแสดงภาพของแมป เมื่อ SQL Server เป็นแหล่งข้อมูลของคุณ เพื่อให้ชัดเจน จะสามารถทำงานได้ หากแหล่งข้อมูลของคุณคือฐานข้อมูล Azure SQL เนื่องจาก Power BI ไม่ได้เชื่อมต่อผ่านเกตเวย์

## <a name="data-related-images"></a>รูปภาพเกี่ยวกับข้อมูล

สามารถใช้รูปภาพในการเพิ่มโลโก้หรือรูปภาพไปยังเค้าโครงรายงานของคุณ เมื่อรูปภาพเกี่ยวข้องกับแถวที่เรียกดูตามชุดข้อมูลรายงาน คุณจะมีสองตัวเลือก:

- นอกจากนี้ ยังเป็นไปได้ที่สามารถเรียกดูข้อมูลรูปภาพจากแหล่งข้อมูลของคุณ (หากจัดเก็บในตารางไว้แล้ว)
- เมื่อมีการจัดเก็บรูปภาพบนเว็บเซิร์ฟเวอร์ คุณสามารถใช้นิพจน์แบบไดนามิกเพื่อสร้างเส้นทาง URL ของรูป

สำหรับข้อมูลและคำแนะนำเพิ่มเติม โปรดดูที่ [คำแนะนำเกี่ยวกับรูปภาพสำหรับรายงานที่มีการแบ่งหน้า](report-paginated-image.md)

## <a name="redundant-data-retrieval"></a>การเรียกข้อมูลซ้ำซ้อน

เป็นไปได้ว่ารายงานของคุณจะเรียกข้อมูลที่ซ้ำซ้อน ซึ่งสามารถเกิดขึ้นได้เมื่อคุณลบเขตข้อมูลคิวรีของชุดข้อมูลหรือรายงานมีชุดข้อมูลที่ไม่ได้ใช้ โปรดหลีกเลี่ยงสถานการณ์เหล่านี้ เนื่องจากจะทำให้เกิดภาระที่ไม่จำเป็นในแหล่งข้อมูลของคุณ เครือข่าย และทรัพยากรความจุของ Power BI

### <a name="deleted-query-fields"></a>เขตข้อมูลคิวรีที่ลบ

บนหน้า **เขตข้อมูล** ของหน้าต่าง**คุณสมบัติชุดข้อมูล** คุณสามารถลบชุดข้อมูล _เขตข้อมูลคิวรี_ (แผนผังเขตข้อมูลคิวรีไปยังคอลัมน์ที่ดึงข้อมูลโดยคิวรีชุดข้อมูล) อย่างไรก็ตาม ตัวสร้างรายงานจะไม่ลบคอลัมน์ที่สอดคล้องกันจากคิวรีชุดข้อมูล

หากคุณต้องการลบเขตข้อมูลคิวัรีจากชุดข้อมูลของคุณ เราขอแนะนำให้คุณลบคอลัมน์ที่สอดคล้องกันออกจากคิวรีชุดข้อมูล ตัวสร้างรายงานจะลบเขตข้อมูลคิวรีที่ซ้ำซ้อนกันโดยอัตโนมัติ หากคุณได้ลบเขตข้อมูลคิวรี โปรดแน่ใจว่าได้ปรับเปลี่ยนคำสั่งคิวรีของชุดข้อมูลเพื่อลบคอลัมน์ออก

### <a name="unused-datasets"></a>ชุดข้อมูลที่ไม่ได้ใช้

เมื่อเรียกใช้รายงาน ชุดข้อมูลทั้งหมดจะถูกประเมิน แม้ว่าจะไม่ได้ผูกกับวัตถุของรายงานก็ตาม สำหรับเหตุผลนี้ โปรดแน่ใจว่าได้ลบการทดสอบหรือชุดข้อมูลการพัฒนาใดๆ ออกก่อนที่คุณจะเผยแพร่รายงาน

## <a name="next-steps"></a>ขั้นตอนถัดไป

สำหรับข้อมูลเพิ่มเติมที่เกี่ยวข้องกับบทความนี้ โปรดดูทรัพยากรต่อไปนี้:

- [แหล่งข้อมูลที่ได้รับการสนับสนุนสำหรับรายงานที่มีการแบ่งหน้าของ Power BI](../paginated-reports/paginated-reports-data-sources.md)
- มีคำถามหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)
- มีข้อเสนอแนะไหม [สนับสนุนแนวคิดในการปรับปรุง Power BI](https://ideas.powerbi.com/)

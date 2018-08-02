---
title: เคล็ดลับและลูกเล่นสำหรับการถามคำถามด้วย ถามตอบใน Power BI
description: เคล็ดลับและลูกเล่นสำหรับการถามคำถามด้วย ถามตอบใน Power BI
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 01/18/2018
ms.author: jastru
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 0165eb7161e9ba931c336300f73316d215b1c88d
ms.sourcegitcommit: fbb7924603f8915d07b5e6fc8f4d0c7f70c1a1e1
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 08/02/2018
ms.locfileid: "34247081"
---
# <a name="tips-for-asking-questions-in-power-bi-qa"></a>เคล็ดลับสำหรับการถามคำถามใน ถามตอบ Power BI
## <a name="words-and-terminology-that-qa-recognizes"></a>คำและคำศัพท์ที่ถามตอบรู้จัก
รายการของคำสำคัญนี้ไม่ใช่รายการที่ครบถ้วน  วิธีดีที่สุดเพื่อดูว่า Power BI รู้จักคำสำคัญหรือไม่ คือทดลองใช้ โดยการพิมพ์ในกล่องคำถาม  ถ้าคำหรือคำศัพท์เป็นสีเทา แสดงว่า Power BI ไม่รู้จัก หรือไม่รู้จักในบริบทปัจจุบัน

รายการด้านล่างใช้กริยาช่องที่ 1 แต่มักจะรู้จักกริยาทุกช่องด้วย ตัวอย่างเช่น “is” จะรวมถึง are, was, were, will be, have, has, had, will have, has got, do, does, did  และ “sort” รวม sorted และ sorting  PowerBI ยังรู้จักคำในรูปเอกพจน์ และพหูพจน์ ตัวอย่างเช่น Power BI รู้จัก "year" และ "years"

> [!NOTE]
> ถามตอบยังมีใน[แอป Microsoft Power BI สำหรับ iOS บนอุปกรณ์ iPads, iPhones และ iPod Touch](mobile-apps-ios-qna.md)
> 
> 

ถ้าคุณเป็นเจ้าของชุดข้อมูล เพิ่มคำวลีและคำเหมือน เพื่อปรับปรุงผลลัพธ์การถามตอบสำหรับลูกค้าของคุณ

**การรวม**: total, sum, amount, number, quantity, count, average, most, least, fewest, largest, smallest, highest, biggest, maximum, max, greatest, lowest, littlest, minimum, min

**คำนำหน้านาม**: a, an, the

**ช่องว่างและบูลีน**: blank, empty, null, คำที่ขึ้นต้นด้วย “non” หรือ “non-“, empty string, empty text, true, t, false, f

**การเปรียบเทียบ**: vs, versus, compared to, compared with

**คำสันธาน**: and, or, each of, with, versus, &, and, but, nor, along with, in addition to

**การย่อคำ**: ถามตอบรู้จักการย่อคำเกือบทุกตัว ต้องลองดู  ต่อไปนี้เป็นตัวอย่าง: didn’t, haven’t, he’d, he’s, isn’t, it’s, she’ll, they’d, weren’t, where’ll, who’s, won’t, wouldn’t

**วันที่**: Power BI รู้จักคำเกี่ยวกับวันที่ (วday, week, month, year, quarter, decade ฯลฯ) และวันที่ที่เขียนในรูปแบบต่าง ๆ มากมาย (ดูด้านล่าง) Power BI ยังรู้จักคำสำคัญต่อไปนี้: ชื่อเดือน, Days 1-31, decade

ตัวอย่าง: January 3rd of 1995, January 3rd 1995, jan 03 1995, 3 Jan 1995, the 3rd of January, January 1995, 1995 January, 1995-01, 01/1995, names of months

**วันที่สัมพัทธ์**: today, right now, current time, yesterday, tomorrow, the current, next, the coming, last, previous, ago, before now, sooner than, after, later than, from, at, on, from now, after now, in the future, past, last, previous, within, in, over, N days ago, N days from now, next, once, twice

ตัวอย่าง: count of orders in the past 6 days.

**การเท่ากัน (ช่วง)**: in, equal to, =, after, is more than, in, between, before

ตัวอย่าง: Order year is before 2012? Price equals between 10 and 20? Is the age of John greater than 40? Total sales in 200-300?

**การเท่ากัน (ค่า)**:  is, equal, equal to, in, of, for, within, is in, is on

ตัวอย่าง: Which products are green? Order date equals 2012. Is the age of John 40? Total sales that is not equal to 200? Order date of 1/1/2016. 10 in price? Green for color? 10 in price?

**ชื่อ**: ถ้าคอลัมน์ในชุดข้อมูลมีคำว่า "name" อยู่ (เช่น EmployeeName) ถามตอบจะเข้าใจว่าค่าในคอลัมน์นั้นเป็นชื่อ และคุณสามารถถามคำถามเช่น "which employees are named robert."

**สรรพนาม**: he, him, himself, his, she, herself, her, hers, it, itself, its, they, their, them, themselves, theirs, this, these, that, those

**คำสั่งคิวรี**: sorted, sort by, direction, group, group by, by, show, list, display, give me, name, just, only, arrange, rank, compare, to, with, against, alphabetically, ascending, descending, order

**ช่วง**: greater, more, larger, above, over, >, less, smaller, fewer, below, under, <,  at least, no less than, >=, at most, no more than, <=, in, between, in the range of, from, later, earlier, sooner, after, on, at, later than, after, since, starting with, starting from, ending with

**เวลา**: am, pm, o'clock, noon, midnight, hour, minute, second, hh:mm:ss

ตัวอย่าง: 10 pm, 10:35 pm, 10:35:15 pm, 10 oclock, noon, midnight, hour, minute, second.

**N อันดับแรก** (เรียงลำดับ, จัดอันดับ): top, bottom, highest, lowest, first, last, next, earliest, newest, oldest, latest, most recent, next

**ชนิดของวิชวล**: วิชวลดั้งเดิมทุกชนิดใน Power BI.  ถ้าเป็นตัวเลือกในบานหน้าต่างการแสดงภาพ คุณสามารถรวมไว้ในคำถามของคุณได้  แต่มีข้อยกเว้นคือ[วิชวลแบบกำหนดเอง](power-bi-custom-visuals.md) ที่คุณได้เพิ่มไปยังบานหน้าต่างการแสดงภาพด้วยตนเอง

ตัวอย่าง: show districts by month and sales total as bar chart

**คำ Wh (ความสัมพันธ์, คุณสมบัติ)**: when, where, which, who, whom, how many, how much, how many times, how often, how frequently, amount, number, quantity, how long, what

## <a name="qa-helps-you-phrase-the-question"></a>ถามตอบช่วยให้คุณเรียบเรียงคำถาม
ถามตอบ จะทำดีที่สุดเพื่อให้แน่ใจว่า คำตอบได้สะท้อนคำถามที่ถามอย่างแม่นยำ ซึ่งจะทำโดยหลายวิธีด้วยกัน สำหรับทั้งหมดนี้ คุณสามารถยอมรับการดำเนินการทั้งหมด บางส่วน หรือไม่ยอมรับเลยก็ได้ ขณะที่คุณพิมพ์คำถามของคุณ ถามตอบจะ:

* ทำคำและคำถามให้สมบูรณ์โดยอัตโนมัติ ซึ่งใช้กลยุทธ์ต่าง ๆ รวมทั้งการใช้ คำที่รู้จัก คำถามที่นิยมถามกับเวิร์กบุ๊กพื้นฐาน และคำถามที่ใช้ก่อนหน้าที่ส่งกลับผลลัพธ์ที่ถูกต้อง เพื่อให้เป็นคำและคำถามที่สมบูรณ์อัตโนมัติ ถ้าตัวเลือกหลายตัวในการทำให้สมบูรณ์อัตโนมัติ จะแสดงในรายการดรอปดาวน์
* แก้ไขการสะกดคำ
* แสดงตัวอย่างของคำตอบในรูปแบบการแสดงภาพ การแสดงภาพจะปรับปรุงเมื่อคุณพิมพ์และแก้ไขคำถาม (โดยไม่รอให้คุณกด Enter)
* คำแนะนำอัตโนมัติ จะแทนที่คำศัพท์จากชุดข้อมูลเบื้องต้นเมื่อคุณย้ายเคอร์เซอร์กลับไปที่กล่องคำถาม
* เขียนคำถามใหม่ตามข้อมูลในชุดพื้นฐาน ซึ่งจะช่วยให้แน่ใจว่า ถามตอบเข้าใจคำถามของคุณ เมื่อถามตอบแทนที่คำที่คุณใช้ ด้วยคำเหมือนจากชุดข้อมูลพื้นฐาน
* หรี่คำที่ไม่เข้าใจความหมาย

## <a name="dont-stop-now"></a>อย่าพึ่งหยุด
หลังจากที่ถามตอบแสดงผลลัพธ์ของคุณแล้ว ดำเนินการสนทนาต่อไป ใช้คุณลักษณะที่โต้ตอบของการแสดงภาพ และถามตอบเพื่อเปิดเผยข้อมูลเชิงลึกเพิ่มเติม

## <a name="next-steps"></a>ขั้นตอนถัดไป
[กลับไปยัง Q&A ใน Power BI](power-bi-q-and-a.md)  

[Power BI - แนวคิดพื้นฐาน](service-basic-concepts.md)  

มีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


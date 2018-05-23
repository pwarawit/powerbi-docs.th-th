---
title: ข้อกำหนดฮาร์ดแวร์และซอฟต์แวร์สำหรับติดตั้งเซิร์ฟเวอร์รายงาน Power BI
description: ที่นี่คุณจะพบข้อกำหนดขั้นต่ำของฮาร์ดแวร์และซอฟต์แวร์เพื่อติดตั้งและเรียกใช้เซิร์ฟเวอร์รายงาน Power BI
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: 2963dbe2a5d1109e4396568624e16bf49d98da10
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/17/2018
---
# <a name="hardware-and-software-requirements-for-installing-power-bi-report-server"></a>ข้อกำหนดฮาร์ดแวร์และซอฟต์แวร์สำหรับติดตั้งเซิร์ฟเวอร์รายงาน Power BI
ที่นี่คุณจะพบข้อกำหนดขั้นต่ำของฮาร์ดแวร์และซอฟต์แวร์เพื่อติดตั้งและเรียกใช้เซิร์ฟเวอร์รายงาน Power BI

## <a name="processor-memory-and-operating-system-requirements"></a>ข้อกำหนดตัวประมวลผล หน่วยความจำ และระบบปฏิบัติการ
| คอมโพเนนต์ | ข้อกำหนด |
| --- | --- |
| .NET framework |4.6<br><br>คุณสามารถติดตั้ง.NET Framework จาก[Microsoft.NET Framework 4.6 (ตัวติดตั้งเว็บ) สำหรับ Windows](http://support.microsoft.com/kb/3045560)ได้ด้วยตนเอง<br/><br/> สำหรับข้อมูลเพิ่มเติมและคำแนะนำเกี่ยวกับ .NET Framework 4.6 ดู[คู่มือ .NET Framework Deployment สำหรับนักพัฒนา](http://msdn.microsoft.com/library/ee942965\(v=vs.110\).aspx)<br/><br/>Windows 8.1 และ Windows Server 2012 R2 จำเป็นต้องมี[KB2919355](http://support.microsoft.com/kb/2919355) ก่อนติดตั้ง.NET Framework 4.6 |
| ฮาร์ดดิสก์ |เซิร์ฟเวอร์รายงาน Power BI จำเป็นต้องมีเนื้อที่บนฮาร์ดดิสก์อย่างน้อย 1 กิกะไบต์<br><br>จะต้องเพิ่มเนื้อที่ว่างบนเซิร์ฟเวอร์ฐานข้อมูลที่โฮสต์ฐานข้อมูลของเซิร์ฟเวอร์รายงาน |
| หน่วยความจำ |**ต่ำสุด:** 1 GB<br/><br/> **แนะนำ:** อย่างน้อย 4 GB |
| ความเร็วในการประมวลผล |**ค่าต่ำสุด:** x64 ตัวประมวลผล: 1.4 GHz<br/><br/> **แนะนำ:** 2.0 GHz หรือเร็วกว่า |
| ชนิดตัวประมวลผล |x64 Processor: AMD Opteron, AMD Athlon 64, Xeon Intel with Intel EM64T support, IV Pentium Intel with EM64T support |
| ระบบปฏิบัติการ |Windows Server 2016 Datacenter<br><br>Windows Server 2016 Standard<br><br>Windows Server 2012 R2 Datacenter<br><br>Windows Server 2012 R2 Standard<br><br>Windows Server 2012 R2 Essentials<br><br>Windows Server 2012 R2 Foundation<br><br>Windows Server 2012 Datacenter<br><br>Windows Server 2012 Standard<br><br>Windows Server 2012 Essentials<br><br>Windows Server 2012 Foundation<br><br>Windows 10 Home<br><br>Windows 10 Professional<br><br>Windows 10 Enterprise<br><br>Windows 8.1<br><br>Windows 8.1 Pro<br><br>Windows 8.1 Enterprise<br><br>Windows 8<br><br>Windows 8 Pro<br><br>Windows 8 Enterprise |

> [!NOTE]
> สนับสนุนการติดตั้งของเซิร์ฟเวอร์รายงาน Power BI บนตัวประมวลผล x64 เท่านั้น
> 
> 

## <a name="database-server-version-requirements"></a>ข้อกำหนดเวอร์ชันของเซิร์ฟเวอร์ฐานข้อมูล
SQL Server ถูกใช้เพื่อโฮสต์ฐานข้อมูลของเซิร์ฟเวอร์รายงาน สามารถมีอินสแตนซ์ของเครื่องมือฐานข้อมูล SQL Server ภายในเครื่องหรือระยะไกล ต่อไปนี้เป็นรุ่นของเครื่องมือฐานข้อมูล SQL Server ที่สามารถใช้โฮสต์ฐานข้อมูลของเซิร์ฟเวอร์รายงาน:

* SQL Server 2017
* SQL Server 2016
* SQL Server 2014
* SQL Server 2012
* SQL Server 2008 R2
* SQL Server 2008

สร้างฐานข้อมูลของเซิร์ฟเวอร์รายงานที่คอมพิวเตอร์ระยะไกลจำเป็นต้องให้คุณกำหนดค่าการเชื่อมต่อเพื่อใช้บัญชีผู้ใช้โดเมนหรือบัญชีบริการที่มีการเข้าถึงเครือข่าย ถ้าคุณตัดสินใจที่จะใช้กับอินสแตนซ์ SQL Server ระยะไกล พิจารณาอย่างรอบคอบว่าเซิร์ฟเวอร์รายงานควรใช้ข้อมูลประจำตัวใดเพื่อเชื่อมต่อกับอินสแตนซ์ของ SQL Server สำหรับข้อมูลเพิ่มเติม ดู[กำหนดค่าการเชื่อมต่อฐานข้อมูลของเซิร์ฟเวอร์รายงาน](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-a-report-server-database-connection-ssrs-configuration-manager)

## <a name="considerations"></a>ข้อควรพิจารณา
เซิร์ฟเวอร์รายงาน Power BI จะติดตั้งค่าเริ่มต้นเป็นการตั้งค่าหลัก ซึ่งจำเป็นในการทำให้เซิร์ฟเวอร์รายงานสามารถใช้งานได้ มีข้อกำหนดดังต่อไปนี้:

* กลไกจัดการฐานข้อมูล SQL Server ต้องพร้อมใช้งานหลังจากการติดตั้งและก่อนที่คุณจะกำหนดค่าฐานข้อมูลสำหรับเซิร์ฟเวอร์รายงาน อินสแตนซ์ Database Engine จะโฮสต์ฐานข้อมูลของเซิร์ฟเวอร์รายงานที่ Reporting Services Configuration Manager เป็นผู้สร้าง Database Engine ไม่จำเป็นสำหรับการติดตั้งค่าจริง
* บัญชีผู้ใช้ที่ใช้รันการตั้งค่าต้องเป็นสมาชิกของกลุ่มผู้ดูแลระบบท้องถิ่น
* บัญชีผู้ใช้ที่ใช้สำหรับ Reporting Services Configuration Manager ต้องมีสิทธิ์ในการเข้าถึงและสร้างฐานข้อมูลบนอินสแตนซ์ Database Engine ที่โฮสต์ฐานข้อมูลของเซิร์ฟเวอร์รายงาน
* การติดตั้งต้องสามารถใช้ค่าเริ่มต้นเพื่อจอง URL ที่จะทำให้เข้าถึงเซิร์ฟเวอร์รายงานและพอร์ทัลเว็บ ค่าเหล่านี้คือพอร์ต 80 และอักขระตัวแทนที่คาดเดายาก และชื่อไดเรกทอรีเสมือนในรูปแบบ **ReportServer** และ**รายงาน**

## <a name="read-only-domain-controller-rodc"></a>ตัวควบคุมโดเมนแบบอ่านอย่างเดียว (RODC)
 ในขณะที่สามารถติดตั้งเซิร์ฟเวอร์รายงานในสภาพแวดล้อมที่มีตัวควบคุมโดเมนแบบอ่านอย่างเดียว (RODC), Reporting Services จำเป็นต้องเข้าถึงตัวควบคุมโดเมนแบบอ่าน-เขียนเพื่อให้ทำงานได้อย่างถูกต้อง ถ้า Reporting Services สามารถเข้าถึง RODC ได้เท่านั้นคุณอาจพบข้อผิดพลาดเมื่อพยายามจัดการบริการ

## <a name="power-bi-reports-and-analysis-services-live-connections"></a>การเชื่อมต่อสดของรายงาน Power BI และ Analysis Services
คุณสามารถใช้การเชื่อมต่อสดกับอินสแตนซ์ตารางหรืออินสแตนซ์หลายมิติ เซิร์ฟเวอร์ Analysis Services ของคุณต้องเป็นรุ่นและอิดิทชั่นที่เหมาะสมเพื่อให้ทำงานได้ดี

| **เวอร์ชันของเซิร์ฟเวอร์** | **SKU ที่จำเป็นต้องมี** |
| --- | --- |
| 2012 SP1 CU4 หรือใหม่กว่า |เทคโนโลยีสำหรับการรวบรวมข้อมูล จัดเก็บ วิเคราะห์ และการเข้าถึงข้อมูล รวมถึงการดูในหลากหลายมุมมอง (BI) และ SKU องค์กร |
| 2014 |Business Intelligence and Enterprise SKU |
| 2016 และเวอร์ชันที่ใหม่กว่า |SKU มาตรฐาน หรือสูงกว่า |

## <a name="next-steps"></a>ขั้นตอนถัดไป
[คู่มือผู้ใช้](user-handbook-overview.md)  
[คู่มือผู้ดูแลระบบ](admin-handbook-overview.md)  
[ติดตั้ง Power BI Report Server](install-report-server.md)  
[ติดตั้งตัวสร้างรายงาน](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[ดาวน์โหลด SQL Server Data Tools (SSDT)](http://go.microsoft.com/fwlink/?LinkID=616714)

มีคำถามเพิ่มเติมหรือไม่? [ลองถามชุมชน Power BI](https://community.powerbi.com/)


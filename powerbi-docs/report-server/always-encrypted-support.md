---
title: Always Encrypted ในเซิร์ฟเวอร์รายงาน Power BI
description: บทความนี้จะขยายความการรองรับ Always Encrypted ในเซิร์ฟเวอร์รายงาน Power BI เมื่อใช้แหล่งข้อมูลชนิด Microsoft SQL Server และฐานข้อมูล Microsoft Azure SQL
author: maggiesMSFT
ms.reviewer: cfinlan
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 01/22/2020
ms.author: maggies
ms.openlocfilehash: f8d711bba8dc7570f2d470554fd1d971639bbb7b
ms.sourcegitcommit: a1409030a1616027b138128695b80f6843258168
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/24/2020
ms.locfileid: "76710217"
---
# <a name="always-encrypted-in-power-bi-report-server"></a>Always Encrypted ในเซิร์ฟเวอร์รายงาน Power BI

บทความนี้จะขยายความการรองรับ Always Encrypted ในเซิร์ฟเวอร์รายงาน Power BI เมื่อใช้แหล่งข้อมูลชนิด Microsoft SQL Server และฐานข้อมูล Microsoft Azure SQL สำหรับข้อมูลเพิ่มเติมเกี่ยวกับความสามารถของ Always Encrypted ใน SQL Server ให้ดูที่บทความ [Always Encrypted](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine)

## <a name="always-encrypted-user-isolation"></a>การแยกผู้ใช้ของ Always Encrypted

ในขณะนี้ เซิร์ฟเวอร์รายงาน Power BI ไม่จำกัดการเข้าถึงคอลัมน์ Always Encrypted ในรายงานถ้าผู้ใช้มีสิทธิ์ในการเข้าถึงรายงาน  ดังนั้นหากเซิร์ฟเวอร์ได้รับอนุญาตให้เข้าถึงคีย์การเข้ารหัสของคอลัมน์ผ่านคีย์หลักของคอลัมน์ ผู้ใช้จะสามารถเข้าถึงคอลัมน์ทั้งหมดสำหรับรายงานที่พวกเขาสามารถเข้าถึงได้

## <a name="always-encrypted-column-usage"></a>การใช้งานคอลัมน์ Always Encrypted

### <a name="key-storage-strategies"></a>กลยุทธ์การจัดเก็บคีย์

|ที่เก็บข้อมูล  |สนับสนุน  |
|---------|---------|
|ที่เก็บใบรับรองของ Windows | ใช่ |
|Azure Key Vault | ไม่ใช่ |
| Cryptography Next Generation (CNG) | ไม่ใช่ |

### <a name="certificate-storage-and-access"></a>ที่เก็บใบรับรองและการเข้าถึง

บัญชีผู้ใช้ที่จำเป็นต้องมีสิทธิ์ในการเข้าถึงใบรับรองคือบัญชีบริการ ใบรับรองควรได้รับการจัดเก็บไว้ในที่เก็บใบรับรองของคอมพิวเตอร์เฉพาะที่ สำหรับข้อมูลเพิ่มเติม ให้ด:

- [กำหนดค่าบัญชีผู้ใช้บริการเซิร์ฟเวอร์รายงาน](https://docs.microsoft.com/sql/reporting-services/install-windows/configure-the-report-server-service-account-ssrs-configuration-manager) (ตัวจัดการการกำหนดค่า)
- หัวข้อ [การทำให้ใบรับรองพร้อมใช้งานสำหรับแอปพลิเคชันและผู้ใช้](https://docs.microsoft.com/sql/relational-databases/security/encryption/create-and-store-column-master-keys-always-encrypted#making-certificates-available-to-applications-and-users) ในบทความ SQL Server "สร้างและจัดเก็บคีย์หลักของคอลัมน์สำหรับ Always Encrypted"

### <a name="column-encryption-strategy"></a>กลยุทธ์การเข้ารหัสลับของคอลัมน์

ในเซิร์ฟเวอร์รายงาน Power BI กลยุทธ์การเข้ารหัสลับของคอลัมน์อาจเป็น *แบบเชิงกำหนด* หรือ *แบบสุ่ม* ตารางต่อไปนี้จะขยายความความแตกต่าง โดยขึ้นอยู่กับกลยุทธ์ที่ใช้

|ใช้  |แบบเชิงกำหนด  |แบบสุ่ม  |
|---------|---------|---------|
|สามารถอ่านได้ตามที่อยู่ในผลลัพธ์ของการคิวรี ตัวอย่างเช่น คำสั่ง SELECT | ใช่  | ใช่  |
|สามารถใช้เป็นเอนทิตี Group By ภายในคิวรีได้ | ใช่ | ไม่ใช่ |
|สามารถใช้เป็นเขตข้อมูลรวม ยกเว้นสำหรับ COUNT และ DISTINCT | ไม่ใช่ ยกเว้นสำหรับ COUNT และ DISTINCT | ไม่ใช่ |
|สามารถใช้เป็นพารามิเตอร์รายงาน | ใช่ | ไม่ใช่ |

อ่านเพิ่มเติมเกี่ยวกับ [การเข้ารหัสลับแบบเชิงกำหนดเทียบกับแบบสุ่ม](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine#selecting--deterministic-or-randomized-encryption)

### <a name="parameter-usage"></a>การใช้พารามิเตอร์

การใช้พารามิเตอร์จะใช้กับการเข้ารหัสแบบเชิงกำหนดเท่านั้น

**พารามิเตอร์ค่าเดียว**  คุณสามารถใช้พารามิเตอร์ค่าเดียวกับคอลัมน์ Always Encrypted ได้

**พารามิเตอร์แบบหลายค่า** คุณไม่สามารถใช้พารามิเตอร์แบบหลายค่าที่มีมากกว่าหนึ่งค่ากับคอลัมน์ Always Encrypted ได้

**พารามิเตอร์แบบเรียงซ้อน** คุณสามารถใช้พารามิเตอร์แบบเรียงซ้อนกับ Always Encrypted ถ้า *ทั้งหมด*ต่อไปนี้เป็นจริง:

- คอลัมน์ Always Encrypted ทั้งหมดต้องเป็น Always Encrypted ที่มีกลยุทธ์แบบเชิงกำหนด
- พารามิเตอร์ทั้งหมดที่ใช้กับคอลัมน์ Always Encrypted เป็นพารามิเตอร์ค่าเดียว
- การเปรียบเทียบ SQL ทั้งหมดใช้ตัวดำเนินการเท่ากับ (=)

## <a name="datatype-support"></a>การรองรับชนิดข้อมูล

| ชนิดข้อมูล SQL | รองรับเขตข้อมูลการอ่าน | รองรับการใช้เป็นองค์ประกอบ Group By | การรวมที่รองรับ (COUNT, DISTINCT, MAX, MIN, SUM, เป็นต้น) | รองรับการกรองผ่านความเท่ากันโดยใช้พารามิเตอร์ | บันทึกย่อ |
| --- | --- | --- | --- | --- | --- |
| int | ใช่ | ใช่ | COUNT, DISTINCT | ใช่ เป็นจำนวนเต็ม |   |
| เลขหลังจุดทศนิยมไม่จำกัด | ใช่ | ใช่ | COUNT, DISTINCT | ใช่ เป็นเลขหลังจุดทศนิยมไม่จำกัด |   |
| nvarchar | ใช่ | ใช่ | COUNT, DISTINCT | ใช่ เป็นข้อความ | การเข้ารหัสลับแบบเชิงกำหนดต้องใช้การเรียงลำดับคอลัมน์ที่มีลำดับการจัดเรียงแบบ binary2 สำหรับคอลัมน์อักขระ ดูบทความ [Always Encrypted](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine#selecting--deterministic-or-randomized-encryption) ของ SQL Server สำหรับรายละเอียด  |
| varchar | ใช่ | ใช่ | COUNT, DISTINCT | ไม่ใช่ |   |
| ทศนิยม | ใช่ | ใช่ | COUNT, DISTINCT | ไม่ใช่ |   |
| ตัวเลข | ใช่ | ใช่ | COUNT, DISTINCT | ไม่ใช่ |   |
| วันที่เวลา | ใช่ | ใช่ | COUNT, DISTINCT | ไม่ใช่ |   |
| datetime2 | ใช่ | ใช่ | COUNT, DISTINCT | ใช่ เป็นวันที่/เวลา | รองรับถ้าคอลัมน์ไม่มีความแม่นยำระดับมิลลิวินาที (อีกนัยหนึ่งคือไม่มี datetime2 (0)) |

## <a name="aggregation-alternatives"></a>ตัวเลือกการรวม

ในขณะนี้การรวมที่รองรับเพียงอย่างเดียวกับคอลัมน์ Always Encrypted แบบเชิงกำหนด คือการรวมที่ใช้ตัวดำเนินการเท่ากับ (=) โดยตรง ข้อจำกัด SQL Server นี้เกิดขึ้นเนื่องจากลักษณะของคอลัมน์ Always Encrypted ผู้ใช้ต้องรวมภายในรายงานแทนที่จะเป็นในฐานข้อมูล

## <a name="always-encrypted-in-connection-strings"></a>Always Encrypted ในสตริงการเชื่อมต่อ

คุณจำเป็นต้องเปิดใช้งาน Always Encrypted ในสตริงการเชื่อมต่อสำหรับแหล่งข้อมูล SQL Server อ่านเพิ่มเติมเกี่ยวกับการเปิดใช้งาน [Always Encrypted ในคิวรีแอปพลิเคชัน](https://docs.microsoft.com/sql/relational-databases/security/encryption/develop-using-always-encrypted-with-net-framework-data-provider#enabling-always-encrypted-for-application-queries)

## <a name="next-steps"></a>ขั้นตอนถัดไป

[Always Encrypted](https://docs.microsoft.com/sql/relational-databases/security/encryption/always-encrypted-database-engine) ในฐานข้อมูล SQL Server และ Azure SQL

มีคำถามเพิ่มเติมหรือไม่ [ลองถามชุมชน Power BI](https://community.powerbi.com/)


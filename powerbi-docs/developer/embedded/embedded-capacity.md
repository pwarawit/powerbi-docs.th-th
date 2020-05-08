---
title: ความจุและ SKU ในการวิเคราะห์แบบฝังตัวของ Power BI
description: เข้าใจเกี่ยวกับความจุและ SKU ในการวิเคราะห์แบบฝังตัวของ Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/11/2020
ms.openlocfilehash: 27d6ddd9b24e09805bd22150a22347e5cd93c8e0
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "79492847"
---
# <a name="capacity-and-skus-in-power-bi-embedded-analytics"></a>ความจุและ SKU ในการวิเคราะห์แบบฝังตัวของ Power BI

เมื่อย้ายไปที่การผลิต การวิเคราะห์แบบฝังตัวของ Power BI จำเป็นต้องมีความจุเฉพาะ (*A*, *EM* หรือ *P* SKU) สำหรับการเผยแพร่เนื้อหา Power BI แบบฝังตัว

ความจุเป็นชุดทรัพยากรเฉพาะที่สงวนไว้สำหรับการใช้งานแบบพิเศษ ทำให้คุณสามารถเเผยแพร่แดชบอร์ด รายงาน และชุดข้อมูลไปยังผู้ใช้ โดยไม่จำเป็นต้องซื้อสิทธิ์การใช้งานต่อผู้ใช้ นอกจากนี้ ยังนำเสนอประสิทธิภาพที่เชื่อถือได้และมีเสถียรภาพสำหรับเนื้อหาของคุณ

>[!NOTE]
>สำหรับการเผยแพร่ คุณต้องมีบัญชี Power BI Pro หนึ่งบัญชี

## <a name="what-is-embedded-analytics"></a>การวิเคราะห์แบบฝังตัวคืออะไร

การวิเคราะห์แบบฝังตัว Power BI มีโซลูชันสองแบบ:
* *Power BI Embedded*  - ข้อเสนอของ Azure
* การฝังตัว Power BI เป็นส่วนหนึ่งของ *Power BI Premium*  - ข้อเสนอของ Office

### <a name="power-bi-embedded"></a>Power BI ที่ฝังตัว

Power BI Embedded มีไว้สำหรับ ISV และนักพัฒนาที่ต้องการฝังภาพลงในแอปพลิเคชันของตน

แอปพลิเคชันที่ใช้ Power BI Embedded ทำให้ผู้ใช้สามารถใช้เนื้อหาที่จัดเก็บไว้ในความจุ Power BI Embedded

### <a name="power-bi-premium"></a>Power BI Premium

[Power BI Premium](../../service-premium-what-is.md) มีความจุที่ปรับให้เหมาะกับองค์กร ที่ต้องการโซลูชัน BI ที่สมบูรณ์ ที่ให้มุมมองเดียวกันแก่องค์กร คู่ค้า ลูกค้า และผู้จัดหาสินค้าขององค์กร

Power BI Premium เป็นผลิตภัณฑ์ SaaS ที่ให้ผู้ใช้สามารถใช้เนื้อหาผ่านทางแอปสำหรับอุปกรณ์เคลื่อนที่ แอปที่พัฒนาขึ้นเองภายใน หรือที่พอร์ทัล Power BI (บริการ Power BI) สิ่งนี้ทำให้ Power BI Premium มีโซลูชันสำหรับแอปพลิเคชันของลูกค้าทั้งภายในและภายนอก

## <a name="capacity-and-skus"></a>ความจุและ SKU

ความจุแต่ละแบบจะนำเสนอ SKU เฉพาะแบบ และ SKU แต่ละแบบจะนำเสนอเทียร์ทรัพยากรที่แตกต่างกันสำหรับหน่วยความจำและพลังในการประมวลผล ประเภทของ SKU ที่คุณต้องการ จะขึ้นอยู่กับประเภทโซลูชันที่คุณต้องการปรับใช้

เพื่อทำความเข้าใจปริมาณงานที่รองรับสำหรับแต่ละเทียร์ โปรดดูที่บทความ [กำหนดค่าปริมาณงานในกำลังการผลิตแบบ Premium](../../service-admin-premium-workloads.md)

ใช้ลิงก์นี้เพื่อ{1}วางแผนและทดสอบความจุของคุณ{2}
* [การวางแผนความจุ](embedded-capacity-planning.md)
* [การทดสอบวิธีการ](../../service-premium-capacity-optimize.md#testing-approaches)

### <a name="power-bi-embedded-skus"></a>SKU สำหรับ Power BI Embedded

Power BI Embedded จะถูกจัดส่งด้วย [*a* SKU](../../service-admin-premium-purchase.md#purchase-a-skus-for-testing-and-other-scenarios)

### <a name="power-bi-premium-skus"></a>Power BI Premium SKU

Power BI premium นำเสนอ SKU สองแบบคือ *P* และ *EM*
* [เข้าใจความแตกต่างระหว่าง *P* กับ *EM* SKU](../../service-premium-what-is.md#subscriptions-and-licensing)
* [ซื้อ Premium SKU](../../service-admin-premium-purchase.md)

### <a name="which-sku-should-i-use"></a>SKU ใดที่คุณควรใช้

ตารางนี้ระบุข้อมูลสรุปเกี่ยวกับคุณลักษณะ กำลังการผลิตที่จำเป็น และ SKU เฉพาะที่จำเป็นสำหรับแต่ละรายการ 

</br>
<table>
<col width="20%">
<col width="20%">
<col width="20%">
<col width="20%">
<col width="20%">
<tbody>
<tr>
<td style="text-align: center"; colspan="2"><p><b>คุณสมบัติ</b></p></td>
<td style="text-align: center">
<p><b>Power BI Embedded</b></p>
</td>
<td style="text-align: center"; colspan="2">
<p><b>Power BI Premium</b></p>
</td>
</tr>
<tr>
<td><p><em>อะไรถูกใช้</em><p></td>
<td><p><em>อะไรกำลังใช้</em><p></td>
<td style="text-align: center"><p><em>A SKU</br>(Azure)</em></p></td>
<td style="text-align: center"><p><em>EM SKU</br>(Office)</em></p></td>
<td style="text-align: center"><p><em>P SKU</br>(Office)</em></p></td>
</tr>
<tr>
<td>อาร์ทิแฟกต์แบบฝังตัวจากพื้นที่ทำงานPower BI</td>
<td>
</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td rowspan="2">รายงาน Power BI</td>
<td>แอปพลิเคชันแบบฝังตัวสำหรับองค์กรของคุณ</br>(ข้อมูลของผู้ใช้เอง)</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>แอปพลิเคชันแบบฝังตัวสำหรับลูกค้าของคุณ</br>(ข้อมูลชองแอป)</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td rowspan="3">เนื้อหา Power BI<br>(ด้วยสิทธิ์การใช้งาน Power BI ฟรี)</td>
<td>บริการ power BI</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>Power BI mobile</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
</tr>
<tr>
<td>แอป MS Office</td>
<td style="text-align: center">✖</td>
<td style="text-align: center">✔</td>
<td style="text-align: center">✔</td>
</tr>
</tbody>
</table>

### <a name="capacity-considerations"></a>ข้อควรพิจารณาเกี่ยวกับกำลังการผลิต

ตารางด้านล่างแสดงรายการข้อควรพิจารณาเกี่ยวกับการชำระเงินและการใช้งานต่อความจุ

</br>
<table>
<tbody>
<tr>
<td></td>
<td style="text-align: center;"><p><strong>Power BI Embedded</strong></p></td>
<td style="text-align: center;" colspan="2"><p><strong>Power BI Premium</strong></p></td>
</tr>
<tr>
<td><p><strong>ข้อเสนอ</strong></p></td>
<td style="text-align: center;"><p>Azure</p></td>
<td style="text-align: center;" colspan="2"><p>Office</p></td>
</tr>
<tr>
<td><p><strong>SKU</strong></p></td>
<td style="text-align: center;"><p>A</p></td>
<td style="text-align: center;"><p>EM</p></td>
<td style="text-align: center;"><p>P</p></td>
</tr>
<tr>
<td><p><strong>การเรียกเก็บเงิน</strong></td>
<td style="text-align: center;">รายชั่วโมง</td>
<td style="text-align: center;">รายเดือน</td>
<td style="text-align: center;">รายเดือน</td>
</tr>
<tr>
<td><p><strong>ข้อผูกมัด</strong></td>
<td style="text-align: center;">ไม่มี</td>
<td style="text-align: center;">รายปี</td>
<td style="text-align: center;">รายเดือนหรือรายปี</td>
</tr>
<tr>
<td valign="top"><p><strong>การใช้งาน</strong></td>
<td style="text-align: center;">ทรัพยากร Azure อาจเป็น:</br>- <a href="azure-pbie-scale-capacity.md">ปรับค่าสูงหรือลดลง</a></br>- <a href="azure-pbie-pause-start.md">หยุดชั่วคราวและทำต่อ</a>
</td>
<td style="text-align: center;">ฝังในแอปและใน</br> แอปพลิเคชัน Microsoft</td>
<td style="text-align: center;">ฝังในแอปและ</br> ในบริการ Power BI</td>
</tr>
</tbody>
</table>

### <a name="sku-memory-and-computing-power"></a>หน่วยความจำ SKU และกำลังสำหรับการประมวลผล

ตารางด้านล่างอธิบายแหล่งข้อมูลและขีดจำกัดของแต่ละ SKU

| โหนดความจุ | วี-คอร์รวม | Backend v-cores | RAM (GB) | Frontend v-cores | DirectQuery/Live Connection (ต่อวินาที) | การรีเฟรชแบบจำลองแบบคู่ขนาน |
| --- | --- | --- | --- | --- | --- | --- |
| EM1/A1 | 1 | 0.5 | 2.5 | 0.5 | 3.75 | 1 |
| EM2/A2 | 2 | 1 | 5 | 1 | 7.5 | 2 |
| EM3/A3 | 4 | 2 | 10 | 2 | 15 | 3 |
| P1/A4 | 8 | 4 | 25 | 4 | 30 | 6 |
| P2/A5 | 16 | 8 | 50 | 8 | 60 | 12 |
| P3/A6 | 32 | 16 | 100 | 16 | 120 | 24 |
| P4 | 64 | 32 | 200 | 32 | 240 | 48 |
| P5 | 128 | 64 | 400 | 64 | 480 | 96 |
| | | | | | | |

## <a name="next-steps"></a>ขั้นตอนถัดไป

> [!div class="nextstepaction"]
>[ฝังสำหรับลูกค้าของคุณ](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[ฝังตัวสำหรับองค์กรของคุณ](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [ฝังตัวจากแอป](embed-from-apps.md)
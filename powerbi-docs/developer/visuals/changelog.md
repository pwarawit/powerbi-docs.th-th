---
title: บันทึกการเปลี่ยนแปลง API ของวิชวล Power BI
description: บทความนี้อธิบายถึงการเปลี่ยนแปลงหลักในเวอร์ชันต่างๆ ของ  API ของวิชวล Power BI
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 03/13/2019
ms.openlocfilehash: 3cf415cbd14da28d523a042fdf4099fe464a4a8b
ms.sourcegitcommit: a07fa723bb459494c60cf6d749b4554af723482a
ms.contentlocale: th-TH
ms.lasthandoff: 06/12/2020
ms.locfileid: "84739195"
---
# <a name="power-bi-visuals-api-changelog"></a>บันทึกการเปลี่ยนแปลง API ของวิชวล Power BI
หน้านี้ประกอบด้วยข้อมูลสรุปสั้นๆ ของเวอร์ชัน  API เวอร์ชันที่แสดงที่นี่ถือว่าเป็นเวอร์ชันที่เสถียรและจะไม่มีการเปลี่ยนแปลง

## <a name="api-v320"></a>API v3.2.0
  * สนับสนุน **[supportsMultiVisualSelection](./supportsmultivisualselection-feature.md)**

## <a name="api-v260"></a>API v2.6.0
  * เพิ่ม **isInFocus** เพื่ออัปเดตตัวเลือกและวิธีการ **switchFocusModeState** ไปยังโฮสต์วิชวล
  * รองรับการปรับแต่ง **ผลรวมย่อย**

## <a name="api-v250"></a>API v2.5.0
  * รองรับ **[บานหน้าต่างการวิเคราะห์](./analytics-pane.md)**
  * รองรับวิธีการ `SelectionIdBuilder` **withMatrixNode** และ **withTable**
  * ไม่รองรับอินเทอร์เฟซ `DataRepetitionSelector` อีกต่อไป โดยแทนที่ด้วยอินเทอร์เฟซ `data.CustomVisualOpaqueIdentity`

## <a name="api-v230"></a>API v2.3.0
  * **[API หน้าเริ่มต้น](./landing-page.md)**
  * **[API ที่เก็บข้อมูลภายใน](./local-storage.md)**
  * **[API ตัวกรองทูเพิล (ตัวกรองหลายคอลัมน์)](./filter-api.md#the-tuple-filter-api-multi-column-filter)**
  * **[API เหตุการณ์การแสดงผล](./event-service.md#render-events-in-power-bi-visuals)**

## <a name="api-v220"></a>API v2.2.0
  * รองรับ **[การกู้คืนตัวกรอง JSON จาก DataView](./filter-api.md#restore-the-json-filter-from-the-data-view)**
  * **[API ContextMenu](./context-menu.md)**

## <a name="api-v210"></a>API v2.1.0
  * การปรับปรุงประสิทธิภาพการทำงาน:
    * เวลาโหลดเร็วขึ้น
    * ฟุตพริ้นท์หน่วยความจำที่มีขนาดเล็กลง
    * ข้อมูลและทรานแซคชันเหตุการณ์ที่ปรับอย่างเหมาะสม  

**บันทึกย่อประจำรุ่น**
* การกรอง API ที่สร้างขึ้นใหม่จะพร้อมใช้งานใน  API 2.2 และไม่ได้รับการรองรับใน  API 2.1
* วิชวลจะรับเฉพาะชนิด dataView ที่ได้รับการระบุในความสามารถเท่านั้น วิชวลที่ใช้ชนิด dataView หลายชนิดจะเสียหาย ซึ่งเป็นผลจากการอัปเดตนี้
* ไม่รองรับอินเทอร์เฟซ `DataViewScopeIdentity` อีกต่อไป โดยแทนที่ด้วยอินเทอร์เฟซ `data.DataRepetitionSelector` ถ้าคุณใช้คุณสมบัติหลักของอินเทอร์เฟซ `DataViewScopeIdentity` คุณสามารถแทนที่ด้วย `JSON.stringify(identity)`
* `undefined` ถูกแทนที่ด้วย `null` ภายใน dataView เมื่อมีการวนซ้ำในอาร์เรย์โดยใช้ `var item in myArray` จะเกิดการข้าม `undefined` แต่จะไม่ข้าม `null` วิชวลที่ใช้รูปแบบนี้อาจเสียหายจากการอัปเดตนี้ ตรวจดูให้แน่ใจว่าได้ตรวจสอบ `null` ในอาร์เรย์:
   ```typescript
   for (var item in myArray) {
     if (!item) {
       continue;
     }
     console.log(item);
   }
   ```
* คุณสมบัติ `proto` ไม่จัดเก็บ metadata\data ที่ซ่อนไว้ภายใน dataView อีกต่อไป วิชวลที่สามารถเข้าถึงคุณสมบัติผ่าน `proto` อาจเสียหายจากการอัปเดตนี้

## <a name="api-v1130"></a>API v1.13.0
* รองรับ **[ตัวแบ่งส่วนข้อมูลการซิงค์](./enable-sync-slicers.md)** โปรดทราบว่าจะใช้ได้เฉพาะตัวแบ่งส่วนเขตข้อมูลเดี่ยว เนื่องจาก PBI สถานะของโค้ดปัจจุบัน [อ่านเพิ่มเติม](/power-bi/desktop-slicers)
* การเข้าถึง: [รองรับความคมชัดสูง](./high-contrast-support.md) 
* การเข้าถึง: อนุญาตให้มีการตั้งค่าสถานะโฟกัสของแป้นพิมพ์

## <a name="api-v1120"></a>API v1.12.0
* รองรับธีม
* รองรับ **[fetchMoreData](./fetch-more-data.md)** โปรดทราบว่า **Fetch More Data API** เอาชนะขีดจำกัดสูงสุดของจุดข้อมูลที่ 30K
* **[API คำแนะนำเครื่องมือของ Canvas](./add-tooltips.md#add-report-page-tooltips)**

## <a name="api-v1110"></a>API v1.11.0
* **[ API FilterManager](./filter-api.md)**
* รองรับ **[บุ๊กมาร์ก](./bookmarks-support.md)** 

## <a name="api-v1100"></a>API v1.10.0
* เพิ่ม `ILocalizationManager`
* **API การรับรองความถูกต้อง**

## <a name="api-v190"></a>API v1.9.0
* **[API launchUrl](./launch-url.md)**

## <a name="api-v180"></a>API v1.8.0
* รองรับ **fillRule** ชนิดใหม่ (การไล่ระดับสี) ใน schema ความสามารถ
* รองรับคุณสมบัติ **กฎ** ใน schema ความสามารถสำหรับคุณสมบัติวัตถุ

## <a name="api-v170"></a>API v1.7.0
* รองรับ **[RESJSON](./localization.md#resource-file)**

## <a name="api-v162"></a>API  v1.6.2
* รองรับ **[โหมดแก้ไข](./advanced-edit-mode.md)** สำหรับวิชวลเพื่อเข้าสู่โหมดแก้ไขในวิชวล
* รองรับ **[วิชวล R Power BI แบบโต้ตอบ (html)](https://microsoft.github.io/PowerBI-visuals/tutorials/building-r-powered-custom-visual/creating-r-visuals.md)** โดยอ้างอิงตาม html

## <a name="api-v150"></a>API v1.5.0
* รองรับ **[อนุญาตให้มีการโต้ตอบ](./visuals-interactions.md)** สำหรับความสามารถในการโต้ตอบของวิชวล

## <a name="api-v140"></a>API v1.4.0
* รองรับ **[การแปลเป็นภาษาท้องถิ่น](./localization.md)**

## <a name="api-v130"></a>API v1.3.0
* รองรับ **[คำแนะนำเครื่องมือ](./add-tooltips.md)**

## <a name="api-v120"></a>API v1.2.0
* เพิ่ม **colorPalette** เพื่อจัดการสีที่ใช้ในวิชวลของคุณ
* รองรับ **การเลือกหลายรายการ** - selectionManager สามารถยอมรับอาร์เรย์ของ `SelectionId`
* รองรับ **[วิชวล R](https://microsoft.github.io/PowerBI-visuals/tutorials/building-r-powered-custom-visual/creating-r-visuals.md)** โดยใช้สคริปต์ R

## <a name="api-v110"></a>API v1.1.0
* รองรับการแก้จุดบกพร่องของวิชวลใน iFrame
* เพิ่ม Sandbox น้ำหนักเบาด้วยการเตรียมใช้งาน iFrame ที่รวดเร็วขึ้น
* แก้ไขปัญหา [Capabilities.objects ไม่รองรับชนิด "ข้อความ"](https://github.com/Microsoft/PowerBI-visuals-tools/issues/12)
* รองรับ `pbiviz update` เพื่ออัปเดตข้อกำหนดชนิด API ของวิชวลและ schema
* รองรับค่าสถานะ `--api-version` ใน `pbiviz new` เพื่อสร้างวิชวลด้วยเวอร์ชัน api เฉพาะ
* รองรับ Alpha Release ของ API v1.2.0

**โฮสต์วิชวล**
* เพิ่ม **createSelectionIdBuilder** เพื่อสร้างรหัสเฉพาะที่ใช้สำหรับการเลือกข้อมูล
* เพิ่ม **createSelectionManager** เพื่อจัดการสถานะการเลือกของวิชวลและการสื่อสารเกี่ยวกับการเปลี่ยนแปลงกับโฮสต์วิชวล
* เพิ่มอาร์เรย์ของค่าเริ่มต้น **สี** เพื่อใช้ในวิชวล

## <a name="api-v100"></a>API v1.0.0
* การเผยแพร่ API เริ่มต้น

---
title: นำคีย์การเข้ารหัสลับของคุณเองสำหรับ Power BI (ตัวอย่าง)
description: เรียนรู้วิธีการใช้คีย์การเข้ารหัสลับของคุณเองใน Power BI Premium
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 06/10/2019
LocalizationGroup: Premium
ms.openlocfilehash: 7adcfeec771796aa9fe322512f8ca8584559cea0
ms.sourcegitcommit: c122c1a8c9f502a78ccecd32d2708ab2342409f0
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/11/2019
ms.locfileid: "66829399"
---
# <a name="bring-your-own-encryption-keys-for-power-bi-preview"></a>นำคีย์การเข้ารหัสลับของคุณเองสำหรับ Power BI (ตัวอย่าง)

Power BI เข้ารหัสลับข้อมูล_ที่พัก_และ_ระหว่างดำเนินการ_ ตามค่าเริ่มต้น Power BI ใช้คีย์ที่จัดการโดย Microsoft เพื่อเข้ารหัสลับข้อมูลของคุณ ใน Power BI Premium คุณยังสามารถใช้คีย์ของคุณเองสำหรับข้อมูลที่พักไว้ที่นำเข้าลงในชุดข้อมูล (ดู[ข้อควรพิจารณาเกี่ยวกับแหล่งข้อมูลและที่เก็บข้อมูล](#data-source-and-storage-considerations)สำหรับข้อมูลเพิ่มเติม) ได้ วิธีนี้จะอธิบายไว้มักจะเป็น_การนำคีย์ของคุณมาใช้เอง_(Bring Your Own Key, BYOK)

## <a name="why-use-byok"></a>เหตุใดจึงใช้ BYOK

BYOK ทำให้ง่ายต่อการปฏิบัติตามข้อกำหนดที่ระบุการจัดการคีย์ด้วย Cloud Service Provider (ในกรณีนี้คือ Microsoft) ด้วย BYOK คุณจะสามารถระบุและควบคุมคีย์การเข้ารหัสลับสำหรับข้อมูล Power BI ที่พักไว้ในระดับแอปพลิเคชัน ดังนั้น คุณสามารถควบคุมและยกเลิกคีย์ขององค์กรของคุณ คุณควรตัดสินใจเพื่อออกจากบริการ เมื่อยกเลิกคีย์ ข้อมูลจะไม่สามารถอ่านได้ในบริการ

## <a name="data-source-and-storage-considerations"></a>ข้อควรพิจารณาเกี่ยวกับแหล่งข้อมูลและที่เก็บข้อมูล

หากต้องการใช้ BYOK คุณต้องอัปโหลดข้อมูลในบริการของ Power BI จากไฟล์ Power BI Desktop (PBIX) เมื่อคุณเชื่อมต่อกับแหล่งข้อมูลใน Power BI Desktop คุณต้องระบุโหมดที่เก็บข้อมูลในการนำเข้าของคุณ คุณไม่สามารถใช้ BYOK ในสถานการณ์ต่อไปนี้:

- DirectQuery
- การเชื่อมต่อแบบออนไลน์ของ Analysis Services
- เวิร์กบุ๊ก Excel (เว้นแต่ว่าข้อมูลจะถูกนำเข้าลงใน Power BI Desktop ก่อน)
- ส่งชุดข้อมูล

ในส่วนถัดไป คุณจะได้เรียนรู้วิธีการกำหนดค่า Azure Key Vault ซึ่งเป็นที่ที่คุณจัดเก็บคีย์การเข้ารหัสลับสำหรับ BYOK

## <a name="configure-azure-key-vault"></a>กำหนดค่า Azure Key Vault

Azure Key Vault เป็นเครื่องมือเพื่อจัดเก็บและเข้าถึงความลับ้อย่างปลอดภัย เช่น คีย์การเข้ารหัสลับ คุณสามารถใช้ Key Vault ที่มีอยู่เพื่อจัดเก็บคีย์การเข้ารหัสลับ หรือคุณสามารถสร้างขึ้นใหม่โดยเฉพาะเพื่อใช้กับ Power BI

คำแนะนำในส่วนนี้ถือว่าเป็นความรู้พื้นฐานของ Azure Key Vault สำหรับข้อมูลเพิ่มเติม โปรดดูที่[Azure Key Vault คืออะไร](/azure/key-vault/key-vault-whatis) กำหนดค่า Key Vault ของคุณในวิธีต่อไปนี้:

1. เพิ่มบริการของ Power BI เป็นโครงร่างสำคัญของบริการสำหรับ Key Vault ด้วยสิทธิ์การครอบและยกเลิกการครอบ

1. สร้างคีย์ RSA ที่มีความยาว 4096 บิต (หรือใช้คีย์ที่มีอยู่ของชนิดนี้) ด้วยสิทธิ์การครอบและยกเลิกการครอบ

1. แนะนำ: ตรวจสอบว่า Key Vault มีการเปิดใช้งานตัวเลือก_ลบชั่วคราว_หรือไม่

### <a name="add-the-service-principal"></a>เพิ่มโครงร่างสำคัญของบริการ

1. ในพอร์ทัล Azure ใน Key Vault ของคุณ ภายใต้**นโยบายการเข้าถึง** ให้เลือก**เพิ่มใหม่**

1. ภายใต้**เลือกรายการหลัก** ค้นหาและเลือก Microsoft.Azure.AnalysisServices

1. ภายใต้**สิทธิ์คีย์** เลือก**ยกเลิกการครอบคีย์**และ**ครอบคีย์**

    ![คอมโพเนนต์ไฟล์ PBIX](media/service-encryption-byok/service-principal.png)

1. เลือก**ตกลง** แล้ว**บันทึก**

### <a name="create-an-rsa-key"></a>สร้างคีย์ RSA

1. ใน Key Vault ของคุณ ภายใต้**คีย์** เลือก**สร้าง/นำเข้า**

1. เลือก **ประเภทคีย์** ของ RSA และ**ขนาดคีย์ RSA**คือ 4096

    ![คอมโพเนนต์ไฟล์ PBIX](media/service-encryption-byok/create-rsa-key.png)

1. เลือก **สร้าง**

1. ภายใต้**คีย์** เลือกคีย์ที่คุณสร้างขึ้น

1. เลือก GUID สำหรับคีย์**รุ่นปัจจุบัน**

1. ตรวจสอบว่า ได้เลือกทั้ง **ครอบคีย์**และ**ยกเลิกการครอบคีย์** คัดลอก**รหัสคีย์**ที่จะใช้เมื่อคุณเปิดใช้งาน BYOK ใน Power BI

    ![คอมโพเนนต์ไฟล์ PBIX](media/service-encryption-byok/key-properties.png)

### <a name="soft-delete-option"></a>ลบตัวเลือกชั่วคราว

เราขอแนะนำให้คุณเปิดใช้งาน [ลบชั่วคราว](/azure/key-vault/key-vault-ovw-soft-delete)บน Key Vault ของคุณ เพื่อป้องกันข้อมูลสูญหายในกรณีที่มีการลบคีย์หรือ Key Vault โดยไม่ได้ตั้งใจ คุณต้องใช้ [PowerShell เพื่อเปิดใช้งานคุณสมบัติ "ลบชั่วคราว"](/azure/key-vault/key-vault-soft-delete-powershell) บน Key Vault เนื่องจากตัวเลือกนี้ยังไม่พร้อมใช้งานจากพอร์ทัล Azure

เมื่อมีการกำหนดค่า Azure Key Vault อย่างถูกต้อง คุณก็พร้อมที่จะเปิดใช้งาน BYOK บนผู้เช่าของคุณ

## <a name="enable-byok-on-your-tenant"></a>เปิดใช้งาน BYOK บนผู้เช่าของคุณ

คุณเปิดใช้งาน BYOK ในระดับผู้เช่าด้วย PowerShell โดยการแนะนำคีย์การเข้ารหัสลับที่คุณสร้างและจัดเก็บไว้ใน Azure Key Vault ครั้งแรกให้กับผู้เช่า Power BI ของคุณผู้เช่า จากนั้นกำหนดคีย์การเข้ารหัสลับเหล่านี้ต่อความจุพรีเมียมสำหรับการเข้ารหัสเนื้อหาในความจุ

### <a name="important-considerations"></a>ข้อควรพิจารณาที่สำคัญ

ก่อนที่คุณเปิดใช้งาน BYOK ควรคำนึงถึงข้อควรพิจารณาต่อไปนี้:

- ในขณะนี้ คุณไม่สามารถปิดใช้งาน BYOK หลังจากที่คุณเปิดใช้งานได้ ขึ้นอยู่กับวิธีที่คุณระบุพารามิเตอร์สำหรับ`Add-PowerBIEncryptionKey` คุณสามารถควบคุมวิธีที่คุณใช้ BYOK สำหรับความจุอย่างน้อยหนึ่งรายการ อย่างไรก็ตาม คุณไม่สามารถยกเลิกการแนะนำคีย์ไปยังผู้เช่าของคุณได้ สำหรับข้อมูลเพิ่มเติม ให้ดู [เปิดใช้งาน BYOK](#enable-byok)

- คุณไม่สามารถย้ายพื้นที่ทำงานที่ใช้ BYOK ได้_โดยตรง_จากความจุเฉพาะใน Power BI Premium ไปยังความจุที่แชร์ ก่อนอื่น คุณต้องย้ายพื้นที่ทำงานไปยังความจุเฉพาะที่ไม่ได้เปิดใช้งาน BYOK

### <a name="enable-byok"></a>เปิดใช้งาน BYOK

หากต้องการเปิดใช้งาน BYOK คุณต้องเป็นผู้ดูแลระบบของผู้เช่าสหรับบริการของ Power BI ลงชื่อเข้าใช้โดยใช้ cmdlet`Connect-PowerBIServiceAccount` จากนั้น ใช้`Add-PowerBIEncryptionKey`เพื่อเปิดใช้งาน BYOK ดังที่แสดงในตัวอย่างต่อไปนี้:

```powershell
Add-PowerBIEncryptionKey -Name'Contoso Sales' -KeyVaultKeyUri'https://contoso-vault2.vault.azure.net/keys/ContosoKeyVault/b2ab4ba1c7b341eea5ecaaa2wb54c4d2'
```

cmdlet ยอมรับพารามิเตอร์สลับสามรายการที่ส่งผลต่อการเข้ารหัสลับสำหรับความจุปัจจุบันและในอนาคต ตามค่าเริ่มต้น ไม่มีการตั้งค่าการสลับ:

- `-Activate`: ระบุว่า จะใช้คีย์นี้สำหรับความจุที่มีอยู่ทั้งหมดในผู้เช่าหรือไม่

- `-Default`: ระบุว่า คีย์นี้เป็นค่าเริ่มต้นสำหรับผู้เช่าทั้งหมดในขณะนี้หรือไม่ เมื่อคุณสร้างความจุใหม่ ความจุจะรับคีย์นี้มา

- `-DefaultAndActivate`: ระบุว่า จะใช้คีย์นี้สำหรับความจุที่มีอยู่ทั้งหมดและความจุใหม่ที่คุณสร้างหรือไม่

ถ้าคุณระบุ `-Default` หรือ `-DefaultAndActivate` ความจุทั้งหมดที่สร้างขึ้นในผู้เช่านี้จากจุดนี้จะถูกเข้ารหัสลับโดยใช้คีย์ที่คุณระบุ (หรือคีย์เริ่มต้นที่อัปเดต) คุณไม่สามารถยกเลิกการดำเนินการเริ่มต้นได้ คุณจึงไม่สามารถสร้างความจุพรีเมียมที่ไม่ได้ใช้ BYOK ในผู้เช่าของคุณ

คุณสามารถควบคุมวิธีที่คุณใช้ BYOK ในผู้เช่าของคุณ ตัวอย่างเช่น ในการเข้ารหัสลับความจุเดียว เรียกใช้ `Add-PowerBIEncryptionKey` โดยไม่มี`-Activate`, `-Default` หรือ `-DefaultAndActivate` จากนั้น เรียกใช้ `Set-PowerBICapacityEncryptionKey` สำหรับความจุที่คุณต้องการเปิดใช้งาน BYOK

## <a name="manage-byok"></a>จัดการ BYOK

Power BI มี cmdlet เพิ่มเติมเพื่อช่วยจัดการ BYOK ในผู้เช่าของคุณ:

- ใช้ `Get-PowerBIEncryptionKey` เพื่อรับคีย์ที่ผู้เช่าของคุณกำลังใช้งาน:

    ```powershell
    Get-PowerBIEncryptionKey
    ```

- ใช้ `Get-PowerBIWorkspaceEncryptionStatus` เพื่อดูว่ามีการเข้ารหัสชุดข้อมูลในพื้นที่ทำงานหรือไม่และสถานะการเข้ารหัสลับซิงค์กับพื้นที่ทำงานหรือไม่:

    ```powershell
    Get-PowerBIWorkspaceEncryptionStatus -Name'Contoso Sales'
    ```

    โปรดทราบว่ามีการเปิดใช้งานการเข้ารหัสลับที่ระดับความจุ แต่คุณได้รับสถานะการเข้ารหัสลับที่ระดับชุดข้อมูลสำหรับพื้นที่ทำงานที่ระบุ

- ใช้ `Set-PowerBICapacityEncryptionKey` เพื่ออัปเดตคีย์การเข้ารหัสลับสำหรับความจุ Power BI:

    ```powershell
    Set-PowerBICapacityEncryptionKey-CapacityId 08d57fce-9e79-49ac-afac-d61765f97f6f -KeyName 'Contoso Sales'
    ```

- `Use Switch-PowerBIEncryptionKey` เพื่อสลับ (หรือ_หมุน_) คีย์ที่ใช้ในขณะน้ีสำหรับการเข้ารหัสลับ cmdlet เพียงแค่อัปเดต `-KeyVaultKeyUri` สำหรับคีย์ `-Name`:

    ```powershell
    Switch-PowerBIEncryptionKey -Name'Contoso Sales' -KeyVaultKeyUri'https://contoso-vault2.vault.azure.net/keys/ContosoKeyVault/b2ab4ba1c7b341eea5ecaaa2wb54c4d2'
    ```
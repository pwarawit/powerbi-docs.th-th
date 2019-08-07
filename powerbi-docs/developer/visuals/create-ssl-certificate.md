---
title: การสร้างใบรับรอง SSL
description: แก้ไขคำแนะนำเพื่อสร้างใบรับรองด้วยตนเองสำหรับเซิร์ฟเวอร์สำหรับนักพัฒนา
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 06/18/2019
ms.openlocfilehash: 3287e8a7eb1c36c3f0d8a1fc24faa0442de2dddf
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425447"
---
# <a name="creating-ssl-certificate"></a>การสร้างใบรับรอง SSL

เรียกใช้คำสั่งต่อไปนี้เพื่อสร้างใบรับรองโดยใช้ cpowershell New-SelfSignedCertificate cmdlet บน Windows 8 หรือสูงกว่า

เครื่องมือต้องการการติดตั้ง OpenSSL สำหรับ **Windows** **7** Util `openssll`ต้องพร้อมใช้งานจากบรรทัดคำสั่ง

สำหรับการติดตั้ง OpenSSL เยี่ยมชม [https://www.openssl.org](https://www.openssl.org) หรือ [https://wiki.openssl.org/index.php/Binaries](https://wiki.openssl.org/index.php/Binaries)

```cmd
pbiviz --create-cert
```

## <a name="create-certificate-mac-os-x"></a>สร้างใบรับรอง (Mac OS X)

มักจะพร้อมใช้งาน OpenSSL utils ในระบบปฏิบัติการ Linux หรือ Mac OS X

มิฉะนั้นคุณสามารถติดตั้งจาก

ตัวจัดการแพ็คเกจ *Brew*

```cmd
brew install openssl
brew link openssl --force
```

หรือโดยใช้ *MacPorts*

```cmd
sudo port install openssl
```

หลังจากการติดตั้ง OpenSSL สำหรับการสร้างการเรียกใช้ใบรับรองใหม่:

```cmd
pbiviz --create-cert
```

## <a name="create-certificate-linux"></a>สร้างใบรับรอง (Linux)

OpenSSL utils ไม่พร้อมใช้งานในระบบปฏิบัติการ Linux ของคุณ คุณสามารถติดตั้งโดยใช้คำสั่งต่อไปนี้

สำหรับตัวจัดการแพ็คเกจ *APT*:

```cmd
sudo apt-get install openssl
```

สำหรับ *โปรแกรมอัปเดต Yellowdog*:

```cmd
yum install openssl
```

สำหรับ *ตัวจัดการแพ็คเกจ Redhat*:

```cmd
rpm install openssl
```

ถ้า OpenSSl มีอยู่แล้วในการเรียกใช้ระบบปฏิบัติการของคุณ

```cmd
pbiviz --create-cert
```

เพื่อสร้างใบรับรองใหม่

หรือรับจาก [https://www.openssl.org](https://www.openssl.org) หรือ [https://wiki.openssl.org/index.php/Binaries](https://wiki.openssl.org/index.php/Binaries)

## <a name="generate-certificate-manually"></a>สร้างใบรับรองด้วยตนเอง

คุณสามารถระบุใบรับรองที่สร้างขึ้นโดยเครื่องมือใด ๆ

ถ้าคุณติดตั้ง OpenSSL ในระบบของคุณแล้ว คุณสามารถเรียกใช้คำสั่งต่อไปนี้เพื่อสร้างใบรับรองใหม่

```cmd
openssl req -x509 -newkey rsa:4096 -keyout PowerBICustomVisualTest_private.key -out PowerBICustomVisualTest_public.crt -days 365
```

โดยปกติแล้ว ใบรับรองเซิร์ฟเวอร์เว็บ PowerBI-visuals-tools จะอยู่ที่

```cmd
%appdata%\npm\node_modules\PowerBI-visuals-tools\certs
```

สำหรับอินสแตนซ์ส่วนกลางของเครื่องมือ

หรือ

```cmd
<custom visual project root>\node_modules\PowerBI-visuals-tools\certs
```

สำหรับอินสแตนซ์เฉพาะที่ของเครื่องมือ

คุณควรบันทึกไฟล์ใบรับรองเป็น `PowerBICustomVisualTest_public.cer` และคีย์ส่วนตัวตาม`PowerBICustomVisualTest_public.key`ที่คุณใช้รูปแบบ PEM
บันทึกไฟล์ใบรับรอง `PowerBICustomVisualTest_public.pfx` หากคุณใช้รูปแบบ PFX

ถ้าไฟล์ใบรับรอง PFX ของคุณจำเป็นต้องใช้วลีรหัสผ่าน คุณควรระบุใน

```cmd
\PowerBI-visuals-tools\config.json
```

ที่ส่วนของเซิร์ฟเวอร์:

```cmd
"server":{
    "root":"webRoot",
    "assetsRoute":"/assets",
    "privateKey":"certs/PowerBICustomVisualTest_private.key",
    "certificate":"certs/PowerBICustomVisualTest_public.crt",
    "pfx":"certs/PowerBICustomVisualTest_public.pfx",
    "port":"8080",
    "passphrase":"YOUR PASSPHRASE"
}
```

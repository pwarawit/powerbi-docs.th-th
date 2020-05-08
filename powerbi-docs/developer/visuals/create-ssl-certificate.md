---
title: สร้างใบรับรอง SSL
description: แก้ไขคำแนะนำเพื่อสร้างใบรับรองด้วยตนเองสำหรับเซิร์ฟเวอร์สำหรับนักพัฒนา
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: fab40863d7beae4892a56975aa5e92c4fe5486ac
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "79380283"
---
# <a name="create-an-ssl-certificate"></a>สร้างใบรับรอง SSL

บทความนี้อธิบายวิธีการสร้างใบรับรอง SSL

หากต้องการสร้างใบรับรองโดยใช้ PowerShell `New-SelfSignedCertificate` cmdlet บน Windows 8 หรือใหม่กว่า ให้เรียกใช้คำสั่งต่อไปนี้:

```cmd
pbiviz --install-cert
```

เครื่องมือต้องการการติดตั้ง OpenSSL สำหรับ Windows 7 ยูทิลิตี้ OpenSSL ต้องพร้อมใช้งานจากบรรทัดคำสั่ง (command line)

หากต้องการติดตั้ง OpenSSL ให้ไปที่เว็บไซต์ [OpenSSL](https://www.openssl.org) หรือ [OpenSSL Binaries](https://wiki.openssl.org/index.php/Binaries)

## <a name="create-a-certificate-mac-os-x"></a>สร้างใบรับรอง (Mac OS X)

โดยทั่วไปแล้วยูทิลิตี้ OpenSSL จะพร้อมใช้งานในระบบปฏิบัติการ Linux หรือ Mac OS X

คุณยังสามารถติดตั้งยูทิลิตี้นี้ได้โดยการเรียกใช้คำสั่งต่อไปนี้:

* จากตัวจัดการแพ็คเกจ *Brew*

    ```cmd
    brew install openssl
    brew link openssl --force
    ```

* โดยใช้ *MacPorts*:

    ```cmd
    sudo port install openssl
    ```

หลังจากที่คุณติดตั้งยูทิลิตี้ OpenSSL สำหรับสร้างใบรับรองใหม่แล้ว ให้เรียกใช้คำสั่งต่อไปนี้:

```cmd
pbiviz --install-cert
```

## <a name="create-a-certificate-linux"></a>สร้างใบรับรอง (Linux)

ถ้ายูทิลิตี้ OpenSSL ไม่พร้อมใช้งานในระบบปฏิบัติการ Linux ของคุณ คุณสามารถติดตั้งโดยใช้คำสั่งใดคำสั่งหนึ่งต่อไปนี้:

* สำหรับตัวจัดการแพ็คเกจ *APT*:

    ```cmd
    sudo apt-get install openssl
    ```

* สำหรับ *โปรแกรมอัปเดต Yellowdog*:

    ```cmd
    yum install openssl
    ```

* สำหรับ *ตัวจัดการแพ็คเกจ Redhat*:

    ```cmd
    rpm install openssl
    ```

ถ้ายูทิลิตี้ OpenSSL พร้อมใช้งานในระบบปฏิบัติการของคุณแล้ว ให้สร้างใบรับรองใหม่โดยการเรียกใช้คำสั่งต่อไปนี้:

```cmd
pbiviz --install-cert
```

หรือคุณสามารถรับยูทิลิตี้ OpenSSL ได้โดยไปยังเว็บไซต์ [OpenSSL](https://www.openssl.org) หรือ [OpenSSL Binaries](https://wiki.openssl.org/index.php/Binaries)

## <a name="generate-the-certificate-manually"></a>สร้างใบรับรองด้วยตนเอง

คุณสามารถระบุว่าใบรับรองสร้างขึ้นโดยเครื่องมือใด ๆ

ถ้ามีการติดตั้งยูทิลิตี้ OpenSSL เรียบร้อยแล้วในระบบของคุณ ให้สร้างใบรับรองใหม่โดยการเรียกใช้คำสั่งต่อไปนี้:

```cmd
openssl req -x509 -newkey rsa:4096 -keyout PowerBICustomVisualTest_private.key -out PowerBICustomVisualTest_public.crt -days 365
```

โดยทั่วไปแล้วคุณสามารถค้นหาใบรับรองเว็บเซิร์ฟเวอร์ PowerBI-visuals-tools ได้โดยเรียกใช้คำสั่งใดคำสั่งหนึ่งต่อไปนี้:

* สำหรับอินสแตนซ์ส่วนกลางของเครื่องมือ:

    ```cmd
    %appdata%\npm\node_modules\PowerBI-visuals-tools\certs
    ```

* สำหรับอินสแตนซ์เฉพาะที่ของเครื่องมือ:

    ```cmd
    <custom visual project root>\node_modules\PowerBI-visuals-tools\certs
    ```

หากคุณใช้รูปแบบ PEM ให้บันทึกไฟล์ใบรับรองเป็น *PowerBICustomVisualTest_public.crt* และบันทึก privateKey เป็น *PowerBICustomVisualTest_public.key*

หากคุณใช้รูปแบบ PFX ให้บันทึกไฟล์ใบรับรองเป็น *PowerBICustomVisualTest_public.pfx*

หากไฟล์ใบรับรอง PFX ของคุณต้องการวลีรหัสผ่านให้ทำดังนี้:
1. ในไฟล์กำหนดค่า ให้ระบุว่า:

    ```cmd
    \PowerBI-visuals-tools\config.json
    ```

1. ในส่วน `server` ระบุวลีรหัสผ่านโดยการแทนที่ข้อความตัวอย่าง "*YOUR PASSPHRASE*":

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
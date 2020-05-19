---
title: สร้างใบรับรอง SSL สำหรับวิชวล Power BI
description: เรียนรู้วิธีการสร้างใบรับรอง SSL โดยใช้เครื่องมือวิชวล Power BI ใน Windows, Mac หรือ Linux หรือด้วยตนเอง
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 05/08/2020
ms.openlocfilehash: 37bd8f15dcf17cd0f967e819338a719edf2a3054
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/13/2020
ms.locfileid: "83276386"
---
# <a name="create-an-ssl-certificate"></a>สร้างใบรับรอง SSL

บทความนี้อธิบายวิธีการสร้างและติดตั้งใบรับรอง Secure Sockets Layer (SSL) สำหรับวิชวล Power BI

สำหรับกระบวนการ Windows, macOS X และ Linux คุณต้องมีเครื่องมือวิชวล Power BI **pbiviz** แพคเกจที่ติดตั้ง สำหรับข้อมูลเพิ่มเติมดู [ตั้งค่าสภาพแวดล้อมของนักพัฒนา](https://docs.microsoft.com/power-bi/developer/visuals/custom-visual-develop-tutorial#setting-up-the-developer-environment) 

## <a name="create-a-certificate-on-windows"></a>สร้างใบรับรองบน Windows

หากต้องการสร้างใบรับรองโดยใช้ PowerShell `New-SelfSignedCertificate` cmdlet บน Windows 8 และใหม่กว่า ให้เรียกใช้คำสั่งต่อไปนี้:

```powershell
pbiviz --install-cert
```

สำหรับ Windows 7  `pbiviz` เครื่องมือจำเป็นต้องใช้โปรแกรมอรรถประโยชน์ OpenSSL เพื่อให้มีใช้จากบรรทัดคำสั่ง หากต้องการติดตั้ง OpenSSL ให้ไปที่ [OpenSSL](https://www.openssl.org) หรือ [OpenSSL Binaries](https://wiki.openssl.org/index.php/Binaries)

สำหรับข้อมูลเพิ่มเติมและคำแนะนำสำหรับการติดตั้งใบรับรอง ดู [สร้างและติดตั้งใบรับรองสำหรับ Windows](https://docs.microsoft.com/power-bi/developer/visuals/custom-visual-develop-tutorial#windows)

## <a name="create-a-certificate-on-macos-x"></a>สร้างใบรับรองบน macOS X

โปรแกรมอรรถประโยชน์ OpenSSL มักจะพร้อมใช้งานในระบบปฏิบัติการ macOS X

คุณยังสามารถติดตั้งโปรแกรมอรรถประโยชน์ OpenSSL โดยการเรียกใช้คำสั่งต่อไปนี้:

- จากตัวจัดการแพ็คเกจ *Brew*
  
  ```cmd
  brew install openssl
  brew link openssl --force
  ```

- โดยใช้ *MacPorts*:
  
  ```cmd
  sudo port install openssl
  ```

หลังจากที่คุณติดตั้งโปรแกรมอรรถประโยชน์ OpenSSL ให้เรียกใช้คำสั่งต่อไปนี้เพื่อสร้างใบรับรองใหม่:

```cmd
pbiviz --install-cert
```

สำหรับข้อมูลเพิ่มเติมและคำแนะนำให้ดู [สร้างและติดตั้งใบรับรองสำหรับ OS X](https://docs.microsoft.com/power-bi/developer/visuals/custom-visual-develop-tutorial#osx)

## <a name="create-a-certificate-on-linux"></a>สร้างใบรับรองบน Linux

โปรแกรมอรรถประโยชน์ OpenSSL มักจะพร้อมใช้งานในระบบปฏิบัติการ Linux

ก่อนที่คุณจะเริ่มต้นให้เรียกใช้คำสั่งต่อไปนี้เพื่อตรวจสอบให้แน่ใจว่ามีการติดตั้ง `openssl` และ `certutil`:

```sh
which openssl
which certutil
```

หากไม่ได้ติดตั้ง `openssl` และ `certutil` ให้ติดตั้งโปรแกรมอรรถประโยชน์ `openssl` และ `libnss3`

### <a name="create-the-ssl-configuration-file"></a>สร้างไฟล์การกำหนดค่า SSL

สร้างไฟล์ชื่อ */tmp/openssl.cnf* ที่มีข้อความต่อไปนี้:

```
authorityKeyIdentifier=keyid,issuer
basicConstraints=CA:FALSE
keyUsage = digitalSignature, nonRepudiation, keyEncipherment, dataEncipherment
subjectAltName = @alt_names

[ alt_names ]
DNS.1=localhost
```

### <a name="generate-root-certificate-authority"></a>สร้างผู้ออกใบรับรองหลัก

ในการสร้างผู้ออกใบรับรองหลัก (CA) ในการลงชื่อใบรับรองในเครื่องให้เรียกใช้คำสั่งต่อไปนี้:

```sh
touch $HOME/.rnd
openssl req -x509 -nodes -new -sha256 -days 1024 -newkey rsa:2048 -keyout /tmp/local-root-ca.key -out /tmp/local-root-ca.pem -subj "/C=US/CN=Local Root CA/O=Local Root CA"
openssl x509 -outform pem -in /tmp/local-root-ca.pem -out /tmp/local-root-ca.crt
```

### <a name="generate-a-certificate-for-localhost"></a>สร้างใบรับรองสำหรับ localhost 

หากต้องการสร้างใบรับรองสำหรับ `localhost` โดยใช้ *CA และ* openssl ที่สร้างขึ้นให้เรียกใช้คำสั่งต่อไปนี้:

```sh
PBIVIZ=`which pbiviz`
PBIVIZ=`dirname $PBIVIZ`
PBIVIZ="$PBIVIZ/../lib/node_modules/powerbi-visuals-tools/certs"
# Make sure that $PBIVIZ contains the correct certificate directory path. ls $PBIVIZ should list 'blank' file.
openssl req -new -nodes -newkey rsa:2048 -keyout $PBIVIZ/PowerBIVisualTest_private.key -out $PBIVIZ/PowerBIVisualTest.csr -subj "/C=US/O=PowerBI Visuals/CN=localhost"
openssl x509 -req -sha256 -days 1024 -in $PBIVIZ/PowerBIVisualTest.csr -CA /tmp/local-root-ca.pem -CAkey /tmp/local-root-ca.key -CAcreateserial -extfile /tmp/openssl.cnf -out $PBIVIZ/PowerBIVisualTest_public.crt
```

### <a name="add-root-certificates"></a>เพิ่มใบรับรองหลัก

หากต้องการเพิ่มใบรับรองหลักลงในฐานข้อมูลของเบราว์เซอร์ Chrome ให้เรียกใช้:

```sh
certutil -A -n "Local Root CA" -t "CT,C,C" -i /tmp/local-root-ca.pem -d sql:$HOME/.pki/nssdb
```

หากต้องการเพิ่มใบรับรองหลักลงในฐานข้อมูลของเบราว์เซอร์ Mozilla Firefox ให้เรียกใช้:

```sh
for certDB in $(find $HOME/.mozilla* -name "cert*.db")
do
certDir=$(dirname ${certDB});
certutil -A -n "Local Root CA" -t "CT,C,C" -i /tmp/local-root-ca.pem -d sql:${certDir}
done
```

เมื่อต้องการเพิ่มใบรับรองหลักทั้งระบบ ให้เรียกใช้:

```sh
sudo cp /tmp/local-root-ca.pem /usr/local/share/ca-certificates/
sudo update-ca-certificates
```

### <a name="remove-root-certificates"></a>เอาใบรับรองหลักออก

เมื่อต้องการเอาใบรับรองหลักออก ให้เรียกใช้:

```sh
sudo rm /usr/local/share/ca-certificates/local-root-ca.pem
sudo update-ca-certificates --fresh
```

## <a name="generate-a-certificate-manually"></a>สร้างใบรับรองด้วยตนเอง

คุณยังสามารถสร้างใบรับรอง SSL ด้วยตนเองโดยใช้ OpenSSL คุณสามารถระบุเครื่องมือใดๆ ในการสร้างใบรับรองของคุณ

ถ้ามีการติดตั้งโปรแกรมอรรถประโยชน์ OpenSSL อยู่แล้วให้สร้างใบรับรองใหม่โดยการเรียกใช้:

```cmd
openssl req -x509 -newkey rsa:4096 -keyout PowerBIVisualTest_private.key -out PowerBIVisualTest_public.crt -days 365
```

โดยปกติแล้วคุณสามารถค้นหาใบรับรองเว็บเซิร์ฟเวอร์ `PowerBI-visuals-tools` ได้โดยการเรียกใช้คำสั่งต่อไปนี้:

- สำหรับอินสแตนซ์ส่วนกลางของเครื่องมือ:
  
  ```cmd
  %appdata%\npm\node_modules\PowerBI-visuals-tools\certs
  ```

- สำหรับอินสแตนซ์เฉพาะที่ของเครื่องมือ:
  
  ```cmd
  <Power BI visual project root>\node_modules\PowerBI-visuals-tools\certs
  ```

### <a name="pem-format"></a>รูปแบบ PEM

ถ้าคุณใช้รูปแบบใบรับรอง Privacy Enhanced Mail (PEM) บันทึกไฟล์ใบรับรองเป็น *PowerBIVisualTest_public.crt* และบันทึกคีย์ส่วนตัวเป็น *PowerBIVisualTest_private.key*

### <a name="pfx-format"></a>รูปแบบ PFX

ถ้าคุณใช้รูปแบบใบรับรอง Personal Information Exchange (PFX) บันทึกไฟล์ใบรับรองเป็น *PowerBIVisualTest_public.pfx*

หากไฟล์ใบรับรอง PFX ของคุณต้องการวลีรหัสผ่านให้ทำดังนี้:

1. ในไฟล์กำหนดค่า ให้ระบุว่า:
   
   ```cmd
   \PowerBI-visuals-tools\config.json
   ```
   
1. ในส่วน `server` ระบุวลีรหัสผ่านโดยการแทนที่ข้อความตัวอย่าง \<YOUR PASSPHRASE> placeholder:

    ```cmd
    "server":{
        "root":"webRoot",
        "assetsRoute":"/assets",
        "privateKey":"certs/PowerBIVisualTest_private.key",
        "certificate":"certs/PowerBIVisualTest_public.crt",
        "pfx":"certs/PowerBIVisualTest_public.pfx",
        "port":"8080",
        "passphrase":"<YOUR PASSPHRASE>"
    }
    ```

## <a name="next-steps"></a>ขั้นตอนถัดไป
- [พัฒนาวิชวล Power BI](custom-visual-develop-tutorial.md)
- [ตัวอย่างวิชวล Power BI](samples.md)
- [เผยแพร่วิชวล Power BI ลงใน AppSource](office-store.md)

---
title: การแก้ไขปัญหา เกตเวย์ข้อมูลในองค์กร
description: บทความนี้ให้วิธีการหลาย ๆ วิธี ที่คุณสามารถใช้แก้ไขปัญหาที่พบใน เกตเวย์ข้อมูลในองค์กร และยังให้วิธีแก้ไขปัญหาที่เกิดจากปัญหาที่รู้จักแล้ว รวมถึงเครื่องมือต่าง ๆ ที่มาช่วยคุณแก้ไขปัญหา
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-gateways
ms.topic: conceptual
ms.date: 08/08/2018
LocalizationGroup: Gateways
ms.openlocfilehash: 795f97403ea80caad52e57e54edc3d54a4c5d952
ms.sourcegitcommit: 3b1a1f55465e5dca88783046c6b4c073e4e22e4b
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 11/13/2018
ms.locfileid: "51580551"
---
# <a name="troubleshooting-the-on-premises-data-gateway"></a>การแก้ไขปัญหา เกตเวย์ข้อมูลในองค์กร

บทความนี้อธิบายถึงปัญหาทั่วไปเมื่อใช้**เกตเวย์ข้อมูลภายในองค์กร**

<!-- Shared Community & support links Include -->
[!INCLUDE [gateway-onprem-tshoot-support-links-include](./includes/gateway-onprem-tshoot-support-links-include.md)]

<!-- Shared Troubleshooting Install Include -->
[!INCLUDE [gateway-onprem-tshoot-install-include](./includes/gateway-onprem-tshoot-install-include.md)]

## <a name="configuration"></a>การกำหนดค่า

### <a name="how-to-restart-the-gateway"></a>วิธีการรีสตาร์ทเกตเวย์

เกตเวย์ทำงานเป็นบริการ Windows ดังนั้นคุณสามารถเริ่ม และหยุดได้สองสามวิธี ตัวอย่างเช่น คุณสามารถเปิด พร้อมท์คำสั่งที่มีสิทธิ์ผู้ดูแล บนเครื่องที่เกตเวย์กำลังทำงานอยู่ และจากนั้น เรียกใช้คำสั่งอย่างใดอย่างหนึ่งเหล่านี้:

* เมื่อต้องการหยุดบริการ เรียกใช้คำสั่งนี้:

    '''   net stop PBIEgwService   '''

* เมื่อต้องการเริ่มบริการ เรียกใช้คำสั่งนี้:

    '''   net start PBIEgwService   '''

### <a name="log-file-configuration"></a>การกำหนดค่าไฟล์บันทึก

ไฟล์บันทึกบริการเกตเวย์จะถูกแยกประเภทลงในบักเก็ตสามใบ: ข้อมูล ข้อผิดพลาด และเครือข่าย การจัดประเภทนี้ให้ประสบการณ์ในการแก้ไขปัญหาที่ดีกว่า ซึ่งช่วยให้คุณสามารถโฟกัสบนพื้นที่เฉพาะได้โดยขึ้นอยู่กับข้อผิดพลาดหรือปัญหา คุณสามารถเห็นหมวดหมู่สามประเภทในส่วนย่อยต่อไปนี้จากไฟล์การกำหนดค่าเกตเวย์: `GatewayInfo.log,GatewayErrors.log,GatewayNetwork.log`

```xml
  <system.diagnostics>
    <trace autoflush="true" indentsize="4">
      <listeners>
        <remove name="Default" />
        <add name="ApplicationFileTraceListener"
             type="Microsoft.PowerBI.DataMovement.Pipeline.Common.Diagnostics.RotatableFilesManagerTraceListener, Microsoft.PowerBI.DataMovement.Pipeline.Common"
             initializeData="%LOCALAPPDATA%\Microsoft\On-premises data gateway\,GatewayInfo.log,GatewayErrors.log,GatewayNetwork.log,20,50" />
      </listeners>
    </trace>
  </system.diagnostics>
```

ไฟล์นี้จะตั้งอยู่ในตำแหน่งตามค่าเริ่มต้นที่: *\Program Files\On-premises data gateway\Microsoft.PowerBI.EnterpriseGateway.exe.config* หากต้องการกำหนดค่าจำนวนไฟล์บันทึกเพื่อเก็บรักษาไว้ ให้เปลี่ยนหมายเลขแรก (20 ในตัวอย่างนี้): `GatewayInfo.log,GatewayErrors.log,GatewayNetwork.log,20,50`

### <a name="error-failed-to-create-a-gateway-try-again"></a>ข้อผิดพลาด: การสร้างเกตเวย์ล้มเหลว ลองอีกครั้ง

มีการใส่รายละเอียดทั้งหมดแล้ว แต่การเรียกไปยังบริการ Power BI ส่งข้อผิดพลาดกลับมา ข้อผิดพลาดและ ID กิจกรรมจะแสดงขึ้น อาจเกิดขึ้นจากหลายสาเหตุ คุณสามารถรวบรวมและตรวจสอบ แฟ้มบันทึก ตามที่จะกล่าวถึงด้านล่าง สำหรับรายละเอียดเพิ่มเติม

นี่อาจเกิดจากการกำหนดค่าพร็อกซีก็ได้ ส่วนติดต่อผู้ใช้ในขณะนี้ยังไม่อนุญาตกำหนดค่าพร็อกซี คุณสามารถเรียนรู้เพิ่มเติมเกี่ยวกับ[การแก้ไขการกำหนดค่าพร็อกซี](service-gateway-proxy.md)ได้

### <a name="error-failed-to-update-gateway-details-please-try-again"></a>ข้อผิดพลาด: การอัปเดตรายละเอียดเกตเวย์ล้มเหลว โปรดลองอีกครั้ง

ได้รับข้อมูลจากบริการ Power BI ไปยังเกตเวย์ ข้อมูลที่ถูกส่งผ่านไปบริการภายใน Windows แต่ไม่ตอบกลับมา อีกวิธีหนึ่งคือ การสร้างคีย์สมมาตรล้มเหลว ข้อยกเว้นภายในจะแสดงภายใต้**แสดงรายละเอียด** เพื่อรับรายละเอียดเพิ่มเติม คุณสามารถรวบรวม และตรวจทานบันทึกที่จะกล่าวถึงด้านล่าง

### <a name="error-power-bi-service-reported-local-gateway-as-unreachable-restart-the-gateway-and-try-again"></a>ข้อผิดพลาด: บริการ Power BI รายงานว่าไม่สามารถเข้าถึงเกตเวย์ภายในเครื่องได้ รีสตาร์ทเกตเวย์ และลองอีกครั้ง

ตอนท้ายของการกำหนดค่า บริการ Power BI จะถูกเรียกอีกครั้งเพื่อตรวจสอบเกตเวย์ บริการของ Power BI ไม่ได้รายงานสถานะเกตเวย์ว่า *live* รีสตาร์ทบริการ windows อาจช่วยให้สื่อสารสำเร็จ คุณสามารถรวบรวมและตรวจสอบ แฟ้มบันทึก ตามที่จะกล่าวถึงด้านล่าง สำหรับรายละเอียดเพิ่มเติม

### <a name="script-error-during-sign-into-power-bi"></a>ข้อผิดพลาดของสคริปต์ระหว่างการลงชื่อเข้าใช้ใน Power BI

คุณอาจได้รับข้อผิดพลาดสคริปต์เมื่อลงชื่อเข้าใช้ Power BI ระหว่างการกำหนดค่าเกตเวย์ข้อมูลในองค์กร การติดตั้งการปรับปรุงความปลอดภัยต่อไปนี้จะช่วยแก้ปัญหา สามารถติดตั้งผ่านทาง Windows Update

[MS16-051: ปรับปรุงความปลอดภัยสำหรับ Internet Explorer: 10 พฤษภาคม 2016 (KB 3154070)](https://support.microsoft.com/kb/3154070)

### <a name="gateway-configuration-failed-with-a-null-reference-exception"></a>กำหนดค่าเกตเวย์ล้มเหลว โดยมีข้อยกเว้นการอ้างอิง null

คุณอาจพบข้อผิดพลาดที่คล้ายกับต่อไปนี้

        Failed to update gateway details.  Please try again.
        Error updating gateway configuration.

ซึ่งประกอบด้วยการติดตามสแตก และการติดตามสแตกนั้นอาจมีข้อความต่อไปนี้

        Microsoft.PowerBI.DataMovement.Pipeline.Diagnostics.CouldNotUpdateGatewayConfigurationException: Error updating gateway configuration. ----> System.ArgumentNullException: Value cannot be null.
        Parameter name: serviceSection

ถ้าคุณกำลังอัปเกรดจากเกตเวย์เวอร์ชันที่เก่ากว่า เราเก็บรักษา แฟ้มกำหนดค่า ของเดิม อาจมีบางส่วนในแฟ้มขาดหายไป เมื่อเกตเวย์พยายามอ่าน เราสามารถได้รับข้อยกเว้นการอ้างอิง null ได้

เมื่อต้องแก้ไข ทำขั้นตอนต่อไปนี้

1. ถอนการติดตั้งเกตเวย์
2. ลบโฟลเดอร์ต่อไปนี้

        c:\Program Files\On-premises data gateway
3. ติดตั้งเกตเวย์ใหม่
4. ขั้นตอนนี้ไม่บังคับ คุณอาจใช้คีย์การกู้คืนเมื่อเพื่อคืนค่าเกตเวย์ที่มีอยู่

## <a name="support-for-tls-12"></a>สนับสนุน TLS 1.1/1.2

เกตเวย์ข้อมูลแบบติดตั้งภายในองค์กร จะใช้ Transport Layer Security (TLS) 1.2 หรือ 1.2 ในการสื่อสารกับ Power BI service เป็นค่าเริ่มต้น เพื่อให้แน่ใจว่าการรับส่งข้อมูลทั้งหมดของเกตเวย์ใช้ TLS 1.2 คุณต้องเพิ่มหรือแก้ไขรีจิสทรีคีย์ต่อไปนี้บนเครื่องที่ใช้งาน service ของเกตเวย์:

```
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001
[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]"SchUseStrongCrypto"=dword:00000001
```

> [!NOTE]
> การเพิ่มหรือแก้ไขรีจิสทรีคีย์เหล่านี้จะนำการเปลี่ยนแปลงไปใช้กับแอปพลิเคชัน .NET ทั้งหมด สำหรับข้อมูลเกี่ยวกับการเปลี่ยนแปลงรีจิสทรีที่มีผลต่อ TLS สำหรับแอปพลิเคชันอื่น ๆ ดู[การตั้งค่ารีจิสทรี Transport Layer Security (TLS)](https://docs.microsoft.com/windows-server/security/tls/tls-registry-settings)

## <a name="data-sources"></a>แหล่งข้อมูล

### <a name="error-unable-to-connect-details-invalid-connection-credentials"></a>ข้อผิดพลาด: ไม่สามารถเชื่อมต่อได้ รายละเอียด: “ข้อมูลประจำตัวของการเชื่อมต่อไม่ถูกต้อง”

ภายใน**แสดงรายละเอียด**จะแสดงข้อความแสดงข้อผิดพลาดที่ได้รับจากแหล่งข้อมูล สำหรับ SQL Server คุณจะเห็นสิ่งต่อไปนี้

    Login failed for user 'username'.

ตรวจสอบว่า คุณมีชื่อผู้ใช้และรหัสผ่านที่ถูกต้อง อีกทั้ง ตรวจสอบว่า ข้อมูลประจำตัวเหล่านั้นสามารถเชื่อมต่อกับแหล่งข้อมูลเรียบร้อยแล้ว ตรวจสอบให้แน่ใจว่า บัญชีที่ใช้ตรงกับ **วิธีการรับรองความถูกต้อง**

### <a name="error-unable-to-connect-details-cannot-connect-to-the-database"></a>ข้อผิดพลาด: ไม่สามารถเชื่อมต่อได้ รายละเอียด: “ไม่สามารถเชื่อมต่อกับแหล่งข้อมูลได้”

เราสามารถเชื่อมต่อไปยังเซิร์ฟเวอร์ แต่ไม่สามารถเชื่อมต่อไปยังฐานข้อมูลที่ให้มา ตรวจสอบชื่อของฐานข้อมูล และตรวจสอบว่าข้อมูลประจำตัวของผู้ใช้มีสิทธิ์เข้าถึงฐานข้อมูลนั้น

ภายใน**แสดงรายละเอียด**จะแสดงข้อความแสดงข้อผิดพลาดที่ได้รับจากแหล่งข้อมูล สำหรับ SQL Server คุณจะเห็นสิ่งต่อไปนี้

    Cannot open database "AdventureWorks" requested by the login. The login failed. Login failed for user 'username'.

### <a name="error-unable-to-connect-details-unknown-error-in-data-gateway"></a>ข้อผิดพลาด: ไม่สามารถเชื่อมต่อได้ รายละเอียด: "เกิดข้อผิดพลาดที่ไม่รู้จักในเกตเวย์ข้อมูล"

ข้อผิดพลาดนี้อาจเกิดขึ้นจากหลายสาเหตุ ตรวจสอบให้แน่ใจว่าการตรวจสอบว่า คุณสามารถเชื่อมต่อกับแหล่งข้อมูลจากเครื่องที่เกตเวย์ทำงาน นี่อาจเป็นผลของการที่เชื่อมต่อกับเซิร์ฟเวอร์ไม่ได้

ภายใน**แสดงรายละเอียด**คุณสามารถเห็นรหัสข้อผิดพลาดของ**DM_GWPipeline_UnknownError**ได้

คุณยังสามารถค้นหารายละเอียดเพิ่มเติมได้จาก บันทึกเหตุการณ์ > **บันทึกแอปพลิเคชันและบริการ** > **บริการเกตเวย์ข้อมูลในองค์กร**

### <a name="error-we-encountered-an-error-while-trying-to-connect-to-server-details-we-reached-the-data-gateway-but-the-gateway-cant-access-the-on-premises-data-source"></a>ข้อผิดพลาด: เราพบข้อผิดพลาดขณะพยายามเชื่อมต่อกับ<server> รายละเอียด: "เราเข้าถึงเกตเวย์ข้อมูลได้ แต่เกตเวย์ไม่สามารถเข้าถึงแหล่งข้อมูลในองค์กร"

เราไม่สามารถเชื่อมต่อไปยังแหล่งข้อมูลที่ระบุไว้ ตรวจสอบให้แน่ใจว่าข้อมูลที่ให้ไว้สำหรับแหล่งข้อมูลนั้นถูกต้อง

ภายใน**แสดงรายละเอียด**คุณสามารถเห็นรหัสข้อผิดพลาดของ**DM_GWPipeline_Gateway_DataSourceAccessError**ได้

ถ้าข้อผิดพลาดภายในคล้ายกับข้อความต่อไปนี้ แสดงว่า บัญชีผู้ใช้ที่คุณกำลังใช้สำหรับแหล่งข้อมูล ไม่ใช่ผู้ดูแลเซิร์ฟเวอร์สำหรับ Analysis Services อินสแตนซ์นั้น [เรียนรู้เพิ่มเติม](https://docs.microsoft.com/sql/analysis-services/instances/grant-server-admin-rights-to-an-analysis-services-instance)

    The 'CONTOSO\account' value of the 'EffectiveUserName' XML for Analysis property is not valid.

ถ้าข้อผิดพลาดภายในคล้ายกับข้อความต่อไปนี้ แสดงว่า บัญชีบริการสำหรับ Analysis Services อาจจะขาดแอตทริบิวต์ [token-groups-global-and-universal](https://msdn.microsoft.com/library/windows/desktop/ms680300.aspx) (TGGAU) ในไดเรกทอรี

    The username or password is incorrect.

โดเมนที่มีการเข้าถึงความเข้ากันได้ของ windows รุ่นก่อน 2000 มีแอตทริบิวต์ TGGAU ที่เปิดใช้งาน อย่างไรก็ตาม โดเมนที่สร้างขึ้นใหม่ส่วนใหญ่ไม่เปิดใช้งานแอตทริบิวต์นี้ตามค่าเริ่มต้น คุณสามารถอ่านเพิ่มเติมเกี่ยวกับหัวข้อนี้ได้[ที่นี่](https://support.microsoft.com/kb/331951)

คุณสามารถยืนยัน โดยทำดังต่อไปนี้

1. เชื่อมต่อไปยังเครื่อง Analysis Services ภายใน SQL Server Management Studio ภายใน คุณสมบัติการเชื่อมต่อขั้นสูง ใส่ EffectiveUserName สำหรับผู้ใช้ที่มีปัญหา และดูว่าเกิดข้อผิดพลาดแบบเดียวกันหรือไม่
2. คุณสามารถใช้เครื่องมือ dsacls ของ Active Directory เพื่อตรวจสอบว่ามีแอตทริบิวต์ในรายการหรือไม่ นี่คือเครื่องมือที่พบบนตัวควบคุมโดเมน คุณจำเป็นต้องทราบชื่อโดเมนเฉพาะสำหรับบัญชีผู้ใช้ และส่งค่านั้นไปยังเครื่องมือ

        dsacls "CN=John Doe,CN=UserAccounts,DC=contoso,DC=com"

    คุณต้องการผลลัพธ์ที่คล้ายกับข้อความต่อไปนี้

            Allow BUILTIN\Windows Authorization Access Group
                                          SPECIAL ACCESS for tokenGroupsGlobalAndUniversal
                                          READ PROPERTY

เมื่อต้องการแก้ไขปัญหานี้ คุณจำเป็นต้องเปิดใช้งาน TGGAU บนบัญชีที่ใช้สำหรับบริการ Analysis Services ของ Windows

#### <a name="another-possibility-for-username-or-password-incorrect"></a>อีกสาเหตุหนึ่งที่เป็นไปได้คือ ชื่อผู้ใช้หรือรหัสผ่านไม่ถูกต้อง

ข้อผิดพลาดนี้ก็ยังเกิดขึ้นได้ถ้าเซิร์ฟเวอร์ Analysis Services อยู่ในคนละโดเมนกับผู้ใช้ และไม่มีการกำหนด ความน่าเชื่อถือแบบสองทิศทาง เอาไว้ก่อน

คุณจำเป็นต้องทำงานกับผู้ดูแลโดเมนของคุณเพื่อตรวจสอบความน่าเชื่อถือระหว่างโดเมน

#### <a name="unable-to-see-the-data-gateway-data-sources-in-the-get-data-experience-for-analysis-services-from-the-power-bi-service"></a>ไม่สามารถมองเห็นแหล่งข้อมูลของเกตเวย์ข้อมูลในประสบการณ์ใช้งาน 'รับข้อมูล' สำหรับ Analysis Services จากบริการ Power BI

ตรวจสอบให้แน่ใจว่า บัญชีของคุณอยู่ในรายการในแท็บ**ผู้ใช้** ของแหล่งข้อมูล ในการกำหนดค่าของเกตเวย์ ถ้าคุณไม่มีสิทธิ์การเข้าถึงไปยังเกตเวย์ ให้ตรวจสอบกับผู้ดูแลระบบของเกตเวย์และขอให้ตรวจสอบ เฉพาะบัญชีผู้ใช้ในรายการ**ผู้ใช้**เท่านั้นที่สามารถดูแหล่งข้อมูลที่แสดงอยู่ในรายการของ Analysis Services ได้

### <a name="error-you-dont-have-any-gateway-installed-or-configured-for-the-data-sources-in-this-dataset"></a>ข้อผิดพลาด: คุณไม่ได้ติดตั้งหรือการกำหนดค่าเกตเวย์ สำหรับแหล่งข้อมูลในชุดข้อมูลนี้

ตรวจสอบให้แน่ใจว่า คุณได้เพิ่มหนึ่งหรือหลายแหล่งข้อมูลอย่าง ตามที่อธิบายไว้ใน[เพิ่มแหล่งข้อมูล](service-gateway-manage.md#add-a-data-source) ถ้าเกตเวย์ไม่ปรากฏในพอร์ทัลผู้ดูแลภายใต้**จัดการเกตเวย์** ลองล้างแคชของเบราว์เซอร์คุณ หรือลงชื่อออกจากบริการแล้วลงชื่อเข้าใช้อีกครั้ง

## <a name="datasets"></a>ชุดข้อมูล

### <a name="error-there-is-not-enough-space-for-this-row"></a>ข้อผิดพลาด: มีเนื้อที่ไม่เพียงพอสำหรับแถวนี้

ซึ่งเกิดขึ้นถ้าคุณมีแถวเดียวที่มีขนาดมากกว่า 4 เมกะไบต์ คุณจำเป็นต้องกำหนดว่าแถวไหนมาจากแหล่งข้อมูลของคุณ และพยายามทำการกรองออกหรือลดขนาดสำหรับแถวนั้น

### <a name="error-the-server-name-provided-doesnt-match-the-server-name-on-the-sql-server-ssl-certificate"></a>ข้อผิดพลาด: ชื่อเซิร์ฟเวอร์ที่ระบุไม่ตรงกับชื่อเซิร์ฟเวอร์บนใบรับรอง SSL ของ SQL Server

ซึ่งสามารถเกิดขึ้นเมื่อใบรับรอง CN มีไว้สำหรับเซิร์ฟเวอร์ที่มีชื่อโดเมนที่มีคุณสมบัติครบถ้วน (FQDN) แต่คุณใส่เพียงชื่อ NetBIOS สำหรับเซิร์ฟเวอร์ ซึ่งทำให้ไม่ตรงกันสำหรับใบรับรอง เมื่อต้องแก้ไขปัญหานี้ คุณจำเป็นต้องทำชื่อเซิร์ฟเวอร์ภายในแหล่งข้อมูลเกตเวย์ และไฟล์ PBIX เพื่อใช้ FQDN ของเซิร์ฟเวอร์

### <a name="i-dont-see-the-on-premises-data-gateway-present-when-configuring-scheduled-refresh"></a>ฉันไม่เห็นเกตเวย์ข้อมูลภายในองค์กรอยู่เมื่อกำหนดค่าการรีเฟรชตามกำหนดการ

สิ่งนี้เกิดขึ้นจากสองสามสาเหตุ

1. ชื่อเซิร์ฟเวอร์และชื่อฐานข้อมูล ที่ป้อนลงใน Power BI Desktop และที่กำหนดในแหล่งข้อมูลในเกตเวย์ ไม่ตรงกัน ข้อมูลทั้งสองที่ต้องเป็นค่าเดียวกัน ข้อมูลไม่ตรงตามตัวพิมพ์ใหญ่-เล็ก
2. บัญชีของคุณไม่ได้แสดงอยู่ในรายการในแท็บ**ผู้ใช้** ของแหล่งข้อมูลในการกำหนดค่าในเกตเวย์ คุณต้องรับกับผู้ดูแลระบบของเกตเวย์ให้ถูกเพิ่มในรายการนั้น
3. ไฟล์ Power BI Desktop ของคุณมีแหล่งข้อมูลหลายแหล่ง แต่บางแหล่งข้อมูลไม่ได้กำหนดค่าไว้ในเกตเวย์ คุณจำเป็นต้องมีแหล่งข้อมูลแต่ละแหล่งที่กำหนดด้วยเกตเวย์สำหรับเกตเวย์เพื่อแสดงขึ้นภายในการรีเฟรชตามกำหนดการ

### <a name="error-the-received-uncompressed-data-on-the-gateway-client-has-exceeded-the-limit"></a>ข้อผิดพลาด: ข้อมูลที่ไม่มีการบีบอัดที่ได้รับบนไคลเอ็นต์ของเกตเวย์ได้เกินขีดจำกัด

มีการจำกัดขนาดของข้อมูลไม่บีบอัดที่ 10 GB ต่อ ตาราง ถ้าคุณกำลังมีปัญหานี้ มีหลายทางเลือกที่จะอ็อพติไมซ์ และหลีกเลี่ยงปัญหาดังกล่าว โดยเฉพาะการลดการใช้ค่าสตริงที่ยาว คงที่สูง และแทนโดยใช้คีย์มาตรฐาน หรือเอาคอลัมน์ออก (ถ้าไม่ใช้งาน) จะช่วยได้

## <a name="reports"></a>รายงาน

### <a name="report-could-not-access-the-data-source-because-you-do-not-have-access-to-our-data-source-via-an-on-premises-data-gateway"></a>รายงานไม่สามารถเข้าถึงแหล่งข้อมูลได้ เนื่องจากคุณไม่มีสิทธิ์การเข้าถึงแหล่งข้อมูลของเราผ่านเกตเวย์ข้อมูลภายในองค์กร

มักมีสาเหตุจากหนึ่งในนี้

1. แหล่งข้อมูลไม่ตรงกับสิ่งที่อยู่ในชุดข้อมูลพื้นฐาน ชื่อเซิร์ฟเวอร์และฐานข้อมูล ที่กำหนดในแหล่งข้อมูลของเกตเวย์ข้อมูลในองค์กร และที่คุณใส่ใน Power BI Desktop ไม่ตรงกัน ถ้าคุณใช้อยู่ที่อยู่ IP ใน Power BI Desktop แล้ว แหล่งข้อมูลในเกตเวย์ข้อมูลในองค์กร ก็ต้องใช้ที่อยู่ IP เช่นกัน
2. ไม่แหล่งข้อมูลใด ในเกตเวย์ใด ๆ ภายในองค์กรของคุณพร้อมใช้งาน คุณสามารถกำหนดค่าแหล่งข้อมูลบนเกตเวย์ข้อมูลภายในองค์กรที่มีอยู่หรืออันใหม่

### <a name="error-data-source-access-error-please-contact-the-gateway-administrator"></a>ข้อผิดพลาด: ข้อผิดพลาดในการเข้าถึงแหล่งข้อมูล โปรดติดต่อผู้ดูแลระบบเกตเวย์

ถ้ารายงานนี้ใช้การเชื่อมต่อสดของ Analysis Services คุณอาจเจอปัญหากับค่าถูกส่งผ่านไปยัง EffectiveUserName ที่ไม่ถูกต้อง หรือไม่มีสิทธิ์บนเครื่องของ Analysis Services โดยทั่วไปแล้ว ปัญหาในการรับรองความถูกต้องเกิดจากค่า EffectiveUserName ไม่ตรงกับภายในชื่อผู้ใช้หลัก (UPN) ในเครื่อง

เพื่อการยืนยัน คุณสามารถทำสิ่งต่อไปนี้

1. ค้นหาชื่อผู้ใช้ที่มีผลบังคับใช้จากใน[รายการบันทึกของเกตเวย์](#logs)
2. เมื่อคุณมีค่าที่ใช้ส่งผ่าน ตรวจสอบว่าข้อมูลนั้นถูกต้อง ถ้าเป็นผู้ใช้ของคุณ คุณสามารถใช้คำสั่งต่อไปนี้จากพร้อมท์คำสั่งเพื่อดู UPN UPN มีลักษณะเหมือนกับที่อยู่อีเมล

        whoami /upn

อีกทางเลือกหนึ่ง คุณดูว่า Power BI ได้รับอะไรจาก Azure Active Directory

1. เรียกดู[ https://developer.microsoft.com/graph/graph-explorer ](https://developer.microsoft.com/graph/graph-explorer)
2. เลือก**ลงชื่อเข้าใช้**มุมบนขวา
3. เรียกใช้คิวรีต่อไปนี้ คุณเห็นการตอบสนอง JSON ขนาดใหญ่แทน

        https://graph.windows.net/me?api-version=1.5
4. ค้นหา**userPrincipalName**

ถ้า Azure Active Directory UPN ของคุณไม่ตรงกับ Azure Active Directory UPN ภายในเครื่องของคุณ คุณสามารถใช้คุณลักษณะ[แมปชื่อผู้ใช้](service-gateway-enterprise-manage-ssas.md#map-user-names)เพื่อแทนที่ด้วยค่าที่ถูกต้อง หรือคุณสามารถทำงานกับผู้ดูแลระบบผู้เช่าหรือผู้ดูแลระบบ Active Directory ภายในเครื่องของคุณ เพื่อเปลี่ยน UPN ของคุณ

<!-- Shared Troubleshooting Firewall/Proxy Include -->
[!INCLUDE [gateway-onprem-tshoot-firewall-include](./includes/gateway-onprem-tshoot-firewall-include.md)]

คุณสามารถค้นหาภูมิภาคของศูนย์ข้อมูลที่คุณอยู่ โดยทำดังต่อไปนี้:

1. เลือก **?** มุมบนขวาของบริการ Power BI
2. เลือก **เกี่ยวกับ Power BI**
3. ขอบเขตข้อมูลของคุณจะแสดงอยู่ใน**ข้อมูลของคุณถูกเก็บไว้ใน**

    ![ขอบเขตข้อมูล](media/service-gateway-onprem-tshoot/power-bi-data-region.png)

ถ้าคุณจะยังแก้ปัญหาไม่ได้ คุณลอง ติดตามเครือข่าย โดยใช้เครื่องมือเช่น [fiddler](#fiddler) หรือ netsh แม้ว่าวิธีรวบรวมข้อมูลเหล่านี้เป็นวิธีการขั้นสูง และอาจต้องขอความช่วยเหลือในการวิเคราะห์ข้อมูลที่รวบรวมได้ คุณสามารถติดต่อ[ฝ่ายสนับสนุน](https://support.microsoft.com)สำหรับความช่วยเหลือได้

## <a name="performance"></a>ประสิทธิภาพการทำงาน

<iframe width="560" height="315" src="https://www.youtube.com/embed/IJ_DJ30VNk4?showinfo=0" frameborder="0" allowfullscreen></iframe>

### <a name="performance-counters"></a>ตัวนับประสิทธิภาพ

มีตัวนับประสิทธิภาพหลายตัวที่ช่วยตรวจวัดกิจกรรมต่าง ๆ ในเกตเวย์ ซึ่งจะเป็นประโยชน์ในการทำความเข้าใจว่าถ้าเรามีปริมาณกิจกรรมที่มีขนาดใหญ่ และอาจจำเป็นต้องทำเกตเวย์ใหม่ ตัวนับเหล่านี้ไม่ได้แสดงว่าจะใช้เวลานานเท่าใด

สามารถเข้าถึงตัวนับเหล่านี้ผ่านเครื่องมือ Windows Performance Monitor

![](media/service-gateway-onprem-tshoot/gateway-perfmon.png)

ตัวนับจะจัดกลุ่มได้ดังนี้

| ชนิดตัวนับ | คำอธิบาย |
| --- | --- |
| ADO.NET |ใช้สำหรับการเชื่อมต่อ DirectQuery ใด ๆ |
| ADOMD |ใช้สำหรับ Analysis Services 2014 และเวอร์ชันก่อนหน้า |
| OLEDB |แหล่งข้อมูลบางชนิดใช้ตัวนี้ รวมไปถึง SAP HANA และ Analysis Service 2016 หรือใหม่กว่า |
| Mashup |การนำเข้าข้อมูลจากแหล่งข้อมูลใด ๆ ถ้าคุณกำลังจัดกำหนดการรีเฟรช หรือทำการรีเฟรชตามความต้องการ จะผ่านกลไกจัดการ Mashup |

นี่คือรายการของตัวนับประสิทธที่มี

| ตัวนับ | คำอธิบาย |
| --- | --- |
| จำนวนการเปิดการเชื่อมต่อ ADO.NET ที่ดำเนินการ / วินาที |จำนวนของการดำเนินการ การเปิดการเชื่อมต่อ ADO.NET ต่อวินาที (สำเร็จ หรือล้มเหลว) |
| จำนวนการเปิดการเชื่อมต่อ ADO.NET ที่ล้มเหลว / วินาที |จำนวนของการดำเนินการ การเปิดการเชื่อมต่อ ADO.NET ที่ล้มเหลวต่อวินาที |
| จำนวนการคิวรี ADO.NET ที่ดำเนินการ / วินาที |จำนวนคิวรี ADO.NET ที่ดำเนินการต่อวินาที (สำเร็จ หรือล้มเหลว) |
| จำนวนการคิวรี ADO.NET ที่ล้มเหลว / วินาที |จำนวนคิวรี ADO.NET ที่ดำเนินการแล้วล้มเหลวต่อวินาที |
| จำนวนการเปิดการเชื่อมต่อ ADOMD ที่ดำเนินการ / วินาที |จำนวนของการดำเนินการ การเปิดการเชื่อมต่อ ADOMD ต่อวินาที (สำเร็จ หรือล้มเหลว) |
| จำนวนการเปิดการเชื่อมต่อ ADOMD ที่ล้มเหลว / วินาที |จำนวนของการดำเนินการ การเปิดการเชื่อมต่อ ADOMD ที่ล้มเหลวต่อวินาที |
| จำนวนการคิวรี ADOMD ที่ดำเนินการ / วินาที |จำนวนคิวรี ADOMD ที่ดำเนินการต่อวินาที (สำเร็จ หรือล้มเหลว) |
| จำนวนการคิวรี ADOMD ที่ล้มเหลว / วินาที |จำนวนคิวรี ADOMD ที่ดำเนินการแล้วล้มเหลวต่อวินาที |
| จำนวนการเปิดการเชื่อมต่อทั้งหมดที่ดำเนินการ / วินาที |จำนวนของการดำเนินการ การเปิดการเชื่อมต่อทั้งหมด ต่อวินาที (สำเร็จ หรือล้มเหลว) |
| จำนวนการเปิดการเชื่อมต่อทั้งหมดที่ล้มเหลว / วินาที |จำนวนของการดำเนินการ การเปิดการเชื่อมต่อทั้งหมดที่ล้มเหลว ต่อวินาที |
| จำนวนการคิวรีทั้งหมดที่ดำเนินการ / วินาที |จำนวนคิวรีทั้งหมดที่ดำเนินการต่อวินาที (สำเร็จ หรือล้มเหลว) |
| จำนวนรายการในพูลการเชื่อมต่อของ ADO.NET |จำนวนรายการในพูลการเชื่อมต่อของ ADO.NET |
| จำนวนรายการในพูลการเชื่อมต่อของ OLEDB |จำนวนรายการในพูลการเชื่อมต่อของ OLEDB |
| จำนวนรายการในพูลของ Service Bus |จำนวนของรายการในพูลของ Service Bus |
| จำนวนการเปิดการเชื่อมต่อ Mashup ที่ดำเนินการ / วินาที |จำนวนของการดำเนินการ การเปิดการเชื่อมต่อ Mashup ต่อวินาที (สำเร็จ หรือล้มเหลว) |
| จำนวนการเปิดการเชื่อมต่อ Mashup ที่ล้มเหลว / วินาที |จำนวนของการดำเนินการ การเปิดการเชื่อมต่อ Mashup ที่ล้มเหลวต่อวินาที |
| จำนวนการคิวรี Mashup ที่ดำเนินการ / วินาที |จำนวนคิวรี Mashup ที่ดำเนินการต่อวินาที (สำเร็จ หรือล้มเหลว) |
| จำนวนการคิวรี Mashup ที่ล้มเหลว / วินาที |จำนวนคิวรี Mashup ที่ดำเนินการแล้วล้มเหลวต่อวินาที |
| จำนวนการคิวรีชุดผลลัพธ์หลายชุดของ OLEDB ที่ล้มเหลว / วินาที |จำนวนชุดผลลัพธ์หลายชุดของ OLEDB คิวรีที่ล้มเหลวที่ดำเนินการต่อวินาที |
| จำนวนชุดผลลัพธ์หลายชุด OLEDB ของคิวรีที่ดำเนินการ / วินาที |จำนวนชุดผลลัพธ์หลายชุด OLEDB ของคิวรีที่ดำเนินการต่อวินาที (สำเร็จหรือล้มเหลว) |
| จำนวนการเปิดการเชื่อมต่อ OLEDB ที่ดำเนินการ / วินาที |จำนวนของการดำเนินการ การเปิดการเชื่อมต่อ OLEDB ต่อวินาที (สำเร็จ หรือล้มเหลว) |
| จำนวนการเปิดการเชื่อมต่อ OLEDB ที่ล้มเหลว / วินาที |จำนวนของการดำเนินการ การเปิดการเชื่อมต่อ OLEDB ที่ดำเนินการแล้วล้มเหลวต่อวินาที |
| จำนวนการคิวรี OLEDB ที่ดำเนินการ / วินาที |จำนวนชุดผลลัพธ์หลายชุด OLEDB ของคิวรีที่ดำเนินการต่อวินาที (สำเร็จหรือล้มเหลว) |
| จำนวนการคิวรี OLEDB ที่ล้มเหลว / วินาที |จำนวนชุดผลลัพธ์หลายชุด OLEDB ของคิวรีที่ล้มเหลวที่ดำเนินการต่อวินาที |
| จำนวนคิวรีชุดผลลัพธ์ชุดเดียว OLEDB ที่ดำเนินการ / วินาที |จำนวนคิวรีชุดผลลัพธ์ชุดเดียว OLEDB ที่ดำเนินการต่อวินาที (สำเร็จหรือล้มเหลว) |
| จำนวนการคิวรี ที่ล้มเหลว / วินาที |จำนวนคิวรี ที่ดำเนินการแล้วล้มเหลวต่อวินาที |
| จำนวนการคิวรี OLEDB ชุดผลลัพธ์ชุดเดียว ที่ล้มเหลว / วินาที |จำนวนคิวรีที่ล้มเหลว OLEDB ชุดผลลัพธ์ชุดเดียวที่ดำเนินการต่อวินาที |

## <a name="reviewing-slow-performing-queries"></a>การตรวจทานคิวรีที่ดำเนินการได้ช้า

คุณอาจพบว่าการตอบสนองของเกตเวย์ช้า ซึ่งอาจมาจาก คิวรี DirectQuery หรือการรีเฟรชชุดข้อมูลที่คุณนำเข้า คุณสามารถเปิดใช้การบันทึกเพิ่มเติมเพื่อส่งออกคิวรีและกำหนดเวลา เพื่อช่วยให้เข้าใจสาเหตุการทำงานช้า เมื่อคุณค้นพบคิวรีที่ใช้เวลานาน คุณอาจต้องทำการแก้ไขแหล่งข้อมูลของคุณเพิ่มเติมเพื่อปรับประสิทธิภาพของคิวรี ตัวอย่างเช่น การปรับปรุงดัชนีสำหรับคิวรี SQL Server

คุณจำเป็นต้องปรับเปลี่ยนแฟ้มการกำหนดค่าสองแฟ้มเพื่อกำหนดระยะเวลาของคิวรี

### <a name="microsoftpowerbidatamovementpipelinegatewaycoredllconfig"></a>Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config

ภายในไฟล์ *Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* เปลี่ยนค่าของ `EmitQueryTraces` จาก `False` ไปเป็น `True` ไฟล์นีิจะอยู่ที่ *C:\Program Files\On-premises data gateway* ตามค่าเริ่มต้น เปิดใช้งาน`EmitQueryTraces`เริ่มบันทึกคิวรีที่ถูกส่งจากเกตเวย์ไปยังแหล่งข้อมูล

> [!IMPORTANT]
> การเปิดใช้งาน EmitQueryTraces ทำให้แฟ้มบันทึกมีขนาดใหญ่ขึ้นได้มาก ทั้งนี้ขึ้นอยู่กับปริมาณการงานใช้เกตเวย์ เมื่อคุณเสร็จสิ้นการตรวจทานรายการบันทึก คุณต้องตั้งค่า EmitQueryTraces กลับเป็น False ไม่แนะนำให้คุณเปิดใช้งานการตั้งค่านี้เป็นเวลานาน

```
<setting name="EmitQueryTraces" serializeAs="String">
    <value>True</value>
</setting>
```

**ตัวอย่างคิวรี**

```
DM.EnterpriseGateway Information: 0 : 2016-09-15T16:09:27.2664967Z DM.EnterpriseGateway    4af2c279-1f91-4c33-ae5e-b3c863946c41    d1c77e9e-3858-4b21-3e62-1b6eaf28b176    MGEQ    c32f15e3-699c-4360-9e61-2cc03e8c8f4c    FF59BC20 [DM.GatewayCore] Executing query (timeout=224) "<pi>
SELECT
TOP (1000001) [t0].[ProductCategoryName],[t0].[FiscalYear],SUM([t0].[Amount])
 AS [a0]
FROM
(
(select [$Table].[ProductCategoryName] as [ProductCategoryName],
    [$Table].[ProductSubcategory] as [ProductSubcategory],
    [$Table].[Product] as [Product],
    [$Table].[CustomerKey] as [CustomerKey],
    [$Table].[Region] as [Region],
    [$Table].[Age] as [Age],
    [$Table].[IncomeGroup] as [IncomeGroup],
    [$Table].[CalendarYear] as [CalendarYear],
    [$Table].[FiscalYear] as [FiscalYear],
    [$Table].[Month] as [Month],
    [$Table].[OrderNumber] as [OrderNumber],
    [$Table].[LineNumber] as [LineNumber],
    [$Table].[Quantity] as [Quantity],
    [$Table].[Amount] as [Amount]
from [dbo].[V_CustomerOrders] as [$Table])
)
 AS [t0]
GROUP BY [t0].[ProductCategoryName],[t0].[FiscalYear] </pi>"
```

### <a name="microsoftpowerbidatamovementpipelinediagnosticsdllconfig"></a>Microsoft.PowerBI.DataMovement.Pipeline.Diagnostics.dll.config

ภายในไฟล์ *Microsoft.PowerBI.DataMovement.Pipeline.Diagnostics.dll.config* เปลี่ยนค่า `TracingVerbosity` จาก `4` ไปเป็น `5` ไฟล์นีิจะอยู่ที่ *C:\Program Files\On-premises data gateway* ตามค่าเริ่มต้น การเปลี่ยนการตั้งค่านี้จะเริ่มบันทึกรายการอย่างละเอียดไปยังรายการบันทึกเกตเวย์ ซึ่งรวมถึงรายการที่แสดงระยะเวลาที่ใช้ คุณยังสามารถเปิดใช้รายการอย่างละเอียด โดยการเปิดใช้งานปุ่ม "การบันทึกเพิ่มเติม" ในแอปพลิเคชันเกตเวย์ภายในองค์กร

   ![การบันทึกเพิ่มเติม](media/service-gateway-onprem-tshoot/additional-logging.png)

> [!IMPORTANT]
> การเปิดใช้งาน TracingVerbosity ไปเป็น `5` ทำให้แฟ้มบันทึกมีขนาดใหญ่ขึ้นได้มาก ทั้งนี้ขึ้นอยู่กับปริมาณการงานใช้เกตเวย์ เมื่อคุณเสร็จสิ้นการตรวจทานรายการบันทึก คุณจำเป็นต้องตั้งค่า TraceVerbosity เป็น`4` ไม่แนะนำให้คุณเปิดใช้งานการตั้งค่านี้เป็นเวลานาน

```
<setting name="TracingVerbosity" serializeAs="String">
    <value>5</value>
</setting>
```

<a name="activities"></a>

### <a name="activity-types"></a>ชนิดของกิจกรรม

| ชนิดของกิจกรรม | คำอธิบาย |
| --- | --- |
| MGEQ |คิวรีที่การดำเนินการผ่าน ADO.NET ซึ่งรวมไปถึงแหล่งข้อมูล DirectQuery |
| MGEO |คิวรีที่การดำเนินการผ่าน OLEDB ซึ่งรวมไปถึง SAP HANA และ Analysis Services 2016 |
| MGEM |คิวรีที่การดำเนินการผ่านกลไกจัดการ Mashup ซึ่งจะใช้กับชุดข้อมูลที่นำเข้ามาจาก การรีเฟรชตามตารางเวลา หรือการรีเฟรชตามความต้องการ |

### <a name="determine-the-duration-of-a-query"></a>หาระยะเวลาดำเนินการคิวรี
คุณหาเวลาที่ใช้คิวรีแหล่งข้อมูลได้ดังต่อไปนี้

1. เปิดบันทึกเกตเวย์
2. ค้นหา [ประเภทกิจกรรม](#activities) เพื่อหาคิวรี ตัวอย่างเช่น MGEQ
3. ให้จดบันทึก GUID ที่สองเนื่องจากนี่เป็นรหัสคำขอ
4. ค้นหา MGEQ ต่อจนกว่าคุณพบรายการ FireActivityCompletedSuccessfullyEvent ที่มีระยะเวลา คุณสามารถตรวจสอบว่ารายการมีรหัสคำขอเดียวกันหรือไม่ ระยะเวลามีหน่วยเป็นมิลลิวินาที

        DM.EnterpriseGateway Verbose: 0 : 2016-09-26T23:08:56.7940067Z DM.EnterpriseGateway    baf40f21-2eb4-4af1-9c59-0950ef11ec4a    5f99f566-106d-c8ac-c864-c0808c41a606    MGEQ    21f96cc4-7496-bfdd-748c-b4915cb4b70c    B8DFCF12 [DM.Pipeline.Common.TracingTelemetryService] Event: FireActivityCompletedSuccessfullyEvent (duration=5004)

   > [!NOTE]
   > FireActivityCompletedSuccessfullyEvent เป็นรายการแบบละเอียด รายการนี้จะไม่ถูกบันทึกนอกจากว่า TraceVerbosity อยู่ที่ระดับ 5

## <a name="firewall-or-proxy"></a>ไฟร์วอลล์หรือพร็อกซี

สำหรับข้อมูลเกี่ยวกับการให้ข้อมูลพร็อกซีสำหรับเกตเวย์ของคุณ ดูที่[การตั้งค่ากำหนดค่าพร็อกซีสำหรับเกตเวย์ Power BI](service-gateway-proxy.md)

คุณสามารถทดสอบเพื่อดูว่าไฟร์วอลล์หรือพร็อกซีของคุณกำลังบล็อกการเชื่อมต่ออยู่หรือไม่โดยเรียกใช้[Test-NetConnection](https://docs.microsoft.com/powershell/module/nettcpip/test-netconnection)จากพร้อมท์ PowerShell ซึ่งจะทดสอบการเชื่อมต่อไปยัง Azure Service Bus นี่เป็นเพียงการทดสอบการเชื่อมต่อเครือข่าย และไม่เกี่ยวข้องกับบริการระบบคลาวด์เซิร์ฟเวอร์หรือเกตเวย์ ซึ่งจะช่วยบอกว่าเครื่องของคุณสามารถออกอินเทอร์เน็ตได้จริงหรือไม่

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

> [!NOTE]
> Test-NetConnection สามารถใช้งานกับ Windows Server 2012 R2 และรุ่นใหม่กว่าเท่านั้น และยังสามารถใช้งานกับ Windows 8.1 และรุ่นที่ใหม่กว่าได้ด้วย คุณสามารถใช้ Telnet เพื่อทดสอบการเชื่อมต่อของพอร์ตบนระบบปฏิบัติการรุ่นก่อนหน้า

ผลลัพธ์ควรมีลักษณะคล้ายต่อไปนี้ ความแตกต่างจะอยู่กับ TcpTestSucceeded ถ้า**TcpTestSucceeded**ไม่*ถูกต้อง*คุณอาจจะถูกบล็อกโดยไฟร์วอลล์

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

ถ้าคุณต้องการให้ค่า**ComputerName**และ**พอร์ต**ละเอียดถี่ถ้วนและแทนที่รายการที่ระบุสำหรับ[พอร์ต](https://docs.microsoft.com/power-bi/service-gateway-onprem#ports)

ไฟร์วอลล์อาจจะยังบล็อกการเชื่อมต่อที่ Azure Service Bus ทำกับศูนย์ข้อมูล Azure ถ้าเป็นกรณีนี้ คุณจะต้องทำรายการอนุญาต (ยกเลิกการบล็อก) ที่อยู่ IP สำหรับเขตของคุณสำหรับศูนย์ข้อมูลเหล่านั้น คุณสามารถรับรายการของที่อยู่ Azure IP [ได้ที่นี่](https://www.microsoft.com/download/details.aspx?id=41653)

### <a name="network-ports-test"></a>ทดสอบพอร์ตเครือข่าย

การทดสอบพอร์ตเครือข่ายเป็นเครื่องมือในการตรวจสอบว่าเกตเวย์ของคุณสามารถเข้าถึงพอร์ตที่ถูกต้องสำหรับเซิร์ฟเวอร์ระยะไกลทั้งหมดที่จำเป็นโดยเกตเวย์ของคุณสำหรับการโอนย้ายข้อมูล ถ้าการทดสอบพอร์ตเครือข่ายล้มเหลวในการเชื่อมต่อใด ๆ ของพอร์ตที่ เกตเวย์ของคุณอาจพบปัญหาเครือข่าย ถ้าคุณกำลังประสบปัญหาเครือข่ายในขณะนี้กับเกตเวย์ของคุณ เรียกใช้การทดสอบพอร์ตเครือข่ายเพื่อให้แน่ใจว่าคุณมีสภาพแวดล้อมเครือข่ายที่เหมาะสม  

#### <a name="start-a-new-test"></a>เริ่มการทดสอบใหม่

เมื่อต้องการเรียกใช้การทดสอบพอร์ตเครือข่ายใหม ในส่วนติดต่อผู้ใช้เกตเวย์ข้อมูลภายในองค์กร

![เริ่มต้นการทดสอบพอร์ต](media/service-gateway-onprem-tshoot/gateway-onprem-porttest-starttest.png)

เมื่อดำเนินการทดสอบพอร์ตเครือข่าย เกตเวย์ของคุณจะเรียกใช้รายการของพอร์ตและเซิร์ฟเวอร์จาก Azure Service Bus และจากนั้น ระบบจะพยายามเชื่อมต่อกับเซิร์ฟเวอร์และพอร์ตทั้งหมด เมื่อลิงก์เริ่มต้นการทดสอบใหม่ปรากฏ การทดสอบพอร์ตเครือข่ายได้เสร็จสิ้นการดำเนินการ  

#### <a name="test-results"></a>ผลลัพธ์การทดสอบ

ข้อมูลสรุปของการทดสอบสามารถมองเห็นที่ด้านล่างลิงก์เริ่มต้นทดสอบใหม่เป็นผลลัพธ์การทดสอบล่าสุด ผลลัพธ์สองอันเสร็จสมบูรณ์ (สำเร็จ) และเสร็จสมบูรณ์ (ล้มเหลว ดูผลการทดสอบล่าสุด) ถ้าการทดสอบสำเร็จ ดังนั้นเกตเวย์ของคุณเชื่อมต่อกับพอร์ตที่จำเป็นทั้งหมดสำเร็จแล้ว ถ้าการทดสอบล้มเหลว ดังนั้นสภาพแวดล้อมเครือข่ายของคุณอาจกำลังบล็อกพอร์ตและเซิร์ฟเวอร์ที่จำเป็นเหล่านี้ 

![ผลลัพธ์การทดสอบพอร์ต](media/service-gateway-onprem-tshoot/gateway-onprem-porttest-result.png)

เมื่อต้องดูที่เสร็จสมบูรณ์ล่าสุด เลือกเปิดลิงก์ผลลัพธ์ของการทดสอบที่เสร็จสมบูรณ์ล่าสุด ตามที่เห็นด้านล่าง ผลลัพธ์การทดสอบเปิดในตัวแก้ไขข้อความเริ่มต้นของ Windows  

ผลลัพธ์การทดสอบจะแสดงรายการเซิร์ฟเวอร์ พอร์ต และที่อยู่ IP ทั้งหมดที่จำเป็นโดยเกตเวย์ของคุณ ถ้าผลลัพธ์การทดสอบแสดงว่า Closed สำหรับพอร์ตใดก็ตามที่แสดงด้านล่าง ตรวจสอบให้แน่ใจว่าสภาพแวดล้อมเครือข่ายของคุณไม่ได้บล็อกการเชื่อมต่อ คุณอาจจำเป็นต้องติดต่อผู้ดูแลระบบเครือข่ายของคุณเพื่อเปิดพอร์ตที่จำเป็น

![ไฟล์ผลลัพธ์การทดสอบพอร์ต](media/service-gateway-onprem-tshoot/gateway-onprem-porttest-result-file.png)

## <a name="kerberos"></a>Kerberos

ถ้าเซิร์ฟเวอร์ฐานข้อมูลเบื้องต้นและเกตเวย์ข้อมูลภายในองค์กรไม่ถูกกำหนดค่าอย่างเหมาะสมสำหรับ[การมอบหมายที่มีข้อจำกัดของ Kerberos](service-gateway-sso-kerberos.md) ให้เปิดใช้งาน[การบันทึกอย่างละเอียด](#microsoftpowerbidatamovementpipelinediagnosticsdllconfig)บนเกตเวย์ และตรวจสอบโดยยึดจากข้อผิดพลาด/การติดตามในแฟ้มบันทึกของเกตเวย์เป็นจุดเริ่มต้นสำหรับการแก้ไขปัญหา

### <a name="impersonationlevel"></a>ImpersonationLevel

ค่า ImpersonationLevel เกี่ยวข้องกับการตั้งค่า SPN หรือการตั้งค่านโยบายภายใน

```
[DataMovement.PipeLine.GatewayDataAccess] About to impersonate user DOMAIN\User (IsAuthenticated: True, ImpersonationLevel: Identification)
```

**วิธีแก้**

ทำตามขั้นตอนต่อไปนี้เพื่อแก้ไขปัญหา:
1. ตั้งค่า SPN สำหรับเกตเวย์ภายในองค์กร
2. ตั้งค่า การมอบหมายที่มีข้อจำกัดใน Active Directory (AD) ของคุณ

### <a name="failedtoimpersonateuserexception-failed-to-create-windows-identity-for-user-userid"></a>FailedToImpersonateUserException: ล้มเหลวในการสร้างข้อมูลประจำตัวของ Windows สำหรับผู้ใช้ userid

FailedToImpersonateUserException จะเกิดขึ้นถ้าคุณไม่สามารถเลียนแบบในนามของผู้ใช้อื่น ซึ่งอาจเกิดขึ้นถ้าบัญชีผู้ใช้ของคุณกำลังพยายามจะเลียนแบบ มาจากโดเมนอื่นนอกเหนือจากโดเมนที่บริการเกตเวย์อยู่ (นี่เป็นข้อจำกัด)

**วิธีแก้**

* ตรวจสอบว่า การกำหนดค่าถูกต้องตามขั้นตอนในส่วน ImpersonationLevel ด้านบน
* ให้แน่ใจว่า userid ที่จะพยายามเลียนแบบเป็นบัญชี AD ที่ถูกต้อง

### <a name="general-error-1033-error-while-parsing-the-protocol"></a>ข้อผิดพลาดทั่วไป ข้อผิดพลาด 1033 ขณะแยกวิเคราะห์โพรโทคอล

คุณได้รับข้อผิดพลาด 1033 เมื่อ ID ภายนอกของคุณที่ถูกกำหนดค่าใน SAP HANA ไม่ตรงกับการเข้าสู่ระบบถ้าผู้ใช้เลียนแบบโดยใช้ UPN (alias@domain.com) ในบันทึกคุณเห็น "UPN ต้นฉบับ 'alias@domain.com'แทนที่ ด้วย UPN ใหม่'alias@domain.com' ด้านบนของบันทึกข้อผิดพลาดตามที่เห็นด้านล่าง"

```
[DM.GatewayCore] SingleSignOn Required. Original UPN 'alias@domain.com' replaced with new UPN 'alias@domain.com.'
```

**วิธีแก้**

* SAP HANA บังคับว่า ผู้ใช้ที่ต้องการเลียนแบบ ต้องใช้แอตทริบิวต์ sAMAccountName ใน AD (นามแฝงผู้ใช้) ถ้าไม่ถูกต้อง คุณเห็นข้อผิดพลาด 1033

    ![sAMAccount](media/service-gateway-onprem-tshoot/sAMAccount.png)

* ในบันทึก คุณเห็น sAMAccountName (นามแฝง) และไม่ใช่ UPN ซึ่งเป็นนามแฝงที่ตามด้วยโดเมน (alias@doimain.com)

    ![sAMAccount](media/service-gateway-onprem-tshoot/sAMAccount-02.png)

```
      <setting name="ADUserNameReplacementProperty" serializeAs="String">
        <value>sAMAccount</value>
      </setting>
      <setting name="ADServerPath" serializeAs="String">
        <value />
      </setting>
      <setting name="CustomASDataSource" serializeAs="String">
        <value />
      </setting>
      <setting name="ADUserNameLookupProperty" serializeAs="String">
        <value>AADEmail</value>
```

### <a name="sap-aglibodbchdb-dllhdbodbc-communication-link-failure-10709-connection-failed-rte-1-kerberos-error-major-miscellaneous-failure-851968-minor-no-credentials-are-available-in-the-security-package"></a>[SAP AG] [LIBODBCHDB DLL] [HDBODBC] การเชื่อมโยงการสื่อสารล้มเหลว; -10709 เชื่อมต่อล้มเหลว (RTE: ข้อผิดพลาด Kerberos [-1] หลัก: "ล้มเหลวเบ็ดเตล็ด [851968]" รอง: "ไม่มีข้อมูลประจำตัวที่พร้อมใช้งานในแพคเกจการรักษาความปลอดภัย

คุณได้รับข้อความข้อผิดพลาดการเชื่อมต่อล้มเหลว-10709 ถ้าการมอบหมายของคุณไม่ได้กำหนดค่าอย่างถูกต้องใน AD

**วิธีแก้**

* ให้แน่ใจว่า คุณมีเซิร์ฟเวอร์ SAP Hana บนแท็บการรับมอบสิทธิ์ใน AD สำหรับบัญชีบริการเกตเวย์

   ![แท็บการรับมอบสิทธิ์](media/service-gateway-onprem-tshoot/delegation-in-AD.png)

<!-- Shared Troubleshooting tools Include -->
[!INCLUDE [gateway-onprem-tshoot-tools-include](./includes/gateway-onprem-tshoot-tools-include.md)]

### <a name="refresh-history"></a>ประวัติการรีเฟรช

เมื่อใช้เกตเวย์สำหรับรีเฟรชตามกำหนดการ**ประวัติการรีเฟรช**สามารถช่วยให้คุณเห็นข้อผิดพลาดที่เกิดขึ้น ตลอดจนข้อมูลที่เป็นประโยชน์ถ้าคุณต้องการสร้างคำขอการสนับสนุน คุณสามารถดูการรีเฟรชได้ทั้งตามกำหนดการ ตลอดจนตามต้องการ นี่คือวิธีการที่คุณไปที่ **ประวัติการรีเฟรช**

1. ในพื้นที่นำทางของ Power BI ใน**ชุดข้อมูล** เลือกชุดข้อมูล &gt;เปิดเมนู&gt; **กำหนดตารางเวลาการรีเฟรช**

    ![](media/service-gateway-onprem-tshoot/scheduled-refresh.png)
2. ใน**ตั้งค่าสำหรับ...** &gt; **กำหนดตารางเวลาการรีเฟรช**เลือก**ประวัติการรีเฟรช**

    ![](media/service-gateway-onprem-tshoot/scheduled-refresh-2.png)

    ![](media/service-gateway-onprem-tshoot/refresh-history.png)

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการแก้ไขปัญหาการรีเฟรชในสถานการณ์ต่าง ๆ ให้ดูบทความ[การแก้ไขปัญหาการรีเฟรชสถานการณ์ต่าง ๆ](refresh-troubleshooting-refresh-scenarios.md)

## <a name="next-steps"></a>ขั้นตอนถัดไป
[การกำหนดค่าพร็อกซีสำหรับเกตเวย์ Power BI](service-gateway-proxy.md)  
[เกตเวย์ข้อมูลภายในองค์กร](service-gateway-onprem.md)  
[เกตเวย์ข้อมูลในองค์กร - เชิงลึก](service-gateway-onprem-indepth.md)  
[จัดการแหล่งข้อมูลของคุณ - Analysis Services](service-gateway-enterprise-manage-ssas.md)  
[จัดการแหล่งข้อมูลของคุณ - SAP HANA](service-gateway-enterprise-manage-sap.md)  
[จัดการแหล่งข้อมูลของคุณ - SQL Server](service-gateway-enterprise-manage-sql.md)  
[จัดการแหล่งข้อมูลของคุณ - นำเข้า/รีเฟรชตามตารางเวลา](service-gateway-enterprise-manage-scheduled-refresh.md)  
คุณมีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)

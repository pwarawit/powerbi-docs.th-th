---
title: แก้ไขปัญหาเกตเวย์ - Power BI
description: บทความนี้มีข้อมูลวิธีการหลาย ๆ วิธีที่คุณสามารถใช้แก้ไขปัญหาที่พบในเกตเวย์ข้อมูลภายในองค์กร และยังให้วิธีแก้ไขปัญหาที่เกิดจากปัญหาที่รู้จักแล้ว รวมถึงเครื่องมือต่าง ๆ ที่มาช่วยคุณแก้ไขปัญหา
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-gateways
ms.topic: conceptual
ms.date: 07/15/2019
LocalizationGroup: Gateways
ms.openlocfilehash: a013b42f1cd7cc9b2c5c24f9636683a52687ceb8
ms.sourcegitcommit: 277fadf523e2555004f074ec36054bbddec407f8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 07/16/2019
ms.locfileid: "68271401"
---
# <a name="troubleshoot-gateways---power-bi"></a>แก้ไขปัญหาเกตเวย์ - Power BI

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

บทความนี้อธิบายถึงปัญหาทั่วไปเมื่อใช้**เกตเวย์ข้อมูลภายในองค์กร**กับ Power BI ถ้าคุณพบปัญหาที่ไม่ได้อยู่ในรายการด้านล่าง คุณสามารถใช้ไซต์ [ชุมชน](http://community.powerbi.com) Power BI หรือคุณสามารถสร้าง[ตั๋วสนับสนุน](http://powerbi.microsoft.com/support)ได้

## <a name="configuration"></a>การกำหนดค่า

### <a name="error-power-bi-service-reported-local-gateway-as-unreachable-restart-the-gateway-and-try-again"></a>ข้อผิดพลาด: บริการ Power BI รายงานว่าไม่สามารถเข้าถึงเกตเวย์ภายในเครื่องได้ รีสตาร์ทเกตเวย์ และลองอีกครั้ง

ตอนท้ายของการกำหนดค่า บริการ Power BI จะถูกเรียกอีกครั้งเพื่อตรวจสอบเกตเวย์ บริการของ Power BI ไม่ได้รายงานสถานะเกตเวย์ว่า live รีสตาร์ทบริการ windows อาจช่วยให้สื่อสารสำเร็จ คุณสามารถรวบรวมและตรวจทานบันทึกตามที่อธิบายไว้ใน[บันทึกการเก็บรวบรวมจากแอป](/data-integration/gateway/service-gateway-tshoot#collect-logs-from-the-on-premises-data-gateway-app)ในเกตเวย์ข้อมูลภายในองค์กรเพื่อรับข้อมูลรายละเอียดเพิ่มเติม

## <a name="data-sources"></a>แหล่งข้อมูล

### <a name="error-unable-to-connect-details-invalid-connection-credentials"></a>ข้อผิดพลาด: ไม่สามารถเชื่อมต่อได้ รายละเอียด: "ข้อมูลประจำตัวของการเชื่อมต่อไม่ถูกต้อง"

ภายใน**แสดงรายละเอียด**จะแสดงข้อความแสดงข้อผิดพลาดที่ได้รับจากแหล่งข้อมูล สำหรับ SQL Server คุณจะเห็นสิ่งต่อไปนี้

    Login failed for user 'username'.

ตรวจสอบว่า คุณมีชื่อผู้ใช้และรหัสผ่านที่ถูกต้อง อีกทั้ง ตรวจสอบว่า ข้อมูลประจำตัวเหล่านั้นสามารถเชื่อมต่อกับแหล่งข้อมูลเรียบร้อยแล้ว ตรวจสอบให้แน่ใจว่า บัญชีที่ใช้ตรงกับ **วิธีการรับรองความถูกต้อง**

### <a name="error-unable-to-connect-details-cannot-connect-to-the-database"></a>ข้อผิดพลาด: ไม่สามารถเชื่อมต่อได้ รายละเอียด: "ไม่สามารถติดต่อแหล่งข้อมูลได้"

เราสามารถเชื่อมต่อไปยังเซิร์ฟเวอร์ แต่ไม่สามารถเชื่อมต่อไปยังฐานข้อมูลที่ให้มา ตรวจสอบชื่อของฐานข้อมูล และตรวจสอบว่าข้อมูลประจำตัวของผู้ใช้มีสิทธิ์เข้าถึงฐานข้อมูลนั้น

ภายใน**แสดงรายละเอียด**จะแสดงข้อความแสดงข้อผิดพลาดที่ได้รับจากแหล่งข้อมูล สำหรับ SQL Server คุณจะเห็นสิ่งต่อไปนี้

    Cannot open database "AdventureWorks" requested by the login. The login failed. Login failed for user 'username'.

### <a name="error-unable-to-connect-details-unknown-error-in-data-gateway"></a>ข้อผิดพลาด: ไม่สามารถเชื่อมต่อได้ รายละเอียด: "เกิดข้อผิดพลาดที่ไม่รู้จักในเกตเวย์ข้อมูล"

ข้อผิดพลาดนี้อาจเกิดขึ้นจากหลายสาเหตุ ตรวจสอบให้แน่ใจว่าการตรวจสอบว่า คุณสามารถเชื่อมต่อกับแหล่งข้อมูลจากเครื่องที่เกตเวย์ทำงาน นี่อาจเป็นผลของการที่เชื่อมต่อกับเซิร์ฟเวอร์ไม่ได้

ภายใน**แสดงรายละเอียด**คุณสามารถเห็นรหัสข้อผิดพลาดของ**DM_GWPipeline_UnknownError**ได้

คุณยังสามารถค้นหารายละเอียดเพิ่มเติมได้จาก บันทึกเหตุการณ์ > **บันทึกแอปพลิเคชันและบริการ** > **บริการเกตเวย์ข้อมูลในองค์กร**

### <a name="error-we-encountered-an-error-while-trying-to-connect-to-server-details-we-reached-the-data-gateway-but-the-gateway-cant-access-the-on-premises-data-source"></a>ข้อผิดพลาด: เราพบข้อผิดพลาดขณะพยายามเชื่อมต่อกับ\<เซิร์ฟเวอร์\> รายละเอียด: "เราสามารถเข้าถึงเกตเวย์ข้อมูลได้ แต่เกตเวย์ข้อมูลไม่สามารถเข้าถึงแหล่งข้อมูลในองค์กรได้"

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

ตรวจสอบให้แน่ใจว่า คุณได้เพิ่มหนึ่งหรือหลายแหล่งข้อมูลอย่าง ตามที่อธิบายไว้ใน[เพิ่มแหล่งข้อมูล](service-gateway-data-sources.md#add-a-data-source) ถ้าเกตเวย์ไม่ปรากฏในพอร์ทัลผู้ดูแลภายใต้**จัดการเกตเวย์** ลองล้างแคชของเบราว์เซอร์คุณ หรือลงชื่อออกจากบริการแล้วลงชื่อเข้าใช้อีกครั้ง

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

1. แหล่งข้อมูลไม่ตรงกับสิ่งที่อยู่ในชุดข้อมูลต้นแบบ ชื่อเซิร์ฟเวอร์และฐานข้อมูลที่กำหนดในแหล่งข้อมูลของเกตเวย์ข้อมูลในองค์กร และที่คุณใส่ใน Power BI Desktop ต้องตรงกัน ถ้าคุณใช้อยู่ที่อยู่ IP ใน Power BI Desktop แล้ว แหล่งข้อมูลในเกตเวย์ข้อมูลภายในองค์กร ก็ต้องใช้ที่อยู่ IP เช่นกัน
2. ไม่แหล่งข้อมูลใดในเกตเวย์ใด ๆ ภายในองค์กรของคุณพร้อมใช้งาน คุณสามารถกำหนดค่าแหล่งข้อมูลบนเกตเวย์ข้อมูลภายในองค์กรที่มีอยู่หรืออันใหม่

### <a name="error-data-source-access-error-please-contact-the-gateway-administrator"></a>ข้อผิดพลาด: ข้อผิดพลาดในการเข้าถึงแหล่งข้อมูล โปรดติดต่อผู้ดูแลระบบเกตเวย์

ถ้ารายงานนี้ใช้การเชื่อมต่อสดของ Analysis Services คุณอาจเจอปัญหากับค่าถูกส่งผ่านไปยัง EffectiveUserName ที่ไม่ถูกต้อง หรือไม่มีสิทธิ์บนเครื่องของ Analysis Services โดยทั่วไปแล้ว ปัญหาในการรับรองความถูกต้องเกิดจากค่า EffectiveUserName ไม่ตรงกับภายในชื่อผู้ใช้หลัก (UPN) ในเครื่อง

เพื่อการยืนยัน คุณสามารถทำสิ่งต่อไปนี้

1. ค้นหาชื่อผู้ใช้ที่มีผลบังคับใช้จากใน[รายการบันทึกของเกตเวย์](/data-integration/gateway/service-gateway-tshoot#collect-logs-from-the-on-premises-data-gateway-app)
2. เมื่อคุณมีค่าที่ใช้ส่งผ่าน ตรวจสอบว่าข้อมูลนั้นถูกต้อง ถ้าเป็นผู้ใช้ของคุณ คุณสามารถใช้คำสั่งต่อไปนี้จากพร้อมท์คำสั่งเพื่อดู UPN UPN มีลักษณะเหมือนกับที่อยู่อีเมล

        whoami /upn

อีกทางเลือกหนึ่ง คุณดูว่า Power BI ได้รับอะไรจาก Azure Active Directory

1. เรียกดู[ https://developer.microsoft.com/graph/graph-explorer ](https://developer.microsoft.com/graph/graph-explorer)
2. เลือก**ลงชื่อเข้าใช้**มุมบนขวา
3. เรียกใช้คิวรีต่อไปนี้ คุณเห็นการตอบสนอง JSON ขนาดใหญ่แทน

        https://graph.windows.net/me?api-version=1.5
4. ค้นหา**userPrincipalName**

ถ้า Azure Active Directory UPN ของคุณไม่ตรงกับ UPN Active Directory ในเครื่องของคุณ คุณสามารถใช้การ[แมปชื่อผู้ใช้](service-gateway-enterprise-manage-ssas.md#mapping-usernames-for-analysis-services-data-sources)เพื่อแทนที่ด้วยค่าถูกต้องได้ หรือคุณสามารถทำงานกับผู้ดูแลระบบผู้เช่าหรือผู้ดูแลระบบ Active Directory ภายในเครื่องของคุณ เพื่อเปลี่ยน UPN ของคุณ

## <a name="kerberos"></a>Kerberos

ถ้าเซิร์ฟเวอร์ฐานข้อมูลเบื้องต้นและเกตเวย์ข้อมูลภายในองค์กรไม่ถูกกำหนดค่าอย่างเหมาะสมสำหรับ[การมอบหมายที่มีข้อจำกัดของ Kerberos](service-gateway-sso-kerberos.md) ให้เปิดใช้งาน[การบันทึกอย่างละเอียด](/data-integration/gateway/service-gateway-performance#slow-performing-queries)บนเกตเวย์ และตรวจสอบโดยยึดจากข้อผิดพลาด/การติดตามในแฟ้มบันทึกของเกตเวย์เป็นจุดเริ่มต้นสำหรับการแก้ไขปัญหา เมื่อต้องการรวบรวมบันทึกเกตเวย์สำหรับการดู ดูที่ [รวบรวมบันทึกจากแอปในเกตเวย์ข้อมูลภายในองค์กร](/data-integration/gateway/service-gateway-tshoot#collect-logs-from-the-on-premises-data-gateway-app)

### <a name="impersonationlevel"></a>ImpersonationLevel

ค่า ImpersonationLevel เกี่ยวข้องกับการตั้งค่า SPN หรือการตั้งค่านโยบายภายใน

```
[DataMovement.PipeLine.GatewayDataAccess] About to impersonate user DOMAIN\User (IsAuthenticated: True, ImpersonationLevel: Identification)
```

**วิธีแก้**

ทำตามขั้นตอนต่อไปนี้เพื่อแก้ไขปัญหา:

1. ตั้งค่า SPN สำหรับเกตเวย์ภายในองค์กร
2. ตั้งค่าการมอบหมายที่มีข้อจำกัดใน Active Directory (AD) ของคุณ

### <a name="failedtoimpersonateuserexception-failed-to-create-windows-identity-for-user-userid"></a>FailedToImpersonateUserException: ไม่สามารถสร้างข้อมูลประจำตัวของ windows สำหรับผู้ใช้ userid

FailedToImpersonateUserException จะเกิดขึ้นถ้าคุณไม่สามารถเลียนแบบในนามของผู้ใช้อื่น ซึ่งอาจเกิดขึ้นถ้าบัญชีผู้ใช้ของคุณกำลังพยายามจะเลียนแบบ มาจากโดเมนอื่นนอกเหนือจากโดเมนที่บริการเกตเวย์อยู่ (นี่เป็นข้อจำกัด)

**วิธีแก้**

* ตรวจสอบว่า การกำหนดค่าถูกต้องตามขั้นตอนในส่วน ImpersonationLevel ด้านบน
* ให้แน่ใจว่า userid ที่จะพยายามเลียนแบบเป็นบัญชี AD ที่ถูกต้อง

### <a name="general-error-1033-error-while-parsing-the-protocol"></a>ข้อผิดพลาดทั่วไป ข้อผิดพลาด 1033 ขณะแยกวิเคราะห์โพรโทคอล

คุณได้รับข้อผิดพลาด 1033 เมื่อ ID ภายนอกของคุณที่ถูกกำหนดค่าใน SAP HANA ไม่ตรงกับการเข้าสู่ระบบถ้าผู้ใช้เลียนแบบโดยใช้ UPN (alias@domain.com) ในบันทึก คุณจะเห็น "UPN ต้นฉบับ 'alias@domain.com' ถูกแทนที่ ด้วย UPN ใหม่ 'alias@domain.com' ด้านบนของบันทึกข้อผิดพลาดตามรูปด้านล่าง

```
[DM.GatewayCore] SingleSignOn Required. Original UPN 'alias@domain.com' replaced with new UPN 'alias@domain.com.'
```

**วิธีแก้**

* SAP HANA บังคับว่า ผู้ใช้ที่ต้องการเลียนแบบ ต้องใช้แอตทริบิวต์ sAMAccountName ใน AD (นามแฝงผู้ใช้) ถ้าไม่ถูกต้อง คุณเห็นข้อผิดพลาด 1033

    ![sAMAccount](media/service-gateway-onprem-tshoot/sAMAccount.png)

* ในบันทึก คุณเห็น sAMAccountName (นามแฝง) และไม่ใช่ UPN ซึ่งเป็นนามแฝงที่ตามด้วยโดเมน (alias@doimain.com)

    ![sAMAccount](media/service-gateway-onprem-tshoot/sAMAccount-02.png)

```xml
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

### <a name="sap-aglibodbchdb-dllhdbodbc-communication-link-failure-10709-connection-failed-rte-1-kerberos-error-major-miscellaneous-failure-851968-minor-no-credentials-are-available-in-the-security-package"></a>[SAP AG] [LIBODBCHDB DLL] [HDBODBC] การเชื่อมโยงการสื่อสารล้มเหลว; -10709 เชื่อมต่อล้มเหลว (RTE: ข้อผิดพลาด Kerberos [-1] หลัก: "ล้มเหลวไม่รุนแรง [851968]" รอง: "ไม่มีข้อมูลประจำตัวที่พร้อมใช้งานในแพคเกจการรักษาความปลอดภัย

คุณได้รับข้อความข้อผิดพลาดการเชื่อมต่อล้มเหลว-10709 ถ้าการมอบหมายของคุณไม่ได้กำหนดค่าอย่างถูกต้องใน AD

**วิธีแก้**

* ให้แน่ใจว่า คุณมีเซิร์ฟเวอร์ SAP Hana บนแท็บการรับมอบสิทธิ์ใน AD สำหรับบัญชีบริการเกตเวย์

   ![แท็บการรับมอบสิทธิ์](media/service-gateway-onprem-tshoot/delegation-in-AD.png)

## <a name="refresh-history"></a>ประวัติการรีเฟรช

เมื่อใช้เกตเวย์สำหรับรีเฟรชตามกำหนดการ**ประวัติการรีเฟรช**สามารถช่วยให้คุณเห็นข้อผิดพลาดที่เกิดขึ้น ตลอดจนข้อมูลที่เป็นประโยชน์ถ้าคุณต้องการสร้างคำขอการสนับสนุน คุณสามารถดูการรีเฟรชได้ทั้งตามกำหนดการ ตลอดจนตามต้องการ ขั้นตอนต่อไปนี้แสดงวิธีการที่คุณไปที่ **ประวัติการรีเฟรช**

1. ในพื้นที่นำทางของ Power BI ใน**ชุดข้อมูล** เลือกชุดข้อมูล &gt;เปิดเมนู&gt; **กำหนดตารางเวลาการรีเฟรช**

    ![วิธีการเลือกกำหนดเวลารีเฟรช](media/service-gateway-onprem-tshoot/scheduled-refresh.png)

2. ใน**ตั้งค่าสำหรับ...** &gt; **กำหนดตารางเวลาการรีเฟรช**เลือก**ประวัติการรีเฟรช**

    ![เลือกประวัติการรีเฟรช](media/service-gateway-onprem-tshoot/scheduled-refresh-2.png)

    ![การแสดงประวัติการรีเฟรช](media/service-gateway-onprem-tshoot/refresh-history.png)

สำหรับข้อมูลเพิ่มเติมเกี่ยวกับการแก้ไขปัญหาการรีเฟรชในสถานการณ์ต่าง ๆ ให้ดูบทความ[การแก้ไขปัญหาการรีเฟรชสถานการณ์ต่าง ๆ](refresh-troubleshooting-refresh-scenarios.md)

## <a name="fiddler-trace"></a>ติดตาม Fiddler

[Fiddler](http://www.telerik.com/fiddler)เป็นเครื่องมือแบบไม่เสียค่าใช้จ่ายจาก Telerik ที่ใช้ตรวจดูการรับส่งข้อมูลของ HTTP คุณสามารถดูกลับไปกลับมาได้ด้วยบริการ Power BI จากเครื่องลูกค้า ซึ่งอาจจะแสดงข้อผิดพลาดและข้อมูลอื่น ๆ ที่เกี่ยวข้อง

![การใช้การติดตาม Fiddler](media/service-gateway-onprem-tshoot/fiddler.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป

* [แก้ไขปัญหาเกตเวย์ข้อมูลภายในองค์กร](/data-integration/gateway/service-gateway-tshoot)
* [การกำหนดค่าพร็อกซีสำหรับเกตเวย์ข้อมูลภายในองค์กร](/data-integration/gateway/service-gateway-proxy)  
* [จัดการแหล่งข้อมูลของคุณ - Analysis Services](service-gateway-enterprise-manage-ssas.md)  
* [จัดการแหล่งข้อมูลของคุณ - SAP HANA](service-gateway-enterprise-manage-sap.md)  
* [จัดการแหล่งข้อมูลของคุณ - SQL Server](service-gateway-enterprise-manage-sql.md)  
* [จัดการแหล่งข้อมูลของคุณ - นำเข้า/รีเฟรชตามตารางเวลา](service-gateway-enterprise-manage-scheduled-refresh.md)  

คุณมีคำถามเพิ่มเติมหรือไม่ [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)

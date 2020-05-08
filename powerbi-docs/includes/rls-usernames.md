---
ms.openlocfilehash: 3e89344ef1298864b485f465b28c56397a7e1511
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 05/05/2020
ms.locfileid: "61194084"
---
## <a name="using-the-username-or-userprincipalname-dax-function"></a>การใช้ฟังก์ชัน DAX the username() หรือ userprincipalname()
คุณสามารถใช้ประโยชน์จากฟังก์ชัน DAX *username()* หรือ*userprincipalname()* ภายในชุดข้อมูลของคุณได้ คุณสามารถใช้กับนิพจน์ใน Power BI Desktop ได้ เมื่อคุณเผยแพร่แบบจำลองของคุณ จะมีการใช้แบบจำลองภายในบริการ Power BI

ภายใน Power BI Desktop *username()* จะส่งผู้ใช้กลับในรูปแบบของ*DOMAIN\User*และ*userprincipalname()* จะส่งผู้ใช้กลับในรูปแบบของ<em>user@contoso.com</em>

ภายในบริการ Power BI *username()* และ*userprincipalname()* จะส่งกลับชื่อผู้ใช้หลัก (UPN) ซึ่งมีลักษณะคล้ายกับที่อยู่อีเมล์


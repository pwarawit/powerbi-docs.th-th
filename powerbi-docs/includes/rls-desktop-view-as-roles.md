---
ms.openlocfilehash: 8dc488a47ac2b5b4e7980b7404b2722b1120b6ab
ms.sourcegitcommit: cde65bb8b1bed1ee8cf512651afeb829ddc155de
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 02/19/2020
ms.locfileid: "77464417"
---
## <a name="validate-the-roles-within-power-bi-desktop"></a>ตรวจสอบบทบาทภายใน Power BI Desktop
คุณสามารถทดสอบผลลัพธ์ของบทบาทภายใน Power BI Desktop ได้หลังจากที่คุณสร้างบทบาทของตัวเองแล้ว

1. จากแท็บ **การวางรูปแบบ** เลือก **ดูในฐานะบทบาท** 

    ![เลือกดูในฐานะบทบาท](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles.png)

    หน้าต่าง **ดูในฐานะบทบาท** จะปรากฏขึ้นเมื่อคุณมองเห็นบทบาทที่สร้าง

    ![หน้าต่างดูในฐานะบทบาท](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-view-as-roles-dialog.png)

3. เลือกบทบาทที่คุณสร้าง จากนั้นเลือก **ตกลง** เพื่อนำไปใช้กับบทบาทดังกล่าว 

   รายงานจะแสดงข้อมูลที่เกี่ยวข้องกับบทบาทนั้น

4. นอกจากนี้คุณยังสามารถเลือก **ผู้ใช้อื่น** และใส่ผู้ใช้ที่กำหนด 

    ![เลือกผู้ใช้อื่น](./media/rls-desktop-view-as-roles/powerbi-desktop-rls-other-user.png)

   การใส่ชื่อผู้ใช้หลัก (UPN) เป็นสิ่งบริการ Power BI และเซิร์ฟเวอร์รายงาน Power BI จะใช้เป็นสิ่งที่ดีที่สุด

   ภายใน Power BI Desktop **ผู้ใช้อื่น** จะแสดงผลลัพธ์ที่แตกต่างกันในกรณีที่คุณใช้การรักษาความปลอดภัยแบบไดนามิก โดยยึดตามนิพจน์ DAX ของคุณ 

5. เลือก**ตกลง** 

   รายงานจะแสดงผลตามสิ่งที่ผู้ใช้นั้นสามารถมองเห็นได้




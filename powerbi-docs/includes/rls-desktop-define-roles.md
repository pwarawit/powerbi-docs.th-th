## <a name="define-roles-and-rules-in-power-bi-desktop"></a>กำหนดบทบาทและกฎใน Power BI Desktop
คุณสามารถกำหนดบทบาทและกฎภายใน Power BI Desktop เมื่อคุณเผยแพร่ไปยัง Power BI ระบบจะเผยแพร่ไปยังคำจำกัดความบทบาทด้วยเช่นกัน

เมื่อต้องการกำหนดบทบาทความปลอดภัย กรุณาทำตามขั้นตอนเหล่านี้

1. นำเข้าข้อมูลลงในรายงาน Power BI Desktop ของคุณหรือกำหนดค่าการเชื่อมต่อ DirectQuery
   
   > [!NOTE]
   > คุณไม่สามารถกำหนดบทบาทภายใน Power BI Desktop สำหรับข้อมูล Analysis Services แบบ live connection คุณต้องดำเนินการดังกล่าวภายในแบบจำลอง Analysis Services
   > 
   > 
1. เลือกแถบ**แบบจำลอง**
2. เลือก**จัดการบทบาท**
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security.png)
4. เลือก**สร้าง**
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-role.png)
5. ระบุชื่อสำหรับบทบาท 
6. เลือกตารางที่คุณต้องการปรับใช้กฎ DAX
7. ป้อนนิพจน์ DAX นิพจน์นี้จะส่งกลับว่าค่าเป็นจริงหรือเท็จ ตัวอย่างเช่น: [เอนทิตี ID] = "Value"
   
   > [!NOTE]
   > คุณสามารถใช้*username()* ภายในนิพจน์นี้ได้ โปรดทราบว่า*username()* จะมีรูปแบบของ*DOMAIN\username*ภายใน Power BI Desktop ภายในบริการ Power BI และเซิร์ฟเวอร์รายงาน Power BI นั้นอยู่ในรูปแบบของชื่อผู้ใช้หลัก (UPN) ของผู้ใช้ อีกวิธีหนึ่งคือ คุณสามารถใช้ *userprincipalname()* ซึ่งจะส่งผู้ใช้กลับในรูปแบบของชื่อหลักเสมอ *username@contoso.com*
   > 
   > 
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-rule.png)
8. หลังจากที่คุณได้สร้างนิพจน์ DAX แล้วคุณสามารถเลือกทำเครื่องหมายบนกล่องนิพจน์เพื่อตรวจสอบนิพจน์
   
   ![](./media/rls-desktop-define-roles/powerbi-desktop-security-validate-dax.png)
9. เลือก**บันทึก**

คุณไม่สามารถกำหนดผู้ใช้ให้กับบทบาทภายใน Power BI Desktop คุณกำหนดในบริการ Power BI คุณสามารถเปิดใช้งานความปลอดภัยแบบไดนามิกภายใน Power BI Desktop ด้วยการใช้ฟังก์ชัน DAX*username()* หรือ*userprincipalname()* และกำหนดค่าความสัมพันธ์ที่เหมาะสม 


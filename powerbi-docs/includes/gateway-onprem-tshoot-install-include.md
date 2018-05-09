## <a name="update-to-the-latest-version"></a>ปรับปรุงเป็นเวอร์ชันล่าสุด
หากรุ่นของเกตเวย์ไม่ทันสมัยอาจทำให้เกิดปัญหาจำนวนมาก  ดังนั้นหลักปฏิบัติทั่วไปที่ดีคือต้องแน่ใจว่ารุ่นของคุณเป็นรุ่นล่าสุด  ถ้าคุณไม่ได้ปรับปรุงเกตเวย์นานเป็นเดือนหรือนานกว่านั้น คุณอาจจะต้องพิจารณาการติดตั้งเกตเวย์รุ่นล่าสุดและดูว่าจะเกิดปัญหาซ้ำหรือไม่

## <a name="common-issues"></a>ปัญหาทั่วไป
นี่คือปัญหาทั่วไปและวิธีแก้ปัญหาบางส่วนที่ที่ช่วยลูกค้าจำนวนมากในสภาพแวดล้อมที่จำกัดการเข้าถึงอินเทอร์เน็ต

<iframe width="560" height="315" src="https://www.youtube.com/embed/-t7RO6mHATI?showinfo=0" frameborder="0" allowfullscreen></iframe>

### <a name="authentication-to-proxy-server"></a>การรับรองความถูกต้องให้กับพร็อกซีเซิร์ฟเวอร์
พร็อกซีของคุณอาจจำเป็นต้องได้รับการรับรองความถูกต้องจากบัญชีผู้ใช้โดเมน ตามค่าเริ่มต้น เกตเวย์ใช้ Service SID สำหรับผู้ใช้ที่เข้าสู่ระบบบริการ windows การเปลี่ยนแปลงผู้ใช้ที่เข้าสู่ระบบเป็นผู้ใช้โดเมนสามารถช่วยได้ สำหรับข้อมูลเพิ่มเติม ดูที่[การเปลี่ยนบัญชีบริการเกตเวย์เป็นผู้ใช้โดเมน](../service-gateway-proxy.md#changing-the-gateway-service-account-to-a-domain-user)

### <a name="your-proxy-only-allows-ports-80-and-443-traffic"></a>พร็อกซีของคุณอนุญาตให้ใช้การรับส่งข้อมูลพอร์ต 80 และ 443
พร็อกซีบางอย่างจำกัดให้มีการรับส่งข้อมูลไปยังพอร์ต 80 และ 443 เท่านั้น ตามค่าเริ่มต้น การสื่อสารกับ Azure Service Bus จะเกิดขึ้นบนพอร์ตอื่นนอกเหนือจาก 443

คุณสามารถบังคับให้เกตเวย์สื่อสารกับ Azure Service Bus โดยใช้ HTTPS แทนการใช้ TCP โดยตรง คุณจะต้องแก้ไขไฟล์*Microsoft.PowerBI.DataMovement.Pipeline.GatewayCore.dll.config* เปลี่ยนค่าจาก`AutoDetect`เป็น`Https` ไฟล์นี้จะอยู่ที่ *C:\Program Files\On-premises data gateway*ตามค่าเริ่มต้น

```
<setting name="ServiceBusSystemConnectivityModeString" serializeAs="String">
    <value>Https</value>
</setting>
```

## <a name="installation"></a>การติดตั้ง
### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>ข้อผิดพลาด: ไม่สามารถเพิ่มผู้ใช้ไปยังกลุ่ม  (-2147463168   PBIEgwService   Performance Log Users   )
หากคุณกำลังพยายามติดตั้งเกตเวย์บนตัวควบคุมโดเมน คุณอาจพบข้อผิดพลาดนี้ การใช้งานบนตัวควบคุมโดเมนไม่ได้รับการสนับสนุน คุณจะต้องใช้งานเกตเวย์บนเครื่องที่ไม่ใช่ตัวควบคุมโดเมน


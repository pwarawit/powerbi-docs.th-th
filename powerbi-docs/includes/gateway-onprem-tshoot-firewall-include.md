## <a name="firewall-or-proxy"></a>ไฟร์วอลล์หรือพร็อกซี
สำหรับข้อมูลเกี่ยวกับการให้ข้อมูลพร็อกซีสำหรับเกตเวย์ของคุณ ดูที่[การตั้งค่ากำหนดค่าพร็อกซีสำหรับเกตเวย์ Power BI](../service-gateway-proxy.md)

คุณสามารถทดสอบเพื่อดูว่าไฟร์วอลล์หรือพร็อกซีของคุณถูกบล็อกการเชื่อมต่ออยู่หรือไม่โดยเรียกใช้[Test-NetConnection](https://technet.microsoft.com/library/dn372891.aspx)จากพร้อมท์ PowerShell ซึ่งจะทดสอบการเชื่อมต่อไปยัง Azure Service Bus นี่เป็นเพียงการทดสอบการเชื่อมต่อเครือข่าย และไม่เกี่ยวข้องกับบริการระบบคลาวด์เซิร์ฟเวอร์หรือเกตเวย์ ซึ่งจะช่วยบอกว่าเครื่องของคุณสามารถออกอินเทอร์เน็ตได้จริงหรือไม่

    Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350

> [!NOTE]
> Test-NetConnection สามารถใช้งานกับ Windows Server 2012 R2 และรุ่นใหม่กว่าเท่านั้น และยังสามารถใช้งานกับ Windows 8.1 และรุ่นที่ใหม่กว่าได้ด้วย คุณสามารถใช้ Telnet เพื่อทดสอบการเชื่อมต่อของพอร์ตบนระบบปฏิบัติการรุ่นก่อนหน้า
> 
> 

ผลลัพธ์ควรมีลักษณะคล้ายต่อไปนี้ ความแตกต่างจะอยู่กับ TcpTestSucceeded ถ้า**TcpTestSucceeded**ไม่*ถูกต้อง*คุณอาจจะถูกบล็อกโดยไฟร์วอลล์

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

ถ้าคุณต้องการให้ค่า**ComputerName**และ**พอร์ต**ละเอียดถี่ถ้วนและแทนที่รายการที่ระบุสำหรับ[พอร์ต](../service-gateway-onprem.md#ports)

ไฟร์วอลล์อาจจะยังบล็อกการเชื่อมต่อที่ Azure Service Bus ทำกับศูนย์ข้อมูล Azure ถ้าเป็นกรณีนี้ คุณจะต้องไปที่รายการที่อนุญาต (ยกเลิกบล็อก) ที่อยู่ IP สำหรับเขตของคุณสำหรับศูนย์ข้อมูลเหล่านั้น คุณสามารถรับรายการของที่อยู่ Azure IP [ได้ที่นี่](https://www.microsoft.com/download/details.aspx?id=41653)


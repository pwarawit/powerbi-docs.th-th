---
title: Spark บน HDInsight พร้อม DirectQuery
description: Spark บน HDInsight พร้อม DirectQuery
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/01/2018
LocalizationGroup: Data from databases
ms.openlocfilehash: 398737276e55e15273a2245a4b7a72fdca938438
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 01/15/2019
ms.locfileid: "54287727"
---
# <a name="spark-on-hdinsight-with-directquery"></a>Spark บน HDInsight พร้อม DirectQuery

Spark บน Azure HDInsight ที่มี DirectQuery ช่วยให้คุณสามารถสร้างรายงานแบบไดนามิกที่ยึดตามข้อมูลและการวัดในกลุ่มเครื่อง Spark ของคุณที่มีอยู่แล้วได้ ด้วย DirectQuery แบบสอบถามจะถูกส่งกลับไปยังกลุ่มเครื่อง Azure HDInsight Spark ขณะที่คุณสำรวจข้อมูลในมุมมองรายงาน ประสบการณ์การใช้งานนี้แนะนำสำหรับผู้ใช้ที่คุ้นเคยกับเอนทิตีที่ผู้ใช้งานดังกล่าวเชื่อมต่อด้วย

> [!WARNING]
> มีการปิดใช้งานรีเฟรชไทล์อัตโนมัติสำหรับแดชบอร์ดที่สร้างขึ้นบนชุดข้อมูลตาม Spark คุณสามารถเลือก**รีเฟรชไทล์แดชบอร์ด**เพื่อรีเฟรชด้วยตนเองได้ รายงานไม่ได้รับผลกระทบ และควรอัปเดตอยู่เสมอ 

คุณสามารถใช้ขั้นตอนต่อไปนี้เพื่อเชื่อมต่อ Spark ของคุณบนแหล่งข้อมูล Azure HDInsight โดยใช้ DirectQuery ภายในบริการ Power BI ได้

> [!Important]
> เรามีการปรับปรุงการเชื่อมต่อของเรากับ Spark  สำหรับประสบการณ์ดีที่สุดในการเชื่อมต่อกับแหล่งข้อมูล Spark ของคุณ ใช้ Power BI Desktop  เมื่อคุณได้สร้างรูปแบบข้อมูลและรายงานของคุณแล้ว คุณสามารถเผยแพร่สิ่งดังกล่าวไปยังบริการ Power BI  ตัวเชื่อมต่อโดยตรงสำหรับ Spark ในบริการ Power BI ในขณะนี้ไม่ได้รับการสนับสนุน

1. เลือกปุ่ม**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ

     ![](media/spark-on-hdinsight-with-direct-connect/spark-getdata.png)
2. เลือก**ฐานข้อมูลและเพิ่มเติม**

     ![](media/spark-on-hdinsight-with-direct-connect/spark-getdata-databases.png)
3. เลือกตัวเชื่อมต่อ **Spark บน HDInsight** และเลือก**เชื่อมต่อ**

     ![](media/spark-on-hdinsight-with-direct-connect/spark-getdata-databases-connect.png)
4. ใส่ชื่อของ**เซิร์ฟเวอร์**ที่คุณต้องการเชื่อมต่อ และ**ชื่อผู้ใช้**และ**รหัสผ่าน**ของคุณ เซิร์ฟเวอร์จะอยู่ในรูปแบบ\<clustername\>azurehdinsight.net่เสมอ ดูรายละเอียดเพิ่มเติมเกี่ยวกับการค้นหาค่าเหล่านี้

     ![](media/spark-on-hdinsight-with-direct-connect/spark-server-name.png)

     ![](media/spark-on-hdinsight-with-direct-connect/spark-username.png)
5. เมื่อเชื่อมต่อแล้ว คุณจะเห็นชุดข้อมูลใหม่ที่มีชื่อว่า "SparkDataset" นอกจากนี้ คุณยังสามารถเข้าถึงชุดข้อมูลได้ผ่านคำอธิบายคุณลักษณะไทล์ที่สร้างขึ้น

     ![](media/spark-on-hdinsight-with-direct-connect/spark-dataset.png)
6. การเจาะลึกลงในชุดข้อมูลทำให้คุณสามารถสำรวจตารางและคอลัมน์ทั้งหมดในฐานข้อมูลของคุณได้ การเลือกคอลัมน์จะเป็นการส่งแบบสอบถามกลับไปยังแหล่งข้อมูล และสร้างภาพของคุณแบบไดนามิก ภาพเหล่านี้สามารถถูกบันทึกไว้ในรายงานใหม่และปักหมุดกลับไปยังแดชบอร์ดของคุณได้

## <a name="finding-your-spark-on-hdinsight-parameters"></a>ค้นหา Spark ของคุณบนพารามิเตอร์ HDInsight

เซิร์ฟเวอร์อยู่ในรูปแบบ\<clustername\>azurehdinsight.net เสมอ และสามารถพบได้ในพอร์ทัล Azure

![](media/spark-on-hdinsight-with-direct-connect/spark-server-name-parameter.png)

ชื่อผู้ใช้และรหัสผ่านสามารถอยู่ในพอร์ทัล Azure ได้เช่นกัน

## <a name="limitations"></a>ข้อจำกัด

ข้อจำกัดและบันทึกย่อเหล่านี้อาจเปลี่ยนแปลงขณะที่เราปรับปรุงประสบการณ์การใช้งานขึ้นเรื่อย ๆ สามารถดูเอกสารเพิ่มเติมได้ที่[ใช้เครื่องมือ BI กับ Apache Spark บน Azure HDInsight](/azure/hdinsight/spark/apache-spark-use-bi-tools/)

* บริการ Power BI สนับสนุนเฉพาะการกำหนดค่าของ Spark 2.0 และ HDInsight 3.5 เท่านั้น
* ทุกการดำเนินการ เช่น การเลือกคอลัมน์หรือเพิ่มตัวกรองจะส่งแบบสอบถามย้อนกลับไปยังฐานข้อมูล ดังนั้น ก่อนที่จะเลือกเขตข้อมูลที่มีขนาดใหญ่มาก ให้พิจารณาเลือกชนิดภาพที่เหมาะสมก่อน
* การถามตอบไม่พร้อมใช้งานสำหรับชุดข้อมูล DirectQuery
* การเปลี่ยนแปลงเค้าร่างจะไม่ถูกเลือกโดยอัตโนมัติ
* Power BI สนับสนุน 16000 คอลัมน์ **ทั่วตารางทั้งหมด**ภายในชุดข้อมูล นอกจากนี้ Power BI ยังรวมถึงคอลัมน์ตัวเลขแถวภายในต่อตาราง ซึ่งหมายความว่า ถ้าคุณมี 100 ตารางในชุดข้อมูล จำนวนคอลัมน์ที่พร้อมใช้งานจะเป็น 15,900 คุณอาจพบข้อจำกัดนี้ ซึ่งขึ้นอยู่กับจำนวนข้อมูลที่คุณกำลังทำงานอยู่จากแหล่งข้อมูล Spark ของคุณ

## <a name="troubleshooting"></a>การแก้ไขปัญหา

ถ้าคุณกำลังมีปัญหาในการดำเนินการแบบสอบถามเทียบกับกลุ่มเครื่องของคุณ ตรวจสอบแอปพลิเคชันว่ายังคงทำงานอยู่หรือไม่ และเริ่มต้นใหม่ถ้าจำเป็น

นอกจากนี้ คุณสามารถจัดสรรทรัพยากรเพิ่มเติมภายในพอร์ทัล Azure ได้ภายใต้**กำหนดค่า** > **ปรับมาตราส่วนกลุ่มเครื่อง**:

![](media/spark-on-hdinsight-with-direct-connect/spark-scale.png)

## <a name="next-steps"></a>ขั้นตอนถัดไป

[เริ่มใช้งาน: สร้างกลุ่มเครื่อง Apache Spark บน HDInsight Linux และเรียกใช้แบบสอบถามแบบโต้ตอบโดยใช้ Spark SQL](/azure/hdinsight/spark/apache-spark-jupyter-spark-sql/)  
[Power BI คืออะไร](power-bi-overview.md)  
[รับข้อมูลสำหรับ Power BI](service-get-data.md)
[ใช้ Kerberos บนเกตเวย์ภายในองค์กรสำหรับ SSO](service-gateway-sso-kerberos.md)

มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)
---
title: Spark บน HDInsight พร้อม DirectQuery
description: Spark บน HDInsight พร้อม DirectQuery
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 06/28/2017
ms.author: maghan
LocalizationGroup: Data from databases
ms.openlocfilehash: 236a3d1bde84d4259d921d44730057a4e2fd3591
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: th-TH
ms.lasthandoff: 06/04/2018
ms.locfileid: "34256759"
---
# <a name="spark-on-hdinsight-with-directquery"></a>Spark บน HDInsight พร้อม DirectQuery
Spark บน Azure HDInsight ที่มี DirectQuery ช่วยให้คุณสามารถสร้างรายงานแบบไดนามิกที่ยึดตามข้อมูลและการวัดในกลุ่มเครื่อง Spark ของคุณที่มีอยู่แล้วได้ ด้วย DirectQuery แบบสอบถามจะถูกส่งกลับไปยังกลุ่มเครื่อง Azure HDInsight Spark ขณะที่คุณสำรวจข้อมูลในมุมมองรายงาน ประสบการณ์การใช้งานนี้แนะนำสำหรับผู้ใช้ที่คุ้นเคยกับเอนทิตีที่ผู้ใช้งานดังกล่าวเชื่อมต่อด้วย

> [!WARNING]
> มีการปิดใช้งานรีเฟรชไทล์อัตโนมัติสำหรับแดชบอร์ดที่สร้างขึ้นบนชุดข้อมูลตาม Spark คุณสามารถเลือก**รีเฟรชไทล์แดชบอร์ด**เพื่อรีเฟรชด้วยตนเองได้ รายงานไม่ได้รับผลกระทบ และควรอัปเดตอยู่เสมอ 
> 
> 

คุณสามารถใช้ขั้นตอนต่อไปนี้เพื่อเชื่อมต่อ Spark ของคุณบนแหล่งข้อมูล Azure HDInsight โดยใช้ DirectQuery ภายในบริการ Power BI ได้

1. เลือก**รับข้อมูล**ที่ด้านล่างของพื้นที่นำทางด้านซ้ายมือ
   
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
ข้อจำกัดและบันทึกย่อเหล่านี้อาจเปลี่ยนแปลงขณะที่เราปรับปรุงประสบการณ์การใช้งานขึ้นเรื่อย ๆ สามารถดูเอกสารเพิ่มเติมได้ที่[ใช้เครื่องมือ BI กับ Apache Spark บน Azure HDInsight](https://azure.microsoft.com/documentation/articles/hdinsight-apache-spark-use-bi-tools/)

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
[เริ่มต้นใช้งาน: สร้างกลุ่มเครื่อง Apache Spark บน HDInsight Linux และเรียกใช้แบบสอบถามแบบโต้ตอบโดยใช้ Spark SQL](https://azure.microsoft.com/documentation/articles/hdinsight-apache-spark-jupyter-spark-sql)  
[เริ่มต้นใช้งาน Power BI](service-get-started.md)  
[รับข้อมูลสำหรับ Power BI](service-get-data.md)  
มีคำถามเพิ่มเติมหรือไม่? [ลองไปที่ชุมชน Power BI](http://community.powerbi.com/)


---
title: เพิ่มการอ้างอิงบทบาท ARC ให้กับเอกสาร XBRL
linktitle: เพิ่มการอ้างอิงบทบาท ARC ให้กับเอกสาร XBRL
second_title: Aspose.Finance .NET API
description: เรียนรู้วิธีจัดการเอกสาร XBRL อย่างมีประสิทธิภาพโดยใช้ Aspose.Finance สำหรับ .NET เพิ่มการอ้างอิงบทบาท ARC ได้อย่างง่ายดายพร้อมคำแนะนำทีละขั้นตอน
type: docs
weight: 10
url: /th/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## การแนะนำ
ในโลกของการจัดการและการรายงานข้อมูลทางการเงิน eXtensible Business Reporting Language (XBRL) มีบทบาทสำคัญ โดยกำหนดมาตรฐานวิธีการสื่อสารและแลกเปลี่ยนข้อมูลทางการเงิน เพื่อให้มั่นใจถึงความสม่ำเสมอ ความถูกต้อง และมีประสิทธิภาพ อย่างไรก็ตาม การจัดการกับเอกสาร XBRL โดยเฉพาะอย่างยิ่งเมื่อรวมบทบาทและการอ้างอิงเฉพาะเข้าด้วยกัน จำเป็นต้องมีความเข้าใจอย่างละเอียดถี่ถ้วนเกี่ยวกับกลไกพื้นฐาน บทช่วยสอนนี้มุ่งเน้นไปที่งานอย่างหนึ่ง: การเพิ่มการอ้างอิงบทบาท ARC ให้กับเอกสาร XBRL โดยใช้ Aspose.Finance สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
### การตั้งค่าสภาพแวดล้อม
1.  ติดตั้ง Aspose.Finance สำหรับ .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Finance สำหรับ .NET จาก[เผยแพร่](https://releases.aspose.com/finance/net/).
   
2. สภาพแวดล้อมการพัฒนา: ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณด้วย Visual Studio หรือ IDE ที่ต้องการอื่นๆ
## นำเข้าเนมสเปซ
ตรวจสอบให้แน่ใจว่าได้นำเข้าเนมสเปซที่จำเป็นในโค้ด C# ของคุณ:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีต้นทางและเอาต์พุต
ก่อนดำเนินการต่อ ให้ระบุไดเร็กทอรีต้นทางและเอาต์พุตที่จะวางและบันทึกไฟล์ XBRL ของคุณตามลำดับ
```csharp
// ไดเรกทอรีต้นทาง
string sourceDir = "Your Source Directory";
// ไดเร็กทอรีเอาต์พุต
string outputDir = "Your Output Directory";
```
## ขั้นตอนที่ 2: สร้างเอกสาร XBRL
 ยกตัวอย่าง`XbrlDocument` วัตถุที่จะทำงานกับข้อมูล XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
## ขั้นตอนที่ 3: เข้าถึง XbrlInstance Collection
เข้าถึงคอลเลกชันของอินสแตนซ์ XBRL ภายในเอกสาร
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## ขั้นตอนที่ 4: เพิ่ม XbrlInstance
เพิ่มอินสแตนซ์ XBRL ใหม่ให้กับคอลเลกชัน
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## ขั้นตอนที่ 5: เพิ่มการอ้างอิงสคีมา
รวมการอ้างอิงสคีมาในอินสแตนซ์ XBRL โดยระบุไดเรกทอรีต้นทาง คำนำหน้าเนมสเปซ และ URI
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
## ขั้นตอนที่ 6: ดึงข้อมูล ArcroleType
 ดึงข้อมูล`ArcroleType` ตาม URI ที่เฉพาะเจาะจง
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/เชิงอรรถ-test");
```
## ขั้นตอนที่ 7: เพิ่ม ArcroleReference
 ถ้า`ArcroleType` พบสร้าง`ArcroleReference` และเพิ่มลงในการอ้างอิงอาร์โครลของอินสแตนซ์ XBRL
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## ขั้นตอนที่ 8: บันทึกเอกสาร
บันทึกเอกสาร XBRL ที่แก้ไขไปยังไดเร็กทอรีเอาต์พุตที่ระบุ
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## บทสรุป
ในบทช่วยสอนนี้ เราได้สำรวจวิธีการเพิ่มการอ้างอิงบทบาท ARC ให้กับเอกสาร XBRL โดยใช้ Aspose.Finance สำหรับ .NET ด้วยการทำตามคำแนะนำทีละขั้นตอนเหล่านี้และใช้ประโยชน์จากความสามารถของ Aspose.Finance คุณสามารถจัดการและจัดการข้อมูล XBRL ได้อย่างมีประสิทธิภาพเพื่อให้ตรงตามความต้องการเฉพาะของคุณ
## คำถามที่พบบ่อย
### XBRL คืออะไร?
XBRL ย่อมาจาก eXtensible Business Reporting Language ซึ่งเป็นภาษามาตรฐานสำหรับการสื่อสารทางอิเล็กทรอนิกส์ของข้อมูลทางธุรกิจและข้อมูลทางการเงิน
### เหตุใด XBRL จึงมีความสำคัญ
XBRL รับประกันความสม่ำเสมอ ความถูกต้อง และมีประสิทธิภาพในการแลกเปลี่ยนและการวิเคราะห์ข้อมูลทางการเงิน ซึ่งเป็นประโยชน์ต่อหน่วยงานกำกับดูแล นักวิเคราะห์ และธุรกิจ
### Aspose.Finance สามารถจัดการงาน XBRL ที่ซับซ้อนได้หรือไม่
ใช่ Aspose.Finance นำเสนอฟังก์ชันการทำงานที่มีประสิทธิภาพสำหรับการทำงานกับเอกสาร XBRL รวมถึงการจัดการงานที่ซับซ้อน เช่น การอ้างอิงบทบาทและการจัดการอนุกรมวิธาน
### Aspose.Finance เข้ากันได้กับไลบรารี .NET อื่นหรือไม่
ใช่ Aspose.Finance ทำงานร่วมกับไลบรารี .NET อื่นๆ ได้อย่างราบรื่น โดยให้การสนับสนุนอย่างกว้างขวางสำหรับการจัดการและการรายงานข้อมูลทางการเงิน
### ฉันจะรับการสนับสนุนเพิ่มเติมสำหรับ Aspose.Finance ได้ที่ไหน
 สำหรับการสนับสนุนเพิ่มเติมโปรดไปที่[หน้าสนับสนุน Aspose.Finance](https://forum.aspose.com/c/finance/43).
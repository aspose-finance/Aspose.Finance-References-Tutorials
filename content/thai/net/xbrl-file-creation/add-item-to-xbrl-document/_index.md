---
title: เพิ่มรายการลงในเอกสาร XBRL
linktitle: เพิ่มรายการลงในเอกสาร XBRL
second_title: Aspose.Finance .NET API
description: เรียนรู้วิธีเพิ่มรายการลงในเอกสาร XBRL โดยใช้ Aspose.Finance สำหรับ .NET ลดความซับซ้อนในการรายงานทางการเงินในแอปพลิเคชัน .NET ของคุณ #จัดสรร #การเงิน
type: docs
weight: 13
url: /th/net/xbrl-file-creation/add-item-to-xbrl-document/
---
Extensible Business Reporting Language (XBRL) ได้กลายเป็นรูปแบบมาตรฐานสำหรับการรายงานทางการเงิน ซึ่งช่วยให้สามารถสื่อสารข้อมูลทางการเงินได้อย่างมีประสิทธิภาพและแม่นยำ Aspose.Finance สำหรับ .NET มีฟังก์ชันการทำงานที่มีประสิทธิภาพในการทำงานกับเอกสาร XBRL ในแอปพลิเคชัน .NET ของคุณ ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนต่างๆ ในการเพิ่มรายการลงในเอกสาร XBRL โดยใช้ Aspose.Finance สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
### 1. ติดตั้ง Aspose.Finance สำหรับ .NET
 หากคุณยังไม่ได้ดาวน์โหลดและติดตั้ง Aspose.Finance สำหรับ .NET จาก[เว็บไซต์อย่างเป็นทางการ](https://releases.aspose.com/finance/net/)- ปฏิบัติตามคำแนะนำในการติดตั้งเพื่อตั้งค่าไลบรารีในสภาพแวดล้อม .NET ของคุณ
### 2. ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ
ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อมการพัฒนาที่ใช้งานได้สำหรับการพัฒนา .NET คุณจะต้องมี IDE ที่เข้ากันได้ เช่น Visual Studio พร้อมด้วยเฟรมเวิร์ก .NET ที่ติดตั้งบนระบบของคุณ
## นำเข้าเนมสเปซ
ขั้นแรก นำเข้าเนมสเปซที่จำเป็นลงในแอปพลิเคชัน .NET ของคุณเพื่อใช้ฟังก์ชันการทำงานที่ Aspose.Finance สำหรับ .NET มอบให้
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#ตอนนี้ เราจะแบ่งโค้ดตัวอย่างออกเป็นหลายขั้นตอน:
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีต้นทางและเอาต์พุต
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 แทนที่`"Your Source Directory"` และ`"Your Output Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีต้นทางและเอาต์พุตของคุณตามลำดับ
## ขั้นตอนที่ 2: สร้างเอกสาร XBRL และอินสแตนซ์
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
เริ่มต้นเอกสาร XBRL และอินสแตนซ์ที่จะใช้งานได้
## ขั้นตอนที่ 3: เพิ่มการอ้างอิงสคีมา
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
เพิ่มการอ้างอิงสคีมาให้กับอินสแตนซ์ XBRL โดยระบุเส้นทางไปยังไฟล์สคีมาและระบุรายละเอียดเนมสเปซ
## ขั้นตอนที่ 4: กำหนดบริบทและเอนทิตี
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
สร้างบริบทและเอนทิตีสำหรับอินสแตนซ์ XBRL โดยระบุช่วงเวลาและรายละเอียดเอนทิตี
## ขั้นตอนที่ 5: เพิ่มหน่วย
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
กำหนดหน่วยสำหรับอินสแตนซ์ XBRL โดยระบุชื่อที่ผ่านการรับรองการวัด
## ขั้นตอนที่ 6: เพิ่มรายการ
```csharp
Concept fixedAssetsConcept = schema.GetConceptByName("fixedAssets");
if (fixedAssetsConcept != null)
{
    Item item = new Item(fixedAssetsConcept);
    item.ContextRef = context;
    item.UnitRef = unit;
    item.Precision = 4;
    item.Value = "1444";
    xbrlInstance.Facts.Add(item);
}
```
เพิ่มรายการลงในอินสแตนซ์ XBRL โดยระบุแนวคิด บริบท หน่วย ความแม่นยำ และค่า
## ขั้นตอนที่ 7: บันทึกเอกสาร
```csharp
document.Save(outputDir + @"document5.xbrl");
```
บันทึกเอกสาร XBRL ไปยังไดเร็กทอรีเอาต์พุต
## บทสรุป
การเพิ่มรายการลงในเอกสาร XBRL เป็นสิ่งจำเป็นสำหรับการแสดงข้อมูลทางการเงินอย่างถูกต้อง Aspose.Finance สำหรับ .NET ทำให้กระบวนการนี้ง่ายขึ้นโดยการจัดหา API ที่ครอบคลุมเพื่อทำงานกับเอกสาร XBRL ในแอปพลิเคชัน .NET
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Finance สำหรับ .NET กับแอปพลิเคชัน .NET ใดๆ ได้หรือไม่
ใช่ Aspose.Finance สำหรับ .NET เข้ากันได้กับแอปพลิเคชัน .NET ใดๆ รวมถึงแอปพลิเคชัน ASP.NET, WinForms และคอนโซล
### Aspose.Finance สำหรับ .NET ใช้งานได้ฟรีหรือไม่
 Aspose.Finance สำหรับ .NET เป็นห้องสมุดเชิงพาณิชย์ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีเพื่อประเมินคุณลักษณะต่างๆ และสามารถซื้อใบอนุญาตได้จาก[ที่นี่](https://purchase.aspose.com/buy).
### Aspose.Finance สำหรับ .NET รองรับรูปแบบการรายงานทางการเงินอื่นๆ นอกเหนือจาก XBRL หรือไม่
Aspose.Finance สำหรับ .NET มุ่งเน้นไปที่ฟังก์ชันการทำงานที่เกี่ยวข้องกับ XBRL เป็นหลัก อย่างไรก็ตาม Aspose มีไลบรารีอื่นๆ สำหรับการทำงานกับรูปแบบทางการเงินที่แตกต่างกัน
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Finance สำหรับ .NET ได้อย่างไร
 คุณสามารถรับการสนับสนุนสำหรับ Aspose.Finance สำหรับ .NET ผ่านทาง[ฟอรั่มอย่างเป็นทางการ](https://forum.aspose.com/c/finance/43)ซึ่งคุณสามารถถามคำถามและโต้ตอบกับผู้ใช้รายอื่นและเจ้าหน้าที่ฝ่ายสนับสนุนได้
### ฉันสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Finance สำหรับ .NET ได้หรือไม่
 ใช่ สิทธิ์การใช้งานชั่วคราวสำหรับ Aspose.Finance สำหรับ .NET นั้นมีไว้เพื่อการทดสอบ คุณสามารถได้รับอย่างใดอย่างหนึ่ง[ที่นี่](https://purchase.aspose.com/temporary-license/).
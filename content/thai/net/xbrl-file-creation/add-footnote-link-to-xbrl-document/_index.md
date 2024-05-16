---
title: เพิ่มลิงก์เชิงอรรถไปยังเอกสาร XBRL
linktitle: เพิ่มลิงก์เชิงอรรถไปยังเอกสาร XBRL
second_title: Aspose.Finance .NET API
description: เรียนรู้วิธีเพิ่มลิงก์เชิงอรรถไปยังเอกสาร XBRL โดยใช้ Aspose.Finance สำหรับ .NET ปรับปรุงรายงานทางการเงินด้วยบริบทเพิ่มเติมได้อย่างง่ายดาย
type: docs
weight: 12
url: /th/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
การเพิ่มลิงก์เชิงอรรถไปยังเอกสาร XBRL มีความสำคัญอย่างยิ่งในการให้บริบทหรือคำอธิบายเพิ่มเติมสำหรับจุดข้อมูลเฉพาะ ในบทช่วยสอนนี้ เราจะอธิบายกระบวนการทีละขั้นตอนโดยใช้ Aspose.Finance สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1.  Aspose.Finance สำหรับ .NET: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Finance สำหรับ .NET บนระบบของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/finance/net/).
  
2. สภาพแวดล้อมการพัฒนา: มีสภาพแวดล้อมการพัฒนาที่ตั้งค่าด้วย .NET Framework หรือ .NET Core
## นำเข้าเนมสเปซ:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีต้นทางและเอาต์พุต
ขั้นแรก ให้ระบุไดเร็กทอรีสำหรับไฟล์ต้นฉบับและไฟล์เอาต์พุต:
```csharp
// ไดเรกทอรีต้นทาง
string sourceDir = "Your Source Directory";
// ไดเร็กทอรีเอาต์พุต
string outputDir = "Your Output Directory";
```
## ขั้นตอนที่ 2: สร้างเอกสาร XBRL และอินสแตนซ์
เริ่มต้นเอกสาร XBRL และอินสแตนซ์:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## ขั้นตอนที่ 3: เพิ่มการอ้างอิงสคีมา
เพิ่มการอ้างอิงสคีมาให้กับอินสแตนซ์ XBRL:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## ขั้นตอนที่ 4: กำหนดบริบท
กำหนดบริบทสำหรับอินสแตนซ์ XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## ขั้นตอนที่ 5: เพิ่มลิงก์เชิงอรรถ
สร้างและเพิ่มลิงก์เชิงอรรถไปยังอินสแตนซ์ XBRL:
```csharp
FootnoteLink footnoteLink = new FootnoteLink();
Footnote footnote = new Footnote("footnote1");
footnote.Text = "Including the effects of the merger.";
Loc loc = new Loc("#cd1", "fact1");
FootnoteArc footnoteArc = new FootnoteArc(loc.Label, footnote.Label);
footnoteLink.Footnotes.Add(footnote);
footnoteLink.Locators.Add(loc);
footnoteLink.FootnoteArcs.Add(footnoteArc);
xbrlInstance.FootnoteLinks.Add(footnoteLink);
```
## ขั้นตอนที่ 6: บันทึกเอกสาร
บันทึกเอกสาร XBRL ที่แก้ไข:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## บทสรุป
การเพิ่มลิงก์เชิงอรรถไปยังเอกสาร XBRL เป็นกระบวนการที่ไม่ซับซ้อนกับ Aspose.Finance สำหรับ .NET ด้วยการทำตามขั้นตอนที่ระบุไว้ในบทช่วยสอนนี้ คุณสามารถรวมบริบทหรือคำอธิบายเพิ่มเติมลงในรายงานทางการเงินของคุณได้อย่างราบรื่น
## คำถามที่พบบ่อย
### ฉันสามารถเพิ่มลิงก์เชิงอรรถหลายรายการไปยังเอกสาร XBRL เดียวได้หรือไม่
ได้ คุณสามารถเพิ่มลิงก์เชิงอรรถได้หลายลิงก์โดยทำซ้ำขั้นตอนที่อธิบายไว้ในบทช่วยสอนนี้สำหรับแต่ละลิงก์เพิ่มเติม
### Aspose.Finance สำหรับ .NET เข้ากันได้กับทั้ง .NET Framework และ .NET Core หรือไม่
ใช่ Aspose.Finance สำหรับ .NET รองรับทั้งสภาพแวดล้อม .NET Framework และ .NET Core
### ฉันจะขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Finance สำหรับ .NET ได้อย่างไร
 คุณสามารถขอรับใบอนุญาตชั่วคราวได้จาก[ที่นี่](https://purchase.aspose.com/temporary-license/).
### Aspose.Finance สำหรับ .NET ให้การสนับสนุนการตรวจสอบ XBRL หรือไม่
ใช่ Aspose.Finance สำหรับ .NET ให้การสนับสนุนที่ครอบคลุมสำหรับการตรวจสอบ XBRL เพื่อให้มั่นใจว่าสอดคล้องกับมาตรฐานอุตสาหกรรม
### ฉันจะค้นหาแหล่งข้อมูลเพิ่มเติมและการสนับสนุนสำหรับ Aspose.Finance สำหรับ .NET ได้ที่ไหน
 ท่านสามารถเยี่ยมชมได้ที่[Aspose.Finance สำหรับฟอรัม .NET](https://forum.aspose.com/c/finance/43) สำหรับการสนับสนุนและการเข้าถึงเอกสาร[ที่นี่](https://reference.aspose.com/finance/net/).
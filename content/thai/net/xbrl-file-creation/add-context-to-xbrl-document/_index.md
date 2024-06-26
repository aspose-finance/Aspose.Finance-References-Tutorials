---
title: เพิ่มบริบทให้กับเอกสาร XBRL
linktitle: เพิ่มบริบทให้กับเอกสาร XBRL
second_title: Aspose.Finance .NET API
description: เรียนรู้วิธีเพิ่มบริบทให้กับเอกสาร XBRL ใน .NET โดยใช้ Aspose.Finance เพื่อการรายงานทางการเงินที่มีประสิทธิภาพยิ่งขึ้น #Aspose #การเงิน #XBRL
type: docs
weight: 11
url: /th/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## การแนะนำ
ในขอบเขตของการรายงานทางการเงิน XBRL (eXtensible Business Reporting Language) มีบทบาทสำคัญในการกำหนดมาตรฐานการแลกเปลี่ยนข้อมูลทางธุรกิจ การเพิ่มบริบทให้กับเอกสาร XBRL ถือเป็นสิ่งสำคัญในการรับรองความสมบูรณ์และความเกี่ยวข้องของข้อมูลที่มีอยู่ ด้วย Aspose.Finance สำหรับ .NET กระบวนการนี้จะมีความคล่องตัวและมีประสิทธิภาพ ช่วยให้นักพัฒนาสามารถรวมบริบทเข้ากับเอกสาร XBRL ของตนได้อย่างราบรื่น
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเข้าสู่บทช่วยสอน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:
1. Aspose.Finance สำหรับไลบรารี .NET: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Finance สำหรับ .NET จาก[เผยแพร่](https://releases.aspose.com/finance/net/).
2. สภาพแวดล้อมการพัฒนา .NET: ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าสภาพแวดล้อมการพัฒนา .NET ที่ใช้งานได้บนเครื่องของคุณ
3. ความเข้าใจพื้นฐานของ C#: ความคุ้นเคยกับภาษาการเขียนโปรแกรม C# จะเป็นประโยชน์ในการปฏิบัติตามตัวอย่าง
## นำเข้าเนมสเปซ
ในโปรเจ็กต์ C# ของคุณ ให้นำเข้าเนมสเปซที่จำเป็นเพื่อเข้าถึงฟังก์ชันการทำงานที่ Aspose.Finance สำหรับ .NET มอบให้:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเรกทอรีผลลัพธ์
ก่อนที่จะเพิ่มบริบทให้กับเอกสาร XBRL ให้ระบุไดเร็กทอรีเอาต์พุตที่จะบันทึกเอกสารที่แก้ไข:
```csharp
string outputDir = "Your Output Directory";
```
 แทนที่`"Your Output Directory"` ด้วยเส้นทางที่ต้องการในระบบของคุณ
## ขั้นตอนที่ 2: สร้างเอกสาร XBRL
 ยกตัวอย่าง`XbrlDocument` วัตถุที่จะทำงานกับเอกสาร XBRL:
```csharp
XbrlDocument document = new XbrlDocument();
```
วัตถุนี้แสดงถึงเอกสาร XBRL ที่จะถูกจัดการ
## ขั้นตอนที่ 3: เพิ่มอินสแตนซ์ XBRL
เพิ่มอินสแตนซ์ XBRL ให้กับเอกสาร แต่ละอินสแตนซ์ประกอบด้วยข้อมูลสำหรับระยะเวลาการรายงานเฉพาะ:
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
ขั้นตอนนี้จะเริ่มต้นอินสแตนซ์ XBRL ภายในเอกสาร
## ขั้นตอนที่ 4: กำหนดระยะเวลาบริบทและเอนทิตี
สร้างช่วงเวลาบริบทและเอนทิตีสำหรับอินสแตนซ์ XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
ระบุรายละเอียดรอบระยะเวลาและเอนทิตีตามความต้องการการรายงานของคุณ
## ขั้นตอนที่ 5: สร้างบริบท
สร้างบริบทโดยใช้รอบระยะเวลาและเอนทิตีที่กำหนดไว้ในขั้นตอนก่อนหน้า:
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
บริบทนี้สรุปข้อมูลชั่วคราวและที่เกี่ยวข้องกับเอนทิตี
## ขั้นตอนที่ 6: เพิ่มบริบทให้กับอินสแตนซ์ XBRL
เชื่อมโยงบริบทที่สร้างขึ้นในขั้นตอนก่อนหน้ากับอินสแตนซ์ XBRL:
```csharp
xbrlInstance.Contexts.Add(context);
```
ขั้นตอนนี้เชื่อมโยงบริบทกับอินสแตนซ์ XBRL โดยให้ข้อมูลบริบทที่เกี่ยวข้องกับข้อมูล
## ขั้นตอนที่ 7: บันทึกเอกสาร
บันทึกเอกสาร XBRL ที่แก้ไขไปยังไดเร็กทอรีเอาต์พุตที่ระบุ:
```csharp
document.Save(outputDir + @"document3.xbrl");
```
นี่เป็นการสิ้นสุดกระบวนการ โดยบันทึกเอกสาร XBRL พร้อมกับบริบทที่เพิ่มเข้ามา
## บทสรุป
ด้วยการทำตามขั้นตอนเหล่านี้ คุณจะสามารถเพิ่มบริบทให้กับเอกสาร XBRL ได้อย่างมีประสิทธิภาพโดยใช้ Aspose.Finance สำหรับ .NET สิ่งนี้ช่วยเพิ่มความชัดเจนและความสามารถในการใช้งานข้อมูลทางการเงิน อำนวยความสะดวกในการวิเคราะห์และการรายงานที่แม่นยำ
## คำถามที่พบบ่อย
### Aspose.Finance สำหรับ .NET สามารถจัดการเอกสาร XBRL ขนาดใหญ่ได้หรือไม่
Aspose.Finance สำหรับ .NET ได้รับการปรับให้เหมาะสมเพื่อจัดการเอกสาร XBRL ในขนาดที่แตกต่างกัน รวมถึงชุดข้อมูลขนาดใหญ่
### มีเวอร์ชันทดลองใช้สำหรับ Aspose.Finance สำหรับ .NET หรือไม่
ใช่ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีได้จากเว็บไซต์ทางการของ Aspose
### Aspose.Finance สำหรับ .NET รองรับมาตรฐานการรายงานทางการเงินอื่นๆ นอกเหนือจาก XBRL หรือไม่
Aspose.Finance มุ่งเน้นไปที่ฟังก์ชันที่เกี่ยวข้องกับ XBRL เป็นหลัก แต่ยังให้การสนับสนุนรูปแบบทางการเงินอื่นๆ ด้วย
### ฉันสามารถปรับแต่งข้อมูลบริบทตามความต้องการเฉพาะของฉันได้หรือไม่
แน่นอนว่า Aspose.Finance สำหรับ .NET มอบความยืดหยุ่นในการปรับแต่งข้อมูลบริบทให้เหมาะกับความต้องการของคุณ
### ฉันจะค้นหาการสนับสนุนหรือแหล่งข้อมูลเพิ่มเติมสำหรับ Aspose.Finance สำหรับ .NET ได้ที่ไหน
คุณสามารถไปที่ฟอรัม Aspose.Finance เพื่อขอความช่วยเหลือจากชุมชน หรือสำรวจเอกสารประกอบเพื่อดูคำแนะนำที่ครอบคลุม
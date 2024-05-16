---
title: เพิ่มการอ้างอิงบทบาทให้กับเอกสาร XBRL
linktitle: เพิ่มการอ้างอิงบทบาทให้กับเอกสาร XBRL
second_title: Aspose.Finance .NET API
description: เรียนรู้วิธีเพิ่มการอ้างอิงบทบาทให้กับเอกสาร XBRL โดยใช้ Aspose.Finance สำหรับ .NET ลดความซับซ้อนของการรายงานทางการเงินในแอปพลิเคชัน .NET ของคุณด้วยบทช่วยสอนนี้
type: docs
weight: 14
url: /th/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (eXtensible Business Reporting Language) ได้กลายเป็นมาตรฐานสำหรับการแลกเปลี่ยนข้อมูลทางธุรกิจ โดยเฉพาะอย่างยิ่งในการรายงานทางการเงิน Aspose.Finance สำหรับ .NET ช่วยให้การทำงานกับเอกสาร XBRL ในแอปพลิเคชัน .NET ง่ายขึ้น บทช่วยสอนนี้จะแนะนำคุณตลอดกระบวนการเพิ่มการอ้างอิงบทบาทให้กับเอกสาร XBRL โดยใช้ Aspose.Finance สำหรับ .NET
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:
### 1. ติดตั้ง Aspose.Finance สำหรับ .NET
ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Aspose.Finance สำหรับ .NET ในสภาพแวดล้อมการพัฒนาของคุณ หากยังไม่มี ให้ดาวน์โหลดจาก[เผยแพร่](https://releases.aspose.com/finance/net/) และปฏิบัติตามคำแนะนำในการติดตั้ง
### 2. ตั้งค่าสภาพแวดล้อมการพัฒนาของคุณ
ตรวจสอบให้แน่ใจว่าคุณมีสภาพแวดล้อมการพัฒนาที่ใช้งานได้สำหรับการพัฒนา .NET ซึ่งรวมถึง IDE ที่เข้ากันได้ เช่น Visual Studio และเฟรมเวิร์ก .NET ที่ติดตั้งบนระบบของคุณ
## นำเข้าเนมสเปซ
เริ่มต้นด้วยการนำเข้าเนมสเปซที่จำเป็นลงในแอปพลิเคชัน .NET ของคุณเพื่อเข้าถึงฟังก์ชันการทำงานที่ Aspose.Finance สำหรับ .NET มอบให้
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## ขั้นตอนที่ 4: ดึงข้อมูลประเภทบทบาทและเพิ่มการอ้างอิงบทบาท
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
ดึงข้อมูลประเภทบทบาทโดยใช้ URI และเพิ่มการอ้างอิงบทบาทไปยังอินสแตนซ์ XBRL
## ขั้นตอนที่ 5: บันทึกเอกสาร
```csharp
document.Save(outputDir + @"document7.xbrl");
```
บันทึกเอกสาร XBRL ไปยังไดเร็กทอรีเอาต์พุต
## บทสรุป
การเพิ่มการอ้างอิงบทบาทให้กับเอกสาร XBRL เป็นสิ่งสำคัญสำหรับการกำหนดบทบาทขององค์ประกอบต่างๆ ภายในเอกสาร Aspose.Finance สำหรับ .NET มอบวิธีที่ตรงไปตรงมาในการทำงานนี้ให้สำเร็จ โดยช่วยให้นักพัฒนาสามารถทำงานกับเอกสาร XBRL ในแอปพลิเคชัน .NET ของตนได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### ฉันสามารถใช้ Aspose.Finance สำหรับ .NET กับแอปพลิเคชัน .NET ใดๆ ได้หรือไม่
ใช่ Aspose.Finance สำหรับ .NET เข้ากันได้กับแอปพลิเคชัน .NET ใดๆ รวมถึงแอปพลิเคชัน ASP.NET, WinForms และคอนโซล
### Aspose.Finance สำหรับ .NET ใช้งานได้ฟรีหรือไม่
 Aspose.Finance สำหรับ .NET เป็นห้องสมุดเชิงพาณิชย์ คุณสามารถดาวน์โหลดเวอร์ชันทดลองใช้ฟรีเพื่อประเมินคุณลักษณะต่างๆ และสามารถซื้อใบอนุญาตได้จาก[ที่นี่](https://purchase.aspose.com/buy).
### Aspose.Finance สำหรับ .NET รองรับรูปแบบการรายงานทางการเงินอื่นๆ นอกเหนือจาก XBRL หรือไม่
Aspose.Finance สำหรับ .NET มุ่งเน้นไปที่ฟังก์ชันการทำงานที่เกี่ยวข้องกับ XBRL เป็นหลัก อย่างไรก็ตาม Aspose มีไลบรารีอื่นๆ สำหรับการทำงานกับรูปแบบทางการเงินที่แตกต่างกัน
### ฉันจะรับการสนับสนุนสำหรับ Aspose.Finance สำหรับ .NET ได้อย่างไร
 คุณสามารถรับการสนับสนุนสำหรับ Aspose.Finance สำหรับ .NET ผ่านทาง[ฟอรั่ม](https://forum.aspose.com/c/finance/43)ซึ่งคุณสามารถถามคำถามและโต้ตอบกับผู้ใช้รายอื่นและเจ้าหน้าที่ฝ่ายสนับสนุนได้
### ฉันสามารถขอรับใบอนุญาตชั่วคราวสำหรับ Aspose.Finance สำหรับ .NET ได้หรือไม่
 ใช่ สิทธิ์การใช้งานชั่วคราวสำหรับ Aspose.Finance สำหรับ .NET นั้นมีไว้เพื่อการทดสอบ คุณสามารถได้รับอย่างใดอย่างหนึ่ง[ที่นี่](https://purchase.aspose.com/temporary-license/).
---
title: สร้างไฟล์ตอบกลับธุรกรรมธนาคาร OFX
linktitle: สร้างไฟล์ตอบกลับธุรกรรมธนาคาร OFX
second_title: Aspose.Finance .NET API
description: เรียนรู้วิธีสร้างไฟล์ตอบกลับธุรกรรมธนาคาร OFX ได้อย่างง่ายดายโดยใช้ Aspose.Finance สำหรับ .NET ปรับปรุงการแลกเปลี่ยนข้อมูลทางการเงินวันนี้!
type: docs
weight: 13
url: /th/net/ofx-file-manipulation/create-ofx-bank-transaction-response-file/
---
## การแนะนำ
ในขอบเขตของการประมวลผลข้อมูลทางการเงิน การสร้างไฟล์ตอบกลับธุรกรรมธนาคาร OFX (Open Financial Exchange) ถือเป็นงานที่สำคัญ ไฟล์เหล่านี้สรุปข้อมูลธุรกรรมในรูปแบบมาตรฐาน อำนวยความสะดวกในการแลกเปลี่ยนระหว่างสถาบันการเงินและระบบซอฟต์แวร์ได้อย่างราบรื่น Aspose.Finance สำหรับ .NET นำเสนอโซลูชันที่มีประสิทธิภาพสำหรับการสร้างไฟล์ตอบกลับธุรกรรมธนาคาร OFX ภายในเฟรมเวิร์ก .NET ได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่จะเจาะลึกการสร้างไฟล์ตอบกลับธุรกรรมธนาคาร OFX โดยใช้ Aspose.Finance สำหรับ .NET ตรวจสอบให้แน่ใจว่าเป็นไปตามข้อกำหนดเบื้องต้นต่อไปนี้:
### 1. รับ Aspose.Finance สำหรับ .NET
 ขั้นแรก ดาวน์โหลดและติดตั้ง Aspose.Finance สำหรับ .NET จากทางการ[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/finance/net/).
### 2. ตั้งค่าสภาพแวดล้อมการพัฒนา
ตรวจสอบให้แน่ใจว่าได้กำหนดค่าสภาพแวดล้อมการพัฒนาที่เหมาะสม รวมถึง Visual Studio เวอร์ชันที่เข้ากันได้และเฟรมเวิร์ก .NET
### 3. ความคุ้นเคยขั้นพื้นฐานกับ C#
ความเข้าใจพื้นฐานเกี่ยวกับภาษาการเขียนโปรแกรม C# ถือเป็นสิ่งสำคัญในการเข้าใจแนวคิดที่กล่าวถึงในบทช่วยสอนนี้
## นำเข้าเนมสเปซ
หากต้องการเริ่มสร้างไฟล์ตอบกลับธุรกรรมธนาคาร OFX ด้วย Aspose.Finance สำหรับ .NET ให้นำเข้าเนมสเปซที่จำเป็น:
## 1. นำเข้าเนมสเปซ Aspose.Finance
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
ตอนนี้ เราจะแบ่งตัวอย่างที่ให้ไว้ออกเป็นหลายขั้นตอนเพื่อแนะนำคุณตลอดกระบวนการสร้างไฟล์ตอบกลับธุรกรรมธนาคาร OFX โดยใช้ Aspose.Finance สำหรับ .NET
## ขั้นตอนที่ 1: กำหนดไดเรกทอรีผลลัพธ์
```csharp
string outputDir = "Your Output Directory";
```
ระบุเส้นทางไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ตอบกลับธุรกรรมธนาคาร OFX ที่สร้างขึ้น
## ขั้นตอนที่ 2: เริ่มต้นเอกสารตอบกลับ OFX
```csharp
OfxResponseDocument document = new OfxResponseDocument();
```
 สร้างอินสแตนซ์ใหม่ของ`OfxResponseDocument` คลาสเพื่อเริ่มสร้างเอกสารตอบกลับ OFX
## ขั้นตอนที่ 3: ตั้งค่าการตอบสนอง Signon
```csharp
document.SignonResponseMessageSetV1 = new SignonResponseMessageSetV1();
```
 ยกตัวอย่าง`SignonResponseMessageSetV1` คลาสเพื่อจัดการการตอบสนองการลงชื่อเข้าใช้ภายในเอกสาร OFX
## ขั้นตอนที่ 4: ตั้งค่ารายละเอียดการตอบกลับ Signon
```csharp
SignonResponse signonResponse = new SignonResponse();
```
 สร้างใหม่`SignonResponse` วัตถุเพื่อสรุปรายละเอียดการตอบกลับการลงชื่อเข้าใช้
## ขั้นตอนที่ 5: ตั้งค่าสถานะการตอบกลับ Signon
```csharp
signonResponse.Status = new Status();
signonResponse.Status.Code = "0";
signonResponse.Status.Severity = SeverityEnum.INFO;
signonResponse.Status.Message = "SUCCESS";
```
กำหนดค่าสถานะของการตอบสนองการลงชื่อเข้าใช้ โดยระบุรหัส ความเข้มงวด และข้อความ
## ขั้นตอนที่ 6: กำหนดรายละเอียดสถาบันการเงิน
```csharp
FinancialInstitution fi = new FinancialInstitution();
fi.Organization = "aspose";
fi.FinancialInstitutionId = "1";
```
ให้ข้อมูลเกี่ยวกับสถาบันการเงินที่เกี่ยวข้องกับการทำธุรกรรม
## ขั้นตอนที่ 7: ตั้งค่าคุกกี้เซสชัน
```csharp
signonResponse.SessionCookie = "11111111111111111";
```
กำหนดคุกกี้เซสชันเพื่อวัตถุประสงค์ในการตรวจสอบสิทธิ์
## ขั้นตอนที่ 8: เพิ่มชุดข้อความตอบกลับจากธนาคาร
```csharp
document.BankResponseMessageSetV1 = new BankResponseMessageSetV1();
```
 ยกตัวอย่าง`BankResponseMessageSetV1` คลาสเพื่อจัดการข้อความตอบกลับของธนาคาร
## ขั้นตอนที่ 9: เพิ่มการตอบสนองต่อธุรกรรมใบแจ้งยอด
```csharp
StatementTransactionResponse stmtTransResponse = new StatementTransactionResponse();
document.BankResponseMessageSetV1.StatementTransactionResponses.Add(stmtTransResponse);
```
สร้างออบเจ็กต์การตอบกลับธุรกรรมใบแจ้งยอด และเพิ่มลงในชุดข้อความตอบกลับของธนาคาร
## ขั้นตอนที่ 10: ตั้งค่ารายละเอียดธุรกรรม
```csharp
stmtTransResponse.TransactionUniqueId = "829631324";
stmtTransResponse.Status = new Status();
stmtTransResponse.Status.Code = "0";
stmtTransResponse.Status.Severity = SeverityEnum.INFO;
```
กำหนดค่ารายละเอียดเฉพาะธุรกรรม เช่น ตัวระบุและสถานะที่ไม่ซ้ำกัน
## ขั้นตอนที่ 11: เพิ่มข้อมูลบัญชีธนาคาร
```csharp
stmtTransResponse.StatementResponse.BankAccountFrom = new BankAccount();
stmtTransResponse.StatementResponse.BankAccountFrom.BankId = "1111111";
stmtTransResponse.StatementResponse.BankAccountFrom.AccountId = "1111111111111";
stmtTransResponse.StatementResponse.BankAccountFrom.AccountType = AccountEnum.CHECKING;
```
ระบุรายละเอียดเกี่ยวกับบัญชีธนาคารที่เกี่ยวข้องกับธุรกรรม
## ขั้นตอนที่ 12: เพิ่มรายการธุรกรรมของธนาคาร
```csharp
stmtTransResponse.StatementResponse.BankTransactionList = new BankTransactionList();
stmtTransResponse.StatementResponse.BankTransactionList.StartDate = "20200601000000";
stmtTransResponse.StatementResponse.BankTransactionList.EndDate = "20200611000000";
```
สร้างรายการธุรกรรมธนาคารและระบุวันที่เริ่มต้นและสิ้นสุดสำหรับธุรกรรม
## ขั้นตอนที่ 13: เพิ่มธุรกรรมใบแจ้งยอด
```csharp
StatementTransaction transaction1 = new StatementTransaction();
//รายละเอียดธุรกรรมสำหรับธุรกรรม1
StatementTransaction transaction2 = new StatementTransaction();
// รายละเอียดธุรกรรมสำหรับธุรกรรม2
stmtTransResponse.StatementResponse.BankTransactionList.StatementTransactions.Add(transaction1);
stmtTransResponse.StatementResponse.BankTransactionList.StatementTransactions.Add(transaction2);
```
สร้างอินสแตนซ์ธุรกรรมใบแจ้งยอด เติมรายละเอียด และเพิ่มลงในรายการธุรกรรมของธนาคาร
## ขั้นตอนที่ 14: ตั้งค่าบัญชีแยกประเภทและยอดคงเหลือที่มีอยู่
```csharp
stmtTransResponse.StatementResponse.LedgerBalance = new LedgerBalance();
stmtTransResponse.StatementResponse.LedgerBalance.BalanceAmount = "+2222.42";
stmtTransResponse.StatementResponse.LedgerBalance.DateAsOf = "20200611000000";
stmtTransResponse.StatementResponse.AvailableBalance = new AvailableBalance();
stmtTransResponse.StatementResponse.AvailableBalance.BalanceAmount = "+222222.42";
stmtTransResponse.StatementResponse.AvailableBalance.DateAsOf = "20200611000000";
```
ระบุยอดดุลบัญชีแยกประเภทและยอดคงเหลือที่เกี่ยวข้องกับบัญชีธนาคาร
## ขั้นตอนที่ 15: บันทึกไฟล์ตอบกลับ OFX
```csharp
document.Save(outputDir + @"newOfxResponseBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxResponseBankStatement.sgml", OfxVersionEnum.V1x);
```
บันทึกไฟล์ตอบกลับ OFX ที่สร้างขึ้นในรูปแบบ XML และ SGML ตามลำดับ
## บทสรุป
การสร้างไฟล์ตอบกลับธุรกรรมธนาคาร OFX โดยใช้ Aspose.Finance สำหรับ .NET ช่วยให้นักพัฒนามีแนวทางที่มีประสิทธิภาพในการจัดการการแลกเปลี่ยนข้อมูลทางการเงิน ด้วยการทำตามคำแนะนำทีละขั้นตอนที่สรุปไว้ในบทความนี้ คุณสามารถสร้างไฟล์ OFX ที่ปรับให้เหมาะกับความต้องการของแอปพลิเคชันของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### 1. ฉันสามารถรวม Aspose.Finance สำหรับ .NET เข้ากับซอฟต์แวร์ทางการเงินอื่นๆ ได้หรือไม่
ใช่ Aspose.Finance สำหรับ .NET นำเสนอความสามารถในการบูรณาการอย่างราบรื่นกับโซลูชันซอฟต์แวร์ทางการเงินต่างๆ เพื่อให้มั่นใจถึงความเข้ากันได้และความสามารถในการทำงานร่วมกัน
### 2. Aspose.Finance สำหรับ .NET เหมาะสำหรับการใช้งานส่วนบุคคลและองค์กรหรือไม่
อย่างแน่นอน! ไม่ว่าคุณจะเป็นนักพัฒนารายบุคคลหรือเป็นส่วนหนึ่งขององค์กรขนาดใหญ่ Aspose.Finance สำหรับ .NET ตอบสนองความต้องการของผู้ใช้ที่หลากหลายด้วยคุณสมบัติที่ยืดหยุ่นและตัวเลือกการออกใบอนุญาต
### 3. มีข้อจำกัดเกี่ยวกับจำนวนธุรกรรมที่สามารถจัดการโดยใช้ Aspose.Finance สำหรับ .NET หรือไม่
ไม่ Aspose.Finance สำหรับ .NET ได้รับการออกแบบมาเพื่อจัดการธุรกรรมปริมาณมากได้อย่างมีประสิทธิภาพ โดยไม่มีข้อจำกัดใดๆ ไม่ว่าคุณจะประมวลผลธุรกรรมบางรายการหรือจัดการข้อมูลทางการเงินที่กว้างขวาง ไลบรารีจะรับประกันประสิทธิภาพและความสามารถในการปรับขนาดที่เหมาะสมที่สุด
### 4. ฉันสามารถปรับแต่งรูปแบบและโครงสร้างของไฟล์ OFX ที่สร้างโดย Aspose.Finance สำหรับ .NET ได้หรือไม่
แน่นอน! Aspose.Finance สำหรับ .NET มีตัวเลือกการปรับแต่งที่ครอบคลุม ซึ่งช่วยให้คุณปรับแต่งรูปแบบ โครงสร้าง และเนื้อหาของไฟล์ OFX ตามความต้องการเฉพาะของคุณ คุณสามารถปรับพารามิเตอร์ต่างๆ ได้อย่างง่ายดายเพื่อให้ตรงตามมาตรฐานและความต้องการของแอปพลิเคชันหรือองค์กรของคุณ
### 5. มีการสนับสนุนด้านเทคนิคสำหรับ Aspose.Finance สำหรับ .NET หรือไม่
 ใช่ มีการสนับสนุนด้านเทคนิคที่ครอบคลุมสำหรับ Aspose.Finance สำหรับผู้ใช้ .NET คุณสามารถเข้าถึง[ฟอรั่ม](https://forum.aspose.com/c/finance/43) เพื่อขอความช่วยเหลือ รายงานปัญหา หรือมีส่วนร่วมกับชุมชนนักพัฒนาและผู้เชี่ยวชาญที่มีชีวิตชีวา
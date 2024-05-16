---
title: สร้างไฟล์คำขอธุรกรรมธนาคาร OFX
linktitle: สร้างไฟล์คำขอธุรกรรมธนาคาร OFX
second_title: Aspose.Finance .NET API
description: เรียนรู้วิธีสร้างไฟล์คำขอธุรกรรมธนาคาร OFX โดยใช้ Aspose.Finance สำหรับ .NET พร้อมคำแนะนำโดยละเอียดทีละขั้นตอนของเรา #จัดสรร #การเงิน
type: docs
weight: 12
url: /th/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
การสร้างไฟล์คำขอธุรกรรมธนาคาร OFX อาจดูยุ่งยาก แต่ด้วยเครื่องมือและคำแนะนำที่เหมาะสม อาจเป็นกระบวนการที่ไม่ซับซ้อน ในบทช่วยสอนนี้ เราจะอธิบายแต่ละขั้นตอนในการสร้างไฟล์คำขอธุรกรรมธนาคาร OFX โดยใช้ Aspose.Finance สำหรับ .NET เราจะครอบคลุมข้อกำหนดเบื้องต้น เนมสเปซที่จำเป็น และให้คำแนะนำโดยละเอียดทีละขั้นตอนเพื่อให้แน่ใจว่าคุณสามารถปฏิบัติตามได้อย่างง่ายดาย
## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเจาะลึกบทช่วยสอน มีบางสิ่งที่คุณต้องเตรียม:
1.  Visual Studio: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Visual Studio บนคอมพิวเตอร์ของคุณ คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์อย่างเป็นทางการ](https://visualstudio.microsoft.com/).
2.  Aspose.Finance สำหรับ .NET: คุณต้องมีไลบรารี Aspose.Finance สำหรับ .NET คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/finance/net/).
3. ความรู้พื้นฐาน C#: การทำความเข้าใจพื้นฐานของการเขียนโปรแกรม C# จะช่วยให้คุณปฏิบัติตามตัวอย่างโค้ดได้
เมื่อคุณมีข้อกำหนดเบื้องต้นเหล่านี้แล้ว คุณก็พร้อมที่จะเริ่มต้น!
## นำเข้าเนมสเปซ
ขั้นแรก เรามานำเข้าเนมสเปซที่จำเป็นกันก่อน เนมสเปซเหล่านี้มีความสำคัญอย่างยิ่งในการเข้าถึงคลาสและวิธีการที่จำเป็นในการสร้างไฟล์คำขอธุรกรรมธนาคาร OFX
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## ขั้นตอนที่ 1: ตั้งค่าไดเร็กทอรีการทำงาน
ก่อนที่เราจะเริ่มสร้างไฟล์คำขอ OFX เราจำเป็นต้องระบุไดเร็กทอรีเอาต์พุตที่จะบันทึกไฟล์
```csharp
string outputDir = "Your Output Directory";
```
 แทนที่`"Your Output Directory"` พร้อมพาธไปยังไดเร็กทอรีที่คุณต้องการบันทึกไฟล์ที่สร้างขึ้น
## ขั้นตอนที่ 2: สร้างเอกสารคำขอ OFX
 ต่อไปเราต้องสร้างอินสแตนซ์ของ`OfxRequestDocument` ระดับ. คลาสนี้จะทำหน้าที่เป็นคอนเทนเนอร์สำหรับคำขอ OFX ของเรา
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## ขั้นตอนที่ 3: ตั้งค่าคำขอการลงชื่อเข้าใช้
คำขอลงชื่อเข้าใช้เป็นสิ่งจำเป็นสำหรับการตรวจสอบสิทธิ์ผู้ใช้และการเริ่มต้นเซสชัน OFX เราจะตั้งค่าข้อความคำขอการลงชื่อเข้าใช้และเติมรายละเอียดที่จำเป็น เช่น วันที่ลูกค้า ID ผู้ใช้ รหัสผ่าน และข้อมูลสถาบันการเงิน
```csharp
document.SignonRequestMessageSetV1 = new SignonRequestMessageSetV1();
SignonRequest signonRequest = new SignonRequest();
document.SignonRequestMessageSetV1.SignonRequest = signonRequest;
signonRequest.ClientDate = "20200611000000";
signonRequest.UserId = "aspose";
signonRequest.UserPassword = "password";
FinancialInstitution fi = new FinancialInstitution();
fi.Organization = "aspose";
fi.FinancialInstitutionId = "1";
signonRequest.FinancialInstitution = fi;
signonRequest.AppVersion = "1.0";
signonRequest.AppId = "Aspose.Finance";
signonRequest.ClientUserId = "aaaaaaa";
```
## ขั้นตอนที่ 4: ตั้งค่าข้อความคำขอของธนาคาร
เมื่อตั้งค่าคำขอลงชื่อเข้าใช้แล้ว เราจะไปยังการสร้างข้อความคำขอจากธนาคาร ข้อความนี้จะมีรายละเอียดของบัญชีธนาคารและคำขอใบแจ้งยอดธุรกรรม
```csharp
document.BankRequestMessageSetV1 = new BankRequestMessageSetV1();
StatementTransactionRequest stmtTransRequest = new StatementTransactionRequest();
document.BankRequestMessageSetV1.StatementTransactionRequests.Add(stmtTransRequest);
stmtTransRequest.TransactionUniqueId = "1111111";
stmtTransRequest.StatementRequest = new StatementRequest();
stmtTransRequest.StatementRequest.BankAccountFrom = new BankAccount();
stmtTransRequest.StatementRequest.BankAccountFrom.BankId = "sssss";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountId = "sfsdfsfsdf";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountType = AccountEnum.CHECKING;
```
## ขั้นตอนที่ 5: รวมรายละเอียดธุรกรรม
 ในการเรียกข้อมูลธุรกรรมที่เฉพาะเจาะจง เราจำเป็นต้องระบุช่วงวันที่และจะรวมธุรกรรมไว้ในคำขอหรือไม่ นี้จะกระทำโดยการตั้งค่า`IncTransaction` วัตถุ.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## ขั้นตอนที่ 6: บันทึกเอกสารคำขอ OFX
สุดท้ายนี้ เราจะบันทึกเอกสารคำขอ OFX ในรูปแบบ XML และ SGML สิ่งนี้ทำให้มั่นใจได้ถึงความเข้ากันได้กับระบบต่าง ๆ ที่อาจใช้รูปแบบใดรูปแบบหนึ่ง
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## ขั้นตอนที่ 7: ยืนยันการดำเนินการที่สำเร็จ
เพื่อยืนยันว่ากระบวนการดำเนินการสำเร็จ เราสามารถพิมพ์ข้อความไปยังคอนโซลได้
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## บทสรุป
การสร้างไฟล์คำขอธุรกรรมธนาคาร OFX โดยใช้ Aspose.Finance สำหรับ .NET เป็นกระบวนการที่มีระเบียบวิธีที่เกี่ยวข้องกับการตั้งค่าเอกสารคำขอ การกำหนดค่าข้อความการลงชื่อเข้าใช้และคำขอจากธนาคาร การระบุรายละเอียดธุรกรรม และการบันทึกเอกสาร ด้วยการทำตามคำแนะนำทีละขั้นตอนนี้ คุณสามารถสร้างไฟล์คำขอ OFX ที่ปรับให้เหมาะกับความต้องการเฉพาะของคุณได้อย่างมีประสิทธิภาพ
## คำถามที่พบบ่อย
### 1. ไฟล์ OFX คืออะไร
ไฟล์ OFX (Open Financial Exchange) เป็นรูปแบบมาตรฐานที่ใช้ในการแลกเปลี่ยนข้อมูลทางการเงินระหว่างสถาบันและผู้ใช้ มีการใช้กันอย่างแพร่หลายสำหรับใบแจ้งยอดธนาคาร ธุรกรรม และกิจกรรมทางการเงินอื่นๆ
### 2. ฉันสามารถใช้ Aspose.Finance สำหรับ .NET กับภาษาการเขียนโปรแกรมอื่นๆ ได้หรือไม่
Aspose.Finance สำหรับ .NET ได้รับการออกแบบมาเป็นพิเศษเพื่อใช้กับภาษา .NET เช่น C# อย่างไรก็ตาม คุณสามารถใช้ในสภาพแวดล้อมที่รองรับ .NET ได้
### 3. Aspose.Finance สำหรับ .NET มีรุ่นทดลองใช้ฟรีหรือไม่
ใช่ คุณสามารถดาวน์โหลด Aspose.Finance สำหรับ .NET รุ่นทดลองใช้ฟรีได้จาก[ที่นี่](https://releases.aspose.com/).
### 4. ฉันจะรับการสนับสนุนสำหรับ Aspose.Finance สำหรับ .NET ได้อย่างไร
 คุณสามารถรับการสนับสนุนจากชุมชน Aspose และทีมงานด้านเทคนิคผ่านทางพวกเขา[ฟอรั่มการสนับสนุน](https://forum.aspose.com/c/finance/43).
### 5. ฉันสามารถรับใบอนุญาตชั่วคราวสำหรับ Aspose.Finance สำหรับ .NET ได้หรือไม่
 ใช่ Aspose เสนอ[ใบอนุญาตชั่วคราว](https://purchase.aspose.com/temporary-license/) ที่คุณสามารถใช้เพื่อประเมินผลิตภัณฑ์ได้
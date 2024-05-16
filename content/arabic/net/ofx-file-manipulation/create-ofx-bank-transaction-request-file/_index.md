---
title: إنشاء ملف طلب معاملة بنك OFX
linktitle: إنشاء ملف طلب معاملة بنك OFX
second_title: Aspose.Finance .NET API
description: تعرف على كيفية إنشاء ملف طلب معاملة بنك OFX باستخدام Aspose.Finance لـ .NET من خلال دليلنا التفصيلي خطوة بخطوة. #التمويل
type: docs
weight: 12
url: /ar/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
قد يبدو إنشاء ملف طلب معاملة بنك OFX أمرًا شاقًا، ولكن باستخدام الأدوات والإرشادات المناسبة، يمكن أن تكون عملية واضحة. في هذا البرنامج التعليمي، سنرشدك خلال كل خطوة لإنشاء ملف طلب معاملة بنك OFX باستخدام Aspose.Finance for .NET. سنغطي المتطلبات الأساسية ومساحات الأسماء الضرورية ونقدم دليلاً تفصيليًا خطوة بخطوة لضمان إمكانية المتابعة بسهولة.
## المتطلبات الأساسية
قبل أن نتعمق في البرنامج التعليمي، هناك بعض الأشياء التي ستحتاج إلى توفرها:
1.  Visual Studio: تأكد من تثبيت Visual Studio على جهاز الكمبيوتر الخاص بك. يمكنك تنزيله من[الموقع الرسمي](https://visualstudio.microsoft.com/).
2.  Aspose.Finance لـ .NET: أنت بحاجة إلى مكتبة Aspose.Finance لـ .NET. يمكنك تنزيله من[هنا](https://releases.aspose.com/finance/net/).
3. المعرفة الأساسية لـ C#: سيساعدك فهم أساسيات برمجة C# على متابعة أمثلة التعليمات البرمجية.
بمجرد توفر هذه المتطلبات الأساسية، تصبح جاهزًا للبدء!
## استيراد مساحات الأسماء
أولاً، لنستورد مساحات الأسماء الضرورية. تعد مساحات الأسماء هذه ضرورية للوصول إلى الفئات والأساليب المطلوبة لإنشاء ملف طلب المعاملات البنكية لـ OFX.
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## الخطوة 1: إعداد دليل العمل
قبل أن نبدأ في إنشاء ملف طلب OFX، نحتاج إلى تحديد دليل الإخراج حيث سيتم حفظ الملف.
```csharp
string outputDir = "Your Output Directory";
```
 يستبدل`"Your Output Directory"` مع المسار إلى الدليل الذي تريد حفظ الملف الذي تم إنشاؤه فيه.
## الخطوة 2: إنشاء مستند طلب OFX
 بعد ذلك، نحتاج إلى إنشاء مثيل لـ`OfxRequestDocument` فصل. سيكون هذا الفصل بمثابة حاوية لطلب OFX الخاص بنا.
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## الخطوة 3: إعداد طلب تسجيل الدخول
يعد طلب تسجيل الدخول ضروريًا لمصادقة المستخدم وبدء جلسة OFX. سنقوم بإعداد رسالة طلب تسجيل الدخول وملئها بالتفاصيل الضرورية مثل تاريخ العميل ومعرف المستخدم وكلمة المرور ومعلومات المؤسسة المالية.
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
## الخطوة 4: إعداد رسالة طلب البنك
الآن بعد أن تم إعداد طلب تسجيل الدخول، سننتقل إلى إنشاء رسالة طلب البنك. ستحتوي هذه الرسالة على تفاصيل الحساب البنكي وطلب كشف حساب المعاملة.
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
## الخطوة 5: تضمين تفاصيل المعاملة
 لاسترداد معاملات محددة، نحتاج إلى تحديد النطاق الزمني وما إذا كان سيتم تضمين المعاملات في الطلب. ويتم ذلك عن طريق إعداد`IncTransaction` هدف.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## الخطوة 6: احفظ مستند طلب OFX
وأخيرًا، سنقوم بحفظ مستند طلب OFX بتنسيقي XML وSGML. وهذا يضمن التوافق مع الأنظمة المختلفة التي قد تستخدم أيًا من التنسيقين.
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## الخطوة 7: تأكيد التنفيذ الناجح
للتأكد من تنفيذ العملية بنجاح، يمكننا طباعة رسالة إلى وحدة التحكم.
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## خاتمة
يعد إنشاء ملف طلب معاملة بنك OFX باستخدام Aspose.Finance لـ .NET عملية منهجية تتضمن إعداد مستند طلب وتكوين رسائل تسجيل الدخول والطلب البنكي وتحديد تفاصيل المعاملة وحفظ المستند. باتباع هذا الدليل التفصيلي، يمكنك إنشاء ملفات طلب OFX بكفاءة مصممة خصيصًا لتلبية احتياجاتك الخاصة.
## الأسئلة الشائعة
### 1. ما هو ملف OFX؟
يعد ملف OFX (التبادل المالي المفتوح) تنسيقًا قياسيًا يستخدم لتبادل البيانات المالية بين المؤسسات والمستخدمين. يتم استخدامه على نطاق واسع للبيانات المصرفية والمعاملات والأنشطة المالية الأخرى.
### 2. هل يمكنني استخدام Aspose.Finance لـ .NET مع لغات البرمجة الأخرى؟
تم تصميم Aspose.Finance for .NET خصيصًا للاستخدام مع لغات .NET مثل C#. ومع ذلك، يمكنك استخدامه في أي بيئة تدعم .NET.
### 3. هل تتوفر نسخة تجريبية مجانية من Aspose.Finance لـ .NET؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من Aspose.Finance لـ .NET من[هنا](https://releases.aspose.com/).
### 4. كيف يمكنني الحصول على دعم Aspose.Finance لـ .NET؟
 يمكنك الحصول على الدعم من مجتمع Aspose والفريق الفني من خلال موقعهم[منتدى الدعم](https://forum.aspose.com/c/finance/43).
### 5. هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.Finance لـ .NET؟
 نعم، يقدم Aspose أ[ترخيص مؤقت](https://purchase.aspose.com/temporary-license/) التي يمكنك استخدامها لتقييم المنتج.
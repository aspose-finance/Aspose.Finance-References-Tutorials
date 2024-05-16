---
title: أضف رابط الحاشية السفلية إلى مستند XBRL
linktitle: أضف رابط الحاشية السفلية إلى مستند XBRL
second_title: Aspose.Finance .NET API
description: تعرف على كيفية إضافة روابط الحواشي السفلية إلى مستندات XBRL باستخدام Aspose.Finance لـ .NET. تعزيز التقارير المالية بسياق إضافي دون عناء.
type: docs
weight: 12
url: /ar/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
تعد إضافة رابط حاشية سفلية إلى مستند XBRL أمرًا ضروريًا لتوفير سياق أو تفسيرات إضافية لنقاط بيانات محددة. في هذا البرنامج التعليمي، سنتعرف على العملية خطوة بخطوة باستخدام Aspose.Finance for .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
1.  Aspose.Finance لـ .NET: تأكد من تثبيت Aspose.Finance لـ .NET على نظامك. يمكنك تنزيله من[هنا](https://releases.aspose.com/finance/net/).
  
2. بيئة التطوير: قم بإعداد بيئة تطوير باستخدام .NET Framework أو .NET Core.
## استيراد مساحات الأسماء:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## الخطوة 1: تعيين أدلة المصدر والإخراج
أولاً، حدد المجلدات الخاصة بالملفات المصدرية والمخرجات:
```csharp
// دليل المصدر
string sourceDir = "Your Source Directory";
// دليل الإخراج
string outputDir = "Your Output Directory";
```
## الخطوة 2: إنشاء مستند ومثيل XBRL
تهيئة مستند XBRL ومثيله:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## الخطوة 3: إضافة مراجع المخطط
أضف مراجع المخطط إلى مثيل XBRL:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## الخطوة 4: تحديد السياق
تحديد سياق مثيل XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## الخطوة 5: إضافة رابط الحاشية السفلية
قم بإنشاء وإضافة رابط حاشية سفلية إلى مثيل XBRL:
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
## الخطوة 6: احفظ المستند
احفظ مستند XBRL المعدل:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## خاتمة
تعد إضافة رابط حاشية سفلية إلى مستند XBRL عملية مباشرة مع Aspose.Finance for .NET. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك دمج سياق أو تفسيرات إضافية بسلاسة في تقاريرك المالية.
## الأسئلة الشائعة
### هل يمكنني إضافة روابط حواشي سفلية متعددة إلى مستند XBRL واحد؟
نعم، يمكنك إضافة روابط حواشي سفلية متعددة عن طريق تكرار الخطوات الموضحة في هذا البرنامج التعليمي لكل رابط إضافي.
### هل يتوافق Aspose.Finance for .NET مع كل من .NET Framework و.NET Core؟
نعم، يدعم Aspose.Finance for .NET كلاً من بيئات .NET Framework و.NET Core.
### كيف يمكنني الحصول على ترخيص مؤقت لـ Aspose.Finance لـ .NET؟
 يمكنك الحصول على ترخيص مؤقت من[هنا](https://purchase.aspose.com/temporary-license/).
### هل يوفر Aspose.Finance for .NET الدعم للتحقق من صحة XBRL؟
نعم، يقدم Aspose.Finance for .NET دعمًا شاملاً للتحقق من صحة XBRL لضمان الامتثال لمعايير الصناعة.
### أين يمكنني العثور على موارد ودعم إضافيين لـ Aspose.Finance لـ .NET؟
 يمكنك زيارة[Aspose.Finance لمنتدى .NET](https://forum.aspose.com/c/finance/43) للحصول على الدعم والوصول إلى الوثائق[هنا](https://reference.aspose.com/finance/net/).
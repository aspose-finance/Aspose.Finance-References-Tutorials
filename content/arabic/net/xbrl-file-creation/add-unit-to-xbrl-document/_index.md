---
title: إضافة وحدة إلى وثيقة XBRL
linktitle: إضافة وحدة إلى وثيقة XBRL
second_title: Aspose.Finance .NET API
description: تعرف على كيفية إضافة وحدات إلى مستندات XBRL بسهولة باستخدام Aspose.Finance for .NET. تعزيز قدرات معالجة البيانات المالية الخاصة بك اليوم!
type: docs
weight: 16
url: /ar/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
مرحبًا بك في عالم Aspose.Finance for .NET - بوابتك إلى المعالجة الفعالة للمستندات المالية ضمن تطبيقات .NET. سواء كنت تقوم بإنشاء برامج محاسبة أو أدوات تحليل مالي أو أي تطبيق مالي آخر، فإن Aspose.Finance for .NET يزودك بمجموعة شاملة من الميزات لتبسيط عملية التطوير الخاصة بك.
## المتطلبات الأساسية
قبل أن نتعمق في الاستفادة من قوة Aspose.Finance لـ .NET، دعونا نتأكد من أن لدينا المتطلبات الأساسية اللازمة:
### 1. تثبيت الاستوديو المرئي
تأكد من تثبيت Visual Studio على نظامك. إذا لم يكن الأمر كذلك، فيمكنك تنزيله وتثبيته من موقع Microsoft الرسمي.
### 2. الحصول على الترخيص
 لفتح الإمكانات الكاملة لـ Aspose.Finance لـ .NET، تحتاج إلى ترخيص صالح. يمكنك شراء ترخيص من[هنا](https://purchase.aspose.com/buy) أو اختر ترخيصًا مؤقتًا لأغراض الاختبار.
### 3. قم بتنزيل Aspose.Finance والمراجع الخاصة بـ .NET
 قم بتنزيل مكتبة Aspose.Finance for .NET من[صفحة الإصدارات](https://releases.aspose.com/finance/net/) وقم بالإشارة إليه في مشروع .NET الخاص بك.
### 4. الوصول إلى الوثائق والدعم
 الرجوع إلى[توثيق](https://reference.aspose.com/finance/net/)للحصول على معلومات مفصلة حول استخدام Aspose.Finance لـ .NET. بالإضافة إلى ذلك، يمكنك طلب المساعدة من مجتمع Aspose.Finance على الموقع[منتدى الدعم](https://forum.aspose.com/c/finance/43).
## استيراد مساحات الأسماء
الآن، لنستورد مساحات الأسماء الضرورية إلى مشروع .NET الخاص بك:
## الخطوة 1: إضافة مساحة الاسم Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
تحتوي مساحة الاسم هذه على فئات وطرق أساسية للعمل مع مستندات وبيانات XBRL.
دعنا نقسم المثال المقدم إلى خطوات متعددة لفهم كيفية إضافة وحدة إلى مستند XBRL باستخدام Aspose.Finance for .NET.
## الخطوة 1: تحديد دليل الإخراج
```csharp
// دليل الإخراج
string outputDir = "Your Output Directory";
```
 يستبدل`"Your Output Directory"` بالمسار الفعلي إلى دليل الإخراج المطلوب.
## الخطوة 2: إنشاء مستند XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
يؤدي هذا إلى تهيئة مثيل جديد لمستند XBRL.
## الخطوة 3: الوصول إلى مثيلات XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
يؤدي ذلك إلى استرداد مجموعة مثيلات XBRL من المستند وإضافة مثيل جديد إليها.
## الخطوة 4: إضافة الوحدة
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"))؛
xbrlInstance.Units.Add(unit);
```
يؤدي هذا إلى إنشاء وحدة قياس جديدة (في هذه الحالة، الدولار الأمريكي) وإضافتها إلى مثيل XBRL. يمكنك ضبط رمز العملة ومساحة الاسم URI حسب الحاجة.
## الخطوة 5: احفظ المستند
```csharp
document.Save(outputDir + @"document4.xbrl");
```
يؤدي هذا إلى حفظ مستند XBRL المعدل في دليل الإخراج المحدد.
## خاتمة
في الختام، يعمل Aspose.Finance for .NET على تمكين المطورين من معالجة المستندات والبيانات المالية بسهولة داخل تطبيقات .NET الخاصة بهم. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك دمج Aspose.Finance for .NET بسلاسة في مشاريعك وتعزيز قدرات المعالجة المالية الخاصة بها.
## الأسئلة الشائعة
### 1. هل يمكنني استخدام Aspose.Finance لـ .NET بدون ترخيص؟
لا، يلزم الحصول على ترخيص صالح لفتح الميزات الكاملة لـ Aspose.Finance لـ .NET. ومع ذلك، تتوفر تراخيص مؤقتة لأغراض الاختبار.
### 2. هل Aspose.Finance for .NET مناسب لبناء برامج المحاسبة؟
نعم، يوفر Aspose.Finance for .NET وظائف قوية مصممة خصيصًا لبناء برامج المحاسبة والتطبيقات المالية ذات الصلة.
### 3. أين يمكنني العثور على الدعم لـ Aspose.Finance لـ .NET؟
يمكنك طلب المساعدة من مجتمع Aspose.Finance في منتدى الدعم.
### 4. هل يمكنني تخصيص وحدة القياس في مستند XBRL؟
نعم، يمكنك إنشاء وإضافة وحدات قياس مخصصة إلى مستندات XBRL باستخدام Aspose.Finance for .NET.
### 5. هل يدعم Aspose.Finance for .NET عملات متعددة؟
نعم، يدعم Aspose.Finance for .NET عملات متعددة، مما يسمح بمعالجة البيانات المالية المتنوعة.
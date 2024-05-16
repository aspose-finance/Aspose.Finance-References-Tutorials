---
title: أضف مرجع المخطط إلى مستند XBRL
linktitle: أضف مرجع المخطط إلى مستند XBRL
second_title: Aspose.Finance .NET API
description: تعرف على كيفية إضافة مراجع المخطط إلى مستندات XBRL باستخدام Aspose.Finance لـ .NET. قم بتبسيط معالجة بياناتك المالية اليوم!
type: docs
weight: 15
url: /ar/net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## تقديم Aspose.Finance لـ .NET
Aspose.Finance for .NET هي مكتبة قوية توفر وظائف شاملة لمعالجة المستندات والبيانات المالية ومعالجتها داخل تطبيقات .NET. سواء كنت تقوم بإنشاء برامج محاسبة أو أدوات تحليل مالي أو أي تطبيق مالي آخر، فإن Aspose.Finance for .NET يقدم مجموعة واسعة من الميزات لتبسيط عملية التطوير الخاصة بك.
## المتطلبات الأساسية
قبل الغوص في استخدام Aspose.Finance لـ .NET، تأكد من إعداد المتطلبات الأساسية التالية:
### 1. قم بتثبيت فيجوال ستوديو
تأكد من تثبيت Visual Studio على نظامك. يمكنك تنزيله وتثبيته من موقع Microsoft الرسمي.
### 2. الحصول على ترخيص Aspose.Finance
للاستفادة من الإمكانات الكاملة لـ Aspose.Finance لـ .NET، يتعين عليك الحصول على ترخيص صالح. يمكنك شراء ترخيص من[هنا](https://purchase.aspose.com/buy) أو اختر ترخيصًا مؤقتًا لأغراض الاختبار.
### 3. قم بتنزيل Aspose.Finance والمراجع الخاصة بـ .NET
 قم بتنزيل مكتبة Aspose.Finance for .NET من[صفحة الإصدارات](https://releases.aspose.com/finance/net/) وقم بالإشارة إليه في مشروع .NET الخاص بك.
### 4. الوصول إلى الوثائق والدعم
 الرجوع إلى[وثائق واجهة برمجة التطبيقات](https://reference.aspose.com/finance/net/) للحصول على معلومات مفصلة حول استخدام Aspose.Finance لـ .NET. بالإضافة إلى ذلك، يمكنك طلب المساعدة من مجتمع Aspose.Finance على الموقع[منتدى الدعم](https://forum.aspose.com/c/finance/43).
## استيراد مساحات الأسماء
لنبدأ باستيراد مساحات الأسماء الضرورية إلى مشروع .NET الخاص بك:
## الخطوة 1: إضافة مساحة الاسم Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
تحتوي مساحة الاسم هذه على فئات وطرق للعمل مع مستندات وبيانات XBRL.
الآن، دعنا نقسم المثال المقدم إلى خطوات متعددة لفهم كيفية إضافة مرجع مخطط إلى مستند XBRL باستخدام Aspose.Finance for .NET.
## الخطوة 1: تحديد أدلة المصدر والإخراج
```csharp
// دليل المصدر
string sourceDir = "Your Source Directory";
// دليل الإخراج
string outputDir = "Your Output Directory";
```
 يستبدل`"Your Source Directory"` و`"Your Output Directory"`مع المسارات الفعلية إلى دليل المصدر والإخراج على التوالي.
## الخطوة 2: إنشاء مستند XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
يؤدي هذا إلى إنشاء مثيل جديد لمستند XBRL.
## الخطوة 3: الوصول إلى مثيلات XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
يؤدي ذلك إلى استرداد مجموعة مثيلات XBRL من المستند وإضافة مثيل جديد إليها.
## الخطوة 4: إضافة مرجع المخطط
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
 يؤدي هذا إلى إضافة مرجع مخطط إلى مثيل XBRL. يستبدل`"schema.xsd"` بالاسم الفعلي لملف المخطط الخاص بك،`"example"` مع البادئة المناسبة، و`"http://example.com/xbrl/taxonomy"` مع مساحة الاسم المستهدفة URI.
## الخطوة 5: احفظ المستند
```csharp
document.Save(outputDir + @"document2.xbrl");
```
يؤدي هذا إلى حفظ مستند XBRL المعدل في دليل الإخراج المحدد.
## خاتمة
في الختام، يقدم Aspose.Finance for .NET حلاً قويًا للتعامل مع المستندات والبيانات المالية في تطبيقات .NET. باتباع الخطوات الموضحة في هذا البرنامج التعليمي، يمكنك بسهولة دمج Aspose.Finance في مشاريعك ومعالجة مستندات XBRL بكفاءة.
## الأسئلة الشائعة
 (أسئلة مكررة)
### 1. هل يمكنني استخدام Aspose.Finance لـ .NET بدون ترخيص؟
لا، أنت بحاجة إلى ترخيص صالح للاستفادة من الميزات الكاملة لـ Aspose.Finance لـ .NET. ومع ذلك، يمكنك الحصول على ترخيص مؤقت لأغراض الاختبار.
### 2. هل Aspose.Finance مناسب لبناء برامج المحاسبة؟
نعم، يوفر Aspose.Finance وظائف شاملة لمعالجة البيانات المالية، مما يجعله مثاليًا لبناء برامج المحاسبة والتطبيقات ذات الصلة.
### 3. أين يمكنني العثور على الدعم لـ Aspose.Finance؟
يمكنك طلب المساعدة من مجتمع Aspose.Finance في منتدى الدعم الرسمي.
### 4. هل يمكنني تخصيص البادئة المرجعية للمخطط؟
نعم، يمكنك اختيار بادئة مناسبة عند إضافة مرجع مخطط إلى مستند XBRL باستخدام Aspose.Finance for .NET.
### 5. هل يدعم Aspose.Finance التنسيقات المالية الأخرى إلى جانب XBRL؟
نعم، يدعم Aspose.Finance العديد من التنسيقات والمعايير المالية، مما يتيح التكامل السلس في التطبيقات المالية المتنوعة.
---
title: أضف سياقًا إلى مستند XBRL
linktitle: أضف سياقًا إلى مستند XBRL
second_title: Aspose.Finance .NET API
description: تعرف على كيفية إضافة سياق إلى مستندات XBRL في .NET باستخدام Aspose.Finance لإعداد تقارير مالية مبسطة. #Aspose #Finance #XBRL
type: docs
weight: 11
url: /ar/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## مقدمة
في مجال إعداد التقارير المالية، تلعب لغة XBRL (لغة تقارير الأعمال الموسعة) دورًا محوريًا في توحيد تبادل المعلومات التجارية. تعد إضافة سياق إلى مستندات XBRL أمرًا بالغ الأهمية لضمان سلامة وأهمية البيانات التي تحتوي عليها. مع Aspose.Finance for .NET، تصبح هذه العملية مبسطة وفعالة، مما يسمح للمطورين بدمج السياق بسلاسة في مستندات XBRL الخاصة بهم.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
1. Aspose.Finance for .NET Library: قم بتنزيل وتثبيت Aspose.Finance for .NET Library من[إطلاق](https://releases.aspose.com/finance/net/).
2. بيئة تطوير .NET: تأكد من أن لديك بيئة تطوير .NET عاملة تم إعدادها على جهازك.
3. الفهم الأساسي لـ C#: الإلمام بلغة البرمجة C# سيكون مفيدًا في متابعة الأمثلة.
## استيراد مساحات الأسماء
في مشروع C# الخاص بك، قم باستيراد مساحات الأسماء الضرورية للوصول إلى الوظائف التي يوفرها Aspose.Finance لـ .NET:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## الخطوة 1: تعيين دليل الإخراج
قبل إضافة سياق إلى مستند XBRL، حدد دليل الإخراج حيث سيتم حفظ المستند المعدل:
```csharp
string outputDir = "Your Output Directory";
```
 يستبدل`"Your Output Directory"` بالمسار المطلوب على نظامك.
## الخطوة 2: إنشاء مستند XBRL
 إنشاء مثيل ل`XbrlDocument` كائن للعمل مع وثائق XBRL:
```csharp
XbrlDocument document = new XbrlDocument();
```
يمثل هذا الكائن مستند XBRL الذي سيتم معالجته.
## الخطوة 3: إضافة مثيل XBRL
أضف مثيل XBRL إلى المستند. يحتوي كل مثيل على البيانات الخاصة بفترة إعداد التقارير المحددة:
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
تعمل هذه الخطوة على تهيئة مثيل XBRL داخل المستند.
## الخطوة 4: تحديد فترة السياق والكيان
قم بإنشاء فترة سياق وكيان لمثيل XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
حدد تفاصيل الفترة والكيان وفقًا لمتطلبات إعداد التقارير الخاصة بك.
## الخطوة 5: إنشاء السياق
أنشئ سياقًا باستخدام الفترة والكيان المحدد في الخطوة السابقة:
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
يتضمن هذا السياق المعلومات الزمنية والمتعلقة بالكيان.
## الخطوة 6: إضافة سياق إلى مثيل XBRL
قم بربط السياق الذي تم إنشاؤه في الخطوة السابقة بمثيل XBRL:
```csharp
xbrlInstance.Contexts.Add(context);
```
تربط هذه الخطوة السياق بمثيل XBRL، مما يوفر المعلومات السياقية ذات الصلة بالبيانات.
## الخطوة 7: احفظ المستند
احفظ مستند XBRL المعدل في دليل الإخراج المحدد:
```csharp
document.Save(outputDir + @"document3.xbrl");
```
يؤدي هذا إلى إنهاء العملية، وحفظ مستند XBRL بالسياق المُضاف.
## خاتمة
باتباع هذه الخطوات، يمكنك إضافة سياق إلى مستندات XBRL بشكل فعال باستخدام Aspose.Finance لـ .NET. وهذا يعزز وضوح البيانات المالية وسهولة استخدامها، ويسهل التحليل الدقيق وإعداد التقارير.
## الأسئلة الشائعة
### هل يستطيع Aspose.Finance for .NET التعامل مع مستندات XBRL الكبيرة؟
تم تحسين Aspose.Finance for .NET للتعامل مع مستندات XBRL ذات الأحجام المختلفة، بما في ذلك مجموعات البيانات الكبيرة.
### هل هناك إصدار تجريبي متاح لـ Aspose.Finance لـ .NET؟
نعم، يمكنك تنزيل نسخة تجريبية مجانية من موقع Aspose الرسمي.
### هل يدعم Aspose.Finance for .NET معايير إعداد التقارير المالية الأخرى إلى جانب XBRL؟
يركز Aspose.Finance في المقام الأول على الوظائف المتعلقة بـ XBRL ولكنه يوفر أيضًا الدعم للتنسيقات المالية الأخرى.
### هل يمكنني تخصيص معلومات السياق وفقًا لمتطلباتي المحددة؟
بالتأكيد، يوفر Aspose.Finance for .NET المرونة لتخصيص معلومات السياق لتناسب احتياجاتك.
### أين يمكنني العثور على دعم أو موارد إضافية لـ Aspose.Finance for .NET؟
يمكنك زيارة منتدى Aspose.Finance للحصول على المساعدة من المجتمع أو استكشاف الوثائق للحصول على إرشادات شاملة.
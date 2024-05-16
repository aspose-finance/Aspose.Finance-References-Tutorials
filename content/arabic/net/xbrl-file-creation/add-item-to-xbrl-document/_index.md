---
title: إضافة عنصر إلى مستند XBRL
linktitle: إضافة عنصر إلى مستند XBRL
second_title: Aspose.Finance .NET API
description: تعرف على كيفية إضافة عناصر إلى مستندات XBRL باستخدام Aspose.Finance لـ .NET. قم بتبسيط إعداد التقارير المالية في تطبيقات .NET الخاصة بك. #التمويل
type: docs
weight: 13
url: /ar/net/xbrl-file-creation/add-item-to-xbrl-document/
---
أصبحت لغة تقارير الأعمال الموسعة (XBRL) تنسيقًا قياسيًا لإعداد التقارير المالية، مما يتيح التواصل الفعال والدقيق للبيانات المالية. يوفر Aspose.Finance for .NET وظائف قوية للعمل مع مستندات XBRL في تطبيقات .NET الخاصة بك. في هذا البرنامج التعليمي، سنتعرف على خطوات إضافة عنصر إلى مستند XBRL باستخدام Aspose.Finance for .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
### 1. قم بتثبيت Aspose.Finance لـ .NET
 إذا لم تكن قد قمت بذلك بالفعل، فقم بتنزيل Aspose.Finance for .NET وتثبيته من[الموقع الرسمي](https://releases.aspose.com/finance/net/). اتبع تعليمات التثبيت لإعداد المكتبة في بيئة .NET الخاصة بك.
### 2. قم بإعداد بيئة التطوير الخاصة بك
تأكد من أن لديك بيئة تطوير عمل لتطوير .NET. ستحتاج إلى بيئة تطوير متكاملة (IDE) متوافقة مثل Visual Studio، بالإضافة إلى إطار عمل .NET المثبت على نظامك.
## استيراد مساحات الأسماء
أولاً، قم باستيراد مساحات الأسماء الضرورية إلى تطبيق .NET الخاص بك للاستفادة من الوظائف التي يوفرها Aspose.Finance لـ .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
# الآن دعونا نقسم كود المثال إلى خطوات متعددة:
## الخطوة 1: تحديد أدلة المصدر والإخراج
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 يستبدل`"Your Source Directory"` و`"Your Output Directory"` مع المسارات إلى مجلدات المصدر والإخراج، على التوالي.
## الخطوة 2: إنشاء مستند ومثيل XBRL
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
قم بتهيئة مستند XBRL ومثيله للعمل معه.
## الخطوة 3: إضافة مرجع المخطط
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
قم بإضافة مرجع مخطط إلى مثيل XBRL، مع توفير المسار إلى ملف المخطط وتحديد تفاصيل مساحة الاسم.
## الخطوة 4: تحديد السياق والكيان
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
قم بإنشاء سياق وكيان لمثيل XBRL، مع تحديد تفاصيل الفترة والكيان.
## الخطوة 5: إضافة الوحدة
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"))؛
xbrlInstance.Units.Add(unit);
```
حدد وحدة لمثيل XBRL، مع تحديد الأسماء المؤهلة للقياس.
## الخطوة 6: إضافة عنصر
```csharp
Concept fixedAssetsConcept = schema.GetConceptByName("fixedAssets");
if (fixedAssetsConcept != null)
{
    Item item = new Item(fixedAssetsConcept);
    item.ContextRef = context;
    item.UnitRef = unit;
    item.Precision = 4;
    item.Value = "1444";
    xbrlInstance.Facts.Add(item);
}
```
قم بإضافة عنصر إلى مثيل XBRL، مع تحديد مفهومه وسياقه ووحدته ودقته وقيمته.
## الخطوة 7: حفظ المستند
```csharp
document.Save(outputDir + @"document5.xbrl");
```
احفظ مستند XBRL في دليل الإخراج.
## خاتمة
تعد إضافة عناصر إلى مستند XBRL أمرًا ضروريًا لتمثيل البيانات المالية بدقة. يعمل Aspose.Finance for .NET على تبسيط هذه العملية من خلال توفير واجهة برمجة تطبيقات شاملة للعمل مع مستندات XBRL في تطبيقات .NET.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Finance لـ .NET مع أي تطبيق .NET؟
نعم، Aspose.Finance for .NET متوافق مع أي تطبيق .NET، بما في ذلك تطبيقات ASP.NET وWinForms وConsole.
### هل Aspose.Finance for .NET مجاني للاستخدام؟
 Aspose.Finance for .NET هي مكتبة تجارية. يمكنك تنزيل نسخة تجريبية مجانية لتقييم مميزاته، كما يمكن شراء التراخيص منه[هنا](https://purchase.aspose.com/buy).
### هل يدعم Aspose.Finance for .NET تنسيقات التقارير المالية الأخرى إلى جانب XBRL؟
يركز Aspose.Finance for .NET بشكل أساسي على الوظائف المرتبطة بـ XBRL. ومع ذلك، يقدم Aspose مكتبات أخرى للعمل بتنسيقات مالية مختلفة.
### كيف يمكنني الحصول على دعم Aspose.Finance لـ .NET؟
 يمكنك الحصول على دعم Aspose.Finance لـ .NET من خلال[المنتدى الرسمي](https://forum.aspose.com/c/finance/43)حيث يمكنك طرح الأسئلة والتفاعل مع المستخدمين الآخرين وموظفي الدعم.
### هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.Finance لـ .NET؟
 نعم، التراخيص المؤقتة لـ Aspose.Finance لـ .NET متاحة لأغراض الاختبار. يمكنك الحصول على واحدة[هنا](https://purchase.aspose.com/temporary-license/).
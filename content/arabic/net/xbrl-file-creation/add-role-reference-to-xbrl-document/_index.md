---
title: أضف مرجع الدور إلى مستند XBRL
linktitle: أضف مرجع الدور إلى مستند XBRL
second_title: Aspose.Finance .NET API
description: تعرف على كيفية إضافة مراجع الأدوار إلى مستندات XBRL باستخدام Aspose.Finance لـ .NET. قم بتبسيط إعداد التقارير المالية في تطبيقات .NET الخاصة بك باستخدام هذا البرنامج التعليمي.
type: docs
weight: 14
url: /ar/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
لقد أصبحت لغة XBRL (لغة تقارير الأعمال القابلة للتوسيع) معيارًا لتبادل المعلومات التجارية، خاصة في مجال إعداد التقارير المالية. يعمل Aspose.Finance for .NET على تبسيط العمل مع مستندات XBRL في تطبيقات .NET. سيرشدك هذا البرنامج التعليمي خلال عملية إضافة مرجع الدور إلى مستند XBRL باستخدام Aspose.Finance for .NET.
## المتطلبات الأساسية
قبل أن نبدأ، تأكد من توفر المتطلبات الأساسية التالية:
### 1. قم بتثبيت Aspose.Finance لـ .NET
تأكد من تثبيت Aspose.Finance for .NET في بيئة التطوير الخاصة بك. إذا لم تكن قد قمت بذلك بالفعل، قم بتنزيله من[إطلاق](https://releases.aspose.com/finance/net/) واتبع تعليمات التثبيت.
### 2. قم بإعداد بيئة التطوير الخاصة بك
تأكد من أن لديك بيئة تطوير عمل لتطوير .NET. يتضمن ذلك بيئة تطوير متكاملة (IDE) متوافقة مثل Visual Studio وإطار عمل .NET المثبت على نظامك.
## استيراد مساحات الأسماء
ابدأ باستيراد مساحات الأسماء الضرورية إلى تطبيق .NET الخاص بك للوصول إلى الوظائف التي يوفرها Aspose.Finance لـ .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## الخطوة 4: استرداد نوع الدور وإضافة مرجع الدور
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
استرجع نوع الدور باستخدام URI الخاص به وأضف مرجع الدور إلى مثيل XBRL.
## الخطوة 5: حفظ المستند
```csharp
document.Save(outputDir + @"document7.xbrl");
```
احفظ مستند XBRL في دليل الإخراج.
## خاتمة
تعد إضافة مراجع الدور إلى مستندات XBRL أمرًا ضروريًا لتحديد أدوار العناصر المختلفة داخل المستند. يوفر Aspose.Finance for .NET طريقة مباشرة لإنجاز هذه المهمة، مما يمكّن المطورين من العمل بكفاءة مع مستندات XBRL في تطبيقات .NET الخاصة بهم.
## الأسئلة الشائعة
### هل يمكنني استخدام Aspose.Finance لـ .NET مع أي تطبيق .NET؟
نعم، Aspose.Finance for .NET متوافق مع أي تطبيق .NET، بما في ذلك تطبيقات ASP.NET وWinForms وConsole.
### هل Aspose.Finance for .NET مجاني للاستخدام؟
 Aspose.Finance for .NET هي مكتبة تجارية. يمكنك تنزيل نسخة تجريبية مجانية لتقييم مميزاته، كما يمكن شراء التراخيص منه[هنا](https://purchase.aspose.com/buy).
### هل يدعم Aspose.Finance for .NET تنسيقات التقارير المالية الأخرى إلى جانب XBRL؟
يركز Aspose.Finance for .NET بشكل أساسي على الوظائف المرتبطة بـ XBRL. ومع ذلك، يقدم Aspose مكتبات أخرى للعمل بتنسيقات مالية مختلفة.
### كيف يمكنني الحصول على دعم Aspose.Finance لـ .NET؟
 يمكنك الحصول على دعم Aspose.Finance لـ .NET من خلال[المنتدى](https://forum.aspose.com/c/finance/43)حيث يمكنك طرح الأسئلة والتفاعل مع المستخدمين الآخرين وموظفي الدعم.
### هل يمكنني الحصول على ترخيص مؤقت لـ Aspose.Finance لـ .NET؟
 نعم، التراخيص المؤقتة لـ Aspose.Finance لـ .NET متاحة لأغراض الاختبار. يمكنك الحصول على واحدة[هنا](https://purchase.aspose.com/temporary-license/).
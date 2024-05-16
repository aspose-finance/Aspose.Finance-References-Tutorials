---
title: أضف مرجع دور ARC إلى مستند XBRL
linktitle: أضف مرجع دور ARC إلى مستند XBRL
second_title: Aspose.Finance .NET API
description: تعرف على كيفية التعامل بكفاءة مع مستندات XBRL باستخدام Aspose.Finance لـ .NET. أضف مراجع دور ARC بسهولة من خلال إرشادات خطوة بخطوة.
type: docs
weight: 10
url: /ar/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## مقدمة
في عالم إدارة البيانات المالية وإعداد التقارير، تلعب لغة تقارير الأعمال القابلة للتوسيع (XBRL) دورًا حاسمًا. فهو يوحد طريقة توصيل المعلومات المالية وتبادلها، مما يضمن الاتساق والدقة والكفاءة. ومع ذلك، فإن التعامل مع مستندات XBRL، خاصة عند دمج أدوار ومراجع محددة، يتطلب فهمًا دقيقًا للآليات الأساسية. يركز هذا البرنامج التعليمي على إحدى هذه المهام: إضافة مرجع دور ARC إلى مستند XBRL باستخدام Aspose.Finance لـ .NET.
## المتطلبات الأساسية
قبل الغوص في البرنامج التعليمي، تأكد من أن لديك المتطلبات الأساسية التالية:
### إعداد البيئة
1.  تثبيت Aspose.Finance لـ .NET: قم بتنزيل وتثبيت مكتبة Aspose.Finance لـ .NET من[إطلاق](https://releases.aspose.com/finance/net/).
   
2. بيئة التطوير: قم بإعداد بيئة التطوير الخاصة بك باستخدام Visual Studio أو أي بيئة تطوير متكاملة مفضلة أخرى.
## استيراد مساحات الأسماء
تأكد من استيراد مساحات الأسماء الضرورية في كود C# الخاص بك:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## الخطوة 1: تحديد أدلة المصدر والإخراج
قبل المتابعة، حدد مجلدي المصدر والمخرجات حيث سيتم تحديد موقع ملفات XBRL وحفظها، على التوالي.
```csharp
// دليل المصدر
string sourceDir = "Your Source Directory";
// دليل الإخراج
string outputDir = "Your Output Directory";
```
## الخطوة 2: إنشاء مستند XBRL
 إنشاء مثيل ل`XbrlDocument` كائن للعمل مع بيانات XBRL.
```csharp
XbrlDocument document = new XbrlDocument();
```
## الخطوة 3: الوصول إلى مجموعة XbrlInstance
قم بالوصول إلى مجموعة مثيلات XBRL داخل المستند.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## الخطوة 4: إضافة XbrlInstance
قم بإضافة مثيل XBRL جديد إلى المجموعة.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## الخطوة 5: إضافة مرجع المخطط
قم بتضمين مرجع المخطط في مثيل XBRL، مع تحديد الدليل المصدر، وبادئة مساحة الاسم، وURI.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
## الخطوة 6: استرداد ArcroleType
 استرداد`ArcroleType` بناءً على URI محدد.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## الخطوة 7: إضافة ArcroleReference
 إذا`ArcroleType` تم العثور عليه، قم بإنشاء`ArcroleReference` وإضافته إلى مراجع القوس لمثيل XBRL.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## الخطوة 8: احفظ المستند
احفظ مستند XBRL المعدل في دليل الإخراج المحدد.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## خاتمة
في هذا البرنامج التعليمي، اكتشفنا كيفية إضافة مرجع دور ARC إلى مستند XBRL باستخدام Aspose.Finance لـ .NET. باتباع هذه التعليمات خطوة بخطوة والاستفادة من إمكانيات Aspose.Finance، يمكنك إدارة بيانات XBRL ومعالجتها بكفاءة لتلبية متطلباتك المحددة.
## الأسئلة الشائعة
### ما هو XBRL؟
XBRL تعني لغة تقارير الأعمال الموسعة، وهي لغة موحدة للاتصال الإلكتروني للبيانات التجارية والمالية.
### لماذا تعتبر لغة XBRL مهمة؟
تضمن XBRL الاتساق والدقة والكفاءة في تبادل وتحليل المعلومات المالية، مما يفيد المنظمين والمحللين والشركات.
### هل يستطيع Aspose.Finance التعامل مع مهام XBRL المعقدة؟
نعم، يوفر Aspose.Finance وظائف قوية للعمل مع مستندات XBRL، بما في ذلك التعامل مع المهام المعقدة مثل مراجع الأدوار وإدارة التصنيف.
### هل Aspose.Finance متوافق مع مكتبات .NET الأخرى؟
نعم، يتكامل Aspose.Finance بسلاسة مع مكتبات .NET الأخرى، مما يوفر دعمًا شاملاً لمعالجة البيانات المالية وإعداد التقارير.
### أين يمكنني العثور على دعم إضافي لـ Aspose.Finance؟
 للحصول على دعم إضافي قم بزيارة[صفحة دعم Aspose.Finance](https://forum.aspose.com/c/finance/43).
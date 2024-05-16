---
title: Добавить ссылку на сноску в документ XBRL
linktitle: Добавить ссылку на сноску в документ XBRL
second_title: API Aspose.Finance .NET
description: Узнайте, как добавлять ссылки на сноски в документы XBRL с помощью Aspose.Finance для .NET. Усовершенствуйте финансовые отчеты с помощью дополнительного контекста без особых усилий.
type: docs
weight: 12
url: /ru/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
Добавление ссылки на сноску в документ XBRL имеет решающее значение для предоставления дополнительного контекста или объяснений конкретных точек данных. В этом руководстве мы шаг за шагом рассмотрим этот процесс, используя Aspose.Finance для .NET.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
1.  Aspose.Finance for .NET: убедитесь, что в вашей системе установлен Aspose.Finance for .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/finance/net/).
  
2. Среда разработки: настройте среду разработки с использованием .NET Framework или .NET Core.
## Импортировать пространства имен:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Шаг 1. Установите исходный и выходной каталоги
Сначала укажите каталоги для исходных и выходных файлов:
```csharp
// Исходный каталог
string sourceDir = "Your Source Directory";
// Выходной каталог
string outputDir = "Your Output Directory";
```
## Шаг 2. Создайте документ и экземпляр XBRL
Инициализируйте документ и экземпляр XBRL:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Шаг 3. Добавьте ссылки на схему
Добавьте ссылки на схему в экземпляр XBRL:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## Шаг 4: Определите контекст
Определите контекст для экземпляра XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## Шаг 5. Добавьте ссылку на сноску
Создайте и добавьте ссылку на сноску к экземпляру XBRL:
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
## Шаг 6: Сохраните документ
Сохраните измененный документ XBRL:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## Заключение
Добавление ссылки на сноску в документ XBRL — это простой процесс с помощью Aspose.Finance для .NET. Следуя шагам, описанным в этом руководстве, вы сможете легко включать дополнительный контекст или пояснения в свои финансовые отчеты.
## Часто задаваемые вопросы
### Могу ли я добавить несколько ссылок на сноски в один документ XBRL?
Да, вы можете добавить несколько ссылок на сноски, повторив шаги, описанные в этом руководстве, для каждой дополнительной ссылки.
### Совместим ли Aspose.Finance для .NET с .NET Framework и .NET Core?
Да, Aspose.Finance для .NET поддерживает среды .NET Framework и .NET Core.
### Как я могу получить временную лицензию на Aspose.Finance для .NET?
 Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### Обеспечивает ли Aspose.Finance для .NET поддержку проверки XBRL?
Да, Aspose.Finance для .NET предлагает комплексную поддержку проверки XBRL для обеспечения соответствия отраслевым стандартам.
### Где я могу найти дополнительные ресурсы и поддержку Aspose.Finance для .NET?
 Вы можете посетить[Форум Aspose.Finance для .NET](https://forum.aspose.com/c/finance/43) для поддержки и доступа к документации[здесь](https://reference.aspose.com/finance/net/).
---
title: Добавить элемент в документ XBRL
linktitle: Добавить элемент в документ XBRL
second_title: API Aspose.Finance .NET
description: Узнайте, как добавлять элементы в документы XBRL с помощью Aspose.Finance для .NET. Упростите финансовую отчетность в своих приложениях .NET. #Aspose #Финансы
type: docs
weight: 13
url: /ru/net/xbrl-file-creation/add-item-to-xbrl-document/
---
Расширяемый язык деловой отчетности (XBRL) стал стандартным форматом финансовой отчетности, обеспечивающим эффективную и точную передачу финансовых данных. Aspose.Finance for .NET обеспечивает надежную функциональность для работы с документами XBRL в ваших приложениях .NET. В этом руководстве мы рассмотрим шаги по добавлению элемента в документ XBRL с помощью Aspose.Finance для .NET.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
### 1. Установите Aspose.Finance для .NET.
 Если вы еще этого не сделали, загрузите и установите Aspose.Finance для .NET с сайта[Официальный веб-сайт](https://releases.aspose.com/finance/net/). Следуйте инструкциям по установке, чтобы настроить библиотеку в вашей среде .NET.
### 2. Настройте среду разработки
Убедитесь, что у вас есть рабочая среда разработки для .NET. Вам понадобится совместимая IDE, например Visual Studio, а также платформа .NET, установленная в вашей системе.
## Импортировать пространства имен
Сначала импортируйте необходимые пространства имен в ваше .NET-приложение, чтобы использовать функциональные возможности, предоставляемые Aspose.Finance для .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Теперь давайте разобьем пример кода на несколько шагов:
## Шаг 1. Определите исходный и выходной каталоги
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Заменять`"Your Source Directory"` и`"Your Output Directory"` с путями к исходному и выходному каталогам соответственно.
## Шаг 2. Создайте документ и экземпляр XBRL
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Инициализируйте документ XBRL и экземпляр для работы.
## Шаг 3. Добавьте ссылку на схему
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
Добавьте ссылку на схему в экземпляр XBRL, указав путь к файлу схемы и указав сведения о пространстве имен.
## Шаг 4. Определите контекст и сущность
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
Создайте контекст и сущность для экземпляра XBRL, указав период и детали сущности.
## Шаг 5: Добавьте единицу
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Определите единицу для экземпляра XBRL, указав полные имена показателей.
## Шаг 6: Добавьте элемент
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
Добавьте элемент в экземпляр XBRL, указав его концепцию, контекст, единицу измерения, точность и значение.
## Шаг 7: Сохранить документ
```csharp
document.Save(outputDir + @"document5.xbrl");
```
Сохраните документ XBRL в выходной каталог.
## Заключение
Добавление элементов в документ XBRL имеет важное значение для точного представления финансовых данных. Aspose.Finance для .NET упрощает этот процесс, предоставляя комплексный API для работы с документами XBRL в приложениях .NET.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Finance для .NET с любым приложением .NET?
Да, Aspose.Finance for .NET совместим с любым приложением .NET, включая ASP.NET, WinForms и консольные приложения.
### Можно ли использовать Aspose.Finance для .NET бесплатно?
 Aspose.Finance for .NET — коммерческая библиотека. Вы можете загрузить бесплатную пробную версию, чтобы оценить ее возможности, а лицензии можно приобрести на сайте[здесь](https://purchase.aspose.com/buy).
### Поддерживает ли Aspose.Finance for .NET другие форматы финансовой отчетности, кроме XBRL?
Aspose.Finance для .NET в первую очередь фокусируется на функциях, связанных с XBRL. Однако Aspose предлагает и другие библиотеки для работы с разными финансовыми форматами.
### Как я могу получить поддержку Aspose.Finance для .NET?
 Вы можете получить поддержку Aspose.Finance для .NET через[официальный форум](https://forum.aspose.com/c/finance/43)где вы можете задавать вопросы и общаться с другими пользователями и сотрудниками службы поддержки.
### Могу ли я получить временную лицензию на Aspose.Finance для .NET?
 Да, временные лицензии на Aspose.Finance для .NET доступны в целях тестирования. Вы можете получить один[здесь](https://purchase.aspose.com/temporary-license/).
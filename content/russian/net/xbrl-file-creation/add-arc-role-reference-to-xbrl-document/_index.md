---
title: Добавить ссылку на роль ARC в документ XBRL
linktitle: Добавить ссылку на роль ARC в документ XBRL
second_title: API Aspose.Finance .NET
description: Узнайте, как эффективно манипулировать документами XBRL с помощью Aspose.Finance для .NET. Добавляйте ссылки на роли ARC без особых усилий с помощью пошаговых инструкций.
type: docs
weight: 10
url: /ru/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## Введение
В мире управления финансовыми данными и отчетности решающую роль играет расширяемый язык бизнес-отчетности (XBRL). Он стандартизирует способы передачи и обмена финансовой информацией, обеспечивая согласованность, точность и эффективность. Однако манипулирование документами XBRL, особенно при включении определенных ролей и ссылок, требует тонкого понимания основных механизмов. В этом руководстве основное внимание уделяется одной из таких задач: добавлению ссылки на роль ARC в документ XBRL с использованием Aspose.Finance для .NET.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
### Настройка среды
1.  Установите Aspose.Finance for .NET: Загрузите и установите библиотеку Aspose.Finance for .NET из[релизы](https://releases.aspose.com/finance/net/).
   
2. Среда разработки: настройте среду разработки с помощью Visual Studio или любой другой предпочтительной IDE.
## Импортировать пространства имен
Обязательно импортируйте необходимые пространства имен в свой код C#:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Шаг 1. Определите исходный и выходной каталоги
Прежде чем продолжить, укажите исходный и выходной каталоги, в которых будут расположены и сохранены ваши файлы XBRL соответственно.
```csharp
// Исходный каталог
string sourceDir = "Your Source Directory";
// Выходной каталог
string outputDir = "Your Output Directory";
```
## Шаг 2. Создайте документ XBRL
 Создать экземпляр`XbrlDocument` объект для работы с данными XBRL.
```csharp
XbrlDocument document = new XbrlDocument();
```
## Шаг 3. Доступ к коллекции XbrlInstance
Получите доступ к коллекции экземпляров XBRL в документе.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## Шаг 4. Добавьте XbrlInstance
Добавьте в коллекцию новый экземпляр XBRL.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Шаг 5. Добавьте ссылку на схему
Включите ссылку на схему в экземпляр XBRL, указав исходный каталог, префикс пространства имен и URI.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
## Шаг 6: Получите ArcroleType
 Получить`ArcroleType` на основе определенного URI.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## Шаг 7. Добавьте ссылку ArcroleReference
 Если`ArcroleType` найден, создайте`ArcroleReference` и добавьте его в ссылки на дуги экземпляра XBRL.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## Шаг 8: Сохраните документ
Сохраните измененный документ XBRL в указанном выходном каталоге.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## Заключение
В этом руководстве мы рассмотрели, как добавить ссылку на роль ARC в документ XBRL с помощью Aspose.Finance для .NET. Следуя этим пошаговым инструкциям и используя возможности Aspose.Finance, вы сможете эффективно управлять данными XBRL и манипулировать ими в соответствии с вашими конкретными требованиями.
## Часто задаваемые вопросы
### Что такое XBRL?
XBRL означает расширяемый язык бизнес-отчетности, стандартизированный язык для электронной передачи деловых и финансовых данных.
### Почему XBRL важен?
XBRL обеспечивает согласованность, точность и эффективность обмена и анализа финансовой информации, принося пользу регулирующим органам, аналитикам и предприятиям.
### Может ли Aspose.Finance справиться со сложными задачами XBRL?
Да, Aspose.Finance предлагает надежные функциональные возможности для работы с документами XBRL, включая выполнение сложных задач, таких как ссылки на роли и управление таксономией.
### Совместим ли Aspose.Finance с другими библиотеками .NET?
Да, Aspose.Finance легко интегрируется с другими библиотеками .NET, обеспечивая обширную поддержку для манипулирования финансовыми данными и составления отчетов.
### Где я могу найти дополнительную поддержку Aspose.Finance?
 Для получения дополнительной поддержки посетите[Страница поддержки Aspose.Finance](https://forum.aspose.com/c/finance/43).
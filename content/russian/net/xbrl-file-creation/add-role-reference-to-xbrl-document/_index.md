---
title: Добавить ссылку на роль в документ XBRL
linktitle: Добавить ссылку на роль в документ XBRL
second_title: API Aspose.Finance .NET
description: Узнайте, как добавлять ссылки на роли в документы XBRL с помощью Aspose.Finance для .NET. Упростите финансовую отчетность в своих приложениях .NET с помощью этого руководства.
type: docs
weight: 14
url: /ru/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (расширяемый язык бизнес-отчетности) стал стандартом для обмена деловой информацией, особенно в финансовой отчетности. Aspose.Finance для .NET упрощает работу с документами XBRL в приложениях .NET. Это руководство проведет вас через процесс добавления ссылки на роль в документ XBRL с помощью Aspose.Finance для .NET.
## Предварительные условия
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
### 1. Установите Aspose.Finance для .NET.
Убедитесь, что в вашей среде разработки установлен Aspose.Finance for .NET. Если вы еще этого не сделали, загрузите его с сайта[релизы](https://releases.aspose.com/finance/net/) и следуйте инструкциям по установке.
### 2. Настройте среду разработки
Убедитесь, что у вас есть рабочая среда разработки для .NET. Сюда входит совместимая IDE, такая как Visual Studio, и платформа .NET, установленная в вашей системе.
## Импортировать пространства имен
Начните с импорта необходимых пространств имен в ваше .NET-приложение, чтобы получить доступ к функциям, предоставляемым Aspose.Finance для .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## Шаг 4. Получение типа роли и добавление ссылки на роль
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
Получите тип роли, используя его URI, и добавьте ссылку на роль в экземпляр XBRL.
## Шаг 5: Сохранить документ
```csharp
document.Save(outputDir + @"document7.xbrl");
```
Сохраните документ XBRL в выходной каталог.
## Заключение
Добавление ссылок на роли в документы XBRL имеет решающее значение для определения ролей различных элементов в документе. Aspose.Finance для .NET предоставляет простой способ выполнения этой задачи, давая разработчикам возможность эффективно работать с документами XBRL в своих .NET-приложениях.
## Часто задаваемые вопросы
### Могу ли я использовать Aspose.Finance для .NET с любым приложением .NET?
Да, Aspose.Finance for .NET совместим с любым приложением .NET, включая ASP.NET, WinForms и консольные приложения.
### Можно ли использовать Aspose.Finance для .NET бесплатно?
 Aspose.Finance for .NET — коммерческая библиотека. Вы можете загрузить бесплатную пробную версию, чтобы оценить ее возможности, а лицензии можно приобрести на сайте[здесь](https://purchase.aspose.com/buy).
### Поддерживает ли Aspose.Finance for .NET другие форматы финансовой отчетности, кроме XBRL?
Aspose.Finance для .NET в первую очередь фокусируется на функциях, связанных с XBRL. Однако Aspose предлагает и другие библиотеки для работы с разными финансовыми форматами.
### Как я могу получить поддержку Aspose.Finance для .NET?
 Вы можете получить поддержку Aspose.Finance для .NET через[Форум](https://forum.aspose.com/c/finance/43)где вы можете задавать вопросы и общаться с другими пользователями и сотрудниками службы поддержки.
### Могу ли я получить временную лицензию на Aspose.Finance для .NET?
 Да, временные лицензии на Aspose.Finance для .NET доступны в целях тестирования. Вы можете получить один[здесь](https://purchase.aspose.com/temporary-license/).
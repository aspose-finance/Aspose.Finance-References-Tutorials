---
title: Создать файл запроса на операцию OFX-банка
linktitle: Создать файл запроса на операцию OFX-банка
second_title: API Aspose.Finance .NET
description: Узнайте, как создать файл запроса транзакции OFX-банка с помощью Aspose.Finance для .NET, с помощью нашего подробного пошагового руководства. #Aspose #Финансы
type: docs
weight: 12
url: /ru/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
Создание файла запроса на банковскую транзакцию OFX может показаться сложной задачей, но при наличии правильных инструментов и инструкций это может оказаться простым процессом. В этом руководстве мы познакомим вас с каждым шагом создания файла запроса банковской транзакции OFX с использованием Aspose.Finance для .NET. Мы рассмотрим предварительные требования, необходимые пространства имен и предоставим подробное пошаговое руководство, чтобы вы могли легко следовать им.
## Предварительные условия
Прежде чем мы углубимся в руководство, вам необходимо иметь в виду несколько вещей:
1.  Visual Studio: убедитесь, что на вашем компьютере установлена Visual Studio. Вы можете скачать его с сайта[Официальный веб-сайт](https://visualstudio.microsoft.com/).
2.  Aspose.Finance для .NET: вам понадобится библиотека Aspose.Finance для .NET. Вы можете скачать его с[здесь](https://releases.aspose.com/finance/net/).
3. Базовые знания C#. Понимание основ программирования на C# поможет вам следовать примерам кода.
Если у вас есть все необходимые условия, вы готовы приступить к работе!
## Импортировать пространства имен
Сначала давайте импортируем необходимые пространства имен. Эти пространства имен имеют решающее значение для доступа к классам и методам, необходимым для создания файла запроса транзакции банка OFX.
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## Шаг 1. Настройте рабочий каталог
Прежде чем мы начнем создавать файл запроса OFX, нам необходимо указать выходной каталог, в котором файл будет сохранен.
```csharp
string outputDir = "Your Output Directory";
```
 Заменять`"Your Output Directory"` с указанием пути к каталогу, в котором вы хотите сохранить сгенерированный файл.
## Шаг 2. Создайте документ запроса OFX
 Далее нам нужно создать экземпляр`OfxRequestDocument` сорт. Этот класс будет служить контейнером для нашего запроса OFX.
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## Шаг 3. Настройте запрос на вход
Запрос на вход необходим для аутентификации пользователя и начала сеанса OFX. Мы настроим сообщение с запросом на вход и заполним его необходимыми данными, такими как дата клиента, идентификатор пользователя, пароль и информация о финансовом учреждении.
```csharp
document.SignonRequestMessageSetV1 = new SignonRequestMessageSetV1();
SignonRequest signonRequest = new SignonRequest();
document.SignonRequestMessageSetV1.SignonRequest = signonRequest;
signonRequest.ClientDate = "20200611000000";
signonRequest.UserId = "aspose";
signonRequest.UserPassword = "password";
FinancialInstitution fi = new FinancialInstitution();
fi.Organization = "aspose";
fi.FinancialInstitutionId = "1";
signonRequest.FinancialInstitution = fi;
signonRequest.AppVersion = "1.0";
signonRequest.AppId = "Aspose.Finance";
signonRequest.ClientUserId = "aaaaaaa";
```
## Шаг 4. Настройте сообщение банковского запроса
Теперь, когда запрос на вход настроен, мы перейдем к созданию сообщения банковского запроса. Это сообщение будет содержать информацию о банковском счете и запрос выписки по транзакции.
```csharp
document.BankRequestMessageSetV1 = new BankRequestMessageSetV1();
StatementTransactionRequest stmtTransRequest = new StatementTransactionRequest();
document.BankRequestMessageSetV1.StatementTransactionRequests.Add(stmtTransRequest);
stmtTransRequest.TransactionUniqueId = "1111111";
stmtTransRequest.StatementRequest = new StatementRequest();
stmtTransRequest.StatementRequest.BankAccountFrom = new BankAccount();
stmtTransRequest.StatementRequest.BankAccountFrom.BankId = "sssss";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountId = "sfsdfsfsdf";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountType = AccountEnum.CHECKING;
```
## Шаг 5. Добавьте сведения о транзакции
 Чтобы получить конкретные транзакции, нам нужно указать диапазон дат и указать, включать ли транзакции в запрос. Это осуществляется путем настройки`IncTransaction` объект.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## Шаг 6. Сохраните документ запроса OFX
Наконец, мы сохраним документ запроса OFX в форматах XML и SGML. Это обеспечивает совместимость с различными системами, которые могут использовать любой формат.
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## Шаг 7: Подтвердите успешное выполнение
Чтобы подтвердить успешное выполнение процесса, мы можем вывести сообщение на консоль.
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## Заключение
Создание файла запроса банковской транзакции OFX с использованием Aspose.Finance for .NET — это методический процесс, который включает в себя настройку документа запроса, настройку сообщений входа в систему и банковских запросов, указание деталей транзакции и сохранение документа. Следуя этому пошаговому руководству, вы сможете эффективно создавать файлы запросов OFX, адаптированные к вашим конкретным потребностям.
## Часто задаваемые вопросы
### 1. Что такое файл OFX?
Файл OFX (Open Financial Exchange) — это стандартный формат, используемый для обмена финансовыми данными между учреждениями и пользователями. Он широко используется для банковских выписок, транзакций и другой финансовой деятельности.
### 2. Могу ли я использовать Aspose.Finance для .NET с другими языками программирования?
Aspose.Finance for .NET специально разработан для использования с языками .NET, такими как C#. Однако вы можете использовать его в любой среде, поддерживаемой .NET.
### 3. Доступна ли бесплатная пробная версия Aspose.Finance для .NET?
Да, вы можете загрузить бесплатную пробную версию Aspose.Finance для .NET с сайта[здесь](https://releases.aspose.com/).
### 4. Как мне получить поддержку Aspose.Finance для .NET?
 Вы можете получить поддержку от сообщества Aspose и технической команды через их[форум поддержки](https://forum.aspose.com/c/finance/43).
### 5. Могу ли я получить временную лицензию на Aspose.Finance для .NET?
 Да, Aspose предлагает[временная лицензия](https://purchase.aspose.com/temporary-license/) которые вы можете использовать для оценки продукта.
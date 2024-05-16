---
title: 创建 OFX 银行交易请求文件
linktitle: 创建 OFX 银行交易请求文件
second_title: Aspose.Finance .NET API
description: 通过我们详细的分步指南了解如何使用 Aspose.Finance for .NET 创建 OFX 银行交易请求文件。#Aspose #Finance
type: docs
weight: 12
url: /zh/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
创建 OFX 银行交易请求文件似乎很困难，但有了正确的工具和指导，它可以是一个简单的过程。在本教程中，我们将引导您完成使用 Aspose.Finance for .NET 生成 OFX 银行交易请求文件的每个步骤。我们将介绍先决条件、必要的命名空间，并提供详细的分步指南，以确保您可以轻松完成。
## 先决条件
在深入学习本教程之前，您需要做好以下几件事：
1.  Visual Studio：请确保您的计算机上已安装 Visual Studio。您可以从[官方网站](https://visualstudio.microsoft.com/).
2. Aspose.Finance for .NET：您需要 Aspose.Finance for .NET 库。您可以从以下位置下载[这里](https://releases.aspose.com/finance/net/).
3. 基本 C# 知识：了解 C# 编程的基础知识将帮助您理解代码示例。
一旦满足了这些先决条件，您就可以开始了！
## 导入命名空间
首先，让我们导入必要的命名空间。这些命名空间对于访问创建 OFX 银行交易请求文件所需的类和方法至关重要。
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## 步骤 1：设置工作目录
在我们开始创建 OFX 请求文件之前，我们需要指定保存文件的输出目录。
```csharp
string outputDir = "Your Output Directory";
```
代替`"Your Output Directory"`使用您想要保存生成的文件的目录路径。
## 步骤 2：创建 OFX 请求文档
接下来，我们需要创建一个实例`OfxRequestDocument`类。此类将作为我们的 OFX 请求的容器。
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## 步骤 3：设置登录请求
登录请求对于验证用户身份和启动 OFX 会话至关重要。我们将设置登录请求消息，并在其中填充必要的详细信息，例如客户日期、用户 ID、密码和金融机构信息。
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
## 步骤 4：设置银行请求消息
现在登录请求已设置完毕，我们将继续创建银行请求消息。此消息将包含银行账户的详细信息和交易报表请求。
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
## 步骤 5：添加交易详细信息
要检索特定交易，我们需要指定日期范围以及是否在请求中包含交易。这可以通过设置`IncTransaction`目的。
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## 步骤 6：保存 OFX 请求文档
最后，我们将以 XML 和 SGML 格式保存 OFX 请求文档。这确保与可能使用任一格式的不同系统兼容。
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## 步骤7：确认执行成功
为了确认该过程执行成功，我们可以向控制台打印一条消息。
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## 结论
使用 Aspose.Finance for .NET 创建 OFX 银行交易请求文件是一个系统性的过程，包括设置请求文档、配置登录和银行请求消息、指定交易详细信息以及保存文档。通过遵循此分步指南，您可以高效地生成适合您特定需求的 OFX 请求文件。
## 常见问题解答
### 1.什么是 OFX 文件？
OFX（开放金融交换）文件是机构与用户之间交换财务数据的标准格式。它广泛用于银行对账单、交易和其他金融活动。
### 2. 我可以将 Aspose.Finance for .NET 与其他编程语言一起使用吗？
Aspose.Finance for .NET 专为 C# 等 .NET 语言而设计。不过，您可以在任何支持 .NET 的环境中使用它。
### 3. Aspose.Finance for .NET 有免费试用版吗？
是的，您可以从以下网址下载 Aspose.Finance for .NET 的免费试用版[这里](https://releases.aspose.com/).
### 4. 如何获得 Aspose.Finance for .NET 的支持？
您可以通过以下方式获得 Aspose 社区和技术团队的支持[支持论坛](https://forum.aspose.com/c/finance/43).
### 5. 我可以获得 Aspose.Finance for .NET 的临时许可证吗？
是的，Aspose 提供[临时执照](https://purchase.aspose.com/temporary-license/)您可以用它来评估产品。
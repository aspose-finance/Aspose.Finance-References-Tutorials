---
title: 建立 OFX 銀行交易請求文件
linktitle: 建立 OFX 銀行交易請求文件
second_title: Aspose.Finance .NET API
description: 透過我們詳細的逐步指南，了解如何使用 Aspose.Finance for .NET 建立 OFX 銀行交易請求檔。 #Aspose #Finance
type: docs
weight: 12
url: /zh-hant/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
建立 OFX 銀行交易請求文件可能看起來令人畏懼，但如果有正確的工具和指導，這可能是一個簡單的過程。在本教學中，我們將引導您完成使用 Aspose.Finance for .NET 產生 OFX 銀行交易請求檔案的每個步驟。我們將介紹先決條件、必要的命名空間，並提供詳細的逐步指南，以確保您可以輕鬆遵循。
## 先決條件
在我們深入學習本教程之前，您需要準備好一些東西：
1.  Visual Studio：確保您的電腦上安裝了 Visual Studio。您可以從[官方網站](https://visualstudio.microsoft.com/).
2. Aspose.Finance for .NET：您需要 Aspose.Finance for .NET 函式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/finance/net/).
3. 基本 C# 知識：了解 C# 程式設計的基礎知識將幫助您理解程式碼範例。
一旦滿足了這些先決條件，您就可以開始了！
## 導入命名空間
首先，讓我們導入必要的名稱空間。這些命名空間對於存取建立 OFX 銀行交易請求檔案所需的類別和方法至關重要。
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## 第 1 步：設定工作目錄
在開始建立 OFX 請求檔案之前，我們需要指定保存檔案的輸出目錄。
```csharp
string outputDir = "Your Output Directory";
```
代替`"Your Output Directory"`以及要保存生成文件的目錄的路徑。
## 第 2 步：建立 OFX 請求文檔
接下來，我們需要建立一個實例`OfxRequestDocument`班級。這個類別將作為我們的 OFX 請求的容器。
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## 第 3 步：設定登入請求
登入請求對於驗證使用者身分和啟動 OFX 會話至關重要。我們將設定登入請求訊息，並在其中填充必要的詳細信息，例如客戶日期、使用者 ID、密碼和金融機構資訊。
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
## 第 4 步：設定銀行請求訊息
現在登入請求已設置，我們將繼續建立銀行請求訊息。該訊息將包含銀行帳戶和交易報表請求的詳細資訊。
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
## 第 5 步：包含交易詳細信息
要檢索特定交易，我們需要指定日期範圍以及是否在請求中包含交易。這是透過設定來完成的`IncTransaction`目的。
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## 第 6 步：儲存 OFX 請求文檔
最後，我們將以 XML 和 SGML 格式儲存 OFX 請求文件。這確保了與可能使用任一格式的不同系統的兼容性。
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## 第七步：確認執行成功
為了確認進程執行成功，我們可以在控制台列印一則訊息。
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## 結論
使用 Aspose.Finance for .NET 建立 OFX 銀行交易請求文件是一個系統化的過程，涉及設定請求文件、配置登入和銀行請求訊息、指定交易詳細資訊以及保存文件。透過遵循此逐步指南，您可以有效地產生適合您的特定需求的 OFX 請求檔案。
## 常見問題解答
### 1.OFX檔是什麼？
OFX（開放式金融交換）檔案是用於在機構和使用者之間交換金融資料的標準格式。它廣泛用於銀行報表、交易和其他金融活動。
### 2. 我可以將Aspose.Finance for .NET與其他程式語言一起使用嗎？
Aspose.Finance for .NET 專為與 C# 等 .NET 語言一起使用而設計。但是，您可以在任何支援 .NET 的環境中使用它。
### 3. Aspose.Finance for .NET 是否有免費試用版？
是的，您可以從以下位置下載 Aspose.Finance for .NET 的免費試用版：[這裡](https://releases.aspose.com/).
### 4. 如何獲得 Aspose.Finance for .NET 支援？
您可以透過 Aspose 社群和技術團隊獲得支持[支援論壇](https://forum.aspose.com/c/finance/43).
### 5. 我可以取得 Aspose.Finance for .NET 的臨時授權嗎？
是的，Aspose 提供了[臨時執照](https://purchase.aspose.com/temporary-license/)您可以用它來評估產品。
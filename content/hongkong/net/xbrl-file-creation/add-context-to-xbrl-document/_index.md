---
title: 新增上下文到 XBRL 文檔
linktitle: 新增上下文到 XBRL 文檔
second_title: Aspose.Finance .NET API
description: 了解如何使用 Aspose.Finance 為 .NET 中的 XBRL 文件新增上下文，以簡化財務報告。 #Aspose #Finance #XBRL
type: docs
weight: 11
url: /zh-hant/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## 介紹
在財務報告領域，XBRL（可擴展商業報告語言）在標準化商業資訊交換方面發揮關鍵作用。為 XBRL 文件添加上下文對於確保其所包含資料的完整性和相關性至關重要。借助 Aspose.Finance for .NET，此流程變得精簡且高效，使開發人員能夠將上下文無縫合併到其 XBRL 文件中。
## 先決條件
在深入學習本教程之前，請確保您符合以下先決條件：
1. Aspose.Finance for .NET 函式庫：從下列位置下載並安裝 Aspose.Finance for .NET 函式庫：[發布](https://releases.aspose.com/finance/net/).
2. .NET 開發環境：確保您的電腦上設定了有效的 .NET 開發環境。
3. 對 C# 的基本了解：熟悉 C# 程式語言將有助於理解範例。
## 導入命名空間
在您的 C# 專案中，匯入必要的命名空間以存取 Aspose.Finance for .NET 提供的功能：
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## 第1步：設定輸出目錄
在將上下文新增至 XBRL 文件之前，請指定將儲存修改後的文件的輸出目錄：
```csharp
string outputDir = "Your Output Directory";
```
代替`"Your Output Directory"`與系統上所需的路徑。
## 第 2 步：建立 XBRL 文檔
實例化一個`XbrlDocument`物件使用 XBRL 文件：
```csharp
XbrlDocument document = new XbrlDocument();
```
該物件代表將要操作的 XBRL 文件。
## 步驟 3：新增 XBRL 實例
將 XBRL 實例新增至文件。每個實例包含特定報告期間的資料：
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
此步驟將初始化文件中的 XBRL 實例。
## 步驟 4：定義上下文週期和實體
為 XBRL 實例建立上下文期間和實體：
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
根據您的報告要求指定期間和實體詳細資訊。
## 第 5 步：建立上下文
使用上一個步驟中定義的周期和實體建構上下文：
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
該上下文封裝了時間和實體相關的資訊。
## 第 6 步：將上下文新增至 XBRL 實例
將上一步中建立的上下文與 XBRL 實例關聯：
```csharp
xbrlInstance.Contexts.Add(context);
```
此步驟將上下文連結到 XBRL 實例，為資料提供相關上下文資訊。
## 步驟7：儲存文檔
將修改後的XBRL文件儲存到指定的輸出目錄：
```csharp
document.Save(outputDir + @"document3.xbrl");
```
這完成了該過程，保存帶有添加上下文的 XBRL 文件。
## 結論
透過執行這些步驟，您可以使用 Aspose.Finance for .NET 有效地在 XBRL 文件中新增上下文。這增強了財務數據的清晰度和可用性，促進準確的分析和報告。
## 常見問題解答
### Aspose.Finance for .NET 可以處理大型 XBRL 文件嗎？
Aspose.Finance for .NET 經過最佳化，可以處理不同大小的 XBRL 文檔，包括大型資料集。
### Aspose.Finance for .NET 有試用版嗎？
是的，您可以從 Aspose 官方網站下載免費試用版。
### 除了 XBRL 之外，Aspose.Finance for .NET 是否支援其他財務報告標準？
Aspose.Finance 主要專注於 XBRL 相關功能，但也提供其他財務格式的支援。
### 我可以根據我的具體需求自訂上下文資訊嗎？
當然，Aspose.Finance for .NET 提供了自訂上下文資訊以滿足您的需求的靈活性。
### 在哪裡可以找到 Aspose.Finance for .NET 的其他支援或資源？
您可以造訪 Aspose.Finance 論壇尋求社群的協助，或瀏覽文件以獲得全面的指導。
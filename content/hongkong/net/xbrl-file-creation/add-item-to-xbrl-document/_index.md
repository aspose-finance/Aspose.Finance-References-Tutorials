---
title: 將項目新增至 XBRL 文檔
linktitle: 將項目新增至 XBRL 文檔
second_title: Aspose.Finance .NET API
description: 了解如何使用 Aspose.Finance for .NET 將專案新增至 XBRL 文件。簡化 .NET 應用程式中的財務報告。 #Aspose #Finance
type: docs
weight: 13
url: /zh-hant/net/xbrl-file-creation/add-item-to-xbrl-document/
---
可擴展業務報告語言 (XBRL) 已成為財務報告的標準格式，可實現財務資料的高效、準確通訊。 Aspose.Finance for .NET 提供了在 .NET 應用程式中處理 XBRL 文件的強大功能。在本教學中，我們將逐步介紹使用 Aspose.Finance for .NET 將專案新增至 XBRL 文件的步驟。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
### 1.安裝Aspose.Finance for .NET
如果您還沒有安裝 Aspose.Finance for .NET，請從[官方網站](https://releases.aspose.com/finance/net/)。依照安裝說明在 .NET 環境中設定庫。
### 2. 設定您的開發環境
確保您擁有用於 .NET 開發的有效開發環境。您需要一個相容的 IDE（例如 Visual Studio），以及系統上安裝的 .NET 框架。
## 導入命名空間
首先，將必要的命名空間匯入到您的 .NET 應用程式中，以利用 Aspose.Finance for .NET 提供的功能。
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#現在讓我們將範例程式碼分解為多個步驟：
## 第 1 步：定義來源目錄和輸出目錄
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
代替`"Your Source Directory"`和`"Your Output Directory"`分別包含來源目錄和輸出目錄的路徑。
## 步驟 2：建立 XBRL 文件和實例
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
初始化要使用的 XBRL 文件和實例。
## 第 3 步：新增架構參考
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
新增對 XBRL 實例的架構引用，提供架構檔案的路徑並指定命名空間詳細資訊。
## 第 4 步：定義上下文和實體
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
為 XBRL 實例建立上下文和實體，指定期間和實體詳細資訊。
## 第 5 步：新增單位
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"))；
xbrlInstance.Units.Add(unit);
```
定義 XBRL 實例的單位，指定度量限定名稱。
## 第 6 步：新增項目
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
將項目新增至 XBRL 實例，指定其概念、上下文、單位、精確度和值。
## 步驟7：儲存文檔
```csharp
document.Save(outputDir + @"document5.xbrl");
```
將 XBRL 文件儲存到輸出目錄。
## 結論
為 XBRL 文件新增項目對於準確表示財務資料至關重要。 Aspose.Finance for .NET 透過提供全面的 API 來處理 .NET 應用程式中的 XBRL 文檔，從而簡化了這個過程。
## 常見問題解答
### 我可以將 Aspose.Finance for .NET 與任何 .NET 應用程式一起使用嗎？
是的，Aspose.Finance for .NET 與任何 .NET 應用程式相容，包括 ASP.NET、WinForms 和控制台應用程式。
### Aspose.Finance for .NET 可以免費使用嗎？
 Aspose.Finance for .NET 是一個商業函式庫。您可以下載免費試用版來評估其功能，並且可以從以下位置購買許可證[這裡](https://purchase.aspose.com/buy).
### 除 XBRL 之外，Aspose.Finance for .NET 是否支援其他財務報告格式？
Aspose.Finance for .NET 主要關注 XBRL 相關功能。然而，Aspose 提供了其他函式庫來處理不同的金融格式。
### 我如何獲得 Aspose.Finance for .NET 支援？
您可以透過以下方式獲得 Aspose.Finance for .NET 支持[官方論壇](https://forum.aspose.com/c/finance/43)，您可以在其中提出問題並與其他用戶和支援人員互動。
### 我可以取得 Aspose.Finance for .NET 的臨時授權嗎？
是的，Aspose.Finance for .NET 的臨時許可證可用於測試目的。您可以獲得一個[這裡](https://purchase.aspose.com/temporary-license/).
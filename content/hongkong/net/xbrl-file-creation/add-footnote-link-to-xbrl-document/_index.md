---
title: 新增 XBRL 文件的腳註鏈接
linktitle: 新增 XBRL 文件的腳註鏈接
second_title: Aspose.Finance .NET API
description: 了解如何使用 Aspose.Finance for .NET 將腳註連結新增至 XBRL 文件。輕鬆透過附加背景增強財務報告。
type: docs
weight: 12
url: /zh-hant/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
在 XBRL 文件中新增腳註連結對於為特定資料點提供附加上下文或解釋至關重要。在本教程中，我們將使用 Aspose.Finance for .NET 逐步完成該過程。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1.  Aspose.Finance for .NET：請確定您的系統上已安裝 Aspose.Finance for .NET。您可以從以下位置下載：[這裡](https://releases.aspose.com/finance/net/).
  
2. 開發環境：使用 .NET Framework 或 .NET Core 設定開發環境。
## 導入命名空間：
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## 第 1 步：設定來源目錄和輸出目錄
首先，指定原始檔案和輸出檔案的目錄：
```csharp
//原始碼目錄
string sourceDir = "Your Source Directory";
//輸出目錄
string outputDir = "Your Output Directory";
```
## 步驟 2：建立 XBRL 文件和實例
初始化 XBRL 文件和實例：
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## 第 3 步：新增架構引用
將架構引用加入到 XBRL 實例：
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## 第 4 步：定義上下文
定義 XBRL 實例的上下文：
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## 第 5 步：新增腳註鏈接
建立腳註連結並將其新增至 XBRL 實例：
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
## 第 6 步：儲存文檔
儲存修改後的 XBRL 文件：
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## 結論
使用 Aspose.Finance for .NET 將腳註連結新增至 XBRL 文件是一個簡單的過程。透過遵循本教程中概述的步驟，您可以將其他上下文或解釋無縫地合併到您的財務報告中。
## 常見問題解答
### 我可以為單一 XBRL 文件添加多個腳註連結嗎？
是的，您可以透過對每個附加連結重複本教程中概述的步驟來新增多個腳註連結。
### Aspose.Finance for .NET 是否與 .NET Framework 和 .NET Core 相容？
是的，Aspose.Finance for .NET 支援 .NET Framework 和 .NET Core 環境。
### 如何取得 Aspose.Finance for .NET 的臨時授權？
您可以從以下地址取得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### Aspose.Finance for .NET 是否提供對 XBRL 驗證的支援？
是的，Aspose.Finance for .NET 為 XBRL 驗證提供全面支持，以確保符合業界標準。
### 在哪裡可以找到 Aspose.Finance for .NET 的其他資源和支援？
您可以訪問[Aspose.Finance for .NET 論壇](https://forum.aspose.com/c/finance/43)支援和存取文檔[這裡](https://reference.aspose.com/finance/net/).
---
title: 將 ARC 角色引用新增至 XBRL 文檔
linktitle: 將 ARC 角色引用新增至 XBRL 文檔
second_title: Aspose.Finance .NET API
description: 了解如何使用 Aspose.Finance for .NET 有效率地操作 XBRL 文件。透過逐步指導輕鬆新增 ARC 角色引用。
type: docs
weight: 10
url: /zh-hant/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## 介紹
在財務資料管理和報告領域，可擴展業務報告語言 (XBRL) 發揮著至關重要的作用。它標準化了財務資訊的溝通和交換方式，確保一致性、準確性和效率。然而，操作 XBRL 文檔，尤其是在合併特定角色和引用時，需要對底層機制有細緻的了解。本教學重點在於這樣一項任務：使用 Aspose.Finance for .NET 將 ARC 角色參考新增至 XBRL 文件。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
### 環境設定
1. 安裝 Aspose.Finance for .NET：從下列位置下載並安裝 Aspose.Finance for .NET 程式庫：[發布](https://releases.aspose.com/finance/net/).
   
2. 開發環境：使用 Visual Studio 或任何其他首選 IDE 設定開發環境。
## 導入命名空間
確保在 C# 程式碼中導入必要的命名空間：
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## 第 1 步：定義來源目錄和輸出目錄
在繼續之前，請分別指定 XBRL 檔案所在的來源目錄和輸出目錄。
```csharp
//原始碼目錄
string sourceDir = "Your Source Directory";
//輸出目錄
string outputDir = "Your Output Directory";
```
## 第 2 步：建立 XBRL 文檔
實例化一個`XbrlDocument`使用 XBRL 資料的物件。
```csharp
XbrlDocument document = new XbrlDocument();
```
## 步驟 3：造訪 XbrlInstance 集合
存取文件中 XBRL 實例的集合。
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## 第 4 步：新增 XbrlInstance
將新的 XBRL 實例加入集合。
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## 第 5 步：新增架構參考
在 XBRL 實例中包含架構引用，指定來源目錄、命名空間前綴和 URI。
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
## 第 6 步：擷取 ArcroleType
檢索`ArcroleType`基於特定的 URI。
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## 步驟7：新增ArcroleReference
如果`ArcroleType`找到後，創建一個`ArcroleReference`並將其新增至 XBRL 實例的 arcrole 引用。
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## 第 8 步：儲存文檔
將修改後的 XBRL 文件儲存到指定的輸出目錄。
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## 結論
在本教學中，我們探討如何使用 Aspose.Finance for .NET 將 ARC 角色參考新增至 XBRL 文件。透過遵循這些逐步說明並利用 Aspose.Finance 的功能，您可以有效地管理和操作 XBRL 資料以滿足您的特定要求。
## 常見問題解答
### 什麼是XBRL？
XBRL 代表可擴展商業報告語言，是一種用於商業和財務數據電子通訊的標準化語言。
### 為什麼 XBRL 很重要？
XBRL 確保財務資訊交換和分析的一致性、準確性和效率，使監管機構、分析師和企業受益。
### Aspose.Finance 可以處理複雜的 XBRL 任務嗎？
是的，Aspose.Finance 提供了處理 XBRL 文件的強大功能，包括處理角色引用和分類管理等複雜任務。
### Aspose.Finance 與其他 .NET 函式庫相容嗎？
是的，Aspose.Finance 與其他 .NET 程式庫無縫集成，為財務資料操作和報告提供廣泛的支援。
### 在哪裡可以找到對 Aspose.Finance 的額外支援？
如需更多支持，請訪問[Aspose.Finance 支援頁面](https://forum.aspose.com/c/finance/43).
---
title: 將角色引用新增至 XBRL 文檔
linktitle: 將角色引用新增至 XBRL 文檔
second_title: Aspose.Finance .NET API
description: 了解如何使用 Aspose.Finance for .NET 將角色參考新增至 XBRL 文件。透過本教程簡化 .NET 應用程式中的財務報告。
type: docs
weight: 14
url: /zh-hant/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL（可擴展商業報告語言）已成為交換商業資訊的標準，特別是在財務報告方面。 Aspose.Finance for .NET 簡化了 .NET 應用程式中 XBRL 文件的使用。本教學將引導您完成使用 Aspose.Finance for .NET 將角色參考新增至 XBRL 文件的過程。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
### 1.安裝Aspose.Finance for .NET
確保您的開發環境中安裝了 Aspose.Finance for .NET。如果您還沒有下載，請從[發布](https://releases.aspose.com/finance/net/)並按照安裝說明進行操作。
### 2. 設定您的開發環境
確保您擁有用於 .NET 開發的有效開發環境。這包括相容的 IDE，例如安裝在系統上的 Visual Studio 和 .NET 框架。
## 導入命名空間
首先將必要的命名空間匯入到您的 .NET 應用程式中，以存取 Aspose.Finance for .NET 提供的功能。
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## 步驟 4：檢索角色類型並新增角色引用
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
使用其 URI 檢索角色類型並將角色引用新增至 XBRL 實例。
## 第5步：儲存文檔
```csharp
document.Save(outputDir + @"document7.xbrl");
```
將 XBRL 文件儲存到輸出目錄。
## 結論
在 XBRL 文件中新增角色引用對於定義文件中各種元素的角色至關重要。 Aspose.Finance for .NET 提供了一種簡單的方法來完成此任務，使開發人員能夠在其 .NET 應用程式中有效地使用 XBRL 文件。
## 常見問題解答
### 我可以將 Aspose.Finance for .NET 與任何 .NET 應用程式一起使用嗎？
是的，Aspose.Finance for .NET 與任何 .NET 應用程式相容，包括 ASP.NET、WinForms 和控制台應用程式。
### Aspose.Finance for .NET 可以免費使用嗎？
 Aspose.Finance for .NET 是一個商業函式庫。您可以下載免費試用版來評估其功能，並且可以從以下位置購買許可證[這裡](https://purchase.aspose.com/buy).
### 除 XBRL 之外，Aspose.Finance for .NET 是否支援其他財務報告格式？
Aspose.Finance for .NET 主要關注 XBRL 相關功能。然而，Aspose 提供了其他函式庫來處理不同的金融格式。
### 我如何獲得 Aspose.Finance for .NET 支援？
您可以透過以下方式獲得 Aspose.Finance for .NET 支持[論壇](https://forum.aspose.com/c/finance/43)，您可以在其中提出問題並與其他用戶和支援人員互動。
### 我可以取得 Aspose.Finance for .NET 的臨時授權嗎？
是的，Aspose.Finance for .NET 的臨時許可證可用於測試目的。您可以獲得一個[這裡](https://purchase.aspose.com/temporary-license/).
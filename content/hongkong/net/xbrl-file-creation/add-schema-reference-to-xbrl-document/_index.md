---
title: 將架構引用新增至 XBRL 文檔
linktitle: 將架構引用新增至 XBRL 文檔
second_title: Aspose.Finance .NET API
description: 了解如何使用 Aspose.Finance for .NET 將架構參考新增至 XBRL 文件。立即簡化您的財務資料處理！
type: docs
weight: 15
url: /zh-hant/net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## 介紹 Aspose.Finance for .NET
Aspose.Finance for .NET 是一個功能強大的程式庫，提供了在 .NET 應用程式中處理和操作財務文件和資料的全面功能。無論您是在建立會計軟體、財務分析工具或任何其他財務應用程序，Aspose.Finance for .NET 都提供了廣泛的功能來簡化您的開發流程。
## 先決條件
在深入使用 Aspose.Finance for .NET 之前，請確保您已設定以下先決條件：
### 1.安裝Visual Studio
確保您的系統上安裝了 Visual Studio。您可以從微軟官方網站下載並安裝它。
### 2. 取得Aspose.Finance許可證
要利用 Aspose.Finance for .NET 的全部功能，您需要取得有效的授權。您可以從以下位置購買許可證[這裡](https://purchase.aspose.com/buy)或選擇用於測試目的的臨時許可證。
### 3. 下載並參考 Aspose.Finance for .NET
從下列位置下載 Aspose.Finance for .NET 函式庫[發布頁面](https://releases.aspose.com/finance/net/)並在您的 .NET 專案中引用它。
### 4. 取得文件和支持
請參閱[API文件](https://reference.aspose.com/finance/net/)有關使用 Aspose.Finance for .NET 的詳細資訊。此外，您可以在 Aspose.Finance 社群尋求協助[支援論壇](https://forum.aspose.com/c/finance/43).
## 導入命名空間
首先，我們將必要的命名空間匯入到您的 .NET 專案中：
## 第1步：新增Aspose.Finance命名空間
```csharp
using Aspose.Finance.Xbrl;
using System;
```
此命名空間包含用於處理 XBRL 文件和資料的類別和方法。
現在，讓我們將提供的範例分解為多個步驟，以了解如何使用 Aspose.Finance for .NET 新增對 XBRL 文件的架構參考。
## 第 1 步：定義來源目錄和輸出目錄
```csharp
//原始碼目錄
string sourceDir = "Your Source Directory";
//輸出目錄
string outputDir = "Your Output Directory";
```
代替`"Your Source Directory"`和`"Your Output Directory"`分別是來源目錄和輸出目錄的實際路徑。
## 第 2 步：建立 XBRL 文檔
```csharp
XbrlDocument document = new XbrlDocument();
```
這將建立 XBRL 文件的新實例。
## 步驟 3：存取 XBRL 實例
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
這將從文件中檢索 XBRL 實例的集合並向其中新增一個新實例。
## 第 4 步：新增架構參考
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
這將會新增對 XBRL 實例的架構參考。代替`"schema.xsd"`與您的架構文件的實際名稱，`"example"`具有合適的前綴，並且`"http://example.com/xbrl/taxonomy"`與目標命名空間 URI。
## 第 5 步：儲存文檔
```csharp
document.Save(outputDir + @"document2.xbrl");
```
這會將修改後的 XBRL 文件儲存到指定的輸出目錄。
## 結論
總之，Aspose.Finance for .NET 提供了一個強大的解決方案來處理 .NET 應用程式中的財務文件和資料。透過遵循本教學中概述的步驟，您可以輕鬆地將 Aspose.Finance 整合到您的專案中並有效地操作 XBRL 文件。
## 常見問題解答
 （常問的問題）
### 1. 我可以在沒有許可證的情況下使用Aspose.Finance for .NET嗎？
不需要，您需要有效的許可證才能使用 Aspose.Finance for .NET 的全部功能。但是，您可以獲得用於測試目的的臨時許可證。
### 2. Aspose.Finance適合建構會計軟體嗎？
是的，Aspose.Finance 提供了處理財務資料的全面功能，使其成為建立會計軟體和相關應用程式的理想選擇。
### 3. 在哪裡可以找到 Aspose.Finance 的支援？
您可以在官方支援論壇上向 Aspose.Finance 社群尋求協助。
### 4. 我可以自訂架構引用前綴嗎？
是的，在使用 Aspose.Finance for .NET 將架構參考新增至 XBRL 文件時，您可以選擇合適的前綴。
### 5. Aspose.Finance是否支援XBRL以外的其他財務格式？
是的，Aspose.Finance 支援各種金融格式和標準，能夠無縫整合到各種金融應用程式中。
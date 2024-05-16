---
title: 將單位新增至 XBRL 文檔
linktitle: 將單位新增至 XBRL 文檔
second_title: Aspose.Finance .NET API
description: 了解如何使用 Aspose.Finance for .NET 輕鬆地將單位新增至 XBRL 文件。立即增強您的財務資料處理能力！
type: docs
weight: 16
url: /zh-hant/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
歡迎來到 Aspose.Finance for .NET 的世界 - 您在 .NET 應用程式中進行高效財務文件操作的入口網站。無論您是建立會計軟體、財務分析工具或任何其他財務應用程序，Aspose.Finance for .NET 都為您提供了一套全面的功能來簡化您的開發流程。
## 先決條件
在我們深入研究利用 Aspose.Finance for .NET 的強大功能之前，我們先確保具備必要的先決條件：
### 1. Visual Studio安裝
確保您的系統上安裝了 Visual Studio。如果沒有，您可以從微軟官方網站下載並安裝。
### 2. 取得許可證
要釋放 Aspose.Finance for .NET 的全部潛力，您需要有效的許可證。您可以從以下位置購買許可證[這裡](https://purchase.aspose.com/buy)或選擇用於測試目的的臨時許可證。
### 3. 下載並參考 Aspose.Finance for .NET
從下列位置下載 Aspose.Finance for .NET 函式庫[發布頁面](https://releases.aspose.com/finance/net/)並在您的 .NET 專案中引用它。
### 4. 取得文件和支持
請參閱[文件](https://reference.aspose.com/finance/net/)有關使用 Aspose.Finance for .NET 的詳細資訊。此外，您可以在 Aspose.Finance 社群尋求協助[支援論壇](https://forum.aspose.com/c/finance/43).
## 導入命名空間
現在，讓我們將必要的命名空間匯入到您的 .NET 專案中：
## 第1步：新增Aspose.Finance命名空間
```csharp
using Aspose.Finance.Xbrl;
using System;
```
此命名空間包含處理 XBRL 文件和資料所必需的類別和方法。
讓我們將提供的範例分解為多個步驟，以了解如何使用 Aspose.Finance for .NET 將單元新增至 XBRL 文件。
## 第 1 步：定義輸出目錄
```csharp
//輸出目錄
string outputDir = "Your Output Directory";
```
代替`"Your Output Directory"`與所需輸出目錄的實際路徑。
## 第 2 步：建立 XBRL 文檔
```csharp
XbrlDocument document = new XbrlDocument();
```
這將初始化 XBRL 文件的新實例。
## 步驟 3：存取 XBRL 實例
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
這將從文件中檢索 XBRL 實例的集合並向其中新增一個新實例。
## 第 4 步：新增單位
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"))；
xbrlInstance.Units.Add(unit);
```
這將建立一個新的計量單位（在本例中為美元）並將其新增至 XBRL 實例。您可以根據需要調整貨幣代碼和命名空間 URI。
## 第 5 步：儲存文檔
```csharp
document.Save(outputDir + @"document4.xbrl");
```
這會將修改後的 XBRL 文件儲存到指定的輸出目錄。
## 結論
總之，Aspose.Finance for .NET 使開發人員能夠輕鬆地在其 .NET 應用程式中操作財務文件和資料。透過遵循本教學中概述的步驟，您可以將 Aspose.Finance for .NET 無縫整合到您的專案中並增強其財務處理能力。
## 常見問題解答
### 1. 我可以在沒有許可證的情況下使用Aspose.Finance for .NET嗎？
不需要，需要有效的許可證才能解鎖 Aspose.Finance for .NET 的全部功能。但是，臨時許可證可用於測試目的。
### 2. Aspose.Finance for .NET適合建構會計軟體嗎？
是的，Aspose.Finance for .NET 提供了專為建立會計軟體和相關財務應用程式而客製化的強大功能。
### 3. 在哪裡可以找到 Aspose.Finance for .NET 的支援？
您可以在支援論壇上向 Aspose.Finance 社群尋求協助。
### 4. 我可以自訂 XBRL 文件中的計量單位嗎？
是的，您可以使用 Aspose.Finance for .NET 建立自訂測量單位並將其新增至 XBRL 文件。
### 5. Aspose.Finance for .NET 支援多種貨幣嗎？
是的，Aspose.Finance for .NET 支援多種貨幣，允許進行多功能的財務資料處理。
---
title: 将项目添加到 XBRL 文档
linktitle: 将项目添加到 XBRL 文档
second_title: Aspose.Finance .NET API
description: 了解如何使用 Aspose.Finance for .NET 将项目添加到 XBRL 文档。简化 .NET 应用程序中的财务报告。#Aspose #Finance
type: docs
weight: 13
url: /zh/net/xbrl-file-creation/add-item-to-xbrl-document/
---
可扩展业务报告语言 (XBRL) 已成为财务报告的标准格式，可实现高效、准确的财务数据通信。Aspose.Finance for .NET 提供强大的功能，可在 .NET 应用程序中处理 XBRL 文档。在本教程中，我们将逐步介绍使用 Aspose.Finance for .NET 将项目添加到 XBRL 文档的步骤。
## 先决条件
在开始之前，请确保您满足以下先决条件：
### 1.安装 Aspose.Finance for .NET
如果尚未安装，请从以下位置下载并安装 Aspose.Finance for .NET：[官方网站](https://releases.aspose.com/finance/net/). 按照安装说明在您的 .NET 环境中设置库。
### 2. 设置开发环境
确保您拥有一个可用于 .NET 开发的开发环境。您需要一个兼容的 IDE（例如 Visual Studio）以及安装在系统上的 .NET 框架。
## 导入命名空间
首先，将必要的命名空间导入您的.NET 应用程序，以利用 Aspose.Finance for .NET 提供的功能。
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#现在让我们将示例代码分解为多个步骤：
## 步骤 1：定义源和输出目录
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
代替`"Your Source Directory"`和`"Your Output Directory"`分别为源目录和输出目录的路径。
## 步骤 2：创建 XBRL 文档和实例
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
初始化要使用的 XBRL 文档和实例。
## 步骤 3：添加架构引用
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://例如.com/xbrl/taxonomy”);
```
向 XBRL 实例添加架构引用，提供架构文件的路径并指定命名空间详细信息。
## 步骤 4：定义上下文和实体
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
为 XBRL 实例创建上下文和实体，指定期间和实体详细信息。
## 步骤 5：添加单位
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217”）；
xbrlInstance.Units.Add(unit);
```
为 XBRL 实例定义一个单元，指定度量限定名称。
## 步骤 6：添加商品
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
向 XBRL 实例添加一个项目，指定其概念、上下文、单位、精度和值。
## 步骤 7：保存文档
```csharp
document.Save(outputDir + @"document5.xbrl");
```
将 XBRL 文档保存到输出目录。
## 结论
将项目添加到 XBRL 文档对于准确表示财务数据至关重要。Aspose.Finance for .NET 通过提供全面的 API 来处理 .NET 应用程序中的 XBRL 文档，从而简化了此过程。
## 常见问题解答
### 我可以将 Aspose.Finance for .NET 与任何.NET 应用程序一起使用吗？
是的，Aspose.Finance for .NET 与任何 .NET 应用程序兼容，包括 ASP.NET、WinForms 和控制台应用程序。
### Aspose.Finance for .NET 可以免费使用吗？
 Aspose.Finance for .NET 是一个商业库。您可以下载免费试用版来评估其功能，也可以从以下网站购买许可证：[这里](https://purchase.aspose.com/buy).
### Aspose.Finance for .NET 除了支持 XBRL 之外还支持其他财务报告格式吗？
Aspose.Finance for .NET 主要侧重于 XBRL 相关功能。不过，Aspose 还提供其他库来处理不同的财务格式。
### 如何获得 Aspose.Finance for .NET 的支持？
您可以通过以下方式获得 Aspose.Finance for .NET 的支持[官方论坛](https://forum.aspose.com/c/finance/43)，您可以在此提出问题并与其他用户和支持人员互动。
### 我可以获得 Aspose.Finance for .NET 的临时许可证吗？
是的，Aspose.Finance for .NET 的临时许可证可用于测试目的。您可以获取一个[这里](https://purchase.aspose.com/temporary-license/).
---
title: 将单位添加到XBRL文档
linktitle: 将单位添加到XBRL文档
second_title: Aspose.Finance .NET API
description: 了解如何使用 Aspose.Finance for .NET 轻松将单位添加到 XBRL 文档。立即增强您的财务数据处理能力！
type: docs
weight: 16
url: /zh/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
欢迎来到 Aspose.Finance for .NET 的世界 - 您在 .NET 应用程序中高效处理财务文档的门户。无论您是构建会计软件、财务分析工具还是任何其他财务应用程序，Aspose.Finance for .NET 都为您提供了一套全面的功能来简化您的开发流程。
## 先决条件
在深入研究如何利用 Aspose.Finance for .NET 的强大功能之前，让我们先确保已满足必要的先决条件：
### 1.Visual Studio 安装
确保您的系统上已安装 Visual Studio。如果没有，您可以从 Microsoft 官方网站下载并安装它。
### 2. 获取许可证
要充分发挥 Aspose.Finance for .NET 的潜力，您需要有效的许可证。您可以从以下网站购买许可证[这里](https://purchase.aspose.com/buy)或者选择临时许可证以进行测试。
### 3.下载并引用Aspose.Finance for .NET
从以下位置下载 Aspose.Finance for .NET 库[发布页面](https://releases.aspose.com/finance/net/)并在您的.NET项目中引用它。
### 4. 访问文档和支持
请参阅[文档](https://reference.aspose.com/finance/net/)了解有关使用 Aspose.Finance for .NET 的详细信息。此外，您还可以在[支持论坛](https://forum.aspose.com/c/finance/43).
## 导入命名空间
现在，让我们将必要的命名空间导入到您的 .NET 项目中：
## 步骤 1：添加 Aspose.Finance 命名空间
```csharp
using Aspose.Finance.Xbrl;
using System;
```
该命名空间包含处理 XBRL 文档和数据所必需的类和方法。
让我们将提供的示例分解为多个步骤，以了解如何使用 Aspose.Finance for .NET 将单元添加到 XBRL 文档。
## 步骤 1：定义输出目录
```csharp
//输出目录
string outputDir = "Your Output Directory";
```
代替`"Your Output Directory"`使用您想要的输出目录的实际路径。
## 步骤 2：创建 XBRL 文档
```csharp
XbrlDocument document = new XbrlDocument();
```
这将初始化 XBRL 文档的新实例。
## 步骤 3：访问 XBRL 实例
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
这将从文档中检索 XBRL 实例集合并向其中添加新实例。
## 步骤 4：添加单位
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217”）；
xbrlInstance.Units.Add(unit);
```
这将创建一个新的计量单位（在本例中为美元）并将其添加到 XBRL 实例中。您可以根据需要调整货币代码和命名空间 URI。
## 步骤 5：保存文档
```csharp
document.Save(outputDir + @"document4.xbrl");
```
这会将修改后的 XBRL 文档保存到指定的输出目录。
## 结论
总之，Aspose.Finance for .NET 使开发人员能够轻松地在其 .NET 应用程序中操作财务文档和数据。通过遵循本教程中概述的步骤，您可以将 Aspose.Finance for .NET 无缝集成到您的项目中并增强其财务处理能力。
## 常见问题解答
### 1. 我可以在没有许可证的情况下使用 Aspose.Finance for .NET 吗？
不，需要有效的许可证才能解锁 Aspose.Finance for .NET 的全部功能。但是，临时许可证可用于测试目的。
### 2. Aspose.Finance for .NET 适合构建会计软件吗？
是的，Aspose.Finance for .NET 提供了专为构建会计软件和相关财务应用程序而定制的强大功能。
### 3. 在哪里可以找到对 Aspose.Finance for .NET 的支持？
您可以在支持论坛上向 Aspose.Finance 社区寻求帮助。
### 4. 我可以自定义XBRL文档中的计量单位吗？
是的，您可以使用 Aspose.Finance for .NET 创建并添加自定义计量单位到 XBRL 文档。
### 5. Aspose.Finance for .NET 支持多种货币吗？
是的，Aspose.Finance for .NET 支持多种货币，允许进行多种财务数据处理。
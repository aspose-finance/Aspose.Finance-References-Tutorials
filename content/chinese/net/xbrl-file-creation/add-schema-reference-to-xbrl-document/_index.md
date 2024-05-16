---
title: 将架构引用添加到 XBRL 文档
linktitle: 将架构引用添加到 XBRL 文档
second_title: Aspose.Finance .NET API
description: 了解如何使用 Aspose.Finance for .NET 将架构引用添加到 XBRL 文档。立即简化您的财务数据处理！
type: docs
weight: 15
url: /zh/net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## 介绍 Aspose.Finance for .NET
Aspose.Finance for .NET 是一个功能强大的库，提供全面的功能来处理和操作 .NET 应用程序中的财务文档和数据。无论您是构建会计软件、财务分析工具还是任何其他财务应用程序，Aspose.Finance for .NET 都提供广泛的功能来简化您的开发流程。
## 先决条件
在深入使用 Aspose.Finance for .NET 之前，请确保已设置以下先决条件：
### 1.安装 Visual Studio
确保您的系统上安装了 Visual Studio。您可以从 Microsoft 官方网站下载并安装它。
### 2.获取 Aspose.Finance 许可证
要充分利用 Aspose.Finance for .NET 的全部功能，您需要获得有效的许可证。您可以从以下位置购买许可证[这里](https://purchase.aspose.com/buy)或者选择临时许可证以进行测试。
### 3.下载并引用Aspose.Finance for .NET
从以下位置下载 Aspose.Finance for .NET 库[发布页面](https://releases.aspose.com/finance/net/)并在您的.NET项目中引用它。
### 4. 访问文档和支持
请参阅[API 文档](https://reference.aspose.com/finance/net/)有关使用 Aspose.Finance for .NET 的详细信息。此外，您还可以在[支持论坛](https://forum.aspose.com/c/finance/43).
## 导入命名空间
让我们首先将必要的命名空间导入到您的 .NET 项目中：
## 步骤 1：添加 Aspose.Finance 命名空间
```csharp
using Aspose.Finance.Xbrl;
using System;
```
该命名空间包含用于处理 XBRL 文档和数据的类和方法。
现在，让我们将提供的示例分解为多个步骤，以了解如何使用 Aspose.Finance for .NET 向 XBRL 文档添加模式引用。
## 步骤 1：定义源和输出目录
```csharp
//源目录
string sourceDir = "Your Source Directory";
//输出目录
string outputDir = "Your Output Directory";
```
代替`"Your Source Directory"`和`"Your Output Directory"`分别对应于源目录和输出目录的实际路径。
## 步骤 2：创建 XBRL 文档
```csharp
XbrlDocument document = new XbrlDocument();
```
这将创建 XBRL 文档的新实例。
## 步骤 3：访问 XBRL 实例
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
这将从文档中检索 XBRL 实例集合并向其中添加新实例。
## 步骤 4：添加架构引用
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://例如.com/xbrl/taxonomy”);
```
这将向 XBRL 实例添加架构引用。替换`"schema.xsd"`使用架构文件的实际名称，`"example"`加上合适的前缀，并且`"http://example.com/xbrl/taxonomy"`使用目标命名空间 URI。
## 步骤 5：保存文档
```csharp
document.Save(outputDir + @"document2.xbrl");
```
这会将修改后的 XBRL 文档保存到指定的输出目录。
## 结论
总之，Aspose.Finance for .NET 为处理 .NET 应用程序中的财务文档和数据提供了强大的解决方案。通过遵循本教程中概述的步骤，您可以轻松地将 Aspose.Finance 集成到您的项目中并有效地操作 XBRL 文档。
## 常见问题解答
 （经常问的问题）
### 1. 我可以在没有许可证的情况下使用 Aspose.Finance for .NET 吗？
不，您需要有效的许可证才能使用 Aspose.Finance for .NET 的全部功能。但是，您可以获取临时许可证以进行测试。
### 2. Aspose.Finance 适合构建会计软件吗？
是的，Aspose.Finance 提供了处理财务数据的全面功能，使其成为构建会计软件和相关应用程序的理想选择。
### 3. 在哪里可以找到对 Aspose.Finance 的支持？
您可以在官方支持论坛上向 Aspose.Finance 社区寻求帮助。
### 4.我可以自定义架构引用前缀吗？
是的，您可以在使用 Aspose.Finance for .NET 向 XBRL 文档添加架构引用时选择合适的前缀。
### 5. 除了XBRL之外，Aspose.Finance还支持其他财务格式吗？
是的，Aspose.Finance 支持各种财务格式和标准，能够无缝集成到各种财务应用程序中。
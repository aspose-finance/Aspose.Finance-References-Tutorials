---
title: 向 XBRL 文档添加上下文
linktitle: 向 XBRL 文档添加上下文
second_title: Aspose.Finance .NET API
description: 了解如何使用 Aspose.Finance 在 .NET 中向 XBRL 文档添加上下文，以简化财务报告。#Aspose #Finance #XBRL
type: docs
weight: 11
url: /zh/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## 介绍
在财务报告领域，XBRL（可扩展商业报告语言）在标准化商业信息交换方面发挥着关键作用。向 XBRL 文档添加上下文对于确保其所含数据的完整性和相关性至关重要。借助 Aspose.Finance for .NET，此过程变得精简而高效，使开发人员能够无缝地将上下文合并到他们的 XBRL 文档中。
## 先决条件
在深入学习本教程之前，请确保您已满足以下先决条件：
1. Aspose.Finance for .NET 库：从以下位置下载并安装 Aspose.Finance for .NET 库[发布](https://releases.aspose.com/finance/net/).
2. .NET 开发环境：确保您的机器上已设置可运行的 .NET 开发环境。
3. 对 C# 的基本了解：熟悉 C# 编程语言将有助于理解示例。
## 导入命名空间
在您的 C# 项目中，导入必要的命名空间以访问 Aspose.Finance for .NET 提供的功能：
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## 步骤 1：设置输出目录
在向 XBRL 文档添加上下文之前，请指定将保存修改后的文档的输出目录：
```csharp
string outputDir = "Your Output Directory";
```
代替`"Your Output Directory"`使用系统上所需的路径。
## 第 2 步：创建 XBRL 文档
实例化`XbrlDocument`使用 XBRL 文档的对象：
```csharp
XbrlDocument document = new XbrlDocument();
```
该对象代表将被操作的XBRL文档。
## 步骤 3：添加 XBRL 实例
向文档添加 XBRL 实例。每个实例包含特定报告期的数据：
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
此步骤初始化文档中的 XBRL 实例。
## 步骤 4：定义上下文、时间段和实体
为 XBRL 实例创建上下文期间和实体：
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
根据您的报告要求指定期间和实体详细信息。
## 步骤 5：创建上下文
使用上一步中定义的周期和实体构建上下文：
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
该上下文封装了时间和实体相关的信息。
## 步骤 6：向 XBRL 实例添加上下文
将上一步创建的上下文与XBRL实例关联起来：
```csharp
xbrlInstance.Contexts.Add(context);
```
此步骤将上下文链接到XBRL实例，为数据提供相关的上下文信息。
## 步骤 7：保存文档
将修改后的XBRL文档保存到指定的输出目录：
```csharp
document.Save(outputDir + @"document3.xbrl");
```
这将完成该过程，并保存添加上下文的 XBRL 文档。
## 结论
通过遵循这些步骤，您可以使用 Aspose.Finance for .NET 有效地向 XBRL 文档添加上下文。这提高了财务数据的清晰度和可用性，有助于进行准确的分析和报告。
## 常见问题解答
### Aspose.Finance for .NET 可以处理大型 XBRL 文档吗？
Aspose.Finance for .NET 经过优化，可以处理各种大小的 XBRL 文档，包括大型数据集。
### Aspose.Finance for .NET 有试用版吗？
是的，您可以从 Aspose 官方网站下载免费试用版。
### Aspose.Finance for .NET 除了支持 XBRL 之外还支持其他财务报告标准吗？
Aspose.Finance 主要专注于 XBRL 相关功能，但也提供对其他财务格式的支持。
### 我可以根据我的具体要求定制上下文信息吗？
当然，Aspose.Finance for .NET 提供了灵活性，可以定制上下文信息以满足您的需求。
### 在哪里可以找到有关 Aspose.Finance for .NET 的额外支持或资源？
您可以访问 Aspose.Finance 论坛寻求社区的帮助，或者浏览文档以获得全面的指导。
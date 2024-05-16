---
title: 将脚注链接添加到 XBRL 文档
linktitle: 将脚注链接添加到 XBRL 文档
second_title: Aspose.Finance .NET API
description: 了解如何使用 Aspose.Finance for .NET 将脚注链接添加到 XBRL 文档。轻松通过附加背景信息增强财务报告。
type: docs
weight: 12
url: /zh/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
在 XBRL 文档中添加脚注链接对于提供特定数据点的附加背景或解释至关重要。在本教程中，我们将使用 Aspose.Finance for .NET 逐步完成该过程。
## 先决条件
在开始之前，请确保您已满足以下先决条件：
1.  Aspose.Finance for .NET：确保您已在系统上安装了 Aspose.Finance for .NET。您可以从以下网址下载[这里](https://releases.aspose.com/finance/net/).
  
2. 开发环境：使用 .NET Framework 或 .NET Core 设置开发环境。
## 导入命名空间：
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## 步骤 1：设置源和输出目录
首先，指定源文件和输出文件的目录：
```csharp
//源目录
string sourceDir = "Your Source Directory";
//输出目录
string outputDir = "Your Output Directory";
```
## 步骤 2：创建 XBRL 文档和实例
初始化XBRL文档和实例：
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## 步骤 3：添加架构引用
向 XBRL 实例添加架构引用：
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://例如.com/xbrl/taxonomy”);
SchemaRef schema = schemaRefs[0];
```
## 步骤 4：定义上下文
定义 XBRL 实例的上下文：
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## 步骤 5：添加脚注链接
创建并添加脚注链接至 XBRL 实例：
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
## 步骤 6：保存文档
保存修改后的XBRL文档：
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## 结论
使用 Aspose.Finance for .NET 向 XBRL 文档添加脚注链接是一个简单的过程。按照本教程中概述的步骤，您可以将其他背景或解释无缝地纳入您的财务报告中。
## 常见问题解答
### 我可以向单个 XBRL 文档添加多个脚注链接吗？
是的，您可以为每个附加链接重复本教程中概述的步骤来添加多个脚注链接。
### Aspose.Finance for .NET 是否与 .NET Framework 和 .NET Core 兼容？
是的，Aspose.Finance for .NET 同时支持 .NET Framework 和 .NET Core 环境。
### 如何获取 Aspose.Finance for .NET 的临时许可证？
您可以从[这里](https://purchase.aspose.com/temporary-license/).
### Aspose.Finance for .NET 是否提供对 XBRL 验证的支持？
是的，Aspose.Finance for .NET 提供对 XBRL 验证的全面支持，以确保符合行业标准。
### 在哪里可以找到有关 Aspose.Finance for .NET 的更多资源和支持？
您可以访问[Aspose.Finance for .NET 论坛](https://forum.aspose.com/c/finance/43)获取支持并访问文档[这里](https://reference.aspose.com/finance/net/).
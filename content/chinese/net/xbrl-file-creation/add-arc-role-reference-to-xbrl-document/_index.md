---
title: 将 ARC 角色引用添加到 XBRL 文档
linktitle: 将 ARC 角色引用添加到 XBRL 文档
second_title: Aspose.Finance .NET API
description: 了解如何使用 Aspose.Finance for .NET 高效地操作 XBRL 文档。通过分步指导轻松添加 ARC 角色引用。
type: docs
weight: 10
url: /zh/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## 介绍
在财务数据管理和报告领域，可扩展业务报告语言 (XBRL) 发挥着至关重要的作用。它标准化了财务信息的沟通和交换方式，确保了一致性、准确性和效率。但是，操作 XBRL 文档（尤其是在合并特定角色和引用时）需要对底层机制有细致的了解。本教程重点介绍一项这样的任务：使用 Aspose.Finance for .NET 将 ARC 角色引用添加到 XBRL 文档。
## 先决条件
在深入学习本教程之前，请确保您满足以下先决条件：
### 环境设置
1. 安装 Aspose.Finance for .NET：从以下位置下载并安装 Aspose.Finance for .NET 库[发布](https://releases.aspose.com/finance/net/).
   
2. 开发环境：使用 Visual Studio 或任何其他首选 IDE 设置您的开发环境。
## 导入命名空间
确保在 C# 代码中导入必要的命名空间：
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## 步骤 1：定义源和输出目录
继续之前，请分别指定 XBRL 文件所在的源目录和保存的输出目录。
```csharp
//源目录
string sourceDir = "Your Source Directory";
//输出目录
string outputDir = "Your Output Directory";
```
## 步骤 2：创建 XBRL 文档
实例化`XbrlDocument`对象来处理 XBRL 数据。
```csharp
XbrlDocument document = new XbrlDocument();
```
## 步骤 3：访问 XbrlInstance 集合
访问文档内的 XBRL 实例集合。
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## 步骤 4：添加 XbrlInstance
将新的 XBRL 实例添加到集合中。
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## 步骤 5：添加架构引用
在 XBRL 实例中包含架构引用，指定源目录、命名空间前缀和 URI。
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://例如.com/xbrl/taxonomy”);
```
## 步骤 6：检索 ArcroleType
检索`ArcroleType`基于特定的 URI。
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test”);
```
## 步骤 7：添加 ArcroleReference
如果`ArcroleType`找到后，创建一个`ArcroleReference`并将其添加到XBRL实例的arcrole引用中。
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## 步骤 8：保存文档
将修改后的XBRL文档保存到指定的输出目录。
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## 结论
在本教程中，我们探讨了如何使用 Aspose.Finance for .NET 将 ARC 角色引用添加到 XBRL 文档。通过遵循这些分步说明并利用 Aspose.Finance 的功能，您可以有效地管理和操作 XBRL 数据以满足您的特定要求。
## 常见问题解答
### 什么是 XBRL？
XBRL 代表可扩展商业报告语言，是一种用于商业和财务数据电子通信的标准化语言。
### XBRL 为何如此重要？
XBRL确保财务信息交换和分析的一致性、准确性和效率，使监管机构、分析师和企业受益。
### Aspose.Finance 可以处理复杂的 XBRL 任务吗？
是的，Aspose.Finance 提供了处理 XBRL 文档的强大功能，包括处理角色引用和分类管理等复杂任务。
### Aspose.Finance 是否与其他.NET 库兼容？
是的，Aspose.Finance 与其他.NET 库无缝集成，为财务数据处理和报告提供广泛的支持。
### 在哪里可以找到对 Aspose.Finance 的额外支持？
如需更多支持，请访问[Aspose.Finance 支持页面](https://forum.aspose.com/c/finance/43).
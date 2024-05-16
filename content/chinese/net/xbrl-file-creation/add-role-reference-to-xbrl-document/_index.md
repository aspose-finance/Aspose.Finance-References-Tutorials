---
title: 将角色引用添加到 XBRL 文档
linktitle: 将角色引用添加到 XBRL 文档
second_title: Aspose.Finance .NET API
description: 了解如何使用 Aspose.Finance for .NET 将角色引用添加到 XBRL 文档。通过本教程简化 .NET 应用程序中的财务报告。
type: docs
weight: 14
url: /zh/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL（可扩展业务报告语言）已成为交换业务信息的标准，尤其是在财务报告中。Aspose.Finance for .NET 简化了 .NET 应用程序中使用 XBRL 文档的过程。本教程将指导您完成使用 Aspose.Finance for .NET 向 XBRL 文档添加角色引用的过程。
## 先决条件
在开始之前，请确保您满足以下先决条件：
### 1.安装 Aspose.Finance for .NET
确保在开发环境中安装了 Aspose.Finance for .NET。如果尚未安装，请从[发布](https://releases.aspose.com/finance/net/)并按照安装说明进行操作。
### 2. 设置开发环境
确保您拥有一个可用于 .NET 开发的开发环境。这包括兼容的 IDE（例如 Visual Studio）和安装在您系统上的 .NET 框架。
## 导入命名空间
首先将必要的命名空间导入您的.NET 应用程序，以访问 Aspose.Finance for .NET 提供的功能。
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## 步骤 4：检索角色类型并添加角色引用
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1”);
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
使用其 URI 检索角色类型并向 XBRL 实例添加角色引用。
## 步骤 5：保存文档
```csharp
document.Save(outputDir + @"document7.xbrl");
```
将 XBRL 文档保存到输出目录。
## 结论
向 XBRL 文档添加角色引用对于定义文档中各种元素的角色至关重要。Aspose.Finance for .NET 提供了一种完成此任务的简单方法，使开发人员能够在其 .NET 应用程序中高效地处理 XBRL 文档。
## 常见问题解答
### 我可以将 Aspose.Finance for .NET 与任何.NET 应用程序一起使用吗？
是的，Aspose.Finance for .NET 与任何 .NET 应用程序兼容，包括 ASP.NET、WinForms 和控制台应用程序。
### Aspose.Finance for .NET 可以免费使用吗？
 Aspose.Finance for .NET 是一个商业库。您可以下载免费试用版来评估其功能，也可以从以下网站购买许可证：[这里](https://purchase.aspose.com/buy).
### Aspose.Finance for .NET 除了支持 XBRL 之外还支持其他财务报告格式吗？
Aspose.Finance for .NET 主要侧重于 XBRL 相关功能。不过，Aspose 还提供其他库来处理不同的财务格式。
### 如何获得 Aspose.Finance for .NET 的支持？
您可以通过以下方式获得 Aspose.Finance for .NET 的支持[论坛](https://forum.aspose.com/c/finance/43)，您可以在此提出问题并与其他用户和支持人员互动。
### 我可以获得 Aspose.Finance for .NET 的临时许可证吗？
是的，Aspose.Finance for .NET 的临时许可证可用于测试目的。您可以获取一个[这里](https://purchase.aspose.com/temporary-license/).
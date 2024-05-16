---
title: Add Role Reference to XBRL Document
linktitle: Add Role Reference to XBRL Document
second_title: Aspose.Finance .NET API
description: Learn how to add role references to XBRL documents using Aspose.Finance for .NET. Simplify financial reporting in your .NET applications with this tutorial.
type: docs
weight: 14
url: /net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (eXtensible Business Reporting Language) has become a standard for exchanging business information, particularly in financial reporting. Aspose.Finance for .NET simplifies working with XBRL documents in .NET applications. This tutorial will guide you through the process of adding a role reference to an XBRL document using Aspose.Finance for .NET.
## Prerequisites
Before we get started, ensure you have the following prerequisites:
### 1. Install Aspose.Finance for .NET
Make sure you have Aspose.Finance for .NET installed in your development environment. If you haven't already, download it from the [releases](https://releases.aspose.com/finance/net/) and follow the installation instructions.
### 2. Set Up Your Development Environment
Ensure you have a working development environment for .NET development. This includes a compatible IDE such as Visual Studio and the .NET framework installed on your system.
## Import Namespaces
Begin by importing the necessary namespaces into your .NET application to access the functionality provided by Aspose.Finance for .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
## Step 1: Define Source and Output Directories
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
Replace `"Your Source Directory"` and `"Your Output Directory"` with the paths to your source and output directories, respectively.
## Step 2: Create an XBRL Document and Instance
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Initialize an XBRL document and instance to work with.
## Step 3: Add Schema Reference
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
Add a schema reference to the XBRL instance, providing the path to the schema file and specifying namespace details.
## Step 4: Retrieve Role Type and Add Role Reference
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
Retrieve the role type using its URI and add a role reference to the XBRL instance.
## Step 5: Save Document
```csharp
document.Save(outputDir + @"document7.xbrl");
```
Save the XBRL document to the output directory.
## Conclusion
Adding role references to XBRL documents is crucial for defining the roles of various elements within the document. Aspose.Finance for .NET provides a straightforward way to accomplish this task, empowering developers to efficiently work with XBRL documents in their .NET applications.
## FAQs
### Can I use Aspose.Finance for .NET with any .NET application?
Yes, Aspose.Finance for .NET is compatible with any .NET application, including ASP.NET, WinForms, and Console applications.
### Is Aspose.Finance for .NET free to use?
Aspose.Finance for .NET is a commercial library. You can download a free trial version to evaluate its features, and licenses can be purchased from [here](https://purchase.aspose.com/buy).
### Does Aspose.Finance for .NET support other financial reporting formats besides XBRL?
Aspose.Finance for .NET primarily focuses on XBRL-related functionality. However, Aspose offers other libraries for working with different financial formats.
### How can I get support for Aspose.Finance for .NET?
You can get support for Aspose.Finance for .NET through the [forum](https://forum.aspose.com/c/finance/43), where you can ask questions and interact with other users and support staff.
### Can I obtain a temporary license for Aspose.Finance for .NET?
Yes, temporary licenses for Aspose.Finance for .NET are available for testing purposes. You can obtain one [here](https://purchase.aspose.com/temporary-license/).

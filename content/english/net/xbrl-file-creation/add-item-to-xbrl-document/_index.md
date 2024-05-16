---
title: Add Item to XBRL Document
linktitle: Add Item to XBRL Document
second_title: Aspose.Finance .NET API
description: Learn how to add items to XBRL documents using Aspose.Finance for .NET. Simplify financial reporting in your .NET applications. #Aspose #Finance
type: docs
weight: 13
url: /net/xbrl-file-creation/add-item-to-xbrl-document/
---
Extensible Business Reporting Language (XBRL) has become a standard format for financial reporting, enabling efficient and accurate communication of financial data. Aspose.Finance for .NET provides robust functionality to work with XBRL documents in your .NET applications. In this tutorial, we'll walk through the steps to add an item to an XBRL document using Aspose.Finance for .NET.
## Prerequisites
Before we begin, ensure you have the following prerequisites:
### 1. Install Aspose.Finance for .NET
If you haven't already, download and install Aspose.Finance for .NET from the [official website](https://releases.aspose.com/finance/net/). Follow the installation instructions to set up the library in your .NET environment.
### 2. Set Up Your Development Environment
Make sure you have a working development environment for .NET development. You'll need a compatible IDE such as Visual Studio, along with the .NET framework installed on your system.
## Import Namespaces
First, import the necessary namespaces into your .NET application to utilize the functionality provided by Aspose.Finance for .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Now let's break down the example code into multiple steps:
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
## Step 4: Define Context and Entity
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
Create a context and entity for the XBRL instance, specifying the period and entity details.
## Step 5: Add Unit
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Define a unit for the XBRL instance, specifying the measure qualified names.
## Step 6: Add Item
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
Add an item to the XBRL instance, specifying its concept, context, unit, precision, and value.
## Step 7: Save Document
```csharp
document.Save(outputDir + @"document5.xbrl");
```
Save the XBRL document to the output directory.
## Conclusion
Adding items to an XBRL document is essential for accurately representing financial data. Aspose.Finance for .NET simplifies this process by providing a comprehensive API to work with XBRL documents in .NET applications.
## FAQs
### Can I use Aspose.Finance for .NET with any .NET application?
Yes, Aspose.Finance for .NET is compatible with any .NET application, including ASP.NET, WinForms, and Console applications.
### Is Aspose.Finance for .NET free to use?
Aspose.Finance for .NET is a commercial library. You can download a free trial version to evaluate its features, and licenses can be purchased from [here](https://purchase.aspose.com/buy).
### Does Aspose.Finance for .NET support other financial reporting formats besides XBRL?
Aspose.Finance for .NET primarily focuses on XBRL-related functionality. However, Aspose offers other libraries for working with different financial formats.
### How can I get support for Aspose.Finance for .NET?
You can get support for Aspose.Finance for .NET through the [official forum](https://forum.aspose.com/c/finance/43), where you can ask questions and interact with other users and support staff.
### Can I obtain a temporary license for Aspose.Finance for .NET?
Yes, temporary licenses for Aspose.Finance for .NET are available for testing purposes. You can obtain one [here](https://purchase.aspose.com/temporary-license/).

---
title: Add ARC Role Reference to XBRL Document
linktitle: Add ARC Role Reference to XBRL Document
second_title: Aspose.Finance .NET API
description: Learn how to efficiently manipulate XBRL documents using Aspose.Finance for .NET. Add ARC Role References effortlessly with step-by-step guidance.
type: docs
weight: 10
url: /net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## Introduction
In the world of financial data management and reporting, the eXtensible Business Reporting Language (XBRL) plays a crucial role. It standardizes the way financial information is communicated and exchanged, ensuring consistency, accuracy, and efficiency. However, manipulating XBRL documents, especially when incorporating specific roles and references, requires a nuanced understanding of the underlying mechanisms. This tutorial focuses on one such task: adding an ARC Role Reference to an XBRL document using Aspose.Finance for .NET.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites:
### Environment Setup
1. Install Aspose.Finance for .NET: Download and install the Aspose.Finance for .NET library from the [releases](https://releases.aspose.com/finance/net/).
   
2. Development Environment: Set up your development environment with Visual Studio or any other preferred IDE.
## Import Namespaces
Make sure to import the necessary namespaces in your C# code:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Step 1: Define Source and Output Directories
Before proceeding, specify the source and output directories where your XBRL files will be located and saved, respectively.
```csharp
// Source directory
string sourceDir = "Your Source Directory";
// Output directory
string outputDir = "Your Output Directory";
```
## Step 2: Create an XBRL Document
Instantiate an `XbrlDocument` object to work with XBRL data.
```csharp
XbrlDocument document = new XbrlDocument();
```
## Step 3: Access XbrlInstance Collection
Access the collection of XBRL instances within the document.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## Step 4: Add XbrlInstance
Add a new XBRL instance to the collection.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Step 5: Add Schema Reference
Include a schema reference in the XBRL instance, specifying the source directory, namespace prefix, and URI.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
## Step 6: Retrieve ArcroleType
Retrieve the `ArcroleType` based on a specific URI.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## Step 7: Add ArcroleReference
If the `ArcroleType` is found, create an `ArcroleReference` and add it to the XBRL instance's arcrole references.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## Step 8: Save the Document
Save the modified XBRL document to the specified output directory.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## Conclusion
In this tutorial, we've explored how to add an ARC Role Reference to an XBRL document using Aspose.Finance for .NET. By following these step-by-step instructions and leveraging the capabilities of Aspose.Finance, you can efficiently manage and manipulate XBRL data to meet your specific requirements.
## FAQs
### What is XBRL?
XBRL stands for eXtensible Business Reporting Language, a standardized language for the electronic communication of business and financial data.
### Why is XBRL important?
XBRL ensures consistency, accuracy, and efficiency in the exchange and analysis of financial information, benefiting regulators, analysts, and businesses.
### Can Aspose.Finance handle complex XBRL tasks?
Yes, Aspose.Finance offers robust functionality for working with XBRL documents, including handling complex tasks such as role references and taxonomy management.
### Is Aspose.Finance compatible with other .NET libraries?
Yes, Aspose.Finance seamlessly integrates with other .NET libraries, providing extensive support for financial data manipulation and reporting.
### Where can I find additional support for Aspose.Finance?
For additional support visit the [Aspose.Finance support page](https://forum.aspose.com/c/finance/43).

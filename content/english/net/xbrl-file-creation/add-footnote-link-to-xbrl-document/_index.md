---
title: Add Footnote Link to XBRL Document
linktitle: Add Footnote Link to XBRL Document
second_title: Aspose.Finance .NET API
description: Learn how to add footnote links to XBRL documents using Aspose.Finance for .NET. Enhance financial reports with additional context effortlessly.
type: docs
weight: 12
url: /net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
Adding a footnote link to an XBRL document is crucial for providing additional context or explanations for specific data points. In this tutorial, we'll walk through the process step by step using Aspose.Finance for .NET.
## Prerequisites
Before we begin, ensure you have the following prerequisites in place:
1. Aspose.Finance for .NET: Make sure you have installed Aspose.Finance for .NET on your system. You can download it from [here](https://releases.aspose.com/finance/net/).
  
2. Development Environment: Have a development environment set up with a .NET Framework or .NET Core.
## Import Namespaces:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Step 1: Set Source and Output Directories
First, specify the directories for the source and output files:
```csharp
// Source directory
string sourceDir = "Your Source Directory";
// Output directory
string outputDir = "Your Output Directory";
```
## Step 2: Create an XBRL Document and Instance
Initialize an XBRL document and instance:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Step 3: Add Schema References
Add schema references to the XBRL instance:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## Step 4: Define Context
Define the context for the XBRL instance:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## Step 5: Add Footnote Link
Create and add a footnote link to the XBRL instance:
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
## Step 6: Save the Document
Save the modified XBRL document:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## Conclusion
Adding a footnote link to an XBRL document is a straightforward process with Aspose.Finance for .NET. By following the steps outlined in this tutorial, you can seamlessly incorporate additional context or explanations into your financial reports.
## FAQs
### Can I add multiple footnote links to a single XBRL document?
Yes, you can add multiple footnote links by repeating the steps outlined in this tutorial for each additional link.
### Is Aspose.Finance for .NET compatible with both .NET Framework and .NET Core?
Yes, Aspose.Finance for .NET supports both .NET Framework and .NET Core environments.
### How can I obtain a temporary license for Aspose.Finance for .NET?
You can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/).
### Does Aspose.Finance for .NET provide support for XBRL validation?
Yes, Aspose.Finance for .NET offers comprehensive support for XBRL validation to ensure compliance with industry standards.
### Where can I find additional resources and support for Aspose.Finance for .NET?
You can visit the [Aspose.Finance for .NET forum](https://forum.aspose.com/c/finance/43) for support and access documentation [here](https://reference.aspose.com/finance/net/).
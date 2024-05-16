---
title: Add Context to XBRL Document
linktitle: Add Context to XBRL Document
second_title: Aspose.Finance .NET API
description: Learn how to add context to XBRL documents in .NET using Aspose.Finance for streamlined financial reporting. #Aspose #Finance #XBRL
type: docs
weight: 11
url: /net/xbrl-file-creation/add-context-to-xbrl-document/
---
## Introduction
In the realm of financial reporting, XBRL (eXtensible Business Reporting Language) plays a pivotal role in standardizing the exchange of business information. Adding context to XBRL documents is crucial for ensuring the integrity and relevance of the data they contain. With Aspose.Finance for .NET, this process becomes streamlined and efficient, allowing developers to seamlessly incorporate context into their XBRL documents.
## Prerequisites
Before diving into the tutorial, ensure that you have the following prerequisites:
1. Aspose.Finance for .NET Library: Download and install the Aspose.Finance for .NET library from the [releases](https://releases.aspose.com/finance/net/).
2. .NET Development Environment: Make sure you have a working .NET development environment set up on your machine.
3. Basic Understanding of C#: Familiarity with C# programming language will be helpful in following along with the examples.
## Import Namespaces
In your C# project, import the necessary namespaces to access the functionality provided by Aspose.Finance for .NET:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Step 1: Set Output Directory
Before adding context to the XBRL document, specify the output directory where the modified document will be saved:
```csharp
string outputDir = "Your Output Directory";
```
Replace `"Your Output Directory"` with the desired path on your system.
## Step 2: Create XBRL Document
Instantiate an `XbrlDocument` object to work with XBRL documents:
```csharp
XbrlDocument document = new XbrlDocument();
```
This object represents the XBRL document that will be manipulated.
## Step 3: Add XBRL Instance
Add an XBRL instance to the document. Each instance contains the data for a specific reporting period:
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
This step initializes an XBRL instance within the document.
## Step 4: Define Context Period and Entity
Create a context period and entity for the XBRL instance:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
Specify the period and entity details according to your reporting requirements.
## Step 5: Create Context
Construct a context using the period and entity defined in the previous step:
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
This context encapsulates the temporal and entity-related information.
## Step 6: Add Context to XBRL Instance
Associate the context created in the previous step with the XBRL instance:
```csharp
xbrlInstance.Contexts.Add(context);
```
This step links the context to the XBRL instance, providing relevant contextual information to the data.
## Step 7: Save the Document
Save the modified XBRL document to the specified output directory:
```csharp
document.Save(outputDir + @"document3.xbrl");
```
This finalizes the process, saving the XBRL document with the added context.
## Conclusion
By following these steps, you can effectively add context to XBRL documents using Aspose.Finance for .NET. This enhances the clarity and usability of financial data, facilitating accurate analysis and reporting.
## FAQs
### Can Aspose.Finance for .NET handle large XBRL documents?
Aspose.Finance for .NET is optimized to handle XBRL documents of varying sizes, including large datasets.
### Is there a trial version available for Aspose.Finance for .NET?
Yes, you can download a free trial version from the official Aspose website.
### Does Aspose.Finance for .NET support other financial reporting standards besides XBRL?
Aspose.Finance primarily focuses on XBRL-related functionalities but also provides support for other financial formats.
### Can I customize the context information according to my specific requirements?
Absolutely, Aspose.Finance for .NET offers flexibility for customizing context information to suit your needs.
### Where can I find additional support or resources for Aspose.Finance for .NET?
You can visit the Aspose.Finance forum for assistance from the community or explore the documentation for comprehensive guidance.

---
title: Add Schema Reference to XBRL Document
linktitle: Add Schema Reference to XBRL Document
second_title: Aspose.Finance .NET API
description: Learn how to add schema references to XBRL documents using Aspose.Finance for .NET. Streamline your financial data processing today!
type: docs
weight: 15
url: /net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## Introducing Aspose.Finance for .NET
Aspose.Finance for .NET is a powerful library that provides comprehensive functionalities for processing and manipulating financial documents and data within .NET applications. Whether you're building accounting software, financial analysis tools, or any other financial application, Aspose.Finance for .NET offers a wide range of features to streamline your development process.
## Prerequisites
Before diving into using Aspose.Finance for .NET, make sure you have the following prerequisites set up:
### 1. Install Visual Studio
Ensure that you have Visual Studio installed on your system. You can download and install it from the official Microsoft website.
### 2. Obtain an Aspose.Finance License
To utilize the full capabilities of Aspose.Finance for .NET, you need to acquire a valid license. You can purchase a license from [here](https://purchase.aspose.com/buy) or opt for a temporary license for testing purposes.
### 3. Download and Reference Aspose.Finance for .NET
Download the Aspose.Finance for .NET library from the [releases page](https://releases.aspose.com/finance/net/) and reference it in your .NET project.
### 4. Access Documentation and Support
Refer to the [API documentation](https://reference.aspose.com/finance/net/) for detailed information on using Aspose.Finance for .NET. Additionally, you can seek assistance from the Aspose.Finance community on the [support forum](https://forum.aspose.com/c/finance/43).
## Importing Namespaces
Let's start by importing the necessary namespaces into your .NET project:
## Step 1: Add Aspose.Finance Namespace
```csharp
using Aspose.Finance.Xbrl;
using System;
```
This namespace contains classes and methods for working with XBRL documents and data.
Now, let's break down the provided example into multiple steps to understand how to add a schema reference to an XBRL document using Aspose.Finance for .NET.
## Step 1: Define Source and Output Directories
```csharp
// Source directory
string sourceDir = "Your Source Directory";
// Output directory
string outputDir = "Your Output Directory";
```
Replace `"Your Source Directory"` and `"Your Output Directory"` with the actual paths to your source and output directories respectively.
## Step 2: Create an XBRL Document
```csharp
XbrlDocument document = new XbrlDocument();
```
This creates a new instance of the XBRL document.
## Step 3: Access XBRL Instances
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
This retrieves the collection of XBRL instances from the document and adds a new instance to it.
## Step 4: Add Schema Reference
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
This adds a schema reference to the XBRL instance. Replace `"schema.xsd"` with the actual name of your schema file, `"example"` with a suitable prefix, and `"http://example.com/xbrl/taxonomy"` with the target namespace URI.
## Step 5: Save the Document
```csharp
document.Save(outputDir + @"document2.xbrl");
```
This saves the modified XBRL document to the specified output directory.
## Conclusion
In conclusion, Aspose.Finance for .NET offers a robust solution for handling financial documents and data in .NET applications. By following the steps outlined in this tutorial, you can easily integrate Aspose.Finance into your projects and efficiently manipulate XBRL documents.
## FAQs
 (Frequently Asked Questions)
### 1. Can I use Aspose.Finance for .NET without a license?
No, you need a valid license to utilize the full features of Aspose.Finance for .NET. However, you can obtain a temporary license for testing purposes.
### 2. Is Aspose.Finance suitable for building accounting software?
Yes, Aspose.Finance provides comprehensive functionalities for processing financial data, making it ideal for building accounting software and related applications.
### 3. Where can I find support for Aspose.Finance?
You can seek assistance from the Aspose.Finance community on the official support forum.
### 4. Can I customize the schema reference prefix?
Yes, you can choose a suitable prefix when adding a schema reference to an XBRL document using Aspose.Finance for .NET.
### 5. Does Aspose.Finance support other financial formats besides XBRL?
Yes, Aspose.Finance supports various financial formats and standards, enabling seamless integration into diverse financial applications.

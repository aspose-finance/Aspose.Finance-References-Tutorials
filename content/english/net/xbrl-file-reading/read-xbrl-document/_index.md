---
title: Read XBRL Document
linktitle: Read XBRL Document
second_title: Aspose.Finance .NET API
description: Learn how to read XBRL documents in .NET using Aspose.Finance. Enhance your financial data processing capabilities effortlessly. #Aspose #Finance #XBRL
type: docs
weight: 11
url: /net/xbrl-file-reading/read-xbrl-document/
---
## Introduction
Aspose.Finance for .NET is a robust financial software development tool that empowers developers to efficiently manage financial data within their .NET applications. One of its key features is the ability to read XBRL (eXtensible Business Reporting Language) documents seamlessly. In this comprehensive guide, we'll walk through the process of reading XBRL documents using Aspose.Finance for .NET. By the end of this tutorial, you'll have a solid understanding of how to leverage this functionality to enhance your financial data processing capabilities.
## Prerequisites
Before we dive into the tutorial, let's ensure you have everything you need:
### .NET Development Environment
First and foremost, make sure you have a .NET development environment set up on your machine. If you haven't already, you can download and install the latest version of the .NET SDK from the official Microsoft website.
### Aspose.Finance for .NET
To follow along with this tutorial, you'll need to have Aspose.Finance for .NET installed in your development environment. You can download the library from the official download link provided below:
[Download Aspose.Finance for .NET](https://releases.aspose.com/finance/net/)
### XBRL Document
Prepare an XBRL document that you intend to read using Aspose.Finance for .NET. Ensure that you have the file path ready for referencing in your code.
## Import Namespaces
Let's start by importing the necessary namespaces into your .NET project to access the functionalities of Aspose.Finance. Follow these step-by-step instructions:
## Step 1: Open Your .NET Project
Launch your .NET project in your preferred Integrated Development Environment (IDE), such as Visual Studio.
## Step 2: Add Aspose.Finance Reference
Add a reference to Aspose.Finance for .NET in your project. You can achieve this by either downloading the library and referencing it locally or using NuGet Package Manager to install it directly into your project.
## Step 3: Import Namespaces
Now, import the required namespaces at the beginning of your code file. These namespaces provide access to the classes and methods needed for working with XBRL documents.
```csharp
using Aspose.Finance.Xbrl;
using System;
using System.Collections.Generic;
```
## Read XBRL Document
Now that we've set up our environment and imported the necessary namespaces, let's dive into the process of reading an XBRL document using Aspose.Finance for .NET. Follow these step-by-step instructions:
## Step 1: Define Source Directory
Start by defining the directory path where your XBRL document is located. Replace `"Your Source Directory"` with the actual path to your document.
```csharp
string sourceDir = "Your Source Directory";
```
## Step 2: Create XbrlDocument Object
Next, create an `XbrlDocument` object by providing the path to your XBRL document.
```csharp
XbrlDocument document = new XbrlDocument(sourceDir + @"IdScopeContextPeriodStartAfterEnd.xml");
```
## Step 3: Access XBRL Instances
Access the XBRL instances from the document using the `XbrlInstances` property.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[0];
```
## Step 4: Extract Facts, Schema References, Contexts, and Units
Retrieve facts, schema references, contexts, and units from the XBRL instance.
```csharp
List<Fact> facts = xbrlInstance.Facts;
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
List<Context> contexts = xbrlInstance.Contexts;
List<Unit> units = xbrlInstance.Units;
```
## Step 5: Display Success Message
Inform the user that the XBRL document has been read successfully.
```csharp
Console.WriteLine("ReadXbrlDocument executed successfully.");
```
By following these steps, you've successfully read an XBRL document using Aspose.Finance for .NET.
## Conclusion
In this tutorial, we've covered the process of reading XBRL documents using Aspose.Finance for .NET. By leveraging the step-by-step guide provided, you can efficiently handle XBRL documents within your .NET applications, enhancing your financial data processing capabilities.
## FAQs
### Is Aspose.Finance for .NET compatible with all versions of .NET?
Yes, Aspose.Finance for .NET is designed to be compatible with all versions of the .NET framework, ensuring seamless integration into your projects.
### Can I use Aspose.Finance for commercial projects?
Absolutely! Aspose.Finance for .NET can be used for both personal and commercial projects. Simply purchase a license to unlock its full potential.
### Does Aspose.Finance support other document formats besides XBRL?
Yes, Aspose.Finance provides support for various financial document formats, offering flexibility and versatility in handling financial data.
### Is technical support available for Aspose.Finance users?
Certainly! Aspose offers dedicated technical support for its products, including Aspose.Finance. You can access support through the official support forum.
### Can I try Aspose.Finance before making a purchase?
Of course! Aspose offers a free trial version of Aspose.Finance, allowing you to explore its features and capabilities before making a commitment.

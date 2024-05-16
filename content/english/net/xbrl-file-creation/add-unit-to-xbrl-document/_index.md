---
title: Add Unit to XBRL Document
linktitle: Add Unit to XBRL Document
second_title: Aspose.Finance .NET API
description: Learn how to add units to XBRL documents effortlessly with Aspose.Finance for .NET. Enhance your financial data processing capabilities today!
type: docs
weight: 16
url: /net/xbrl-file-creation/add-unit-to-xbrl-document/
---
Welcome to the world of Aspose.Finance for .NET - your gateway to efficient financial document manipulation within .NET applications. Whether you're building accounting software, financial analysis tools, or any other financial application, Aspose.Finance for .NET equips you with a comprehensive set of features to streamline your development process.
## Prerequisites
Before we delve into harnessing the power of Aspose.Finance for .NET, let's ensure we have the necessary prerequisites in place:
### 1. Visual Studio Installation
Ensure you have Visual Studio installed on your system. If not, you can download and install it from the official Microsoft website.
### 2. Obtain a License
To unlock the full potential of Aspose.Finance for .NET, you need a valid license. You can purchase a license from [here](https://purchase.aspose.com/buy) or opt for a temporary license for testing purposes.
### 3. Download and Reference Aspose.Finance for .NET
Download the Aspose.Finance for .NET library from the [releases page](https://releases.aspose.com/finance/net/) and reference it in your .NET project.
### 4. Access Documentation and Support
Refer to the [documentation](https://reference.aspose.com/finance/net/) for detailed information on utilizing Aspose.Finance for .NET. Additionally, you can seek assistance from the Aspose.Finance community on the [support forum](https://forum.aspose.com/c/finance/43).
## Importing Namespaces
Now, let's import the necessary namespaces into your .NET project:
## Step 1: Add Aspose.Finance Namespace
```csharp
using Aspose.Finance.Xbrl;
using System;
```
This namespace contains classes and methods essential for working with XBRL documents and data.
Let's break down the provided example into multiple steps to understand how to add a unit to an XBRL document using Aspose.Finance for .NET.
## Step 1: Define Output Directory
```csharp
// Output directory
string outputDir = "Your Output Directory";
```
Replace `"Your Output Directory"` with the actual path to your desired output directory.
## Step 2: Create an XBRL Document
```csharp
XbrlDocument document = new XbrlDocument();
```
This initializes a new instance of the XBRL document.
## Step 3: Access XBRL Instances
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
This retrieves the collection of XBRL instances from the document and adds a new instance to it.
## Step 4: Add Unit
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
This creates a new unit of measure (in this case, USD) and adds it to the XBRL instance. You can adjust the currency code and namespace URI as needed.
## Step 5: Save the Document
```csharp
document.Save(outputDir + @"document4.xbrl");
```
This saves the modified XBRL document to the specified output directory.
## Conclusion
In conclusion, Aspose.Finance for .NET empowers developers to effortlessly manipulate financial documents and data within their .NET applications. By following the steps outlined in this tutorial, you can seamlessly integrate Aspose.Finance for .NET into your projects and enhance their financial processing capabilities.
## FAQs
### 1. Can I use Aspose.Finance for .NET without a license?
No, a valid license is required to unlock the full features of Aspose.Finance for .NET. However, temporary licenses are available for testing purposes.
### 2. Is Aspose.Finance for .NET suitable for building accounting software?
Yes, Aspose.Finance for .NET provides robust functionalities tailored for building accounting software and related financial applications.
### 3. Where can I find support for Aspose.Finance for .NET?
You can seek assistance from the Aspose.Finance community on the support forum.
### 4. Can I customize the unit of measure in an XBRL document?
Yes, you can create and add custom units of measure to XBRL documents using Aspose.Finance for .NET.
### 5. Does Aspose.Finance for .NET support multiple currencies?
Yes, Aspose.Finance for .NET supports multiple currencies, allowing for versatile financial data processing.

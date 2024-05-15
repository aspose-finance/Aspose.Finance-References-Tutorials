---
title: Convert XBRL to XLSX
linktitle: Convert XBRL to XLSX
second_title: Aspose.Finance .NET API
description: 
type: docs
weight: 11
url: /net/financial-data-conversion/convert-xbrl-to-xlsx/
---

## Complete Source Code
```csharp
using Aspose.Finance.Xbrl;
using System;
using System.Collections.Generic;

namespace CSharp.Conversion
{
    class ConvertXbrlToXlsx
    {
        public static void Run()
        {
            // ExStart:1
            // Working directories
            string sourceDir = "Your Source Directory";
            string outputDir = "Your Output Directory"

            XbrlDocument document = new XbrlDocument(sourceDir + @"IdScopeContextPeriodStartAfterEnd.xml");

            // Set save options
            SaveOptions saveOptions = new SaveOptions();
            saveOptions.SaveFormat = SaveFormat.XLSX;

            // Save file to XLSX format
            document.Save(outputDir + @"ConvertXbrlToXlsx_out.xlsx", saveOptions);
            // ExEnd:1

            Console.WriteLine("ConvertXbrlToXlsx executed successfully.");
        }
    }
}

```

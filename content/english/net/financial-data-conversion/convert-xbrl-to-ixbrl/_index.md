---
title: Convert XBRL to iXBRL
linktitle: Convert XBRL to iXBRL
second_title: Aspose.Finance .NET API
description: 
type: docs
weight: 10
url: /net/financial-data-conversion/convert-xbrl-to-ixbrl/
---

## Complete Source Code
```csharp
using Aspose.Finance.Xbrl;
using System;
using System.Collections.Generic;

namespace CSharp.Conversion
{
    class ConvertXbrlToIXbrl
    {
        public static void Run()
        {
            // ExStart:1
            // Working directories
            string sourceDir = RunExamples.Get_SourceDirectory();
            string outputDir = RunExamples.Get_OutputDirectory();

            XbrlDocument document = new XbrlDocument(sourceDir + @"IdScopeContextPeriodStartAfterEnd.xml");

            // Set save options
            SaveOptions saveOptions = new SaveOptions();
            saveOptions.SaveFormat = SaveFormat.IXBRL;

            // Save file to XLSX format
            document.Save(outputDir + @"ConvertXbrlToIXbrl_out.ixbrl", saveOptions);
            // ExEnd:1

            Console.WriteLine("ConvertXbrlToIXbrl executed successfully.");
        }
    }
}

```

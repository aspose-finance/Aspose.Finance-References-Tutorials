---
title: Convert OFX Response File to OFX Response V2
linktitle: Convert OFX Response File to OFX Response V2
second_title: Aspose.Finance .NET API
description: 
type: docs
weight: 11
url: /net/ofx-file-manipulation/convert-ofx-response-file-to-ofx-response-v2/
---

## Complete Source Code
```csharp
using Aspose.Finance.Ofx;
using System;

namespace CSharp.WorkingWithOfxFiles
{
    class ConvertOfxResponseFileToOfxResponseV2
    {
        public static void Run()
        {
            // ExStart:1
            // Working directories
            string sourceDir = "Your Source Directory";
            string outputDir = "Your Output Directory"

            OfxResponseDocument document = new OfxResponseDocument(sourceDir + @"bankTransactionRes.sgml");
            document.Save(outputDir + @"bankTransactionRes.xml", OfxVersionEnum.V2x);
            // ExEnd:1

            Console.WriteLine("ConvertOfxResponseFileToOfxResponseV2 executed successfully.");
        }
    }
}

```

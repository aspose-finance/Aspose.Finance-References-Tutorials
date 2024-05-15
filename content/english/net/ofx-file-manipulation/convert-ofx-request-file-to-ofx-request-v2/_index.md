---
title: Convert OFX Request File to OFX Request V2
linktitle: Convert OFX Request File to OFX Request V2
second_title: Aspose.Finance .NET API
description: 
type: docs
weight: 10
url: /net/ofx-file-manipulation/convert-ofx-request-file-to-ofx-request-v2/
---

## Complete Source Code
```csharp
using Aspose.Finance.Ofx;
using System;

namespace CSharp.WorkingWithOfxFiles
{
    class ConvertOfxRequestFileToOfxRequestV2
    {
        public static void Run()
        {
            // ExStart:1
            // Working directories
            string sourceDir = "Your Source Directory";
            string outputDir = "Your Output Directory"

            OfxRequestDocument document = new OfxRequestDocument(sourceDir + @"bankTransactionReq.sgml");
            document.Save(outputDir + @"bankTransactionReq.xml", OfxVersionEnum.V2x);
            // ExEnd:1

            Console.WriteLine("ConvertOfxRequestFileToOfxRequestV2 executed successfully.");
        }
    }
}

```

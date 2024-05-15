---
title: Read iXBRL Document
linktitle: Read iXBRL Document
second_title: Aspose.Finance .NET API
description: 
type: docs
weight: 10
url: /net/xbrl-file-reading/read-ixbrl-document/
---

## Complete Source Code
```csharp
using Aspose.Finance.Xbrl;
using Aspose.Finance.Xbrl.Inline;
using System;
using System.Collections.Generic;

namespace CSharp.ReadXbrlFiles
{
    class ReadIxbrlDocument
    {
        public static void Run()
        {
            // ExStart:1
            // Source directory
            string sourceDir = "Your Source Directory";

            InlineXbrlDocument document = new InlineXbrlDocument(sourceDir + @"account_1.html");
            List<InlineFact> inlineFacts = document.Facts;
            List<Context> contexts = document.Contexts;
            List<Unit> units = document.Units;
            // ExEnd:1

            Console.WriteLine("ReadIxbrlDocument executed successfully.");
        }
    }
}

```

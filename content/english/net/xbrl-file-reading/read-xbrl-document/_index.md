---
title: Read XBRL Document
linktitle: Read XBRL Document
second_title: Aspose.Finance .NET API
description: 
type: docs
weight: 11
url: /net/xbrl-file-reading/read-xbrl-document/
---

## Complete Source Code
```csharp
using Aspose.Finance.Xbrl;
using System;
using System.Collections.Generic;

namespace CSharp.ReadXbrlFiles
{
    class ReadXbrlDocument
    {
        public static void Run()
        {
            // ExStart:1
            // Source directory
            string sourceDir = "Your Source Directory";

            XbrlDocument document = new XbrlDocument(sourceDir + @"IdScopeContextPeriodStartAfterEnd.xml");
            XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
            XbrlInstance xbrlInstance = xbrlInstances[0];
            List<Fact> facts = xbrlInstance.Facts;
            SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
            List<Context> contexts = xbrlInstance.Contexts;
            List<Unit> units = xbrlInstance.Units;
            // ExEnd:1

            Console.WriteLine("ReadXbrlDocument executed successfully.");
        }
    }
}

```

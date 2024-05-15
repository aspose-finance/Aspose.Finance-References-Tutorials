---
title: Add Context to XBRL Document
linktitle: Add Context to XBRL Document
second_title: Aspose.Finance .NET API
description: 
type: docs
weight: 11
url: /net/xbrl-file-creation/add-context-to-xbrl-document/
---

## Complete Source Code
```csharp
using Aspose.Finance.Xbrl;
using System;

namespace CSharp.CreateXbrlFiles
{
    class AddContextToXbrlDocument
    {
        public static void Run()
        {
            // ExStart:1
            // Output directory
            string outputDir = "Your Output Directory"

            XbrlDocument document = new XbrlDocument();
            XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
            XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
            ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
            ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
            Context context = new Context(contextPeriod, contextEntity);
            xbrlInstance.Contexts.Add(context);
            document.Save(outputDir + @"document3.xbrl");
            // ExEnd:1

            Console.WriteLine("AddContextToXbrlDocument executed successfully.");
        }
    }
}

```

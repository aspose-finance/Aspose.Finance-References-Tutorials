---
title: Create XBRL File
linktitle: Create XBRL File
second_title: Aspose.Finance .NET API
description: 
type: docs
weight: 17
url: /net/xbrl-file-creation/create-xbrl-file/
---

## Complete Source Code
```csharp
using Aspose.Finance.Xbrl;
using System;

namespace CSharp.CreateXbrlFiles
{
    class CreateXbrlFile
    {
        public static void Run()
        {
            // ExStart:1
            // Output directory
            string outputDir = "Your Output Directory"

            XbrlDocument document = new XbrlDocument();
            XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
            XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
            document.Save(outputDir + @"document1.xbrl");
            // ExEnd:1

            Console.WriteLine("CreateXbrlFile executed successfully.");
        }
    }
}

```

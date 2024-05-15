---
title: Add Schema Reference to XBRL Document
linktitle: Add Schema Reference to XBRL Document
second_title: Aspose.Finance .NET API
description: 
type: docs
weight: 15
url: /net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---

## Complete Source Code
```csharp
using Aspose.Finance.Xbrl;
using System;

namespace CSharp.CreateXbrlFiles
{
    class AddSchemaReferenceToXbrlDocument
    {
        public static void Run()
        {
            // ExStart:1
            // Source directory
            string sourceDir = "Your Source Directory";

            // Output directory
            string outputDir = "Your Output Directory"

            XbrlDocument document = new XbrlDocument();
            XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
            XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
            SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
            schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
            document.Save(outputDir + @"document2.xbrl");
            // ExEnd:1

            Console.WriteLine("AddSchemaReferenceToXbrlDocument executed successfully.");
        }
    }
}

```

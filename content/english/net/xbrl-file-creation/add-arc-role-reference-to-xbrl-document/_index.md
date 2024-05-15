---
title: Add ARC Role Reference to XBRL Document
linktitle: Add ARC Role Reference to XBRL Document
second_title: Aspose.Finance .NET API
description: 
type: docs
weight: 10
url: /net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---

## Complete Source Code
```csharp
using Aspose.Finance.Xbrl;
using System;

namespace CSharp.CreateXbrlFiles
{
    class AddArcRoleReferenceToXbrlDocument
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
            SchemaRef schema = schemaRefs[0];
            ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
            if (arcroleType != null)
            {
                ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
                xbrlInstance.ArcroleReferences.Add(arcroleReference);
            }
            document.Save(outputDir + @"document8.xbrl");
            // ExEnd:1

            Console.WriteLine("AddArcRoleReferenceToXbrlDocument executed successfully.");
        }
    }
}

```

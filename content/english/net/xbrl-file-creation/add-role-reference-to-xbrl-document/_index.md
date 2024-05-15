---
title: Add Role Reference to XBRL Document
linktitle: Add Role Reference to XBRL Document
second_title: Aspose.Finance .NET API
description: 
type: docs
weight: 14
url: /net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---

## Complete Source Code
```csharp
using Aspose.Finance.Xbrl;
using System;

namespace CSharp.CreateXbrlFiles
{
    class AddRoleReferenceToXbrlDocument
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
            RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
            if (roleType != null)
            {
                RoleReference roleReference = new RoleReference(roleType);
                xbrlInstance.RoleReferences.Add(roleReference);
            }
            document.Save(outputDir + @"document7.xbrl");
            // ExEnd:1

            Console.WriteLine("AddRoleReferenceToXbrlDocument executed successfully.");
        }
    }
}

```

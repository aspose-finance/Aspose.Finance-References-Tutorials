---
title: Add Unit to XBRL Document
linktitle: Add Unit to XBRL Document
second_title: Aspose.Finance .NET API
description: 
type: docs
weight: 16
url: /net/xbrl-file-creation/add-unit-to-xbrl-document/
---

## Complete Source Code
```csharp
using Aspose.Finance.Xbrl;
using System;

namespace CSharp.CreateXbrlFiles
{
    class AddUnitToXbrlDocument
    {
        public static void Run()
        {
            // ExStart:1
            // Output directory
            string outputDir = "Your Output Directory"

            XbrlDocument document = new XbrlDocument();
            XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
            XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
            Unit unit = new Unit(UnitType.Measure);
            unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
            xbrlInstance.Units.Add(unit);
            document.Save(outputDir + @"document4.xbrl");
            // ExEnd:1

            Console.WriteLine("AddUnitToXbrlDocument executed successfully.");
        }
    }
}

```

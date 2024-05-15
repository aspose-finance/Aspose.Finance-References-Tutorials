---
title: Add Footnote Link to XBRL Document
linktitle: Add Footnote Link to XBRL Document
second_title: Aspose.Finance .NET API
description: 
type: docs
weight: 12
url: /net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---

## Complete Source Code
```csharp
using Aspose.Finance.Xbrl;
using System;

namespace CSharp.CreateXbrlFiles
{
    class AddFootnoteLinkToXbrlDocument
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
            ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
            ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
            Context context = new Context(contextPeriod, contextEntity);
            context.Id = "cd1";
            xbrlInstance.Contexts.Add(context);
            FootnoteLink footnoteLink = new FootnoteLink();
            Footnote footnote = new Footnote("footnote1");
            footnote.Text = "Including the effects of the merger.";
            Loc loc = new Loc("#cd1", "fact1");
            FootnoteArc footnoteArc = new FootnoteArc(loc.Label, footnote.Label);
            footnoteLink.Footnotes.Add(footnote);
            footnoteLink.Locators.Add(loc);
            footnoteLink.FootnoteArcs.Add(footnoteArc);
            xbrlInstance.FootnoteLinks.Add(footnoteLink);
            document.Save(outputDir + @"document6.xbrl");
            // ExEnd:1

            Console.WriteLine("AddFootnoteLinkToXbrlDocument executed successfully.");
        }
    }
}

```

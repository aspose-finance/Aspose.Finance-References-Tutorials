---
title: Lägg till fotnotslänk till XBRL-dokument
linktitle: Lägg till fotnotslänk till XBRL-dokument
second_title: Aspose.Finance .NET API
description: Lär dig hur du lägger till fotnotslänkar till XBRL-dokument med Aspose.Finance för .NET. Förbättra finansiella rapporter med ytterligare sammanhang utan ansträngning.
type: docs
weight: 12
url: /sv/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
Att lägga till en fotnotslänk till ett XBRL-dokument är avgörande för att ge ytterligare sammanhang eller förklaringar för specifika datapunkter. I den här handledningen går vi igenom processen steg för steg med Aspose.Finance för .NET.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar på plats:
1.  Aspose.Finance for .NET: Se till att du har installerat Aspose.Finance for .NET på ditt system. Du kan ladda ner den från[här](https://releases.aspose.com/finance/net/).
  
2. Utvecklingsmiljö: Ha en utvecklingsmiljö inrättad med ett .NET Framework eller .NET Core.
## Importera namnområden:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Steg 1: Ställ in käll- och utdatakataloger
Ange först katalogerna för käll- och utdatafilerna:
```csharp
// Källkatalog
string sourceDir = "Your Source Directory";
// Utdatakatalog
string outputDir = "Your Output Directory";
```
## Steg 2: Skapa ett XBRL-dokument och en instans
Initiera ett XBRL-dokument och en instans:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Steg 3: Lägg till schemareferenser
Lägg till schemareferenser till XBRL-instansen:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomi");
SchemaRef schema = schemaRefs[0];
```
## Steg 4: Definiera sammanhang
Definiera sammanhanget för XBRL-instansen:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## Steg 5: Lägg till fotnotslänk
Skapa och lägg till en fotnotslänk till XBRL-instansen:
```csharp
FootnoteLink footnoteLink = new FootnoteLink();
Footnote footnote = new Footnote("footnote1");
footnote.Text = "Including the effects of the merger.";
Loc loc = new Loc("#cd1", "fact1");
FootnoteArc footnoteArc = new FootnoteArc(loc.Label, footnote.Label);
footnoteLink.Footnotes.Add(footnote);
footnoteLink.Locators.Add(loc);
footnoteLink.FootnoteArcs.Add(footnoteArc);
xbrlInstance.FootnoteLinks.Add(footnoteLink);
```
## Steg 6: Spara dokumentet
Spara det ändrade XBRL-dokumentet:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## Slutsats
Att lägga till en fotnotslänk till ett XBRL-dokument är en enkel process med Aspose.Finance för .NET. Genom att följa stegen som beskrivs i denna handledning kan du sömlöst införliva ytterligare sammanhang eller förklaringar i dina finansiella rapporter.
## Vanliga frågor
### Kan jag lägga till flera fotnotslänkar till ett enda XBRL-dokument?
Ja, du kan lägga till flera fotnotslänkar genom att upprepa stegen som beskrivs i den här handledningen för varje ytterligare länk.
### Är Aspose.Finance för .NET kompatibelt med både .NET Framework och .NET Core?
Ja, Aspose.Finance för .NET stöder både .NET Framework och .NET Core-miljöer.
### Hur kan jag få en tillfällig licens för Aspose.Finance för .NET?
 Du kan få en tillfällig licens från[här](https://purchase.aspose.com/temporary-license/).
### Ger Aspose.Finance för .NET stöd för XBRL-validering?
Ja, Aspose.Finance för .NET erbjuder omfattande stöd för XBRL-validering för att säkerställa överensstämmelse med industristandarder.
### Var kan jag hitta ytterligare resurser och support för Aspose.Finance för .NET?
 Du kan besöka[Aspose.Finance för .NET-forum](https://forum.aspose.com/c/finance/43) för support och tillgång till dokumentation[här](https://reference.aspose.com/finance/net/).
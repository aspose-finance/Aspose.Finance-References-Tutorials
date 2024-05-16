---
title: Voetnootlink toevoegen aan XBRL-document
linktitle: Voetnootlink toevoegen aan XBRL-document
second_title: Aspose.Finance .NET-API
description: Leer hoe u voetnootlinks aan XBRL-documenten kunt toevoegen met Aspose.Finance voor .NET. Verbeter financiële rapporten moeiteloos met extra context.
type: docs
weight: 12
url: /nl/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
Het toevoegen van een voetnootlink aan een XBRL-document is cruciaal voor het bieden van aanvullende context of uitleg voor specifieke gegevenspunten. In deze zelfstudie doorlopen we stap voor stap het proces met behulp van Aspose.Finance voor .NET.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1.  Aspose.Finance voor .NET: Zorg ervoor dat u Aspose.Finance voor .NET op uw systeem hebt geïnstalleerd. Je kunt het downloaden van[hier](https://releases.aspose.com/finance/net/).
  
2. Ontwikkelomgeving: Laat een ontwikkelomgeving opzetten met een .NET Framework of .NET Core.
## Naamruimten importeren:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Stap 1: Stel de bron- en uitvoermappen in
Specificeer eerst de mappen voor de bron- en uitvoerbestanden:
```csharp
// Bronmap
string sourceDir = "Your Source Directory";
// Uitvoermap
string outputDir = "Your Output Directory";
```
## Stap 2: Maak een XBRL-document en -exemplaar
Initialiseer een XBRL-document en -exemplaar:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Stap 3: Schemaverwijzingen toevoegen
Voeg schemaverwijzingen toe aan de XBRL-instantie:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://voorbeeld.com/xbrl/taxonomie");
SchemaRef schema = schemaRefs[0];
```
## Stap 4: Definieer context
Definieer de context voor de XBRL-instantie:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## Stap 5: voeg een voetnootlink toe
Maak een voetnootlink en voeg deze toe aan de XBRL-instantie:
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
## Stap 6: Sla het document op
Sla het gewijzigde XBRL-document op:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## Conclusie
Het toevoegen van een voetnootlink aan een XBRL-document is een eenvoudig proces met Aspose.Finance voor .NET. Door de stappen in deze zelfstudie te volgen, kunt u naadloos aanvullende context of uitleg in uw financiële rapporten opnemen.
## Veelgestelde vragen
### Kan ik meerdere voetnootlinks toevoegen aan één XBRL-document?
Ja, u kunt meerdere voetnootlinks toevoegen door de stappen in deze zelfstudie voor elke extra link te herhalen.
### Is Aspose.Finance voor .NET compatibel met zowel .NET Framework als .NET Core?
Ja, Aspose.Finance voor .NET ondersteunt zowel .NET Framework- als .NET Core-omgevingen.
### Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Finance voor .NET?
 Een tijdelijke licentie kunt u verkrijgen bij[hier](https://purchase.aspose.com/temporary-license/).
### Biedt Aspose.Finance voor .NET ondersteuning voor XBRL-validatie?
Ja, Aspose.Finance voor .NET biedt uitgebreide ondersteuning voor XBRL-validatie om naleving van industriestandaarden te garanderen.
### Waar kan ik aanvullende bronnen en ondersteuning vinden voor Aspose.Finance voor .NET?
 U kunt een bezoek brengen aan de[Aspose.Finance voor .NET-forum](https://forum.aspose.com/c/finance/43) voor ondersteuning en toegangsdocumentatie[hier](https://reference.aspose.com/finance/net/).
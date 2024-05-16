---
title: Voeg ARC-rolreferentie toe aan XBRL-document
linktitle: Voeg ARC-rolreferentie toe aan XBRL-document
second_title: Aspose.Finance .NET-API
description: Leer hoe u XBRL-documenten efficiënt kunt manipuleren met Aspose.Finance voor .NET. Voeg moeiteloos ARC-rolreferenties toe met stapsgewijze begeleiding.
type: docs
weight: 10
url: /nl/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## Invoering
In de wereld van financieel databeheer en rapportage speelt de eXtensible Business Reporting Language (XBRL) een cruciale rol. Het standaardiseert de manier waarop financiële informatie wordt gecommuniceerd en uitgewisseld, waardoor consistentie, nauwkeurigheid en efficiëntie worden gegarandeerd. Het manipuleren van XBRL-documenten, vooral wanneer er specifieke rollen en referenties in worden opgenomen, vereist echter een genuanceerd begrip van de onderliggende mechanismen. Deze tutorial richt zich op zo'n taak: het toevoegen van een ARC-rolreferentie aan een XBRL-document met behulp van Aspose.Finance voor .NET.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
### Omgeving instellen
1.  Aspose.Finance for .NET installeren: Download en installeer de Aspose.Finance for .NET-bibliotheek van de[releases](https://releases.aspose.com/finance/net/).
   
2. Ontwikkelomgeving: Stel uw ontwikkelomgeving in met Visual Studio of een andere gewenste IDE.
## Naamruimten importeren
Zorg ervoor dat u de benodigde naamruimten in uw C#-code importeert:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Stap 1: Definieer bron- en uitvoermappen
Voordat u verdergaat, geeft u de bron- en uitvoermappen op waar uw XBRL-bestanden respectievelijk zullen worden geplaatst en opgeslagen.
```csharp
// Bronmap
string sourceDir = "Your Source Directory";
// Uitvoermap
string outputDir = "Your Output Directory";
```
## Stap 2: Maak een XBRL-document
 Instantieer een`XbrlDocument` bezwaar om met XBRL-gegevens te werken.
```csharp
XbrlDocument document = new XbrlDocument();
```
## Stap 3: Open de XbrlInstance-verzameling
Krijg toegang tot de verzameling XBRL-instanties binnen het document.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## Stap 4: Voeg XbrlInstance toe
Voeg een nieuwe XBRL-instantie toe aan de verzameling.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Stap 5: Schemareferentie toevoegen
Neem een schemaverwijzing op in het XBRL-exemplaar, waarbij u de bronmap, het naamruimtevoorvoegsel en de URI specificeert.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://voorbeeld.com/xbrl/taxonomie");
```
## Stap 6: ArcroleType ophalen
 Haal de`ArcroleType` gebaseerd op een specifieke URI.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## Stap 7: Voeg ArcroleReference toe
 Als de`ArcroleType` wordt gevonden, maak dan een`ArcroleReference` en voeg het toe aan de arcrole-referenties van de XBRL-instantie.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## Stap 8: Bewaar het document
Sla het gewijzigde XBRL-document op in de opgegeven uitvoermap.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## Conclusie
In deze zelfstudie hebben we onderzocht hoe u een ARC-rolreferentie kunt toevoegen aan een XBRL-document met behulp van Aspose.Finance voor .NET. Door deze stapsgewijze instructies te volgen en gebruik te maken van de mogelijkheden van Aspose.Finance, kunt u XBRL-gegevens efficiënt beheren en manipuleren om aan uw specifieke vereisten te voldoen.
## Veelgestelde vragen
### Wat is XBRL?
XBRL staat voor eXtensible Business Reporting Language, een gestandaardiseerde taal voor de elektronische communicatie van zakelijke en financiële gegevens.
### Waarom is XBRL belangrijk?
XBRL zorgt voor consistentie, nauwkeurigheid en efficiëntie bij de uitwisseling en analyse van financiële informatie, wat toezichthouders, analisten en bedrijven ten goede komt.
### Kan Aspose.Finance complexe XBRL-taken aan?
Ja, Aspose.Finance biedt robuuste functionaliteit voor het werken met XBRL-documenten, inclusief het afhandelen van complexe taken zoals rolreferenties en taxonomiebeheer.
### Is Aspose.Finance compatibel met andere .NET-bibliotheken?
Ja, Aspose.Finance integreert naadloos met andere .NET-bibliotheken en biedt uitgebreide ondersteuning voor de manipulatie en rapportage van financiële gegevens.
### Waar kan ik aanvullende ondersteuning vinden voor Aspose.Finance?
 Bezoek voor aanvullende ondersteuning de[Ondersteuningspagina Aspose.Finance](https://forum.aspose.com/c/finance/43).
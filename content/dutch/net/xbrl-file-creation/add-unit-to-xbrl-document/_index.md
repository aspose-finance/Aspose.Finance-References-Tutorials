---
title: Eenheid toevoegen aan XBRL-document
linktitle: Eenheid toevoegen aan XBRL-document
second_title: Aspose.Finance .NET-API
description: Leer hoe u moeiteloos eenheden aan XBRL-documenten kunt toevoegen met Aspose.Finance voor .NET. Verbeter vandaag nog uw financiële gegevensverwerkingsmogelijkheden!
type: docs
weight: 16
url: /nl/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
Welkom in de wereld van Aspose.Finance for .NET - uw toegangspoort tot efficiënte financiële documentmanipulatie binnen .NET-toepassingen. Of u nu boekhoudsoftware, hulpmiddelen voor financiële analyse of een andere financiële toepassing bouwt, Aspose.Finance voor .NET voorziet u van een uitgebreide reeks functies om uw ontwikkelingsproces te stroomlijnen.
## Vereisten
Voordat we ons verdiepen in het benutten van de kracht van Aspose.Finance voor .NET, moeten we ervoor zorgen dat we aan de noodzakelijke voorwaarden voldoen:
### 1. Visual Studio-installatie
Zorg ervoor dat Visual Studio op uw systeem is geïnstalleerd. Als dit niet het geval is, kunt u het downloaden en installeren vanaf de officiële Microsoft-website.
### 2. Verkrijg een licentie
 Om het volledige potentieel van Aspose.Finance voor .NET te benutten, hebt u een geldige licentie nodig. U kunt een licentie kopen bij[hier](https://purchase.aspose.com/buy) of kies voor een tijdelijke licentie voor testdoeleinden.
### 3. Download en raadpleeg Aspose.Finance voor .NET
 Download de Aspose.Finance voor .NET-bibliotheek van de[releases pagina](https://releases.aspose.com/finance/net/) en verwijs ernaar in uw .NET-project.
### 4. Toegang tot documentatie en ondersteuning
 Verwijs naar de[documentatie](https://reference.aspose.com/finance/net/)voor gedetailleerde informatie over het gebruik van Aspose.Finance voor .NET. Bovendien kunt u hulp zoeken bij de Aspose.Finance-gemeenschap op de website[Helpforum](https://forum.aspose.com/c/finance/43).
## Naamruimten importeren
Laten we nu de benodigde naamruimten in uw .NET-project importeren:
## Stap 1: Voeg de Aspose.Finance-naamruimte toe
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Deze naamruimte bevat klassen en methoden die essentieel zijn voor het werken met XBRL-documenten en gegevens.
Laten we het gegeven voorbeeld in meerdere stappen opsplitsen om te begrijpen hoe u een eenheid aan een XBRL-document kunt toevoegen met behulp van Aspose.Finance voor .NET.
## Stap 1: Definieer de uitvoerdirectory
```csharp
// Uitvoermap
string outputDir = "Your Output Directory";
```
 Vervangen`"Your Output Directory"` met het daadwerkelijke pad naar de gewenste uitvoermap.
## Stap 2: Maak een XBRL-document
```csharp
XbrlDocument document = new XbrlDocument();
```
Hiermee wordt een nieuw exemplaar van het XBRL-document geïnitialiseerd.
## Stap 3: Toegang tot XBRL-instanties
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Hiermee wordt de verzameling XBRL-instanties uit het document opgehaald en wordt er een nieuwe instantie aan toegevoegd.
## Stap 4: Eenheid toevoegen
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Hierdoor wordt een nieuwe maateenheid aangemaakt (in dit geval USD) en wordt deze toegevoegd aan de XBRL-instantie. U kunt de valutacode en de naamruimte-URI indien nodig aanpassen.
## Stap 5: Bewaar het document
```csharp
document.Save(outputDir + @"document4.xbrl");
```
Hiermee wordt het gewijzigde XBRL-document opgeslagen in de opgegeven uitvoermap.
## Conclusie
Concluderend stelt Aspose.Finance voor .NET ontwikkelaars in staat moeiteloos financiële documenten en gegevens binnen hun .NET-applicaties te manipuleren. Door de stappen in deze zelfstudie te volgen, kunt u Aspose.Finance voor .NET naadloos in uw projecten integreren en de financiële verwerkingsmogelijkheden ervan verbeteren.
## Veelgestelde vragen
### 1. Kan ik Aspose.Finance voor .NET gebruiken zonder licentie?
Nee, een geldige licentie is vereist om de volledige functies van Aspose.Finance voor .NET te ontgrendelen. Er zijn echter tijdelijke licenties beschikbaar voor testdoeleinden.
### 2. Is Aspose.Finance voor .NET geschikt voor het bouwen van boekhoudsoftware?
Ja, Aspose.Finance voor .NET biedt robuuste functionaliteiten die op maat zijn gemaakt voor het bouwen van boekhoudsoftware en gerelateerde financiële applicaties.
### 3. Waar kan ik ondersteuning vinden voor Aspose.Finance voor .NET?
U kunt hulp zoeken bij de Aspose.Finance-gemeenschap op het ondersteuningsforum.
### 4. Kan ik de maateenheid in een XBRL-document aanpassen?
Ja, u kunt aangepaste maateenheden maken en toevoegen aan XBRL-documenten met Aspose.Finance voor .NET.
### 5. Ondersteunt Aspose.Finance voor .NET meerdere valuta's?
Ja, Aspose.Finance voor .NET ondersteunt meerdere valuta's, waardoor veelzijdige financiële gegevensverwerking mogelijk is.
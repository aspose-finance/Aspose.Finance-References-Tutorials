---
title: Context toevoegen aan XBRL-document
linktitle: Context toevoegen aan XBRL-document
second_title: Aspose.Finance .NET-API
description: Leer hoe u context kunt toevoegen aan XBRL-documenten in .NET met behulp van Aspose.Finance voor gestroomlijnde financiële rapportage. #Aspose #Financiën #XBRL
type: docs
weight: 11
url: /nl/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## Invoering
Op het gebied van financiële rapportage speelt XBRL (eXtensible Business Reporting Language) een cruciale rol bij het standaardiseren van de uitwisseling van bedrijfsinformatie. Het toevoegen van context aan XBRL-documenten is cruciaal om de integriteit en relevantie van de gegevens die ze bevatten te waarborgen. Met Aspose.Finance voor .NET wordt dit proces gestroomlijnd en efficiënt, waardoor ontwikkelaars naadloos context in hun XBRL-documenten kunnen integreren.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Aspose.Finance voor .NET-bibliotheek: Download en installeer de Aspose.Finance voor .NET-bibliotheek van de[releases](https://releases.aspose.com/finance/net/).
2. .NET-ontwikkelomgeving: Zorg ervoor dat er een werkende .NET-ontwikkelomgeving op uw computer is geïnstalleerd.
3. Basiskennis van C#: Bekendheid met de programmeertaal C# zal nuttig zijn bij het volgen van de voorbeelden.
## Naamruimten importeren
Importeer in uw C#-project de benodigde naamruimten om toegang te krijgen tot de functionaliteit van Aspose.Finance voor .NET:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Stap 1: Stel de uitvoermap in
Voordat u context aan het XBRL-document toevoegt, geeft u de uitvoermap op waar het gewijzigde document zal worden opgeslagen:
```csharp
string outputDir = "Your Output Directory";
```
 Vervangen`"Your Output Directory"` met het gewenste pad op uw systeem.
## Stap 2: XBRL-document maken
 Instantieer een`XbrlDocument` bezwaar tegen het werken met XBRL-documenten:
```csharp
XbrlDocument document = new XbrlDocument();
```
Dit object vertegenwoordigt het XBRL-document dat zal worden gemanipuleerd.
## Stap 3: XBRL-instantie toevoegen
Voeg een XBRL-instantie toe aan het document. Elk exemplaar bevat de gegevens voor een specifieke rapportageperiode:
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Met deze stap wordt een XBRL-instantie binnen het document geïnitialiseerd.
## Stap 4: Definieer contextperiode en entiteit
Maak een contextperiode en entiteit voor de XBRL-instantie:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
Geef de periode- en entiteitsdetails op volgens uw rapportagevereisten.
## Stap 5: Creëer context
Construeer een context met behulp van de periode en entiteit die in de vorige stap zijn gedefinieerd:
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
Deze context omvat de temporele en entiteitsgerelateerde informatie.
## Stap 6: Voeg context toe aan XBRL-instantie
Koppel de context die in de vorige stap is gemaakt aan de XBRL-instantie:
```csharp
xbrlInstance.Contexts.Add(context);
```
Deze stap koppelt de context aan de XBRL-instantie, waardoor relevante contextuele informatie aan de gegevens wordt verstrekt.
## Stap 7: Bewaar het document
Sla het gewijzigde XBRL-document op in de opgegeven uitvoermap:
```csharp
document.Save(outputDir + @"document3.xbrl");
```
Hiermee wordt het proces afgerond en wordt het XBRL-document met de toegevoegde context opgeslagen.
## Conclusie
Door deze stappen te volgen, kunt u effectief context toevoegen aan XBRL-documenten met behulp van Aspose.Finance voor .NET. Dit vergroot de duidelijkheid en bruikbaarheid van financiële gegevens, waardoor nauwkeurige analyse en rapportage mogelijk worden.
## Veelgestelde vragen
### Kan Aspose.Finance voor .NET grote XBRL-documenten aan?
Aspose.Finance voor .NET is geoptimaliseerd voor het verwerken van XBRL-documenten van verschillende groottes, inclusief grote datasets.
### Is er een proefversie beschikbaar voor Aspose.Finance voor .NET?
Ja, u kunt een gratis proefversie downloaden van de officiële Aspose-website.
### Ondersteunt Aspose.Finance voor .NET naast XBRL ook andere financiële rapportagestandaarden?
Aspose.Finance richt zich primair op XBRL-gerelateerde functionaliteiten maar biedt ook ondersteuning voor andere financiële formaten.
### Kan ik de contextinformatie aanpassen aan mijn specifieke vereisten?
Absoluut, Aspose.Finance voor .NET biedt flexibiliteit voor het aanpassen van contextinformatie aan uw behoeften.
### Waar kan ik aanvullende ondersteuning of bronnen vinden voor Aspose.Finance voor .NET?
U kunt het Aspose.Finance-forum bezoeken voor hulp van de community of de documentatie raadplegen voor uitgebreide begeleiding.
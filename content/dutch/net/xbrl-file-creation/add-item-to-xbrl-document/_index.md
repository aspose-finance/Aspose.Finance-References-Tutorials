---
title: Item toevoegen aan XBRL-document
linktitle: Item toevoegen aan XBRL-document
second_title: Aspose.Finance .NET-API
description: Leer hoe u items aan XBRL-documenten kunt toevoegen met Aspose.Finance voor .NET. Vereenvoudig de financiële rapportage in uw .NET-applicaties. #Aspose #Financiën
type: docs
weight: 13
url: /nl/net/xbrl-file-creation/add-item-to-xbrl-document/
---
Extensible Business Reporting Language (XBRL) is een standaardformaat geworden voor financiële rapportage, waardoor efficiënte en nauwkeurige communicatie van financiële gegevens mogelijk is. Aspose.Finance voor .NET biedt robuuste functionaliteit om met XBRL-documenten in uw .NET-applicaties te werken. In deze zelfstudie doorlopen we de stappen om een item aan een XBRL-document toe te voegen met behulp van Aspose.Finance voor .NET.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
### 1. Installeer Aspose.Finance voor .NET
 Download en installeer Aspose.Finance voor .NET als u dat nog niet heeft gedaan[officiële website](https://releases.aspose.com/finance/net/). Volg de installatie-instructies om de bibliotheek in uw .NET-omgeving in te richten.
### 2. Stel uw ontwikkelomgeving in
Zorg ervoor dat u over een werkende ontwikkelomgeving beschikt voor .NET-ontwikkeling. U hebt een compatibele IDE nodig, zoals Visual Studio, en het .NET-framework dat op uw systeem is geïnstalleerd.
## Naamruimten importeren
Importeer eerst de benodigde naamruimten in uw .NET-applicatie om de functionaliteit van Aspose.Finance voor .NET te gebruiken.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Laten we nu de voorbeeldcode in meerdere stappen opsplitsen:
## Stap 1: Definieer bron- en uitvoermappen
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Vervangen`"Your Source Directory"` En`"Your Output Directory"` met de paden naar respectievelijk uw bron- en uitvoermappen.
## Stap 2: Maak een XBRL-document en -exemplaar
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Initialiseer een XBRL-document en -exemplaar om mee te werken.
## Stap 3: Schemareferentie toevoegen
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://voorbeeld.com/xbrl/taxonomie");
```
Voeg een schemaverwijzing toe aan het XBRL-exemplaar, geef het pad naar het schemabestand op en geef naamruimtedetails op.
## Stap 4: Definieer context en entiteit
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
Maak een context en entiteit voor het XBRL-exemplaar, waarbij u de periode- en entiteitsdetails specificeert.
## Stap 5: Eenheid toevoegen
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Definieer een eenheid voor het XBRL-exemplaar en geef de gekwalificeerde namen op.
## Stap 6: Artikel toevoegen
```csharp
Concept fixedAssetsConcept = schema.GetConceptByName("fixedAssets");
if (fixedAssetsConcept != null)
{
    Item item = new Item(fixedAssetsConcept);
    item.ContextRef = context;
    item.UnitRef = unit;
    item.Precision = 4;
    item.Value = "1444";
    xbrlInstance.Facts.Add(item);
}
```
Voeg een item toe aan de XBRL-instantie en specificeer het concept, de context, de eenheid, de precisie en de waarde ervan.
## Stap 7: Document opslaan
```csharp
document.Save(outputDir + @"document5.xbrl");
```
Sla het XBRL-document op in de uitvoermap.
## Conclusie
Het toevoegen van items aan een XBRL-document is essentieel voor het accuraat weergeven van financiële gegevens. Aspose.Finance voor .NET vereenvoudigt dit proces door een uitgebreide API te bieden om met XBRL-documenten in .NET-applicaties te werken.
## Veelgestelde vragen
### Kan ik Aspose.Finance voor .NET gebruiken met elke .NET-toepassing?
Ja, Aspose.Finance voor .NET is compatibel met elke .NET-toepassing, inclusief ASP.NET-, WinForms- en Console-toepassingen.
### Is Aspose.Finance voor .NET gratis te gebruiken?
 Aspose.Finance voor .NET is een commerciële bibliotheek. U kunt een gratis proefversie downloaden om de functies ervan te evalueren, en licenties kunnen worden aangeschaft[hier](https://purchase.aspose.com/buy).
### Ondersteunt Aspose.Finance voor .NET naast XBRL ook andere financiële rapportageformaten?
Aspose.Finance voor .NET richt zich primair op XBRL-gerelateerde functionaliteit. Aspose biedt echter andere bibliotheken voor het werken met verschillende financiële formaten.
### Hoe kan ik ondersteuning krijgen voor Aspose.Finance voor .NET?
 U kunt ondersteuning krijgen voor Aspose.Finance voor .NET via de[officieel forum](https://forum.aspose.com/c/finance/43)waar u vragen kunt stellen en kunt communiceren met andere gebruikers en ondersteunend personeel.
### Kan ik een tijdelijke licentie verkrijgen voor Aspose.Finance voor .NET?
 Ja, tijdelijke licenties voor Aspose.Finance voor .NET zijn beschikbaar voor testdoeleinden. Je kunt er een verkrijgen[hier](https://purchase.aspose.com/temporary-license/).
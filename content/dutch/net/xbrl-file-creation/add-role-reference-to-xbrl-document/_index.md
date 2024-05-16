---
title: Rolreferentie toevoegen aan XBRL-document
linktitle: Rolreferentie toevoegen aan XBRL-document
second_title: Aspose.Finance .NET-API
description: Leer hoe u rolreferenties toevoegt aan XBRL-documenten met behulp van Aspose.Finance voor .NET. Vereenvoudig de financiële rapportage in uw .NET-applicaties met deze tutorial.
type: docs
weight: 14
url: /nl/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (eXtensible Business Reporting Language) is een standaard geworden voor het uitwisselen van bedrijfsinformatie, vooral in de financiële verslaggeving. Aspose.Finance voor .NET vereenvoudigt het werken met XBRL-documenten in .NET-applicaties. Deze tutorial leidt u door het proces van het toevoegen van een rolreferentie aan een XBRL-document met behulp van Aspose.Finance voor .NET.
## Vereisten
Voordat we aan de slag gaan, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
### 1. Installeer Aspose.Finance voor .NET
Zorg ervoor dat Aspose.Finance voor .NET in uw ontwikkelomgeving is geïnstalleerd. Als je dat nog niet hebt gedaan, download het dan van de[releases](https://releases.aspose.com/finance/net/) en volg de installatie-instructies.
### 2. Stel uw ontwikkelomgeving in
Zorg ervoor dat u over een werkende ontwikkelomgeving beschikt voor .NET-ontwikkeling. Dit omvat een compatibele IDE zoals Visual Studio en het .NET-framework dat op uw systeem is geïnstalleerd.
## Naamruimten importeren
Begin met het importeren van de benodigde naamruimten in uw .NET-applicatie om toegang te krijgen tot de functionaliteit van Aspose.Finance voor .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## Stap 4: Roltype ophalen en rolreferentie toevoegen
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
Haal het roltype op met behulp van de URI en voeg een rolverwijzing toe aan de XBRL-instantie.
## Stap 5: Document opslaan
```csharp
document.Save(outputDir + @"document7.xbrl");
```
Sla het XBRL-document op in de uitvoermap.
## Conclusie
Het toevoegen van rolreferenties aan XBRL-documenten is cruciaal voor het definiëren van de rollen van verschillende elementen binnen het document. Aspose.Finance voor .NET biedt een eenvoudige manier om deze taak te volbrengen, waardoor ontwikkelaars efficiënt met XBRL-documenten kunnen werken in hun .NET-applicaties.
## Veelgestelde vragen
### Kan ik Aspose.Finance voor .NET gebruiken met elke .NET-toepassing?
Ja, Aspose.Finance voor .NET is compatibel met elke .NET-toepassing, inclusief ASP.NET-, WinForms- en Console-toepassingen.
### Is Aspose.Finance voor .NET gratis te gebruiken?
 Aspose.Finance voor .NET is een commerciële bibliotheek. U kunt een gratis proefversie downloaden om de functies ervan te evalueren, en licenties kunnen worden aangeschaft[hier](https://purchase.aspose.com/buy).
### Ondersteunt Aspose.Finance voor .NET naast XBRL ook andere financiële rapportageformaten?
Aspose.Finance voor .NET richt zich primair op XBRL-gerelateerde functionaliteit. Aspose biedt echter andere bibliotheken voor het werken met verschillende financiële formaten.
### Hoe kan ik ondersteuning krijgen voor Aspose.Finance voor .NET?
 U kunt ondersteuning krijgen voor Aspose.Finance voor .NET via de[forum](https://forum.aspose.com/c/finance/43)waar u vragen kunt stellen en kunt communiceren met andere gebruikers en ondersteunend personeel.
### Kan ik een tijdelijke licentie verkrijgen voor Aspose.Finance voor .NET?
 Ja, tijdelijke licenties voor Aspose.Finance voor .NET zijn beschikbaar voor testdoeleinden. Je kunt er een verkrijgen[hier](https://purchase.aspose.com/temporary-license/).
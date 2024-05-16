---
title: Lägg till objekt i XBRL-dokument
linktitle: Lägg till objekt i XBRL-dokument
second_title: Aspose.Finance .NET API
description: Lär dig hur du lägger till objekt i XBRL-dokument med Aspose.Finance för .NET. Förenkla finansiell rapportering i dina .NET-applikationer. #Aspose #Finans
type: docs
weight: 13
url: /sv/net/xbrl-file-creation/add-item-to-xbrl-document/
---
Extensible Business Reporting Language (XBRL) har blivit ett standardformat för finansiell rapportering, vilket möjliggör effektiv och korrekt kommunikation av finansiell data. Aspose.Finance för .NET ger robust funktionalitet för att arbeta med XBRL-dokument i dina .NET-applikationer. I den här handledningen går vi igenom stegen för att lägga till ett objekt i ett XBRL-dokument med Aspose.Finance för .NET.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
### 1. Installera Aspose.Finance för .NET
 Om du inte redan har gjort det, ladda ner och installera Aspose.Finance för .NET från[officiell hemsida](https://releases.aspose.com/finance/net/). Följ installationsinstruktionerna för att ställa in biblioteket i din .NET-miljö.
### 2. Ställ in din utvecklingsmiljö
Se till att du har en fungerande utvecklingsmiljö för .NET-utveckling. Du behöver en kompatibel IDE som Visual Studio, tillsammans med .NET-ramverket installerat på ditt system.
## Importera namnområden
Importera först de nödvändiga namnområdena till din .NET-applikation för att använda funktionerna som tillhandahålls av Aspose.Finance för .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Låt oss nu dela upp exempelkoden i flera steg:
## Steg 1: Definiera käll- och utdatakataloger
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Byta ut`"Your Source Directory"` och`"Your Output Directory"` med sökvägarna till dina käll- respektive utdatakataloger.
## Steg 2: Skapa ett XBRL-dokument och en instans
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Initiera ett XBRL-dokument och en instans att arbeta med.
## Steg 3: Lägg till Schema Reference
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomi");
```
Lägg till en schemareferens till XBRL-instansen, ange sökvägen till schemafilen och specificera namnområdesdetaljer.
## Steg 4: Definiera sammanhang och enhet
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
Skapa en kontext och entitet för XBRL-instansen, ange period och entitetsdetaljer.
## Steg 5: Lägg till enhet
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Definiera en enhet för XBRL-instansen och ange de kvalificerade måtten.
## Steg 6: Lägg till objekt
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
Lägg till ett objekt till XBRL-instansen och specificera dess koncept, sammanhang, enhet, precision och värde.
## Steg 7: Spara dokument
```csharp
document.Save(outputDir + @"document5.xbrl");
```
Spara XBRL-dokumentet i utdatakatalogen.
## Slutsats
Att lägga till objekt i ett XBRL-dokument är viktigt för att korrekt representera finansiella data. Aspose.Finance för .NET förenklar denna process genom att tillhandahålla ett omfattande API för att arbeta med XBRL-dokument i .NET-applikationer.
## Vanliga frågor
### Kan jag använda Aspose.Finance för .NET med någon .NET-applikation?
Ja, Aspose.Finance för .NET är kompatibel med alla .NET-applikationer, inklusive ASP.NET, WinForms och Console-applikationer.
### Är Aspose.Finance för .NET gratis att använda?
 Aspose.Finance för .NET är ett kommersiellt bibliotek. Du kan ladda ner en gratis testversion för att utvärdera dess funktioner, och licenser kan köpas från[här](https://purchase.aspose.com/buy).
### Stöder Aspose.Finance for .NET andra finansiella rapporteringsformat förutom XBRL?
Aspose.Finance för .NET fokuserar främst på XBRL-relaterad funktionalitet. Men Aspose erbjuder andra bibliotek för att arbeta med olika finansiella format.
### Hur kan jag få support för Aspose.Finance för .NET?
 Du kan få support för Aspose.Finance för .NET genom[officiellt forum](https://forum.aspose.com/c/finance/43)där du kan ställa frågor och interagera med andra användare och supportpersonal.
### Kan jag få en tillfällig licens för Aspose.Finance för .NET?
 Ja, tillfälliga licenser för Aspose.Finance för .NET är tillgängliga för teständamål. Du kan få en[här](https://purchase.aspose.com/temporary-license/).
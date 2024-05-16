---
title: Lägg till enhet till XBRL-dokument
linktitle: Lägg till enhet till XBRL-dokument
second_title: Aspose.Finance .NET API
description: Lär dig hur du lägger till enheter till XBRL-dokument utan ansträngning med Aspose.Finance för .NET. Förbättra dina finansiella databehandlingsmöjligheter idag!
type: docs
weight: 16
url: /sv/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
Välkommen till Aspose.Finance-världen för .NET - din inkörsport till effektiv finansiell dokumentmanipulation inom .NET-applikationer. Oavsett om du bygger bokföringsprogram, verktyg för finansiell analys eller någon annan finansiell tillämpning, utrustar Aspose.Finance för .NET dig med en omfattande uppsättning funktioner för att effektivisera din utvecklingsprocess.
## Förutsättningar
Innan vi fördjupar oss i att utnyttja kraften i Aspose.Finance för .NET, låt oss se till att vi har de nödvändiga förutsättningarna på plats:
### 1. Installation av Visual Studio
Se till att du har Visual Studio installerat på ditt system. Om inte kan du ladda ner och installera det från Microsofts officiella webbplats.
### 2. Skaffa en licens
 För att låsa upp den fulla potentialen hos Aspose.Finance för .NET behöver du en giltig licens. Du kan köpa en licens från[här](https://purchase.aspose.com/buy) eller välj en tillfällig licens för teständamål.
### 3. Ladda ner och referera till Aspose.Finance för .NET
 Ladda ner Aspose.Finance för .NET-biblioteket från[släpper sida](https://releases.aspose.com/finance/net/) och referera till det i ditt .NET-projekt.
### 4. Få tillgång till dokumentation och support
 Referera till[dokumentation](https://reference.aspose.com/finance/net/)för detaljerad information om hur du använder Aspose.Finance för .NET. Dessutom kan du söka hjälp från Aspose.Finance-communityt om[supportforum](https://forum.aspose.com/c/finance/43).
## Importera namnområden
Låt oss nu importera de nödvändiga namnrymden till ditt .NET-projekt:
## Steg 1: Lägg till Aspose.Finance Namespace
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Detta namnutrymme innehåller klasser och metoder som är viktiga för att arbeta med XBRL-dokument och data.
Låt oss dela upp exemplet i flera steg för att förstå hur man lägger till en enhet i ett XBRL-dokument med Aspose.Finance för .NET.
## Steg 1: Definiera utdatakatalog
```csharp
// Utdatakatalog
string outputDir = "Your Output Directory";
```
 Byta ut`"Your Output Directory"` med den faktiska sökvägen till din önskade utdatakatalog.
## Steg 2: Skapa ett XBRL-dokument
```csharp
XbrlDocument document = new XbrlDocument();
```
Detta initierar en ny instans av XBRL-dokumentet.
## Steg 3: Få åtkomst till XBRL-instanser
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Detta hämtar samlingen av XBRL-instanser från dokumentet och lägger till en ny instans till den.
## Steg 4: Lägg till enhet
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Detta skapar en ny måttenhet (i det här fallet USD) och lägger till den i XBRL-instansen. Du kan justera valutakoden och namnutrymmets URI efter behov.
## Steg 5: Spara dokumentet
```csharp
document.Save(outputDir + @"document4.xbrl");
```
Detta sparar det modifierade XBRL-dokumentet i den angivna utdatakatalogen.
## Slutsats
Sammanfattningsvis ger Aspose.Finance för .NET utvecklare möjlighet att enkelt manipulera finansiella dokument och data i sina .NET-applikationer. Genom att följa stegen som beskrivs i den här handledningen kan du sömlöst integrera Aspose.Finance för .NET i dina projekt och förbättra deras finansiella bearbetningsmöjligheter.
## Vanliga frågor
### 1. Kan jag använda Aspose.Finance för .NET utan licens?
Nej, en giltig licens krävs för att låsa upp alla funktioner i Aspose.Finance för .NET. Däremot finns tillfälliga licenser tillgängliga för teständamål.
### 2. Är Aspose.Finance för .NET lämpligt för att bygga bokföringsprogram?
Ja, Aspose.Finance för .NET tillhandahåller robusta funktioner som är skräddarsydda för att bygga bokföringsprogram och relaterade finansiella applikationer.
### 3. Var kan jag hitta support för Aspose.Finance för .NET?
Du kan söka hjälp från Aspose.Finance-communityt på supportforumet.
### 4. Kan jag anpassa måttenheten i ett XBRL-dokument?
Ja, du kan skapa och lägga till anpassade måttenheter till XBRL-dokument med Aspose.Finance för .NET.
### 5. Stöder Aspose.Finance för .NET flera valutor?
Ja, Aspose.Finance för .NET stöder flera valutor, vilket möjliggör mångsidig finansiell databehandling.
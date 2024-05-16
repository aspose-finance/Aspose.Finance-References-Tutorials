---
title: Lägg till schemareferens till XBRL-dokument
linktitle: Lägg till schemareferens till XBRL-dokument
second_title: Aspose.Finance .NET API
description: Lär dig hur du lägger till schemareferenser till XBRL-dokument med Aspose.Finance för .NET. Effektivisera din finansiella databehandling idag!
type: docs
weight: 15
url: /sv/net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## Vi presenterar Aspose.Finance för .NET
Aspose.Finance för .NET är ett kraftfullt bibliotek som tillhandahåller omfattande funktioner för bearbetning och manipulering av finansiella dokument och data inom .NET-applikationer. Oavsett om du bygger bokföringsprogram, verktyg för finansiell analys eller någon annan finansiell tillämpning, erbjuder Aspose.Finance för .NET ett brett utbud av funktioner för att effektivisera din utvecklingsprocess.
## Förutsättningar
Innan du börjar använda Aspose.Finance för .NET, se till att du har ställt in följande förutsättningar:
### 1. Installera Visual Studio
Se till att du har Visual Studio installerat på ditt system. Du kan ladda ner och installera det från Microsofts officiella webbplats.
### 2. Skaffa en Aspose.Finance-licens
För att kunna använda alla funktioner i Aspose.Finance för .NET måste du skaffa en giltig licens. Du kan köpa en licens från[här](https://purchase.aspose.com/buy) eller välj en tillfällig licens för teständamål.
### 3. Ladda ner och referera till Aspose.Finance för .NET
 Ladda ner Aspose.Finance för .NET-biblioteket från[släpper sida](https://releases.aspose.com/finance/net/) och referera till det i ditt .NET-projekt.
### 4. Få tillgång till dokumentation och support
 Referera till[API dokumentation](https://reference.aspose.com/finance/net/) för detaljerad information om hur du använder Aspose.Finance för .NET. Dessutom kan du söka hjälp från Aspose.Finance-communityt om[supportforum](https://forum.aspose.com/c/finance/43).
## Importera namnområden
Låt oss börja med att importera de nödvändiga namnrymden till ditt .NET-projekt:
## Steg 1: Lägg till Aspose.Finance Namespace
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Detta namnutrymme innehåller klasser och metoder för att arbeta med XBRL-dokument och data.
Låt oss nu dela upp exemplet i flera steg för att förstå hur man lägger till en schemareferens till ett XBRL-dokument med Aspose.Finance för .NET.
## Steg 1: Definiera käll- och utdatakataloger
```csharp
// Källkatalog
string sourceDir = "Your Source Directory";
// Utdatakatalog
string outputDir = "Your Output Directory";
```
 Byta ut`"Your Source Directory"` och`"Your Output Directory"`med de faktiska sökvägarna till dina käll- respektive utdatakataloger.
## Steg 2: Skapa ett XBRL-dokument
```csharp
XbrlDocument document = new XbrlDocument();
```
Detta skapar en ny instans av XBRL-dokumentet.
## Steg 3: Få åtkomst till XBRL-instanser
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Detta hämtar samlingen av XBRL-instanser från dokumentet och lägger till en ny instans till den.
## Steg 4: Lägg till Schema Reference
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomi");
```
 Detta lägger till en schemareferens till XBRL-instansen. Byta ut`"schema.xsd"` med det faktiska namnet på din schemafil,`"example"` med ett lämpligt prefix, och`"http://example.com/xbrl/taxonomy"` med målnamnutrymmets URI.
## Steg 5: Spara dokumentet
```csharp
document.Save(outputDir + @"document2.xbrl");
```
Detta sparar det modifierade XBRL-dokumentet i den angivna utdatakatalogen.
## Slutsats
Sammanfattningsvis erbjuder Aspose.Finance för .NET en robust lösning för hantering av finansiella dokument och data i .NET-applikationer. Genom att följa stegen som beskrivs i denna handledning kan du enkelt integrera Aspose.Finance i dina projekt och effektivt manipulera XBRL-dokument.
## Vanliga frågor
 (Vanliga frågor)
### 1. Kan jag använda Aspose.Finance för .NET utan licens?
Nej, du behöver en giltig licens för att använda alla funktioner i Aspose.Finance för .NET. Du kan dock få en tillfällig licens för teständamål.
### 2. Är Aspose.Finance lämplig för att bygga bokföringsprogram?
Ja, Aspose.Finance tillhandahåller omfattande funktioner för bearbetning av finansiell data, vilket gör den idealisk för att bygga bokföringsprogram och relaterade applikationer.
### 3. Var kan jag hitta support för Aspose.Finance?
Du kan söka hjälp från Aspose.Finance-communityt på det officiella supportforumet.
### 4. Kan jag anpassa schemareferensprefixet?
Ja, du kan välja ett lämpligt prefix när du lägger till en schemareferens till ett XBRL-dokument med Aspose.Finance för .NET.
### 5. Stöder Aspose.Finance andra finansiella format förutom XBRL?
Ja, Aspose.Finance stöder olika finansiella format och standarder, vilket möjliggör sömlös integrering i olika finansiella applikationer.
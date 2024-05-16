---
title: Läs XBRL-dokument
linktitle: Läs XBRL-dokument
second_title: Aspose.Finance .NET API
description: Lär dig hur du läser XBRL-dokument i .NET med Aspose.Finance. Förbättra dina finansiella databehandlingsmöjligheter utan ansträngning. #Aspose #Finans #XBRL
type: docs
weight: 11
url: /sv/net/xbrl-file-reading/read-xbrl-document/
---
## Introduktion
Aspose.Finance för .NET är ett robust finansiellt mjukvaruutvecklingsverktyg som ger utvecklare möjlighet att effektivt hantera finansiell data i sina .NET-applikationer. En av dess nyckelfunktioner är möjligheten att läsa XBRL-dokument (eXtensible Business Reporting Language) sömlöst. I den här omfattande guiden går vi igenom processen att läsa XBRL-dokument med Aspose.Finance för .NET. I slutet av den här handledningen har du en gedigen förståelse för hur du kan utnyttja den här funktionen för att förbättra dina finansiella databehandlingsmöjligheter.
## Förutsättningar
Innan vi dyker in i handledningen, låt oss se till att du har allt du behöver:
### .NET utvecklingsmiljö
Först och främst, se till att du har en .NET-utvecklingsmiljö inställd på din maskin. Om du inte redan har gjort det kan du ladda ner och installera den senaste versionen av .NET SDK från den officiella Microsoft-webbplatsen.
### Aspose.Finance för .NET
För att följa med i denna handledning måste du ha Aspose.Finance för .NET installerat i din utvecklingsmiljö. Du kan ladda ner biblioteket från den officiella nedladdningslänken nedan:
[Ladda ner Aspose.Finance för .NET](https://releases.aspose.com/finance/net/)
### XBRL-dokument
Förbered ett XBRL-dokument som du tänker läsa med Aspose.Finance för .NET. Se till att du har filsökvägen redo för referens i din kod.
## Importera namnområden
Låt oss börja med att importera de nödvändiga namnområdena till ditt .NET-projekt för att få tillgång till funktionerna i Aspose.Finance. Följ dessa steg-för-steg-instruktioner:
## Steg 1: Öppna ditt .NET-projekt
Starta ditt .NET-projekt i din föredragna Integrated Development Environment (IDE), som Visual Studio.
## Steg 2: Lägg till Aspose.Finance-referens
Lägg till en referens till Aspose.Finance för .NET i ditt projekt. Du kan uppnå detta genom att antingen ladda ner biblioteket och referera till det lokalt eller använda NuGet Package Manager för att installera det direkt i ditt projekt.
## Steg 3: Importera namnområden
Importera nu de nödvändiga namnrymden i början av din kodfil. Dessa namnrymder ger åtkomst till de klasser och metoder som behövs för att arbeta med XBRL-dokument.
```csharp
using Aspose.Finance.Xbrl;
using System;
using System.Collections.Generic;
```
## Läs XBRL-dokument
Nu när vi har ställt in vår miljö och importerat de nödvändiga namnområdena, låt oss dyka in i processen att läsa ett XBRL-dokument med Aspose.Finance för .NET. Följ dessa steg-för-steg-instruktioner:
## Steg 1: Definiera källkatalog
 Börja med att definiera katalogsökvägen där ditt XBRL-dokument finns. Byta ut`"Your Source Directory"` med den faktiska sökvägen till ditt dokument.
```csharp
string sourceDir = "Your Source Directory";
```
## Steg 2: Skapa XbrlDocument Object
 Skapa sedan en`XbrlDocument` objekt genom att ange sökvägen till ditt XBRL-dokument.
```csharp
XbrlDocument document = new XbrlDocument(sourceDir + @"IdScopeContextPeriodStartAfterEnd.xml");
```
## Steg 3: Få åtkomst till XBRL-instanser
 Få åtkomst till XBRL-instanserna från dokumentet med hjälp av`XbrlInstances` fast egendom.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[0];
```
## Steg 4: Extrahera fakta, schemareferenser, sammanhang och enheter
Hämta fakta, schemareferenser, sammanhang och enheter från XBRL-instansen.
```csharp
List<Fact> facts = xbrlInstance.Facts;
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
List<Context> contexts = xbrlInstance.Contexts;
List<Unit> units = xbrlInstance.Units;
```
## Steg 5: Visa framgångsmeddelande
Informera användaren om att XBRL-dokumentet har lästs.
```csharp
Console.WriteLine("ReadXbrlDocument executed successfully.");
```
Genom att följa dessa steg har du framgångsrikt läst ett XBRL-dokument med Aspose.Finance för .NET.
## Slutsats
I den här handledningen har vi täckt processen att läsa XBRL-dokument med Aspose.Finance för .NET. Genom att använda den medföljande steg-för-steg-guiden kan du effektivt hantera XBRL-dokument i dina .NET-applikationer, vilket förbättrar dina finansiella databehandlingsmöjligheter.
## Vanliga frågor
### Är Aspose.Finance för .NET kompatibel med alla versioner av .NET?
Ja, Aspose.Finance för .NET är designad för att vara kompatibel med alla versioner av .NET-ramverket, vilket säkerställer sömlös integrering i dina projekt.
### Kan jag använda Aspose.Finance för kommersiella projekt?
Absolut! Aspose.Finance för .NET kan användas för både personliga och kommersiella projekt. Köp helt enkelt en licens för att låsa upp dess fulla potential.
### Stöder Aspose.Finance andra dokumentformat än XBRL?
Ja, Aspose.Finance tillhandahåller stöd för olika finansiella dokumentformat, vilket erbjuder flexibilitet och mångsidighet vid hantering av finansiell data.
### Är teknisk support tillgänglig för Aspose.Finance-användare?
Säkert! Aspose erbjuder dedikerad teknisk support för sina produkter, inklusive Aspose.Finance. Du kan komma åt support via det officiella supportforumet.
### Kan jag prova Aspose.Finance innan jag köper?
Självklart! Aspose erbjuder en gratis testversion av Aspose.Finance, så att du kan utforska dess funktioner och möjligheter innan du gör ett åtagande.
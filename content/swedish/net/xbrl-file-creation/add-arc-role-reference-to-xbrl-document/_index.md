---
title: Lägg till ARC-rollreferens till XBRL-dokument
linktitle: Lägg till ARC-rollreferens till XBRL-dokument
second_title: Aspose.Finance .NET API
description: Lär dig hur du effektivt manipulerar XBRL-dokument med Aspose.Finance för .NET. Lägg till ARC-rollreferenser utan ansträngning med steg-för-steg-vägledning.
type: docs
weight: 10
url: /sv/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## Introduktion
en värld av finansiell datahantering och rapportering spelar eXtensible Business Reporting Language (XBRL) en avgörande roll. Den standardiserar hur finansiell information kommuniceras och utbyts, vilket säkerställer konsekvens, noggrannhet och effektivitet. Men att manipulera XBRL-dokument, särskilt när man införlivar specifika roller och referenser, kräver en nyanserad förståelse av de underliggande mekanismerna. Den här handledningen fokuserar på en sådan uppgift: att lägga till en ARC-rollreferens till ett XBRL-dokument med Aspose.Finance för .NET.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
### Miljöinställningar
1.  Installera Aspose.Finance for .NET: Ladda ner och installera Aspose.Finance for .NET-biblioteket från[släpper](https://releases.aspose.com/finance/net/).
   
2. Utvecklingsmiljö: Konfigurera din utvecklingsmiljö med Visual Studio eller någon annan föredragen IDE.
## Importera namnområden
Se till att importera de nödvändiga namnrymden i din C#-kod:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Steg 1: Definiera käll- och utdatakataloger
Innan du fortsätter, ange käll- och utdatakatalogen där dina XBRL-filer ska finnas respektive sparas.
```csharp
// Källkatalog
string sourceDir = "Your Source Directory";
// Utdatakatalog
string outputDir = "Your Output Directory";
```
## Steg 2: Skapa ett XBRL-dokument
 Instantiera en`XbrlDocument` objekt för att arbeta med XBRL-data.
```csharp
XbrlDocument document = new XbrlDocument();
```
## Steg 3: Öppna XbrlInstance Collection
Få tillgång till samlingen av XBRL-instanser i dokumentet.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## Steg 4: Lägg till XbrlInstance
Lägg till en ny XBRL-instans till samlingen.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Steg 5: Lägg till schemareferens
Inkludera en schemareferens i XBRL-instansen och ange källkatalog, namnområdesprefix och URI.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomi");
```
## Steg 6: Hämta ArcroleType
 Hämta`ArcroleType` baserat på en specifik URI.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## Steg 7: Lägg till ArcroleReference
 Om`ArcroleType` hittas, skapa en`ArcroleReference` och lägg till den i XBRL-instansens arcrole-referenser.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## Steg 8: Spara dokumentet
Spara det modifierade XBRL-dokumentet till den angivna utdatakatalogen.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## Slutsats
I den här handledningen har vi utforskat hur man lägger till en ARC-rollreferens till ett XBRL-dokument med Aspose.Finance för .NET. Genom att följa dessa steg-för-steg-instruktioner och utnyttja funktionerna i Aspose.Finance kan du effektivt hantera och manipulera XBRL-data för att möta dina specifika krav.
## Vanliga frågor
### Vad är XBRL?
XBRL står för eXtensible Business Reporting Language, ett standardiserat språk för elektronisk kommunikation av affärs- och finansdata.
### Varför är XBRL viktigt?
XBRL säkerställer konsekvens, noggrannhet och effektivitet i utbyte och analys av finansiell information, vilket gynnar tillsynsmyndigheter, analytiker och företag.
### Kan Aspose.Finance hantera komplexa XBRL-uppgifter?
Ja, Aspose.Finance erbjuder robusta funktioner för att arbeta med XBRL-dokument, inklusive hantering av komplexa uppgifter som rollreferenser och taxonomihantering.
### Är Aspose.Finance kompatibel med andra .NET-bibliotek?
Ja, Aspose.Finance integreras sömlöst med andra .NET-bibliotek, vilket ger omfattande stöd för finansiell datamanipulation och rapportering.
### Var kan jag hitta ytterligare support för Aspose.Finance?
 För ytterligare stöd besök[Aspose.Finance supportsida](https://forum.aspose.com/c/finance/43).
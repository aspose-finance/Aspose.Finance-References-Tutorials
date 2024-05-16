---
title: Lägg till sammanhang till XBRL-dokument
linktitle: Lägg till sammanhang till XBRL-dokument
second_title: Aspose.Finance .NET API
description: Lär dig hur du lägger till sammanhang till XBRL-dokument i .NET med Aspose.Finance för strömlinjeformad finansiell rapportering. #Aspose #Finans #XBRL
type: docs
weight: 11
url: /sv/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## Introduktion
Inom finansiell rapportering spelar XBRL (eXtensible Business Reporting Language) en central roll för att standardisera utbytet av affärsinformation. Att lägga till kontext till XBRL-dokument är avgörande för att säkerställa integriteten och relevansen av data de innehåller. Med Aspose.Finance för .NET blir denna process strömlinjeformad och effektiv, vilket gör det möjligt för utvecklare att sömlöst införliva sammanhang i sina XBRL-dokument.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
1. Aspose.Finance for .NET Library: Ladda ner och installera Aspose.Finance for .NET-biblioteket från[släpper](https://releases.aspose.com/finance/net/).
2. .NET-utvecklingsmiljö: Se till att du har en fungerande .NET-utvecklingsmiljö inställd på din dator.
3. Grundläggande förståelse för C#: Bekantskap med programmeringsspråket C# kommer att vara till hjälp när du följer exemplen.
## Importera namnområden
I ditt C#-projekt, importera de nödvändiga namnområdena för att komma åt funktionaliteten som tillhandahålls av Aspose.Finance för .NET:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Steg 1: Ställ in utdatakatalog
Innan du lägger till kontext till XBRL-dokumentet, ange utdatakatalogen där det ändrade dokumentet ska sparas:
```csharp
string outputDir = "Your Output Directory";
```
 Byta ut`"Your Output Directory"` med önskad sökväg på ditt system.
## Steg 2: Skapa XBRL-dokument
 Instantiera en`XbrlDocument` objekt för att arbeta med XBRL-dokument:
```csharp
XbrlDocument document = new XbrlDocument();
```
Detta objekt representerar XBRL-dokumentet som kommer att manipuleras.
## Steg 3: Lägg till XBRL-instans
Lägg till en XBRL-instans till dokumentet. Varje instans innehåller data för en specifik rapportperiod:
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Detta steg initierar en XBRL-instans i dokumentet.
## Steg 4: Definiera kontextperiod och enhet
Skapa en kontextperiod och entitet för XBRL-instansen:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
Ange period och enhetsinformation enligt dina rapporteringskrav.
## Steg 5: Skapa sammanhang
Konstruera ett sammanhang med den period och entitet som definierades i föregående steg:
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
Detta sammanhang kapslar in den tidsmässiga och entitetsrelaterade informationen.
## Steg 6: Lägg till kontext till XBRL-instans
Associera kontexten som skapades i föregående steg med XBRL-instansen:
```csharp
xbrlInstance.Contexts.Add(context);
```
Det här steget länkar sammanhanget till XBRL-instansen och ger relevant kontextuell information till data.
## Steg 7: Spara dokumentet
Spara det modifierade XBRL-dokumentet till den angivna utdatakatalogen:
```csharp
document.Save(outputDir + @"document3.xbrl");
```
Detta avslutar processen och sparar XBRL-dokumentet med det tillagda sammanhanget.
## Slutsats
Genom att följa dessa steg kan du effektivt lägga till kontext till XBRL-dokument med Aspose.Finance för .NET. Detta förbättrar tydligheten och användbarheten av finansiella data, vilket underlättar korrekt analys och rapportering.
## Vanliga frågor
### Kan Aspose.Finance för .NET hantera stora XBRL-dokument?
Aspose.Finance för .NET är optimerad för att hantera XBRL-dokument av varierande storlek, inklusive stora datamängder.
### Finns det en testversion tillgänglig för Aspose.Finance för .NET?
Ja, du kan ladda ner en gratis testversion från den officiella Aspose-webbplatsen.
### Stöder Aspose.Finance för .NET andra finansiella rapporteringsstandarder förutom XBRL?
Aspose.Finance fokuserar främst på XBRL-relaterade funktionaliteter men ger även stöd för andra finansiella format.
### Kan jag anpassa kontextinformationen efter mina specifika krav?
Absolut, Aspose.Finance för .NET erbjuder flexibilitet för att anpassa kontextinformation för att passa dina behov.
### Var kan jag hitta ytterligare support eller resurser för Aspose.Finance för .NET?
Du kan besöka Aspose.Finance-forumet för hjälp från samhället eller utforska dokumentationen för omfattande vägledning.
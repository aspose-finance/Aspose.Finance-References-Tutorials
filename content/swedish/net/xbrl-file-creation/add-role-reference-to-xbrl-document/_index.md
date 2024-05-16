---
title: Lägg till rollreferens till XBRL-dokument
linktitle: Lägg till rollreferens till XBRL-dokument
second_title: Aspose.Finance .NET API
description: Lär dig hur du lägger till rollreferenser till XBRL-dokument med Aspose.Finance för .NET. Förenkla finansiell rapportering i dina .NET-applikationer med denna handledning.
type: docs
weight: 14
url: /sv/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (eXtensible Business Reporting Language) har blivit en standard för utbyte av affärsinformation, särskilt inom finansiell rapportering. Aspose.Finance för .NET förenklar arbetet med XBRL-dokument i .NET-applikationer. Denna handledning guidar dig genom processen att lägga till en rollreferens till ett XBRL-dokument med Aspose.Finance för .NET.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
### 1. Installera Aspose.Finance för .NET
Se till att du har Aspose.Finance för .NET installerat i din utvecklingsmiljö. Om du inte redan har gjort det, ladda ner den från[släpper](https://releases.aspose.com/finance/net/) och följ installationsanvisningarna.
### 2. Ställ in din utvecklingsmiljö
Se till att du har en fungerande utvecklingsmiljö för .NET-utveckling. Detta inkluderar en kompatibel IDE som Visual Studio och .NET-ramverket installerat på ditt system.
## Importera namnområden
Börja med att importera de nödvändiga namnområdena till din .NET-applikation för att få tillgång till funktionerna som tillhandahålls av Aspose.Finance för .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## Steg 4: Hämta rolltyp och lägg till rollreferens
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
Hämta rolltypen med dess URI och lägg till en rollreferens till XBRL-instansen.
## Steg 5: Spara dokument
```csharp
document.Save(outputDir + @"document7.xbrl");
```
Spara XBRL-dokumentet i utdatakatalogen.
## Slutsats
Att lägga till rollreferenser till XBRL-dokument är avgörande för att definiera rollerna för olika element i dokumentet. Aspose.Finance för .NET ger ett enkelt sätt att utföra denna uppgift, vilket ger utvecklare möjlighet att effektivt arbeta med XBRL-dokument i sina .NET-applikationer.
## Vanliga frågor
### Kan jag använda Aspose.Finance för .NET med någon .NET-applikation?
Ja, Aspose.Finance för .NET är kompatibel med alla .NET-applikationer, inklusive ASP.NET, WinForms och Console-applikationer.
### Är Aspose.Finance för .NET gratis att använda?
 Aspose.Finance för .NET är ett kommersiellt bibliotek. Du kan ladda ner en gratis testversion för att utvärdera dess funktioner, och licenser kan köpas från[här](https://purchase.aspose.com/buy).
### Stöder Aspose.Finance for .NET andra finansiella rapporteringsformat förutom XBRL?
Aspose.Finance för .NET fokuserar främst på XBRL-relaterad funktionalitet. Men Aspose erbjuder andra bibliotek för att arbeta med olika finansiella format.
### Hur kan jag få support för Aspose.Finance för .NET?
 Du kan få support för Aspose.Finance för .NET genom[forum](https://forum.aspose.com/c/finance/43)där du kan ställa frågor och interagera med andra användare och supportpersonal.
### Kan jag få en tillfällig licens för Aspose.Finance för .NET?
 Ja, tillfälliga licenser för Aspose.Finance för .NET är tillgängliga för teständamål. Du kan få en[här](https://purchase.aspose.com/temporary-license/).
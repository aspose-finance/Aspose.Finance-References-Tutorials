---
title: Skapa fil för OFX-banktransaktionsbegäran
linktitle: Skapa fil för OFX-banktransaktionsbegäran
second_title: Aspose.Finance .NET API
description: Lär dig hur du skapar en OFX-banktransaktionsbegäran med Aspose.Finance för .NET med vår detaljerade steg-för-steg-guide. #Aspose #Finans
type: docs
weight: 12
url: /sv/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
Att skapa en fil för OFX-banktransaktioner kan verka skrämmande, men med rätt verktyg och vägledning kan det vara en enkel process. I den här handledningen går vi igenom varje steg för att generera en OFX-banktransaktionsbegäran med Aspose.Finance för .NET. Vi kommer att täcka förutsättningarna, de nödvändiga namnutrymmena och tillhandahålla en detaljerad, steg-för-steg-guide för att säkerställa att du enkelt kan följa med.
## Förutsättningar
Innan vi dyker in i handledningen finns det några saker du måste ha på plats:
1.  Visual Studio: Se till att du har Visual Studio installerat på din dator. Du kan ladda ner den från[officiell hemsida](https://visualstudio.microsoft.com/).
2.  Aspose.Finance for .NET: Du behöver Aspose.Finance for .NET-biblioteket. Du kan ladda ner den från[här](https://releases.aspose.com/finance/net/).
3. Grundläggande C#-kunskap: Att förstå grunderna i C#-programmering hjälper dig att följa med i kodexemplen.
När du har dessa förutsättningar på plats är du redo att börja!
## Importera namnområden
Låt oss först importera de nödvändiga namnrymden. Dessa namnutrymmen är avgörande för att komma åt de klasser och metoder som krävs för att skapa OFX-banktransaktionsbegäran.
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## Steg 1: Konfigurera arbetskatalogen
Innan vi börjar skapa OFX-förfrågningsfilen måste vi ange utdatakatalogen där filen ska sparas.
```csharp
string outputDir = "Your Output Directory";
```
 Byta ut`"Your Output Directory"` med sökvägen till katalogen där du vill spara den genererade filen.
## Steg 2: Skapa OFX Request Document
 Därefter måste vi skapa en instans av`OfxRequestDocument` klass. Den här klassen kommer att fungera som behållaren för vår OFX-förfrågan.
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## Steg 3: Konfigurera inloggningsförfrågan
Signon-begäran är viktig för att autentisera användaren och initiera OFX-sessionen. Vi ställer in meddelandet om inloggningsförfrågan och fyller i det med nödvändig information som kunddatum, användar-ID, lösenord och information om finansinstitut.
```csharp
document.SignonRequestMessageSetV1 = new SignonRequestMessageSetV1();
SignonRequest signonRequest = new SignonRequest();
document.SignonRequestMessageSetV1.SignonRequest = signonRequest;
signonRequest.ClientDate = "20200611000000";
signonRequest.UserId = "aspose";
signonRequest.UserPassword = "password";
FinancialInstitution fi = new FinancialInstitution();
fi.Organization = "aspose";
fi.FinancialInstitutionId = "1";
signonRequest.FinancialInstitution = fi;
signonRequest.AppVersion = "1.0";
signonRequest.AppId = "Aspose.Finance";
signonRequest.ClientUserId = "aaaaaaa";
```
## Steg 4: Ställ in meddelandet om bankförfrågan
Nu när inloggningsbegäran är konfigurerad går vi vidare till att skapa meddelandet om bankförfrågan. Detta meddelande kommer att innehålla information om bankkontot och begäran om transaktionsutdrag.
```csharp
document.BankRequestMessageSetV1 = new BankRequestMessageSetV1();
StatementTransactionRequest stmtTransRequest = new StatementTransactionRequest();
document.BankRequestMessageSetV1.StatementTransactionRequests.Add(stmtTransRequest);
stmtTransRequest.TransactionUniqueId = "1111111";
stmtTransRequest.StatementRequest = new StatementRequest();
stmtTransRequest.StatementRequest.BankAccountFrom = new BankAccount();
stmtTransRequest.StatementRequest.BankAccountFrom.BankId = "sssss";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountId = "sfsdfsfsdf";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountType = AccountEnum.CHECKING;
```
## Steg 5: Inkludera transaktionsinformation
 För att hämta specifika transaktioner måste vi ange datumintervallet och om transaktioner ska inkluderas i begäran. Detta görs genom att ställa in`IncTransaction` objekt.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## Steg 6: Spara OFX Request Document
Slutligen kommer vi att spara OFX-förfrågningsdokumentet i både XML- och SGML-format. Detta säkerställer kompatibilitet med olika system som kan använda båda formaten.
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## Steg 7: Bekräfta framgångsrik exekvering
För att bekräfta att processen utfördes framgångsrikt kan vi skriva ut ett meddelande till konsolen.
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## Slutsats
Att skapa en OFX-banktransaktionsförfrågningsfil med Aspose.Finance för .NET är en metodisk process som involverar att ställa in ett förfrågningsdokument, konfigurera inloggnings- och bankförfrågningsmeddelanden, specificera transaktionsdetaljer och spara dokumentet. Genom att följa denna steg-för-steg-guide kan du effektivt generera OFX-förfrågningsfiler som är skräddarsydda för dina specifika behov.
## Vanliga frågor
### 1. Vad är en OFX-fil?
En OFX-fil (Open Financial Exchange) är ett standardformat som används för att utbyta finansiell data mellan institutioner och användare. Det används ofta för kontoutdrag, transaktioner och andra finansiella aktiviteter.
### 2. Kan jag använda Aspose.Finance för .NET med andra programmeringsspråk?
Aspose.Finance för .NET är speciellt utformad för användning med .NET-språk som C#. Du kan dock använda den i vilken .NET-stödd miljö som helst.
### 3. Finns det en gratis testversion tillgänglig för Aspose.Finance för .NET?
Ja, du kan ladda ner en gratis testversion av Aspose.Finance för .NET från[här](https://releases.aspose.com/).
### 4. Hur får jag support för Aspose.Finance för .NET?
 Du kan få support från Aspose-communityt och det tekniska teamet genom deras[supportforum](https://forum.aspose.com/c/finance/43).
### 5. Kan jag få en tillfällig licens för Aspose.Finance för .NET?
 Ja, Aspose erbjuder en[tillfällig licens](https://purchase.aspose.com/temporary-license/) som du kan använda för att utvärdera produkten.
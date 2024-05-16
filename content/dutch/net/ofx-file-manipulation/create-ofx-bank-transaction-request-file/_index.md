---
title: OFX-banktransactieverzoekbestand maken
linktitle: OFX-banktransactieverzoekbestand maken
second_title: Aspose.Finance .NET-API
description: Leer hoe u een OFX-banktransactieverzoekbestand maakt met Aspose.Finance voor .NET met onze gedetailleerde, stapsgewijze handleiding. #Aspose #Financiën
type: docs
weight: 12
url: /nl/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
Het maken van een OFX-banktransactieverzoekbestand lijkt misschien lastig, maar met de juiste tools en begeleiding kan het een eenvoudig proces zijn. In deze zelfstudie begeleiden we u bij elke stap van het genereren van een OFX-banktransactieverzoekbestand met Aspose.Finance voor .NET. We bespreken de vereisten, de benodigde naamruimten en bieden een gedetailleerde, stapsgewijze handleiding zodat u deze gemakkelijk kunt volgen.
## Vereisten
Voordat we ingaan op de tutorial, zijn er een paar dingen die je moet regelen:
1.  Visual Studio: Zorg ervoor dat Visual Studio op uw computer is geïnstalleerd. Je kunt het downloaden van de[officiële website](https://visualstudio.microsoft.com/).
2.  Aspose.Finance voor .NET: U hebt de Aspose.Finance voor .NET-bibliotheek nodig. Je kunt het downloaden van[hier](https://releases.aspose.com/finance/net/).
3. Basiskennis van C#: Als u de basisprincipes van C#-programmeren begrijpt, kunt u de codevoorbeelden volgen.
Zodra u aan deze vereisten voldoet, bent u klaar om aan de slag te gaan!
## Naamruimten importeren
Laten we eerst de benodigde naamruimten importeren. Deze naamruimten zijn cruciaal voor toegang tot de klassen en methoden die nodig zijn om het OFX-banktransactieverzoekbestand te maken.
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## Stap 1: Stel de werkmap in
Voordat we beginnen met het maken van het OFX-verzoekbestand, moeten we de uitvoermap opgeven waar het bestand zal worden opgeslagen.
```csharp
string outputDir = "Your Output Directory";
```
 Vervangen`"Your Output Directory"` met het pad naar de map waar u het gegenereerde bestand wilt opslaan.
## Stap 2: Maak het OFX-aanvraagdocument
 Vervolgens moeten we een exemplaar maken van de`OfxRequestDocument` klas. Deze klasse zal dienen als container voor ons OFX-verzoek.
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## Stap 3: Stel het aanmeldingsverzoek in
Het aanmeldingsverzoek is essentieel voor het authenticeren van de gebruiker en het starten van de OFX-sessie. We stellen het aanmeldingsverzoekbericht in en vullen het in met de nodige details, zoals de klantdatum, gebruikers-ID, wachtwoord en informatie over de financiële instelling.
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
## Stap 4: Stel het bankverzoekbericht in
Nu het aanmeldingsverzoek is ingesteld, gaan we verder met het maken van het bankverzoekbericht. Dit bericht bevat de gegevens van de bankrekening en het verzoek om een transactieoverzicht.
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
## Stap 5: Voeg transactiegegevens toe
 Om specifieke transacties op te halen, moeten we het datumbereik specificeren en of transacties in het verzoek moeten worden opgenomen. Dit wordt gedaan door het instellen van de`IncTransaction` voorwerp.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## Stap 6: Bewaar het OFX-aanvraagdocument
Ten slotte slaan we het OFX-verzoekdocument op in zowel XML- als SGML-indeling. Dit garandeert compatibiliteit met verschillende systemen die beide formaten kunnen gebruiken.
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## Stap 7: Bevestig succesvolle uitvoering
Om te bevestigen dat het proces succesvol is uitgevoerd, kunnen we een bericht naar de console afdrukken.
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## Conclusie
Het maken van een OFX-banktransactieverzoekbestand met Aspose.Finance voor .NET is een methodisch proces waarbij een verzoekdocument wordt opgezet, aanmeldings- en bankverzoekberichten worden geconfigureerd, transactiedetails worden gespecificeerd en het document wordt opgeslagen. Door deze stapsgewijze handleiding te volgen, kunt u efficiënt OFX-aanvraagbestanden genereren die zijn afgestemd op uw specifieke behoeften.
## Veelgestelde vragen
### 1. Wat is een OFX-bestand?
Een OFX-bestand (Open Financial Exchange) is een standaardformaat dat wordt gebruikt voor het uitwisselen van financiële gegevens tussen instellingen en gebruikers. Het wordt veel gebruikt voor bankafschriften, transacties en andere financiële activiteiten.
### 2. Kan ik Aspose.Finance voor .NET gebruiken met andere programmeertalen?
Aspose.Finance voor .NET is speciaal ontworpen voor gebruik met .NET-talen zoals C#. U kunt het echter in elke door .NET ondersteunde omgeving gebruiken.
### 3. Is er een gratis proefversie beschikbaar voor Aspose.Finance voor .NET?
Ja, u kunt een gratis proefversie van Aspose.Finance voor .NET downloaden van[hier](https://releases.aspose.com/).
### 4. Hoe krijg ik ondersteuning voor Aspose.Finance voor .NET?
 U kunt ondersteuning krijgen van de Aspose-gemeenschap en het technische team via hun[Helpforum](https://forum.aspose.com/c/finance/43).
### 5. Kan ik een tijdelijke licentie krijgen voor Aspose.Finance voor .NET?
 Ja, Aspose biedt een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) waarmee u het product kunt beoordelen.
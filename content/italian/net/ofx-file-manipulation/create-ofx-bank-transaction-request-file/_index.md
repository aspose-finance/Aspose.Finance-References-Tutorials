---
title: Crea file di richiesta di transazione bancaria OFX
linktitle: Crea file di richiesta di transazione bancaria OFX
second_title: API Aspose.Finance .NET
description: Scopri come creare un file di richiesta di transazione bancaria OFX utilizzando Aspose.Finance per .NET con la nostra guida dettagliata passo passo. #Aspose #Finanza
type: docs
weight: 12
url: /it/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
La creazione di un file di richiesta di transazione bancaria OFX potrebbe sembrare scoraggiante, ma con gli strumenti e le indicazioni giuste, può essere un processo semplice. In questo tutorial, ti guideremo attraverso ogni passaggio della generazione di un file di richiesta di transazione bancaria OFX utilizzando Aspose.Finance per .NET. Tratteremo i prerequisiti, gli spazi dei nomi necessari e forniremo una guida dettagliata passo dopo passo per assicurarti di poter seguire facilmente.
## Prerequisiti
Prima di immergerci nel tutorial, ci sono alcune cose che dovrai avere a disposizione:
1.  Visual Studio: assicurati di avere Visual Studio installato sul tuo computer. Puoi scaricarlo da[Sito ufficiale](https://visualstudio.microsoft.com/).
2.  Aspose.Finance per .NET: è necessaria la libreria Aspose.Finance per .NET. Puoi scaricarlo da[Qui](https://releases.aspose.com/finance/net/).
3. Conoscenza di base di C#: comprendere le basi della programmazione C# ti aiuterà a seguire gli esempi di codice.
Una volta stabiliti questi prerequisiti, sei pronto per iniziare!
## Importa spazi dei nomi
Per prima cosa importiamo gli spazi dei nomi necessari. Questi spazi dei nomi sono fondamentali per accedere alle classi e ai metodi richiesti per creare il file di richiesta di transazione bancaria OFX.
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## Passaggio 1: impostare la directory di lavoro
Prima di iniziare a creare il file di richiesta OFX, dobbiamo specificare la directory di output in cui verrà salvato il file.
```csharp
string outputDir = "Your Output Directory";
```
 Sostituire`"Your Output Directory"` con il percorso della directory in cui si desidera salvare il file generato.
## Passaggio 2: crea il documento di richiesta OFX
 Successivamente, dobbiamo creare un'istanza di`OfxRequestDocument` classe. Questa classe fungerà da contenitore per la nostra richiesta OFX.
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## Passaggio 3: impostare la richiesta di accesso
La richiesta di accesso è essenziale per autenticare l'utente e avviare la sessione OFX. Imposteremo il messaggio di richiesta di accesso e lo popoleremo con i dettagli necessari come la data del cliente, l'ID utente, la password e le informazioni sull'istituto finanziario.
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
## Passaggio 4: imposta il messaggio di richiesta bancaria
Ora che la richiesta di accesso è stata configurata, passeremo alla creazione del messaggio di richiesta bancaria. Questo messaggio conterrà i dettagli del conto bancario e la richiesta di estratto conto della transazione.
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
## Passaggio 5: includi i dettagli della transazione
 Per recuperare transazioni specifiche, dobbiamo specificare l'intervallo di date e se includere le transazioni nella richiesta. Questo viene fatto impostando il file`IncTransaction` oggetto.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## Passaggio 6: salva il documento di richiesta OFX
Infine, salveremo il documento di richiesta OFX nei formati XML e SGML. Ciò garantisce la compatibilità con diversi sistemi che possono utilizzare entrambi i formati.
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## Passaggio 7: conferma dell'esecuzione riuscita
Per confermare che il processo è stato eseguito correttamente, possiamo stampare un messaggio sulla console.
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## Conclusione
La creazione di un file di richiesta di transazione bancaria OFX utilizzando Aspose.Finance per .NET è un processo metodico che prevede l'impostazione di un documento di richiesta, la configurazione dei messaggi di accesso e di richiesta bancaria, la specifica dei dettagli della transazione e il salvataggio del documento. Seguendo questa guida passo passo, puoi generare in modo efficiente file di richiesta OFX su misura per le tue esigenze specifiche.
## Domande frequenti
### 1. Cos'è un file OFX?
Un file OFX (Open Financial Exchange) è un formato standard utilizzato per lo scambio di dati finanziari tra istituzioni e utenti. È ampiamente utilizzato per estratti conto, transazioni e altre attività finanziarie.
### 2. Posso utilizzare Aspose.Finance per .NET con altri linguaggi di programmazione?
Aspose.Finance per .NET è specificamente progettato per l'uso con linguaggi .NET come C#. Tuttavia, puoi utilizzarlo in qualsiasi ambiente supportato da .NET.
### 3. È disponibile una prova gratuita per Aspose.Finance per .NET?
Sì, puoi scaricare una prova gratuita di Aspose.Finance per .NET da[Qui](https://releases.aspose.com/).
### 4. Come posso ottenere supporto per Aspose.Finance per .NET?
 Puoi ottenere supporto dalla comunità Aspose e dal team tecnico tramite il loro[Forum di assistenza](https://forum.aspose.com/c/finance/43).
### 5. Posso ottenere una licenza temporanea per Aspose.Finance per .NET?
 Sì, Aspose offre a[licenza temporanea](https://purchase.aspose.com/temporary-license/) che puoi utilizzare per valutare il prodotto.
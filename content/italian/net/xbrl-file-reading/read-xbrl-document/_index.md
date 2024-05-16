---
title: Leggi il documento XBRL
linktitle: Leggi il documento XBRL
second_title: API Aspose.Finance .NET
description: Scopri come leggere documenti XBRL in .NET utilizzando Aspose.Finance. Migliora le tue capacità di elaborazione dei dati finanziari senza sforzo. #Aspose #Finanza #XBRL
type: docs
weight: 11
url: /it/net/xbrl-file-reading/read-xbrl-document/
---
## introduzione
Aspose.Finance per .NET è un robusto strumento di sviluppo di software finanziario che consente agli sviluppatori di gestire in modo efficiente i dati finanziari all'interno delle loro applicazioni .NET. Una delle sue caratteristiche principali è la capacità di leggere documenti XBRL (eXtensible Business Reporting Language) senza problemi. In questa guida completa, analizzeremo il processo di lettura dei documenti XBRL utilizzando Aspose.Finance per .NET. Al termine di questo tutorial avrai una conoscenza approfondita di come sfruttare questa funzionalità per migliorare le tue capacità di elaborazione dei dati finanziari.
## Prerequisiti
Prima di immergerci nel tutorial, assicuriamoci di avere tutto ciò di cui hai bisogno:
### Ambiente di sviluppo .NET
Innanzitutto, assicurati di avere un ambiente di sviluppo .NET configurato sul tuo computer. Se non l'hai già fatto, puoi scaricare e installare la versione più recente di .NET SDK dal sito Web ufficiale di Microsoft.
### Aspose.Finance per .NET
Per seguire questo tutorial, dovrai avere Aspose.Finance per .NET installato nel tuo ambiente di sviluppo. È possibile scaricare la libreria dal collegamento di download ufficiale fornito di seguito:
[Scarica Aspose.Finance per .NET](https://releases.aspose.com/finance/net/)
### Documento XBRL
Preparare un documento XBRL che intendi leggere utilizzando Aspose.Finance per .NET. Assicurati di avere il percorso del file pronto per fare riferimento nel tuo codice.
## Importa spazi dei nomi
Iniziamo importando gli spazi dei nomi necessari nel tuo progetto .NET per accedere alle funzionalità di Aspose.Finance. Segui queste istruzioni passo passo:
## Passaggio 1: apri il tuo progetto .NET
Avvia il tuo progetto .NET nel tuo ambiente di sviluppo integrato (IDE) preferito, come Visual Studio.
## Passaggio 2: aggiungere il riferimento Aspose.Finance
Aggiungi un riferimento ad Aspose.Finance per .NET nel tuo progetto. Puoi ottenere questo risultato scaricando la libreria e facendovi riferimento localmente oppure usando NuGet Package Manager per installarla direttamente nel tuo progetto.
## Passaggio 3: importare gli spazi dei nomi
Ora importa gli spazi dei nomi richiesti all'inizio del file di codice. Questi spazi dei nomi forniscono l'accesso alle classi e ai metodi necessari per lavorare con i documenti XBRL.
```csharp
using Aspose.Finance.Xbrl;
using System;
using System.Collections.Generic;
```
## Leggi il documento XBRL
Ora che abbiamo configurato il nostro ambiente e importato gli spazi dei nomi necessari, immergiamoci nel processo di lettura di un documento XBRL utilizzando Aspose.Finance per .NET. Segui queste istruzioni passo passo:
## Passaggio 1: definire la directory di origine
 Inizia definendo il percorso della directory in cui si trova il tuo documento XBRL. Sostituire`"Your Source Directory"` con il percorso effettivo del documento.
```csharp
string sourceDir = "Your Source Directory";
```
## Passaggio 2: crea l'oggetto XbrlDocument
 Successivamente, crea un file`XbrlDocument` oggetto fornendo il percorso del documento XBRL.
```csharp
XbrlDocument document = new XbrlDocument(sourceDir + @"IdScopeContextPeriodStartAfterEnd.xml");
```
## Passaggio 3: accedi alle istanze XBRL
 Accedi alle istanze XBRL dal documento utilizzando il file`XbrlInstances` proprietà.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[0];
```
## Passaggio 4: estrazione di fatti, riferimenti a schemi, contesti e unità
Recupera fatti, riferimenti a schemi, contesti e unità dall'istanza XBRL.
```csharp
List<Fact> facts = xbrlInstance.Facts;
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
List<Context> contexts = xbrlInstance.Contexts;
List<Unit> units = xbrlInstance.Units;
```
## Passaggio 5: Visualizza il messaggio di successo
Informa l'utente che il documento XBRL è stato letto correttamente.
```csharp
Console.WriteLine("ReadXbrlDocument executed successfully.");
```
Seguendo questi passaggi, hai letto con successo un documento XBRL utilizzando Aspose.Finance per .NET.
## Conclusione
In questo tutorial, abbiamo trattato il processo di lettura dei documenti XBRL utilizzando Aspose.Finance per .NET. Sfruttando la guida passo passo fornita, puoi gestire in modo efficiente i documenti XBRL all'interno delle tue applicazioni .NET, migliorando le tue capacità di elaborazione dei dati finanziari.
## Domande frequenti
### Aspose.Finance per .NET è compatibile con tutte le versioni di .NET?
Sì, Aspose.Finance per .NET è progettato per essere compatibile con tutte le versioni del framework .NET, garantendo una perfetta integrazione nei tuoi progetti.
### Posso utilizzare Aspose.Finance per progetti commerciali?
Assolutamente! Aspose.Finance per .NET può essere utilizzato sia per progetti personali che commerciali. Basta acquistare una licenza per sbloccare tutto il suo potenziale.
### Aspose.Finance supporta altri formati di documenti oltre a XBRL?
Sì, Aspose.Finance fornisce supporto per vari formati di documenti finanziari, offrendo flessibilità e versatilità nella gestione dei dati finanziari.
### Il supporto tecnico è disponibile per gli utenti Aspose.Finance?
Certamente! Aspose offre supporto tecnico dedicato per i suoi prodotti, incluso Aspose.Finance. Puoi accedere al supporto tramite il forum di supporto ufficiale.
### Posso provare Aspose.Finance prima di effettuare un acquisto?
Ovviamente! Aspose offre una versione di prova gratuita di Aspose.Finance, che ti consente di esplorarne le caratteristiche e le capacità prima di prendere un impegno.
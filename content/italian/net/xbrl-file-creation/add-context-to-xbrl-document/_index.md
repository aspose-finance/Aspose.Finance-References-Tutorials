---
title: Aggiungi contesto al documento XBRL
linktitle: Aggiungi contesto al documento XBRL
second_title: API Aspose.Finance .NET
description: Scopri come aggiungere contesto ai documenti XBRL in .NET utilizzando Aspose.Finance per un reporting finanziario semplificato. #Aspose #Finanza #XBRL
type: docs
weight: 11
url: /it/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## introduzione
Nel campo del reporting finanziario, XBRL (eXtensible Business Reporting Language) svolge un ruolo fondamentale nella standardizzazione dello scambio di informazioni aziendali. L'aggiunta di contesto ai documenti XBRL è fondamentale per garantire l'integrità e la pertinenza dei dati in essi contenuti. Con Aspose.Finance per .NET, questo processo diventa snello ed efficiente, consentendo agli sviluppatori di incorporare perfettamente il contesto nei propri documenti XBRL.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
1. Aspose.Finance per .NET Library: scaricare e installare la libreria Aspose.Finance per .NET dal[rilascia](https://releases.aspose.com/finance/net/).
2. Ambiente di sviluppo .NET: assicurati di avere un ambiente di sviluppo .NET funzionante configurato sul tuo computer.
3. Comprensione di base di C#: la familiarità con il linguaggio di programmazione C# sarà utile per seguire gli esempi.
## Importa spazi dei nomi
Nel tuo progetto C#, importa gli spazi dei nomi necessari per accedere alle funzionalità fornite da Aspose.Finance per .NET:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Passaggio 1: imposta la directory di output
Prima di aggiungere contesto al documento XBRL, specificare la directory di output in cui verrà salvato il documento modificato:
```csharp
string outputDir = "Your Output Directory";
```
 Sostituire`"Your Output Directory"` con il percorso desiderato sul tuo sistema.
## Passaggio 2: crea il documento XBRL
 Istanziare un`XbrlDocument` oggetto di lavorare con documenti XBRL:
```csharp
XbrlDocument document = new XbrlDocument();
```
Questo oggetto rappresenta il documento XBRL che verrà manipolato.
## Passaggio 3: aggiungi l'istanza XBRL
Aggiungi un'istanza XBRL al documento. Ogni istanza contiene i dati per un periodo di riferimento specifico:
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Questo passaggio inizializza un'istanza XBRL all'interno del documento.
## Passaggio 4: definire il periodo e l'entità del contesto
Crea un periodo di contesto e un'entità per l'istanza XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
Specifica il periodo e i dettagli dell'entità in base ai tuoi requisiti di reporting.
## Passaggio 5: crea contesto
Costruisci un contesto utilizzando il periodo e l'entità definiti nel passaggio precedente:
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
Questo contesto incapsula le informazioni temporali e relative all'entità.
## Passaggio 6: aggiungi contesto all'istanza XBRL
Associa il contesto creato nel passaggio precedente all'istanza XBRL:
```csharp
xbrlInstance.Contexts.Add(context);
```
Questo passaggio collega il contesto all'istanza XBRL, fornendo informazioni contestuali rilevanti ai dati.
## Passaggio 7: salva il documento
Salva il documento XBRL modificato nella directory di output specificata:
```csharp
document.Save(outputDir + @"document3.xbrl");
```
Questo finalizza il processo, salvando il documento XBRL con il contesto aggiunto.
## Conclusione
Seguendo questi passaggi, puoi aggiungere efficacemente contesto ai documenti XBRL utilizzando Aspose.Finance per .NET. Ciò migliora la chiarezza e l'usabilità dei dati finanziari, facilitando analisi e reporting accurati.
## Domande frequenti
### Aspose.Finance per .NET può gestire documenti XBRL di grandi dimensioni?
Aspose.Finance per .NET è ottimizzato per gestire documenti XBRL di varie dimensioni, inclusi set di dati di grandi dimensioni.
### È disponibile una versione di prova per Aspose.Finance per .NET?
Sì, puoi scaricare una versione di prova gratuita dal sito web ufficiale di Aspose.
### Aspose.Finance per .NET supporta altri standard di rendicontazione finanziaria oltre a XBRL?
Aspose.Finance si concentra principalmente sulle funzionalità relative a XBRL ma fornisce anche supporto per altri formati finanziari.
### Posso personalizzare le informazioni di contesto in base alle mie esigenze specifiche?
Assolutamente, Aspose.Finance per .NET offre flessibilità per personalizzare le informazioni sul contesto in base alle proprie esigenze.
### Dove posso trovare ulteriore supporto o risorse per Aspose.Finance per .NET?
È possibile visitare il forum Aspose.Finance per ricevere assistenza dalla comunità o esplorare la documentazione per una guida completa.
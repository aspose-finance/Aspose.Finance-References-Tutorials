---
title: Aggiungi riferimento al ruolo ARC al documento XBRL
linktitle: Aggiungi riferimento al ruolo ARC al documento XBRL
second_title: API Aspose.Finance .NET
description: Scopri come manipolare in modo efficiente i documenti XBRL utilizzando Aspose.Finance per .NET. Aggiungi facilmente riferimenti al ruolo ARC con una guida passo passo.
type: docs
weight: 10
url: /it/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## introduzione
Nel mondo della gestione e del reporting dei dati finanziari, l’eXtensible Business Reporting Language (XBRL) gioca un ruolo cruciale. Standardizza il modo in cui le informazioni finanziarie vengono comunicate e scambiate, garantendo coerenza, accuratezza ed efficienza. Tuttavia, la manipolazione dei documenti XBRL, soprattutto quando si incorporano ruoli e riferimenti specifici, richiede una comprensione approfondita dei meccanismi sottostanti. Questo tutorial si concentra su una di queste attività: aggiungere un riferimento al ruolo ARC a un documento XBRL utilizzando Aspose.Finance per .NET.
## Prerequisiti
Prima di immergerti nel tutorial, assicurati di possedere i seguenti prerequisiti:
### Configurazione dell'ambiente
1.  Installa Aspose.Finance per .NET: scarica e installa la libreria Aspose.Finance per .NET dal[rilascia](https://releases.aspose.com/finance/net/).
   
2. Ambiente di sviluppo: configura il tuo ambiente di sviluppo con Visual Studio o qualsiasi altro IDE preferito.
## Importa spazi dei nomi
Assicurati di importare gli spazi dei nomi necessari nel codice C#:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Passaggio 1: definire le directory di origine e di output
Prima di procedere, specifica rispettivamente le directory di origine e di output in cui verranno posizionati e salvati i file XBRL.
```csharp
// Directory di origine
string sourceDir = "Your Source Directory";
// Cartella di destinazione
string outputDir = "Your Output Directory";
```
## Passaggio 2: crea un documento XBRL
 Istanziare un`XbrlDocument` oggetto per lavorare con i dati XBRL.
```csharp
XbrlDocument document = new XbrlDocument();
```
## Passaggio 3: accedi alla raccolta XbrlInstance
Accedi alla raccolta di istanze XBRL all'interno del documento.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## Passaggio 4: aggiungi XbrlInstance
Aggiungi una nuova istanza XBRL alla raccolta.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Passaggio 5: aggiungere il riferimento allo schema
Includere un riferimento allo schema nell'istanza XBRL, specificando la directory di origine, il prefisso dello spazio dei nomi e l'URI.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://esempio.com/xbrl/taxonomy");
```
## Passaggio 6: recuperare ArcroleType
 Recupera il`ArcroleType` basato su un URI specifico.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## Passaggio 7: aggiungi ArcroleReference
 Se la`ArcroleType` viene trovato, crea un`ArcroleReference` e aggiungerlo ai riferimenti arcrole dell'istanza XBRL.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## Passaggio 8: salva il documento
Salva il documento XBRL modificato nella directory di output specificata.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## Conclusione
In questo tutorial, abbiamo esplorato come aggiungere un riferimento al ruolo ARC a un documento XBRL utilizzando Aspose.Finance per .NET. Seguendo queste istruzioni dettagliate e sfruttando le funzionalità di Aspose.Finance, puoi gestire e manipolare in modo efficiente i dati XBRL per soddisfare le tue esigenze specifiche.
## Domande frequenti
### Cos'è XBRL?
XBRL sta per eXtensible Business Reporting Language, un linguaggio standardizzato per la comunicazione elettronica di dati aziendali e finanziari.
### Perché XBRL è importante?
XBRL garantisce coerenza, accuratezza ed efficienza nello scambio e nell'analisi delle informazioni finanziarie, a vantaggio di regolatori, analisti e aziende.
### Aspose.Finance può gestire attività XBRL complesse?
Sì, Aspose.Finance offre solide funzionalità per lavorare con documenti XBRL, inclusa la gestione di attività complesse come i riferimenti ai ruoli e la gestione della tassonomia.
### Aspose.Finance è compatibile con altre librerie .NET?
Sì, Aspose.Finance si integra perfettamente con altre librerie .NET, fornendo ampio supporto per la manipolazione e il reporting dei dati finanziari.
### Dove posso trovare ulteriore supporto per Aspose.Finance?
 Per ulteriore supporto visitare il[Pagina di supporto Aspose.Finance](https://forum.aspose.com/c/finance/43).
---
title: Aggiungi riferimento allo schema al documento XBRL
linktitle: Aggiungi riferimento allo schema al documento XBRL
second_title: API Aspose.Finance .NET
description: Scopri come aggiungere riferimenti allo schema ai documenti XBRL utilizzando Aspose.Finance per .NET. Semplifica l'elaborazione dei tuoi dati finanziari oggi stesso!
type: docs
weight: 15
url: /it/net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## Presentazione di Aspose.Finance per .NET
Aspose.Finance per .NET è una potente libreria che fornisce funzionalità complete per l'elaborazione e la manipolazione di documenti e dati finanziari all'interno delle applicazioni .NET. Che tu stia creando software di contabilità, strumenti di analisi finanziaria o qualsiasi altra applicazione finanziaria, Aspose.Finance per .NET offre un'ampia gamma di funzionalità per semplificare il processo di sviluppo.
## Prerequisiti
Prima di immergerti nell'utilizzo di Aspose.Finance per .NET, assicurati di aver impostato i seguenti prerequisiti:
### 1. Installa Visual Studio
Assicurati di avere Visual Studio installato sul tuo sistema. Puoi scaricarlo e installarlo dal sito Web ufficiale di Microsoft.
### 2. Ottieni una licenza Aspose.Finance
Per utilizzare tutte le funzionalità di Aspose.Finance per .NET, è necessario acquisire una licenza valida. È possibile acquistare una licenza da[Qui](https://purchase.aspose.com/buy) oppure optare per una licenza temporanea a scopo di test.
### 3. Scarica e fai riferimento ad Aspose.Finance per .NET
 Scarica la libreria Aspose.Finance per .NET da[pagina delle uscite](https://releases.aspose.com/finance/net/) e fai riferimento ad esso nel tuo progetto .NET.
### 4. Accedi alla documentazione e al supporto
 Fare riferimento al[Documentazione dell'API](https://reference.aspose.com/finance/net/) per informazioni dettagliate sull'utilizzo di Aspose.Finance per .NET. Inoltre, puoi chiedere assistenza alla comunità Aspose.Finance su[Forum di assistenza](https://forum.aspose.com/c/finance/43).
## Importazione di spazi dei nomi
Iniziamo importando gli spazi dei nomi necessari nel tuo progetto .NET:
## Passaggio 1: aggiungere lo spazio dei nomi Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Questo spazio dei nomi contiene classi e metodi per lavorare con documenti e dati XBRL.
Ora suddividiamo l'esempio fornito in più passaggi per comprendere come aggiungere un riferimento allo schema a un documento XBRL utilizzando Aspose.Finance per .NET.
## Passaggio 1: definire le directory di origine e di output
```csharp
// Directory di origine
string sourceDir = "Your Source Directory";
// Cartella di destinazione
string outputDir = "Your Output Directory";
```
 Sostituire`"Your Source Directory"` E`"Your Output Directory"`con i percorsi effettivi rispettivamente delle directory di origine e di output.
## Passaggio 2: crea un documento XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
Questo crea una nuova istanza del documento XBRL.
## Passaggio 3: accedi alle istanze XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Ciò recupera la raccolta di istanze XBRL dal documento e vi aggiunge una nuova istanza.
## Passaggio 4: aggiungere il riferimento allo schema
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://esempio.com/xbrl/taxonomy");
```
 Ciò aggiunge un riferimento allo schema all'istanza XBRL. Sostituire`"schema.xsd"` con il nome effettivo del file di schema,`"example"` con un prefisso adatto, e`"http://example.com/xbrl/taxonomy"` con l'URI dello spazio dei nomi di destinazione.
## Passaggio 5: salva il documento
```csharp
document.Save(outputDir + @"document2.xbrl");
```
Ciò salva il documento XBRL modificato nella directory di output specificata.
## Conclusione
In conclusione, Aspose.Finance per .NET offre una soluzione solida per la gestione di documenti e dati finanziari nelle applicazioni .NET. Seguendo i passaggi delineati in questo tutorial, puoi facilmente integrare Aspose.Finance nei tuoi progetti e manipolare in modo efficiente i documenti XBRL.
## Domande frequenti
 (Domande frequenti)
### 1. Posso utilizzare Aspose.Finance per .NET senza licenza?
No, è necessaria una licenza valida per utilizzare tutte le funzionalità di Aspose.Finance per .NET. Tuttavia, è possibile ottenere una licenza temporanea a scopo di test.
### 2. Aspose.Finance è adatto alla creazione di software di contabilità?
Sì, Aspose.Finance fornisce funzionalità complete per l'elaborazione dei dati finanziari, rendendolo ideale per la creazione di software di contabilità e applicazioni correlate.
### 3. Dove posso trovare supporto per Aspose.Finance?
Puoi chiedere assistenza alla comunità Aspose.Finance sul forum di supporto ufficiale.
### 4. Posso personalizzare il prefisso di riferimento dello schema?
Sì, puoi scegliere un prefisso adatto quando aggiungi un riferimento allo schema a un documento XBRL utilizzando Aspose.Finance per .NET.
### 5. Aspose.Finance supporta altri formati finanziari oltre a XBRL?
Sì, Aspose.Finance supporta vari formati e standard finanziari, consentendo una perfetta integrazione in diverse applicazioni finanziarie.
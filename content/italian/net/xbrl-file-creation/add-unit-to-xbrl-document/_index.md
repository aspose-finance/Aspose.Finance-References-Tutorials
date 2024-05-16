---
title: Aggiungi unità al documento XBRL
linktitle: Aggiungi unità al documento XBRL
second_title: API Aspose.Finance .NET
description: Scopri come aggiungere unità ai documenti XBRL senza sforzo con Aspose.Finance per .NET. Migliora oggi stesso le tue capacità di elaborazione dei dati finanziari!
type: docs
weight: 16
url: /it/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
Benvenuti nel mondo di Aspose.Finance per .NET: il vostro gateway per un'efficiente manipolazione dei documenti finanziari all'interno delle applicazioni .NET. Che tu stia creando software di contabilità, strumenti di analisi finanziaria o qualsiasi altra applicazione finanziaria, Aspose.Finance per .NET ti fornisce un set completo di funzionalità per semplificare il processo di sviluppo.
## Prerequisiti
Prima di approfondire lo sfruttamento della potenza di Aspose.Finance per .NET, assicuriamoci di disporre dei prerequisiti necessari:
### 1. Installazione di Visual Studio
Assicurati di avere Visual Studio installato sul tuo sistema. In caso contrario, puoi scaricarlo e installarlo dal sito Web ufficiale di Microsoft.
### 2. Ottieni una licenza
 Per sbloccare tutto il potenziale di Aspose.Finance per .NET, è necessaria una licenza valida. È possibile acquistare una licenza da[Qui](https://purchase.aspose.com/buy) oppure optare per una licenza temporanea a scopo di test.
### 3. Scarica e fai riferimento ad Aspose.Finance per .NET
 Scarica la libreria Aspose.Finance per .NET da[pagina delle uscite](https://releases.aspose.com/finance/net/) e fai riferimento ad esso nel tuo progetto .NET.
### 4. Accedi alla documentazione e al supporto
 Fare riferimento al[documentazione](https://reference.aspose.com/finance/net/)per informazioni dettagliate sull'utilizzo di Aspose.Finance per .NET. Inoltre, puoi chiedere assistenza alla comunità Aspose.Finance su[Forum di assistenza](https://forum.aspose.com/c/finance/43).
## Importazione di spazi dei nomi
Ora importiamo gli spazi dei nomi necessari nel tuo progetto .NET:
## Passaggio 1: aggiungere lo spazio dei nomi Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Questo spazio dei nomi contiene classi e metodi essenziali per lavorare con documenti e dati XBRL.
Analizziamo l'esempio fornito in più passaggi per capire come aggiungere un'unità a un documento XBRL utilizzando Aspose.Finance per .NET.
## Passaggio 1: definire la directory di output
```csharp
// Cartella di destinazione
string outputDir = "Your Output Directory";
```
 Sostituire`"Your Output Directory"` con il percorso effettivo della directory di output desiderata.
## Passaggio 2: crea un documento XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
Ciò inizializza una nuova istanza del documento XBRL.
## Passaggio 3: accedi alle istanze XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Ciò recupera la raccolta di istanze XBRL dal documento e vi aggiunge una nuova istanza.
## Passaggio 4: aggiungi unità
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Ciò crea una nuova unità di misura (in questo caso, USD) e la aggiunge all'istanza XBRL. Puoi modificare il codice valuta e l'URI dello spazio dei nomi secondo necessità.
## Passaggio 5: salva il documento
```csharp
document.Save(outputDir + @"document4.xbrl");
```
Ciò salva il documento XBRL modificato nella directory di output specificata.
## Conclusione
In conclusione, Aspose.Finance per .NET consente agli sviluppatori di manipolare senza sforzo documenti e dati finanziari all'interno delle loro applicazioni .NET. Seguendo i passaggi descritti in questo tutorial, puoi integrare perfettamente Aspose.Finance per .NET nei tuoi progetti e migliorare le loro capacità di elaborazione finanziaria.
## Domande frequenti
### 1. Posso utilizzare Aspose.Finance per .NET senza licenza?
No, è necessaria una licenza valida per sbloccare tutte le funzionalità di Aspose.Finance per .NET. Tuttavia, sono disponibili licenze temporanee a scopo di test.
### 2. Aspose.Finance per .NET è adatto per la creazione di software di contabilità?
Sì, Aspose.Finance per .NET fornisce robuste funzionalità su misura per la creazione di software di contabilità e relative applicazioni finanziarie.
### 3. Dove posso trovare supporto per Aspose.Finance per .NET?
Puoi chiedere assistenza alla comunità Aspose.Finance sul forum di supporto.
### 4. Posso personalizzare l'unità di misura in un documento XBRL?
Sì, puoi creare e aggiungere unità di misura personalizzate ai documenti XBRL utilizzando Aspose.Finance per .NET.
### 5. Aspose.Finance per .NET supporta più valute?
Sì, Aspose.Finance per .NET supporta più valute, consentendo un'elaborazione versatile dei dati finanziari.
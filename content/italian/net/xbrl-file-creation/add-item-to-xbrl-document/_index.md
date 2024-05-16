---
title: Aggiungi elemento al documento XBRL
linktitle: Aggiungi elemento al documento XBRL
second_title: API Aspose.Finance .NET
description: Scopri come aggiungere elementi ai documenti XBRL utilizzando Aspose.Finance per .NET. Semplifica il reporting finanziario nelle tue applicazioni .NET. #Aspose #Finanza
type: docs
weight: 13
url: /it/net/xbrl-file-creation/add-item-to-xbrl-document/
---
Extensible Business Reporting Language (XBRL) è diventato un formato standard per il reporting finanziario, consentendo una comunicazione efficiente e accurata dei dati finanziari. Aspose.Finance per .NET fornisce funzionalità robuste per lavorare con documenti XBRL nelle applicazioni .NET. In questo tutorial, esamineremo i passaggi per aggiungere un elemento a un documento XBRL utilizzando Aspose.Finance per .NET.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
### 1. Installare Aspose.Finance per .NET
 Se non lo hai già fatto, scarica e installa Aspose.Finance per .NET da[Sito ufficiale](https://releases.aspose.com/finance/net/). Segui le istruzioni di installazione per configurare la libreria nel tuo ambiente .NET.
### 2. Configura il tuo ambiente di sviluppo
Assicurati di disporre di un ambiente di sviluppo funzionante per lo sviluppo .NET. Avrai bisogno di un IDE compatibile come Visual Studio, insieme al framework .NET installato sul tuo sistema.
## Importa spazi dei nomi
Innanzitutto, importa gli spazi dei nomi necessari nella tua applicazione .NET per utilizzare la funzionalità fornita da Aspose.Finance per .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Ora suddividiamo il codice di esempio in più passaggi:
## Passaggio 1: definire le directory di origine e di output
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Sostituire`"Your Source Directory"` E`"Your Output Directory"` con i percorsi rispettivamente delle directory di origine e di output.
## Passaggio 2: crea un documento e un'istanza XBRL
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Inizializza un documento XBRL e un'istanza con cui lavorare.
## Passaggio 3: aggiungere il riferimento allo schema
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://esempio.com/xbrl/taxonomy");
```
Aggiungi un riferimento allo schema all'istanza XBRL, fornendo il percorso del file di schema e specificando i dettagli dello spazio dei nomi.
## Passaggio 4: definire il contesto e l'entità
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
Crea un contesto e un'entità per l'istanza XBRL, specificando il periodo e i dettagli dell'entità.
## Passaggio 5: aggiungi unità
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Definire un'unità per l'istanza XBRL, specificando i nomi qualificati della misura.
## Passaggio 6: aggiungi articolo
```csharp
Concept fixedAssetsConcept = schema.GetConceptByName("fixedAssets");
if (fixedAssetsConcept != null)
{
    Item item = new Item(fixedAssetsConcept);
    item.ContextRef = context;
    item.UnitRef = unit;
    item.Precision = 4;
    item.Value = "1444";
    xbrlInstance.Facts.Add(item);
}
```
Aggiungi un elemento all'istanza XBRL, specificandone concetto, contesto, unità, precisione e valore.
## Passaggio 7: salva il documento
```csharp
document.Save(outputDir + @"document5.xbrl");
```
Salva il documento XBRL nella directory di output.
## Conclusione
L'aggiunta di elementi a un documento XBRL è essenziale per rappresentare accuratamente i dati finanziari. Aspose.Finance per .NET semplifica questo processo fornendo un'API completa per lavorare con documenti XBRL nelle applicazioni .NET.
## Domande frequenti
### Posso utilizzare Aspose.Finance per .NET con qualsiasi applicazione .NET?
Sì, Aspose.Finance per .NET è compatibile con qualsiasi applicazione .NET, incluse le applicazioni ASP.NET, WinForms e Console.
### Aspose.Finance per .NET è gratuito?
 Aspose.Finance per .NET è una libreria commerciale. È possibile scaricare una versione di prova gratuita per valutarne le funzionalità e da cui è possibile acquistare le licenze[Qui](https://purchase.aspose.com/buy).
### Aspose.Finance per .NET supporta altri formati di reporting finanziario oltre a XBRL?
Aspose.Finance per .NET si concentra principalmente sulle funzionalità relative a XBRL. Tuttavia, Aspose offre altre librerie per lavorare con diversi formati finanziari.
### Come posso ottenere supporto per Aspose.Finance per .NET?
 È possibile ottenere supporto per Aspose.Finance per .NET tramite il[foro ufficiale](https://forum.aspose.com/c/finance/43)dove puoi porre domande e interagire con altri utenti e personale di supporto.
### Posso ottenere una licenza temporanea per Aspose.Finance per .NET?
 Sì, le licenze temporanee per Aspose.Finance per .NET sono disponibili a scopo di test. Puoi ottenerne uno[Qui](https://purchase.aspose.com/temporary-license/).
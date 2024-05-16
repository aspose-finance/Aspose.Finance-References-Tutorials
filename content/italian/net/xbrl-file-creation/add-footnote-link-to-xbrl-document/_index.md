---
title: Aggiungi collegamento nota a piè di pagina al documento XBRL
linktitle: Aggiungi collegamento nota a piè di pagina al documento XBRL
second_title: API Aspose.Finance .NET
description: Scopri come aggiungere collegamenti alle note a piè di pagina ai documenti XBRL utilizzando Aspose.Finance per .NET. Migliora i report finanziari con contesto aggiuntivo senza sforzo.
type: docs
weight: 12
url: /it/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
L'aggiunta di un collegamento a una nota a piè di pagina a un documento XBRL è fondamentale per fornire ulteriore contesto o spiegazioni per punti dati specifici. In questo tutorial, esamineremo passo dopo passo il processo utilizzando Aspose.Finance per .NET.
## Prerequisiti
Prima di iniziare, assicurati di disporre dei seguenti prerequisiti:
1.  Aspose.Finance per .NET: assicurati di aver installato Aspose.Finance per .NET sul tuo sistema. Puoi scaricarlo da[Qui](https://releases.aspose.com/finance/net/).
  
2. Ambiente di sviluppo: disporre di un ambiente di sviluppo configurato con .NET Framework o .NET Core.
## Importa spazi dei nomi:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Passaggio 1: imposta le directory di origine e di output
Innanzitutto, specifica le directory per i file di origine e di output:
```csharp
// Directory di origine
string sourceDir = "Your Source Directory";
// Cartella di destinazione
string outputDir = "Your Output Directory";
```
## Passaggio 2: crea un documento e un'istanza XBRL
Inizializza un documento e un'istanza XBRL:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Passaggio 3: aggiungere riferimenti allo schema
Aggiungi riferimenti allo schema all'istanza XBRL:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://esempio.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## Passaggio 4: definire il contesto
Definire il contesto per l'istanza XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## Passaggio 5: aggiungi il collegamento alla nota a piè di pagina
Crea e aggiungi un collegamento a piè di pagina all'istanza XBRL:
```csharp
FootnoteLink footnoteLink = new FootnoteLink();
Footnote footnote = new Footnote("footnote1");
footnote.Text = "Including the effects of the merger.";
Loc loc = new Loc("#cd1", "fact1");
FootnoteArc footnoteArc = new FootnoteArc(loc.Label, footnote.Label);
footnoteLink.Footnotes.Add(footnote);
footnoteLink.Locators.Add(loc);
footnoteLink.FootnoteArcs.Add(footnoteArc);
xbrlInstance.FootnoteLinks.Add(footnoteLink);
```
## Passaggio 6: salva il documento
Salva il documento XBRL modificato:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## Conclusione
L'aggiunta di un collegamento a una nota a piè di pagina a un documento XBRL è un processo semplice con Aspose.Finance per .NET. Seguendo i passaggi descritti in questo tutorial, puoi incorporare facilmente contesto o spiegazioni aggiuntivi nei tuoi report finanziari.
## Domande frequenti
### Posso aggiungere più collegamenti a piè di pagina a un singolo documento XBRL?
Sì, puoi aggiungere più collegamenti alle note a piè di pagina ripetendo i passaggi descritti in questo tutorial per ciascun collegamento aggiuntivo.
### Aspose.Finance per .NET è compatibile sia con .NET Framework che con .NET Core?
Sì, Aspose.Finance per .NET supporta sia gli ambienti .NET Framework che .NET Core.
### Come posso ottenere una licenza temporanea per Aspose.Finance per .NET?
 È possibile ottenere una licenza temporanea da[Qui](https://purchase.aspose.com/temporary-license/).
### Aspose.Finance per .NET fornisce supporto per la convalida XBRL?
Sì, Aspose.Finance per .NET offre supporto completo per la convalida XBRL per garantire la conformità agli standard di settore.
### Dove posso trovare risorse aggiuntive e supporto per Aspose.Finance per .NET?
 Puoi visitare il[Aspose.Finance per il forum .NET](https://forum.aspose.com/c/finance/43) per supporto e accesso alla documentazione[Qui](https://reference.aspose.com/finance/net/).
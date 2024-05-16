---
title: Aggiungi riferimento al ruolo al documento XBRL
linktitle: Aggiungi riferimento al ruolo al documento XBRL
second_title: API Aspose.Finance .NET
description: Scopri come aggiungere riferimenti ai ruoli ai documenti XBRL utilizzando Aspose.Finance per .NET. Semplifica il reporting finanziario nelle tue applicazioni .NET con questo tutorial.
type: docs
weight: 14
url: /it/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (eXtensible Business Reporting Language) è diventato uno standard per lo scambio di informazioni aziendali, in particolare nel reporting finanziario. Aspose.Finance per .NET semplifica il lavoro con documenti XBRL nelle applicazioni .NET. Questo tutorial ti guiderà attraverso il processo di aggiunta di un riferimento al ruolo a un documento XBRL utilizzando Aspose.Finance per .NET.
## Prerequisiti
Prima di iniziare, assicurati di possedere i seguenti prerequisiti:
### 1. Installare Aspose.Finance per .NET
Assicurati di avere Aspose.Finance per .NET installato nel tuo ambiente di sviluppo. Se non l'hai già fatto, scaricalo da[rilascia](https://releases.aspose.com/finance/net/) e seguire le istruzioni di installazione.
### 2. Configura il tuo ambiente di sviluppo
Assicurati di disporre di un ambiente di sviluppo funzionante per lo sviluppo .NET. Ciò include un IDE compatibile come Visual Studio e il framework .NET installato sul tuo sistema.
## Importa spazi dei nomi
Inizia importando gli spazi dei nomi necessari nella tua applicazione .NET per accedere alle funzionalità fornite da Aspose.Finance per .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## Passaggio 4: recuperare il tipo di ruolo e aggiungere il riferimento al ruolo
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
Recupera il tipo di ruolo utilizzando il relativo URI e aggiungi un riferimento al ruolo all'istanza XBRL.
## Passaggio 5: salva il documento
```csharp
document.Save(outputDir + @"document7.xbrl");
```
Salva il documento XBRL nella directory di output.
## Conclusione
L'aggiunta di riferimenti ai ruoli ai documenti XBRL è fondamentale per definire i ruoli dei vari elementi all'interno del documento. Aspose.Finance per .NET fornisce un modo semplice per eseguire questa attività, consentendo agli sviluppatori di lavorare in modo efficiente con i documenti XBRL nelle loro applicazioni .NET.
## Domande frequenti
### Posso utilizzare Aspose.Finance per .NET con qualsiasi applicazione .NET?
Sì, Aspose.Finance per .NET è compatibile con qualsiasi applicazione .NET, incluse le applicazioni ASP.NET, WinForms e Console.
### Aspose.Finance per .NET è gratuito?
 Aspose.Finance per .NET è una libreria commerciale. È possibile scaricare una versione di prova gratuita per valutarne le funzionalità e da cui è possibile acquistare le licenze[Qui](https://purchase.aspose.com/buy).
### Aspose.Finance per .NET supporta altri formati di reporting finanziario oltre a XBRL?
Aspose.Finance per .NET si concentra principalmente sulle funzionalità relative a XBRL. Tuttavia, Aspose offre altre librerie per lavorare con diversi formati finanziari.
### Come posso ottenere supporto per Aspose.Finance per .NET?
 È possibile ottenere supporto per Aspose.Finance per .NET tramite il[Forum](https://forum.aspose.com/c/finance/43)dove puoi porre domande e interagire con altri utenti e personale di supporto.
### Posso ottenere una licenza temporanea per Aspose.Finance per .NET?
 Sì, le licenze temporanee per Aspose.Finance per .NET sono disponibili a scopo di test. Puoi ottenerne uno[Qui](https://purchase.aspose.com/temporary-license/).
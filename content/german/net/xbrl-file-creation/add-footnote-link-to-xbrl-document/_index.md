---
title: Fußnotenlink zum XBRL-Dokument hinzufügen
linktitle: Fußnotenlink zum XBRL-Dokument hinzufügen
second_title: Aspose.Finance .NET API
description: Erfahren Sie, wie Sie mit Aspose.Finance für .NET Fußnotenlinks zu XBRL-Dokumenten hinzufügen. Erweitern Sie Finanzberichte mühelos mit zusätzlichem Kontext.
type: docs
weight: 12
url: /de/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
Das Hinzufügen eines Fußnotenlinks zu einem XBRL-Dokument ist wichtig, um zusätzlichen Kontext oder Erklärungen für bestimmte Datenpunkte bereitzustellen. In diesem Tutorial gehen wir den Prozess Schritt für Schritt mit Aspose.Finance für .NET durch.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Aspose.Finance für .NET: Stellen Sie sicher, dass Sie Aspose.Finance für .NET auf Ihrem System installiert haben. Sie können es herunterladen von[Hier](https://releases.aspose.com/finance/net/).
  
2. Entwicklungsumgebung: Richten Sie eine Entwicklungsumgebung mit einem .NET Framework oder .NET Core ein.
## Namespaces importieren:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Schritt 1: Quell- und Ausgabeverzeichnisse festlegen
Geben Sie zunächst die Verzeichnisse für die Quell- und Ausgabedateien an:
```csharp
// Quellverzeichnis
string sourceDir = "Your Source Directory";
// Ausgabe Verzeichnis
string outputDir = "Your Output Directory";
```
## Schritt 2: Erstellen eines XBRL-Dokuments und einer XBRL-Instanz
Initialisieren Sie ein XBRL-Dokument und eine Instanz:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Schritt 3: Schemaverweise hinzufügen
Fügen Sie der XBRL-Instanz Schemareferenzen hinzu:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## Schritt 4: Kontext definieren
Definieren Sie den Kontext für die XBRL-Instanz:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## Schritt 5: Fußnotenlink hinzufügen
Erstellen und fügen Sie einen Fußnotenlink zur XBRL-Instanz hinzu:
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
## Schritt 6: Speichern Sie das Dokument
Speichern Sie das geänderte XBRL-Dokument:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## Abschluss
Das Hinzufügen eines Fußnotenlinks zu einem XBRL-Dokument ist mit Aspose.Finance für .NET ein unkomplizierter Vorgang. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie nahtlos zusätzlichen Kontext oder Erklärungen in Ihre Finanzberichte einbinden.
## FAQs
### Kann ich einem einzelnen XBRL-Dokument mehrere Fußnotenlinks hinzufügen?
Ja, Sie können mehrere Fußnotenlinks hinzufügen, indem Sie die in diesem Tutorial beschriebenen Schritte für jeden zusätzlichen Link wiederholen.
### Ist Aspose.Finance für .NET sowohl mit .NET Framework als auch mit .NET Core kompatibel?
Ja, Aspose.Finance für .NET unterstützt sowohl .NET Framework- als auch .NET Core-Umgebungen.
### Wie kann ich eine temporäre Lizenz für Aspose.Finance für .NET erhalten?
 Eine vorläufige Lizenz erhalten Sie bei[Hier](https://purchase.aspose.com/temporary-license/).
### Bietet Aspose.Finance für .NET Unterstützung für die XBRL-Validierung?
Ja, Aspose.Finance für .NET bietet umfassende Unterstützung für die XBRL-Validierung, um die Einhaltung von Industriestandards zu gewährleisten.
### Wo finde ich zusätzliche Ressourcen und Support für Aspose.Finance für .NET?
 Besuchen Sie die[Aspose.Finance für .NET-Forum](https://forum.aspose.com/c/finance/43) für Support und Zugriff auf Dokumentation[Hier](https://reference.aspose.com/finance/net/).
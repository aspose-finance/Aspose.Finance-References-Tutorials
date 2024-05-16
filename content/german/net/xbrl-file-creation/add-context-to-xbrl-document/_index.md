---
title: Kontext zum XBRL-Dokument hinzufügen
linktitle: Kontext zum XBRL-Dokument hinzufügen
second_title: Aspose.Finance .NET API
description: Erfahren Sie, wie Sie mit Aspose.Finance Kontext zu XBRL-Dokumenten in .NET hinzufügen, um die Finanzberichterstattung zu optimieren. #Aspose #Finance #XBRL
type: docs
weight: 11
url: /de/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## Einführung
Im Bereich der Finanzberichterstattung spielt XBRL (eXtensible Business Reporting Language) eine zentrale Rolle bei der Standardisierung des Austauschs von Geschäftsinformationen. Das Hinzufügen von Kontext zu XBRL-Dokumenten ist entscheidend, um die Integrität und Relevanz der darin enthaltenen Daten sicherzustellen. Mit Aspose.Finance für .NET wird dieser Prozess rationalisiert und effizient, sodass Entwickler Kontext nahtlos in ihre XBRL-Dokumente integrieren können.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Aspose.Finance für .NET-Bibliothek: Laden Sie die Aspose.Finance für .NET-Bibliothek herunter und installieren Sie sie von der[Mitteilungen](https://releases.aspose.com/finance/net/).
2. .NET-Entwicklungsumgebung: Stellen Sie sicher, dass auf Ihrem Computer eine funktionierende .NET-Entwicklungsumgebung eingerichtet ist.
3. Grundlegende Kenntnisse in C#: Um den Beispielen folgen zu können, sind Kenntnisse der Programmiersprache C# hilfreich.
## Namespaces importieren
Importieren Sie in Ihr C#-Projekt die erforderlichen Namespaces, um auf die von Aspose.Finance für .NET bereitgestellte Funktionalität zuzugreifen:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Schritt 1: Ausgabeverzeichnis festlegen
Bevor Sie dem XBRL-Dokument Kontext hinzufügen, geben Sie das Ausgabeverzeichnis an, in dem das geänderte Dokument gespeichert wird:
```csharp
string outputDir = "Your Output Directory";
```
 Ersetzen`"Your Output Directory"` durch den gewünschten Pfad auf Ihrem System.
## Schritt 2: XBRL-Dokument erstellen
 Instanziieren Sie einen`XbrlDocument` Objekt zum Arbeiten mit XBRL-Dokumenten:
```csharp
XbrlDocument document = new XbrlDocument();
```
Dieses Objekt stellt das zu bearbeitende XBRL-Dokument dar.
## Schritt 3: XBRL-Instanz hinzufügen
Fügen Sie dem Dokument eine XBRL-Instanz hinzu. Jede Instanz enthält die Daten für einen bestimmten Berichtszeitraum:
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Dieser Schritt initialisiert eine XBRL-Instanz innerhalb des Dokuments.
## Schritt 4: Kontextzeitraum und Entität definieren
Erstellen Sie einen Kontextzeitraum und eine Entität für die XBRL-Instanz:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
Geben Sie den Zeitraum und die Entitätsdetails entsprechend Ihren Berichtsanforderungen an.
## Schritt 5: Kontext erstellen
Erstellen Sie einen Kontext mithilfe des Zeitraums und der Entität, die Sie im vorherigen Schritt definiert haben:
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
Dieser Kontext kapselt die zeitlichen und entitätsbezogenen Informationen.
## Schritt 6: Kontext zur XBRL-Instanz hinzufügen
Verknüpfen Sie den im vorherigen Schritt erstellten Kontext mit der XBRL-Instanz:
```csharp
xbrlInstance.Contexts.Add(context);
```
Dieser Schritt verknüpft den Kontext mit der XBRL-Instanz und stellt den Daten relevante Kontextinformationen bereit.
## Schritt 7: Speichern Sie das Dokument
Speichern Sie das geänderte XBRL-Dokument im angegebenen Ausgabeverzeichnis:
```csharp
document.Save(outputDir + @"document3.xbrl");
```
Damit wird der Vorgang abgeschlossen und das XBRL-Dokument mit dem hinzugefügten Kontext gespeichert.
## Abschluss
Wenn Sie diese Schritte befolgen, können Sie mit Aspose.Finance für .NET effektiv Kontext zu XBRL-Dokumenten hinzufügen. Dies verbessert die Klarheit und Benutzerfreundlichkeit von Finanzdaten und erleichtert genaue Analysen und Berichte.
## FAQs
### Kann Aspose.Finance für .NET große XBRL-Dokumente verarbeiten?
Aspose.Finance für .NET ist für die Verarbeitung von XBRL-Dokumenten unterschiedlicher Größe, einschließlich großer Datensätze, optimiert.
### Gibt es eine Testversion von Aspose.Finance für .NET?
Ja, Sie können eine kostenlose Testversion von der offiziellen Aspose-Website herunterladen.
### Unterstützt Aspose.Finance für .NET neben XBRL noch andere Standards für die Finanzberichterstattung?
Aspose.Finance konzentriert sich hauptsächlich auf XBRL-bezogene Funktionen, bietet aber auch Unterstützung für andere Finanzformate.
### Kann ich die Kontextinformationen meinen spezifischen Anforderungen entsprechend anpassen?
Absolut, Aspose.Finance für .NET bietet Flexibilität bei der Anpassung von Kontextinformationen an Ihre Bedürfnisse.
### Wo finde ich zusätzlichen Support oder Ressourcen für Aspose.Finance für .NET?
Sie können das Aspose.Finance-Forum besuchen, um Hilfe von der Community zu erhalten, oder die Dokumentation für umfassende Anleitungen durchsehen.
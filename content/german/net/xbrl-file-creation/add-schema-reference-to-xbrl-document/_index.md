---
title: Schemaverweis zum XBRL-Dokument hinzufügen
linktitle: Schemaverweis zum XBRL-Dokument hinzufügen
second_title: Aspose.Finance .NET API
description: Erfahren Sie, wie Sie mit Aspose.Finance für .NET Schemaverweise zu XBRL-Dokumenten hinzufügen. Optimieren Sie noch heute Ihre Finanzdatenverarbeitung!
type: docs
weight: 15
url: /de/net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## Einführung von Aspose.Finance für .NET
Aspose.Finance für .NET ist eine leistungsstarke Bibliothek, die umfassende Funktionen für die Verarbeitung und Bearbeitung von Finanzdokumenten und -daten in .NET-Anwendungen bietet. Egal, ob Sie Buchhaltungssoftware, Finanzanalysetools oder andere Finanzanwendungen erstellen, Aspose.Finance für .NET bietet eine breite Palette an Funktionen zur Optimierung Ihres Entwicklungsprozesses.
## Voraussetzungen
Bevor Sie mit der Verwendung von Aspose.Finance für .NET beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
### 1. Installieren Sie Visual Studio
Stellen Sie sicher, dass Visual Studio auf Ihrem System installiert ist. Sie können es von der offiziellen Microsoft-Website herunterladen und installieren.
### 2. Erwerben Sie eine Aspose.Finance-Lizenz
Um die vollen Funktionen von Aspose.Finance für .NET nutzen zu können, benötigen Sie eine gültige Lizenz. Sie können eine Lizenz erwerben bei[Hier](https://purchase.aspose.com/buy) oder entscheiden Sie sich für eine temporäre Lizenz zu Testzwecken.
### 3. Aspose.Finance für .NET herunterladen und referenzieren
 Laden Sie die Aspose.Finance für .NET-Bibliothek herunter von der[Veröffentlichungsseite](https://releases.aspose.com/finance/net/) und verweisen Sie in Ihrem .NET-Projekt darauf.
### 4. Zugriff auf Dokumentation und Support
 Weitere Informationen finden Sie im[API-Dokumentation](https://reference.aspose.com/finance/net/) für detaillierte Informationen zur Verwendung von Aspose.Finance für .NET. Darüber hinaus können Sie sich an die Aspose.Finance-Community wenden unter[Hilfeforum](https://forum.aspose.com/c/finance/43).
## Namespaces importieren
Beginnen wir mit dem Importieren der erforderlichen Namespaces in Ihr .NET-Projekt:
## Schritt 1: Aspose.Finance-Namespace hinzufügen
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Dieser Namespace enthält Klassen und Methoden zum Arbeiten mit XBRL-Dokumenten und -Daten.
Lassen Sie uns nun das bereitgestellte Beispiel in mehrere Schritte aufteilen, um zu verstehen, wie mit Aspose.Finance für .NET eine Schemareferenz zu einem XBRL-Dokument hinzugefügt wird.
## Schritt 1: Quell- und Ausgabeverzeichnisse definieren
```csharp
// Quellverzeichnis
string sourceDir = "Your Source Directory";
// Ausgabe Verzeichnis
string outputDir = "Your Output Directory";
```
 Ersetzen`"Your Source Directory"` Und`"Your Output Directory"`mit den tatsächlichen Pfaden zu Ihren Quell- und Ausgabeverzeichnissen.
## Schritt 2: Erstellen Sie ein XBRL-Dokument
```csharp
XbrlDocument document = new XbrlDocument();
```
Dadurch wird eine neue Instanz des XBRL-Dokuments erstellt.
## Schritt 3: Zugriff auf XBRL-Instanzen
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Dadurch wird die Sammlung der XBRL-Instanzen aus dem Dokument abgerufen und eine neue Instanz hinzugefügt.
## Schritt 4: Schemareferenz hinzufügen
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
 Dadurch wird eine Schemareferenz zur XBRL-Instanz hinzugefügt. Ersetzen Sie`"schema.xsd"` durch den tatsächlichen Namen Ihrer Schemadatei,`"example"` mit einem passenden Präfix und`"http://example.com/xbrl/taxonomy"` durch die Ziel-Namespace-URI.
## Schritt 5: Speichern Sie das Dokument
```csharp
document.Save(outputDir + @"document2.xbrl");
```
Dadurch wird das geänderte XBRL-Dokument im angegebenen Ausgabeverzeichnis gespeichert.
## Abschluss
Zusammenfassend lässt sich sagen, dass Aspose.Finance für .NET eine robuste Lösung für die Handhabung von Finanzdokumenten und -daten in .NET-Anwendungen bietet. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie Aspose.Finance problemlos in Ihre Projekte integrieren und XBRL-Dokumente effizient bearbeiten.
## FAQs
 (Häufig gestellte Fragen)
### 1. Kann ich Aspose.Finance für .NET ohne Lizenz verwenden?
Nein, Sie benötigen eine gültige Lizenz, um den vollen Funktionsumfang von Aspose.Finance für .NET nutzen zu können. Sie können jedoch eine temporäre Lizenz zu Testzwecken erwerben.
### 2. Ist Aspose.Finance zum Erstellen von Buchhaltungssoftware geeignet?
Ja, Aspose.Finance bietet umfassende Funktionen zur Verarbeitung von Finanzdaten und eignet sich daher ideal für die Erstellung von Buchhaltungssoftware und verwandten Anwendungen.
### 3. Wo finde ich Support für Aspose.Finance?
Sie können im offiziellen Support-Forum Hilfe von der Aspose.Finance-Community erhalten.
### 4. Kann ich das Schemareferenzpräfix anpassen?
Ja, Sie können ein geeignetes Präfix auswählen, wenn Sie mit Aspose.Finance für .NET eine Schemareferenz zu einem XBRL-Dokument hinzufügen.
### 5. Unterstützt Aspose.Finance außer XBRL noch andere Finanzformate?
Ja, Aspose.Finance unterstützt verschiedene Finanzformate und -standards und ermöglicht so eine nahtlose Integration in verschiedene Finanzanwendungen.
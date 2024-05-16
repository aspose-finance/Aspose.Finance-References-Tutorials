---
title: Einheit zum XBRL-Dokument hinzufügen
linktitle: Einheit zum XBRL-Dokument hinzufügen
second_title: Aspose.Finance .NET API
description: Erfahren Sie, wie Sie mit Aspose.Finance für .NET mühelos Einheiten zu XBRL-Dokumenten hinzufügen. Verbessern Sie noch heute Ihre Möglichkeiten zur Verarbeitung finanzieller Daten!
type: docs
weight: 16
url: /de/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
Willkommen in der Welt von Aspose.Finance für .NET – Ihrem Tor zur effizienten Bearbeitung von Finanzdokumenten in .NET-Anwendungen. Egal, ob Sie Buchhaltungssoftware, Finanzanalysetools oder andere Finanzanwendungen erstellen, Aspose.Finance für .NET bietet Ihnen einen umfassenden Satz an Funktionen zur Optimierung Ihres Entwicklungsprozesses.
## Voraussetzungen
Bevor wir uns mit der Nutzung der Leistungsfähigkeit von Aspose.Finance für .NET befassen, stellen wir sicher, dass die erforderlichen Voraussetzungen erfüllt sind:
### 1. Visual Studio-Installation
Stellen Sie sicher, dass Visual Studio auf Ihrem System installiert ist. Wenn nicht, können Sie es von der offiziellen Microsoft-Website herunterladen und installieren.
### 2. Erwerben Sie eine Lizenz
 Um das volle Potenzial von Aspose.Finance für .NET auszuschöpfen, benötigen Sie eine gültige Lizenz. Sie können eine Lizenz erwerben bei[Hier](https://purchase.aspose.com/buy) oder entscheiden Sie sich für eine temporäre Lizenz zu Testzwecken.
### 3. Aspose.Finance für .NET herunterladen und referenzieren
 Laden Sie die Aspose.Finance für .NET-Bibliothek herunter von der[Veröffentlichungsseite](https://releases.aspose.com/finance/net/) und verweisen Sie in Ihrem .NET-Projekt darauf.
### 4. Zugriff auf Dokumentation und Support
 Weitere Informationen finden Sie im[Dokumentation](https://reference.aspose.com/finance/net/)für detaillierte Informationen zur Verwendung von Aspose.Finance für .NET. Darüber hinaus können Sie sich an die Aspose.Finance-Community wenden unter[Hilfeforum](https://forum.aspose.com/c/finance/43).
## Namespaces importieren
Importieren wir nun die erforderlichen Namespaces in Ihr .NET-Projekt:
## Schritt 1: Aspose.Finance-Namespace hinzufügen
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Dieser Namespace enthält Klassen und Methoden, die für die Arbeit mit XBRL-Dokumenten und -Daten wichtig sind.
Lassen Sie uns das bereitgestellte Beispiel in mehrere Schritte aufteilen, um zu verstehen, wie mit Aspose.Finance für .NET eine Einheit zu einem XBRL-Dokument hinzugefügt wird.
## Schritt 1: Ausgabeverzeichnis definieren
```csharp
// Ausgabe Verzeichnis
string outputDir = "Your Output Directory";
```
 Ersetzen`"Your Output Directory"` durch den tatsächlichen Pfad zu Ihrem gewünschten Ausgabeverzeichnis.
## Schritt 2: Erstellen Sie ein XBRL-Dokument
```csharp
XbrlDocument document = new XbrlDocument();
```
Dadurch wird eine neue Instanz des XBRL-Dokuments initialisiert.
## Schritt 3: Zugriff auf XBRL-Instanzen
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Dadurch wird die Sammlung der XBRL-Instanzen aus dem Dokument abgerufen und eine neue Instanz hinzugefügt.
## Schritt 4: Einheit hinzufügen
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Dadurch wird eine neue Maßeinheit (in diesem Fall USD) erstellt und der XBRL-Instanz hinzugefügt. Sie können den Währungscode und den Namespace-URI nach Bedarf anpassen.
## Schritt 5: Speichern Sie das Dokument
```csharp
document.Save(outputDir + @"document4.xbrl");
```
Dadurch wird das geänderte XBRL-Dokument im angegebenen Ausgabeverzeichnis gespeichert.
## Abschluss
Zusammenfassend lässt sich sagen, dass Aspose.Finance für .NET Entwicklern die mühelose Bearbeitung von Finanzdokumenten und -daten in ihren .NET-Anwendungen ermöglicht. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie Aspose.Finance für .NET nahtlos in Ihre Projekte integrieren und deren Finanzverarbeitungsfunktionen verbessern.
## FAQs
### 1. Kann ich Aspose.Finance für .NET ohne Lizenz verwenden?
Nein, zum Freischalten des vollen Funktionsumfangs von Aspose.Finance für .NET ist eine gültige Lizenz erforderlich. Für Testzwecke sind jedoch temporäre Lizenzen verfügbar.
### 2. Ist Aspose.Finance für .NET zum Erstellen von Buchhaltungssoftware geeignet?
Ja, Aspose.Finance für .NET bietet robuste Funktionen, die auf die Erstellung von Buchhaltungssoftware und verwandten Finanzanwendungen zugeschnitten sind.
### 3. Wo finde ich Support für Aspose.Finance für .NET?
Sie können im Support-Forum Hilfe von der Aspose.Finance-Community erhalten.
### 4. Kann ich die Maßeinheit in einem XBRL-Dokument anpassen?
Ja, Sie können mit Aspose.Finance für .NET benutzerdefinierte Maßeinheiten zu XBRL-Dokumenten erstellen und hinzufügen.
### 5. Unterstützt Aspose.Finance für .NET mehrere Währungen?
Ja, Aspose.Finance für .NET unterstützt mehrere Währungen und ermöglicht so eine vielseitige Verarbeitung finanzieller Daten.
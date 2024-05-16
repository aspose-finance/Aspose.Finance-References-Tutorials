---
title: ARC-Rollenverweis zum XBRL-Dokument hinzufügen
linktitle: ARC-Rollenverweis zum XBRL-Dokument hinzufügen
second_title: Aspose.Finance .NET API
description: Erfahren Sie, wie Sie XBRL-Dokumente mit Aspose.Finance für .NET effizient bearbeiten. Fügen Sie mit einer Schritt-für-Schritt-Anleitung mühelos ARC-Rollenverweise hinzu.
type: docs
weight: 10
url: /de/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## Einführung
In der Welt des Finanzdatenmanagements und der Berichterstattung spielt die eXtensible Business Reporting Language (XBRL) eine entscheidende Rolle. Sie standardisiert die Art und Weise, wie Finanzinformationen kommuniziert und ausgetauscht werden, und sorgt so für Konsistenz, Genauigkeit und Effizienz. Die Bearbeitung von XBRL-Dokumenten, insbesondere bei der Einbindung spezifischer Rollen und Referenzen, erfordert jedoch ein differenziertes Verständnis der zugrunde liegenden Mechanismen. Dieses Tutorial konzentriert sich auf eine solche Aufgabe: das Hinzufügen einer ARC-Rollenreferenz zu einem XBRL-Dokument mithilfe von Aspose.Finance für .NET.
## Voraussetzungen
Bevor Sie mit dem Lernprogramm beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
### Umgebungs-Setup
1.  Installieren Sie Aspose.Finance für .NET: Laden Sie die Aspose.Finance für .NET-Bibliothek herunter und installieren Sie sie von der[Mitteilungen](https://releases.aspose.com/finance/net/).
   
2. Entwicklungsumgebung: Richten Sie Ihre Entwicklungsumgebung mit Visual Studio oder einer anderen bevorzugten IDE ein.
## Namespaces importieren
Stellen Sie sicher, dass Sie die erforderlichen Namespaces in Ihren C#-Code importieren:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Schritt 1: Quell- und Ausgabeverzeichnisse definieren
Bevor Sie fortfahren, geben Sie die Quell- und Ausgabeverzeichnisse an, in denen Ihre XBRL-Dateien liegen bzw. gespeichert werden.
```csharp
// Quellverzeichnis
string sourceDir = "Your Source Directory";
// Ausgabe Verzeichnis
string outputDir = "Your Output Directory";
```
## Schritt 2: Erstellen Sie ein XBRL-Dokument
 Instanziieren Sie einen`XbrlDocument` Objekt zum Arbeiten mit XBRL-Daten.
```csharp
XbrlDocument document = new XbrlDocument();
```
## Schritt 3: Zugriff auf die XbrlInstance-Sammlung
Greifen Sie auf die Sammlung von XBRL-Instanzen im Dokument zu.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## Schritt 4: XbrlInstance hinzufügen
Fügen Sie der Sammlung eine neue XBRL-Instanz hinzu.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Schritt 5: Schemaverweis hinzufügen
Fügen Sie in die XBRL-Instanz eine Schemareferenz ein und geben Sie das Quellverzeichnis, das Namespace-Präfix und die URI an.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
## Schritt 6: ArcroleType abrufen
 Abrufen der`ArcroleType` basierend auf einer bestimmten URI.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## Schritt 7: ArcroleReference hinzufügen
 Wenn das`ArcroleType` gefunden wird, erstellen Sie eine`ArcroleReference` und fügen Sie es den Arcrole-Referenzen der XBRL-Instanz hinzu.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## Schritt 8: Speichern Sie das Dokument
Speichern Sie das geänderte XBRL-Dokument im angegebenen Ausgabeverzeichnis.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## Abschluss
In diesem Tutorial haben wir untersucht, wie man mit Aspose.Finance für .NET einem XBRL-Dokument eine ARC-Rollenreferenz hinzufügt. Indem Sie diese Schritt-für-Schritt-Anleitung befolgen und die Funktionen von Aspose.Finance nutzen, können Sie XBRL-Daten effizient verwalten und bearbeiten, um Ihre spezifischen Anforderungen zu erfüllen.
## FAQs
### Was ist XBRL?
XBRL steht für eXtensible Business Reporting Language, eine standardisierte Sprache für die elektronische Kommunikation von Geschäfts- und Finanzdaten.
### Warum ist XBRL wichtig?
XBRL gewährleistet Konsistenz, Genauigkeit und Effizienz beim Austausch und der Analyse von Finanzinformationen und kommt damit Aufsichtsbehörden, Analysten und Unternehmen zugute.
### Kann Aspose.Finance komplexe XBRL-Aufgaben bewältigen?
Ja, Aspose.Finance bietet robuste Funktionen für die Arbeit mit XBRL-Dokumenten, einschließlich der Handhabung komplexer Aufgaben wie Rollenreferenzen und Taxonomieverwaltung.
### Ist Aspose.Finance mit anderen .NET-Bibliotheken kompatibel?
Ja, Aspose.Finance lässt sich nahtlos in andere .NET-Bibliotheken integrieren und bietet umfassende Unterstützung für die Manipulation und Berichterstattung von Finanzdaten.
### Wo finde ich zusätzliche Unterstützung für Aspose.Finance?
 Für zusätzliche Unterstützung besuchen Sie die[Aspose.Finance Support-Seite](https://forum.aspose.com/c/finance/43).
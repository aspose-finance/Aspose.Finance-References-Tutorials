---
title: Element zum XBRL-Dokument hinzufügen
linktitle: Element zum XBRL-Dokument hinzufügen
second_title: Aspose.Finance .NET API
description: Erfahren Sie, wie Sie mit Aspose.Finance für .NET Elemente zu XBRL-Dokumenten hinzufügen. Vereinfachen Sie die Finanzberichterstattung in Ihren .NET-Anwendungen. #Aspose #Finance
type: docs
weight: 13
url: /de/net/xbrl-file-creation/add-item-to-xbrl-document/
---
Extensible Business Reporting Language (XBRL) hat sich zu einem Standardformat für Finanzberichte entwickelt und ermöglicht eine effiziente und genaue Kommunikation von Finanzdaten. Aspose.Finance für .NET bietet robuste Funktionen für die Arbeit mit XBRL-Dokumenten in Ihren .NET-Anwendungen. In diesem Tutorial führen wir Sie durch die Schritte zum Hinzufügen eines Elements zu einem XBRL-Dokument mit Aspose.Finance für .NET.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
### 1. Installieren Sie Aspose.Finance für .NET
 Wenn Sie es noch nicht getan haben, laden Sie Aspose.Finance für .NET herunter und installieren Sie es von der[offizielle Website](https://releases.aspose.com/finance/net/)Befolgen Sie die Installationsanweisungen, um die Bibliothek in Ihrer .NET-Umgebung einzurichten.
### 2. Richten Sie Ihre Entwicklungsumgebung ein
Stellen Sie sicher, dass Sie über eine funktionierende Entwicklungsumgebung für die .NET-Entwicklung verfügen. Sie benötigen eine kompatible IDE wie Visual Studio sowie das auf Ihrem System installierte .NET-Framework.
## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces in Ihre .NET-Anwendung, um die von Aspose.Finance für .NET bereitgestellte Funktionalität zu nutzen.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Jetzt zerlegen wir den Beispielcode in mehrere Schritte:
## Schritt 1: Quell- und Ausgabeverzeichnisse definieren
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Ersetzen`"Your Source Directory"` Und`"Your Output Directory"` mit den Pfaden zu Ihren Quell- und Ausgabeverzeichnissen.
## Schritt 2: Erstellen eines XBRL-Dokuments und einer XBRL-Instanz
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Initialisieren Sie ein XBRL-Dokument und eine Instanz, mit der Sie arbeiten möchten.
## Schritt 3: Schemaverweis hinzufügen
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
Fügen Sie der XBRL-Instanz eine Schemareferenz hinzu, indem Sie den Pfad zur Schemadatei angeben und Details zum Namespace festlegen.
## Schritt 4: Kontext und Entität definieren
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
Erstellen Sie einen Kontext und eine Entität für die XBRL-Instanz und geben Sie den Zeitraum und die Entitätsdetails an.
## Schritt 5: Einheit hinzufügen
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Definieren Sie eine Einheit für die XBRL-Instanz und geben Sie die qualifizierten Namen der Kennzahl an.
## Schritt 6: Artikel hinzufügen
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
Fügen Sie der XBRL-Instanz ein Element hinzu und geben Sie dessen Konzept, Kontext, Einheit, Genauigkeit und Wert an.
## Schritt 7: Dokument speichern
```csharp
document.Save(outputDir + @"document5.xbrl");
```
Speichern Sie das XBRL-Dokument im Ausgabeverzeichnis.
## Abschluss
Das Hinzufügen von Elementen zu einem XBRL-Dokument ist für die genaue Darstellung von Finanzdaten unerlässlich. Aspose.Finance für .NET vereinfacht diesen Prozess, indem es eine umfassende API für die Arbeit mit XBRL-Dokumenten in .NET-Anwendungen bereitstellt.
## FAQs
### Kann ich Aspose.Finance für .NET mit jeder .NET-Anwendung verwenden?
Ja, Aspose.Finance für .NET ist mit jeder .NET-Anwendung kompatibel, einschließlich ASP.NET, WinForms und Konsolenanwendungen.
### Ist die Nutzung von Aspose.Finance für .NET kostenlos?
 Aspose.Finance für .NET ist eine kommerzielle Bibliothek. Sie können eine kostenlose Testversion herunterladen, um die Funktionen zu testen. Lizenzen können bei[Hier](https://purchase.aspose.com/buy).
### Unterstützt Aspose.Finance für .NET außer XBRL noch andere Finanzberichtsformate?
Aspose.Finance für .NET konzentriert sich hauptsächlich auf XBRL-bezogene Funktionen. Aspose bietet jedoch auch andere Bibliotheken für die Arbeit mit verschiedenen Finanzformaten.
### Wie kann ich Support für Aspose.Finance für .NET erhalten?
 Sie erhalten Support für Aspose.Finance für .NET über die[offizielles Forum](https://forum.aspose.com/c/finance/43)wo Sie Fragen stellen und mit anderen Benutzern und dem Supportpersonal interagieren können.
### Kann ich eine temporäre Lizenz für Aspose.Finance für .NET erhalten?
 Ja, es sind temporäre Lizenzen für Aspose.Finance für .NET zu Testzwecken verfügbar. Sie können eine erhalten[Hier](https://purchase.aspose.com/temporary-license/).
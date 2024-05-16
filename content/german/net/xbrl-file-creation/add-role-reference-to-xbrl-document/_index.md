---
title: Rollenreferenz zum XBRL-Dokument hinzufügen
linktitle: Rollenreferenz zum XBRL-Dokument hinzufügen
second_title: Aspose.Finance .NET API
description: Erfahren Sie, wie Sie mit Aspose.Finance für .NET Rollenverweise zu XBRL-Dokumenten hinzufügen. Vereinfachen Sie mit diesem Tutorial die Finanzberichterstattung in Ihren .NET-Anwendungen.
type: docs
weight: 14
url: /de/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
XBRL (eXtensible Business Reporting Language) hat sich zum Standard für den Austausch von Geschäftsinformationen entwickelt, insbesondere im Finanzberichtswesen. Aspose.Finance für .NET vereinfacht die Arbeit mit XBRL-Dokumenten in .NET-Anwendungen. Dieses Tutorial führt Sie durch den Prozess des Hinzufügens einer Rollenreferenz zu einem XBRL-Dokument mit Aspose.Finance für .NET.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
### 1. Installieren Sie Aspose.Finance für .NET
Stellen Sie sicher, dass Aspose.Finance für .NET in Ihrer Entwicklungsumgebung installiert ist. Wenn Sie es noch nicht getan haben, laden Sie es von der[Mitteilungen](https://releases.aspose.com/finance/net/) und folgen Sie den Installationsanweisungen.
### 2. Richten Sie Ihre Entwicklungsumgebung ein
Stellen Sie sicher, dass Sie über eine funktionierende Entwicklungsumgebung für die .NET-Entwicklung verfügen. Dazu gehört eine kompatible IDE wie Visual Studio und das auf Ihrem System installierte .NET-Framework.
## Namespaces importieren
Importieren Sie zunächst die erforderlichen Namespaces in Ihre .NET-Anwendung, um auf die von Aspose.Finance für .NET bereitgestellte Funktionalität zuzugreifen.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## Schritt 4: Rollentyp abrufen und Rollenreferenz hinzufügen
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
Rufen Sie den Rollentyp anhand seiner URI ab und fügen Sie der XBRL-Instanz eine Rollenreferenz hinzu.
## Schritt 5: Dokument speichern
```csharp
document.Save(outputDir + @"document7.xbrl");
```
Speichern Sie das XBRL-Dokument im Ausgabeverzeichnis.
## Abschluss
Das Hinzufügen von Rollenverweisen zu XBRL-Dokumenten ist entscheidend, um die Rollen verschiedener Elemente im Dokument zu definieren. Aspose.Finance für .NET bietet eine unkomplizierte Möglichkeit, diese Aufgabe zu erledigen, und ermöglicht Entwicklern, effizient mit XBRL-Dokumenten in ihren .NET-Anwendungen zu arbeiten.
## FAQs
### Kann ich Aspose.Finance für .NET mit jeder .NET-Anwendung verwenden?
Ja, Aspose.Finance für .NET ist mit jeder .NET-Anwendung kompatibel, einschließlich ASP.NET, WinForms und Konsolenanwendungen.
### Ist die Nutzung von Aspose.Finance für .NET kostenlos?
 Aspose.Finance für .NET ist eine kommerzielle Bibliothek. Sie können eine kostenlose Testversion herunterladen, um die Funktionen zu testen. Lizenzen können bei[Hier](https://purchase.aspose.com/buy).
### Unterstützt Aspose.Finance für .NET außer XBRL noch andere Finanzberichtsformate?
Aspose.Finance für .NET konzentriert sich hauptsächlich auf XBRL-bezogene Funktionen. Aspose bietet jedoch auch andere Bibliotheken für die Arbeit mit verschiedenen Finanzformaten.
### Wie kann ich Support für Aspose.Finance für .NET erhalten?
 Sie erhalten Support für Aspose.Finance für .NET über die[Forum](https://forum.aspose.com/c/finance/43)wo Sie Fragen stellen und mit anderen Benutzern und dem Supportpersonal interagieren können.
### Kann ich eine temporäre Lizenz für Aspose.Finance für .NET erhalten?
 Ja, es sind temporäre Lizenzen für Aspose.Finance für .NET zu Testzwecken verfügbar. Sie können eine erhalten[Hier](https://purchase.aspose.com/temporary-license/).
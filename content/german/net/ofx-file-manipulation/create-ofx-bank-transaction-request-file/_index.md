---
title: OFX Bank-Transaktionsanforderungsdatei erstellen
linktitle: OFX Bank-Transaktionsanforderungsdatei erstellen
second_title: Aspose.Finance .NET API
description: Erfahren Sie in unserer ausführlichen Schritt-für-Schritt-Anleitung, wie Sie mit Aspose.Finance für .NET eine OFX-Banktransaktionsanforderungsdatei erstellen. #Aspose #Finance
type: docs
weight: 12
url: /de/net/ofx-file-manipulation/create-ofx-bank-transaction-request-file/
---
Das Erstellen einer OFX-Banktransaktionsanforderungsdatei kann entmutigend erscheinen, aber mit den richtigen Tools und Anleitungen kann es ein unkomplizierter Prozess sein. In diesem Tutorial führen wir Sie durch jeden Schritt der Generierung einer OFX-Banktransaktionsanforderungsdatei mit Aspose.Finance für .NET. Wir behandeln die Voraussetzungen, die erforderlichen Namespaces und stellen eine detaillierte Schritt-für-Schritt-Anleitung bereit, damit Sie problemlos mitmachen können.
## Voraussetzungen
Bevor wir mit dem Tutorial beginnen, müssen Sie einige Dinge vorbereitet haben:
1.  Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem Computer installiert ist. Sie können es von der[offizielle Website](https://visualstudio.microsoft.com/).
2.  Aspose.Finance für .NET: Sie benötigen die Bibliothek Aspose.Finance für .NET. Sie können sie herunterladen von[Hier](https://releases.aspose.com/finance/net/).
3. Grundlegende C#-Kenntnisse: Das Verständnis der Grundlagen der C#-Programmierung wird Ihnen helfen, den Codebeispielen zu folgen.
Sobald diese Voraussetzungen erfüllt sind, können Sie loslegen!
## Namespaces importieren
Lassen Sie uns zunächst die erforderlichen Namespaces importieren. Diese Namespaces sind für den Zugriff auf die Klassen und Methoden, die zum Erstellen der OFX-Banktransaktionsanforderungsdatei erforderlich sind, von entscheidender Bedeutung.
```csharp
using Aspose.Finance.Ofx;
using Aspose.Finance.Ofx.Bank;
using Aspose.Finance.Ofx.Signon;
using System;
```
## Schritt 1: Einrichten des Arbeitsverzeichnisses
Bevor wir mit der Erstellung der OFX-Anforderungsdatei beginnen, müssen wir das Ausgabeverzeichnis angeben, in dem die Datei gespeichert wird.
```csharp
string outputDir = "Your Output Directory";
```
 Ersetzen`"Your Output Directory"` durch den Pfad zum Verzeichnis, in dem Sie die generierte Datei speichern möchten.
## Schritt 2: Erstellen Sie das OFX-Anforderungsdokument
 Als nächstes müssen wir eine Instanz des`OfxRequestDocument` Klasse. Diese Klasse dient als Container für unsere OFX-Anfrage.
```csharp
OfxRequestDocument document = new OfxRequestDocument();
```
## Schritt 3: Einrichten der Anmeldeanforderung
Die Anmeldeanforderung ist für die Authentifizierung des Benutzers und das Einleiten der OFX-Sitzung erforderlich. Wir richten die Anmeldeanforderungsnachricht ein und füllen sie mit den erforderlichen Details wie Kundendatum, Benutzer-ID, Kennwort und Informationen zum Finanzinstitut.
```csharp
document.SignonRequestMessageSetV1 = new SignonRequestMessageSetV1();
SignonRequest signonRequest = new SignonRequest();
document.SignonRequestMessageSetV1.SignonRequest = signonRequest;
signonRequest.ClientDate = "20200611000000";
signonRequest.UserId = "aspose";
signonRequest.UserPassword = "password";
FinancialInstitution fi = new FinancialInstitution();
fi.Organization = "aspose";
fi.FinancialInstitutionId = "1";
signonRequest.FinancialInstitution = fi;
signonRequest.AppVersion = "1.0";
signonRequest.AppId = "Aspose.Finance";
signonRequest.ClientUserId = "aaaaaaa";
```
## Schritt 4: Einrichten der Bankanforderungsnachricht
Nachdem die Anmeldeanforderung nun eingerichtet ist, können wir mit der Erstellung der Bankanforderungsnachricht fortfahren. Diese Nachricht enthält die Details des Bankkontos und die Transaktionsauszugsanforderung.
```csharp
document.BankRequestMessageSetV1 = new BankRequestMessageSetV1();
StatementTransactionRequest stmtTransRequest = new StatementTransactionRequest();
document.BankRequestMessageSetV1.StatementTransactionRequests.Add(stmtTransRequest);
stmtTransRequest.TransactionUniqueId = "1111111";
stmtTransRequest.StatementRequest = new StatementRequest();
stmtTransRequest.StatementRequest.BankAccountFrom = new BankAccount();
stmtTransRequest.StatementRequest.BankAccountFrom.BankId = "sssss";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountId = "sfsdfsfsdf";
stmtTransRequest.StatementRequest.BankAccountFrom.AccountType = AccountEnum.CHECKING;
```
## Schritt 5: Transaktionsdetails angeben
 Um bestimmte Transaktionen abzurufen, müssen wir den Datumsbereich angeben und ob Transaktionen in die Anfrage einbezogen werden sollen. Dies geschieht durch die Einrichtung des`IncTransaction` Objekt.
```csharp
stmtTransRequest.StatementRequest.IncTransaction = new IncTransaction();
stmtTransRequest.StatementRequest.IncTransaction.StartDate = "20200601000000";
stmtTransRequest.StatementRequest.IncTransaction.EndDate = "20200611000000";
stmtTransRequest.StatementRequest.IncTransaction.Include = true;
```
## Schritt 6: Speichern Sie das OFX-Anforderungsdokument
Abschließend speichern wir das OFX-Anforderungsdokument sowohl im XML- als auch im SGML-Format. Dadurch wird die Kompatibilität mit verschiedenen Systemen sichergestellt, die möglicherweise eines der beiden Formate verwenden.
```csharp
document.Save(outputDir + @"newOfxRequestBankStatement.xml", OfxVersionEnum.V2x);
document.Save(outputDir + @"newOfxRequestBankStatement.sgml", OfxVersionEnum.V1x);
```
## Schritt 7: Erfolgreiche Ausführung bestätigen
Um zu bestätigen, dass der Vorgang erfolgreich ausgeführt wurde, können wir eine Nachricht auf der Konsole ausgeben.
```csharp
Console.WriteLine("CreateOfxBankTransactionRequestFile executed successfully.");
```
## Abschluss
Das Erstellen einer OFX-Banktransaktionsanforderungsdatei mit Aspose.Finance für .NET ist ein methodischer Prozess, der das Einrichten eines Anforderungsdokuments, das Konfigurieren von Anmelde- und Bankanforderungsnachrichten, das Angeben von Transaktionsdetails und das Speichern des Dokuments umfasst. Indem Sie dieser Schritt-für-Schritt-Anleitung folgen, können Sie effizient OFX-Anforderungsdateien erstellen, die auf Ihre spezifischen Anforderungen zugeschnitten sind.
## FAQs
### 1. Was ist eine OFX-Datei?
Eine OFX-Datei (Open Financial Exchange) ist ein Standardformat für den Austausch von Finanzdaten zwischen Institutionen und Benutzern. Es wird häufig für Kontoauszüge, Transaktionen und andere Finanzaktivitäten verwendet.
### 2. Kann ich Aspose.Finance für .NET mit anderen Programmiersprachen verwenden?
Aspose.Finance für .NET ist speziell für die Verwendung mit .NET-Sprachen wie C# konzipiert. Sie können es jedoch in jeder .NET-unterstützten Umgebung verwenden.
### 3. Gibt es eine kostenlose Testversion für Aspose.Finance für .NET?
Ja, Sie können eine kostenlose Testversion von Aspose.Finance für .NET herunterladen von[Hier](https://releases.aspose.com/).
### 4. Wie erhalte ich Support für Aspose.Finance für .NET?
 Sie können Unterstützung von der Aspose-Community und dem technischen Team erhalten über deren[Hilfeforum](https://forum.aspose.com/c/finance/43).
### 5. Kann ich eine temporäre Lizenz für Aspose.Finance für .NET erhalten?
 Ja, Aspose bietet eine[vorläufige Lizenz](https://purchase.aspose.com/temporary-license/) mit deren Hilfe Sie das Produkt bewerten können.
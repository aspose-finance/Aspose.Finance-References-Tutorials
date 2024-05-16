---
title: Προσθήκη αντικειμένου στο έγγραφο XBRL
linktitle: Προσθήκη αντικειμένου στο έγγραφο XBRL
second_title: Aspose.Finance .NET API
description: Μάθετε πώς να προσθέτετε στοιχεία σε έγγραφα XBRL χρησιμοποιώντας το Aspose.Finance για .NET. Απλοποιήστε τις οικονομικές αναφορές στις εφαρμογές σας .NET. #Αποθέστε #Οικονομικά
type: docs
weight: 13
url: /el/net/xbrl-file-creation/add-item-to-xbrl-document/
---
Η Extensible Business Reporting Language (XBRL) έχει γίνει μια τυπική μορφή για τις οικονομικές αναφορές, που επιτρέπει την αποτελεσματική και ακριβή επικοινωνία των οικονομικών δεδομένων. Το Aspose.Finance for .NET παρέχει ισχυρή λειτουργικότητα για εργασία με έγγραφα XBRL στις εφαρμογές σας .NET. Σε αυτό το σεμινάριο, θα ακολουθήσουμε τα βήματα για την προσθήκη ενός στοιχείου σε ένα έγγραφο XBRL χρησιμοποιώντας το Aspose.Finance για .NET.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
### 1. Εγκαταστήστε το Aspose.Finance για .NET
 Εάν δεν το έχετε κάνει ήδη, κατεβάστε και εγκαταστήστε το Aspose.Finance για .NET από το[επίσημη ιστοσελίδα](https://releases.aspose.com/finance/net/). Ακολουθήστε τις οδηγίες εγκατάστασης για να ρυθμίσετε τη βιβλιοθήκη στο περιβάλλον σας .NET.
### 2. Ρυθμίστε το Αναπτυξιακό σας Περιβάλλον
Βεβαιωθείτε ότι έχετε ένα εργασιακό περιβάλλον ανάπτυξης για την ανάπτυξη .NET. Θα χρειαστείτε ένα συμβατό IDE όπως το Visual Studio, μαζί με το πλαίσιο .NET εγκατεστημένο στο σύστημά σας.
## Εισαγωγή χώρων ονομάτων
Αρχικά, εισαγάγετε τους απαραίτητους χώρους ονομάτων στην εφαρμογή σας .NET για να χρησιμοποιήσετε τη λειτουργικότητα που παρέχεται από το Aspose.Finance για το .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
```
#Τώρα ας αναλύσουμε το παράδειγμα κώδικα σε πολλά βήματα:
## Βήμα 1: Ορισμός καταλόγου προέλευσης και εξόδου
```csharp
string sourceDir = "Your Source Directory";
string outputDir = "Your Output Directory";
```
 Αντικαθιστώ`"Your Source Directory"` και`"Your Output Directory"` με τις διαδρομές προς τους καταλόγους προέλευσης και εξόδου, αντίστοιχα.
## Βήμα 2: Δημιουργήστε ένα έγγραφο και ένα παράδειγμα XBRL
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Αρχικοποιήστε ένα έγγραφο και μια παρουσία XBRL για εργασία.
## Βήμα 3: Προσθήκη αναφοράς σχήματος
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
Προσθέστε μια αναφορά σχήματος στην παρουσία XBRL, παρέχοντας τη διαδρομή προς το αρχείο σχήματος και προσδιορίζοντας τις λεπτομέρειες του χώρου ονομάτων.
## Βήμα 4: Ορίστε το πλαίσιο και την οντότητα
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
xbrlInstance.Contexts.Add(context);
```
Δημιουργήστε ένα περιβάλλον και μια οντότητα για την παρουσία XBRL, προσδιορίζοντας την περίοδο και τις λεπτομέρειες της οντότητας.
## Βήμα 5: Προσθήκη μονάδας
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Καθορίστε μια μονάδα για την παρουσία XBRL, προσδιορίζοντας τα ονόματα των χαρακτηριστικών μετρήσεων.
## Βήμα 6: Προσθήκη αντικειμένου
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
Προσθέστε ένα στοιχείο στην παρουσία XBRL, προσδιορίζοντας την έννοια, το πλαίσιο, τη μονάδα, την ακρίβεια και την αξία του.
## Βήμα 7: Αποθήκευση εγγράφου
```csharp
document.Save(outputDir + @"document5.xbrl");
```
Αποθηκεύστε το έγγραφο XBRL στον κατάλογο εξόδου.
## συμπέρασμα
Η προσθήκη στοιχείων σε ένα έγγραφο XBRL είναι απαραίτητη για την ακριβή αναπαράσταση των οικονομικών δεδομένων. Το Aspose.Finance for .NET απλοποιεί αυτή τη διαδικασία παρέχοντας ένα ολοκληρωμένο API για εργασία με έγγραφα XBRL σε εφαρμογές .NET.
## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Finance για .NET με οποιαδήποτε εφαρμογή .NET;
Ναι, το Aspose.Finance για .NET είναι συμβατό με οποιαδήποτε εφαρμογή .NET, συμπεριλαμβανομένων των εφαρμογών ASP.NET, WinForms και Console.
### Είναι δωρεάν η χρήση του Aspose.Finance για .NET;
 Το Aspose.Finance for .NET είναι μια εμπορική βιβλιοθήκη. Μπορείτε να πραγματοποιήσετε λήψη μιας δωρεάν δοκιμαστικής έκδοσης για να αξιολογήσετε τις δυνατότητές της και από την οποία μπορείτε να αγοράσετε άδειες[εδώ](https://purchase.aspose.com/buy).
### Το Aspose.Finance for .NET υποστηρίζει άλλες μορφές οικονομικών αναφορών εκτός από το XBRL;
Το Aspose.Finance for .NET εστιάζει κυρίως στη λειτουργικότητα που σχετίζεται με το XBRL. Ωστόσο, η Aspose προσφέρει άλλες βιβλιοθήκες για εργασία με διαφορετικές οικονομικές μορφές.
### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Finance για .NET;
 Μπορείτε να λάβετε υποστήριξη για το Aspose.Finance για .NET μέσω του[επίσημο φόρουμ](https://forum.aspose.com/c/finance/43)όπου μπορείτε να κάνετε ερωτήσεις και να αλληλεπιδράτε με άλλους χρήστες και το προσωπικό υποστήριξης.
### Μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Finance για .NET;
 Ναι, οι προσωρινές άδειες χρήσης για το Aspose.Finance για .NET είναι διαθέσιμες για δοκιμαστικούς σκοπούς. Μπορείτε να αποκτήσετε ένα[εδώ](https://purchase.aspose.com/temporary-license/).
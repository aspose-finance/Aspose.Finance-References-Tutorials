---
title: Προσθήκη συνδέσμου υποσημείωσης στο έγγραφο XBRL
linktitle: Προσθήκη συνδέσμου υποσημείωσης στο έγγραφο XBRL
second_title: Aspose.Finance .NET API
description: Μάθετε πώς να προσθέτετε συνδέσμους υποσημειώσεων σε έγγραφα XBRL χρησιμοποιώντας το Aspose.Finance για .NET. Βελτιώστε τις οικονομικές αναφορές με πρόσθετο πλαίσιο χωρίς κόπο.
type: docs
weight: 12
url: /el/net/xbrl-file-creation/add-footnote-link-to-xbrl-document/
---
Η προσθήκη ενός συνδέσμου υποσημείωσης σε ένα έγγραφο XBRL είναι ζωτικής σημασίας για την παροχή πρόσθετου πλαισίου ή επεξηγήσεων για συγκεκριμένα σημεία δεδομένων. Σε αυτό το σεμινάριο, θα ακολουθήσουμε τη διαδικασία βήμα προς βήμα χρησιμοποιώντας το Aspose.Finance για .NET.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
1.  Aspose.Finance για .NET: Βεβαιωθείτε ότι έχετε εγκαταστήσει το Aspose.Finance για .NET στο σύστημά σας. Μπορείτε να το κατεβάσετε από[εδώ](https://releases.aspose.com/finance/net/).
  
2. Περιβάλλον ανάπτυξης: Δημιουργήστε ένα περιβάλλον ανάπτυξης με .NET Framework ή .NET Core.
## Εισαγωγή χώρων ονομάτων:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Βήμα 1: Ορισμός καταλόγου προέλευσης και εξόδου
Αρχικά, καθορίστε τους καταλόγους για τα αρχεία προέλευσης και εξόδου:
```csharp
// Κατάλογος πηγής
string sourceDir = "Your Source Directory";
// Κατάλογο εξόδου
string outputDir = "Your Output Directory";
```
## Βήμα 2: Δημιουργήστε ένα έγγραφο και ένα παράδειγμα XBRL
Αρχικοποιήστε ένα έγγραφο και ένα παράδειγμα XBRL:
```csharp
XbrlDocument document = new XbrlDocument();
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Βήμα 3: Προσθήκη Αναφορών Σχήματος
Προσθέστε αναφορές σχήματος στην παρουσία XBRL:
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
SchemaRef schema = schemaRefs[0];
```
## Βήμα 4: Ορίστε το πλαίσιο
Ορίστε το πλαίσιο για την παρουσία XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
Context context = new Context(contextPeriod, contextEntity);
context.Id = "cd1";
xbrlInstance.Contexts.Add(context);
```
## Βήμα 5: Προσθήκη συνδέσμου υποσημείωσης
Δημιουργήστε και προσθέστε έναν σύνδεσμο υποσημείωσης στην παρουσία XBRL:
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
## Βήμα 6: Αποθηκεύστε το έγγραφο
Αποθηκεύστε το τροποποιημένο έγγραφο XBRL:
```csharp
document.Save(outputDir + @"document6.xbrl");
```

## συμπέρασμα
Η προσθήκη συνδέσμου υποσημείωσης σε ένα έγγραφο XBRL είναι μια απλή διαδικασία με το Aspose.Finance για .NET. Ακολουθώντας τα βήματα που περιγράφονται σε αυτό το σεμινάριο, μπορείτε να ενσωματώσετε απρόσκοπτα πρόσθετο πλαίσιο ή επεξηγήσεις στις οικονομικές σας αναφορές.
## Συχνές ερωτήσεις
### Μπορώ να προσθέσω πολλαπλούς συνδέσμους υποσημείωσης σε ένα μόνο έγγραφο XBRL;
Ναι, μπορείτε να προσθέσετε πολλούς συνδέσμους υποσημείωσης επαναλαμβάνοντας τα βήματα που περιγράφονται σε αυτόν τον οδηγό για κάθε πρόσθετο σύνδεσμο.
### Είναι το Aspose.Finance για .NET συμβατό τόσο με .NET Framework όσο και με .NET Core;
Ναι, το Aspose.Finance for .NET υποστηρίζει περιβάλλοντα .NET Framework και .NET Core.
### Πώς μπορώ να αποκτήσω μια προσωρινή άδεια για το Aspose.Finance για .NET;
 Μπορείτε να αποκτήσετε προσωρινή άδεια από[εδώ](https://purchase.aspose.com/temporary-license/).
### Το Aspose.Finance για .NET παρέχει υποστήριξη για επικύρωση XBRL;
Ναι, το Aspose.Finance για .NET προσφέρει ολοκληρωμένη υποστήριξη για την επικύρωση XBRL για τη διασφάλιση της συμμόρφωσης με τα βιομηχανικά πρότυπα.
### Πού μπορώ να βρω πρόσθετους πόρους και υποστήριξη για το Aspose.Finance για .NET;
 Μπορείτε να επισκεφθείτε το[Aspose.Finance για το φόρουμ .NET](https://forum.aspose.com/c/finance/43) για τεκμηρίωση υποστήριξης και πρόσβασης[εδώ](https://reference.aspose.com/finance/net/).
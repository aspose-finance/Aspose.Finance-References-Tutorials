---
title: Προσθήκη αναφοράς ρόλου ARC στο έγγραφο XBRL
linktitle: Προσθήκη αναφοράς ρόλου ARC στο έγγραφο XBRL
second_title: Aspose.Finance .NET API
description: Μάθετε πώς να χειρίζεστε αποτελεσματικά έγγραφα XBRL χρησιμοποιώντας το Aspose.Finance για .NET. Προσθέστε αναφορές ρόλων ARC χωρίς κόπο με καθοδήγηση βήμα προς βήμα.
type: docs
weight: 10
url: /el/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## Εισαγωγή
Στον κόσμο της διαχείρισης οικονομικών δεδομένων και των αναφορών, η εκτεταμένη γλώσσα αναφοράς επιχειρήσεων (XBRL) διαδραματίζει κρίσιμο ρόλο. Τυποποιεί τον τρόπο με τον οποίο κοινοποιούνται και ανταλλάσσονται οι οικονομικές πληροφορίες, διασφαλίζοντας συνέπεια, ακρίβεια και αποτελεσματικότητα. Ωστόσο, ο χειρισμός εγγράφων XBRL, ειδικά όταν ενσωματώνονται συγκεκριμένοι ρόλοι και αναφορές, απαιτεί μια λεπτή κατανόηση των υποκείμενων μηχανισμών. Αυτό το σεμινάριο εστιάζει σε μια τέτοια εργασία: την προσθήκη μιας αναφοράς ρόλου ARC σε ένα έγγραφο XBRL χρησιμοποιώντας το Aspose.Finance για .NET.
## Προαπαιτούμενα
Πριν βουτήξετε στο σεμινάριο, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
### Ρύθμιση περιβάλλοντος
1.  Εγκατάσταση Aspose.Finance για .NET: Κάντε λήψη και εγκατάσταση της βιβλιοθήκης Aspose.Finance για .NET από τη[εκδόσεις](https://releases.aspose.com/finance/net/).
   
2. Περιβάλλον ανάπτυξης: Ρυθμίστε το περιβάλλον ανάπτυξης με το Visual Studio ή οποιοδήποτε άλλο προτιμώμενο IDE.
## Εισαγωγή χώρων ονομάτων
Βεβαιωθείτε ότι έχετε εισαγάγει τους απαραίτητους χώρους ονομάτων στον κώδικα C#:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Βήμα 1: Ορισμός καταλόγου προέλευσης και εξόδου
Πριν συνεχίσετε, καθορίστε τους καταλόγους προέλευσης και εξόδου όπου θα βρίσκονται και θα αποθηκευτούν τα αρχεία XBRL, αντίστοιχα.
```csharp
// Κατάλογος πηγής
string sourceDir = "Your Source Directory";
// Κατάλογο εξόδου
string outputDir = "Your Output Directory";
```
## Βήμα 2: Δημιουργήστε ένα έγγραφο XBRL
 Instantiate an`XbrlDocument` αντικείμενο εργασίας με δεδομένα XBRL.
```csharp
XbrlDocument document = new XbrlDocument();
```
## Βήμα 3: Πρόσβαση στη Συλλογή XbrlInstance
Πρόσβαση στη συλλογή παρουσιών XBRL μέσα στο έγγραφο.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## Βήμα 4: Προσθήκη XbrlInstance
Προσθέστε μια νέα παρουσία XBRL στη συλλογή.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Βήμα 5: Προσθήκη αναφοράς σχήματος
Συμπεριλάβετε μια αναφορά σχήματος στην παρουσία XBRL, προσδιορίζοντας τον κατάλογο προέλευσης, το πρόθεμα χώρου ονομάτων και το URI.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://example.com/xbrl/taxonomy");
```
## Βήμα 6: Ανάκτηση ArcroleType
 Ανακτήστε το`ArcroleType` με βάση ένα συγκεκριμένο URI.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test");
```
## Βήμα 7: Προσθήκη ArcroleReference
 Αν το`ArcroleType` βρίσκεται, δημιουργείται ένα`ArcroleReference` και προσθέστε το στις αναφορές arcrole της παρουσίας XBRL.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## Βήμα 8: Αποθηκεύστε το έγγραφο
Αποθηκεύστε το τροποποιημένο έγγραφο XBRL στον καθορισμένο κατάλογο εξόδου.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## συμπέρασμα
Σε αυτό το σεμινάριο, εξερευνήσαμε πώς να προσθέσετε μια αναφορά ρόλου ARC σε ένα έγγραφο XBRL χρησιμοποιώντας το Aspose.Finance για .NET. Ακολουθώντας αυτές τις οδηγίες βήμα προς βήμα και αξιοποιώντας τις δυνατότητες του Aspose.Finance, μπορείτε να διαχειριστείτε και να χειριστείτε αποτελεσματικά τα δεδομένα XBRL για να ανταποκριθείτε στις συγκεκριμένες απαιτήσεις σας.
## Συχνές ερωτήσεις
### Τι είναι το XBRL;
Το XBRL σημαίνει εκτεταμένη γλώσσα αναφοράς επιχειρήσεων, μια τυποποιημένη γλώσσα για την ηλεκτρονική επικοινωνία επιχειρηματικών και οικονομικών δεδομένων.
### Γιατί είναι σημαντικό το XBRL;
Το XBRL διασφαλίζει συνέπεια, ακρίβεια και αποτελεσματικότητα στην ανταλλαγή και ανάλυση οικονομικών πληροφοριών, προς όφελος των ρυθμιστικών αρχών, των αναλυτών και των επιχειρήσεων.
### Μπορεί το Aspose.Finance να χειριστεί περίπλοκες εργασίες XBRL;
Ναι, το Aspose.Finance προσφέρει ισχυρή λειτουργικότητα για την εργασία με έγγραφα XBRL, συμπεριλαμβανομένου του χειρισμού πολύπλοκων εργασιών όπως οι αναφορές ρόλων και η διαχείριση ταξινόμησης.
### Είναι το Aspose.Finance συμβατό με άλλες βιβλιοθήκες .NET;
Ναι, το Aspose.Finance ενσωματώνεται απρόσκοπτα με άλλες βιβλιοθήκες .NET, παρέχοντας εκτεταμένη υποστήριξη για χειρισμό οικονομικών δεδομένων και αναφορά.
### Πού μπορώ να βρω πρόσθετη υποστήριξη για το Aspose.Finance;
 Για πρόσθετη υποστήριξη επισκεφθείτε το[Σελίδα υποστήριξης Aspose.Finance](https://forum.aspose.com/c/finance/43).
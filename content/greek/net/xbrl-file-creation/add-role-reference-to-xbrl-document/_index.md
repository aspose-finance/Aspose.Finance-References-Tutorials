---
title: Προσθήκη αναφοράς ρόλου στο έγγραφο XBRL
linktitle: Προσθήκη αναφοράς ρόλου στο έγγραφο XBRL
second_title: Aspose.Finance .NET API
description: Μάθετε πώς να προσθέτετε αναφορές ρόλων σε έγγραφα XBRL χρησιμοποιώντας το Aspose.Finance για .NET. Απλοποιήστε τις οικονομικές αναφορές στις εφαρμογές σας .NET με αυτό το σεμινάριο.
type: docs
weight: 14
url: /el/net/xbrl-file-creation/add-role-reference-to-xbrl-document/
---
Η XBRL (eXtensible Business Reporting Language) έχει γίνει ένα πρότυπο για την ανταλλαγή επιχειρηματικών πληροφοριών, ιδιαίτερα στη χρηματοοικονομική αναφορά. Το Aspose.Finance for .NET απλοποιεί την εργασία με έγγραφα XBRL σε εφαρμογές .NET. Αυτό το σεμινάριο θα σας καθοδηγήσει στη διαδικασία προσθήκης αναφοράς ρόλου σε ένα έγγραφο XBRL χρησιμοποιώντας το Aspose.Finance για .NET.
## Προαπαιτούμενα
Πριν ξεκινήσουμε, βεβαιωθείτε ότι έχετε τις ακόλουθες προϋποθέσεις:
### 1. Εγκαταστήστε το Aspose.Finance για .NET
Βεβαιωθείτε ότι έχετε εγκατεστημένο το Aspose.Finance for .NET στο περιβάλλον ανάπτυξης σας. Αν δεν το έχετε κάνει ήδη, κατεβάστε το από το[εκδόσεις](https://releases.aspose.com/finance/net/) και ακολουθήστε τις οδηγίες εγκατάστασης.
### 2. Ρυθμίστε το Αναπτυξιακό σας Περιβάλλον
Βεβαιωθείτε ότι έχετε ένα εργασιακό περιβάλλον ανάπτυξης για την ανάπτυξη .NET. Αυτό περιλαμβάνει ένα συμβατό IDE, όπως το Visual Studio και το πλαίσιο .NET που είναι εγκατεστημένο στο σύστημά σας.
## Εισαγωγή χώρων ονομάτων
Ξεκινήστε εισάγοντας τους απαραίτητους χώρους ονομάτων στην εφαρμογή σας .NET για πρόσβαση στη λειτουργικότητα που παρέχεται από το Aspose.Finance για το .NET.
```csharp
using Aspose.Finance.Xbrl;
using System;
using Aspose
.Finance.Xbrl.Roles;
```
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
## Βήμα 4: Ανάκτηση τύπου ρόλου και προσθήκη αναφοράς ρόλου
```csharp
SchemaRef schema = schemaRefs[0];
RoleType roleType = schema.GetRoleTypeByURI("http://abc.com/role/link1");
if (roleType != null)
{
    RoleReference roleReference = new RoleReference(roleType);
    xbrlInstance.RoleReferences.Add(roleReference);
}
```
Ανακτήστε τον τύπο ρόλου χρησιμοποιώντας το URI του και προσθέστε μια αναφορά ρόλου στην παρουσία XBRL.
## Βήμα 5: Αποθήκευση εγγράφου
```csharp
document.Save(outputDir + @"document7.xbrl");
```
Αποθηκεύστε το έγγραφο XBRL στον κατάλογο εξόδου.
## συμπέρασμα
Η προσθήκη αναφορών ρόλων σε έγγραφα XBRL είναι ζωτικής σημασίας για τον καθορισμό των ρόλων διαφόρων στοιχείων μέσα στο έγγραφο. Το Aspose.Finance for .NET παρέχει έναν απλό τρόπο για να ολοκληρώσετε αυτήν την εργασία, δίνοντας τη δυνατότητα στους προγραμματιστές να εργάζονται αποτελεσματικά με έγγραφα XBRL στις εφαρμογές τους .NET.
## Συχνές ερωτήσεις
### Μπορώ να χρησιμοποιήσω το Aspose.Finance για .NET με οποιαδήποτε εφαρμογή .NET;
Ναι, το Aspose.Finance για .NET είναι συμβατό με οποιαδήποτε εφαρμογή .NET, συμπεριλαμβανομένων των εφαρμογών ASP.NET, WinForms και Console.
### Είναι δωρεάν η χρήση του Aspose.Finance για .NET;
 Το Aspose.Finance for .NET είναι μια εμπορική βιβλιοθήκη. Μπορείτε να πραγματοποιήσετε λήψη μιας δωρεάν δοκιμαστικής έκδοσης για να αξιολογήσετε τις δυνατότητές της και από την οποία μπορείτε να αγοράσετε άδειες[εδώ](https://purchase.aspose.com/buy).
### Το Aspose.Finance for .NET υποστηρίζει άλλες μορφές οικονομικών αναφορών εκτός από το XBRL;
Το Aspose.Finance for .NET εστιάζει κυρίως στη λειτουργικότητα που σχετίζεται με το XBRL. Ωστόσο, η Aspose προσφέρει άλλες βιβλιοθήκες για εργασία με διαφορετικές οικονομικές μορφές.
### Πώς μπορώ να λάβω υποστήριξη για το Aspose.Finance για .NET;
 Μπορείτε να λάβετε υποστήριξη για το Aspose.Finance για .NET μέσω του[δικαστήριο](https://forum.aspose.com/c/finance/43)όπου μπορείτε να κάνετε ερωτήσεις και να αλληλεπιδράτε με άλλους χρήστες και το προσωπικό υποστήριξης.
### Μπορώ να αποκτήσω προσωρινή άδεια για το Aspose.Finance για .NET;
 Ναι, οι προσωρινές άδειες χρήσης για το Aspose.Finance για .NET είναι διαθέσιμες για δοκιμαστικούς σκοπούς. Μπορείτε να αποκτήσετε ένα[εδώ](https://purchase.aspose.com/temporary-license/).
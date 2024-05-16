---
title: Dodaj odniesienie do roli ARC do dokumentu XBRL
linktitle: Dodaj odniesienie do roli ARC do dokumentu XBRL
second_title: Aspose.Finance API .NET
description: Dowiedz się, jak efektywnie manipulować dokumentami XBRL za pomocą Aspose.Finance dla .NET. Dodaj odniesienia do ról ARC bez wysiłku, korzystając ze wskazówek krok po kroku.
type: docs
weight: 10
url: /pl/net/xbrl-file-creation/add-arc-role-reference-to-xbrl-document/
---
## Wstęp
świecie zarządzania danymi finansowymi i raportowania kluczową rolę odgrywa eXtensible Business Reporting Language (XBRL). Standaryzuje sposób przekazywania i wymiany informacji finansowych, zapewniając spójność, dokładność i efektywność. Jednakże manipulowanie dokumentami XBRL, zwłaszcza gdy uwzględniane są określone role i odniesienia, wymaga szczegółowego zrozumienia leżących u ich podstaw mechanizmów. Ten samouczek skupia się na jednym takim zadaniu: dodaniu odniesienia do roli ARC do dokumentu XBRL przy użyciu Aspose.Finance dla .NET.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
### Konfiguracja środowiska
1.  Zainstaluj Aspose.Finance dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Finance dla .NET z[wydania](https://releases.aspose.com/finance/net/).
   
2. Środowisko programistyczne: Skonfiguruj środowisko programistyczne za pomocą programu Visual Studio lub innego preferowanego środowiska IDE.
## Importuj przestrzenie nazw
Pamiętaj, aby zaimportować niezbędne przestrzenie nazw do kodu C#:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Krok 1: Zdefiniuj katalogi źródłowe i wyjściowe
Przed kontynuowaniem określ katalogi źródłowy i wyjściowy, w których będą odpowiednio zlokalizowane i zapisane pliki XBRL.
```csharp
// Katalog źródłowy
string sourceDir = "Your Source Directory";
// Katalog wyjściowy
string outputDir = "Your Output Directory";
```
## Krok 2: Utwórz dokument XBRL
 Utwórz instancję`XbrlDocument` sprzeciw do pracy z danymi XBRL.
```csharp
XbrlDocument document = new XbrlDocument();
```
## Krok 3: Uzyskaj dostęp do kolekcji XbrlInstance
Uzyskaj dostęp do kolekcji instancji XBRL w dokumencie.
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
```
## Krok 4: Dodaj XbrlInstance
Dodaj nową instancję XBRL do kolekcji.
```csharp
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
## Krok 5: Dodaj odniesienie do schematu
Dołącz odwołanie do schematu w instancji XBRL, określając katalog źródłowy, przedrostek przestrzeni nazw i identyfikator URI.
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://przykład.com/xbrl/taxonomy");
```
## Krok 6: Pobierz ArcroleType
 Odzyskaj`ArcroleType` w oparciu o konkretny identyfikator URI.
```csharp
SchemaRef schema = schemaRefs[0];
ArcroleType arcroleType = schema.GetArcroleTypeByURI("http://abc.com/arcrole/footnote-test”);
```
## Krok 7: Dodaj ArcroleReference
 Jeśli`ArcroleType` zostanie znaleziony, utwórz plik`ArcroleReference` i dodaj go do odwołań arcrole instancji XBRL.
```csharp
if (arcroleType != null)
{
    ArcroleReference arcroleReference = new ArcroleReference(arcroleType);
    xbrlInstance.ArcroleReferences.Add(arcroleReference);
}
```
## Krok 8: Zapisz dokument
Zapisz zmodyfikowany dokument XBRL w określonym katalogu wyjściowym.
```csharp
document.Save(outputDir + @"document8.xbrl");
```
## Wniosek
W tym samouczku omówiliśmy, jak dodać odwołanie do roli ARC do dokumentu XBRL przy użyciu Aspose.Finance dla .NET. Postępując zgodnie z tymi instrukcjami krok po kroku i wykorzystując możliwości Aspose.Finance, możesz efektywnie zarządzać danymi XBRL i manipulować nimi, aby spełnić Twoje specyficzne wymagania.
## Często zadawane pytania
### Co to jest XBRL?
XBRL oznacza eXtensible Business Reporting Language, ujednolicony język elektronicznej komunikacji danych biznesowych i finansowych.
### Dlaczego XBRL jest ważny?
XBRL zapewnia spójność, dokładność i efektywność wymiany i analizy informacji finansowych, z korzyścią dla organów regulacyjnych, analityków i przedsiębiorstw.
### Czy Aspose.Finance poradzi sobie ze złożonymi zadaniami XBRL?
Tak, Aspose.Finance oferuje solidną funkcjonalność do pracy z dokumentami XBRL, w tym obsługę złożonych zadań, takich jak odniesienia do ról i zarządzanie taksonomią.
### Czy Aspose.Finance jest kompatybilny z innymi bibliotekami .NET?
Tak, Aspose.Finance bezproblemowo integruje się z innymi bibliotekami .NET, zapewniając szerokie wsparcie w zakresie manipulacji danymi finansowymi i raportowania.
### Gdzie mogę znaleźć dodatkowe wsparcie dla Aspose.Finance?
 Aby uzyskać dodatkowe wsparcie, odwiedź stronę[Strona wsparcia Aspose.Finance](https://forum.aspose.com/c/finance/43).
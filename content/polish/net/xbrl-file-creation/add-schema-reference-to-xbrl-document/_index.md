---
title: Dodaj odniesienie do schematu do dokumentu XBRL
linktitle: Dodaj odniesienie do schematu do dokumentu XBRL
second_title: Aspose.Finance API .NET
description: Dowiedz się, jak dodawać odniesienia do schematu do dokumentów XBRL przy użyciu Aspose.Finance dla .NET. Usprawnij przetwarzanie danych finansowych już dziś!
type: docs
weight: 15
url: /pl/net/xbrl-file-creation/add-schema-reference-to-xbrl-document/
---
## Przedstawiamy Aspose.Finance dla .NET
Aspose.Finance dla .NET to potężna biblioteka zapewniająca kompleksowe funkcje przetwarzania i manipulowania dokumentami i danymi finansowymi w aplikacjach .NET. Niezależnie od tego, czy tworzysz oprogramowanie księgowe, narzędzia do analizy finansowej, czy jakąkolwiek inną aplikację finansową, Aspose.Finance dla .NET oferuje szeroką gamę funkcji usprawniających proces programowania.
## Warunki wstępne
Zanim zaczniesz korzystać z Aspose.Finance dla .NET, upewnij się, że masz skonfigurowane następujące wymagania wstępne:
### 1. Zainstaluj Visual Studio
Upewnij się, że masz zainstalowany program Visual Studio w swoim systemie. Można go pobrać i zainstalować z oficjalnej strony Microsoftu.
### 2. Uzyskaj licencję Aspose.Finance
Aby w pełni wykorzystać możliwości Aspose.Finance dla .NET, musisz nabyć ważną licencję. Możesz kupić licencję od[Tutaj](https://purchase.aspose.com/buy) lub wybierz licencję tymczasową do celów testowych.
### 3. Pobierz i odwołaj się do Aspose.Finance dla .NET
 Pobierz bibliotekę Aspose.Finance dla .NET z[strona z wydaniami](https://releases.aspose.com/finance/net/) i odwołuj się do niego w swoim projekcie .NET.
### 4. Uzyskaj dostęp do dokumentacji i wsparcia
 Patrz[Dokumentacja API](https://reference.aspose.com/finance/net/) aby uzyskać szczegółowe informacje na temat korzystania z Aspose.Finance dla .NET. Dodatkowo możesz zwrócić się o pomoc do społeczności Aspose.Finance na stronie[forum wsparcia](https://forum.aspose.com/c/finance/43).
## Importowanie przestrzeni nazw
Zacznijmy od zaimportowania niezbędnych przestrzeni nazw do projektu .NET:
## Krok 1: Dodaj przestrzeń nazw Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Ta przestrzeń nazw zawiera klasy i metody do pracy z dokumentami i danymi XBRL.
Teraz podzielmy podany przykład na wiele kroków, aby zrozumieć, jak dodać odwołanie do schematu do dokumentu XBRL przy użyciu Aspose.Finance dla .NET.
## Krok 1: Zdefiniuj katalogi źródłowe i wyjściowe
```csharp
// Katalog źródłowy
string sourceDir = "Your Source Directory";
// Katalog wyjściowy
string outputDir = "Your Output Directory";
```
 Zastępować`"Your Source Directory"` I`"Your Output Directory"` rzeczywistymi ścieżkami odpowiednio do katalogów źródłowych i wyjściowych.
## Krok 2: Utwórz dokument XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
Spowoduje to utworzenie nowej instancji dokumentu XBRL.
## Krok 3: Uzyskaj dostęp do instancji XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Spowoduje to pobranie kolekcji instancji XBRL z dokumentu i dodanie do niego nowej instancji.
## Krok 4: Dodaj odniesienie do schematu
```csharp
SchemaRefCollection schemaRefs = xbrlInstance.SchemaRefs;
schemaRefs.Add(sourceDir + @"schema.xsd", "example", "http://przykład.com/xbrl/taxonomy");
```
 Spowoduje to dodanie odniesienia do schematu do instancji XBRL. Zastępować`"schema.xsd"` z rzeczywistą nazwą pliku schematu,`"example"` z odpowiednim przedrostkiem i`"http://example.com/xbrl/taxonomy"` z docelowym identyfikatorem URI przestrzeni nazw.
## Krok 5: Zapisz dokument
```csharp
document.Save(outputDir + @"document2.xbrl");
```
Spowoduje to zapisanie zmodyfikowanego dokumentu XBRL w określonym katalogu wyjściowym.
## Wniosek
Podsumowując, Aspose.Finance dla .NET oferuje solidne rozwiązanie do obsługi dokumentów finansowych i danych w aplikacjach .NET. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz łatwo zintegrować Aspose.Finance ze swoimi projektami i efektywnie manipulować dokumentami XBRL.
## Często zadawane pytania
 (Często Zadawane Pytania)
### 1. Czy mogę używać Aspose.Finance dla .NET bez licencji?
Nie, potrzebujesz ważnej licencji, aby móc korzystać z pełnych funkcji Aspose.Finance dla .NET. Można jednak uzyskać licencję tymczasową do celów testowych.
### 2. Czy Aspose.Finance nadaje się do tworzenia oprogramowania księgowego?
Tak, Aspose.Finance zapewnia kompleksowe funkcjonalności do przetwarzania danych finansowych, dzięki czemu idealnie nadaje się do tworzenia oprogramowania księgowego i powiązanych aplikacji.
### 3. Gdzie mogę znaleźć wsparcie dla Aspose.Finance?
Możesz zwrócić się o pomoc do społeczności Aspose.Finance na oficjalnym forum wsparcia.
### 4. Czy mogę dostosować przedrostek odniesienia do schematu?
Tak, możesz wybrać odpowiedni przedrostek podczas dodawania odniesienia do schematu do dokumentu XBRL przy użyciu Aspose.Finance dla .NET.
### 5. Czy Aspose.Finance obsługuje inne formaty finansowe oprócz XBRL?
Tak, Aspose.Finance obsługuje różne formaty i standardy finansowe, umożliwiając bezproblemową integrację z różnorodnymi aplikacjami finansowymi.
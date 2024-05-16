---
title: Dodaj jednostkę do dokumentu XBRL
linktitle: Dodaj jednostkę do dokumentu XBRL
second_title: Aspose.Finance API .NET
description: Dowiedz się, jak bez wysiłku dodawać jednostki do dokumentów XBRL za pomocą Aspose.Finance dla .NET. Zwiększ swoje możliwości przetwarzania danych finansowych już dziś!
type: docs
weight: 16
url: /pl/net/xbrl-file-creation/add-unit-to-xbrl-document/
---
Witamy w świecie Aspose.Finance dla .NET - Twojej bramy do wydajnej manipulacji dokumentami finansowymi w aplikacjach .NET. Niezależnie od tego, czy tworzysz oprogramowanie księgowe, narzędzia do analizy finansowej, czy jakąkolwiek inną aplikację finansową, Aspose.Finance dla .NET zapewnia kompleksowy zestaw funkcji usprawniających proces programowania.
## Warunki wstępne
Zanim zagłębimy się w wykorzystanie mocy Aspose.Finance dla .NET, upewnijmy się, że mamy niezbędne warunki wstępne:
### 1. Instalacja Visual Studio
Upewnij się, że masz zainstalowany program Visual Studio w swoim systemie. Jeśli nie, możesz pobrać i zainstalować go z oficjalnej strony Microsoft.
### 2. Uzyskaj licencję
 Aby odblokować pełny potencjał Aspose.Finance dla .NET, potrzebujesz ważnej licencji. Możesz kupić licencję od[Tutaj](https://purchase.aspose.com/buy) lub wybierz licencję tymczasową do celów testowych.
### 3. Pobierz i odwołaj się do Aspose.Finance dla .NET
 Pobierz bibliotekę Aspose.Finance dla .NET z[strona z wydaniami](https://releases.aspose.com/finance/net/) i odwołuj się do niego w swoim projekcie .NET.
### 4. Uzyskaj dostęp do dokumentacji i wsparcia
 Patrz[dokumentacja](https://reference.aspose.com/finance/net/)aby uzyskać szczegółowe informacje na temat wykorzystania Aspose.Finance dla .NET. Dodatkowo możesz zwrócić się o pomoc do społeczności Aspose.Finance na stronie[forum wsparcia](https://forum.aspose.com/c/finance/43).
## Importowanie przestrzeni nazw
Teraz zaimportujmy niezbędne przestrzenie nazw do projektu .NET:
## Krok 1: Dodaj przestrzeń nazw Aspose.Finance
```csharp
using Aspose.Finance.Xbrl;
using System;
```
Ta przestrzeń nazw zawiera klasy i metody niezbędne do pracy z dokumentami i danymi XBRL.
Podzielmy podany przykład na wiele kroków, aby zrozumieć, jak dodać jednostkę do dokumentu XBRL przy użyciu Aspose.Finance dla .NET.
## Krok 1: Zdefiniuj katalog wyjściowy
```csharp
// Katalog wyjściowy
string outputDir = "Your Output Directory";
```
 Zastępować`"Your Output Directory"` z rzeczywistą ścieżką do żądanego katalogu wyjściowego.
## Krok 2: Utwórz dokument XBRL
```csharp
XbrlDocument document = new XbrlDocument();
```
Spowoduje to inicjowanie nowej instancji dokumentu XBRL.
## Krok 3: Uzyskaj dostęp do instancji XBRL
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Spowoduje to pobranie kolekcji instancji XBRL z dokumentu i dodanie do niego nowej instancji.
## Krok 4: Dodaj jednostkę
```csharp
Unit unit = new Unit(UnitType.Measure);
unit.MeasureQualifiedNames.Add(new QualifiedName("USD", "iso4217", "http://www.xbrl.org/2003/iso4217"));
xbrlInstance.Units.Add(unit);
```
Spowoduje to utworzenie nowej jednostki miary (w tym przypadku USD) i dodanie jej do instancji XBRL. W razie potrzeby możesz dostosować kod waluty i identyfikator URI przestrzeni nazw.
## Krok 5: Zapisz dokument
```csharp
document.Save(outputDir + @"document4.xbrl");
```
Spowoduje to zapisanie zmodyfikowanego dokumentu XBRL w określonym katalogu wyjściowym.
## Wniosek
Podsumowując, Aspose.Finance dla .NET umożliwia programistom łatwe manipulowanie dokumentami finansowymi i danymi w aplikacjach .NET. Wykonując kroki opisane w tym samouczku, możesz bezproblemowo zintegrować Aspose.Finance dla .NET ze swoimi projektami i zwiększyć ich możliwości przetwarzania finansowego.
## Często zadawane pytania
### 1. Czy mogę używać Aspose.Finance dla .NET bez licencji?
Nie, do odblokowania pełnych funkcji Aspose.Finance dla .NET wymagana jest ważna licencja. Jednakże do celów testowych dostępne są licencje tymczasowe.
### 2. Czy Aspose.Finance dla .NET nadaje się do tworzenia oprogramowania księgowego?
Tak, Aspose.Finance dla .NET zapewnia solidne funkcjonalności dostosowane do tworzenia oprogramowania księgowego i powiązanych aplikacji finansowych.
### 3. Gdzie mogę znaleźć wsparcie dla Aspose.Finance dla .NET?
Możesz zwrócić się o pomoc do społeczności Aspose.Finance na forum wsparcia.
### 4. Czy mogę dostosować jednostkę miary w dokumencie XBRL?
Tak, możesz tworzyć i dodawać niestandardowe jednostki miary do dokumentów XBRL za pomocą Aspose.Finance dla .NET.
### 5. Czy Aspose.Finance dla .NET obsługuje wiele walut?
Tak, Aspose.Finance dla .NET obsługuje wiele walut, umożliwiając wszechstronne przetwarzanie danych finansowych.
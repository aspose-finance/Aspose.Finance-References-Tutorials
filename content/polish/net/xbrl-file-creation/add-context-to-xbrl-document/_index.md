---
title: Dodaj kontekst do dokumentu XBRL
linktitle: Dodaj kontekst do dokumentu XBRL
second_title: Aspose.Finance API .NET
description: Dowiedz się, jak dodać kontekst do dokumentów XBRL w .NET przy użyciu Aspose.Finance w celu usprawnienia raportowania finansowego. #Aspose #Finanse #XBRL
type: docs
weight: 11
url: /pl/net/xbrl-file-creation/add-context-to-xbrl-document/
---
## Wstęp
W obszarze sprawozdawczości finansowej kluczową rolę w standaryzacji wymiany informacji biznesowych odgrywa XBRL (eXtensible Business Reporting Language). Dodanie kontekstu do dokumentów XBRL ma kluczowe znaczenie dla zapewnienia integralności i przydatności zawartych w nich danych. Dzięki Aspose.Finance dla .NET proces ten staje się usprawniony i wydajny, umożliwiając programistom płynne włączanie kontekstu do swoich dokumentów XBRL.
## Warunki wstępne
Przed przystąpieniem do samouczka upewnij się, że spełniasz następujące wymagania wstępne:
1. Biblioteka Aspose.Finance dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Finance dla .NET z[wydania](https://releases.aspose.com/finance/net/).
2. Środowisko programistyczne .NET: Upewnij się, że na komputerze jest skonfigurowane działające środowisko programistyczne .NET.
3. Podstawowa znajomość języka C#: Znajomość języka programowania C# będzie pomocna w podążaniu za przykładami.
## Importuj przestrzenie nazw
W swoim projekcie C# zaimportuj niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności zapewnianych przez Aspose.Finance dla .NET:
```csharp
using Aspose.Finance.Xbrl;
using System;
```
## Krok 1: Ustaw katalog wyjściowy
Przed dodaniem kontekstu do dokumentu XBRL określ katalog wyjściowy, w którym zostanie zapisany zmodyfikowany dokument:
```csharp
string outputDir = "Your Output Directory";
```
 Zastępować`"Your Output Directory"` z żądaną ścieżką w systemie.
## Krok 2: Utwórz dokument XBRL
 Utwórz instancję`XbrlDocument` obiekt do pracy z dokumentami XBRL:
```csharp
XbrlDocument document = new XbrlDocument();
```
Obiekt ten reprezentuje dokument XBRL, który będzie poddany manipulacji.
## Krok 3: Dodaj instancję XBRL
Dodaj instancję XBRL do dokumentu. Każda instancja zawiera dane za konkretny okres raportowania:
```csharp
XbrlInstanceCollection xbrlInstances = document.XbrlInstances;
XbrlInstance xbrlInstance = xbrlInstances[xbrlInstances.Add()];
```
Ten krok inicjuje instancję XBRL w dokumencie.
## Krok 4: Zdefiniuj okres kontekstu i jednostkę
Utwórz okres kontekstu i encję dla instancji XBRL:
```csharp
ContextPeriod contextPeriod = new ContextPeriod(DateTime.Parse("2020-01-01"), DateTime.Parse("2020-02-10"));
ContextEntity contextEntity = new ContextEntity("exampleIdentifierScheme", "exampleIdentifier");
```
Określ okres i szczegóły podmiotu zgodnie ze swoimi wymaganiami dotyczącymi raportowania.
## Krok 5: Utwórz kontekst
Zbuduj kontekst, korzystając z okresu i podmiotu zdefiniowanych w poprzednim kroku:
```csharp
Context context = new Context(contextPeriod, contextEntity);
```
Kontekst ten obejmuje informacje tymczasowe i związane z jednostką.
## Krok 6: Dodaj kontekst do instancji XBRL
Powiąż kontekst utworzony w poprzednim kroku z instancją XBRL:
```csharp
xbrlInstance.Contexts.Add(context);
```
Ten krok łączy kontekst z instancją XBRL, dostarczając odpowiednie informacje kontekstowe do danych.
## Krok 7: Zapisz dokument
Zapisz zmodyfikowany dokument XBRL w określonym katalogu wyjściowym:
```csharp
document.Save(outputDir + @"document3.xbrl");
```
To kończy proces i zapisuje dokument XBRL z dodanym kontekstem.
## Wniosek
Wykonując poniższe kroki, możesz skutecznie dodać kontekst do dokumentów XBRL przy użyciu Aspose.Finance dla .NET. Zwiększa to przejrzystość i użyteczność danych finansowych, ułatwiając dokładne analizy i raportowanie.
## Często zadawane pytania
### Czy Aspose.Finance dla .NET obsługuje duże dokumenty XBRL?
Aspose.Finance dla .NET jest zoptymalizowany do obsługi dokumentów XBRL o różnych rozmiarach, w tym dużych zbiorów danych.
### Czy dostępna jest wersja próbna Aspose.Finance dla .NET?
Tak, możesz pobrać bezpłatną wersję próbną z oficjalnej strony Aspose.
### Czy Aspose.Finance dla .NET obsługuje inne standardy raportowania finansowego oprócz XBRL?
Aspose.Finance koncentruje się przede wszystkim na funkcjonalnościach związanych z XBRL, ale zapewnia także obsługę innych formatów finansowych.
### Czy mogę dostosować informacje kontekstowe zgodnie z moimi konkretnymi wymaganiami?
Absolutnie Aspose.Finance dla .NET oferuje elastyczność dostosowywania informacji kontekstowych do własnych potrzeb.
### Gdzie mogę znaleźć dodatkowe wsparcie lub zasoby dla Aspose.Finance dla .NET?
Możesz odwiedzić forum Aspose.Finance, aby uzyskać pomoc społeczności lub zapoznać się z dokumentacją w celu uzyskania kompleksowych wskazówek.